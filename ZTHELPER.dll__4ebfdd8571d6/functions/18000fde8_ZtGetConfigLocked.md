# ZtGetConfigLocked

- ea: `0x18000fde8`
- end: `0x18000ff4a`
- name: `ZtGetConfigLocked`
- size: `354`
- prototype: `__int64 __fastcall(int, int, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180004310`
- `0x180004e18`
- `0x18000e080`

## callees

- `0x180004218`
- `0x18000fde8`
- `0x180015008`
- `0x1800152b0`
- `0x1800162f4`

## pseudocode

```c
__int64 __fastcall ZtGetConfigLocked(int a1, int a2, __int64 a3)
{
  __int64 v4; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  USHORT v9; // dx
  __int64 v11; // [rsp+20h] [rbp-58h]

  v4 = a1;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dq(1035, 0x10u, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, a1, a3);
  WxZeroOut<_DNS_ZT_CONFIG>((_BYTE *)a3);
  if ( !a3 )
  {
    v8 = 87;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    v8 = 5023;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      return v8;
    v9 = 17;
LABEL_13:
    WPP_SF_d(1035, v9, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v8);
    goto LABEL_14;
  }
  if ( (unsigned int)v4 > 1 )
  {
    v8 = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      return v8;
    v9 = 18;
    goto LABEL_13;
  }
  v8 = 0;
  *(_OWORD *)a3 = *(_OWORD *)&g_rgZtConfig[7 * v4];
  *(_OWORD *)(a3 + 16) = *(_OWORD *)&g_rgZtConfig[7 * v4 + 2];
  *(_OWORD *)(a3 + 32) = *(_OWORD *)&g_rgZtConfig[7 * v4 + 4];
  *(_QWORD *)(a3 + 48) = g_rgZtConfig[7 * v4 + 6];
  if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
    return v8;
  LODWORD(v11) = *(_DWORD *)(a3 + 16);
  WPP_SF_ddllllldddd(
    56 * v4,
    v6,
    v7,
    v4,
    v11,
    *(_DWORD *)(a3 + 20),
    *(_DWORD *)(a3 + 24),
    *(_DWORD *)(a3 + 28),
    *(_DWORD *)(a3 + 32),
    *(_DWORD *)(a3 + 36),
    *(_DWORD *)(a3 + 40),
    *(_DWORD *)(a3 + 44),
    *(_DWORD *)(a3 + 48),
    *(_DWORD *)(a3 + 52));
LABEL_14:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x14u, (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000fde8  mov     [rsp+arg_0], rbx
0x18000fded  mov     [rsp+arg_8], rsi
0x18000fdf2  push    rdi
0x18000fdf3  sub     rsp, 70h
0x18000fdf7  mov     rdi, r8
0x18000fdfa  movsxd  rsi, ecx
0x18000fdfd  mov     ebx, edx
0x18000fdff  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fe06  jz      short loc_18000FE26
0x18000fe08  mov     [rsp+78h+var_58], r8
0x18000fe0d  mov     edx, 10h
0x18000fe12  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000fe19  mov     ecx, 40Bh
0x18000fe1e  mov     r9d, esi
0x18000fe21  call    WPP_SF_dq
0x18000fe26  mov     rcx, rdi
0x18000fe29  call    ??$WxZeroOut@U_DNS_ZT_CONFIG@@@@YAXPEAU_DNS_ZT_CONFIG@@@Z; WxZeroOut<_DNS_ZT_CONFIG>(_DNS_ZT_CONFIG *)
0x18000fe2e  test    rdi, rdi
0x18000fe31  jnz     short loc_18000FE3B
0x18000fe33  lea     ebx, [rdi+57h]
0x18000fe36  jmp     loc_18000FF14
0x18000fe3b  test    ebx, ebx
0x18000fe3d  jz      loc_18000FEED
0x18000fe43  cmp     esi, 1
0x18000fe46  ja      loc_18000FEDA
0x18000fe4c  lea     rax, g_rgZtConfig
0x18000fe53  xor     ebx, ebx
0x18000fe55  imul    rcx, rsi, 38h ; '8'
0x18000fe59  movups  xmm0, xmmword ptr [rcx+rax]
0x18000fe5d  movups  xmmword ptr [rdi], xmm0
0x18000fe60  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x18000fe65  movups  xmmword ptr [rdi+10h], xmm1
0x18000fe69  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x18000fe6e  movups  xmmword ptr [rdi+20h], xmm0
0x18000fe72  movsd   xmm1, qword ptr [rcx+rax+30h]
0x18000fe78  movsd   qword ptr [rdi+30h], xmm1
0x18000fe7d  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fe84  jz      loc_18000FF36
0x18000fe8a  mov     eax, [rdi+34h]
0x18000fe8d  mov     r9d, esi
0x18000fe90  mov     [rsp+78h+var_10], eax
0x18000fe94  mov     eax, [rdi+30h]
0x18000fe97  mov     [rsp+78h+var_18], eax
0x18000fe9b  mov     eax, [rdi+2Ch]
0x18000fe9e  mov     [rsp+78h+var_20], eax
0x18000fea2  mov     eax, [rdi+28h]
0x18000fea5  mov     [rsp+78h+var_28], eax
0x18000fea9  mov     eax, [rdi+24h]
0x18000feac  mov     [rsp+78h+var_30], eax
0x18000feb0  mov     eax, [rdi+20h]
0x18000feb3  mov     [rsp+78h+var_38], eax
0x18000feb7  mov     eax, [rdi+1Ch]
0x18000feba  mov     [rsp+78h+var_40], eax
0x18000febe  mov     eax, [rdi+18h]
0x18000fec1  mov     [rsp+78h+var_48], eax
0x18000fec5  mov     eax, [rdi+14h]
0x18000fec8  mov     [rsp+78h+var_50], eax
0x18000fecc  mov     eax, [rdi+10h]
0x18000fecf  mov     dword ptr [rsp+78h+var_58], eax
0x18000fed3  call    WPP_SF_ddllllldddd
0x18000fed8  jmp     short loc_18000FF14
0x18000feda  mov     ebx, 57h ; 'W'
0x18000fedf  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fee6  jz      short loc_18000FF36
0x18000fee8  lea     edx, [rbx-45h]
0x18000feeb  jmp     short loc_18000FF00
0x18000feed  mov     ebx, 139Fh
0x18000fef2  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000fef9  jz      short loc_18000FF36
0x18000fefb  mov     edx, 11h
0x18000ff00  mov     r9d, ebx
0x18000ff03  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000ff0a  mov     ecx, 40Bh
0x18000ff0f  call    WPP_SF_d
0x18000ff14  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ff1b  jz      short loc_18000FF36
0x18000ff1d  mov     edx, 14h
0x18000ff22  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x18000ff29  mov     ecx, 40Bh
0x18000ff2e  mov     r9d, ebx
0x18000ff31  call    WPP_SF_d
0x18000ff36  lea     r11, [rsp+78h+var_8]
0x18000ff3b  mov     eax, ebx
0x18000ff3d  mov     rbx, [r11+10h]
0x18000ff41  mov     rsi, [r11+18h]
0x18000ff45  mov     rsp, r11
0x18000ff48  pop     rdi
0x18000ff49  retn
```

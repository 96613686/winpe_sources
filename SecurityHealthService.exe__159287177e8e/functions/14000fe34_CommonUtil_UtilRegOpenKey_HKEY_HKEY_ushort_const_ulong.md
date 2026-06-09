# CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)

- ea: `0x14000fe34`
- end: `0x14000ff49`
- name: `?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z`
- size: `277`
- prototype: `__int64 __fastcall(CommonUtil *this, HKEY *, const WCHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007384`

## callees

- `0x140005394`
- `0x1400071c0`
- `0x14000fe34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fe72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fe72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000feb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ff19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000feb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ff19`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegOpenKey(CommonUtil *this, HKEY *a2, const WCHAR *a3, const unsigned __int16 *a4)
{
  int v6; // ebx
  bool v8; // sf
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, (REGSAM)a4, &hKey);
  if ( v6 == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_473dbbf2212f33a3d422106396b3062c_Traceguids, a3);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  else
  {
    if ( !v6 )
      goto LABEL_18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_473dbbf2212f33a3d422106396b3062c_Traceguids,
        (_DWORD)a3,
        v6);
    v8 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v8 = v6 < 0;
    }
    if ( v8 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v6;
    }
    else
    {
LABEL_18:
      if ( hKey )
      {
        *(_QWORD *)this = hKey;
        return 0;
      }
      else
      {
        return 2147549183LL;
      }
    }
  }
}

```

## disassembly

```asm
0x14000fe34  mov     r11, rsp
0x14000fe37  mov     [r11+8], rbx
0x14000fe3b  mov     [r11+18h], rsi
0x14000fe3f  mov     [r11+10h], rdx
0x14000fe43  push    rdi
0x14000fe44  sub     rsp, 30h
0x14000fe48  mov     rdi, r8
0x14000fe4b  mov     qword ptr [rcx], 0
0x14000fe52  mov     rsi, rcx
0x14000fe55  mov     qword ptr [r11+10h], 0
0x14000fe5d  lea     rax, [r11+10h]
0x14000fe61  mov     rdx, rdi; lpSubKey
0x14000fe64  xor     r8d, r8d; ulOptions
0x14000fe67  mov     [r11-18h], rax
0x14000fe6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fe72  call    cs:__imp_RegOpenKeyExW
0x14000fe78  mov     ebx, eax
0x14000fe7a  cmp     eax, 2
0x14000fe7d  jnz     short loc_14000FEC5
0x14000fe7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe86  lea     rax, WPP_GLOBAL_Control
0x14000fe8d  cmp     rcx, rax
0x14000fe90  jz      short loc_14000FEAE
0x14000fe92  test    byte ptr [rcx+1Ch], 10h
0x14000fe96  jz      short loc_14000FEAE
0x14000fe98  mov     rcx, [rcx+10h]
0x14000fe9c  lea     edx, [rbx+8]
0x14000fe9f  mov     r9, rdi
0x14000fea2  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000fea9  call    WPP_SF_S
0x14000feae  mov     rcx, [rsp+38h+hKey]; hKey
0x14000feb3  test    rcx, rcx
0x14000feb6  jz      short loc_14000FEBE
0x14000feb8  call    cs:__imp_RegCloseKey
0x14000febe  mov     eax, 80070002h
0x14000fec3  jmp     short loc_14000FF39
0x14000fec5  test    ebx, ebx
0x14000fec7  jz      short loc_14000FF23
0x14000fec9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fed0  lea     rax, WPP_GLOBAL_Control
0x14000fed7  cmp     rcx, rax
0x14000feda  jz      short loc_14000FEFE
0x14000fedc  test    byte ptr [rcx+1Ch], 1
0x14000fee0  jz      short loc_14000FEFE
0x14000fee2  mov     rcx, [rcx+10h]
0x14000fee6  lea     r8, WPP_473dbbf2212f33a3d422106396b3062c_Traceguids
0x14000feed  mov     edx, 0Bh
0x14000fef2  mov     [rsp+38h+var_18], ebx
0x14000fef6  mov     r9, rdi
0x14000fef9  call    WPP_SF_Sd
0x14000fefe  test    ebx, ebx
0x14000ff00  jle     short loc_14000FF0D
0x14000ff02  movzx   ebx, bx
0x14000ff05  or      ebx, 80070000h
0x14000ff0b  test    ebx, ebx
0x14000ff0d  jns     short loc_14000FF23
0x14000ff0f  mov     rcx, [rsp+38h+hKey]; hKey
0x14000ff14  test    rcx, rcx
0x14000ff17  jz      short loc_14000FF1F
0x14000ff19  call    cs:__imp_RegCloseKey
0x14000ff1f  mov     eax, ebx
0x14000ff21  jmp     short loc_14000FF39
0x14000ff23  mov     rax, [rsp+38h+hKey]
0x14000ff28  test    rax, rax
0x14000ff2b  jnz     short loc_14000FF34
0x14000ff2d  mov     eax, 8000FFFFh
0x14000ff32  jmp     short loc_14000FF39
0x14000ff34  mov     [rsi], rax
0x14000ff37  xor     eax, eax
0x14000ff39  mov     rbx, [rsp+38h+arg_0]
0x14000ff3e  mov     rsi, [rsp+38h+arg_10]
0x14000ff43  add     rsp, 30h
0x14000ff47  pop     rdi
0x14000ff48  retn
```

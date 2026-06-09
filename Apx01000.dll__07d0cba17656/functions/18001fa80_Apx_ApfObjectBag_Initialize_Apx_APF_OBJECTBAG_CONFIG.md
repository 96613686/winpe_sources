# Apx::ApfObjectBag::Initialize(Apx::_APF_OBJECTBAG_CONFIG *)

- ea: `0x18001fa80`
- end: `0x18001fc53`
- name: `?Initialize@ApfObjectBag@Apx@@AEAAJPEAU_APF_OBJECTBAG_CONFIG@2@@Z`
- size: `467`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct Apx::_APF_OBJECTBAG_CONFIG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800203ac`

## callees

- `0x180001d30`
- `0x18000a12c`
- `0x18001051c`
- `0x18001fa80`
- `0x1800205f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001fb3f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001fb3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fb67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fb67`

## string_xrefs

- `0x18001fb0a`: `\REGISTRY\MACHINE\`

## pseudocode

```c
__int64 __fastcall Apx::ApfObjectBag::Initialize(unsigned __int64 this, struct Apx::_APF_OBJECTBAG_CONFIG *a2)
{
  int v4; // ecx
  REGSAM v5; // esi
  bool v6; // zf
  __int64 v7; // rcx
  const WCHAR *v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v15[22]; // [rsp+40h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
  }
  v4 = (*((_DWORD *)a2 + 1) & 1) != 0 ? 0x20019 : 0;
  v5 = ((*((_DWORD *)a2 + 1) & 1) != 0 ? 0x19 : 0) | 0x20006;
  v6 = (*((_BYTE *)a2 + 4) & 2) == 0;
  *(_QWORD *)(this + 40) = *((_QWORD *)a2 + 5);
  if ( v6 )
    v5 = v4;
  v7 = *((_QWORD *)a2 + 1);
  if ( v7 )
  {
    v8 = (const WCHAR *)*((_QWORD *)a2 + 2);
LABEL_11:
    v10 = RegOpenKeyExW((HKEY)v7, v8, 0, v5, (PHKEY)(this + 24));
    if ( v10 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids, ~this, v10);
      }
      *(_DWORD *)(this + 16) |= 1u;
      *(_QWORD *)(this + 32) = *((_QWORD *)a2 + 4);
    }
    v11 = 0;
    goto LABEL_24;
  }
  v9 = *((_QWORD *)a2 + 2);
  v14 = *(_OWORD *)L"\\REGISTRY\\MACHINE\\";
  *(_OWORD *)v15 = *(_OWORD *)L"Y\\MACHINE\\";
  *(_QWORD *)&v15[14] = *(_QWORD *)L"NE\\";
  if ( !(unsigned int)_o__wcsnicmp(v9, &v14, 18) )
  {
    v7 = -2147483646;
    v8 = (const WCHAR *)(*((_QWORD *)a2 + 2) + 36LL);
    goto LABEL_11;
  }
  v11 = -2147024809;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids,
      ~(_DWORD)this,
      *((_QWORD *)a2 + 2),
      87);
LABEL_24:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
    WPP_SF_(v12[2], 20, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
  return v11;
}

```

## disassembly

```asm
0x18001fa80  mov     [rsp+arg_10], rbx
0x18001fa85  push    rbp
0x18001fa86  push    rsi
0x18001fa87  push    rdi
0x18001fa88  sub     rsp, 60h
0x18001fa8c  mov     rax, cs:__security_cookie
0x18001fa93  xor     rax, rsp
0x18001fa96  mov     [rsp+78h+var_20], rax
0x18001fa9b  mov     rdi, rdx
0x18001fa9e  mov     rbx, rcx
0x18001faa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faa8  lea     rbp, WPP_GLOBAL_Control
0x18001faaf  cmp     rcx, rbp
0x18001fab2  jz      short loc_18001FAD5
0x18001fab4  test    byte ptr [rcx+1Ch], 1
0x18001fab8  jz      short loc_18001FAD5
0x18001faba  cmp     byte ptr [rcx+19h], 5
0x18001fabe  jb      short loc_18001FAD5
0x18001fac0  mov     rcx, [rcx+10h]
0x18001fac4  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18001facb  mov     edx, 10h
0x18001fad0  call    WPP_SF_
0x18001fad5  mov     eax, [rdi+4]
0x18001fad8  and     al, 1
0x18001fada  neg     al
0x18001fadc  mov     rax, [rdi+28h]
0x18001fae0  sbb     ecx, ecx
0x18001fae2  and     ecx, 20019h
0x18001fae8  mov     esi, ecx
0x18001faea  or      esi, 20006h
0x18001faf0  test    byte ptr [rdi+4], 2
0x18001faf4  mov     [rbx+28h], rax
0x18001faf8  cmovz   esi, ecx
0x18001fafb  mov     rcx, [rdi+8]
0x18001faff  test    rcx, rcx
0x18001fb02  jz      short loc_18001FB0A
0x18001fb04  mov     rdx, [rdi+10h]
0x18001fb08  jmp     short loc_18001FB58
0x18001fb0a  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\REGISTRY\\MACHINE\\"
0x18001fb11  mov     rcx, [rdi+10h]
0x18001fb15  mov     r8d, 12h
0x18001fb1b  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "Y\\MACHINE\\"
0x18001fb22  lea     rdx, [rsp+78h+var_48]
0x18001fb27  movups  [rsp+78h+var_48], xmm0
0x18001fb2c  movsd   xmm0, qword ptr cs:aRegistryMachin+1Eh; "NE\\"
0x18001fb34  movups  xmmword ptr [rsp+78h+var_38], xmm1
0x18001fb39  movsd   qword ptr [rsp+78h+var_38+0Eh], xmm0
0x18001fb3f  call    cs:__imp__o__wcsnicmp
0x18001fb45  test    eax, eax
0x18001fb47  jnz     short loc_18001FBC2
0x18001fb49  mov     rdx, [rdi+10h]
0x18001fb4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fb54  add     rdx, 24h ; '$'; lpSubKey
0x18001fb58  lea     rax, [rbx+18h]
0x18001fb5c  mov     r9d, esi; samDesired
0x18001fb5f  xor     r8d, r8d; ulOptions
0x18001fb62  mov     [rsp+78h+phkResult], rax; phkResult
0x18001fb67  call    cs:__imp_RegOpenKeyExW
0x18001fb6d  test    eax, eax
0x18001fb6f  jz      short loc_18001FBBE
0x18001fb71  jle     short loc_18001FB7B
0x18001fb73  movzx   eax, ax
0x18001fb76  or      eax, 80070000h
0x18001fb7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb82  cmp     rcx, rbp
0x18001fb85  jz      short loc_18001FBB2
0x18001fb87  test    byte ptr [rcx+1Ch], 20h
0x18001fb8b  jz      short loc_18001FBB2
0x18001fb8d  cmp     byte ptr [rcx+19h], 4
0x18001fb91  jb      short loc_18001FBB2
0x18001fb93  mov     rcx, [rcx+10h]
0x18001fb97  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18001fb9e  mov     r9, rbx
0x18001fba1  mov     dword ptr [rsp+78h+phkResult], eax
0x18001fba5  not     r9
0x18001fba8  mov     edx, 12h
0x18001fbad  call    WPP_SF_qd
0x18001fbb2  or      dword ptr [rbx+10h], 1
0x18001fbb6  mov     rax, [rdi+20h]
0x18001fbba  mov     [rbx+20h], rax
0x18001fbbe  xor     esi, esi
0x18001fbc0  jmp     short loc_18001FC07
0x18001fbc2  mov     esi, 80070057h
0x18001fbc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbce  cmp     rcx, rbp
0x18001fbd1  jz      short loc_18001FC34
0x18001fbd3  test    byte ptr [rcx+1Ch], 20h
0x18001fbd7  jz      short loc_18001FC0E
0x18001fbd9  cmp     byte ptr [rcx+19h], 2
0x18001fbdd  jb      short loc_18001FC0E
0x18001fbdf  mov     rax, [rdi+10h]
0x18001fbe3  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18001fbea  mov     rcx, [rcx+10h]
0x18001fbee  not     rbx
0x18001fbf1  mov     r9, rbx
0x18001fbf4  mov     [rsp+78h+var_50], esi
0x18001fbf8  mov     edx, 11h
0x18001fbfd  mov     [rsp+78h+phkResult], rax
0x18001fc02  call    WPP_SF_qSd
0x18001fc07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc0e  cmp     rcx, rbp
0x18001fc11  jz      short loc_18001FC34
0x18001fc13  test    byte ptr [rcx+1Ch], 1
0x18001fc17  jz      short loc_18001FC34
0x18001fc19  cmp     byte ptr [rcx+19h], 5
0x18001fc1d  jb      short loc_18001FC34
0x18001fc1f  mov     rcx, [rcx+10h]
0x18001fc23  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18001fc2a  mov     edx, 14h
0x18001fc2f  call    WPP_SF_
0x18001fc34  mov     eax, esi
0x18001fc36  mov     rcx, [rsp+78h+var_20]
0x18001fc3b  xor     rcx, rsp; StackCookie
0x18001fc3e  call    __security_check_cookie
0x18001fc43  mov     rbx, [rsp+78h+arg_10]
0x18001fc4b  add     rsp, 60h
0x18001fc4f  pop     rdi
0x18001fc50  pop     rsi
0x18001fc51  pop     rbp
0x18001fc52  retn
```

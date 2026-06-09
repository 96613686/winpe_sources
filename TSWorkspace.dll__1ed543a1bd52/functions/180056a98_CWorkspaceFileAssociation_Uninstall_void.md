# CWorkspaceFileAssociation::Uninstall(void *)

- ea: `0x180056a98`
- end: `0x180056d0d`
- name: `?Uninstall@CWorkspaceFileAssociation@@QEAAJPEAX@Z`
- size: `629`
- prototype: `int(CWorkspaceFileAssociation *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800396d4`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x180020bf0`
- `0x180056a98`
- `0x180056d14`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180056b99`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180056b99`
- `ADVAPI32!RegCloseKey` at `0x180056cf9`
- `ADVAPI32!RegCloseKey` at `0x180056cf9`
- `KERNEL32!RegDeleteTreeW` at `0x180056c23`
- `KERNEL32!RegDeleteTreeW` at `0x180056c23`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspaceFileAssociation::Uninstall(CWorkspaceFileAssociation *this, void *a2)
{
  PVOID *v4; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rbx
  unsigned int v7; // eax
  int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // eax
  const WCHAR *v11; // rax
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  unsigned int v17; // [rsp+40h] [rbp-48h]
  HKEY hKey; // [rsp+A0h] [rbp+18h] BYREF

  hKey = 0;
  if ( (int)CWorkspaceFileAssociation::UnregisterSecondaryHandler(this, a2) >= 0 )
    goto LABEL_6;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
      CurrentThreadActivityIdPrefix);
LABEL_6:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
      v7,
      v6);
  }
LABEL_11:
  v8 = RegOpenKeyTransactedW(HKEY_CURRENT_USER, L"Software\\classes", 0, 0x2001Fu, &hKey, a2, 0);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      else
        v9 = v8;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v10, v9);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v17 = v8;
    goto LABEL_39;
  }
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
  v12 = RegDeleteTreeW(hKey, v11);
  if ( v12 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v13);
    }
    goto LABEL_38;
  }
  if ( !v12 )
  {
LABEL_38:
    v17 = 0;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v12 > 0 )
      v14 = (unsigned __int16)v12 | 0x80070000;
    else
      v14 = v12;
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v15, v14);
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v17 = v12;
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  return v17;
}

```

## disassembly

```asm
0x180056a98  mov     rax, rsp
0x180056a9b  push    rbx
0x180056a9c  push    rsi
0x180056a9d  push    rdi
0x180056a9e  push    r14
0x180056aa0  sub     rsp, 68h
0x180056aa4  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180056aac  mov     r14, rdx
0x180056aaf  mov     rsi, rcx
0x180056ab2  mov     qword ptr [rax+18h], 0
0x180056aba  call    ?UnregisterSecondaryHandler@CWorkspaceFileAssociation@@IEAAJPEAX@Z; CWorkspaceFileAssociation::UnregisterSecondaryHandler(void *)
0x180056abf  mov     [rsp+88h+var_48], eax
0x180056ac3  test    eax, eax
0x180056ac5  jns     short loc_180056B10
0x180056ac7  lea     rdi, WPP_GLOBAL_Control
0x180056ace  mov     rax, cs:WPP_GLOBAL_Control
0x180056ad5  cmp     rax, rdi
0x180056ad8  jz      loc_180056B67
0x180056ade  test    byte ptr [rax+1Ch], 1
0x180056ae2  jz      short loc_180056B1E
0x180056ae4  cmp     byte ptr [rax+19h], 2
0x180056ae8  jb      short loc_180056B1E
0x180056aea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056aef  mov     edx, 41h ; 'A'
0x180056af4  mov     r9d, eax
0x180056af7  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b05  mov     rcx, [rcx+10h]
0x180056b09  call    WPP_SF_D
0x180056b0e  jmp     short loc_180056B17
0x180056b10  lea     rdi, WPP_GLOBAL_Control
0x180056b17  mov     rax, cs:WPP_GLOBAL_Control
0x180056b1e  cmp     rax, rdi
0x180056b21  jz      short loc_180056B67
0x180056b23  test    byte ptr [rax+1Ch], 1
0x180056b27  jz      short loc_180056B67
0x180056b29  cmp     byte ptr [rax+19h], 4
0x180056b2d  jb      short loc_180056B67
0x180056b2f  lea     rcx, [rsi+0D8h]
0x180056b36  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056b3b  mov     rbx, rax
0x180056b3e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056b43  mov     edx, 42h ; 'B'
0x180056b48  mov     [rsp+88h+phkResult], rbx
0x180056b4d  mov     r9d, eax
0x180056b50  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b5e  mov     rcx, [rcx+10h]
0x180056b62  call    WPP_SF_DS
0x180056b67  mov     [rsp+88h+pExtendedParemeter], 0; pExtendedParemeter
0x180056b70  mov     [rsp+88h+hTransaction], r14; hTransaction
0x180056b75  lea     rax, [rsp+88h+hKey]
0x180056b7d  mov     [rsp+88h+phkResult], rax; phkResult
0x180056b82  mov     r9d, 2001Fh; samDesired
0x180056b88  xor     r8d, r8d; ulOptions
0x180056b8b  lea     rdx, aSoftwareClasse; "Software\\classes"
0x180056b92  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180056b99  call    cs:__imp_RegOpenKeyTransactedW
0x180056b9f  mov     ebx, eax
0x180056ba1  test    eax, eax
0x180056ba3  jz      short loc_180056C0C
0x180056ba5  mov     rax, cs:WPP_GLOBAL_Control
0x180056bac  cmp     rax, rdi
0x180056baf  jz      short loc_180056BF6
0x180056bb1  test    byte ptr [rax+1Ch], 8
0x180056bb5  jz      short loc_180056BF6
0x180056bb7  cmp     byte ptr [rax+19h], 2
0x180056bbb  jb      short loc_180056BF6
0x180056bbd  test    ebx, ebx
0x180056bbf  jg      short loc_180056BC5
0x180056bc1  mov     edi, ebx
0x180056bc3  jmp     short loc_180056BCE
0x180056bc5  movzx   edi, bx
0x180056bc8  or      edi, 80070000h
0x180056bce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056bd3  mov     edx, 43h ; 'C'
0x180056bd8  mov     dword ptr [rsp+88h+phkResult], edi
0x180056bdc  mov     r9d, eax
0x180056bdf  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bed  mov     rcx, [rcx+10h]
0x180056bf1  call    WPP_SF_Dd
0x180056bf6  test    ebx, ebx
0x180056bf8  jle     short loc_180056C03
0x180056bfa  movzx   ebx, bx
0x180056bfd  or      ebx, 80070000h
0x180056c03  mov     [rsp+88h+var_48], ebx
0x180056c07  jmp     loc_180056CEC
0x180056c0c  lea     rcx, [rsi+0D8h]
0x180056c13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056c18  mov     rdx, rax; lpSubKey
0x180056c1b  mov     rcx, [rsp+88h+hKey]; hKey
0x180056c23  call    cs:__imp_RegDeleteTreeW
0x180056c29  mov     ebx, eax
0x180056c2b  cmp     eax, 2
0x180056c2e  jnz     short loc_180056C78
0x180056c30  mov     rax, cs:WPP_GLOBAL_Control
0x180056c37  cmp     rax, rdi
0x180056c3a  jz      loc_180056CE0
0x180056c40  test    byte ptr [rax+1Ch], 1
0x180056c44  jz      loc_180056CE0
0x180056c4a  cmp     byte ptr [rax+19h], 5
0x180056c4e  jb      loc_180056CE0
0x180056c54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056c59  lea     edx, [rbx+42h]
0x180056c5c  mov     r9d, eax
0x180056c5f  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c6d  mov     rcx, [rcx+10h]
0x180056c71  call    WPP_SF_D
0x180056c76  jmp     short loc_180056CE0
0x180056c78  test    ebx, ebx
0x180056c7a  jz      short loc_180056CE0
0x180056c7c  mov     rax, cs:WPP_GLOBAL_Control
0x180056c83  cmp     rax, rdi
0x180056c86  jz      short loc_180056CCD
0x180056c88  test    byte ptr [rax+1Ch], 8
0x180056c8c  jz      short loc_180056CCD
0x180056c8e  cmp     byte ptr [rax+19h], 2
0x180056c92  jb      short loc_180056CCD
0x180056c94  test    ebx, ebx
0x180056c96  jg      short loc_180056C9C
0x180056c98  mov     edi, ebx
0x180056c9a  jmp     short loc_180056CA5
0x180056c9c  movzx   edi, bx
0x180056c9f  or      edi, 80070000h
0x180056ca5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056caa  mov     edx, 45h ; 'E'
0x180056caf  mov     dword ptr [rsp+88h+phkResult], edi
0x180056cb3  mov     r9d, eax
0x180056cb6  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180056cc4  mov     rcx, [rcx+10h]
0x180056cc8  call    WPP_SF_Dd
0x180056ccd  test    ebx, ebx
0x180056ccf  jle     short loc_180056CDA
0x180056cd1  movzx   ebx, bx
0x180056cd4  or      ebx, 80070000h
0x180056cda  mov     [rsp+88h+var_48], ebx
0x180056cde  jmp     short loc_180056CEC
0x180056ce0  mov     [rsp+88h+var_48], 0
0x180056ce8  jmp     short loc_180056CEC
0x180056cea  jmp     short $+2
0x180056cec  mov     rcx, [rsp+88h+hKey]; hKey
0x180056cf4  test    rcx, rcx
0x180056cf7  jz      short loc_180056CFF
0x180056cf9  call    cs:__imp_RegCloseKey
0x180056cff  mov     eax, [rsp+88h+var_48]
0x180056d03  add     rsp, 68h
0x180056d07  pop     r14
0x180056d09  pop     rdi
0x180056d0a  pop     rsi
0x180056d0b  pop     rbx
0x180056d0c  retn
```

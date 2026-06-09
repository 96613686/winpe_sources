# Windows::Auto<_ACL>::Assign(_ACL const *)

- ea: `0x18004eb28`
- end: `0x18004ecd6`
- name: `?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f6b0`

## callees

- `0x1800031d0`
- `0x18000693e`
- `0x18000aedc`
- `0x1800497c0`
- `0x18004eb28`

## import_xrefs

- `ntdll!RtlValidAcl` at `0x18004eb69`
- `ntdll!RtlValidAcl` at `0x18004eb69`
- `ntdll!RtlQueryInformationAcl` at `0x18004ebd3`
- `ntdll!RtlQueryInformationAcl` at `0x18004ebd3`
- `ntdll!RtlAllocateHeap` at `0x18004ec3f`
- `ntdll!RtlAllocateHeap` at `0x18004ec3f`

## string_xrefs

- `0x18004eb79`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004ebe5`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004ec53`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004eb93`: `Windows::Auto<struct _ACL>::Assign`
- `0x18004ebff`: `Windows::Auto<struct _ACL>::Assign`
- `0x18004ec6d`: `Windows::Auto<struct _ACL>::Assign`
- `0x18004ec82`: `m_pACL`
- `0x18004eba8`: `pAcl == 0 || ::RtlValidAcl(pAcl)`
- `0x18004ec11`: `::RtlQueryInformationAcl( pAcl, &SizeInfo, sizeof SizeInfo, ::AclSizeInformation)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_ACL>::Assign(_QWORD *a1, struct _ACL *a2)
{
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  PVOID Heap; // rax
  const char *v8; // [rsp+20h] [rbp-40h] BYREF
  const char *v9; // [rsp+28h] [rbp-38h]
  __int64 v10; // [rsp+30h] [rbp-30h]
  const char *v11; // [rsp+38h] [rbp-28h]
  __int64 Information; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+48h] [rbp-18h]

  Information = 0;
  v13 = 0;
  if ( *a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18004ECD5LL);
  }
  if ( a2 )
  {
    if ( !RtlValidAcl(a2) )
    {
      v10 = 980;
      v8 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v9 = "Windows::Auto<struct _ACL>::Assign";
      v11 = "pAcl == 0 || ::RtlValidAcl(pAcl)";
      RtlReportErrorOrigination(&v8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      return 3221225485LL;
    }
    v5 = RtlQueryInformationAcl(a2, &Information, 0xCu, AclSizeInformation);
    v6 = v5;
    if ( v5 < 0 )
    {
      v10 = 988;
      v8 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v9 = "Windows::Auto<struct _ACL>::Assign";
      v11 = "::RtlQueryInformationAcl( pAcl, &SizeInfo, sizeof SizeInfo, ::AclSizeInformation)";
      RtlReportErrorOrigination(&v8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v5);
      return v6;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(HIDWORD(Information) + v13));
    *a1 = Heap;
    if ( !Heap )
    {
      v10 = 995;
      v8 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v9 = "Windows::Auto<struct _ACL>::Assign";
      v11 = "m_pACL";
      RtlReportErrorOrigination(&v8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
      return 3221225495LL;
    }
    memcpy_0(Heap, a2, (unsigned int)(v13 + HIDWORD(Information)));
  }
  return 0;
}

```

## disassembly

```asm
0x18004eb28  mov     [rsp-18h+arg_10], rbx
0x18004eb2d  push    rbp
0x18004eb2e  push    rsi
0x18004eb2f  push    rdi
0x18004eb30  mov     rbp, rsp
0x18004eb33  sub     rsp, 60h
0x18004eb37  mov     rax, cs:__security_cookie
0x18004eb3e  xor     rax, rsp
0x18004eb41  mov     [rbp+var_10], rax
0x18004eb45  xor     eax, eax
0x18004eb47  mov     rbx, rdx
0x18004eb4a  mov     rsi, rcx
0x18004eb4d  mov     [rbp+Information], rax
0x18004eb51  mov     [rbp+var_18], eax
0x18004eb54  cmp     [rcx], rax
0x18004eb57  jnz     loc_18004ECCB
0x18004eb5d  test    rdx, rdx
0x18004eb60  jz      loc_18004ECAC
0x18004eb66  mov     rcx, rdx; Acl
0x18004eb69  call    cs:__imp_RtlValidAcl
0x18004eb70  nop     dword ptr [rax+rax+00h]
0x18004eb75  test    al, al
0x18004eb77  jnz     short loc_18004EBC2
0x18004eb79  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004eb80  mov     [rbp+var_30], 3D4h
0x18004eb88  mov     [rbp+var_40], rax
0x18004eb8c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004eb93  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x18004eb9a  mov     r8d, 0C000000Dh
0x18004eba0  mov     [rbp+var_38], rax
0x18004eba4  lea     rcx, [rbp+var_40]
0x18004eba8  lea     rax, aPacl0Rtlvalida; "pAcl == 0 || ::RtlValidAcl(pAcl)"
0x18004ebaf  mov     [rbp+var_28], rax
0x18004ebb3  call    RtlReportErrorOrigination
0x18004ebb8  mov     eax, 0C000000Dh
0x18004ebbd  jmp     loc_18004ECAE
0x18004ebc2  mov     r9d, 2; InformationClass
0x18004ebc8  lea     rdx, [rbp+Information]; Information
0x18004ebcc  mov     rcx, rbx; Acl
0x18004ebcf  lea     r8d, [r9+0Ah]; InformationLength
0x18004ebd3  call    cs:__imp_RtlQueryInformationAcl
0x18004ebda  nop     dword ptr [rax+rax+00h]
0x18004ebdf  mov     edi, eax
0x18004ebe1  test    eax, eax
0x18004ebe3  jns     short loc_18004EC28
0x18004ebe5  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004ebec  mov     [rbp+var_30], 3DCh
0x18004ebf4  mov     [rbp+var_40], rax
0x18004ebf8  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004ebff  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x18004ec06  mov     r8d, edi
0x18004ec09  mov     [rbp+var_38], rax
0x18004ec0d  lea     rcx, [rbp+var_40]
0x18004ec11  lea     rax, aRtlqueryinform; "::RtlQueryInformationAcl( pAcl, &SizeIn"...
0x18004ec18  mov     [rbp+var_28], rax
0x18004ec1c  call    RtlReportErrorOrigination
0x18004ec21  mov     eax, edi
0x18004ec23  jmp     loc_18004ECAE
0x18004ec28  mov     rcx, gs:60h
0x18004ec31  xor     edx, edx; Flags
0x18004ec33  mov     r8d, [rbp+var_18]
0x18004ec37  add     r8d, dword ptr [rbp+Information+4]; Size
0x18004ec3b  mov     rcx, [rcx+30h]; HeapHandle
0x18004ec3f  call    cs:__imp_RtlAllocateHeap
0x18004ec46  nop     dword ptr [rax+rax+00h]
0x18004ec4b  mov     [rsi], rax
0x18004ec4e  test    rax, rax
0x18004ec51  jnz     short loc_18004EC99
0x18004ec53  lea     rax, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004ec5a  mov     [rbp+var_30], 3E3h
0x18004ec62  mov     [rbp+var_40], rax
0x18004ec66  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004ec6d  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x18004ec74  mov     r8d, 0C0000017h
0x18004ec7a  mov     [rbp+var_38], rax
0x18004ec7e  lea     rcx, [rbp+var_40]
0x18004ec82  lea     rax, aMPacl; "m_pACL"
0x18004ec89  mov     [rbp+var_28], rax
0x18004ec8d  call    RtlReportErrorOrigination
0x18004ec92  mov     eax, 0C0000017h
0x18004ec97  jmp     short loc_18004ECAE
0x18004ec99  mov     r8d, dword ptr [rbp+Information+4]
0x18004ec9d  mov     rdx, rbx; Src
0x18004eca0  add     r8d, [rbp+var_18]; Size
0x18004eca4  mov     rcx, rax; void *
0x18004eca7  call    memcpy_0
0x18004ecac  xor     eax, eax
0x18004ecae  mov     rcx, [rbp+var_10]
0x18004ecb2  xor     rcx, rsp; StackCookie
0x18004ecb5  call    __security_check_cookie
0x18004ecba  mov     rbx, [rsp+60h+arg_10]
0x18004ecc2  add     rsp, 60h
0x18004ecc6  pop     rdi
0x18004ecc7  pop     rsi
0x18004ecc8  pop     rbp
0x18004ecc9  retn
0x18004eccb  mov     ecx, 0C00000E5h; int
0x18004ecd0  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

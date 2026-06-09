# DllRegisterServer

- ea: `0x180056650`
- end: `0x180056804`
- name: `DllRegisterServer`
- size: `436`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180055128`
- `0x1800556e0`
- `0x180055e7c`
- `0x180056650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180056697`
- `KERNEL32!GetLastError` at `0x180056697`
- `KERNEL32!LocalFree` at `0x1800567f2`
- `KERNEL32!LocalFree` at `0x1800567f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180056689`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180056689`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800567e1`
- `RPCRT4!NdrDllRegisterProxy` at `0x1800567e1`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const WCHAR *v0; // rcx
  HRESULT v1; // ebx
  signed int LastError; // eax
  unsigned int v3; // edi
  __int64 v4; // rcx
  int v5; // eax
  _QWORD v7[5]; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+28h] BYREF

  v0 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-3418"
        "522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GA;;;BA)(A;OICIIO;GA;;;BA)(A;;GRGX;;;B"
        "U)(A;OICIIO;GRGX;;;BU)(A;;GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  SecurityDescriptor = 0;
  if ( !byte_18011CF98 )
    v0 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-34"
          "18522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GRGX;;;BU)(A;OICIIO;GRGX;;;BU)(A;;"
          "GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v0, 1u, &SecurityDescriptor, 0) )
  {
    v1 = 0;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_17;
  }
  v7[1] = SecurityDescriptor;
  v3 = 0;
  v7[0] = 24;
  v7[2] = 0;
  while ( v1 >= 0 )
  {
    v4 = 56LL * (int)v3;
    v5 = sub_1800556E0(
           *(__int64 *)((char *)&off_180106110 + v4),
           *(__int64 *)((char *)&off_180106110 + v4 + 8),
           *(__int64 *)((char *)&off_180106110 + v4 + 16),
           *(__int64 *)((char *)&off_180106110 + v4 + 24),
           *((_BYTE *)&off_180106110 + v4 + 40),
           (__int64)v7);
    ++v3;
    v1 = v5;
    if ( v3 >= 0x11 )
    {
      if ( v5 >= 0 )
      {
        v1 = sub_180055128(
               (__int64)L"{7E55A26D-EF95-4A45-9F55-21E52ADF9878}",
               (__int64)L"Interactive User",
               8,
               L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;S-1-1"
                "5-2-2743877165-1931364543-2468930561-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
               (ULONG)L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;S-1-15-2-2743877165-1931364543-24689305"
                       "61-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
               (__int64)v7);
        if ( v1 >= 0 )
        {
          v1 = sub_180055128(
                 (__int64)L"{1D278EEF-5C38-4F2A-8C7D-D5C13B662567}",
                 (__int64)L"Interactive User",
                 520,
                 L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;S-1"
                  "-15-2-2743877165-1931364543-2468930561-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
                 (ULONG)L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;S-1-15-2-2743877165-1931364543-246893"
                         "0561-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
                 (__int64)v7);
          if ( v1 >= 0 )
          {
            v1 = sub_180055128(
                   (__int64)L"{37096FBE-2F09-4FF6-8507-C6E4E1179839}",
                   0,
                   8,
                   L"O:BAG:BAD:(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)S:(ML;;NX;;;LW)",
                   (ULONG)L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;S-1-15-2-2743877165-1931364543-2468"
                           "930561-3765762410-1162139025-1178895811-1086226821)S:(ML;;NX;;;LW)",
                   (__int64)v7);
            if ( v1 >= 0 )
            {
              v1 = sub_180055E7C();
              if ( v1 >= 0 )
                v1 = NdrDllRegisterProxy(hDll, (const ProxyFileInfo **)&pProxyFileList, &pclsid);
            }
          }
        }
      }
      break;
    }
  }
LABEL_17:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x180056650  push    rbp
0x180056652  push    rbx
0x180056653  push    rdi
0x180056654  push    r14
0x180056656  mov     rbp, rsp
0x180056659  sub     rsp, 58h
0x18005665d  cmp     cs:byte_18011CF98, 0
0x180056664  lea     rax, aDPAGaS15809560; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x18005666b  lea     rcx, aDPAGaS15809560_0; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x180056672  mov     [rbp+SecurityDescriptor], 0
0x18005667a  cmovz   rcx, rax; StringSecurityDescriptor
0x18005667e  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180056682  xor     r9d, r9d; SecurityDescriptorSize
0x180056685  lea     edx, [r9+1]; StringSDRevision
0x180056689  call    cs:ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005668f  test    eax, eax
0x180056691  jz      short loc_180056697
0x180056693  xor     ebx, ebx
0x180056695  jmp     short loc_1800566B4
0x180056697  call    cs:GetLastError
0x18005669d  mov     ebx, eax
0x18005669f  test    eax, eax
0x1800566a1  jle     short loc_1800566AC
0x1800566a3  movzx   ebx, ax
0x1800566a6  or      ebx, 80070000h
0x1800566ac  test    ebx, ebx
0x1800566ae  js      loc_1800567E9
0x1800566b4  mov     rax, [rbp+SecurityDescriptor]
0x1800566b8  lea     r14, off_180106110
0x1800566bf  mov     [rbp+var_20], rax
0x1800566c3  xor     edi, edi
0x1800566c5  mov     [rbp+var_28], 18h
0x1800566cd  mov     [rbp+var_18], 0
0x1800566d5  test    ebx, ebx
0x1800566d7  js      loc_1800567E9
0x1800566dd  movsxd  rax, edi
0x1800566e0  imul    rcx, rax, 38h ; '8'
0x1800566e4  lea     rax, [rbp+var_28]
0x1800566e8  mov     [rsp+58h+var_30], rax
0x1800566ed  mov     al, [rcx+r14+28h]
0x1800566f2  mov     r9, [rcx+r14+18h]
0x1800566f7  mov     r8, [rcx+r14+10h]
0x1800566fc  mov     rdx, [rcx+r14+8]
0x180056701  mov     rcx, [rcx+r14]
0x180056705  mov     byte ptr [rsp+58h+var_38], al
0x180056709  call    sub_1800556E0
0x18005670e  inc     edi
0x180056710  mov     ebx, eax
0x180056712  cmp     edi, 11h
0x180056715  jb      short loc_1800566D5
0x180056717  test    eax, eax
0x180056719  js      loc_1800567E9
0x18005671f  lea     rax, [rbp+var_28]
0x180056723  mov     r14d, 8
0x180056729  mov     [rsp+58h+var_30], rax
0x18005672e  lea     rdi, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x180056735  mov     r8d, r14d
0x180056738  mov     [rsp+58h+var_38], rdi
0x18005673d  lea     r9, aOBagBadACcdclc; "O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCL"...
0x180056744  lea     rdx, aInteractiveUse; "Interactive User"
0x18005674b  lea     rcx, a7e55a26dEf954a; "{7E55A26D-EF95-4A45-9F55-21E52ADF9878}"
0x180056752  call    sub_180055128
0x180056757  mov     ebx, eax
0x180056759  test    eax, eax
0x18005675b  js      loc_1800567E9
0x180056761  lea     rax, [rbp+var_28]
0x180056765  mov     r8d, 208h
0x18005676b  mov     [rsp+58h+var_30], rax
0x180056770  lea     r9, aOBagBadACcdclc; "O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCL"...
0x180056777  lea     rdx, aInteractiveUse; "Interactive User"
0x18005677e  mov     [rsp+58h+var_38], rdi
0x180056783  lea     rcx, a1d278eef5c384f; "{1D278EEF-5C38-4F2A-8C7D-D5C13B662567}"
0x18005678a  call    sub_180055128
0x18005678f  mov     ebx, eax
0x180056791  test    eax, eax
0x180056793  js      short loc_1800567E9
0x180056795  lea     rax, [rbp+var_28]
0x180056799  mov     r8d, r14d
0x18005679c  mov     [rsp+58h+var_30], rax
0x1800567a1  lea     r9, aOBagBadACcdclc_0; "O:BAG:BAD:(A;;CCDCLCSWRP;;;BA)(A;;CCDCL"...
0x1800567a8  xor     edx, edx
0x1800567aa  mov     [rsp+58h+var_38], rdi
0x1800567af  lea     rcx, a37096fbe2f094f; "{37096FBE-2F09-4FF6-8507-C6E4E1179839}"
0x1800567b6  call    sub_180055128
0x1800567bb  mov     ebx, eax
0x1800567bd  test    eax, eax
0x1800567bf  js      short loc_1800567E9
0x1800567c1  call    sub_180055E7C
0x1800567c6  mov     ebx, eax
0x1800567c8  test    eax, eax
0x1800567ca  js      short loc_1800567E9
0x1800567cc  mov     rcx, cs:hDll; hDll
0x1800567d3  lea     r8, pclsid; pclsid
0x1800567da  lea     rdx, pProxyFileList; pProxyFileList
0x1800567e1  call    cs:NdrDllRegisterProxy
0x1800567e7  mov     ebx, eax
0x1800567e9  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800567ed  test    rcx, rcx
0x1800567f0  jz      short loc_1800567F8
0x1800567f2  call    cs:__imp_LocalFree
0x1800567f8  mov     eax, ebx
0x1800567fa  add     rsp, 58h
0x1800567fe  pop     r14
0x180056800  pop     rdi
0x180056801  pop     rbx
0x180056802  pop     rbp
0x180056803  retn
```

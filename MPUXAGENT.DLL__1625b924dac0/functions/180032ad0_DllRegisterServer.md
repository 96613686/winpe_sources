# DllRegisterServer

- ea: `0x180032ad0`
- end: `0x180032c3b`
- name: `DllRegisterServer`
- size: `363`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800095a0`
- `0x180031784`
- `0x180031bbc`
- `0x180032ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180032c16`
- `KERNEL32!LocalFree` at `0x180032c16`
- `KERNEL32!GetLastError` at `0x180032b29`
- `KERNEL32!GetLastError` at `0x180032b29`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032b1b`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032b1b`
- `RPCRT4!NdrDllRegisterProxy` at `0x180032c04`
- `RPCRT4!NdrDllRegisterProxy` at `0x180032c04`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const WCHAR *v0; // rcx
  HRESULT v1; // ebx
  signed int LastError; // eax
  wchar_t **v3; // rdi
  int v4; // esi
  int v5; // eax
  __int64 v6; // r8
  const wchar_t *v7; // rcx
  const wchar_t *v8; // r9
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL v11; // [rsp+38h] [rbp-30h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF

  v0 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-3418"
        "522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GA;;;BA)(A;OICIIO;GA;;;BA)(A;;GRGX;;;B"
        "U)(A;OICIIO;GRGX;;;BU)(A;;GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  hMem = 0;
  if ( !byte_18009AA60 )
    v0 = L"D:P(A;;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;OICIIO;GA;;;S-1-5-80-956008885-34"
          "18522649-1831038044-1853292631-2271478464)(A;;GA;;;SY)(A;OICIIO;GA;;;SY)(A;;GRGX;;;BU)(A;OICIIO;GRGX;;;BU)(A;;"
          "GRGX;;;AC)(A;OICIIO;GRGX;;;AC)";
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v0, 1u, &hMem, 0) )
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
      goto LABEL_18;
  }
  v3 = &off_180096E88;
  v11 = hMem;
  v4 = 0;
  v10 = 24;
  v12 = 0;
  while ( v1 >= 0 )
  {
    v5 = sub_180031BBC(
           (unsigned int)*(v3 - 3),
           (unsigned int)*(v3 - 2),
           (unsigned int)*(v3 - 1),
           (unsigned int)*v3,
           *((_BYTE *)v3 + 16),
           (__int64)&v10);
    ++v4;
    v3 += 7;
    v1 = v5;
    if ( v4 )
    {
      if ( v5 >= 0 )
      {
        v7 = L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;AC)(A;;0x23;;;AN)S:(ML;;NX;;;S-1-16-0)";
        if ( !byte_18009AA60 )
          v7 = L"O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;IU)(A;;0x3;;;AC)S:(ML;;NX;;;LW)";
        v8 = L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;AC)(A;;"
              "0x23;;;AN)S:(ML;;NX;;;S-1-16-0)";
        if ( !byte_18009AA60 )
          v8 = L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;AC)S:(ML;;NX;;;LW)";
        v1 = sub_180031784(
               v7,
               L"O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCLCSWRP;;;BA)(A;;CCDCLCSWRP;;;IU)(A;;CCDCLCSWRP;;;LS)(A;;0xb;;;AC)S:(ML;;NX;;;LW)",
               v6,
               v8,
               v7,
               &v10,
               v10,
               v11,
               v12);
        if ( v1 >= 0 )
          v1 = NdrDllRegisterProxy(hDll, (const ProxyFileInfo **)&pProxyFileList, &pclsid);
      }
      break;
    }
  }
LABEL_18:
  if ( hMem )
    LocalFree(hMem);
  return v1;
}

```

## disassembly

```asm
0x180032ad0  mov     r11, rsp
0x180032ad3  mov     [r11+8], rbx
0x180032ad7  mov     [r11+10h], rsi
0x180032adb  push    rdi
0x180032adc  sub     rsp, 60h
0x180032ae0  mov     rax, cs:__security_cookie
0x180032ae7  xor     rax, rsp
0x180032aea  mov     [rsp+68h+var_18], rax
0x180032aef  cmp     cs:byte_18009AA60, 0
0x180032af6  lea     rax, aDPAGaS15809560; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x180032afd  lea     rcx, aDPAGaS15809560_0; "D:P(A;;GA;;;S-1-5-80-956008885-34185226"...
0x180032b04  mov     qword ptr [r11-20h], 0
0x180032b0c  cmovz   rcx, rax; StringSecurityDescriptor
0x180032b10  lea     r8, [r11-20h]; SecurityDescriptor
0x180032b14  xor     r9d, r9d; SecurityDescriptorSize
0x180032b17  lea     edx, [r9+1]; StringSDRevision
0x180032b1b  call    cs:ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180032b21  test    eax, eax
0x180032b23  jz      short loc_180032B29
0x180032b25  xor     ebx, ebx
0x180032b27  jmp     short loc_180032B46
0x180032b29  call    cs:GetLastError
0x180032b2f  mov     ebx, eax
0x180032b31  test    eax, eax
0x180032b33  jle     short loc_180032B3E
0x180032b35  movzx   ebx, ax
0x180032b38  or      ebx, 80070000h
0x180032b3e  test    ebx, ebx
0x180032b40  js      loc_180032C0C
0x180032b46  mov     rax, [rsp+68h+hMem]
0x180032b4b  lea     rdi, off_180096E88; "{1111A26D-EF95-4A45-9F55-21E52ADF9887}"
0x180032b52  mov     [rsp+68h+var_30], rax
0x180032b57  xor     esi, esi
0x180032b59  mov     [rsp+68h+var_38], 18h
0x180032b62  mov     [rsp+68h+var_28], 0
0x180032b6b  test    ebx, ebx
0x180032b6d  js      loc_180032C0C
0x180032b73  mov     r9, [rdi]
0x180032b76  lea     rax, [rsp+68h+var_38]
0x180032b7b  mov     r8, [rdi-8]
0x180032b7f  mov     rdx, [rdi-10h]
0x180032b83  mov     rcx, [rdi-18h]
0x180032b87  mov     [rsp+68h+var_40], rax
0x180032b8c  mov     al, [rdi+10h]
0x180032b8f  mov     byte ptr [rsp+68h+var_48], al
0x180032b93  call    sub_180031BBC
0x180032b98  inc     esi
0x180032b9a  add     rdi, 38h ; '8'
0x180032b9e  mov     ebx, eax
0x180032ba0  cmp     esi, 1
0x180032ba3  jb      short loc_180032B6B
0x180032ba5  test    eax, eax
0x180032ba7  js      short loc_180032C0C
0x180032ba9  mov     al, cs:byte_18009AA60
0x180032baf  lea     rdx, aOBagBadA0x3SyA_0; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x180032bb6  test    al, al
0x180032bb8  lea     rcx, aOBagBadA0x3SyA_1; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x180032bbf  lea     rax, [rsp+68h+var_38]
0x180032bc4  cmovz   rcx, rdx
0x180032bc8  mov     [rsp+68h+var_40], rax
0x180032bcd  lea     rdx, aOBagBadACcdclc_0; "O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCL"...
0x180032bd4  mov     [rsp+68h+var_48], rcx
0x180032bd9  lea     r9, aOBagBadACcdclc_1; "O:BAG:BAD:(A;;CCDCLCSWRP;;;SY)(A;;CCDCL"...
0x180032be0  cmovz   r9, rdx
0x180032be4  call    sub_180031784
0x180032be9  mov     ebx, eax
0x180032beb  test    eax, eax
0x180032bed  js      short loc_180032C0C
0x180032bef  mov     rcx, cs:hDll; hDll
0x180032bf6  lea     r8, pclsid; pclsid
0x180032bfd  lea     rdx, pProxyFileList; pProxyFileList
0x180032c04  call    cs:NdrDllRegisterProxy
0x180032c0a  mov     ebx, eax
0x180032c0c  mov     rcx, [rsp+68h+hMem]; hMem
0x180032c11  test    rcx, rcx
0x180032c14  jz      short loc_180032C1C
0x180032c16  call    cs:__imp_LocalFree
0x180032c1c  mov     eax, ebx
0x180032c1e  mov     rcx, [rsp+68h+var_18]
0x180032c23  xor     rcx, rsp; StackCookie
0x180032c26  call    __security_check_cookie
0x180032c2b  mov     rbx, [rsp+68h+arg_0]
0x180032c30  mov     rsi, [rsp+68h+arg_8]
0x180032c35  add     rsp, 60h
0x180032c39  pop     rdi
0x180032c3a  retn
```

# DefaultActivityContextStore::DeleteContext(ActivityContext &)

- ea: `0x1800197f0`
- end: `0x1800198e9`
- name: `?DeleteContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x1800075e8`
- `0x180017e2c`
- `0x1800188f8`
- `0x1800197f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800198b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800198b7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019838`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019838`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::DeleteContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  int v2; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v5; // [rsp+30h] [rbp-2D8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned __int16 v7[40]; // [rsp+90h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-228h] BYREF

  v5 = 0;
  SubKey[0] = 0;
  v7[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), sz, 39) == 39 )
  {
    v2 = EEDBTrimGuidBracket(sz, v7);
    if ( v2 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v2 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v7, v5);
      if ( v2 >= 0 )
        RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    }
  }
  else
  {
    v2 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800197f0  push    rbx
0x1800197f2  sub     rsp, 300h
0x1800197f9  mov     rax, cs:__security_cookie
0x180019800  xor     rax, rsp
0x180019803  mov     [rsp+308h+var_18], rax
0x18001980b  xor     eax, eax
0x18001980d  mov     [rsp+308h+var_2D8], 0
0x180019816  lea     rcx, [rdx+8]; rguid
0x18001981a  mov     [rsp+308h+SubKey], ax
0x180019822  lea     rdx, [rsp+308h+sz]; lpsz
0x180019827  mov     [rsp+308h+var_278], ax
0x18001982f  mov     [rsp+308h+sz], ax
0x180019834  lea     r8d, [rax+27h]; cchMax
0x180019838  call    cs:__imp_StringFromGUID2
0x18001983f  nop     dword ptr [rax+rax+00h]
0x180019844  cmp     eax, 27h ; '''
0x180019847  jz      short loc_180019850
0x180019849  mov     ebx, 8000FFFFh
0x18001984e  jmp     short loc_1800198C3
0x180019850  lea     rdx, [rsp+308h+var_278]; unsigned __int16 *
0x180019858  lea     rcx, [rsp+308h+sz]; unsigned __int16 *
0x18001985d  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180019862  mov     ebx, eax
0x180019864  test    eax, eax
0x180019866  js      short loc_1800198C3
0x180019868  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18001986d  lea     rcx, [rsp+308h+var_278]
0x180019875  mov     r9, rax
0x180019878  mov     [rsp+308h+var_2E0], rcx
0x18001987d  lea     r8, aSSS; "%s\\%s\\%s"
0x180019884  lea     rcx, aContext; "Context"
0x18001988b  mov     edx, 104h; unsigned __int64
0x180019890  mov     [rsp+308h+var_2E8], rcx
0x180019895  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x18001989d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800198a2  mov     ebx, eax
0x1800198a4  test    eax, eax
0x1800198a6  js      short loc_1800198C3
0x1800198a8  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x1800198b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800198b7  call    cs:__imp_RegDeleteTreeW
0x1800198be  nop     dword ptr [rax+rax+00h]
0x1800198c3  lea     rcx, [rsp+308h+var_2D8]
0x1800198c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800198cd  mov     eax, ebx
0x1800198cf  mov     rcx, [rsp+308h+var_18]
0x1800198d7  xor     rcx, rsp; StackCookie
0x1800198da  call    __security_check_cookie
0x1800198df  add     rsp, 300h
0x1800198e6  pop     rbx
0x1800198e7  retn
```

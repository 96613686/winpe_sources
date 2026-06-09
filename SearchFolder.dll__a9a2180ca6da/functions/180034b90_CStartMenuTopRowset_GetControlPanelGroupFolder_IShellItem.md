# CStartMenuTopRowset::_GetControlPanelGroupFolder(IShellItem * *)

- ea: `0x180034b90`
- end: `0x180034c56`
- name: `?_GetControlPanelGroupFolder@CStartMenuTopRowset@@AEAAJPEAPEAUIShellItem@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *this, struct IShellItem **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003930`

## callees

- `0x1800054dc`
- `0x180006900`
- `0x180034b90`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180034c21`
- `SHELL32!SHCreateItemFromParsingName` at `0x180034c21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034be0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034be0`

## pseudocode

```c
__int64 __fastcall CStartMenuTopRowset::_GetControlPanelGroupFolder(CStartMenuTopRowset *this, struct IShellItem **a2)
{
  HRESULT Instance; // ebx
  LPVOID ppv[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-228h] BYREF

  *a2 = 0;
  ppv[0] = 0;
  Instance = CoCreateInstance(&CLSID_OpenControlPanel, 0, 0x17u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, WCHAR *, __int64))(*(_QWORD *)ppv[0] + 32LL))(
                 ppv[0],
                 0,
                 pszPath,
                 260);
    if ( Instance >= 0 )
      Instance = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)a2);
  }
  ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180034b90  mov     [rsp+arg_0], rbx
0x180034b95  push    rdi
0x180034b96  sub     rsp, 260h
0x180034b9d  mov     rax, cs:__security_cookie
0x180034ba4  xor     rax, rsp
0x180034ba7  mov     [rsp+268h+var_18], rax
0x180034baf  mov     rdi, rdx
0x180034bb2  mov     qword ptr [rdx], 0
0x180034bb9  mov     [rsp+268h+var_238], 0
0x180034bc2  lea     rax, [rsp+268h+var_238]
0x180034bc7  mov     [rsp+268h+ppv], rax; ppv
0x180034bcc  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180034bd3  xor     edx, edx; pUnkOuter
0x180034bd5  lea     r8d, [rdx+17h]; dwClsContext
0x180034bd9  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180034be0  call    cs:__imp_CoCreateInstance
0x180034be6  mov     ebx, eax
0x180034be8  test    eax, eax
0x180034bea  js      short loc_180034C29
0x180034bec  mov     rcx, [rsp+268h+var_238]
0x180034bf1  mov     rax, [rcx]
0x180034bf4  mov     r9d, 104h
0x180034bfa  lea     r8, [rsp+268h+pszPath]
0x180034bff  xor     edx, edx
0x180034c01  mov     rax, [rax+20h]
0x180034c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c0a  mov     ebx, eax
0x180034c0c  test    eax, eax
0x180034c0e  js      short loc_180034C29
0x180034c10  mov     r9, rdi; ppv
0x180034c13  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180034c1a  xor     edx, edx; pbc
0x180034c1c  lea     rcx, [rsp+268h+pszPath]; pszPath
0x180034c21  call    cs:__imp_SHCreateItemFromParsingName
0x180034c27  mov     ebx, eax
0x180034c29  lea     rcx, [rsp+268h+var_238]
0x180034c2e  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180034c33  mov     eax, ebx
0x180034c35  mov     rcx, [rsp+268h+var_18]
0x180034c3d  xor     rcx, rsp; StackCookie
0x180034c40  call    __security_check_cookie
0x180034c45  mov     rbx, [rsp+268h+arg_0]
0x180034c4d  add     rsp, 260h
0x180034c54  pop     rdi
0x180034c55  retn
```

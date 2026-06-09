# GetUrlFromPath

- ea: `0x18001b6f8`
- end: `0x18001b7f2`
- name: `GetUrlFromPath`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001aaf4`

## callees

- `0x180006cc4`
- `0x18000d17c`
- `0x18001b6f8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001b70f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001b70f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b7cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b742`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b742`

## pseudocode

```c
__int64 __fastcall GetUrlFromPath(const WCHAR *a1, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID pv; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7[2]; // [rsp+38h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+40h] BYREF

  v4 = -2147024809;
  if ( PathFileExistsW(a1) )
  {
    ppv = 0;
    v4 = CoCreateInstance(&CLSID_InternetShortcut, 0, 1u, &GUID_cabb0da0_da57_11cf_9974_0020afd79762, &ppv);
    if ( v4 >= 0 )
    {
      v7[0] = 0;
      v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_0000010b_0000_0000_c000_000000000046,
             v7);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD))(*(_QWORD *)v7[0] + 40LL))(v7[0], a1, 0);
        if ( v4 >= 0 )
        {
          pv = 0;
          v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv + 32LL))(ppv, &pv);
          if ( !v4 )
          {
            v4 = StringCchCopyW(a2, 0x824u, (const unsigned __int16 *)pv);
            CoTaskMemFree(pv);
          }
        }
      }
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(v7);
    }
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b6f8  push    rbp
0x18001b6fa  push    rbx
0x18001b6fb  push    rsi
0x18001b6fc  push    rdi
0x18001b6fd  mov     rbp, rsp
0x18001b700  sub     rsp, 48h
0x18001b704  mov     rsi, rdx
0x18001b707  mov     rdi, rcx
0x18001b70a  mov     ebx, 80070057h
0x18001b70f  call    cs:__imp_PathFileExistsW
0x18001b715  test    eax, eax
0x18001b717  jz      loc_18001B7E7
0x18001b71d  xor     edx, edx; pUnkOuter
0x18001b71f  mov     [rbp+arg_18], 0
0x18001b727  lea     rax, [rbp+arg_18]
0x18001b72b  lea     r9, _GUID_cabb0da0_da57_11cf_9974_0020afd79762; riid
0x18001b732  mov     [rsp+48h+ppv], rax; ppv
0x18001b737  lea     rcx, CLSID_InternetShortcut; rclsid
0x18001b73e  lea     r8d, [rdx+1]; dwClsContext
0x18001b742  call    cs:__imp_CoCreateInstance
0x18001b748  mov     ebx, eax
0x18001b74a  test    eax, eax
0x18001b74c  js      loc_18001B7DE
0x18001b752  mov     rcx, [rbp+arg_18]
0x18001b756  lea     r8, [rbp+var_10]
0x18001b75a  mov     [rbp+var_10], 0
0x18001b762  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18001b769  mov     rax, [rcx]
0x18001b76c  mov     rax, [rax]
0x18001b76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b774  mov     ebx, eax
0x18001b776  test    eax, eax
0x18001b778  js      short loc_18001B7D5
0x18001b77a  mov     rcx, [rbp+var_10]
0x18001b77e  xor     r8d, r8d
0x18001b781  mov     rdx, rdi
0x18001b784  mov     rax, [rcx]
0x18001b787  mov     rax, [rax+28h]
0x18001b78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b790  mov     ebx, eax
0x18001b792  test    eax, eax
0x18001b794  js      short loc_18001B7D5
0x18001b796  mov     rcx, [rbp+arg_18]
0x18001b79a  lea     rdx, [rbp+pv]
0x18001b79e  mov     [rbp+pv], 0
0x18001b7a6  mov     rax, [rcx]
0x18001b7a9  mov     rax, [rax+20h]
0x18001b7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7b2  mov     ebx, eax
0x18001b7b4  test    eax, eax
0x18001b7b6  jnz     short loc_18001B7D5
0x18001b7b8  mov     r8, [rbp+pv]; unsigned __int16 *
0x18001b7bc  mov     edx, 824h; unsigned __int64
0x18001b7c1  mov     rcx, rsi; unsigned __int16 *
0x18001b7c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b7c9  mov     rcx, [rbp+pv]; pv
0x18001b7cd  mov     ebx, eax
0x18001b7cf  call    cs:__imp_CoTaskMemFree
0x18001b7d5  lea     rcx, [rbp+var_10]
0x18001b7d9  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001b7de  lea     rcx, [rbp+arg_18]
0x18001b7e2  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18001b7e7  mov     eax, ebx
0x18001b7e9  add     rsp, 48h
0x18001b7ed  pop     rdi
0x18001b7ee  pop     rsi
0x18001b7ef  pop     rbx
0x18001b7f0  pop     rbp
0x18001b7f1  retn
```

# GetLocaleFromCondition

- ea: `0x18003c324`
- end: `0x18003c3fb`
- name: `GetLocaleFromCondition`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a290`
- `0x180033460`
- `0x1800340bc`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18003c324`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c38f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c3cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c38f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c3cc`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003c3b2`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003c3b2`

## pseudocode

```c
__int64 __fastcall GetLocaleFromCondition(__int64 a1, int *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // r9
  int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, LPCWSTR *); // rbx
  LCID v7; // eax
  int v8; // ecx
  LPCWSTR lpName; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF

  *a2 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v11);
  v4 = (**v3)(v3, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v11);
  if ( v4 >= 0 )
  {
    v5 = v11;
    lpName = 0;
    v6 = *(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v11 + 120LL);
    CoTaskMemFree(0);
    v4 = v6(v5, &lpName);
    if ( v4 >= 0 )
    {
      v7 = LocaleNameToLCID(lpName, 0);
      v8 = 127;
      if ( v7 != 4096 )
        v8 = v7;
      *a2 = v8;
    }
    CoTaskMemFree((LPVOID)lpName);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c324  mov     [rsp+arg_10], rbx
0x18003c329  mov     [rsp+arg_18], rsi
0x18003c32e  push    rdi
0x18003c32f  sub     rsp, 40h
0x18003c333  mov     rax, cs:__security_cookie
0x18003c33a  xor     rax, rsp
0x18003c33d  mov     [rsp+48h+var_18], rax
0x18003c342  mov     r9, rcx
0x18003c345  mov     dword ptr [rdx], 0
0x18003c34b  lea     rcx, [rsp+48h+var_20]; void *
0x18003c350  mov     rsi, rdx
0x18003c353  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003c358  mov     r8, [r9]
0x18003c35b  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18003c362  mov     rcx, r9
0x18003c365  mov     rax, [r8]
0x18003c368  lea     r8, [rsp+48h+var_20]
0x18003c36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c372  mov     ebx, eax
0x18003c374  test    eax, eax
0x18003c376  js      short loc_18003C3D2
0x18003c378  mov     rdi, [rsp+48h+var_20]
0x18003c37d  xor     ecx, ecx; pv
0x18003c37f  mov     [rsp+48h+lpName], 0
0x18003c388  mov     rax, [rdi]
0x18003c38b  mov     rbx, [rax+78h]
0x18003c38f  call    cs:__imp_CoTaskMemFree
0x18003c395  lea     rdx, [rsp+48h+lpName]
0x18003c39a  mov     rcx, rdi
0x18003c39d  mov     rax, rbx
0x18003c3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3a5  mov     ebx, eax
0x18003c3a7  test    eax, eax
0x18003c3a9  js      short loc_18003C3C7
0x18003c3ab  mov     rcx, [rsp+48h+lpName]; lpName
0x18003c3b0  xor     edx, edx; dwFlags
0x18003c3b2  call    cs:__imp_LocaleNameToLCID
0x18003c3b8  cmp     eax, 1000h
0x18003c3bd  mov     ecx, 7Fh
0x18003c3c2  cmovnz  ecx, eax
0x18003c3c5  mov     [rsi], ecx
0x18003c3c7  mov     rcx, [rsp+48h+lpName]; pv
0x18003c3cc  call    cs:__imp_CoTaskMemFree
0x18003c3d2  lea     rcx, [rsp+48h+var_20]
0x18003c3d7  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003c3dc  mov     eax, ebx
0x18003c3de  mov     rcx, [rsp+48h+var_18]
0x18003c3e3  xor     rcx, rsp; StackCookie
0x18003c3e6  call    __security_check_cookie
0x18003c3eb  mov     rbx, [rsp+48h+arg_10]
0x18003c3f0  mov     rsi, [rsp+48h+arg_18]
0x18003c3f5  add     rsp, 40h
0x18003c3f9  pop     rdi
0x18003c3fa  retn
```

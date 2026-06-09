# CAxInstaller::~CAxInstaller(void)

- ea: `0x180005e18`
- end: `0x180005eb8`
- name: `??1CAxInstaller@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(CAxInstaller *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008340`
- `0x180008384`
- `0x180008c80`

## callees

- `0x180005e18`
- `0x180005ec0`
- `0x180006370`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005e70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e97`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e97`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005ea4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005ea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e3f`

## pseudocode

```c
void __fastcall CAxInstaller::~CAxInstaller(CAxInstaller *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  v2 = (void *)*((_QWORD *)this + 85);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 89);
  if ( v3 )
    CloseHandle(v3);
  CAxInstaller::Cleanup(this);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 87);
  if ( v4 )
    (**v4)(v4, 1);
  SysFreeString(*((BSTR *)this + 82));
  SysFreeString(*((BSTR *)this + 81));
  SysFreeString(*((BSTR *)this + 80));
  SysFreeString(*((BSTR *)this + 79));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 592));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CAxInstaller *)((char *)this + 24));
}

```

## disassembly

```asm
0x180005e18  push    rbx
0x180005e1a  sub     rsp, 20h
0x180005e1e  mov     rbx, rcx
0x180005e21  mov     rcx, [rcx+2A8h]; hObject
0x180005e28  test    rcx, rcx
0x180005e2b  jz      short loc_180005E33
0x180005e2d  call    cs:__imp_CloseHandle
0x180005e33  mov     rcx, [rbx+2C8h]; hObject
0x180005e3a  test    rcx, rcx
0x180005e3d  jz      short loc_180005E45
0x180005e3f  call    cs:__imp_CloseHandle
0x180005e45  mov     rcx, rbx; this
0x180005e48  call    ?Cleanup@CAxInstaller@@UEAAJXZ; CAxInstaller::Cleanup(void)
0x180005e4d  mov     rcx, [rbx+2B8h]
0x180005e54  test    rcx, rcx
0x180005e57  jz      short loc_180005E69
0x180005e59  mov     rax, [rcx]
0x180005e5c  mov     edx, 1
0x180005e61  mov     rax, [rax]
0x180005e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e69  mov     rcx, [rbx+290h]; bstrString
0x180005e70  call    cs:__imp_SysFreeString
0x180005e76  mov     rcx, [rbx+288h]; bstrString
0x180005e7d  call    cs:__imp_SysFreeString
0x180005e83  mov     rcx, [rbx+280h]; bstrString
0x180005e8a  call    cs:__imp_SysFreeString
0x180005e90  mov     rcx, [rbx+278h]; bstrString
0x180005e97  call    cs:__imp_SysFreeString
0x180005e9d  lea     rcx, [rbx+250h]; lpCriticalSection
0x180005ea4  call    cs:__imp_DeleteCriticalSection
0x180005eaa  lea     rcx, [rbx+18h]; this
0x180005eae  add     rsp, 20h
0x180005eb2  pop     rbx
0x180005eb3  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```

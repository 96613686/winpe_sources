# AppEnumeratorImpl::~AppEnumeratorImpl(void)

- ea: `0x180042d14`
- end: `0x180042d58`
- name: `??1AppEnumeratorImpl@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(AppEnumeratorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a6d90`

## callees

- `0x180002840`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d21`

## pseudocode

```c
void __fastcall AppEnumeratorImpl::~AppEnumeratorImpl(AppEnumeratorImpl *this)
{
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>((__int64 *)this + 5);
  ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>((__int64 *)this + 3);
  ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>((__int64 *)this + 2);
  ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>((__int64 *)this + 1);
}

```

## disassembly

```asm
0x180042d14  push    rbx
0x180042d16  sub     rsp, 20h
0x180042d1a  mov     rbx, rcx
0x180042d1d  mov     rcx, [rcx+30h]; string
0x180042d21  call    cs:__imp_WindowsDeleteString
0x180042d27  lea     rcx, [rbx+28h]
0x180042d2b  mov     qword ptr [rbx+30h], 0
0x180042d33  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180042d38  lea     rcx, [rbx+18h]
0x180042d3c  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180042d41  lea     rcx, [rbx+10h]
0x180042d45  call    ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
0x180042d4a  lea     rcx, [rbx+8]
0x180042d4e  add     rsp, 20h
0x180042d52  pop     rbx
0x180042d53  jmp     ??1?$CComPtrBase@UIPackage@ApplicationModel@Windows@ABI@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ABI::Windows::ApplicationModel::IPackage>::~CComPtrBase<ABI::Windows::ApplicationModel::IPackage>(void)
```

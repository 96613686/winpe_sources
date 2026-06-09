# CFileDownloadManager::~CFileDownloadManager(void)

- ea: `0x1800369c4`
- end: `0x180036a84`
- name: `??1CFileDownloadManager@@UEAA@XZ`
- size: `192`
- prototype: `void __fastcall(CFileDownloadManager *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180036648`
- `0x180036fa0`
- `0x18012e19f`

## callees

- `0x180009188`
- `0x180009384`
- `0x180010d38`
- `0x180036678`
- `0x18003c944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a2c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a2c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036a45`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CFileDownloadManager::~CFileDownloadManager(CFileDownloadManager *this)
{
  std::wstring::~wstring((__int64)this + 360);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 344);
  EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::~EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>((char *)this + 320);
  EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::~EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>((char *)this + 296);
  std::vector<ActiveDownloadInfo>::_Tidy((char *)this + 272);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)this + 80);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)this + 64);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)this + 48);
  std::wstring::~wstring((__int64)this + 16);
  *(_QWORD *)this = &IFileDownloadManager::`vftable';
}

```

## disassembly

```asm
0x1800369c4  mov     [rsp+arg_0], rcx
0x1800369c9  push    rbx
0x1800369ca  sub     rsp, 20h
0x1800369ce  mov     rbx, rcx
0x1800369d1  add     rcx, 168h
0x1800369d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800369dd  nop
0x1800369de  lea     rcx, [rbx+158h]
0x1800369e5  mov     [rsp+28h+arg_8], rcx
0x1800369ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800369ef  nop
0x1800369f0  lea     rcx, [rbx+140h]
0x1800369f7  call    ??1?$EcsQueue@V?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@@UEAA@XZ; EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::~EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>(void)
0x1800369fc  nop
0x1800369fd  lea     rcx, [rbx+128h]
0x180036a04  call    ??1?$EcsQueue@V?$CComPtr@UIStagedFileCommitInfo@@@ATL@@@@UEAA@XZ; EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>::~EcsQueue<ATL::CComPtr<IStagedFileCommitInfo>>(void)
0x180036a09  nop
0x180036a0a  lea     rcx, [rbx+110h]
0x180036a11  call    ?_Tidy@?$vector@UActiveDownloadInfo@@V?$allocator@UActiveDownloadInfo@@@std@@@std@@AEAAXXZ; std::vector<ActiveDownloadInfo>::_Tidy(void)
0x180036a16  nop
0x180036a17  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180036a1e  call    cs:__imp_DeleteCriticalSection
0x180036a24  nop
0x180036a25  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180036a2c  call    cs:__imp_DeleteCriticalSection
0x180036a32  nop
0x180036a33  lea     rcx, [rbx+98h]; lpCriticalSection
0x180036a3a  call    cs:__imp_DeleteCriticalSection
0x180036a40  nop
0x180036a41  lea     rcx, [rbx+70h]; lpCriticalSection
0x180036a45  call    cs:__imp_DeleteCriticalSection
0x180036a4b  nop
0x180036a4c  lea     rcx, [rbx+50h]
0x180036a50  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180036a55  nop
0x180036a56  lea     rcx, [rbx+40h]
0x180036a5a  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180036a5f  nop
0x180036a60  lea     rcx, [rbx+30h]
0x180036a64  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180036a69  nop
0x180036a6a  lea     rcx, [rbx+10h]
0x180036a6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036a73  nop
0x180036a74  lea     rax, ??_7IFileDownloadManager@@6B@; const IFileDownloadManager::`vftable'
0x180036a7b  mov     [rbx], rax
0x180036a7e  add     rsp, 20h
0x180036a82  pop     rbx
0x180036a83  retn
```

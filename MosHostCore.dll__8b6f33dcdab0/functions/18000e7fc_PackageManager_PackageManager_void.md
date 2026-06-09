# PackageManager::~PackageManager(void)

- ea: `0x18000e7fc`
- end: `0x18000e923`
- name: `??1PackageManager@@QEAA@XZ`
- size: `295`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012350`
- `0x180023ba9`

## callees

- `0x1800078d0`
- `0x18000e6ec`
- `0x18000e7fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e91c`

## pseudocode

```c
void __fastcall PackageManager::~PackageManager(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx
  void *SpinCount; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  HANDLE v5; // rcx
  void *v6; // rcx

  OwningThread = this[5].OwningThread;
  if ( OwningThread )
  {
    std::_Deallocate<16>(OwningThread, (this[5].SpinCount - (_QWORD)OwningThread) & 0xFFFFFFFFFFFFFFF8uLL);
    this[5].OwningThread = 0;
    this[5].LockSemaphore = 0;
    this[5].SpinCount = 0;
  }
  SpinCount = (void *)this[4].SpinCount;
  if ( SpinCount )
  {
    std::_Deallocate<16>(SpinCount, (*(_QWORD *)&this[5].LockCount - (_QWORD)SpinCount) & 0xFFFFFFFFFFFFFFF8uLL);
    this[4].SpinCount = 0;
    this[5].DebugInfo = 0;
    *(_QWORD *)&this[5].LockCount = 0;
  }
  DebugInfo = this[4].DebugInfo;
  if ( DebugInfo )
  {
    std::_Deallocate<16>(DebugInfo, ((char *)this[4].OwningThread - (char *)DebugInfo) & 0xFFFFFFFFFFFFFFFCuLL);
    this[4].DebugInfo = 0;
    *(_QWORD *)&this[4].LockCount = 0;
    this[4].OwningThread = 0;
  }
  v5 = this[3].OwningThread;
  if ( v5 )
  {
    std::_Deallocate<16>(v5, (this[3].SpinCount - (_QWORD)v5) & 0xFFFFFFFFFFFFFFFCuLL);
    this[3].OwningThread = 0;
    this[3].LockSemaphore = 0;
    this[3].SpinCount = 0;
  }
  v6 = (void *)this[2].SpinCount;
  if ( v6 )
  {
    std::_Deallocate<16>(v6, (*(_QWORD *)&this[3].LockCount - (_QWORD)v6) & 0xFFFFFFFFFFFFFFFCuLL);
    this[2].SpinCount = 0;
    this[3].DebugInfo = 0;
    *(_QWORD *)&this[3].LockCount = 0;
  }
  std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::~_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>((__int64)&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000e7fc  mov     [rsp+arg_0], rbx
0x18000e801  push    rdi
0x18000e802  sub     rsp, 20h
0x18000e806  mov     rbx, rcx
0x18000e809  xor     edi, edi
0x18000e80b  mov     rcx, [rcx+0D8h]
0x18000e812  test    rcx, rcx
0x18000e815  jz      short loc_18000E83F
0x18000e817  mov     rdx, [rbx+0E8h]
0x18000e81e  sub     rdx, rcx
0x18000e821  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000e825  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e82a  mov     [rbx+0D8h], rdi
0x18000e831  mov     [rbx+0E0h], rdi
0x18000e838  mov     [rbx+0E8h], rdi
0x18000e83f  mov     rcx, [rbx+0C0h]
0x18000e846  test    rcx, rcx
0x18000e849  jz      short loc_18000E873
0x18000e84b  mov     rdx, [rbx+0D0h]
0x18000e852  sub     rdx, rcx
0x18000e855  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000e859  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e85e  mov     [rbx+0C0h], rdi
0x18000e865  mov     [rbx+0C8h], rdi
0x18000e86c  mov     [rbx+0D0h], rdi
0x18000e873  mov     rcx, [rbx+0A0h]
0x18000e87a  test    rcx, rcx
0x18000e87d  jz      short loc_18000E8A7
0x18000e87f  mov     rdx, [rbx+0B0h]
0x18000e886  sub     rdx, rcx
0x18000e889  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000e88d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e892  mov     [rbx+0A0h], rdi
0x18000e899  mov     [rbx+0A8h], rdi
0x18000e8a0  mov     [rbx+0B0h], rdi
0x18000e8a7  mov     rcx, [rbx+88h]
0x18000e8ae  test    rcx, rcx
0x18000e8b1  jz      short loc_18000E8DB
0x18000e8b3  mov     rdx, [rbx+98h]
0x18000e8ba  sub     rdx, rcx
0x18000e8bd  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000e8c1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e8c6  mov     [rbx+88h], rdi
0x18000e8cd  mov     [rbx+90h], rdi
0x18000e8d4  mov     [rbx+98h], rdi
0x18000e8db  mov     rcx, [rbx+70h]
0x18000e8df  test    rcx, rcx
0x18000e8e2  jz      short loc_18000E906
0x18000e8e4  mov     rdx, [rbx+80h]
0x18000e8eb  sub     rdx, rcx
0x18000e8ee  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000e8f2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000e8f7  mov     [rbx+70h], rdi
0x18000e8fb  mov     [rbx+78h], rdi
0x18000e8ff  mov     [rbx+80h], rdi
0x18000e906  lea     rcx, [rbx+28h]
0x18000e90a  call    ??1?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::~_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>(void)
0x18000e90f  mov     rcx, rbx
0x18000e912  mov     rbx, [rsp+28h+arg_0]
0x18000e917  add     rsp, 20h
0x18000e91b  pop     rdi
0x18000e91c  jmp     cs:__imp_DeleteCriticalSection
```

# CInkModule::~CInkModule(void)

- ea: `0x180030988`
- end: `0x180030a70`
- name: `??1CInkModule@@QEAA@XZ`
- size: `232`
- prototype: `void __fastcall(CInkModule *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18010ba10`

## callees

- `0x180002740`
- `0x1800102f0`
- `0x18002a314`
- `0x18002b004`
- `0x18002e0c4`
- `0x180030988`
- `0x180030a78`
- `0x180030ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a3f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a49`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a3f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a49`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030a53`

## pseudocode

```c
void __fastcall CInkModule::~CInkModule(CInkModule *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 47);
  if ( v2 )
  {
    WinFree(v2);
    *((_QWORD *)this + 47) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 46);
  if ( v3 )
  {
    WinFree(v3);
    *((_QWORD *)this + 46) = 0;
  }
  Vector<SmartPtr<SmartAdapt<tagXFORM>>,Allocator<SmartPtr<SmartAdapt<tagXFORM>>>>::~Vector<SmartPtr<SmartAdapt<tagXFORM>>,Allocator<SmartPtr<SmartAdapt<tagXFORM>>>>((char *)this + 456);
  Vector<SGPtr,Allocator<SGPtr>>::~Vector<SGPtr,Allocator<SGPtr>>((char *)this + 432);
  Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>::~Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>((char *)this + 408);
  Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>::~Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>((char *)this + 384);
  SmartPtrBase::unref((CInkModule *)((char *)this + 360));
  SmartPtrBase::unref((CInkModule *)((char *)this + 352));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  Vector<SmartLockPtr,Allocator<SmartLockPtr>>::~Vector<SmartLockPtr,Allocator<SmartLockPtr>>((char *)this + 16);
  SmartLockPtr::~SmartLockPtr((CInkModule *)((char *)this + 8));
}

```

## disassembly

```asm
0x180030988  push    rbx
0x18003098a  sub     rsp, 20h
0x18003098e  mov     rbx, rcx
0x180030991  mov     rcx, [rcx+178h]; void *
0x180030998  test    rcx, rcx
0x18003099b  jz      short loc_1800309AD
0x18003099d  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800309a2  mov     qword ptr [rbx+178h], 0
0x1800309ad  mov     rcx, [rbx+170h]; void *
0x1800309b4  test    rcx, rcx
0x1800309b7  jz      short loc_1800309C9
0x1800309b9  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800309be  mov     qword ptr [rbx+170h], 0
0x1800309c9  lea     rcx, [rbx+1C8h]
0x1800309d0  call    ??1?$Vector@V?$SmartPtr@V?$SmartAdapt@UtagXFORM@@@@@@V?$Allocator@V?$SmartPtr@V?$SmartAdapt@UtagXFORM@@@@@@@@@@QEAA@XZ; Vector<SmartPtr<SmartAdapt<tagXFORM>>,Allocator<SmartPtr<SmartAdapt<tagXFORM>>>>::~Vector<SmartPtr<SmartAdapt<tagXFORM>>,Allocator<SmartPtr<SmartAdapt<tagXFORM>>>>(void)
0x1800309d5  lea     rcx, [rbx+1B0h]
0x1800309dc  call    ??1?$Vector@VSGPtr@@V?$Allocator@VSGPtr@@@@@@QEAA@XZ; Vector<SGPtr,Allocator<SGPtr>>::~Vector<SGPtr,Allocator<SGPtr>>(void)
0x1800309e1  lea     rcx, [rbx+198h]
0x1800309e8  call    ??1?$Vector@V?$SmartPtr@VPkDs@@@@V?$Allocator@V?$SmartPtr@VPkDs@@@@@@@@QEAA@XZ; Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>::~Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>(void)
0x1800309ed  lea     rcx, [rbx+180h]
0x1800309f4  call    ??1?$Vector@V?$SmartPtr@VPkDs@@@@V?$Allocator@V?$SmartPtr@VPkDs@@@@@@@@QEAA@XZ; Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>::~Vector<SmartPtr<PkDs>,Allocator<SmartPtr<PkDs>>>(void)
0x1800309f9  lea     rcx, [rbx+168h]; this
0x180030a00  call    ?unref@SmartPtrBase@@IEAAXXZ; SmartPtrBase::unref(void)
0x180030a05  lea     rcx, [rbx+160h]; this
0x180030a0c  call    ?unref@SmartPtrBase@@IEAAXXZ; SmartPtrBase::unref(void)
0x180030a11  lea     rcx, [rbx+120h]; lpCriticalSection
0x180030a18  call    cs:__imp_DeleteCriticalSection
0x180030a1e  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180030a25  call    cs:__imp_DeleteCriticalSection
0x180030a2b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180030a32  call    cs:__imp_DeleteCriticalSection
0x180030a38  lea     rcx, [rbx+90h]; lpCriticalSection
0x180030a3f  call    cs:__imp_DeleteCriticalSection
0x180030a45  lea     rcx, [rbx+60h]; lpCriticalSection
0x180030a49  call    cs:__imp_DeleteCriticalSection
0x180030a4f  lea     rcx, [rbx+30h]; lpCriticalSection
0x180030a53  call    cs:__imp_DeleteCriticalSection
0x180030a59  lea     rcx, [rbx+10h]
0x180030a5d  call    ??1?$Vector@VSmartLockPtr@@V?$Allocator@VSmartLockPtr@@@@@@QEAA@XZ; Vector<SmartLockPtr,Allocator<SmartLockPtr>>::~Vector<SmartLockPtr,Allocator<SmartLockPtr>>(void)
0x180030a62  lea     rcx, [rbx+8]; this
0x180030a66  add     rsp, 20h
0x180030a6a  pop     rbx
0x180030a6b  jmp     ??1SmartLockPtr@@QEAA@XZ; SmartLockPtr::~SmartLockPtr(void)
```

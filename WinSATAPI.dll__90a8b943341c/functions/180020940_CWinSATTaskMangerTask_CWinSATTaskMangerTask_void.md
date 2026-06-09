# CWinSATTaskMangerTask::~CWinSATTaskMangerTask(void)

- ea: `0x180020940`
- end: `0x18002099f`
- name: `??1CWinSATTaskMangerTask@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CWinSATTaskMangerTask *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014148`
- `0x1800143bc`

## callees

- `0x180008490`
- `0x18000e490`
- `0x180011d1c`
- `0x180020940`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002095c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002095c`

## pseudocode

```c
void __fastcall CWinSATTaskMangerTask::~CWinSATTaskMangerTask(CWinSATTaskMangerTask *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CWinSATTaskMangerTask::`vftable';
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 11) = 0;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((char *)this + 120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 8);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWinSATTaskMangerTask *)((char *)this + 16));
}

```

## disassembly

```asm
0x180020940  push    rbx
0x180020942  sub     rsp, 20h
0x180020946  lea     rax, ??_7CWinSATTaskMangerTask@@6B@; const CWinSATTaskMangerTask::`vftable'
0x18002094d  mov     rbx, rcx
0x180020950  mov     [rcx], rax
0x180020953  mov     rcx, [rcx+58h]; hObject
0x180020957  test    rcx, rcx
0x18002095a  jz      short loc_18002096D
0x18002095c  call    cs:__imp_CloseHandle
0x180020963  nop     dword ptr [rax+rax+00h]
0x180020968  and     qword ptr [rbx+58h], 0
0x18002096d  lea     rcx, [rbx+78h]
0x180020971  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020976  lea     rcx, [rbx+50h]
0x18002097a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002097f  lea     rcx, [rbx+48h]
0x180020983  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020988  lea     rcx, [rbx+40h]
0x18002098c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020991  lea     rcx, [rbx+10h]; this
0x180020995  add     rsp, 20h
0x180020999  pop     rbx
0x18002099a  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```

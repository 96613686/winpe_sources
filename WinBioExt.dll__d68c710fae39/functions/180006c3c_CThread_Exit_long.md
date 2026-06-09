# CThread::Exit(long)

- ea: `0x180006c3c`
- end: `0x180006cd6`
- name: `?Exit@CThread@@AEAAXJ@Z`
- size: `154`
- prototype: `void __fastcall __noreturn(CThread *__hidden this, DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006da0`

## callees

- `0x1800066d0`
- `0x1800066e4`
- `0x1800069e8`
- `0x180006ae4`
- `0x180006c3c`
- `0x180006d18`
- `0x180006d5c`
- `0x180006e90`
- `0x180006edc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006ccf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006ccf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn CThread::Exit(CThread *this, DWORD dwExitCode)
{
  __int64 v4; // rax
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp+8h] BYREF
  char v7; // [rsp+50h] [rbp+18h] BYREF

  CNotifyEvent::Signal((CThread *)((char *)this + 112));
  while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 4, *((_DWORD *)this + 26)) != 4 )
    ;
  hLibModule = 0;
  locked_pointer<std::list<CThread *>>::locked_pointer<std::list<CThread *>>(v5);
  CThread::thread_list(v5);
  v4 = locked_pointer<std::list<CThread *>>::operator->(v5);
  std::list<CThread *>::erase(v4, &v7, *((_QWORD *)this + 12));
  std::swap<HINSTANCE__ *,0>(&hLibModule, (char *)this + 88);
  locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(v5);
  CNotifyEvent::Signal((CThread *)((char *)this + 120));
  CThread::Release(this);
  FreeLibraryAndExitThread(hLibModule, dwExitCode);
}

```

## disassembly

```asm
0x180006c3c  mov     [rsp+arg_8], rbx
0x180006c41  push    rdi
0x180006c42  sub     rsp, 30h
0x180006c46  mov     edi, edx
0x180006c48  mov     rbx, rcx
0x180006c4b  add     rcx, 70h ; 'p'; this
0x180006c4f  call    ?Signal@CNotifyEvent@@QEAAXXZ; CNotifyEvent::Signal(void)
0x180006c54  mov     ecx, 4
0x180006c59  mov     eax, [rbx+68h]
0x180006c5c  lock cmpxchg [rbx+68h], ecx
0x180006c61  cmp     eax, ecx
0x180006c63  jnz     short loc_180006C59
0x180006c65  mov     [rsp+38h+hLibModule], 0
0x180006c6e  lea     rcx, [rsp+38h+var_18]
0x180006c73  call    ??0?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::locked_pointer<std::list<CThread *>>(void)
0x180006c78  nop
0x180006c79  lea     rcx, [rsp+38h+var_18]
0x180006c7e  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z; CThread::thread_list(locked_pointer<std::list<CThread *>> *)
0x180006c83  lea     rcx, [rsp+38h+var_18]
0x180006c88  call    ??C?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAAPEAV?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@XZ; locked_pointer<std::list<CThread *>>::operator->(void)
0x180006c8d  mov     rcx, rax
0x180006c90  mov     r8, [rbx+60h]
0x180006c94  lea     rdx, [rsp+38h+arg_10]
0x180006c99  call    ?erase@?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCThread@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCThread@@@std@@@std@@@2@@Z; std::list<CThread *>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<CThread *>>>)
0x180006c9e  lea     rdx, [rbx+58h]
0x180006ca2  lea     rcx, [rsp+38h+hLibModule]
0x180006ca7  call    ??$swap@PEAUHINSTANCE__@@$0A@@std@@YAXAEAPEAUHINSTANCE__@@0@Z; std::swap<HINSTANCE__ *,0>(HINSTANCE__ * &,HINSTANCE__ * &)
0x180006cac  nop
0x180006cad  lea     rcx, [rsp+38h+var_18]
0x180006cb2  call    ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
0x180006cb7  lea     rcx, [rbx+78h]; this
0x180006cbb  call    ?Signal@CNotifyEvent@@QEAAXXZ; CNotifyEvent::Signal(void)
0x180006cc0  mov     rcx, rbx; this
0x180006cc3  call    ?Release@CThread@@AEBAJXZ; CThread::Release(void)
0x180006cc8  mov     edx, edi; dwExitCode
0x180006cca  mov     rcx, [rsp+38h+hLibModule]; hLibModule
0x180006ccf  call    cs:__imp_FreeLibraryAndExitThread
```

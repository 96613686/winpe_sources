# CExec::ProcessTracker::~ProcessTracker(void)

- ea: `0x140015b40`
- end: `0x140015bc4`
- name: `??1ProcessTracker@CExec@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(CExec::ProcessTracker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001a940`

## callees

- `0x1400026b8`
- `0x140015b40`
- `0x14001b8ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015bb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015bb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140015b56`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140015b56`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x140015b82`
- `api-ms-win-core-console-l1-2-1!ClosePseudoConsole` at `0x140015b82`
- `profapi!__imp_UnloadProfileBasic` at `0x140015b6a`
- `profapi!__imp_UnloadProfileBasic` at `0x140015b6a`

## pseudocode

```c
void __fastcall CExec::ProcessTracker::~ProcessTracker(CExec::ProcessTracker *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rdi
  void *v4; // rdi

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 5);
  if ( v2 )
    CloseThreadpoolWait(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    UnloadProfileBasic(*((_QWORD *)this + 3), 0);
    CloseHandle(v3);
  }
  if ( *((_QWORD *)this + 2) )
    ClosePseudoConsole();
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    ConsoleToPipeRedirector::~ConsoleToPipeRedirector(*((ConsoleToPipeRedirector **)this + 1));
    operator delete(v4, 0x180u);
  }
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)this);
}

```

## disassembly

```asm
0x140015b40  mov     [rsp+arg_0], rbx
0x140015b45  push    rdi
0x140015b46  sub     rsp, 20h
0x140015b4a  mov     rbx, rcx
0x140015b4d  mov     rcx, [rcx+28h]; pwa
0x140015b51  test    rcx, rcx
0x140015b54  jz      short loc_140015B5C
0x140015b56  call    cs:__imp_CloseThreadpoolWait
0x140015b5c  mov     rdi, [rbx+18h]
0x140015b60  test    rdi, rdi
0x140015b63  jz      short loc_140015B79
0x140015b65  xor     edx, edx
0x140015b67  mov     rcx, rdi
0x140015b6a  call    cs:__imp_UnloadProfileBasic
0x140015b70  mov     rcx, rdi; hObject
0x140015b73  call    cs:__imp_CloseHandle
0x140015b79  mov     rcx, [rbx+10h]
0x140015b7d  test    rcx, rcx
0x140015b80  jz      short loc_140015B88
0x140015b82  call    cs:__imp_ClosePseudoConsole
0x140015b88  mov     rdi, [rbx+8]
0x140015b8c  test    rdi, rdi
0x140015b8f  jz      short loc_140015BA6
0x140015b91  mov     rcx, rdi; this
0x140015b94  call    ??1ConsoleToPipeRedirector@@QEAA@XZ; ConsoleToPipeRedirector::~ConsoleToPipeRedirector(void)
0x140015b99  mov     edx, 180h; unsigned __int64
0x140015b9e  mov     rcx, rdi; void *
0x140015ba1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015ba6  mov     rcx, [rbx]; hObject
0x140015ba9  lea     rax, [rcx-1]
0x140015bad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140015bb1  ja      short loc_140015BB9
0x140015bb3  call    cs:__imp_CloseHandle
0x140015bb9  mov     rbx, [rsp+28h+arg_0]
0x140015bbe  add     rsp, 20h
0x140015bc2  pop     rdi
0x140015bc3  retn
```

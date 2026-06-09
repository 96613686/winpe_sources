# ActionDialogManager::~ActionDialogManager(void)

- ea: `0x140003430`
- end: `0x1400034e1`
- name: `??1ActionDialogManager@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(ActionDialogManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140007a78`

## callees

- `0x14000175c`
- `0x140003430`
- `0x14000a010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140003467`
- `KERNEL32!SetLastError` at `0x140003467`
- `KERNEL32!DeleteCriticalSection` at `0x140003478`
- `KERNEL32!DeleteCriticalSection` at `0x140003478`
- `KERNEL32!GetLastError` at `0x14000344a`
- `KERNEL32!GetLastError` at `0x14000344a`

## pseudocode

```c
void __fastcall ActionDialogManager::~ActionDialogManager(ActionDialogManager *this)
{
  void (__fastcall ***v1)(_QWORD, __int64); // rsi
  DWORD LastError; // ebx
  _QWORD **v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx

  v1 = *(void (__fastcall ****)(_QWORD, __int64))this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    (**v1)(v1, 1);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v4 = (_QWORD **)*((_QWORD *)this + 1);
  *v4[1] = 0;
  v5 = *v4;
  if ( v5 )
  {
    do
    {
      v6 = (_QWORD *)*v5;
      operator delete(v5);
      v5 = v6;
    }
    while ( v6 );
  }
  operator delete(*((void **)this + 1));
  if ( *(_QWORD *)this )
    (***(void (__fastcall ****)(_QWORD, __int64))this)(*(_QWORD *)this, 1);
}

```

## disassembly

```asm
0x140003430  mov     [rsp+arg_8], rbx
0x140003435  mov     [rsp+arg_10], rsi
0x14000343a  push    rdi
0x14000343b  sub     rsp, 20h
0x14000343f  mov     rsi, [rcx]
0x140003442  mov     rdi, rcx
0x140003445  test    rsi, rsi
0x140003448  jz      short loc_14000346D
0x14000344a  call    cs:__imp_GetLastError
0x140003450  mov     rdx, [rsi]
0x140003453  mov     rcx, rsi
0x140003456  mov     ebx, eax
0x140003458  mov     rax, [rdx]
0x14000345b  mov     edx, 1
0x140003460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003465  mov     ecx, ebx; dwErrCode
0x140003467  call    cs:__imp_SetLastError
0x14000346d  lea     rcx, [rdi+18h]; lpCriticalSection
0x140003471  mov     qword ptr [rdi], 0
0x140003478  call    cs:__imp_DeleteCriticalSection
0x14000347e  mov     rcx, [rdi+8]
0x140003482  mov     esi, 18h
0x140003487  mov     rax, [rcx+8]
0x14000348b  mov     qword ptr [rax], 0
0x140003492  mov     rcx, [rcx]; Block
0x140003495  test    rcx, rcx
0x140003498  jz      short loc_1400034AD
0x14000349a  mov     rbx, [rcx]
0x14000349d  mov     rdx, rsi
0x1400034a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400034a5  mov     rcx, rbx
0x1400034a8  test    rbx, rbx
0x1400034ab  jnz     short loc_14000349A
0x1400034ad  mov     rcx, [rdi+8]; Block
0x1400034b1  mov     rdx, rsi
0x1400034b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400034b9  mov     rcx, [rdi]
0x1400034bc  test    rcx, rcx
0x1400034bf  jz      short loc_1400034D1
0x1400034c1  mov     rax, [rcx]
0x1400034c4  mov     edx, 1
0x1400034c9  mov     rax, [rax]
0x1400034cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034d1  mov     rbx, [rsp+28h+arg_8]
0x1400034d6  mov     rsi, [rsp+28h+arg_10]
0x1400034db  add     rsp, 20h
0x1400034df  pop     rdi
0x1400034e0  retn
```

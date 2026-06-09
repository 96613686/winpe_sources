# CommonUtil::OpenCurrentThreadToken(void * *,ulong)

- ea: `0x1800da404`
- end: `0x1800da4a6`
- name: `?OpenCurrentThreadToken@CommonUtil@@YAJPEAPEAXK@Z`
- size: `162`
- prototype: `int(CommonUtil *__hidden this, void **, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c8b44`
- `0x1800df59c`

## callees

- `0x1800da404`
- `0x1800db5b8`
- `0x1800db638`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800da453`
- `KERNEL32!CloseHandle` at `0x1800da482`
- `KERNEL32!CloseHandle` at `0x1800da453`
- `KERNEL32!CloseHandle` at `0x1800da482`
- `KERNEL32!GetCurrentProcess` at `0x1800da440`
- `KERNEL32!GetCurrentProcess` at `0x1800da440`
- `KERNEL32!GetCurrentThread` at `0x1800da421`
- `KERNEL32!GetCurrentThread` at `0x1800da421`

## pseudocode

```c
__int64 __fastcall CommonUtil::OpenCurrentThreadToken(CommonUtil *this, void **a2)
{
  unsigned int v2; // esi
  void **CurrentThread; // rax
  unsigned int v5; // r9d
  int v6; // ebx
  void **CurrentProcess; // rbx
  bool v9; // [rsp+20h] [rbp-8h]
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  v2 = (unsigned int)a2;
  hObject = 0;
  CurrentThread = (void **)GetCurrentThread();
  v6 = CommonUtil::UtilOpenThreadToken((CommonUtil *)&hObject, CurrentThread, (void *)v2, v5, v9);
  if ( v6 == -2147023888 )
  {
    CurrentProcess = (void **)GetCurrentProcess();
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    v6 = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, CurrentProcess, (void *)v2);
  }
  if ( v6 >= 0 )
  {
    *(_QWORD *)this = hObject;
    return 0;
  }
  else
  {
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800da404  mov     [rsp+arg_0], rbx
0x1800da409  mov     [rsp+arg_8], rsi
0x1800da40e  push    rdi; bool
0x1800da40f  sub     rsp, 20h
0x1800da413  mov     esi, edx
0x1800da415  mov     [rsp+28h+hObject], 0
0x1800da41e  mov     rdi, rcx
0x1800da421  call    cs:__imp_GetCurrentThread
0x1800da427  mov     r8d, esi; void *
0x1800da42a  lea     rcx, [rsp+28h+hObject]; this
0x1800da42f  mov     rdx, rax; void **
0x1800da432  call    ?UtilOpenThreadToken@CommonUtil@@YAJPEAPEAXPEAXK_N@Z; CommonUtil::UtilOpenThreadToken(void * *,void *,ulong,bool)
0x1800da437  mov     ebx, eax
0x1800da439  cmp     eax, 800703F0h
0x1800da43e  jnz     short loc_1800DA474
0x1800da440  call    cs:__imp_GetCurrentProcess
0x1800da446  mov     rcx, [rsp+28h+hObject]; hObject
0x1800da44b  mov     rbx, rax
0x1800da44e  test    rcx, rcx
0x1800da451  jz      short loc_1800DA462
0x1800da453  call    cs:__imp_CloseHandle
0x1800da459  mov     [rsp+28h+hObject], 0
0x1800da462  mov     r8d, esi; void *
0x1800da465  lea     rcx, [rsp+28h+hObject]; this
0x1800da46a  mov     rdx, rbx; void **
0x1800da46d  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x1800da472  mov     ebx, eax
0x1800da474  test    ebx, ebx
0x1800da476  jns     short loc_1800DA48C
0x1800da478  mov     rcx, [rsp+28h+hObject]; hObject
0x1800da47d  test    rcx, rcx
0x1800da480  jz      short loc_1800DA488
0x1800da482  call    cs:__imp_CloseHandle
0x1800da488  mov     eax, ebx
0x1800da48a  jmp     short loc_1800DA496
0x1800da48c  mov     rax, [rsp+28h+hObject]
0x1800da491  mov     [rdi], rax
0x1800da494  xor     eax, eax
0x1800da496  mov     rbx, [rsp+28h+arg_0]
0x1800da49b  mov     rsi, [rsp+28h+arg_8]
0x1800da4a0  add     rsp, 20h
0x1800da4a4  pop     rdi
0x1800da4a5  retn
```

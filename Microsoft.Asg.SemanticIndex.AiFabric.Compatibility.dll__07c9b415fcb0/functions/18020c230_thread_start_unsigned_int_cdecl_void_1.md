# thread_start_unsigned_int_(__cdecl_)(void__)_1_

- ea: `0x18020c230`
- end: `0x18020c295`
- name: `thread_start_unsigned_int_(__cdecl_)(void__)_1_`
- size: `101`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18020c230`
- `0x18020c440`
- `0x1802123c8`
- `0x1802169e4`
- `0x18021bb58`
- `0x18021be74`
- `0x180242160`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18020c23e`
- `KERNEL32!GetLastError` at `0x18020c23e`
- `KERNEL32!ExitThread` at `0x18020c246`
- `KERNEL32!ExitThread` at `0x18020c246`

## pseudocode

```c
void __fastcall __noreturn thread_start_unsigned_int____cdecl___void____1_(_BYTE *lpThreadParameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !lpThreadParameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(_acrt_getptd() + 960) = lpThreadParameter;
  if ( (unsigned int)_acrt_get_begin_thread_init_policy() == 2 )
    lpThreadParameter[32] = (unsigned int)_acrt_RoInitialize(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))lpThreadParameter)(*((_QWORD *)lpThreadParameter + 1));
  endthreadex(v3);
}

```

## disassembly

```asm
0x18020c230  push    rbx
0x18020c232  sub     rsp, 20h
0x18020c236  mov     rbx, rcx
0x18020c239  test    rcx, rcx
0x18020c23c  jnz     short loc_18020C24D
0x18020c23e  call    cs:__imp_GetLastError
0x18020c244  mov     ecx, eax; dwExitCode
0x18020c246  call    cs:__imp_ExitThread
0x18020c24d  call    __acrt_getptd
0x18020c252  mov     [rax+3C0h], rbx
0x18020c259  call    __acrt_get_begin_thread_init_policy
0x18020c25e  cmp     eax, 2
0x18020c261  jnz     short loc_18020C273
0x18020c263  lea     ecx, [rax-1]
0x18020c266  call    __acrt_RoInitialize
0x18020c26b  test    eax, eax
0x18020c26d  setz    al
0x18020c270  mov     [rbx+20h], al
0x18020c273  mov     rcx, [rbx+8]
0x18020c277  mov     rax, [rbx]
0x18020c27a  call    _guard_dispatch_icall
0x18020c27f  mov     ecx, eax; ReturnCode
0x18020c281  call    _endthreadex
0x18020c287  mov     ecx, eax; Code
0x18020c289  call    _exit
0x18020c28f  add     rsp, 20h
0x18020c293  pop     rbx
0x18020c294  retn
```

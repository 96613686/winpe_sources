# thread_start_unsigned_int_(__cdecl_)(void_____ptr64)_

- ea: `0x18033ee60`
- end: `0x18033eed8`
- name: `thread_start_unsigned_int_(__cdecl_)(void_____ptr64)_`
- size: `120`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180023c50`
- `0x18033ee38`
- `0x18033ee60`
- `0x18033f080`
- `0x180347ac4`
- `0x180349414`
- `0x18034eaf4`
- `0x18034edac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033ee72`
- `KERNEL32!GetLastError` at `0x18033ee72`
- `KERNEL32!ExitThread` at `0x18033ee7a`
- `KERNEL32!ExitThread` at `0x18033ee7a`

## pseudocode

```c
void __fastcall __noreturn thread_start_unsigned_int____cdecl___void_____ptr64__(_BYTE *lpThreadParameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !lpThreadParameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(_acrt_getptd() + 960) = lpThreadParameter;
  if ( (unsigned __int8)_acrt_is_packaged_app() )
    lpThreadParameter[32] = (unsigned int)_acrt_RoInitialize(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))lpThreadParameter)(*((_QWORD *)lpThreadParameter + 1));
  endthreadex(v3);
}

```

## disassembly

```asm
0x18033ee60  mov     [rsp+arg_0], rbx
0x18033ee65  push    rdi
0x18033ee66  sub     rsp, 20h
0x18033ee6a  mov     rbx, rcx
0x18033ee6d  test    rcx, rcx
0x18033ee70  jnz     short loc_18033EE81
0x18033ee72  call    cs:__imp_GetLastError
0x18033ee78  mov     ecx, eax; dwExitCode
0x18033ee7a  call    cs:__imp_ExitThread
0x18033ee81  call    __acrt_getptd
0x18033ee86  mov     [rax+3C0h], rbx
0x18033ee8d  call    __acrt_is_packaged_app
0x18033ee92  test    al, al
0x18033ee94  jz      short loc_18033EEA8
0x18033ee96  mov     ecx, 1
0x18033ee9b  call    __acrt_RoInitialize
0x18033eea0  test    eax, eax
0x18033eea2  setz    al
0x18033eea5  mov     [rbx+20h], al
0x18033eea8  mov     rdi, [rbx]
0x18033eeab  mov     rbx, [rbx+8]
0x18033eeaf  mov     rcx, rdi; this
0x18033eeb2  call    cs:__guard_check_icall_fptr
0x18033eeb8  mov     rcx, rbx
0x18033eebb  call    rdi
0x18033eebd  mov     ecx, eax; ReturnCode
0x18033eebf  call    _endthreadex
0x18033eec5  mov     ecx, eax; Code
0x18033eec7  call    _exit
0x18033eecd  mov     rbx, [rsp+28h+arg_0]
0x18033eed2  add     rsp, 20h
0x18033eed6  pop     rdi
0x18033eed7  retn
0x18036abb1  push    rbp
0x18036abb3  sub     rsp, 20h
0x18036abb7  mov     rbp, rdx
0x18036abba  mov     rax, [rcx]
0x18036abbd  mov     rdx, rcx; ExceptionPtr
0x18036abc0  mov     ecx, [rax]; ExceptionNum
0x18036abc2  call    _seh_filter_exe
0x18036abc7  nop
0x18036abc8  add     rsp, 20h
0x18036abcc  pop     rbp
0x18036abcd  retn
```

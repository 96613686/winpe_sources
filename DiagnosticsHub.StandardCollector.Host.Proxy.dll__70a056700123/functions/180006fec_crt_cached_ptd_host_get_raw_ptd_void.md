# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x180006fec`
- end: `0x180007053`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `103`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `69`
- callee_count: `3`
- tags: ``

## callers

- `0x180006dc4`
- `0x18000734c`
- `0x18000f22c`
- `0x1800149cc`
- `0x180015458`
- `0x18001af04`
- `0x18001afa4`
- `0x18001b044`
- `0x18001b0e8`
- `0x18001b304`
- `0x18001b3a8`
- `0x18001bb34`
- `0x18001bc0c`
- `0x18001bcd4`
- `0x18001bdbc`
- `0x18001be60`
- `0x18001cf90`
- `0x18001d028`
- `0x18001f11c`
- `0x18001f1d8`
- `0x18001f294`
- `0x18001f354`
- `0x18001f968`
- `0x18001fa1c`
- `0x18001fad8`
- `0x18001fb94`
- `0x18001fc50`
- `0x18001fde8`
- `0x18001fe98`
- `0x18001ff4c`
- `0x180020008`
- `0x1800200c4`
- `0x180020174`
- `0x180020230`
- `0x1800202e4`
- `0x1800203a0`
- `0x180020450`
- `0x180020500`
- `0x180020ec0`
- `0x180021350`
- `0x1800214ac`
- `0x180021e18`
- `0x180021ec0`
- `0x180021f78`
- `0x180022014`
- `0x180055b90`
- `0x180055cb4`
- `0x180055dd8`
- `0x180055efc`
- `0x180056020`

## callees

- `0x180006880`
- `0x180006fec`
- `0x18000f790`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006fff`
- `KERNEL32!GetLastError` at `0x180006fff`
- `KERNEL32!SetLastError` at `0x180007034`
- `KERNEL32!SetLastError` at `0x180007034`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd(__crt_cached_ptd_host *this)
{
  DWORD LastError; // eax
  bool v3; // zf
  __int64 v4; // rdx
  __int64 v5; // rax
  DWORD v6; // ecx
  __int64 v7; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
  {
    LastError = GetLastError();
    v3 = *((_BYTE *)this + 16) == 0;
    dwErrCode = LastError;
    if ( v3 )
    {
      *((_QWORD *)this + 1) = 0;
      v4 = 0;
      *((_BYTE *)this + 16) = 1;
    }
    else
    {
      v4 = *((_QWORD *)this + 1);
    }
    v5 = _acrt_getptd_noexit_explicit(&dwErrCode, v4);
    v6 = dwErrCode;
    v7 = v5;
    *(_QWORD *)this = v5;
    SetLastError(v6);
    if ( !v7 )
      abort();
  }
  return *(struct __acrt_ptd **)this;
}

```

## disassembly

```asm
0x180006fec  mov     [rsp+arg_8], rbx
0x180006ff1  push    rdi
0x180006ff2  sub     rsp, 20h
0x180006ff6  cmp     qword ptr [rcx], 0
0x180006ffa  mov     rdi, rcx
0x180006ffd  jnz     short loc_18000703F
0x180006fff  call    cs:__imp_GetLastError
0x180007005  cmp     byte ptr [rdi+10h], 0
0x180007009  mov     [rsp+28h+dwErrCode], eax
0x18000700d  jnz     short loc_18000701C
0x18000700f  and     qword ptr [rdi+8], 0
0x180007014  xor     edx, edx
0x180007016  mov     byte ptr [rdi+10h], 1
0x18000701a  jmp     short loc_180007020
0x18000701c  mov     rdx, [rdi+8]
0x180007020  lea     rcx, [rsp+28h+dwErrCode]
0x180007025  call    __acrt_getptd_noexit_explicit
0x18000702a  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18000702e  mov     rbx, rax
0x180007031  mov     [rdi], rax
0x180007034  call    cs:__imp_SetLastError
0x18000703a  test    rbx, rbx
0x18000703d  jz      short loc_18000704D
0x18000703f  mov     rax, [rdi]
0x180007042  mov     rbx, [rsp+28h+arg_8]
0x180007047  add     rsp, 20h
0x18000704b  pop     rdi
0x18000704c  retn
0x18000704d  call    abort
```

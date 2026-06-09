# __crt_cached_ptd_host::get_raw_ptd_noexit(void)

- ea: `0x140004348`
- end: `0x1400043b2`
- name: `?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004614`

## callees

- `0x140004348`
- `0x140010180`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004364`
- `KERNEL32!GetLastError` at `0x140004364`
- `KERNEL32!SetLastError` at `0x140004399`
- `KERNEL32!SetLastError` at `0x140004399`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd_noexit(__crt_cached_ptd_host *this)
{
  __int64 v1; // rsi
  __int64 v2; // rdi
  __int64 v4; // rax
  DWORD v5; // ecx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  v2 = 0;
  if ( !*(_QWORD *)this )
  {
    dwErrCode = GetLastError();
    if ( *((_BYTE *)this + 16) )
    {
      v2 = *((_QWORD *)this + 1);
    }
    else
    {
      *((_QWORD *)this + 1) = 0;
      *((_BYTE *)this + 16) = 1;
    }
    v4 = _acrt_getptd_noexit_explicit(&dwErrCode, v2);
    v5 = dwErrCode;
    v1 = v4;
    *(_QWORD *)this = v4;
    SetLastError(v5);
  }
  return (struct __acrt_ptd *)v1;
}

```

## disassembly

```asm
0x140004348  mov     [rsp+arg_8], rbx
0x14000434d  mov     [rsp+arg_10], rsi
0x140004352  push    rdi
0x140004353  sub     rsp, 20h
0x140004357  mov     rsi, [rcx]
0x14000435a  xor     edi, edi
0x14000435c  mov     rbx, rcx
0x14000435f  test    rsi, rsi
0x140004362  jnz     short loc_14000439F
0x140004364  call    cs:GetLastError
0x14000436a  mov     [rsp+28h+dwErrCode], eax
0x14000436e  cmp     [rbx+10h], dil
0x140004372  jnz     short loc_14000437E
0x140004374  mov     [rbx+8], rdi
0x140004378  mov     byte ptr [rbx+10h], 1
0x14000437c  jmp     short loc_140004382
0x14000437e  mov     rdi, [rbx+8]
0x140004382  mov     rdx, rdi
0x140004385  lea     rcx, [rsp+28h+dwErrCode]
0x14000438a  call    __acrt_getptd_noexit_explicit
0x14000438f  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x140004393  mov     rsi, rax
0x140004396  mov     [rbx], rax
0x140004399  call    cs:SetLastError
0x14000439f  mov     rbx, [rsp+28h+arg_8]
0x1400043a4  mov     rax, rsi
0x1400043a7  mov     rsi, [rsp+28h+arg_10]
0x1400043ac  add     rsp, 20h
0x1400043b0  pop     rdi
0x1400043b1  retn
```

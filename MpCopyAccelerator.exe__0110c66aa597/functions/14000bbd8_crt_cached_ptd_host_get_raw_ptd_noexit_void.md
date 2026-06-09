# __crt_cached_ptd_host::get_raw_ptd_noexit(void)

- ea: `0x14000bbd8`
- end: `0x14000bc42`
- name: `?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bea4`

## callees

- `0x14000bbd8`
- `0x140013c58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000bc29`
- `KERNEL32!SetLastError` at `0x14000bc29`
- `KERNEL32!GetLastError` at `0x14000bbf4`
- `KERNEL32!GetLastError` at `0x14000bbf4`

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
0x14000bbd8  mov     [rsp+arg_8], rbx
0x14000bbdd  mov     [rsp+arg_10], rsi
0x14000bbe2  push    rdi
0x14000bbe3  sub     rsp, 20h
0x14000bbe7  mov     rsi, [rcx]
0x14000bbea  xor     edi, edi
0x14000bbec  mov     rbx, rcx
0x14000bbef  test    rsi, rsi
0x14000bbf2  jnz     short loc_14000BC2F
0x14000bbf4  call    cs:__imp_GetLastError
0x14000bbfa  mov     [rsp+28h+dwErrCode], eax
0x14000bbfe  cmp     [rbx+10h], dil
0x14000bc02  jnz     short loc_14000BC0E
0x14000bc04  mov     [rbx+8], rdi
0x14000bc08  mov     byte ptr [rbx+10h], 1
0x14000bc0c  jmp     short loc_14000BC12
0x14000bc0e  mov     rdi, [rbx+8]
0x14000bc12  mov     rdx, rdi
0x14000bc15  lea     rcx, [rsp+28h+dwErrCode]
0x14000bc1a  call    __acrt_getptd_noexit_explicit
0x14000bc1f  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x14000bc23  mov     rsi, rax
0x14000bc26  mov     [rbx], rax
0x14000bc29  call    cs:__imp_SetLastError
0x14000bc2f  mov     rbx, [rsp+28h+arg_8]
0x14000bc34  mov     rax, rsi
0x14000bc37  mov     rsi, [rsp+28h+arg_10]
0x14000bc3c  add     rsp, 20h
0x14000bc40  pop     rdi
0x14000bc41  retn
```

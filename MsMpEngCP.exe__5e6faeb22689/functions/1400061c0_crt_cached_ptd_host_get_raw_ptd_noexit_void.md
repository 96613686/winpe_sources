# __crt_cached_ptd_host::get_raw_ptd_noexit(void)

- ea: `0x1400061c0`
- end: `0x14000622a`
- name: `?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000648c`

## callees

- `0x1400060d8`
- `0x1400061c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400061dc`
- `KERNEL32!GetLastError` at `0x1400061dc`
- `KERNEL32!SetLastError` at `0x140006211`
- `KERNEL32!SetLastError` at `0x140006211`

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
    v4 = sub_1400060D8(&dwErrCode, v2);
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
0x1400061c0  mov     [rsp+arg_8], rbx
0x1400061c5  mov     [rsp+arg_10], rsi
0x1400061ca  push    rdi
0x1400061cb  sub     rsp, 20h
0x1400061cf  mov     rsi, [rcx]
0x1400061d2  xor     edi, edi
0x1400061d4  mov     rbx, rcx
0x1400061d7  test    rsi, rsi
0x1400061da  jnz     short loc_140006217
0x1400061dc  call    cs:GetLastError
0x1400061e2  mov     [rsp+28h+dwErrCode], eax
0x1400061e6  cmp     [rbx+10h], dil
0x1400061ea  jnz     short loc_1400061F6
0x1400061ec  mov     [rbx+8], rdi
0x1400061f0  mov     byte ptr [rbx+10h], 1
0x1400061f4  jmp     short loc_1400061FA
0x1400061f6  mov     rdi, [rbx+8]
0x1400061fa  mov     rdx, rdi
0x1400061fd  lea     rcx, [rsp+28h+dwErrCode]
0x140006202  call    sub_1400060D8
0x140006207  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x14000620b  mov     rsi, rax
0x14000620e  mov     [rbx], rax
0x140006211  call    cs:SetLastError
0x140006217  mov     rbx, [rsp+28h+arg_8]
0x14000621c  mov     rax, rsi
0x14000621f  mov     rsi, [rsp+28h+arg_10]
0x140006224  add     rsp, 20h
0x140006228  pop     rdi
0x140006229  retn
```

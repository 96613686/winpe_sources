# __crt_cached_ptd_host::get_raw_ptd_noexit(void)

- ea: `0x140015d18`
- end: `0x140015d82`
- name: `?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015fe4`

## callees

- `0x140015d18`
- `0x140019748`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140015d69`
- `KERNEL32!SetLastError` at `0x140015d69`
- `KERNEL32!GetLastError` at `0x140015d34`
- `KERNEL32!GetLastError` at `0x140015d34`

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
    v4 = sub_140019748(&dwErrCode, v2);
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
0x140015d18  mov     [rsp+arg_8], rbx
0x140015d1d  mov     [rsp+arg_10], rsi
0x140015d22  push    rdi
0x140015d23  sub     rsp, 20h
0x140015d27  mov     rsi, [rcx]
0x140015d2a  xor     edi, edi
0x140015d2c  mov     rbx, rcx
0x140015d2f  test    rsi, rsi
0x140015d32  jnz     short loc_140015D6F
0x140015d34  call    cs:GetLastError
0x140015d3a  mov     [rsp+28h+dwErrCode], eax
0x140015d3e  cmp     [rbx+10h], dil
0x140015d42  jnz     short loc_140015D4E
0x140015d44  mov     [rbx+8], rdi
0x140015d48  mov     byte ptr [rbx+10h], 1
0x140015d4c  jmp     short loc_140015D52
0x140015d4e  mov     rdi, [rbx+8]
0x140015d52  mov     rdx, rdi
0x140015d55  lea     rcx, [rsp+28h+dwErrCode]
0x140015d5a  call    sub_140019748
0x140015d5f  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x140015d63  mov     rsi, rax
0x140015d66  mov     [rbx], rax
0x140015d69  call    cs:SetLastError
0x140015d6f  mov     rbx, [rsp+28h+arg_8]
0x140015d74  mov     rax, rsi
0x140015d77  mov     rsi, [rsp+28h+arg_10]
0x140015d7c  add     rsp, 20h
0x140015d80  pop     rdi
0x140015d81  retn
```

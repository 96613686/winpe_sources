# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x14000bb70`
- end: `0x14000bbd7`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `103`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be08`
- `0x14000c750`
- `0x140010784`
- `0x1400109d8`
- `0x140016544`
- `0x14001a054`

## callees

- `0x14000bb70`
- `0x140013658`
- `0x140013c58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000bbb8`
- `KERNEL32!SetLastError` at `0x14000bbb8`
- `KERNEL32!GetLastError` at `0x14000bb83`
- `KERNEL32!GetLastError` at `0x14000bb83`

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
0x14000bb70  mov     [rsp+arg_8], rbx
0x14000bb75  push    rdi
0x14000bb76  sub     rsp, 20h
0x14000bb7a  cmp     qword ptr [rcx], 0
0x14000bb7e  mov     rdi, rcx
0x14000bb81  jnz     short loc_14000BBC3
0x14000bb83  call    cs:__imp_GetLastError
0x14000bb89  cmp     byte ptr [rdi+10h], 0
0x14000bb8d  mov     [rsp+28h+dwErrCode], eax
0x14000bb91  jnz     short loc_14000BBA0
0x14000bb93  and     qword ptr [rdi+8], 0
0x14000bb98  xor     edx, edx
0x14000bb9a  mov     byte ptr [rdi+10h], 1
0x14000bb9e  jmp     short loc_14000BBA4
0x14000bba0  mov     rdx, [rdi+8]
0x14000bba4  lea     rcx, [rsp+28h+dwErrCode]
0x14000bba9  call    __acrt_getptd_noexit_explicit
0x14000bbae  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x14000bbb2  mov     rbx, rax
0x14000bbb5  mov     [rdi], rax
0x14000bbb8  call    cs:__imp_SetLastError
0x14000bbbe  test    rbx, rbx
0x14000bbc1  jz      short loc_14000BBD1
0x14000bbc3  mov     rax, [rdi]
0x14000bbc6  mov     rbx, [rsp+28h+arg_8]
0x14000bbcb  add     rsp, 20h
0x14000bbcf  pop     rdi
0x14000bbd0  retn
0x14000bbd1  call    abort
```

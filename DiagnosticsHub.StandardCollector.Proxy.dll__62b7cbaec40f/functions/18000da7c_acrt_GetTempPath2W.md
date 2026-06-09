# __acrt_GetTempPath2W

- ea: `0x18000da7c`
- end: `0x18000dae1`
- name: `__acrt_GetTempPath2W`
- size: `101`
- prototype: `__int64 __fastcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000d058`
- `0x18000da7c`
- `0x180060430`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x18000dad0`
- `KERNEL32!GetTempPathW` at `0x18000dad0`

## string_xrefs

- `0x18000da9d`: `GetTempPath2W`
- `0x18000daab`: `GetTempPath2W`

## pseudocode

```c
DWORD __fastcall _acrt_GetTempPath2W(DWORD nBufferLength, LPWSTR lpBuffer)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_180082030;
  if ( qword_180082030 != -1
    && (qword_180082030
     || (function_slow = try_get_function_slow(
                           6u,
                           "GetTempPath2W",
                           (unsigned int *)&qword_180067880,
                           (unsigned int *)"GetTempPath2W")) != 0) )
  {
    return ((__int64 (__fastcall *)(_QWORD, LPWSTR))function_slow)(nBufferLength, lpBuffer);
  }
  else
  {
    return GetTempPathW(nBufferLength, lpBuffer);
  }
}

```

## disassembly

```asm
0x18000da7c  mov     [rsp+arg_0], rbx
0x18000da81  push    rdi
0x18000da82  sub     rsp, 20h
0x18000da86  mov     rax, cs:qword_180082030
0x18000da8d  mov     rbx, rdx
0x18000da90  mov     edi, ecx
0x18000da92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000da96  jz      short loc_18000DACB
0x18000da98  test    rax, rax
0x18000da9b  jnz     short loc_18000DABF
0x18000da9d  lea     r9, aGettemppath2w; "GetTempPath2W"
0x18000daa4  lea     r8, qword_180067880
0x18000daab  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18000dab2  lea     ecx, [rax+6]
0x18000dab5  call    try_get_function_slow
0x18000daba  test    rax, rax
0x18000dabd  jz      short loc_18000DACB
0x18000dabf  mov     rdx, rbx
0x18000dac2  mov     ecx, edi
0x18000dac4  call    _guard_dispatch_icall
0x18000dac9  jmp     short loc_18000DAD6
0x18000dacb  mov     rdx, rbx; lpBuffer
0x18000dace  mov     ecx, edi; nBufferLength
0x18000dad0  call    cs:__imp_GetTempPathW
0x18000dad6  mov     rbx, [rsp+28h+arg_0]
0x18000dadb  add     rsp, 20h
0x18000dadf  pop     rdi
0x18000dae0  retn
```

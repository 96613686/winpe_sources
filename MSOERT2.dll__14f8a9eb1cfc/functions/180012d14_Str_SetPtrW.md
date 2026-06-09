# Str_SetPtrW

- ea: `0x180012d14`
- end: `0x180012d64`
- name: `Str_SetPtrW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR *ppsz, LPCWSTR psz)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d860`
- `0x18000de50`
- `0x18000e0b0`

## callees

- `0x180012d14`
- `0x180012dd4`
- `0x180014010`

## pseudocode

```c
BOOL __stdcall Str_SetPtrW(LPWSTR *ppsz, LPCWSTR psz)
{
  __int64 (__fastcall *v2)(LPWSTR *, LPCWSTR); // rax

  v2 = (__int64 (__fastcall *)(LPWSTR *, LPCWSTR))qword_18001C0E0;
  if ( qword_18001C0E0 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_18001C0E0, (const CHAR *)0xEC);
    v2 = (__int64 (__fastcall *)(LPWSTR *, LPCWSTR))qword_18001C0E0;
  }
  if ( v2 )
    LODWORD(v2) = v2(ppsz, psz);
  return (int)v2;
}

```

## disassembly

```asm
0x180012d14  mov     [rsp+arg_0], rbx
0x180012d19  push    rdi
0x180012d1a  sub     rsp, 20h
0x180012d1e  mov     rax, cs:qword_18001C0E0
0x180012d25  mov     rbx, rdx
0x180012d28  mov     rdi, rcx
0x180012d2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012d2f  jnz     short loc_180012D49
0x180012d31  mov     edx, 0ECh
0x180012d36  lea     rcx, qword_18001C0E0
0x180012d3d  call    _GetProcFromComCtl32
0x180012d42  mov     rax, cs:qword_18001C0E0
0x180012d49  test    rax, rax
0x180012d4c  jz      short loc_180012D59
0x180012d4e  mov     rdx, rbx
0x180012d51  mov     rcx, rdi
0x180012d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d59  mov     rbx, [rsp+28h+arg_0]
0x180012d5e  add     rsp, 20h
0x180012d62  pop     rdi
0x180012d63  retn
```

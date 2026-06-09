# CByteStream::_HrGrowBuffer(ulong,ulong)

- ea: `0x180011ecc`
- end: `0x180011f28`
- name: `?_HrGrowBuffer@CByteStream@@AEAAJKK@Z`
- size: `92`
- prototype: `__int64 __fastcall(CByteStream *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180011db0`
- `0x180011e40`

## callees

- `0x180011ecc`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180011ef8`
- `ole32!CoTaskMemRealloc` at `0x180011ef8`

## pseudocode

```c
__int64 __fastcall CByteStream::_HrGrowBuffer(CByteStream *this, int a2, int a3)
{
  unsigned int v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  LPVOID v7; // rcx
  __int64 result; // rax

  v4 = *((_DWORD *)this + 3) + 1;
  if ( !v4 )
    return 2147942934LL;
  v5 = v4 + a2;
  if ( v4 + a2 < v4 )
    return 2147942934LL;
  v6 = v5 + a3;
  if ( v5 + a3 < v5 )
    return 2147942934LL;
  v7 = CoTaskMemRealloc(*((LPVOID *)this + 3), v6);
  if ( !v7 )
    return 2147942414LL;
  result = 0;
  *((_QWORD *)this + 3) = v7;
  *((_DWORD *)this + 4) = v6;
  return result;
}

```

## disassembly

```asm
0x180011ecc  mov     [rsp+arg_0], rbx
0x180011ed1  push    rdi
0x180011ed2  sub     rsp, 20h
0x180011ed6  mov     rdi, rcx
0x180011ed9  mov     ecx, [rcx+0Ch]
0x180011edc  inc     ecx
0x180011ede  cmp     ecx, 1
0x180011ee1  jb      short loc_180011F18
0x180011ee3  lea     eax, [rcx+rdx]
0x180011ee6  cmp     eax, ecx
0x180011ee8  jb      short loc_180011F18
0x180011eea  lea     ebx, [rax+r8]
0x180011eee  cmp     ebx, eax
0x180011ef0  jb      short loc_180011F18
0x180011ef2  mov     rcx, [rdi+18h]; pv
0x180011ef6  mov     edx, ebx; cb
0x180011ef8  call    cs:__imp_CoTaskMemRealloc
0x180011efe  mov     rcx, rax
0x180011f01  test    rax, rax
0x180011f04  jnz     short loc_180011F0D
0x180011f06  mov     eax, 8007000Eh
0x180011f0b  jmp     short loc_180011F1D
0x180011f0d  xor     eax, eax
0x180011f0f  mov     [rdi+18h], rcx
0x180011f13  mov     [rdi+10h], ebx
0x180011f16  jmp     short loc_180011F1D
0x180011f18  mov     eax, 80070216h
0x180011f1d  mov     rbx, [rsp+28h+arg_0]
0x180011f22  add     rsp, 20h
0x180011f26  pop     rdi
0x180011f27  retn
```

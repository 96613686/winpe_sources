# CAudioTimeCompression::freeTemps(void)

- ea: `0x180050f60`
- end: `0x180051020`
- name: `?freeTemps@CAudioTimeCompression@@IEAAJXZ`
- size: `192`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aa40`
- `0x18004fd30`

## callees

- `0x180050f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050f75`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050f8d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fa5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fbd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fd5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050f75`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050f8d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fa5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fbd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180050fd5`

## pseudocode

```c
__int64 __fastcall CAudioTimeCompression::freeTemps(CAudioTimeCompression *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 result; // rax

  v2 = (void *)*((_QWORD *)this + 20);
  if ( v2 )
    _aligned_free(v2);
  v3 = (void *)*((_QWORD *)this + 21);
  if ( v3 )
    _aligned_free(v3);
  v4 = (void *)*((_QWORD *)this + 22);
  if ( v4 )
    _aligned_free(v4);
  v5 = (void *)*((_QWORD *)this + 23);
  if ( v5 )
    _aligned_free(v5);
  v6 = (void *)*((_QWORD *)this + 24);
  if ( v6 )
    _aligned_free(v6);
  result = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_DWORD *)this + 38) = 0;
  return result;
}

```

## disassembly

```asm
0x180050f60  push    rbx
0x180050f62  sub     rsp, 20h
0x180050f66  mov     rbx, rcx
0x180050f69  mov     rcx, [rcx+0A0h]; Block
0x180050f70  test    rcx, rcx
0x180050f73  jz      short loc_180050F81
0x180050f75  call    cs:__imp__aligned_free
0x180050f7c  nop     dword ptr [rax+rax+00h]
0x180050f81  mov     rcx, [rbx+0A8h]; Block
0x180050f88  test    rcx, rcx
0x180050f8b  jz      short loc_180050F99
0x180050f8d  call    cs:__imp__aligned_free
0x180050f94  nop     dword ptr [rax+rax+00h]
0x180050f99  mov     rcx, [rbx+0B0h]; Block
0x180050fa0  test    rcx, rcx
0x180050fa3  jz      short loc_180050FB1
0x180050fa5  call    cs:__imp__aligned_free
0x180050fac  nop     dword ptr [rax+rax+00h]
0x180050fb1  mov     rcx, [rbx+0B8h]; Block
0x180050fb8  test    rcx, rcx
0x180050fbb  jz      short loc_180050FC9
0x180050fbd  call    cs:__imp__aligned_free
0x180050fc4  nop     dword ptr [rax+rax+00h]
0x180050fc9  mov     rcx, [rbx+0C0h]; Block
0x180050fd0  test    rcx, rcx
0x180050fd3  jz      short loc_180050FE1
0x180050fd5  call    cs:__imp__aligned_free
0x180050fdc  nop     dword ptr [rax+rax+00h]
0x180050fe1  xor     eax, eax
0x180050fe3  mov     [rbx+0A0h], rax
0x180050fea  mov     [rbx+0A8h], rax
0x180050ff1  mov     [rbx+0B0h], rax
0x180050ff8  mov     [rbx+0C8h], rax
0x180050fff  mov     [rbx+0B8h], rax
0x180051006  mov     [rbx+0C0h], rax
0x18005100d  mov     [rbx+0D0h], eax
0x180051013  mov     [rbx+98h], eax
0x180051019  add     rsp, 20h
0x18005101d  pop     rbx
0x18005101e  retn
```

# XLWrite::IncreaseBuffer(ulong)

- ea: `0x180044ec4`
- end: `0x180044f61`
- name: `?IncreaseBuffer@XLWrite@@AEAAJK@Z`
- size: `157`
- prototype: `__int64 __fastcall(XLWrite *__hidden this, unsigned int)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f700`
- `0x18000f7ac`
- `0x180011dd0`
- `0x180011e70`
- `0x180012cf0`
- `0x180013e00`
- `0x180014270`
- `0x1800148e0`
- `0x1800152e0`
- `0x1800159a8`
- `0x18001db60`
- `0x18003204c`
- `0x18003235c`
- `0x18003dbb0`
- `0x180042668`
- `0x180045b8c`

## callees

- `0x180044ec4`
- `0x180074580`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180044f46`
- `KERNEL32!LocalFree` at `0x180044f46`
- `KERNEL32!LocalAlloc` at `0x180044f14`
- `KERNEL32!LocalAlloc` at `0x180044f14`

## pseudocode

```c
__int64 __fastcall XLWrite::IncreaseBuffer(XLWrite *this, int a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edx
  unsigned int v5; // ebx
  __int64 result; // rax
  char *v7; // rax
  char *v8; // rsi
  const void *v9; // rdx
  void *v10; // rcx
  char *v11; // rax

  v2 = *((_DWORD *)this + 6);
  v4 = v2 + a2;
  if ( v4 < v2 )
    return 2147549183LL;
  v5 = v2 + 2048;
  if ( v2 + 2048 < v2 || v4 > 0xFFFFF7FF )
    return 2147549183LL;
  while ( v5 < v4 )
    v5 += 2048;
  v7 = (char *)LocalAlloc(0, v5);
  v8 = v7;
  if ( !v7 )
    return 2147549183LL;
  v9 = (const void *)*((_QWORD *)this + 1);
  if ( v9 )
  {
    if ( *((_DWORD *)this + 7) )
      memcpy_0(v7, v9, *((unsigned int *)this + 7));
    v10 = (void *)*((_QWORD *)this + 1);
    if ( v10 )
      LocalFree(v10);
  }
  v11 = &v8[*((unsigned int *)this + 7)];
  *((_DWORD *)this + 6) = v5;
  *((_QWORD *)this + 2) = v11;
  result = 0;
  *((_QWORD *)this + 1) = v8;
  return result;
}

```

## disassembly

```asm
0x180044ec4  mov     [rsp+arg_0], rbx
0x180044ec9  mov     [rsp+arg_8], rsi
0x180044ece  push    rdi
0x180044ecf  sub     rsp, 20h
0x180044ed3  mov     eax, [rcx+18h]
0x180044ed6  mov     rdi, rcx
0x180044ed9  add     edx, eax
0x180044edb  cmp     edx, eax
0x180044edd  jb      short loc_180044EF1
0x180044edf  lea     ebx, [rax+800h]
0x180044ee5  cmp     ebx, eax
0x180044ee7  jb      short loc_180044EF1
0x180044ee9  cmp     edx, 0FFFFF7FFh
0x180044eef  jbe     short loc_180044F0C
0x180044ef1  mov     eax, 8000FFFFh
0x180044ef6  mov     rbx, [rsp+28h+arg_0]
0x180044efb  mov     rsi, [rsp+28h+arg_8]
0x180044f00  add     rsp, 20h
0x180044f04  pop     rdi
0x180044f05  retn
0x180044f06  add     ebx, 800h
0x180044f0c  cmp     ebx, edx
0x180044f0e  jb      short loc_180044F06
0x180044f10  mov     edx, ebx; uBytes
0x180044f12  xor     ecx, ecx; uFlags
0x180044f14  call    cs:__imp_LocalAlloc
0x180044f1a  mov     rsi, rax
0x180044f1d  test    rax, rax
0x180044f20  jz      short loc_180044EF1
0x180044f22  mov     rdx, [rdi+8]; Src
0x180044f26  test    rdx, rdx
0x180044f29  jz      short loc_180044F4C
0x180044f2b  cmp     dword ptr [rdi+1Ch], 0
0x180044f2f  jbe     short loc_180044F3D
0x180044f31  mov     r8d, [rdi+1Ch]; Size
0x180044f35  mov     rcx, rax; void *
0x180044f38  call    memcpy_0
0x180044f3d  mov     rcx, [rdi+8]; hMem
0x180044f41  test    rcx, rcx
0x180044f44  jz      short loc_180044F4C
0x180044f46  call    cs:__imp_LocalFree
0x180044f4c  mov     eax, [rdi+1Ch]
0x180044f4f  add     rax, rsi
0x180044f52  mov     [rdi+18h], ebx
0x180044f55  mov     [rdi+10h], rax
0x180044f59  xor     eax, eax
0x180044f5b  mov     [rdi+8], rsi
0x180044f5f  jmp     short loc_180044EF6
```

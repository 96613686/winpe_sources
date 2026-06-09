# XLWrite::IncreaseBuffer(ulong)

- ea: `0x1800461b4`
- end: `0x18004625e`
- name: `?IncreaseBuffer@XLWrite@@AEAAJK@Z`
- size: `170`
- prototype: `__int64 __fastcall(XLWrite *this, int)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f798`
- `0x18000f844`
- `0x180011ed0`
- `0x180012010`
- `0x180012f00`
- `0x180014040`
- `0x1800144c0`
- `0x180014b40`
- `0x180015540`
- `0x180015c10`
- `0x18001df20`
- `0x180032930`
- `0x180032c74`
- `0x18003ea0c`
- `0x180043844`
- `0x180046f3c`

## callees

- `0x1800461b4`
- `0x180076660`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004623d`
- `KERNEL32!LocalFree` at `0x18004623d`
- `KERNEL32!LocalAlloc` at `0x180046205`
- `KERNEL32!LocalAlloc` at `0x180046205`

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
0x1800461b4  mov     [rsp+arg_0], rbx
0x1800461b9  mov     [rsp+arg_8], rsi
0x1800461be  push    rdi
0x1800461bf  sub     rsp, 20h
0x1800461c3  mov     eax, [rcx+18h]
0x1800461c6  mov     rdi, rcx
0x1800461c9  add     edx, eax
0x1800461cb  cmp     edx, eax
0x1800461cd  jb      short loc_1800461E1
0x1800461cf  lea     ebx, [rax+800h]
0x1800461d5  cmp     ebx, eax
0x1800461d7  jb      short loc_1800461E1
0x1800461d9  cmp     edx, 0FFFFF7FFh
0x1800461df  jbe     short loc_1800461FD
0x1800461e1  mov     eax, 8000FFFFh
0x1800461e6  mov     rbx, [rsp+28h+arg_0]
0x1800461eb  mov     rsi, [rsp+28h+arg_8]
0x1800461f0  add     rsp, 20h
0x1800461f4  pop     rdi
0x1800461f5  retn
0x1800461f7  add     ebx, 800h
0x1800461fd  cmp     ebx, edx
0x1800461ff  jb      short loc_1800461F7
0x180046201  mov     edx, ebx; uBytes
0x180046203  xor     ecx, ecx; uFlags
0x180046205  call    cs:__imp_LocalAlloc
0x18004620c  nop     dword ptr [rax+rax+00h]
0x180046211  mov     rsi, rax
0x180046214  test    rax, rax
0x180046217  jz      short loc_1800461E1
0x180046219  mov     rdx, [rdi+8]; Src
0x18004621d  test    rdx, rdx
0x180046220  jz      short loc_180046249
0x180046222  cmp     dword ptr [rdi+1Ch], 0
0x180046226  jbe     short loc_180046234
0x180046228  mov     r8d, [rdi+1Ch]; Size
0x18004622c  mov     rcx, rax; void *
0x18004622f  call    memcpy_0
0x180046234  mov     rcx, [rdi+8]; hMem
0x180046238  test    rcx, rcx
0x18004623b  jz      short loc_180046249
0x18004623d  call    cs:__imp_LocalFree
0x180046244  nop     dword ptr [rax+rax+00h]
0x180046249  mov     eax, [rdi+1Ch]
0x18004624c  add     rax, rsi
0x18004624f  mov     [rdi+18h], ebx
0x180046252  mov     [rdi+10h], rax
0x180046256  xor     eax, eax
0x180046258  mov     [rdi+8], rsi
0x18004625c  jmp     short loc_1800461E6
```

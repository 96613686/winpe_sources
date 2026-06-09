# SxCopyString(ushort const *,ushort * *)

- ea: `0x140006c40`
- end: `0x140006cc2`
- name: `?SxCopyString@@YAJPEBGPEAPEAG@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x140006c40`
- `0x140010942`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140006c7d`
- `ole32!CoTaskMemAlloc` at `0x140006c7d`
- `ole32!CoTaskMemFree` at `0x140006caf`
- `ole32!CoTaskMemFree` at `0x140006caf`

## pseudocode

```c
__int64 __fastcall SxCopyString(const unsigned __int16 *Src, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  __int64 v5; // rax
  SIZE_T v6; // rbp
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx

  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_10;
  }
  *a2 = 0;
  v4 = 0;
  if ( !Src )
    goto LABEL_8;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  v6 = 2 * v5 + 2;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
  v4 = v7;
  if ( v7 )
  {
    memcpy_0(v7, Src, v6);
LABEL_8:
    v8 = 0;
    *a2 = v4;
    goto LABEL_10;
  }
  v8 = -2147024882;
LABEL_10:
  CoTaskMemFree(0);
  return v8;
}

```

## disassembly

```asm
0x140006c40  push    rbx
0x140006c42  push    rbp
0x140006c43  push    rsi
0x140006c44  push    rdi
0x140006c45  push    r14
0x140006c47  sub     rsp, 20h
0x140006c4b  xor     r14d, r14d
0x140006c4e  mov     rsi, rdx
0x140006c51  mov     rbx, rcx
0x140006c54  test    rdx, rdx
0x140006c57  jz      short loc_140006CA8
0x140006c59  mov     [rdx], r14
0x140006c5c  mov     edi, r14d
0x140006c5f  test    rcx, rcx
0x140006c62  jz      short loc_140006CA0
0x140006c64  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006c68  inc     rax
0x140006c6b  cmp     [rcx+rax*2], r14w
0x140006c70  jnz     short loc_140006C68
0x140006c72  lea     rbp, ds:2[rax*2]
0x140006c7a  mov     rcx, rbp; cb
0x140006c7d  call    cs:__imp_CoTaskMemAlloc
0x140006c83  mov     rdi, rax
0x140006c86  test    rax, rax
0x140006c89  jnz     short loc_140006C92
0x140006c8b  mov     ebx, 8007000Eh
0x140006c90  jmp     short loc_140006CAD
0x140006c92  mov     r8, rbp; Size
0x140006c95  mov     rdx, rbx; Src
0x140006c98  mov     rcx, rax; void *
0x140006c9b  call    memcpy_0
0x140006ca0  mov     ebx, r14d
0x140006ca3  mov     [rsi], rdi
0x140006ca6  jmp     short loc_140006CAD
0x140006ca8  mov     ebx, 80070057h
0x140006cad  xor     ecx, ecx; pv
0x140006caf  call    cs:__imp_CoTaskMemFree
0x140006cb5  mov     eax, ebx
0x140006cb7  add     rsp, 20h
0x140006cbb  pop     r14
0x140006cbd  pop     rdi
0x140006cbe  pop     rsi
0x140006cbf  pop     rbp
0x140006cc0  pop     rbx
0x140006cc1  retn
```

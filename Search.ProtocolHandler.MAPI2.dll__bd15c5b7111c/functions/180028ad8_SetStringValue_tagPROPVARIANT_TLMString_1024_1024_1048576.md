# SetStringValue(tagPROPVARIANT * *,TLMString<1024,1024,1048576> &)

- ea: `0x180028ad8`
- end: `0x180028b8d`
- name: `?SetStringValue@@YAJPEAPEAUtagPROPVARIANT@@AEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026f00`

## callees

- `0x180028ad8`
- `0x18003a0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028b02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028b02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028b43`

## pseudocode

```c
__int64 __fastcall SetStringValue(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _WORD *v7; // rsi
  __int64 v8; // rax
  SIZE_T v9; // rbp
  void *v10; // rax

  *a1 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
    return 0;
  v5 = CoTaskMemAlloc(0x18u);
  *a1 = v5;
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  v7 = *(_WORD **)(a2 + 8);
  if ( !v7 )
  {
    v4 = -2147024809;
LABEL_14:
    *(_OWORD *)v6 = 0;
    v6[2] = 0;
    return v4;
  }
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = 2 * v8 + 2;
  v10 = CoTaskMemAlloc(v9);
  v6[1] = v10;
  if ( !v10 )
  {
    v4 = -2147024882;
    goto LABEL_14;
  }
  v4 = 0;
  if ( v9 )
    memcpy_0(v10, v7, v9);
  *(_WORD *)v6 = 31;
  return v4;
}

```

## disassembly

```asm
0x180028ad8  push    rbx
0x180028ada  push    rbp
0x180028adb  push    rsi
0x180028adc  push    rdi
0x180028add  push    r14
0x180028adf  sub     rsp, 20h
0x180028ae3  xor     r14d, r14d
0x180028ae6  mov     rsi, rdx
0x180028ae9  mov     [rcx], r14
0x180028aec  mov     rbx, rcx
0x180028aef  cmp     [rdx+14h], r14d
0x180028af3  jnz     short loc_180028AFD
0x180028af5  mov     ebx, r14d
0x180028af8  jmp     loc_180028B80
0x180028afd  mov     ecx, 18h; cb
0x180028b02  call    cs:__imp_CoTaskMemAlloc
0x180028b08  mov     [rbx], rax
0x180028b0b  mov     rdi, rax
0x180028b0e  test    rax, rax
0x180028b11  jnz     short loc_180028B1A
0x180028b13  mov     ebx, 8007000Eh
0x180028b18  jmp     short loc_180028B80
0x180028b1a  mov     rsi, [rsi+8]
0x180028b1e  test    rsi, rsi
0x180028b21  jnz     short loc_180028B2A
0x180028b23  mov     ebx, 80070057h
0x180028b28  jmp     short loc_180028B74
0x180028b2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028b2e  inc     rax
0x180028b31  cmp     [rsi+rax*2], r14w
0x180028b36  jnz     short loc_180028B2E
0x180028b38  lea     rbp, ds:2[rax*2]
0x180028b40  mov     rcx, rbp; cb
0x180028b43  call    cs:__imp_CoTaskMemAlloc
0x180028b49  mov     [rdi+8], rax
0x180028b4d  test    rax, rax
0x180028b50  jz      short loc_180028B6F
0x180028b52  mov     ebx, r14d
0x180028b55  test    rbp, rbp
0x180028b58  jz      short loc_180028B68
0x180028b5a  mov     r8, rbp; Size
0x180028b5d  mov     rdx, rsi; Src
0x180028b60  mov     rcx, rax; void *
0x180028b63  call    memcpy_0
0x180028b68  mov     word ptr [rdi], 1Fh
0x180028b6d  jmp     short loc_180028B80
0x180028b6f  mov     ebx, 8007000Eh
0x180028b74  xorps   xmm0, xmm0
0x180028b77  xor     eax, eax
0x180028b79  movups  xmmword ptr [rdi], xmm0
0x180028b7c  mov     [rdi+10h], rax
0x180028b80  mov     eax, ebx
0x180028b82  add     rsp, 20h
0x180028b86  pop     r14
0x180028b88  pop     rdi
0x180028b89  pop     rsi
0x180028b8a  pop     rbp
0x180028b8b  pop     rbx
0x180028b8c  retn
```

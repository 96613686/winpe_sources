# BCopyFont

- ea: `0x18001d208`
- end: `0x18001d424`
- name: `BCopyFont`
- size: `540`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001107c`

## callees

- `0x180002938`
- `0x18001d208`
- `0x18005f010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001d367`
- `KERNEL32!LocalFree` at `0x18001d367`
- `KERNEL32!LocalAlloc` at `0x18001d309`
- `KERNEL32!LocalAlloc` at `0x18001d404`
- `KERNEL32!LocalAlloc` at `0x18001d309`
- `KERNEL32!LocalAlloc` at `0x18001d404`

## pseudocode

```c
_BOOL8 __fastcall BCopyFont(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // rax
  float v9; // xmm0_4
  __int64 v10; // rax
  bool v11; // zf
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  __int64 *v18; // r14
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rdx
  __int16 v22; // ax
  __int64 v23; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rsi
  int v29; // [rsp+20h] [rbp-39h] BYREF
  _QWORD *v30; // [rsp+28h] [rbp-31h]
  __int64 v31; // [rsp+30h] [rbp-29h]
  __int64 v32; // [rsp+38h] [rbp-21h]
  int v33; // [rsp+44h] [rbp-15h]
  const char *v34; // [rsp+48h] [rbp-11h]
  int v35; // [rsp+70h] [rbp+17h]
  int v36; // [rsp+74h] [rbp+1Bh]
  const char *v37; // [rsp+78h] [rbp+1Fh]
  __int64 v38; // [rsp+80h] [rbp+27h]

  memset_0(&v29, 0, 0x70u);
  if ( !a2 || !a3 )
    return 0;
  if ( a4 == 7 )
  {
    v33 = 1;
    v34 = "G00GFFEncoding";
  }
  v32 = a3;
  v31 = a3 + 10;
  v35 = 2;
  v37 = ".36397023";
  v8 = *(_QWORD *)(a1 + 752);
  if ( !v8 || (v9 = *(float *)(v8 + 72), v36 = 3, v9 != 0.0) )
    v36 = 2;
  v10 = *(_QWORD *)(a1 + 3744);
  if ( *(_DWORD *)v10 != 1 || (v11 = (*(_BYTE *)(v10 + 4) & 4) == 0, v38 = *(_QWORD *)(a1 + 3744), v11) )
    v38 = 0;
  v12 = a4 - 2;
  if ( !v12 )
  {
    v28 = *(__int64 **)(a2 + 144);
    v20 = LocalAlloc(0x40u, 0x38u);
    if ( !v20 )
      return 0;
    v23 = *v28;
    goto LABEL_20;
  }
  v13 = v12 - 1;
  if ( !v13 || (v14 = v13 - 1) == 0 || (v15 = v14 - 1) == 0 || (v16 = v15 - 1) == 0 )
  {
LABEL_27:
    v26 = *(_QWORD *)(a2 + 144);
    if ( v26 )
      v27 = (*(__int64 (__fastcall **)(_QWORD, int *))(v26 + 200))(*(_QWORD *)(a2 + 144), &v29);
    else
      v27 = 0;
    *(_QWORD *)(a3 + 144) = v27;
    return v27 != 0;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v29 = (*(_WORD *)(a3 + 8) != 0) + 13;
    goto LABEL_27;
  }
  if ( v17 != 3 )
    return 0;
  v18 = *(__int64 **)(a2 + 144);
  v19 = LocalAlloc(0x40u, 0x18u);
  v20 = v19;
  if ( !v19 )
    return 0;
  v21 = *((unsigned int *)v18 + 4) + *(_QWORD *)(*(_QWORD *)(a2 + 152) + 400LL);
  v18[1] = v21;
  v19[1] = v21;
  *((_DWORD *)v19 + 4) = *((_DWORD *)v18 + 4);
  v22 = *(_WORD *)(a3 + 8);
  v30 = v20 + 1;
  v29 = (v22 != 0) + 5;
  v23 = *v18;
LABEL_20:
  if ( !v23 )
  {
    *v20 = 0;
LABEL_22:
    LocalFree(v20);
    return 0;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(v23 + 200))(v23, &v29);
  *v20 = v25;
  if ( !v25 )
    goto LABEL_22;
  *(_QWORD *)(a3 + 144) = v20;
  return 1;
}

```

## disassembly

```asm
0x18001d208  push    rbp
0x18001d20a  push    rbx
0x18001d20b  push    rsi
0x18001d20c  push    rdi
0x18001d20d  push    r14
0x18001d20f  lea     rbp, [rsp-37h]
0x18001d214  sub     rsp, 90h
0x18001d21b  mov     rsi, rdx
0x18001d21e  mov     rdi, r8
0x18001d221  xor     edx, edx; Val
0x18001d223  mov     r14, rcx
0x18001d226  lea     rcx, [rbp+57h+var_90]; void *
0x18001d22a  mov     ebx, r9d
0x18001d22d  lea     r8d, [rdx+70h]; Size
0x18001d231  call    memset_0
0x18001d236  test    rsi, rsi
0x18001d239  jz      loc_18001D373
0x18001d23f  test    rdi, rdi
0x18001d242  jz      loc_18001D373
0x18001d248  cmp     ebx, 7
0x18001d24b  jnz     short loc_18001D25F
0x18001d24d  lea     rax, aG00gffencoding; "G00GFFEncoding"
0x18001d254  mov     [rbp+57h+var_6C], 1
0x18001d25b  mov     [rbp+57h+var_68], rax
0x18001d25f  lea     rax, [rdi+0Ah]
0x18001d263  mov     [rbp+57h+var_78], rdi
0x18001d267  mov     [rbp+57h+var_80], rax
0x18001d26b  mov     ecx, 2
0x18001d270  lea     rax, a36397023; ".36397023"
0x18001d277  mov     [rbp+57h+var_40], ecx
0x18001d27a  mov     [rbp+57h+var_38], rax
0x18001d27e  mov     rax, [r14+2F0h]
0x18001d285  test    rax, rax
0x18001d288  jz      short loc_18001D2A1
0x18001d28a  movss   xmm0, dword ptr [rax+48h]
0x18001d28f  ucomiss xmm0, cs:__real@00000000
0x18001d296  jp      short loc_18001D2A1
0x18001d298  mov     [rbp+57h+var_3C], 3
0x18001d29f  jz      short loc_18001D2A4
0x18001d2a1  mov     [rbp+57h+var_3C], ecx
0x18001d2a4  mov     rax, [r14+0EA0h]
0x18001d2ab  cmp     dword ptr [rax], 1
0x18001d2ae  jnz     short loc_18001D2BA
0x18001d2b0  test    byte ptr [rax+4], 4
0x18001d2b4  mov     [rbp+57h+var_30], rax
0x18001d2b8  jnz     short loc_18001D2C2
0x18001d2ba  mov     [rbp+57h+var_30], 0
0x18001d2c2  sub     ebx, ecx
0x18001d2c4  jz      loc_18001D3F5
0x18001d2ca  sub     ebx, 1
0x18001d2cd  jz      loc_18001D3BE
0x18001d2d3  sub     ebx, 1
0x18001d2d6  jz      loc_18001D3BE
0x18001d2dc  sub     ebx, 1
0x18001d2df  jz      loc_18001D3BE
0x18001d2e5  sub     ebx, 1
0x18001d2e8  jz      loc_18001D3BE
0x18001d2ee  sub     ebx, 1
0x18001d2f1  jz      loc_18001D3AD
0x18001d2f7  cmp     ebx, 3
0x18001d2fa  jnz     short loc_18001D373
0x18001d2fc  mov     r14, [rsi+90h]
0x18001d303  lea     edx, [rbx+15h]; uBytes
0x18001d306  lea     ecx, [rbx+3Dh]; uFlags
0x18001d309  call    cs:__imp_LocalAlloc
0x18001d310  nop     dword ptr [rax+rax+00h]
0x18001d315  mov     rbx, rax
0x18001d318  test    rax, rax
0x18001d31b  jz      short loc_18001D373
0x18001d31d  mov     rax, [rsi+98h]
0x18001d324  mov     ecx, [r14+10h]
0x18001d328  mov     rdx, [rax+190h]
0x18001d32f  add     rdx, rcx
0x18001d332  lea     rcx, [rbx+8]
0x18001d336  mov     [r14+8], rdx
0x18001d33a  mov     [rcx], rdx
0x18001d33d  mov     eax, [r14+10h]
0x18001d341  mov     [rbx+10h], eax
0x18001d344  movzx   eax, word ptr [rdi+8]
0x18001d348  mov     [rbp+57h+var_88], rcx
0x18001d34c  neg     ax
0x18001d34f  sbb     ecx, ecx
0x18001d351  neg     ecx
0x18001d353  add     ecx, 5
0x18001d356  mov     [rbp+57h+var_90], ecx
0x18001d359  mov     rax, [r14]
0x18001d35c  test    rax, rax
0x18001d35f  jnz     short loc_18001D384
0x18001d361  mov     [rbx], rax
0x18001d364  mov     rcx, rbx; hMem
0x18001d367  call    cs:__imp_LocalFree
0x18001d36e  nop     dword ptr [rax+rax+00h]
0x18001d373  xor     eax, eax
0x18001d375  add     rsp, 90h
0x18001d37c  pop     r14
0x18001d37e  pop     rdi
0x18001d37f  pop     rsi
0x18001d380  pop     rbx
0x18001d381  pop     rbp
0x18001d382  retn
0x18001d384  mov     rcx, rax
0x18001d387  lea     rdx, [rbp+57h+var_90]
0x18001d38b  mov     rax, [rax+0C8h]
0x18001d392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d397  mov     [rbx], rax
0x18001d39a  test    rax, rax
0x18001d39d  jz      short loc_18001D364
0x18001d39f  mov     [rdi+90h], rbx
0x18001d3a6  mov     eax, 1
0x18001d3ab  jmp     short loc_18001D375
0x18001d3ad  movzx   eax, word ptr [rdi+8]
0x18001d3b1  neg     ax
0x18001d3b4  sbb     ecx, ecx
0x18001d3b6  neg     ecx
0x18001d3b8  add     ecx, 0Dh
0x18001d3bb  mov     [rbp+57h+var_90], ecx
0x18001d3be  mov     rax, [rsi+90h]
0x18001d3c5  test    rax, rax
0x18001d3c8  jnz     short loc_18001D3CE
0x18001d3ca  xor     ecx, ecx
0x18001d3cc  jmp     short loc_18001D3E4
0x18001d3ce  mov     rcx, rax
0x18001d3d1  lea     rdx, [rbp+57h+var_90]
0x18001d3d5  mov     rax, [rax+0C8h]
0x18001d3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3e1  mov     rcx, rax
0x18001d3e4  xor     eax, eax
0x18001d3e6  mov     [rdi+90h], rcx
0x18001d3ed  test    rcx, rcx
0x18001d3f0  setnz   al
0x18001d3f3  jmp     short loc_18001D375
0x18001d3f5  mov     rsi, [rsi+90h]
0x18001d3fc  mov     edx, 38h ; '8'; uBytes
0x18001d401  lea     ecx, [rdx+8]; uFlags
0x18001d404  call    cs:__imp_LocalAlloc
0x18001d40b  nop     dword ptr [rax+rax+00h]
0x18001d410  mov     rbx, rax
0x18001d413  test    rax, rax
0x18001d416  jz      loc_18001D373
0x18001d41c  mov     rax, [rsi]
0x18001d41f  jmp     loc_18001D35C
```

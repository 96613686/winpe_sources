# BCopyFont

- ea: `0x18001c7f0`
- end: `0x18001c9f9`
- name: `BCopyFont`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010b48`

## callees

- `0x1800028d8`
- `0x18001c7f0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001c949`
- `KERNEL32!LocalFree` at `0x18001c949`
- `KERNEL32!LocalAlloc` at `0x18001c8f1`
- `KERNEL32!LocalAlloc` at `0x18001c9df`
- `KERNEL32!LocalAlloc` at `0x18001c8f1`
- `KERNEL32!LocalAlloc` at `0x18001c9df`

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
0x18001c7f0  push    rbp
0x18001c7f2  push    rbx
0x18001c7f3  push    rsi
0x18001c7f4  push    rdi
0x18001c7f5  push    r14
0x18001c7f7  lea     rbp, [rsp-37h]
0x18001c7fc  sub     rsp, 90h
0x18001c803  mov     rsi, rdx
0x18001c806  mov     rdi, r8
0x18001c809  xor     edx, edx; Val
0x18001c80b  mov     r14, rcx
0x18001c80e  lea     rcx, [rbp+57h+var_90]; void *
0x18001c812  mov     ebx, r9d
0x18001c815  lea     r8d, [rdx+70h]; Size
0x18001c819  call    memset_0
0x18001c81e  test    rsi, rsi
0x18001c821  jz      loc_18001C94F
0x18001c827  test    rdi, rdi
0x18001c82a  jz      loc_18001C94F
0x18001c830  cmp     ebx, 7
0x18001c833  jnz     short loc_18001C847
0x18001c835  lea     rax, aG00gffencoding; "G00GFFEncoding"
0x18001c83c  mov     [rbp+57h+var_6C], 1
0x18001c843  mov     [rbp+57h+var_68], rax
0x18001c847  lea     rax, [rdi+0Ah]
0x18001c84b  mov     [rbp+57h+var_78], rdi
0x18001c84f  mov     [rbp+57h+var_80], rax
0x18001c853  mov     ecx, 2
0x18001c858  lea     rax, a36397023; ".36397023"
0x18001c85f  mov     [rbp+57h+var_40], ecx
0x18001c862  mov     [rbp+57h+var_38], rax
0x18001c866  mov     rax, [r14+2F0h]
0x18001c86d  test    rax, rax
0x18001c870  jz      short loc_18001C889
0x18001c872  movss   xmm0, dword ptr [rax+48h]
0x18001c877  ucomiss xmm0, cs:__real@00000000
0x18001c87e  jp      short loc_18001C889
0x18001c880  mov     [rbp+57h+var_3C], 3
0x18001c887  jz      short loc_18001C88C
0x18001c889  mov     [rbp+57h+var_3C], ecx
0x18001c88c  mov     rax, [r14+0EA0h]
0x18001c893  cmp     dword ptr [rax], 1
0x18001c896  jnz     short loc_18001C8A2
0x18001c898  test    byte ptr [rax+4], 4
0x18001c89c  mov     [rbp+57h+var_30], rax
0x18001c8a0  jnz     short loc_18001C8AA
0x18001c8a2  mov     [rbp+57h+var_30], 0
0x18001c8aa  sub     ebx, ecx
0x18001c8ac  jz      loc_18001C9D0
0x18001c8b2  sub     ebx, 1
0x18001c8b5  jz      loc_18001C999
0x18001c8bb  sub     ebx, 1
0x18001c8be  jz      loc_18001C999
0x18001c8c4  sub     ebx, 1
0x18001c8c7  jz      loc_18001C999
0x18001c8cd  sub     ebx, 1
0x18001c8d0  jz      loc_18001C999
0x18001c8d6  sub     ebx, 1
0x18001c8d9  jz      loc_18001C988
0x18001c8df  cmp     ebx, 3
0x18001c8e2  jnz     short loc_18001C94F
0x18001c8e4  mov     r14, [rsi+90h]
0x18001c8eb  lea     edx, [rbx+15h]; uBytes
0x18001c8ee  lea     ecx, [rbx+3Dh]; uFlags
0x18001c8f1  call    cs:__imp_LocalAlloc
0x18001c8f7  mov     rbx, rax
0x18001c8fa  test    rax, rax
0x18001c8fd  jz      short loc_18001C94F
0x18001c8ff  mov     rax, [rsi+98h]
0x18001c906  mov     ecx, [r14+10h]
0x18001c90a  mov     rdx, [rax+190h]
0x18001c911  add     rdx, rcx
0x18001c914  lea     rcx, [rbx+8]
0x18001c918  mov     [r14+8], rdx
0x18001c91c  mov     [rcx], rdx
0x18001c91f  mov     eax, [r14+10h]
0x18001c923  mov     [rbx+10h], eax
0x18001c926  movzx   eax, word ptr [rdi+8]
0x18001c92a  mov     [rbp+57h+var_88], rcx
0x18001c92e  neg     ax
0x18001c931  sbb     ecx, ecx
0x18001c933  neg     ecx
0x18001c935  add     ecx, 5
0x18001c938  mov     [rbp+57h+var_90], ecx
0x18001c93b  mov     rax, [r14]
0x18001c93e  test    rax, rax
0x18001c941  jnz     short loc_18001C95F
0x18001c943  mov     [rbx], rax
0x18001c946  mov     rcx, rbx; hMem
0x18001c949  call    cs:__imp_LocalFree
0x18001c94f  xor     eax, eax
0x18001c951  add     rsp, 90h
0x18001c958  pop     r14
0x18001c95a  pop     rdi
0x18001c95b  pop     rsi
0x18001c95c  pop     rbx
0x18001c95d  pop     rbp
0x18001c95e  retn
0x18001c95f  mov     rcx, rax
0x18001c962  lea     rdx, [rbp+57h+var_90]
0x18001c966  mov     rax, [rax+0C8h]
0x18001c96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c972  mov     [rbx], rax
0x18001c975  test    rax, rax
0x18001c978  jz      short loc_18001C946
0x18001c97a  mov     [rdi+90h], rbx
0x18001c981  mov     eax, 1
0x18001c986  jmp     short loc_18001C951
0x18001c988  movzx   eax, word ptr [rdi+8]
0x18001c98c  neg     ax
0x18001c98f  sbb     ecx, ecx
0x18001c991  neg     ecx
0x18001c993  add     ecx, 0Dh
0x18001c996  mov     [rbp+57h+var_90], ecx
0x18001c999  mov     rax, [rsi+90h]
0x18001c9a0  test    rax, rax
0x18001c9a3  jnz     short loc_18001C9A9
0x18001c9a5  xor     ecx, ecx
0x18001c9a7  jmp     short loc_18001C9BF
0x18001c9a9  mov     rcx, rax
0x18001c9ac  lea     rdx, [rbp+57h+var_90]
0x18001c9b0  mov     rax, [rax+0C8h]
0x18001c9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9bc  mov     rcx, rax
0x18001c9bf  xor     eax, eax
0x18001c9c1  mov     [rdi+90h], rcx
0x18001c9c8  test    rcx, rcx
0x18001c9cb  setnz   al
0x18001c9ce  jmp     short loc_18001C951
0x18001c9d0  mov     rsi, [rsi+90h]
0x18001c9d7  mov     edx, 38h ; '8'; uBytes
0x18001c9dc  lea     ecx, [rdx+8]; uFlags
0x18001c9df  call    cs:__imp_LocalAlloc
0x18001c9e5  mov     rbx, rax
0x18001c9e8  test    rax, rax
0x18001c9eb  jz      loc_18001C94F
0x18001c9f1  mov     rax, [rsi]
0x18001c9f4  jmp     loc_18001C93E
```

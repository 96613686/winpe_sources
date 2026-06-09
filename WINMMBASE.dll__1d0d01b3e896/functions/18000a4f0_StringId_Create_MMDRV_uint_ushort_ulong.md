# StringId_Create(_MMDRV *,uint,ushort * *,ulong *)

- ea: `0x18000a4f0`
- end: `0x18000a6f5`
- name: `?StringId_Create@@YAIPEAU_MMDRV@@IPEAPEAGPEAK@Z`
- size: `517`
- prototype: `unsigned int __fastcall(struct _MMDRV *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180007dd0`
- `0x180009a8c`
- `0x18000a0d8`
- `0x18000a27c`
- `0x18000b584`
- `0x18000f638`

## callees

- `0x18000a4f0`
- `0x18000a6fc`
- `0x18000be70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a5d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a5d9`

## pseudocode

```c
__int64 __fastcall StringId_Create(struct _MMDRV *a1, int a2, unsigned __int16 **a3, unsigned int *a4)
{
  const wchar_t *v4; // rbx
  struct _MMDRV *v6; // r11
  const wchar_t *v7; // rax
  __int64 v8; // r10
  int v9; // ebp
  __int64 v10; // rdx
  size_t v11; // r10
  char *v12; // r12
  __int64 v13; // rcx
  _WORD *i; // rax
  unsigned __int64 v15; // r15
  __int64 result; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  bool v19; // sf
  int v20; // eax
  size_t pcchLength; // [rsp+80h] [rbp+8h] BYREF
  int v22; // [rsp+88h] [rbp+10h]
  unsigned __int16 **v23; // [rsp+90h] [rbp+18h]

  v23 = a3;
  v22 = a2;
  v4 = (const wchar_t *)*((_QWORD *)a1 + 12);
  pcchLength = 0;
  v6 = a1;
  if ( v4 )
  {
    v7 = v4;
    v8 = 0x7FFFFFFF;
    while ( *v7 )
    {
      ++v7;
      if ( !--v8 )
        return 7;
    }
    v9 = 1;
    v10 = 0x7FFFFFFF - v8 + 18;
    v11 = 0;
  }
  else
  {
    v4 = (const wchar_t *)((char *)a1 + 160);
    if ( a1 == (struct _MMDRV *)-160LL || StringLengthWorkerW((STRSAFE_PCNZWCH)a1 + 80, 0x7FFFFFFFu, &pcchLength) < 0 )
      return 7;
    v9 = v11;
    a3 = v23;
    v10 = pcchLength + 9;
  }
  v12 = (char *)v6 + 40;
  if ( v6 == (struct _MMDRV *)-40LL )
    return 7;
  v13 = 0x7FFFFFFF;
  for ( i = (_WORD *)((char *)v6 + 40); *i != (_WORD)v11; ++i )
  {
    if ( !--v13 )
    {
      pcchLength = v11;
      return 7;
    }
  }
  pcchLength = 0x7FFFFFFF - v13;
  v15 = v10 + 0x7FFFFFFF - v13 + 11;
  if ( 2 * v15 > 0xFFFFFFFF )
    return 7;
  if ( a3 )
  {
    v17 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2 * v15);
    LODWORD(v11) = 0;
    v18 = v17;
    if ( v17 )
    {
      if ( v9 )
      {
        if ( v9 != 1 )
          goto LABEL_21;
        if ( !v4 || (v19 = StringLengthWorkerW(v4, 0x7FFFFFFFu, &pcchLength) < 0, v20 = pcchLength, v19) )
          v20 = v11;
        StringCchPrintfW(v18, v15, L"%08X:%08X:%s:%s:%08X", 1, v20, v4, v12, v22);
      }
      else
      {
        StringCchPrintfW(v17, v15, L"%08X:%s:%s:%08X", 0, v4, v12, v22);
      }
      LODWORD(v11) = 0;
LABEL_21:
      *v23 = v18;
      goto LABEL_22;
    }
    return 7;
  }
LABEL_22:
  result = (unsigned int)v11;
  if ( a4 )
    *a4 = 2 * v15;
  return result;
}

```

## disassembly

```asm
0x18000a4f0  mov     rax, rsp
0x18000a4f3  mov     [rax+20h], rbx
0x18000a4f7  mov     [rax+18h], r8
0x18000a4fb  mov     [rax+10h], edx
0x18000a4fe  push    rbp
0x18000a4ff  push    rsi
0x18000a500  push    rdi
0x18000a501  push    r12
0x18000a503  push    r13
0x18000a505  push    r14
0x18000a507  push    r15
0x18000a509  sub     rsp, 40h
0x18000a50d  mov     rbx, [rcx+60h]
0x18000a511  xor     r10d, r10d
0x18000a514  mov     [rax+8], r10
0x18000a518  mov     r13, r9
0x18000a51b  mov     r11, rcx
0x18000a51e  test    rbx, rbx
0x18000a521  jz      loc_18000A6A2
0x18000a527  mov     edi, 7FFFFFFFh
0x18000a52c  mov     rax, rbx
0x18000a52f  mov     r10d, edi
0x18000a532  xor     ecx, ecx
0x18000a534  cmp     [rax], cx
0x18000a537  jz      short loc_18000A545
0x18000a539  add     rax, 2
0x18000a53d  sub     r10, 1
0x18000a541  jnz     short loc_18000A534
0x18000a543  jmp     short loc_18000A59B
0x18000a545  mov     rdx, rdi
0x18000a548  mov     ebp, 1
0x18000a54d  sub     rdx, r10
0x18000a550  add     rdx, 12h
0x18000a554  xor     r10d, r10d
0x18000a557  lea     r12, [r11+28h]
0x18000a55b  test    r12, r12
0x18000a55e  jz      short loc_18000A59B
0x18000a560  mov     rcx, rdi
0x18000a563  mov     rax, r12
0x18000a566  cmp     [rax], r10w
0x18000a56a  jz      short loc_18000A5B8
0x18000a56c  add     rax, 2
0x18000a570  sub     rcx, 1
0x18000a574  jnz     short loc_18000A566
0x18000a576  mov     rax, r10
0x18000a579  mov     [rsp+78h+pcchLength], rax
0x18000a581  test    rcx, rcx
0x18000a584  jz      short loc_18000A59B
0x18000a586  lea     r15, [rax+0Bh]
0x18000a58a  mov     eax, 0FFFFFFFFh
0x18000a58f  add     r15, rdx
0x18000a592  lea     r14, [r15+r15]
0x18000a596  cmp     r14, rax
0x18000a599  jbe     short loc_18000A5C8
0x18000a59b  mov     eax, 7
0x18000a5a0  mov     rbx, [rsp+78h+arg_18]
0x18000a5a8  add     rsp, 40h
0x18000a5ac  pop     r15
0x18000a5ae  pop     r14
0x18000a5b0  pop     r13
0x18000a5b2  pop     r12
0x18000a5b4  pop     rdi
0x18000a5b5  pop     rsi
0x18000a5b6  pop     rbp
0x18000a5b7  retn
0x18000a5b8  mov     rax, rdi
0x18000a5bb  sub     rax, rcx
0x18000a5be  mov     [rsp+78h+pcchLength], rax
0x18000a5c6  jmp     short loc_18000A586
0x18000a5c8  test    r8, r8
0x18000a5cb  jz      short loc_18000A626
0x18000a5cd  mov     rcx, cs:hHeap; hHeap
0x18000a5d4  mov     r8, r14; dwBytes
0x18000a5d7  xor     edx, edx; dwFlags
0x18000a5d9  call    cs:__imp_HeapAlloc
0x18000a5df  xor     r10d, r10d
0x18000a5e2  mov     rsi, rax
0x18000a5e5  test    rax, rax
0x18000a5e8  jz      short loc_18000A59B
0x18000a5ea  test    ebp, ebp
0x18000a5ec  jnz     short loc_18000A63B
0x18000a5ee  mov     ecx, [rsp+78h+arg_8]
0x18000a5f5  lea     r8, a08xSS08x; "%08X:%s:%s:%08X"
0x18000a5fc  mov     dword ptr [rsp+78h+var_48], ecx
0x18000a600  xor     r9d, r9d
0x18000a603  mov     [rsp+78h+var_50], r12
0x18000a608  mov     rcx, rax; unsigned __int16 *
0x18000a60b  mov     rdx, r15; unsigned __int64
0x18000a60e  mov     [rsp+78h+var_58], rbx
0x18000a613  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a618  xor     r10d, r10d
0x18000a61b  mov     rax, [rsp+78h+arg_10]
0x18000a623  mov     [rax], rsi
0x18000a626  mov     eax, r10d
0x18000a629  test    r13, r13
0x18000a62c  jz      loc_18000A5A0
0x18000a632  mov     [r13+0], r14d
0x18000a636  jmp     loc_18000A5A0
0x18000a63b  cmp     ebp, 1
0x18000a63e  jnz     short loc_18000A61B
0x18000a640  test    rbx, rbx
0x18000a643  jz      loc_18000A6ED
0x18000a649  lea     r8, [rsp+78h+pcchLength]; pcchLength
0x18000a651  mov     rdx, rdi; cchMax
0x18000a654  mov     rcx, rbx; psz
0x18000a657  call    StringLengthWorkerW
0x18000a65c  test    eax, eax
0x18000a65e  mov     rax, [rsp+78h+pcchLength]
0x18000a666  js      loc_18000A6ED
0x18000a66c  mov     ecx, [rsp+78h+arg_8]
0x18000a673  lea     r8, a08x08xSS08x; "%08X:%08X:%s:%s:%08X"
0x18000a67a  mov     [rsp+78h+var_40], ecx
0x18000a67e  mov     r9d, 1
0x18000a684  mov     [rsp+78h+var_48], r12
0x18000a689  mov     rdx, r15; unsigned __int64
0x18000a68c  mov     [rsp+78h+var_50], rbx
0x18000a691  mov     rcx, rsi; unsigned __int16 *
0x18000a694  mov     dword ptr [rsp+78h+var_58], eax
0x18000a698  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a69d  jmp     loc_18000A618
0x18000a6a2  lea     rbx, [rcx+0A0h]
0x18000a6a9  test    rbx, rbx
0x18000a6ac  jz      loc_18000A59B
0x18000a6b2  mov     edi, 7FFFFFFFh
0x18000a6b7  lea     r8, [rsp+78h+pcchLength]; pcchLength
0x18000a6bf  mov     edx, edi; cchMax
0x18000a6c1  mov     rcx, rbx; psz
0x18000a6c4  call    StringLengthWorkerW
0x18000a6c9  test    eax, eax
0x18000a6cb  js      loc_18000A59B
0x18000a6d1  mov     rdx, [rsp+78h+pcchLength]
0x18000a6d9  mov     ebp, r10d
0x18000a6dc  mov     r8, [rsp+78h+arg_10]
0x18000a6e4  add     rdx, 9
0x18000a6e8  jmp     loc_18000A557
0x18000a6ed  mov     rax, r10
0x18000a6f0  jmp     loc_18000A66C
```

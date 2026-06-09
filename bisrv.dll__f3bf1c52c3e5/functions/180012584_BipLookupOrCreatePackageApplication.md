# BipLookupOrCreatePackageApplication

- ea: `0x180012584`
- end: `0x180012862`
- name: `BipLookupOrCreatePackageApplication`
- size: `734`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800124a0`
- `0x180077324`
- `0x18007772c`
- `0x1800828f0`

## callees

- `0x180012584`
- `0x180012868`
- `0x180013190`
- `0x180014208`
- `0x18006a8d4`
- `0x18009467a`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800125b8`
- `msvcrt!wcsnlen` at `0x1800125ef`
- `msvcrt!wcsnlen` at `0x1800125b8`
- `msvcrt!wcsnlen` at `0x1800125ef`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800127b3`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800127b3`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012781`
- `ntdll!RtlAcquireSRWLockShared` at `0x180012781`
- `ntdll!RtlCompareUnicodeStrings` at `0x180012606`
- `ntdll!RtlCompareUnicodeStrings` at `0x180012606`
- `ntdll!RtlFreeHeap` at `0x180012803`
- `ntdll!RtlFreeHeap` at `0x180012803`
- `ntdll!RtlAllocateHeap` at `0x180012646`
- `ntdll!RtlAllocateHeap` at `0x180012703`
- `ntdll!RtlAllocateHeap` at `0x180012646`
- `ntdll!RtlAllocateHeap` at `0x180012703`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18001273a`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18001273a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001280e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001280e`

## pseudocode

```c
__int64 __fastcall BipLookupOrCreatePackageApplication(const wchar_t **a1, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // r15d
  const wchar_t *v7; // r14
  const wchar_t *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // r15d
  char *Heap; // rax
  char *v13; // rdi
  const wchar_t **v14; // rax
  PVOID v15; // rcx
  PVOID v16; // rax
  void *v17; // r14
  __int64 v18; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v20; // rbx
  unsigned int ActiveSessionId; // ebx
  int v22; // r12d
  __int64 v23; // r8
  const wchar_t *v24; // rax
  int v25; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+30h] [rbp-48h]
  char v27; // [rsp+88h] [rbp+10h] BYREF
  int v28; // [rsp+90h] [rbp+18h] BYREF
  int v29; // [rsp+98h] [rbp+20h]

  v27 = 0;
  if ( a3 )
    v6 = wcsnlen((const wchar_t *)a3, 0x41u);
  else
    v6 = 0;
  v7 = (const wchar_t *)(a2 + 6);
  v8 = (const wchar_t *)a2[6];
  if ( v8 == (const wchar_t *)(a2 + 6) )
    v8 = 0;
  while ( v8 )
  {
    if ( v8 == (const wchar_t *)-60LL )
      v9 = 0;
    else
      v9 = wcsnlen(v8 + 30, 0x41u);
    LOBYTE(v25) = 1;
    if ( !(unsigned int)RtlCompareUnicodeStrings(a3, v6, v8 + 30, v9, v25) )
    {
      v10 = 0;
      *a1 = v8;
      return v10;
    }
    v24 = *(const wchar_t **)v8;
    v8 = 0;
    if ( v24 != v7 )
      v8 = v24;
  }
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, 0xD8u);
  v13 = Heap;
  if ( !Heap )
  {
    v10 = -1073741801;
LABEL_26:
    *a1 = (const wchar_t *)v13;
    return v10;
  }
  memset_0(Heap, 0, 0xD8u);
  *((_QWORD *)v13 + 4) = v13 + 24;
  *((_QWORD *)v13 + 3) = v13 + 24;
  *((_QWORD *)v13 + 6) = v13 + 40;
  *((_QWORD *)v13 + 5) = v13 + 40;
  *(_OWORD *)(v13 + 60) = *(_OWORD *)a3;
  *(_OWORD *)(v13 + 76) = *(_OWORD *)(a3 + 16);
  *(_OWORD *)(v13 + 92) = *(_OWORD *)(a3 + 32);
  *(_OWORD *)(v13 + 108) = *(_OWORD *)(a3 + 48);
  *(_OWORD *)(v13 + 124) = *(_OWORD *)(a3 + 64);
  *(_OWORD *)(v13 + 140) = *(_OWORD *)(a3 + 80);
  *(_OWORD *)(v13 + 156) = *(_OWORD *)(a3 + 96);
  *(_OWORD *)(v13 + 172) = *(_OWORD *)(a3 + 112);
  *((_WORD *)v13 + 94) = *(_WORD *)(a3 + 128);
  *((_QWORD *)v13 + 2) = a2;
  v14 = (const wchar_t **)a2[7];
  if ( *v14 != v7 )
    __fastfail(3u);
  v15 = BipHeap;
  *(_QWORD *)v13 = v7;
  *((_QWORD *)v13 + 1) = v14;
  v10 = 0;
  *v14 = (const wchar_t *)v13;
  a2[7] = v13;
  v16 = RtlAllocateHeap(v15, 0, 0x1D0u);
  v17 = v16;
  if ( !v16 )
    goto LABEL_26;
  v18 = *((_QWORD *)v13 + 2) + 160LL;
  v28 = 464;
  PsmCreateKey(v18, v13 + 60, v16, &v28);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v29 = 1 << dword_1800C46D8;
  v20 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v26 = v20;
  if ( *(_DWORD *)(v20 + 4) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
  RtlAcquireSRWLockShared(BipSessionLock);
  *(_DWORD *)(v20 + 4) |= v29;
  ActiveSessionId = BipPackageGetActiveSessionId(a2);
  v22 = ~(1 << dword_1800C46D8);
  RtlReleaseSRWLockShared(BipSessionLock);
  *(_DWORD *)(v26 + 4) &= v22;
  if ( (int)BipSystemIntUiQueryState(a2[3], ActiveSessionId, v17, &v27) >= 0 )
  {
    LOBYTE(v23) = v27;
    BipPackageUpdateForegroundState(a2, a3, v23);
  }
  *a1 = (const wchar_t *)v13;
  RtlFreeHeap(BipHeap, 0, v17);
  return v10;
}

```

## disassembly

```asm
0x180012584  mov     rax, rsp
0x180012587  mov     [rax+8], rbx
0x18001258b  push    rbp
0x18001258c  push    rsi
0x18001258d  push    rdi
0x18001258e  push    r12
0x180012590  push    r13
0x180012592  push    r14
0x180012594  push    r15
0x180012596  sub     rsp, 40h
0x18001259a  mov     byte ptr [rax+10h], 0
0x18001259e  mov     rbp, r8
0x1800125a1  mov     r13, rdx
0x1800125a4  mov     rsi, rcx
0x1800125a7  test    r8, r8
0x1800125aa  jz      loc_18001282D
0x1800125b0  mov     edx, 41h ; 'A'; MaxCount
0x1800125b5  mov     rcx, r8; Source
0x1800125b8  call    cs:__imp_wcsnlen
0x1800125be  mov     r15, rax
0x1800125c1  xor     ecx, ecx
0x1800125c3  lea     r14, [r13+30h]
0x1800125c7  mov     rbx, [r14]
0x1800125ca  cmp     rbx, r14
0x1800125cd  cmovz   rbx, rcx
0x1800125d1  lea     r12d, [rcx+1]
0x1800125d5  test    rbx, rbx
0x1800125d8  jz      short loc_180012635
0x1800125da  lea     rdi, [rbx+3Ch]
0x1800125de  test    rdi, rdi
0x1800125e1  jz      loc_180012835
0x1800125e7  mov     edx, 41h ; 'A'; MaxCount
0x1800125ec  mov     rcx, rdi; Source
0x1800125ef  call    cs:__imp_wcsnlen
0x1800125f5  mov     r9d, eax
0x1800125f8  mov     r8, rdi
0x1800125fb  mov     edx, r15d
0x1800125fe  mov     rcx, rbp
0x180012601  mov     byte ptr [rsp+78h+var_58], r12b
0x180012606  call    cs:__imp_RtlCompareUnicodeStrings
0x18001260c  test    eax, eax
0x18001260e  jnz     loc_18001283C
0x180012614  xor     r15d, r15d
0x180012617  mov     [rsi], rbx
0x18001261a  mov     rbx, [rsp+78h+arg_0]
0x180012622  mov     eax, r15d
0x180012625  add     rsp, 40h
0x180012629  pop     r15
0x18001262b  pop     r14
0x18001262d  pop     r13
0x18001262f  pop     r12
0x180012631  pop     rdi
0x180012632  pop     rsi
0x180012633  pop     rbp
0x180012634  retn
0x180012635  mov     rcx, cs:BipHeap; HeapHandle
0x18001263c  mov     ebx, 0D8h
0x180012641  mov     r8d, ebx; Size
0x180012644  xor     edx, edx; Flags
0x180012646  call    cs:__imp_RtlAllocateHeap
0x18001264c  mov     rdi, rax
0x18001264f  test    rax, rax
0x180012652  jz      loc_18001284D
0x180012658  mov     r8d, ebx; Size
0x18001265b  xor     edx, edx; Val
0x18001265d  mov     rcx, rax; void *
0x180012660  call    memset_0
0x180012665  lea     rax, [rdi+18h]
0x180012669  mov     [rax+8], rax
0x18001266d  mov     [rax], rax
0x180012670  lea     rax, [rdi+28h]
0x180012674  mov     [rax+8], rax
0x180012678  mov     [rax], rax
0x18001267b  movups  xmm0, xmmword ptr [rbp+0]
0x18001267f  movups  xmmword ptr [rdi+3Ch], xmm0
0x180012683  movups  xmm1, xmmword ptr [rbp+10h]
0x180012687  movups  xmmword ptr [rdi+4Ch], xmm1
0x18001268b  movups  xmm0, xmmword ptr [rbp+20h]
0x18001268f  movups  xmmword ptr [rdi+5Ch], xmm0
0x180012693  movups  xmm1, xmmword ptr [rbp+30h]
0x180012697  movups  xmmword ptr [rdi+6Ch], xmm1
0x18001269b  movups  xmm0, xmmword ptr [rbp+40h]
0x18001269f  movups  xmmword ptr [rdi+7Ch], xmm0
0x1800126a3  movups  xmm1, xmmword ptr [rbp+50h]
0x1800126a7  movups  xmmword ptr [rdi+8Ch], xmm1
0x1800126ae  movups  xmm0, xmmword ptr [rbp+60h]
0x1800126b2  movups  xmmword ptr [rdi+9Ch], xmm0
0x1800126b9  movups  xmm1, xmmword ptr [rbp+70h]
0x1800126bd  movups  xmmword ptr [rdi+0ACh], xmm1
0x1800126c4  movzx   eax, word ptr [rbp+80h]
0x1800126cb  mov     [rdi+0BCh], ax
0x1800126d2  mov     [rdi+10h], r13
0x1800126d6  mov     rax, [r14+8]
0x1800126da  cmp     [rax], r14
0x1800126dd  jnz     loc_18001285B
0x1800126e3  mov     rcx, cs:BipHeap; HeapHandle
0x1800126ea  xor     edx, edx; Flags
0x1800126ec  mov     [rdi], r14
0x1800126ef  mov     r8d, 1D0h; Size
0x1800126f5  mov     [rdi+8], rax
0x1800126f9  xor     r15d, r15d
0x1800126fc  mov     [rax], rdi
0x1800126ff  mov     [r14+8], rdi
0x180012703  call    cs:__imp_RtlAllocateHeap
0x180012709  mov     r14, rax
0x18001270c  test    rax, rax
0x18001270f  jz      loc_180012853
0x180012715  mov     rcx, [rdi+10h]
0x180012719  lea     r9, [rsp+78h+arg_10]
0x180012721  add     rcx, 0A0h
0x180012728  mov     [rsp+78h+arg_10], 1D0h
0x180012733  mov     r8, rax
0x180012736  lea     rdx, [rdi+3Ch]
0x18001273a  call    cs:__imp_PsmCreateKey
0x180012740  mov     ecx, cs:dword_1800C46D8
0x180012746  mov     edx, r12d
0x180012749  mov     rax, gs:58h
0x180012752  shl     edx, cl
0x180012754  mov     ecx, cs:_tls_index
0x18001275a  mov     r8d, 4
0x180012760  mov     [rsp+78h+arg_18], edx
0x180012767  mov     rbx, [rax+rcx*8]
0x18001276b  mov     [rsp+78h+var_48], rbx
0x180012770  cmp     [rbx+r8], edx
0x180012774  jnb     loc_18001280E
0x18001277a  lea     rcx, BipSessionLock
0x180012781  call    cs:__imp_RtlAcquireSRWLockShared
0x180012787  mov     eax, [rsp+78h+arg_18]
0x18001278e  mov     rcx, r13
0x180012791  mov     edx, 4
0x180012796  or      [rbx+rdx], eax
0x180012799  call    BipPackageGetActiveSessionId
0x18001279e  mov     ecx, cs:dword_1800C46D8
0x1800127a4  mov     ebx, eax
0x1800127a6  shl     r12d, cl
0x1800127a9  lea     rcx, BipSessionLock
0x1800127b0  not     r12d
0x1800127b3  call    cs:__imp_RtlReleaseSRWLockShared
0x1800127b9  mov     rax, [rsp+78h+var_48]
0x1800127be  lea     r9, [rsp+78h+arg_8]
0x1800127c6  mov     ecx, 4
0x1800127cb  mov     r8, r14
0x1800127ce  mov     edx, ebx
0x1800127d0  and     [rax+rcx], r12d
0x1800127d4  mov     rcx, [r13+18h]
0x1800127d8  call    BipSystemIntUiQueryState
0x1800127dd  test    eax, eax
0x1800127df  js      short loc_1800127F4
0x1800127e1  mov     r8b, [rsp+78h+arg_8]
0x1800127e9  mov     rdx, rbp
0x1800127ec  mov     rcx, r13
0x1800127ef  call    BipPackageUpdateForegroundState
0x1800127f4  mov     [rsi], rdi
0x1800127f7  mov     r8, r14; P
0x1800127fa  mov     rcx, cs:BipHeap; HeapHandle
0x180012801  xor     edx, edx; Flags
0x180012803  call    cs:__imp_RtlFreeHeap
0x180012809  jmp     loc_18001261A
0x18001280e  call    cs:__imp_IsDebuggerPresent
0x180012814  test    eax, eax
0x180012816  jz      loc_18001277A
0x18001281c  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180012823  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180012828  jmp     loc_18001277A
0x18001282d  xor     r15d, r15d
0x180012830  jmp     loc_1800125C1
0x180012835  xor     eax, eax
0x180012837  jmp     loc_1800125F5
0x18001283c  mov     rax, [rbx]
0x18001283f  xor     ebx, ebx
0x180012841  cmp     rax, r14
0x180012844  cmovnz  rbx, rax
0x180012848  jmp     loc_1800125D5
0x18001284d  mov     r15d, 0C0000017h
0x180012853  mov     [rsi], rdi
0x180012856  jmp     loc_18001261A
0x18001285b  mov     ecx, 3
0x180012860  int     29h; Win8: RtlFailFast(ecx)
```

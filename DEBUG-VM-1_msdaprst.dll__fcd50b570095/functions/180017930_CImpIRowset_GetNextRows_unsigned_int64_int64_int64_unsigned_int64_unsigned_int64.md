# CImpIRowset::GetNextRows(unsigned __int64,__int64,__int64,unsigned __int64 *,unsigned __int64 * *)

- ea: `0x180017930`
- end: `0x180017c17`
- name: `?GetNextRows@CImpIRowset@@UEAAJ_K_J1PEA_KPEAPEA_K@Z`
- size: `743`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, __int64, __int64, unsigned __int64 *, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180011278`
- `0x180015fb4`
- `0x180016e68`
- `0x1800172e0`
- `0x180017930`
- `0x180020764`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001796a`
- `KERNEL32!GetCurrentThreadId` at `0x18001796a`
- `KERNEL32!LeaveCriticalSection` at `0x1800179d4`
- `KERNEL32!LeaveCriticalSection` at `0x180017a33`
- `KERNEL32!LeaveCriticalSection` at `0x180017bbd`
- `KERNEL32!LeaveCriticalSection` at `0x180017bf7`
- `KERNEL32!LeaveCriticalSection` at `0x1800179d4`
- `KERNEL32!LeaveCriticalSection` at `0x180017a33`
- `KERNEL32!LeaveCriticalSection` at `0x180017bbd`
- `KERNEL32!LeaveCriticalSection` at `0x180017bf7`
- `ole32!CoTaskMemAlloc` at `0x180017b10`
- `ole32!CoTaskMemAlloc` at `0x180017b10`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017986`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180017986`
- `MSDART!UMSEnterCSWraper` at `0x18001795d`
- `MSDART!UMSEnterCSWraper` at `0x18001795d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CImpIRowset::GetNextRows(
        CImpIRowset *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        unsigned __int64 **a6)
{
  __int64 v9; // rbx
  unsigned __int64 *v10; // r13
  unsigned __int64 **v11; // r15
  bool v12; // sf
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v16; // r9
  int v17; // ecx
  __int64 v18; // rcx
  int NextSlots; // eax
  unsigned int v20; // r8d
  unsigned int v21; // ebp
  int v22; // esi
  __int64 v23; // r14
  int v24; // eax
  unsigned __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // edi
  __int64 v31; // rcx
  unsigned int v32; // [rsp+70h] [rbp+8h] BYREF
  __int64 v33; // [rsp+78h] [rbp+10h]

  v33 = a2;
  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  v32 = 0;
  SetErrorInfo(0, 0);
  v10 = a5;
  if ( !a5 || (v11 = a6) == 0 )
  {
    v17 = -2147024809;
    goto LABEL_44;
  }
  *a5 = 0;
  if ( a4 )
  {
    if ( a4 < 0 )
    {
LABEL_42:
      v17 = -2147217884;
      goto LABEL_44;
    }
    v12 = a3 < 0;
  }
  else
  {
    v12 = a3 < 0;
    if ( !a3 )
    {
      --*(_DWORD *)(v9 + 16);
LABEL_8:
      v13 = (*(_DWORD *)(v9 + 12))-- == 1;
      if ( v13 )
        *(_DWORD *)(v9 + 8) = -1;
      v14 = *(_QWORD *)v9;
      --*(_DWORD *)(v14 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      return 0;
    }
  }
  if ( v12 )
    goto LABEL_42;
  if ( (unsigned int)CBitArray::ArrayEmpty(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL)) )
  {
    v17 = -2147217883;
LABEL_44:
    v30 = Exit(v17, 0);
    --*(_DWORD *)(v9 + 16);
    v13 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v9 + 8) = -1;
    v31 = *(_QWORD *)v9;
    --*(_DWORD *)(v31 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
    return v30;
  }
  if ( (*(_DWORD *)(v16 + 248) & 0x100) != 0 )
    goto LABEL_17;
  if ( (int)CRowset::Rebind(
              (CRowset *)v16,
              (unsigned __int8 *)(*(_QWORD *)(v16 + 224)
                                + (unsigned int)(*(_DWORD *)(v16 + 220) * *(_DWORD *)(v16 + 232)))) < 0 )
  {
LABEL_21:
    v17 = -2147467259;
    goto LABEL_44;
  }
  NextSlots = GetNextSlots(*(struct tagLSTSLOT **)(*((_QWORD *)this + 3) + 200LL), 1u, &v32);
  if ( NextSlots < 0 )
  {
LABEL_23:
    v17 = NextSlots;
    goto LABEL_44;
  }
  v21 = 1;
  v22 = 1;
  v23 = a3 + 1;
  while ( v22 <= v23 )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3), v33);
    if ( v24 == 1 )
    {
      v21 = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 248LL) |= 0x100u;
      break;
    }
    if ( v24 < 0 )
      goto LABEL_21;
    ++v22;
  }
  *(_DWORD *)(*((_QWORD *)this + 3) + 244LL) = *(_DWORD *)(*((_QWORD *)this + 3) + 240LL);
  *(_DWORD *)(*((_QWORD *)this + 3) + 240LL) += v22 - 1;
  *(_DWORD *)(*((_QWORD *)this + 3) + 236LL) += v22 - 1;
  *v10 = v21;
  if ( !*v11 )
  {
    v25 = (unsigned __int64 *)CoTaskMemAlloc(8u);
    *v11 = v25;
    if ( !v25 )
    {
      v17 = -2147024882;
      goto LABEL_44;
    }
  }
  v26 = *((_QWORD *)this + 3);
  if ( v21 )
  {
    v27 = *(_DWORD *)(v26 + 220) * v32;
    v28 = *(_QWORD *)(v26 + 224);
    ++*(_DWORD *)(v27 + v28);
    *(_QWORD *)(v27 + v28 + 16) = *(unsigned int *)(*((_QWORD *)this + 3) + 244LL) + 1LL;
    ++*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
    **v11 = v32;
  }
  else
  {
    NextSlots = ReleaseSlots(*(struct tagLSTSLOT **)(v26 + 200), v32, v20);
    if ( NextSlots < 0 )
      goto LABEL_23;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 248LL) & 0x100) != 0 )
  {
LABEL_17:
    --*(_DWORD *)(v9 + 16);
    v13 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v9 + 8) = -1;
    v18 = *(_QWORD *)v9;
    --*(_DWORD *)(v18 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 8));
    return 265926;
  }
  --*(_DWORD *)(v9 + 16);
  if ( a4 <= 1 )
    goto LABEL_8;
  v13 = (*(_DWORD *)(v9 + 12))-- == 1;
  if ( v13 )
    *(_DWORD *)(v9 + 8) = -1;
  v29 = *(_QWORD *)v9;
  --*(_DWORD *)(v29 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
  return 265920;
}

```

## disassembly

```asm
0x180017930  mov     [rsp+arg_10], rbx
0x180017935  mov     [rsp+arg_8], rdx
0x18001793a  push    rbp
0x18001793b  push    rsi
0x18001793c  push    rdi
0x18001793d  push    r12
0x18001793f  push    r13
0x180017941  push    r14
0x180017943  push    r15
0x180017945  sub     rsp, 30h
0x180017949  mov     r12, r9
0x18001794c  mov     r14, r8
0x18001794f  mov     rdi, rcx
0x180017952  mov     rbx, [rcx+18h]
0x180017956  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001795a  mov     rcx, rbx
0x18001795d  call    cs:__imp_UMSEnterCSWraper
0x180017963  xor     ebp, ebp
0x180017965  cmp     [rbx+0Ch], ebp
0x180017968  jnz     short loc_180017973
0x18001796a  call    cs:__imp_GetCurrentThreadId
0x180017970  mov     [rbx+8], eax
0x180017973  inc     dword ptr [rbx+0Ch]
0x180017976  inc     dword ptr [rbx+10h]
0x180017979  mov     [rsp+68h+var_48], rbx
0x18001797e  mov     [rsp+68h+arg_0], ebp
0x180017982  xor     edx, edx; perrinfo
0x180017984  xor     ecx, ecx; dwReserved
0x180017986  call    cs:__imp_SetErrorInfo
0x18001798c  mov     r13, [rsp+68h+arg_20]
0x180017994  test    r13, r13
0x180017997  jz      loc_180017BD1
0x18001799d  mov     r15, [rsp+68h+arg_28]
0x1800179a5  test    r15, r15
0x1800179a8  jz      loc_180017BD1
0x1800179ae  mov     [r13+0], rbp
0x1800179b2  test    r12, r12
0x1800179b5  jnz     short loc_1800179E1
0x1800179b7  test    r14, r14
0x1800179ba  jnz     short loc_1800179EA
0x1800179bc  or      edx, 0FFFFFFFFh
0x1800179bf  add     [rbx+10h], edx
0x1800179c2  add     [rbx+0Ch], edx
0x1800179c5  jnz     short loc_1800179CA
0x1800179c7  mov     [rbx+8], edx
0x1800179ca  mov     rcx, [rbx]
0x1800179cd  dec     dword ptr [rcx+30h]
0x1800179d0  add     rcx, 8; lpCriticalSection
0x1800179d4  call    cs:__imp_LeaveCriticalSection
0x1800179da  xor     eax, eax
0x1800179dc  jmp     loc_180017BFF
0x1800179e1  js      loc_180017BCA
0x1800179e7  test    r14, r14
0x1800179ea  js      loc_180017BCA
0x1800179f0  mov     r9, [rdi+18h]
0x1800179f4  mov     rcx, [r9+0D0h]; this
0x1800179fb  call    ?ArrayEmpty@CBitArray@@QEAAJXZ; CBitArray::ArrayEmpty(void)
0x180017a00  test    eax, eax
0x180017a02  jz      short loc_180017A0E
0x180017a04  mov     ecx, 80040E25h
0x180017a09  jmp     loc_180017BD6
0x180017a0e  test    dword ptr [r9+0F8h], 100h
0x180017a19  jz      short loc_180017A43
0x180017a1b  or      edx, 0FFFFFFFFh
0x180017a1e  add     [rbx+10h], edx
0x180017a21  add     [rbx+0Ch], edx
0x180017a24  jnz     short loc_180017A29
0x180017a26  mov     [rbx+8], edx
0x180017a29  mov     rcx, [rbx]
0x180017a2c  dec     dword ptr [rcx+30h]
0x180017a2f  add     rcx, 8; lpCriticalSection
0x180017a33  call    cs:__imp_LeaveCriticalSection
0x180017a39  mov     eax, 40EC6h
0x180017a3e  jmp     loc_180017BFF
0x180017a43  mov     edx, [r9+0E8h]
0x180017a4a  imul    edx, [r9+0DCh]
0x180017a52  add     rdx, [r9+0E0h]; unsigned __int8 *
0x180017a59  mov     rcx, r9; this
0x180017a5c  call    ?Rebind@CRowset@@QEAAJPEAE@Z; CRowset::Rebind(uchar *)
0x180017a61  test    eax, eax
0x180017a63  jns     short loc_180017A6F
0x180017a65  mov     ecx, 80004005h
0x180017a6a  jmp     loc_180017BD6
0x180017a6f  mov     rcx, [rdi+18h]
0x180017a73  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x180017a78  mov     edx, 1; unsigned int
0x180017a7d  mov     rcx, [rcx+0C8h]; struct tagLSTSLOT *
0x180017a84  call    ?GetNextSlots@@YAJPEAUtagLSTSLOT@@KPEAK@Z; GetNextSlots(tagLSTSLOT *,ulong,ulong *)
0x180017a89  test    eax, eax
0x180017a8b  jns     short loc_180017A94
0x180017a8d  mov     ecx, eax
0x180017a8f  jmp     loc_180017BD6
0x180017a94  mov     ebp, 1
0x180017a99  mov     esi, ebp
0x180017a9b  inc     r14
0x180017a9e  movsxd  rax, esi
0x180017aa1  cmp     rax, r14
0x180017aa4  jg      short loc_180017AD5
0x180017aa6  mov     rcx, [rdi+18h]
0x180017aaa  mov     rax, [rcx]
0x180017aad  mov     rdx, [rsp+68h+arg_8]
0x180017ab2  mov     rax, [rax+38h]
0x180017ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017abb  cmp     eax, ebp
0x180017abd  jz      short loc_180017AC7
0x180017abf  test    eax, eax
0x180017ac1  js      short loc_180017A65
0x180017ac3  inc     esi
0x180017ac5  jmp     short loc_180017A9E
0x180017ac7  xor     ebp, ebp
0x180017ac9  mov     rax, [rdi+18h]
0x180017acd  bts     dword ptr [rax+0F8h], 8
0x180017ad5  mov     rcx, [rdi+18h]
0x180017ad9  mov     eax, [rcx+0F0h]
0x180017adf  mov     [rcx+0F4h], eax
0x180017ae5  mov     rcx, [rdi+18h]
0x180017ae9  lea     eax, [rsi-1]
0x180017aec  add     [rcx+0F0h], eax
0x180017af2  mov     rcx, [rdi+18h]
0x180017af6  lea     eax, [rsi-1]
0x180017af9  add     [rcx+0ECh], eax
0x180017aff  mov     eax, ebp
0x180017b01  mov     [r13+0], rax
0x180017b05  cmp     qword ptr [r15], 0
0x180017b09  jnz     short loc_180017B28
0x180017b0b  mov     ecx, 8; cb
0x180017b10  call    cs:__imp_CoTaskMemAlloc
0x180017b16  mov     [r15], rax
0x180017b19  test    rax, rax
0x180017b1c  jnz     short loc_180017B28
0x180017b1e  mov     ecx, 8007000Eh
0x180017b23  jmp     loc_180017BD6
0x180017b28  mov     rcx, [rdi+18h]
0x180017b2c  test    ebp, ebp
0x180017b2e  jnz     short loc_180017B49
0x180017b30  mov     edx, [rsp+68h+arg_0]; unsigned int
0x180017b34  mov     rcx, [rcx+0C8h]; struct tagLSTSLOT *
0x180017b3b  call    ?ReleaseSlots@@YAJPEAUtagLSTSLOT@@KK@Z; ReleaseSlots(tagLSTSLOT *,ulong,ulong)
0x180017b40  test    eax, eax
0x180017b42  jns     short loc_180017B87
0x180017b44  jmp     loc_180017A8D
0x180017b49  mov     eax, [rsp+68h+arg_0]
0x180017b4d  imul    eax, [rcx+0DCh]
0x180017b54  mov     r8d, eax
0x180017b57  mov     rdx, [rcx+0E0h]
0x180017b5e  inc     dword ptr [rax+rdx]
0x180017b61  mov     rax, [rdi+18h]
0x180017b65  mov     ecx, [rax+0F4h]
0x180017b6b  inc     rcx
0x180017b6e  mov     [r8+rdx+10h], rcx
0x180017b73  mov     rax, [rdi+18h]
0x180017b77  inc     dword ptr [rax+108h]
0x180017b7d  mov     ecx, [rsp+68h+arg_0]
0x180017b81  mov     rax, [r15]
0x180017b84  mov     [rax], rcx
0x180017b87  mov     rax, [rdi+18h]
0x180017b8b  or      edx, 0FFFFFFFFh
0x180017b8e  test    dword ptr [rax+0F8h], 100h
0x180017b98  jnz     loc_180017A1E
0x180017b9e  add     [rbx+10h], edx
0x180017ba1  cmp     r12, 1
0x180017ba5  jle     loc_1800179C2
0x180017bab  add     [rbx+0Ch], edx
0x180017bae  jnz     short loc_180017BB3
0x180017bb0  mov     [rbx+8], edx
0x180017bb3  mov     rcx, [rbx]
0x180017bb6  dec     dword ptr [rcx+30h]
0x180017bb9  add     rcx, 8; lpCriticalSection
0x180017bbd  call    cs:__imp_LeaveCriticalSection
0x180017bc3  mov     eax, 40EC0h
0x180017bc8  jmp     short loc_180017BFF
0x180017bca  mov     ecx, 80040E24h
0x180017bcf  jmp     short loc_180017BD6
0x180017bd1  mov     ecx, 80070057h; int
0x180017bd6  xor     edx, edx; unsigned int
0x180017bd8  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180017bdd  mov     edi, eax
0x180017bdf  or      edx, 0FFFFFFFFh
0x180017be2  add     [rbx+10h], edx
0x180017be5  add     [rbx+0Ch], edx
0x180017be8  jnz     short loc_180017BED
0x180017bea  mov     [rbx+8], edx
0x180017bed  mov     rcx, [rbx]
0x180017bf0  dec     dword ptr [rcx+30h]
0x180017bf3  add     rcx, 8; lpCriticalSection
0x180017bf7  call    cs:__imp_LeaveCriticalSection
0x180017bfd  mov     eax, edi
0x180017bff  mov     rbx, [rsp+68h+arg_10]
0x180017c07  add     rsp, 30h
0x180017c0b  pop     r15
0x180017c0d  pop     r14
0x180017c0f  pop     r13
0x180017c11  pop     r12
0x180017c13  pop     rdi
0x180017c14  pop     rsi
0x180017c15  pop     rbp
0x180017c16  retn
```

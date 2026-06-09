# CImpIAccessor::GetBindings(unsigned __int64,ulong *,unsigned __int64 *,tagDBBINDING * *)

- ea: `0x180002340`
- end: `0x1800024ca`
- name: `?GetBindings@CImpIAccessor@@UEAAJ_KPEAKPEA_KPEAPEAUtagDBBINDING@@@Z`
- size: `394`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *, unsigned __int64 *, struct tagDBBINDING **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002340`
- `0x180015fb4`
- `0x180016d94`
- `0x18002e012`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002379`
- `KERNEL32!GetCurrentThreadId` at `0x180002379`
- `KERNEL32!LeaveCriticalSection` at `0x180002444`
- `KERNEL32!LeaveCriticalSection` at `0x18000247b`
- `KERNEL32!LeaveCriticalSection` at `0x1800024ab`
- `KERNEL32!LeaveCriticalSection` at `0x180002444`
- `KERNEL32!LeaveCriticalSection` at `0x18000247b`
- `KERNEL32!LeaveCriticalSection` at `0x1800024ab`
- `ole32!CoTaskMemAlloc` at `0x180002403`
- `ole32!CoTaskMemAlloc` at `0x180002403`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000239a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000239a`
- `MSDART!UMSEnterCSWraper` at `0x18000236d`
- `MSDART!UMSEnterCSWraper` at `0x18000236d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::GetBindings(
        CImpIAccessor *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int64 *a4,
        struct tagDBBINDING **a5)
{
  __int64 v9; // rbx
  void **v10; // rsi
  unsigned int *v11; // rdi
  unsigned int v12; // ebp
  LPVOID v13; // rax
  bool v14; // zf
  __int64 v15; // rcx
  int v17; // ecx
  unsigned int v18; // edi
  __int64 v19; // rcx
  unsigned int v20; // esi
  __int64 v21; // rcx
  unsigned int *v22; // [rsp+50h] [rbp+8h] BYREF
  __int64 v23; // [rsp+60h] [rbp+18h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  v23 = v9;
  v22 = 0;
  SetErrorInfo(0, 0);
  if ( a3 && a4 && (v10 = (void **)a5) != 0 )
  {
    *a3 = 0;
    *a4 = 0;
    *v10 = 0;
    if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v22) >= 0
      && (v11 = v22) != 0 )
    {
      v12 = 88 * v22[2];
      v13 = CoTaskMemAlloc(v12);
      *v10 = v13;
      if ( v13 )
      {
        *a3 = *v11;
        *a4 = v11[2];
        memcpy_0(*v10, v11 + 4, v12);
        --*(_DWORD *)(v9 + 16);
        v14 = (*(_DWORD *)(v9 + 12))-- == 1;
        if ( v14 )
          *(_DWORD *)(v9 + 8) = -1;
        v15 = *(_QWORD *)v9;
        --*(_DWORD *)(v15 + 48);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
        return 0;
      }
      v17 = -2147024882;
    }
    else
    {
      v17 = -2147217920;
    }
    v18 = Exit(v17, 0);
    --*(_DWORD *)(v9 + 16);
    v14 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v19 = *(_QWORD *)v9;
    --*(_DWORD *)(v19 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 8));
    return v18;
  }
  else
  {
    v20 = Exit(-2147024809, 0);
    --*(_DWORD *)(v9 + 16);
    v14 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v21 = *(_QWORD *)v9;
    --*(_DWORD *)(v21 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 8));
    return v20;
  }
}

```

## disassembly

```asm
0x180002340  mov     [rsp+arg_8], rbx
0x180002345  mov     [rsp+arg_18], rbp
0x18000234a  push    rsi
0x18000234b  push    rdi
0x18000234c  push    r12
0x18000234e  push    r14
0x180002350  push    r15
0x180002352  sub     rsp, 20h
0x180002356  mov     r14, r9
0x180002359  mov     r15, r8
0x18000235c  mov     r12, rdx
0x18000235f  mov     rbp, rcx
0x180002362  mov     rbx, [rcx+18h]
0x180002366  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18000236a  mov     rcx, rbx
0x18000236d  call    cs:__imp_UMSEnterCSWraper
0x180002373  cmp     dword ptr [rbx+0Ch], 0
0x180002377  jnz     short loc_180002382
0x180002379  call    cs:__imp_GetCurrentThreadId
0x18000237f  mov     [rbx+8], eax
0x180002382  inc     dword ptr [rbx+0Ch]
0x180002385  inc     dword ptr [rbx+10h]
0x180002388  mov     [rsp+48h+arg_10], rbx
0x18000238d  mov     [rsp+48h+arg_0], 0
0x180002396  xor     edx, edx; perrinfo
0x180002398  xor     ecx, ecx; dwReserved
0x18000239a  call    cs:__imp_SetErrorInfo
0x1800023a0  test    r15, r15
0x1800023a3  jz      loc_180002485
0x1800023a9  test    r14, r14
0x1800023ac  jz      loc_180002485
0x1800023b2  mov     rsi, [rsp+48h+arg_20]
0x1800023b7  test    rsi, rsi
0x1800023ba  jz      loc_180002485
0x1800023c0  mov     dword ptr [r15], 0
0x1800023c7  mov     qword ptr [r14], 0
0x1800023ce  mov     qword ptr [rsi], 0
0x1800023d5  mov     edx, r12d; unsigned int
0x1800023d8  mov     rcx, [rbp+18h]
0x1800023dc  lea     r8, [rsp+48h+arg_0]; void *
0x1800023e1  mov     rcx, [rcx+0C0h]; this
0x1800023e8  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x1800023ed  test    eax, eax
0x1800023ef  js      short loc_180002455
0x1800023f1  mov     rdi, [rsp+48h+arg_0]
0x1800023f6  test    rdi, rdi
0x1800023f9  jz      short loc_180002455
0x1800023fb  imul    eax, [rdi+8], 58h ; 'X'
0x1800023ff  mov     ebp, eax
0x180002401  mov     ecx, eax; cb
0x180002403  call    cs:__imp_CoTaskMemAlloc
0x180002409  mov     [rsi], rax
0x18000240c  test    rax, rax
0x18000240f  jz      short loc_18000244E
0x180002411  mov     eax, [rdi]
0x180002413  mov     [r15], eax
0x180002416  mov     eax, [rdi+8]
0x180002419  mov     [r14], rax
0x18000241c  lea     rdx, [rdi+10h]; Src
0x180002420  mov     r8d, ebp; Size
0x180002423  mov     rcx, [rsi]; void *
0x180002426  call    memcpy_0
0x18000242b  nop
0x18000242c  or      edx, 0FFFFFFFFh
0x18000242f  add     [rbx+10h], edx
0x180002432  add     [rbx+0Ch], edx
0x180002435  jnz     short loc_18000243A
0x180002437  mov     [rbx+8], edx
0x18000243a  mov     rcx, [rbx]
0x18000243d  dec     dword ptr [rcx+30h]
0x180002440  add     rcx, 8; lpCriticalSection
0x180002444  call    cs:__imp_LeaveCriticalSection
0x18000244a  xor     eax, eax
0x18000244c  jmp     short loc_1800024B3
0x18000244e  mov     ecx, 8007000Eh
0x180002453  jmp     short loc_18000245A
0x180002455  mov     ecx, 80040E00h; int
0x18000245a  xor     edx, edx; unsigned int
0x18000245c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002461  mov     edi, eax
0x180002463  or      edx, 0FFFFFFFFh
0x180002466  add     [rbx+10h], edx
0x180002469  add     [rbx+0Ch], edx
0x18000246c  jnz     short loc_180002471
0x18000246e  mov     [rbx+8], edx
0x180002471  mov     rcx, [rbx]
0x180002474  dec     dword ptr [rcx+30h]
0x180002477  add     rcx, 8; lpCriticalSection
0x18000247b  call    cs:__imp_LeaveCriticalSection
0x180002481  mov     eax, edi
0x180002483  jmp     short loc_1800024B3
0x180002485  xor     edx, edx; unsigned int
0x180002487  mov     ecx, 80070057h; int
0x18000248c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002491  mov     esi, eax
0x180002493  or      edx, 0FFFFFFFFh
0x180002496  add     [rbx+10h], edx
0x180002499  add     [rbx+0Ch], edx
0x18000249c  jnz     short loc_1800024A1
0x18000249e  mov     [rbx+8], edx
0x1800024a1  mov     rcx, [rbx]
0x1800024a4  dec     dword ptr [rcx+30h]
0x1800024a7  add     rcx, 8; lpCriticalSection
0x1800024ab  call    cs:__imp_LeaveCriticalSection
0x1800024b1  mov     eax, esi
0x1800024b3  mov     rbx, [rsp+48h+arg_8]
0x1800024b8  mov     rbp, [rsp+48h+arg_18]
0x1800024bd  add     rsp, 20h
0x1800024c1  pop     r15
0x1800024c3  pop     r14
0x1800024c5  pop     r12
0x1800024c7  pop     rdi
0x1800024c8  pop     rsi
0x1800024c9  retn
```

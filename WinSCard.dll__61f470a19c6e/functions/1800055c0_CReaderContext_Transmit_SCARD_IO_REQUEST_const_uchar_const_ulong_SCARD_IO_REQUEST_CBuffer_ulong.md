# CReaderContext::Transmit(_SCARD_IO_REQUEST const *,uchar const *,ulong,_SCARD_IO_REQUEST *,CBuffer &,ulong)

- ea: `0x1800055c0`
- end: `0x180005891`
- name: `?Transmit@CReaderContext@@QEAAXPEBU_SCARD_IO_REQUEST@@PEBEKPEAU2@AEAVCBuffer@@K@Z`
- size: `721`
- prototype: `void(CReaderContext *__hidden this, const struct _SCARD_IO_REQUEST *, const unsigned __int8 *, unsigned int, struct _SCARD_IO_REQUEST *, struct CBuffer *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003790`

## callees

- `0x1800054a4`
- `0x1800055c0`
- `0x180005970`
- `0x180005a90`
- `0x18000ff10`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005775`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005775`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005753`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005753`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005783`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReaderContext::Transmit(
        CReaderContext *this,
        struct _SCARD_IO_REQUEST *a2,
        const unsigned __int8 *a3,
        int a4,
        struct _SCARD_IO_REQUEST *a5,
        struct CBuffer *a6,
        unsigned int a7)
{
  int v8; // r12d
  CSCardSubcontext *v11; // rdi
  __int64 *v12; // rcx
  unsigned int v13; // eax
  DWORD cbPciLength; // eax
  ulong v15; // eax
  ulong v16; // r14d
  size_t v17; // rsi
  void *v18; // r13
  void *v19; // r15
  void *v20; // rcx
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  void *v24; // rcx
  HANDLE v25; // rax
  __int64 v26; // rdx
  int v27; // [rsp+48h] [rbp-A0h]
  int v28; // [rsp+50h] [rbp-98h]
  _DWORD Size[3]; // [rsp+54h] [rbp-94h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-88h] BYREF
  ulong v31; // [rsp+64h] [rbp-84h] BYREF
  ulong v32; // [rsp+68h] [rbp-80h] BYREF
  ulong v33; // [rsp+6Ch] [rbp-7Ch] BYREF
  ulong v34; // [rsp+70h] [rbp-78h] BYREF
  void *Src; // [rsp+78h] [rbp-70h] BYREF
  __int128 v36; // [rsp+80h] [rbp-68h] BYREF
  __int64 v37; // [rsp+90h] [rbp-58h]
  ulong v38; // [rsp+98h] [rbp-50h] BYREF
  CSCardSubcontext *v39; // [rsp+A0h] [rbp-48h]

  v8 = (int)a3;
  memset(Size, 0, sizeof(Size));
  Src = 0;
  v36 = 0;
  v37 = 0;
  try
  {
    v11 = (CSCardSubcontext *)*((_QWORD *)this + 3);
    CSCardSubcontext::WaitForAvailable(v11);
    v39 = v11;
    v12 = qword_180038380;
    if ( a2 )
      v12 = (__int64 *)a2;
    LODWORD(v36) = *(_DWORD *)v12;
    v13 = *((_DWORD *)v12 + 1);
    if ( v13 < 8 )
    {
      pExceptionObject = -2146435068;
      throw (ulong *)&pExceptionObject;
    }
    LODWORD(v37) = v13 - 8;
    if ( v13 == 8 )
      *((_QWORD *)&v36 + 1) = 0;
    else
      *((_QWORD *)&v36 + 1) = v12 + 1;
    Size[0] = a7;
    if ( a5 )
      cbPciLength = a5->cbPciLength;
    else
      cbPciLength = 8;
    v15 = CalRpcTransmit(
            *(_QWORD *)(*((_QWORD *)this + 3) + 112LL),
            *((_DWORD *)this + 8),
            (int)&v36,
            v8,
            a4,
            cbPciLength,
            (__int64)&Size[1],
            (__int64)&Src,
            (__int64)Size,
            v27,
            v28,
            Size[1],
            pExceptionObject);
    v16 = v15;
    if ( v15 )
    {
      v31 = v15;
      throw &v31;
    }
    if ( a5 )
    {
      v26 = *(_QWORD *)&Size[1];
      if ( a5->cbPciLength < (unsigned __int64)*(unsigned int *)(*(_QWORD *)&Size[1] + 16LL) + 8 )
      {
        v32 = -2146435047;
        throw &v32;
      }
      a5->dwProtocol = **(_DWORD **)&Size[1];
      a5->cbPciLength = *(_DWORD *)(v26 + 16) + 8;
      memcpy_0(&a5[1], *(const void **)(v26 + 8), *(unsigned int *)(v26 + 16));
    }
    v17 = Size[0];
    v18 = Src;
    if ( *((_DWORD *)a6 + 5) >= Size[0] )
    {
      v19 = (void *)*((_QWORD *)a6 + 1);
    }
    else
    {
      v19 = operator new[](Size[0]);
      if ( !v19 )
      {
        v33 = 14;
        throw &v33;
      }
      v20 = (void *)*((_QWORD *)a6 + 1);
      if ( v20 )
        operator delete(v20);
      *((_QWORD *)a6 + 1) = v19;
      *((_DWORD *)a6 + 5) = v17;
    }
    *((_DWORD *)a6 + 4) = 0;
    if ( (_DWORD)v17 )
      memcpy_0(v19, v18, v17);
    *((_DWORD *)a6 + 4) = v17;
    if ( v11 )
      CSCardSubcontext::ReleaseSubcontext(v11);
  }
  catch ( ulong v38 )
  {
    v16 = v38;
  }
  catch ( ... )
  {
    v16 = -2146435068;
  }
  v21 = Src;
  if ( Src )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  v23 = *(void **)&Size[1];
  if ( *(_QWORD *)&Size[1] )
  {
    v24 = *(void **)(*(_QWORD *)&Size[1] + 8LL);
    if ( v24 )
    {
      MIDL_user_free(v24);
      v23 = *(void **)&Size[1];
    }
    if ( v23 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v23);
    }
  }
  if ( v16 )
  {
    v34 = v16;
    throw &v34;
  }
}

```

## disassembly

```asm
0x1800055c0  mov     r11, rsp
0x1800055c3  push    rbx
0x1800055c4  push    rsi
0x1800055c5  push    rdi
0x1800055c6  push    r12
0x1800055c8  push    r13
0x1800055ca  push    r14
0x1800055cc  push    r15
0x1800055ce  sub     rsp, 0B0h
0x1800055d5  mov     r15d, r9d
0x1800055d8  mov     r12, r8
0x1800055db  mov     rsi, rdx
0x1800055de  mov     r14, rcx
0x1800055e1  mov     rbx, [rsp+0E8h+arg_20]
0x1800055e9  xor     r13d, r13d
0x1800055ec  mov     qword ptr [rsp+0E8h+Size+4], r13; int
0x1800055f1  mov     dword ptr [rsp+0E8h+Size], r13d
0x1800055f6  mov     [r11-70h], r13
0x1800055fa  xorps   xmm0, xmm0
0x1800055fd  xor     eax, eax
0x1800055ff  movups  xmmword ptr [r11-68h], xmm0
0x180005604  mov     [r11-58h], rax
0x180005608  mov     rdi, [rcx+18h]
0x18000560c  mov     [r11-48h], r13
0x180005610  mov     rcx, rdi; this
0x180005613  call    ?WaitForAvailable@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::WaitForAvailable(void)
0x180005618  mov     [rsp+0E8h+var_48], rdi
0x180005620  lea     rcx, qword_180038380
0x180005627  test    rsi, rsi
0x18000562a  cmovnz  rcx, rsi
0x18000562e  mov     eax, [rcx]
0x180005630  mov     [rsp+0E8h+var_68], eax
0x180005637  mov     eax, [rcx+4]
0x18000563a  cmp     eax, 8
0x18000563d  jb      loc_1800057C7
0x180005643  add     eax, 0FFFFFFF8h
0x180005646  mov     dword ptr [rsp+0E8h+var_58], eax
0x18000564d  jnz     loc_1800057A5
0x180005653  mov     [rsp+0E8h+var_60], r13
0x18000565b  mov     eax, [rsp+0E8h+arg_30]
0x180005662  mov     dword ptr [rsp+0E8h+Size], eax
0x180005666  test    rbx, rbx
0x180005669  jnz     loc_1800057B6
0x18000566f  mov     eax, 8
0x180005674  mov     rcx, [r14+18h]
0x180005678  lea     rdx, [rsp+0E8h+Size]
0x18000567d  mov     [rsp+0E8h+var_A8], rdx; __int64
0x180005682  lea     rdx, [rsp+0E8h+Src]
0x180005687  mov     [rsp+0E8h+var_B0], rdx; __int64
0x18000568c  lea     rdx, [rsp+0E8h+Size+4]
0x180005691  mov     [rsp+0E8h+var_B8], rdx; __int64
0x180005696  mov     [rsp+0E8h+var_C0], eax; int
0x18000569a  mov     [rsp+0E8h+var_C8], r15d; int
0x18000569f  mov     r9, r12; int
0x1800056a2  lea     r8, [rsp+0E8h+var_68]; int
0x1800056aa  mov     edx, [r14+20h]; int
0x1800056ae  mov     rcx, [rcx+70h]; int
0x1800056b2  call    CalRpcTransmit
0x1800056b7  mov     r14d, eax
0x1800056ba  mov     [rsp+0E8h+var_98], eax
0x1800056be  test    eax, eax
0x1800056c0  jnz     loc_1800057E0
0x1800056c6  test    rbx, rbx
0x1800056c9  jnz     loc_1800057F5
0x1800056cf  mov     esi, dword ptr [rsp+0E8h+Size]
0x1800056d3  mov     r13, [rsp+0E8h+Src]
0x1800056d8  mov     rbx, [rsp+0E8h+arg_28]
0x1800056e0  cmp     [rbx+14h], esi
0x1800056e3  jnb     loc_1800057BE
0x1800056e9  mov     ecx, esi; unsigned __int64
0x1800056eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800056f0  mov     r15, rax
0x1800056f3  test    rax, rax
0x1800056f6  jz      loc_180005845
0x1800056fc  mov     rcx, [rbx+8]; void *
0x180005700  test    rcx, rcx
0x180005703  jz      short loc_18000570A
0x180005705  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000570a  mov     [rbx+8], r15
0x18000570e  mov     [rbx+14h], esi
0x180005711  mov     dword ptr [rbx+10h], 0
0x180005718  test    esi, esi
0x18000571a  jz      short loc_18000572A
0x18000571c  mov     r8, rsi; Size
0x18000571f  mov     rdx, r13; Src
0x180005722  mov     rcx, r15; void *
0x180005725  call    memcpy_0
0x18000572a  mov     [rbx+10h], esi
0x18000572d  test    rdi, rdi
0x180005730  jz      short loc_18000573B
0x180005732  mov     rcx, rdi; this
0x180005735  call    ?ReleaseSubcontext@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::ReleaseSubcontext(void)
0x18000573a  nop
0x18000573b  mov     rbx, [rsp+0E8h+Src]
0x180005740  test    rbx, rbx
0x180005743  jz      short loc_180005759
0x180005745  call    cs:__imp_GetProcessHeap
0x18000574b  mov     rcx, rax; hHeap
0x18000574e  mov     r8, rbx; lpMem
0x180005751  xor     edx, edx; dwFlags
0x180005753  call    cs:__imp_HeapFree
0x180005759  mov     rbx, qword ptr [rsp+0E8h+Size+4]
0x18000575e  test    rbx, rbx
0x180005761  jz      short loc_180005789
0x180005763  mov     rcx, [rbx+8]; void *
0x180005767  test    rcx, rcx
0x18000576a  jnz     loc_18000586B
0x180005770  test    rbx, rbx
0x180005773  jz      short loc_180005789
0x180005775  call    cs:__imp_GetProcessHeap
0x18000577b  mov     rcx, rax; hHeap
0x18000577e  mov     r8, rbx; lpMem
0x180005781  xor     edx, edx; dwFlags
0x180005783  call    cs:__imp_HeapFree
0x180005789  test    r14d, r14d
0x18000578c  jnz     loc_18000587A
0x180005792  add     rsp, 0B0h
0x180005799  pop     r15
0x18000579b  pop     r14
0x18000579d  pop     r13
0x18000579f  pop     r12
0x1800057a1  pop     rdi
0x1800057a2  pop     rsi
0x1800057a3  pop     rbx
0x1800057a4  retn
0x1800057a5  lea     rax, [rcx+8]
0x1800057a9  mov     [rsp+0E8h+var_60], rax
0x1800057b1  jmp     loc_18000565B
0x1800057b6  mov     eax, [rbx+4]
0x1800057b9  jmp     loc_180005674
0x1800057be  mov     r15, [rbx+8]
0x1800057c2  jmp     loc_180005711
0x1800057c7  mov     [rsp+0E8h+pExceptionObject], 80100004h
0x1800057cf  lea     rdx, _TI1K; pThrowInfo
0x1800057d6  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1800057db  call    _CxxThrowException_0
0x1800057e0  mov     [rsp+0E8h+var_84], eax
0x1800057e4  lea     rdx, _TI1K; pThrowInfo
0x1800057eb  lea     rcx, [rsp+0E8h+var_84]; pExceptionObject
0x1800057f0  call    _CxxThrowException_0
0x1800057f5  mov     rdx, qword ptr [rsp+0E8h+Size+4]
0x1800057fa  mov     ecx, [rdx+10h]
0x1800057fd  add     rcx, 8
0x180005801  mov     eax, [rbx+4]
0x180005804  cmp     rax, rcx
0x180005807  jnb     short loc_180005822
0x180005809  mov     [rsp+0E8h+var_80], 80100019h
0x180005811  lea     rdx, _TI1K; pThrowInfo
0x180005818  lea     rcx, [rsp+0E8h+var_80]; pExceptionObject
0x18000581d  call    _CxxThrowException_0
0x180005822  mov     eax, [rdx]
0x180005824  mov     [rbx], eax
0x180005826  mov     eax, [rdx+10h]
0x180005829  add     eax, 8
0x18000582c  mov     [rbx+4], eax
0x18000582f  mov     r8d, [rdx+10h]; Size
0x180005833  lea     rcx, [rbx+8]; void *
0x180005837  mov     rdx, [rdx+8]; Src
0x18000583b  call    memcpy_0
0x180005840  jmp     loc_1800056CF
0x180005845  mov     [rsp+0E8h+var_7C], 0Eh
0x18000584d  lea     rdx, _TI1K; pThrowInfo
0x180005854  lea     rcx, [rsp+0E8h+var_7C]; pExceptionObject
0x180005859  call    _CxxThrowException_0
0x18000585f  jmp     short $+2
0x180005861  mov     r14d, [rsp+0E8h+var_98]
0x180005866  jmp     loc_18000573B
0x18000586b  call    MIDL_user_free
0x180005870  mov     rbx, qword ptr [rsp+0E8h+Size+4]
0x180005875  jmp     loc_180005770
0x18000587a  mov     [rsp+0E8h+var_78], r14d
0x18000587f  lea     rdx, _TI1K; pThrowInfo
0x180005886  lea     rcx, [rsp+0E8h+var_78]; pExceptionObject
0x18000588b  call    _CxxThrowException_0
```

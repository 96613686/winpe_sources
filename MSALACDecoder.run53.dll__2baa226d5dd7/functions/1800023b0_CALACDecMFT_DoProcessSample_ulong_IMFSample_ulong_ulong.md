# CALACDecMFT::DoProcessSample(ulong,IMFSample * *,ulong *,ulong *)

- ea: `0x1800023b0`
- end: `0x18000286e`
- name: `?DoProcessSample@CALACDecMFT@@MEAAJKPEAPEAUIMFSample@@PEAK1@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CALACDecMFT *this, int, struct IMFSample **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001104`
- `0x180001144`
- `0x180001150`
- `0x180001574`
- `0x180001e62`
- `0x180001eac`
- `0x1800023b0`
- `0x180007798`
- `0x180009f88`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180002794`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800027ab`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180002794`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800027ab`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800025d3`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800025d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CALACDecMFT::DoProcessSample(
        CALACDecMFT *this,
        int a2,
        struct IMFSample **a3,
        unsigned int *a4,
        unsigned int *a5)
{
  char *v8; // r12
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  _QWORD *v11; // rax
  void *v12; // rdi
  HRESULT v13; // ebx
  unsigned __int64 v14; // r15
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64 *); // r13
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  IMFMediaBuffer *v19; // rcx
  const void *v20; // rcx
  const void *v21; // rcx
  unsigned __int64 v22; // r15
  char *v23; // rax
  int v24; // edx
  unsigned __int64 v25; // r13
  const void *v26; // rax
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // rcx
  IMFMediaBuffer *v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // [rsp+30h] [rbp-50h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-48h] BYREF
  int v34; // [rsp+40h] [rbp-40h] BYREF
  __int64 v35; // [rsp+48h] [rbp-38h] BYREF
  const void *v36; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-28h]
  unsigned int v38; // [rsp+5Ch] [rbp-24h] BYREF
  unsigned __int64 v39; // [rsp+60h] [rbp-20h]
  __int64 v40; // [rsp+68h] [rbp-18h] BYREF
  __int64 v41; // [rsp+70h] [rbp-10h] BYREF
  size_t Size; // [rsp+C8h] [rbp+48h] BYREF
  struct IMFSample **v43; // [rsp+D0h] [rbp+50h]
  unsigned int *v44; // [rsp+D8h] [rbp+58h]

  v44 = a4;
  v43 = a3;
  if ( a2 )
    return 2147942487LL;
  v35 = 0;
  ppBuffer = 0;
  v8 = 0;
  v9 = operator new(0x10u);
  v10 = v9;
  v39 = (unsigned __int64)v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = 0;
  }
  else
  {
    v10 = 0;
  }
  v11 = operator new(0x10u);
  v12 = v11;
  v39 = (unsigned __int64)v11;
  if ( v11 )
  {
    *v11 = 0;
    v11[1] = 0;
  }
  else
  {
    v12 = 0;
  }
  if ( v10 && v12 )
  {
    v37 = *((_DWORD *)this + 50);
    v38 = v37;
    LODWORD(Size) = 0;
    v40 = 0;
    v41 = 0;
    v14 = *((unsigned int *)this + 48) * (unsigned __int64)*((unsigned int *)this + 49);
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_42;
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 9) + 280LL))(*((_QWORD *)this + 9), &v40);
    if ( v13 < 0 )
      goto LABEL_43;
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64))(*a3)->lpVtbl->SetSampleTime)(*a3, v40);
    if ( v13 < 0 )
      goto LABEL_43;
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 9) + 296LL))(*((_QWORD *)this + 9), &v41);
    if ( v13 < 0 )
      goto LABEL_43;
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64))(*a3)->lpVtbl->SetSampleDuration)(*a3, v41);
    if ( v13 < 0 )
      goto LABEL_43;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*a3)->lpVtbl->SetSampleFlags)(*a3, 0);
    if ( v13 < 0 )
      goto LABEL_43;
    v15 = *((_QWORD *)this + 9);
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 328LL);
    v17 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v13 = v16(v15, &v35);
    if ( v13 < 0 )
      goto LABEL_43;
    v13 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v35 + 40LL))(v35, &Size);
    if ( v13 < 0 )
      goto LABEL_43;
    v39 = (unsigned int)v14;
    v18 = v37 * (unsigned __int64)(unsigned int)v14;
    if ( v18 > 0xFFFFFFFF )
    {
LABEL_42:
      v13 = -2147024362;
      goto LABEL_43;
    }
    v19 = ppBuffer;
    if ( ppBuffer )
    {
      ppBuffer = 0;
      ((void (__fastcall *)(IMFMediaBuffer *))v19->lpVtbl->Release)(v19);
    }
    v13 = MFCreateMemoryBuffer(v18, &ppBuffer);
    if ( v13 < 0 )
      goto LABEL_43;
    v32 = 0;
    v34 = 0;
    v36 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, const void **, unsigned int *, int *))(*(_QWORD *)v35 + 24LL))(
            v35,
            &v36,
            &v32,
            &v34);
    if ( v13 < 0 )
      goto LABEL_43;
    v20 = v36;
    *v10 = v32;
    v10[1] = v20;
    v32 = 0;
    v34 = 0;
    v36 = 0;
    v13 = ((__int64 (__fastcall *)(IMFMediaBuffer *, const void **, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v36,
            &v32,
            &v34);
    if ( v13 < 0 )
      goto LABEL_43;
    v21 = v36;
    *(_QWORD *)v12 = v32;
    *((_QWORD *)v12 + 1) = v21;
    v22 = (unsigned int)(Size + 4);
    v23 = (char *)operator new[](v22);
    v8 = v23;
    if ( v23 )
    {
      memset_0(v23, 0, (unsigned int)v22);
      v24 = Size;
      v25 = (unsigned int)Size;
      if ( !(_DWORD)Size )
      {
LABEL_33:
        v27 = v24 + 4;
        v28 = *((_QWORD *)this + 23);
        *(_QWORD *)v28 = v8;
        *(_QWORD *)(v28 + 8) = &v8[v27];
        *(_DWORD *)(v28 + 16) = 0;
        *(_DWORD *)(v28 + 20) = v27;
        if ( !(unsigned int)ALACDecoder::Decode(
                              *((ALACDecoder **)this + 22),
                              *((_QWORD *)this + 23),
                              *((unsigned __int8 **)v12 + 1),
                              v37,
                              *((_DWORD *)this + 48),
                              &v38) )
        {
          v13 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                  ppBuffer,
                  v38 * (unsigned int)v39);
          if ( v13 >= 0 )
          {
            v13 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))(*v43)->lpVtbl->AddBuffer)(
                    *v43,
                    ppBuffer);
            if ( v13 >= 0 )
            {
              *a5 = 0;
              *v44 = 0;
            }
          }
        }
        goto LABEL_43;
      }
      v26 = (const void *)v10[1];
      v36 = v26;
      if ( v26 && v22 >= (unsigned int)Size )
      {
        memcpy_0(v8, v26, (unsigned int)Size);
        v24 = Size;
        goto LABEL_33;
      }
      memset_0(v8, 0, v22);
      if ( !v36 )
      {
        *(_DWORD *)_o__errno() = 22;
LABEL_41:
        invalid_parameter_noinfo();
        goto LABEL_10;
      }
      if ( v22 < v25 )
      {
        *(_DWORD *)_o__errno() = 34;
        goto LABEL_41;
      }
    }
  }
LABEL_10:
  v13 = -2147024882;
LABEL_43:
  v29 = *((_QWORD *)this + 9);
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    *((_QWORD *)this + 9) = 0;
  }
  if ( v10 )
    operator delete(v10);
  if ( v12 )
    operator delete(v12);
  if ( v8 )
    operator delete(v8);
  v30 = ppBuffer;
  if ( ppBuffer )
  {
    ppBuffer = 0;
    ((void (__fastcall *)(IMFMediaBuffer *))v30->lpVtbl->Release)(v30);
  }
  v31 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800023b0  mov     [rsp-38h+arg_0], rbx
0x1800023b5  mov     [rsp-38h+arg_18], r9
0x1800023ba  mov     [rsp-38h+arg_10], r8
0x1800023bf  push    rbp
0x1800023c0  push    rsi
0x1800023c1  push    rdi
0x1800023c2  push    r12
0x1800023c4  push    r13
0x1800023c6  push    r14
0x1800023c8  push    r15
0x1800023ca  mov     rbp, rsp
0x1800023cd  sub     rsp, 80h
0x1800023d4  mov     r13, r8
0x1800023d7  mov     r14, rcx
0x1800023da  test    edx, edx
0x1800023dc  jz      short loc_1800023E8
0x1800023de  mov     eax, 80070057h
0x1800023e3  jmp     loc_180002853
0x1800023e8  mov     [rbp+var_38], 0
0x1800023f0  mov     [rbp+ppBuffer], 0
0x1800023f8  xor     r12d, r12d
0x1800023fb  lea     ecx, [r12+10h]; Size
0x180002400  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002405  mov     rsi, rax
0x180002408  mov     [rbp+var_20], rax
0x18000240c  test    rax, rax
0x18000240f  jz      short loc_18000241A
0x180002411  mov     [rax], r12
0x180002414  mov     [rax+8], r12
0x180002418  jmp     short loc_18000241C
0x18000241a  xor     esi, esi
0x18000241c  mov     ecx, 10h; Size
0x180002421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002426  mov     rdi, rax
0x180002429  mov     [rbp+var_20], rax
0x18000242d  test    rax, rax
0x180002430  jz      short loc_18000243B
0x180002432  mov     [rax], r12
0x180002435  mov     [rax+8], r12
0x180002439  jmp     short loc_18000243D
0x18000243b  xor     edi, edi
0x18000243d  test    rsi, rsi
0x180002440  jnz     short loc_18000244C
0x180002442  mov     ebx, 8007000Eh
0x180002447  jmp     loc_1800027C6
0x18000244c  test    rdi, rdi
0x18000244f  jz      short loc_180002442
0x180002451  mov     eax, [r14+0C8h]
0x180002458  mov     [rbp+var_28], eax
0x18000245b  mov     [rbp+var_24], eax
0x18000245e  mov     dword ptr [rbp+Size], r12d
0x180002462  mov     [rbp+var_18], r12
0x180002466  mov     [rbp+var_10], r12
0x18000246a  mov     r15d, [r14+0C4h]
0x180002471  mov     eax, [r14+0C0h]
0x180002478  imul    r15, rax
0x18000247c  mov     eax, 0FFFFFFFFh
0x180002481  cmp     r15, rax
0x180002484  ja      loc_1800027C1
0x18000248a  mov     rcx, [r14+48h]
0x18000248e  mov     rax, [rcx]
0x180002491  lea     rdx, [rbp+var_18]
0x180002495  mov     rax, [rax+118h]
0x18000249c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a1  mov     ebx, eax
0x1800024a3  test    eax, eax
0x1800024a5  js      loc_1800027C6
0x1800024ab  mov     rcx, [r13+0]
0x1800024af  mov     rax, [rcx]
0x1800024b2  mov     rdx, [rbp+var_18]
0x1800024b6  mov     rax, [rax+120h]
0x1800024bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c2  mov     ebx, eax
0x1800024c4  test    eax, eax
0x1800024c6  js      loc_1800027C6
0x1800024cc  mov     rcx, [r14+48h]
0x1800024d0  mov     rax, [rcx]
0x1800024d3  lea     rdx, [rbp+var_10]
0x1800024d7  mov     rax, [rax+128h]
0x1800024de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e3  mov     ebx, eax
0x1800024e5  test    eax, eax
0x1800024e7  js      loc_1800027C6
0x1800024ed  mov     rcx, [r13+0]
0x1800024f1  mov     rax, [rcx]
0x1800024f4  mov     rdx, [rbp+var_10]
0x1800024f8  mov     rax, [rax+130h]
0x1800024ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002504  mov     ebx, eax
0x180002506  test    eax, eax
0x180002508  js      loc_1800027C6
0x18000250e  mov     rcx, [r13+0]
0x180002512  mov     rax, [rcx]
0x180002515  xor     edx, edx
0x180002517  mov     rax, [rax+110h]
0x18000251e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002523  mov     ebx, eax
0x180002525  test    eax, eax
0x180002527  js      loc_1800027C6
0x18000252d  mov     rbx, [r14+48h]
0x180002531  mov     rax, [rbx]
0x180002534  mov     r13, [rax+148h]
0x18000253b  mov     rcx, [rbp+var_38]
0x18000253f  test    rcx, rcx
0x180002542  jz      short loc_180002559
0x180002544  mov     [rbp+var_38], 0
0x18000254c  mov     rax, [rcx]
0x18000254f  mov     rax, [rax+10h]
0x180002553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002558  nop
0x180002559  lea     rdx, [rbp+var_38]
0x18000255d  mov     rcx, rbx
0x180002560  mov     rax, r13
0x180002563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002568  mov     ebx, eax
0x18000256a  test    eax, eax
0x18000256c  js      loc_1800027C6
0x180002572  mov     rcx, [rbp+var_38]
0x180002576  mov     rax, [rcx]
0x180002579  lea     rdx, [rbp+Size]
0x18000257d  mov     rax, [rax+28h]
0x180002581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002586  mov     ebx, eax
0x180002588  test    eax, eax
0x18000258a  js      loc_1800027C6
0x180002590  mov     eax, r15d
0x180002593  mov     [rbp+var_20], rax
0x180002597  mov     ebx, r15d
0x18000259a  mov     eax, [rbp+var_28]
0x18000259d  imul    rbx, rax
0x1800025a1  mov     eax, 0FFFFFFFFh
0x1800025a6  cmp     rbx, rax
0x1800025a9  ja      loc_1800027C1
0x1800025af  mov     rcx, [rbp+ppBuffer]
0x1800025b3  test    rcx, rcx
0x1800025b6  jz      short loc_1800025CD
0x1800025b8  mov     [rbp+ppBuffer], 0
0x1800025c0  mov     rax, [rcx]
0x1800025c3  mov     rax, [rax+10h]
0x1800025c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025cc  nop
0x1800025cd  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800025d1  mov     ecx, ebx; cbMaxLength
0x1800025d3  call    cs:__imp_MFCreateMemoryBuffer
0x1800025d9  mov     ebx, eax
0x1800025db  test    eax, eax
0x1800025dd  js      loc_1800027C6
0x1800025e3  mov     rcx, [rbp+var_38]
0x1800025e7  mov     [rbp+var_50], 0
0x1800025ee  mov     [rbp+var_40], 0
0x1800025f5  mov     [rbp+var_30], 0
0x1800025fd  mov     rax, [rcx]
0x180002600  lea     r9, [rbp+var_40]
0x180002604  lea     r8, [rbp+var_50]
0x180002608  lea     rdx, [rbp+var_30]
0x18000260c  mov     rax, [rax+18h]
0x180002610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002615  mov     ebx, eax
0x180002617  test    eax, eax
0x180002619  js      loc_1800027C6
0x18000261f  mov     rcx, [rbp+var_30]
0x180002623  mov     eax, [rbp+var_50]
0x180002626  mov     [rsi], rax
0x180002629  mov     [rsi+8], rcx
0x18000262d  mov     rcx, [rbp+ppBuffer]
0x180002631  mov     [rbp+var_50], 0
0x180002638  mov     [rbp+var_40], 0
0x18000263f  mov     [rbp+var_30], 0
0x180002647  mov     rax, [rcx]
0x18000264a  lea     r9, [rbp+var_40]
0x18000264e  lea     r8, [rbp+var_50]
0x180002652  lea     rdx, [rbp+var_30]
0x180002656  mov     rax, [rax+18h]
0x18000265a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000265f  mov     ebx, eax
0x180002661  test    eax, eax
0x180002663  js      loc_1800027C6
0x180002669  mov     rcx, [rbp+var_30]
0x18000266d  mov     eax, [rbp+var_50]
0x180002670  mov     [rdi], rax
0x180002673  mov     [rdi+8], rcx
0x180002677  mov     eax, dword ptr [rbp+Size]
0x18000267a  add     eax, 4
0x18000267d  mov     r15d, eax
0x180002680  mov     ecx, eax; unsigned __int64
0x180002682  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002687  mov     r12, rax
0x18000268a  test    rax, rax
0x18000268d  jz      loc_180002442
0x180002693  mov     r8d, r15d; Size
0x180002696  xor     edx, edx; Val
0x180002698  mov     rcx, rax; void *
0x18000269b  call    memset_0
0x1800026a0  mov     edx, dword ptr [rbp+Size]
0x1800026a3  mov     r13d, edx
0x1800026a6  test    edx, edx
0x1800026a8  jz      short loc_1800026D5
0x1800026aa  mov     rax, [rsi+8]
0x1800026ae  mov     [rbp+var_30], rax
0x1800026b2  test    rax, rax
0x1800026b5  jz      loc_180002780
0x1800026bb  cmp     r15, rdx
0x1800026be  jb      loc_180002780
0x1800026c4  mov     r8d, edx; Size
0x1800026c7  mov     rdx, rax; Src
0x1800026ca  mov     rcx, r12; void *
0x1800026cd  call    memcpy_0
0x1800026d2  mov     edx, dword ptr [rbp+Size]
0x1800026d5  add     edx, 4
0x1800026d8  mov     rcx, [r14+0B8h]
0x1800026df  mov     [rcx], r12
0x1800026e2  mov     eax, edx
0x1800026e4  add     rax, r12
0x1800026e7  mov     [rcx+8], rax
0x1800026eb  mov     dword ptr [rcx+10h], 0
0x1800026f2  mov     [rcx+14h], edx
0x1800026f5  lea     rax, [rbp+var_24]
0x1800026f9  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800026fe  mov     eax, [r14+0C0h]
0x180002705  mov     [rsp+80h+var_60], eax; unsigned int
0x180002709  mov     r9d, [rbp+var_28]; unsigned int
0x18000270d  mov     r8, [rdi+8]; unsigned __int8 *
0x180002711  mov     rdx, [r14+0B8h]; struct BitBuffer *
0x180002718  mov     rcx, [r14+0B0h]; this
0x18000271f  call    ?Decode@ALACDecoder@@QEAAHPEAUBitBuffer@@PEAEIIPEAI@Z; ALACDecoder::Decode(BitBuffer *,uchar *,uint,uint,uint *)
0x180002724  test    eax, eax
0x180002726  jnz     loc_1800027C6
0x18000272c  mov     rcx, [rbp+ppBuffer]
0x180002730  mov     rax, [rcx]
0x180002733  mov     rdx, [rbp+var_20]
0x180002737  imul    edx, [rbp+var_24]
0x18000273b  mov     rax, [rax+30h]
0x18000273f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002744  mov     ebx, eax
0x180002746  test    eax, eax
0x180002748  js      short loc_1800027C6
0x18000274a  mov     rcx, [rbp+arg_10]
0x18000274e  mov     rcx, [rcx]
0x180002751  mov     rax, [rcx]
0x180002754  mov     rdx, [rbp+ppBuffer]
0x180002758  mov     rax, [rax+150h]
0x18000275f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002764  mov     ebx, eax
0x180002766  test    eax, eax
0x180002768  js      short loc_1800027C6
0x18000276a  mov     rax, [rbp+arg_20]
0x18000276e  mov     dword ptr [rax], 0
0x180002774  mov     rax, [rbp+arg_18]
0x180002778  mov     dword ptr [rax], 0
0x18000277e  jmp     short loc_1800027C6
0x180002780  mov     r8, r15; Size
0x180002783  xor     edx, edx; Val
0x180002785  mov     rcx, r12; void *
0x180002788  call    memset_0
0x18000278d  cmp     [rbp+var_30], 0
0x180002792  jnz     short loc_1800027A2
0x180002794  call    cs:__imp__o__errno
0x18000279a  mov     dword ptr [rax], 16h
0x1800027a0  jmp     short loc_1800027B7
0x1800027a2  cmp     r15, r13
0x1800027a5  jnb     loc_180002442
0x1800027ab  call    cs:__imp__o__errno
0x1800027b1  mov     dword ptr [rax], 22h ; '"'
0x1800027b7  call    _invalid_parameter_noinfo
0x1800027bc  jmp     loc_180002442
0x1800027c1  mov     ebx, 80070216h
0x1800027c6  mov     rcx, [r14+48h]
0x1800027ca  test    rcx, rcx
0x1800027cd  jz      short loc_1800027E3
0x1800027cf  mov     rax, [rcx]
0x1800027d2  mov     rax, [rax+10h]
0x1800027d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027db  mov     qword ptr [r14+48h], 0
0x1800027e3  test    rsi, rsi
0x1800027e6  jz      short loc_1800027F5
0x1800027e8  mov     edx, 10h
0x1800027ed  mov     rcx, rsi; Block
0x1800027f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800027f5  test    rdi, rdi
0x1800027f8  jz      short loc_180002807
0x1800027fa  mov     edx, 10h
0x1800027ff  mov     rcx, rdi; Block
0x180002802  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002807  test    r12, r12
0x18000280a  jz      short loc_180002815
0x18000280c  mov     rcx, r12; Block
0x18000280f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002814  nop
0x180002815  mov     rcx, [rbp+ppBuffer]
0x180002819  test    rcx, rcx
0x18000281c  jz      short loc_180002833
0x18000281e  mov     [rbp+ppBuffer], 0
0x180002826  mov     rax, [rcx]
0x180002829  mov     rax, [rax+10h]
0x18000282d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002832  nop
0x180002833  mov     rcx, [rbp+var_38]
0x180002837  test    rcx, rcx
0x18000283a  jz      short loc_180002851
0x18000283c  mov     [rbp+var_38], 0
  ... truncated ...
```

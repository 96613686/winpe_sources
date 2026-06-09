# CCastableCommandQueue::UMCreateHWQueueForUserModeSubmission_Callback(D3D12DDI_HRTCOMMANDQUEUE,D3D12DDICB_CREATEHWQUEUEFORUSERMODESUBMISSION_0123 *)

- ea: `0x18012e0b0`
- end: `0x18012e442`
- name: `?UMCreateHWQueueForUserModeSubmission_Callback@CCastableCommandQueue@@SAJUD3D12DDI_HRTCOMMANDQUEUE@@PEAUD3D12DDICB_CREATEHWQUEUEFORUSERMODESUBMISSION_0123@@@Z`
- size: `914`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003e68`
- `0x180004600`
- `0x180004da4`
- `0x180004fa8`
- `0x18000b920`
- `0x18007efa0`
- `0x18007f054`
- `0x1800a9f98`
- `0x1800abcc0`
- `0x1800b97e8`
- `0x1800b9808`
- `0x1800bb480`
- `0x1800bc094`
- `0x180119998`
- `0x18012e0b0`

## string_xrefs

- `0x18012e191`: `Cannot mix HwQueue scheduling with context scheduling. This command queue does not own the HwQueue's requested context, but owns software contexts.`
- `0x18012e16a`: `Driver targeted HwQueue against scheduling group that this command queue does not belong to.`
- `0x18012e17a`: `Cannot create UMS HwQueue against context without HwQueueSupported flag.`
- `0x18012e119`: `CreateHwQueueForUserModeSubmissionCb called outside of queue creation.`
- `0x18012e0ed`: `Reserved flags given to CreateHwQueueForUserModeSubmissionCb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCastableCommandQueue::UMCreateHWQueueForUserModeSubmission_Callback(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4)
{
  const char *v6; // r8
  __int64 result; // rax
  CJournal *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r14
  __int64 v11; // rax
  const char *v12; // r8
  NDXGI::CHwQueue *v13; // rax
  unsigned int v14; // ebx
  NDXGI::CHwQueue *v15; // [rsp+30h] [rbp-1E8h] BYREF
  NDXGI::CHwQueue *v16; // [rsp+38h] [rbp-1E0h] BYREF
  _Smtx_t *v17; // [rsp+40h] [rbp-1D8h]
  __int64 v18; // [rsp+48h] [rbp-1D0h]
  _com_error *v19; // [rsp+50h] [rbp-1C8h] BYREF
  int v20; // [rsp+60h] [rbp-1B8h] BYREF
  int v21; // [rsp+64h] [rbp-1B4h]
  int v22; // [rsp+68h] [rbp-1B0h]
  int v23; // [rsp+6Ch] [rbp-1ACh]
  __int128 v24; // [rsp+70h] [rbp-1A8h]
  __int128 v25; // [rsp+80h] [rbp-198h]
  __int128 v26; // [rsp+90h] [rbp-188h]
  __int128 v27; // [rsp+A0h] [rbp-178h]
  __int128 v28; // [rsp+B0h] [rbp-168h]
  __int128 v29; // [rsp+C0h] [rbp-158h]
  __int128 v30; // [rsp+D0h] [rbp-148h]
  __int128 v31; // [rsp+E0h] [rbp-138h]
  __int64 v32; // [rsp+F8h] [rbp-120h]
  int v33; // [rsp+100h] [rbp-118h]
  __int128 v34; // [rsp+108h] [rbp-110h]
  __int128 v35; // [rsp+118h] [rbp-100h]
  __int128 v36; // [rsp+128h] [rbp-F0h]
  __int64 v37; // [rsp+138h] [rbp-E0h]
  __int64 v38; // [rsp+140h] [rbp-D8h]
  __int128 v39; // [rsp+148h] [rbp-D0h]
  __int128 v40; // [rsp+158h] [rbp-C0h]
  __int128 v41; // [rsp+168h] [rbp-B0h]
  __int128 v42; // [rsp+178h] [rbp-A0h]
  __int128 v43; // [rsp+188h] [rbp-90h]
  __int64 v44; // [rsp+198h] [rbp-80h]

  a2[19] = 0;
  if ( *((_DWORD *)a2 + 2) >= 0x40u )
  {
    v6 = "Reserved flags given to CreateHwQueueForUserModeSubmissionCb";
LABEL_3:
    CJournal::RecordJournal(a1, -2147024809, (__int64)v6, a4, 0);
    return 2147942487LL;
  }
  if ( !CCastableCommandQueue::IsCreationThread((CCastableCommandQueue *)a1) )
  {
    v6 = "CreateHwQueueForUserModeSubmissionCb called outside of queue creation.";
    goto LABEL_3;
  }
  memset_0(&v20, 0, 0x180u);
  v10 = *a2;
  v11 = *(_QWORD *)(*a2 + 8);
  if ( v11 && v11 != a1 )
  {
    v12 = "Driver targeted HwQueue against context belonging to different queue.";
LABEL_10:
    CJournal::ReportDriverError(v8, -2147024809, v12, v9);
    return 2147942487LL;
  }
  v8 = *(CJournal **)(v10 + 16);
  if ( v8 && v8 != *(CJournal **)(a1 + 472) )
  {
    v12 = "Driver targeted HwQueue against scheduling group that this command queue does not belong to.";
    goto LABEL_10;
  }
  if ( (*(_BYTE *)(v10 + 76) & 0x10) == 0 )
  {
    v12 = "Cannot create UMS HwQueue against context without HwQueueSupported flag.";
    goto LABEL_10;
  }
  if ( v11 != a1 )
  {
    if ( *(_BYTE *)(a1 + 501) )
    {
      v12 = "Cannot mix HwQueue scheduling with context scheduling. This command queue does not own the HwQueue's request"
            "ed context, but owns software contexts.";
      goto LABEL_10;
    }
    *(_BYTE *)(a1 + 502) = 1;
  }
  v20 = *(_DWORD *)(v10 + 24);
  v21 = *((_DWORD *)a2 + 2);
  v22 = *((_DWORD *)a2 + 3);
  v23 = *((_DWORD *)a2 + 4);
  v24 = *(_OWORD *)((char *)a2 + 20);
  v25 = *(_OWORD *)((char *)a2 + 36);
  v26 = *(_OWORD *)((char *)a2 + 52);
  v27 = *(_OWORD *)((char *)a2 + 68);
  v28 = *(_OWORD *)((char *)a2 + 84);
  v29 = *(_OWORD *)((char *)a2 + 100);
  v30 = *(_OWORD *)((char *)a2 + 116);
  v31 = *(_OWORD *)((char *)a2 + 132);
  v17 = (_Smtx_t *)(v10 + 88);
  v18 = v10 + 88;
  Smtx_lock_exclusive((_Smtx_t *)(v10 + 88));
  try
  {
    std::vector<std::unique_ptr<NDXGI::CHwQueue,CCastableCommandQueue::HwQueueRemoveFromContext>>::reserve(
      a1 + 512,
      ((__int64)(*(_QWORD *)(a1 + 520) - *(_QWORD *)(a1 + 512)) >> 3) + 1);
    std::vector<std::unique_ptr<NDXGI::CHwQueue>>::reserve(
      v10 + 96,
      ((__int64)(*(_QWORD *)(v10 + 104) - *(_QWORD *)(v10 + 96)) >> 3) + 1);
    v13 = (NDXGI::CHwQueue *)operator new(0xC8u);
    v16 = v13;
    if ( v13 )
      v13 = (NDXGI::CHwQueue *)NDXGI::CHwQueue::CHwQueue(
                                 v13,
                                 (struct NDXGI::CContext *)v10,
                                 (struct _D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *)&v20,
                                 (struct CCastableCommandQueue *)a1);
    v15 = v13;
    a2[19] = (__int64)v13;
    v16 = v13;
    std::vector<std::unique_ptr<NDXGI::CHwQueue,CCastableCommandQueue::HwQueueRemoveFromContext>>::emplace_back<NDXGI::CHwQueue *>(
      a1 + 512,
      &v16);
    std::vector<std::unique_ptr<NDXGI::CHwQueue>>::push_back(v10 + 96, &v15);
    *((_DWORD *)a2 + 2) = v21;
    *(_OWORD *)((char *)a2 + 20) = v24;
    *(_OWORD *)((char *)a2 + 36) = v25;
    *(_OWORD *)((char *)a2 + 52) = v26;
    *(_OWORD *)((char *)a2 + 68) = v27;
    *(_OWORD *)((char *)a2 + 84) = v28;
    *(_OWORD *)((char *)a2 + 100) = v29;
    *(_OWORD *)((char *)a2 + 116) = v30;
    *(_OWORD *)((char *)a2 + 132) = v31;
    a2[20] = v32;
    *((_DWORD *)a2 + 42) = v33;
    *((_OWORD *)a2 + 11) = v34;
    *((_OWORD *)a2 + 12) = v35;
    *((_OWORD *)a2 + 13) = v36;
    a2[28] = v37;
    a2[29] = v38;
    *((_OWORD *)a2 + 15) = v39;
    *((_OWORD *)a2 + 16) = v40;
    *((_OWORD *)a2 + 17) = v41;
    *((_OWORD *)a2 + 18) = v42;
    *((_OWORD *)a2 + 19) = v43;
    a2[40] = v44;
    std::unique_ptr<NDXGI::CHwQueue>::~unique_ptr<NDXGI::CHwQueue>(&v15);
    Smtx_unlock_exclusive((_Smtx_t *)(v10 + 88));
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    v14 = -2147024882;
    goto LABEL_24;
  }
  catch ( _com_error *v19 )
  {
    LODWORD(v15) = *((_DWORD *)v19 + 2);
    v14 = (unsigned int)v15;
LABEL_24:
    Smtx_unlock_exclusive(v17);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x18012e0b0  mov     [rsp+arg_10], rbx
0x18012e0b5  push    rsi
0x18012e0b6  push    rdi
0x18012e0b7  push    r13
0x18012e0b9  push    r14
0x18012e0bb  push    r15
0x18012e0bd  sub     rsp, 1F0h
0x18012e0c4  mov     rax, cs:__security_cookie
0x18012e0cb  xor     rax, rsp
0x18012e0ce  mov     [rsp+218h+var_38], rax
0x18012e0d6  mov     rsi, rdx
0x18012e0d9  mov     rbx, rcx
0x18012e0dc  mov     qword ptr [rdx+98h], 0
0x18012e0e7  cmp     dword ptr [rdx+8], 40h ; '@'
0x18012e0eb  jb      short loc_18012E110
0x18012e0ed  lea     r8, aReservedFlagsG_10; "Reserved flags given to CreateHwQueueFo"...
0x18012e0f4  mov     [rsp+218h+var_1F8], 0
0x18012e0fc  mov     edx, 80070057h
0x18012e101  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18012e106  mov     eax, 80070057h
0x18012e10b  jmp     loc_18012E41A
0x18012e110  call    ?IsCreationThread@CCastableCommandQueue@@IEBA_NXZ; CCastableCommandQueue::IsCreationThread(void)
0x18012e115  test    al, al
0x18012e117  jnz     short loc_18012E122
0x18012e119  lea     r8, aCreatehwqueuef_0; "CreateHwQueueForUserModeSubmissionCb ca"...
0x18012e120  jmp     short loc_18012E0F4
0x18012e122  xor     edx, edx; Val
0x18012e124  mov     r8d, 180h; Size
0x18012e12a  lea     rcx, [rsp+218h+var_1B8]; void *
0x18012e12f  call    memset_0
0x18012e134  mov     r14, [rsi]
0x18012e137  mov     rax, [r14+8]
0x18012e13b  test    rax, rax
0x18012e13e  jz      short loc_18012E158
0x18012e140  cmp     rax, rbx
0x18012e143  jz      short loc_18012E158
0x18012e145  lea     r8, aDriverTargeted_0; "Driver targeted HwQueue against context"...
0x18012e14c  mov     edx, 80070057h; int
0x18012e151  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18012e156  jmp     short loc_18012E106
0x18012e158  mov     rcx, [r14+10h]
0x18012e15c  test    rcx, rcx
0x18012e15f  jz      short loc_18012E173
0x18012e161  cmp     rcx, [rbx+1D8h]
0x18012e168  jz      short loc_18012E173
0x18012e16a  lea     r8, aDriverTargeted; "Driver targeted HwQueue against schedul"...
0x18012e171  jmp     short loc_18012E14C
0x18012e173  test    byte ptr [r14+4Ch], 10h
0x18012e178  jnz     short loc_18012E183
0x18012e17a  lea     r8, aCannotCreateUm; "Cannot create UMS HwQueue against conte"...
0x18012e181  jmp     short loc_18012E14C
0x18012e183  cmp     rax, rbx
0x18012e186  jz      short loc_18012E1A1
0x18012e188  cmp     byte ptr [rbx+1F5h], 0
0x18012e18f  jz      short loc_18012E19A
0x18012e191  lea     r8, aCannotMixHwque; "Cannot mix HwQueue scheduling with cont"...
0x18012e198  jmp     short loc_18012E14C
0x18012e19a  mov     byte ptr [rbx+1F6h], 1
0x18012e1a1  mov     eax, [r14+18h]
0x18012e1a5  mov     [rsp+218h+var_1B8], eax
0x18012e1a9  mov     eax, [rsi+8]
0x18012e1ac  mov     [rsp+218h+var_1B4], eax
0x18012e1b0  mov     eax, [rsi+0Ch]
0x18012e1b3  mov     [rsp+218h+var_1B0], eax
0x18012e1b7  mov     eax, [rsi+10h]
0x18012e1ba  mov     [rsp+218h+var_1AC], eax
0x18012e1be  movups  xmm0, xmmword ptr [rsi+14h]
0x18012e1c2  movaps  [rsp+218h+var_1A8], xmm0
0x18012e1c7  movups  xmm1, xmmword ptr [rsi+24h]
0x18012e1cb  movaps  [rsp+218h+var_198], xmm1
0x18012e1d3  movups  xmm0, xmmword ptr [rsi+34h]
0x18012e1d7  movaps  [rsp+218h+var_188], xmm0
0x18012e1df  movups  xmm1, xmmword ptr [rsi+44h]
0x18012e1e3  movaps  [rsp+218h+var_178], xmm1
0x18012e1eb  movups  xmm0, xmmword ptr [rsi+54h]
0x18012e1ef  movaps  [rsp+218h+var_168], xmm0
0x18012e1f7  movups  xmm1, xmmword ptr [rsi+64h]
0x18012e1fb  movaps  [rsp+218h+var_158], xmm1
0x18012e203  movups  xmm0, xmmword ptr [rsi+74h]
0x18012e207  movaps  [rsp+218h+var_148], xmm0
0x18012e20f  movups  xmm1, xmmword ptr [rsi+84h]
0x18012e216  movaps  [rsp+218h+var_138], xmm1
0x18012e21e  lea     rdi, [r14+58h]
0x18012e222  mov     [rsp+218h+var_1D8], rdi
0x18012e227  mov     [rsp+218h+var_1D0], rdi
0x18012e22c  mov     rcx, rdi; _Smtx_t *
0x18012e22f  call    _Smtx_lock_exclusive
0x18012e234  nop
0x18012e235  lea     r13, [rbx+200h]
0x18012e23c  mov     rdx, [r13+8]
0x18012e240  sub     rdx, [r13+0]
0x18012e244  sar     rdx, 3
0x18012e248  inc     rdx
0x18012e24b  mov     rcx, r13
0x18012e24e  call    ?reserve@?$vector@V?$unique_ptr@VCHwQueue@NDXGI@@UHwQueueRemoveFromContext@CCastableCommandQueue@@@std@@V?$allocator@V?$unique_ptr@VCHwQueue@NDXGI@@UHwQueueRemoveFromContext@CCastableCommandQueue@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::unique_ptr<NDXGI::CHwQueue,CCastableCommandQueue::HwQueueRemoveFromContext>>::reserve(unsigned __int64)
0x18012e253  lea     r15, [r14+60h]
0x18012e257  mov     rdx, [r15+8]
0x18012e25b  sub     rdx, [r15]
0x18012e25e  sar     rdx, 3
0x18012e262  inc     rdx
0x18012e265  mov     rcx, r15
0x18012e268  call    ?reserve@?$vector@V?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::unique_ptr<NDXGI::CHwQueue>>::reserve(unsigned __int64)
0x18012e26d  mov     ecx, 0C8h; dwBytes
0x18012e272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012e277  mov     [rsp+218h+var_1E0], rax
0x18012e27c  test    rax, rax
0x18012e27f  jz      short loc_18012E295
0x18012e281  mov     r9, rbx; struct CCastableCommandQueue *
0x18012e284  lea     r8, [rsp+218h+var_1B8]; struct _D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION *
0x18012e289  mov     rdx, r14; struct NDXGI::CContext *
0x18012e28c  mov     rcx, rax; this
0x18012e28f  call    ??0CHwQueue@NDXGI@@QEAA@PEAVCContext@1@AEAU_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION@@PEAVCCastableCommandQueue@@@Z; NDXGI::CHwQueue::CHwQueue(NDXGI::CContext *,_D3DKMT_CREATEHWQUEUEFORUSERMODESUBMISSION &,CCastableCommandQueue *)
0x18012e294  nop
0x18012e295  mov     [rsp+218h+var_1E8], rax
0x18012e29a  mov     [rsi+98h], rax
0x18012e2a1  mov     [rsp+218h+var_1E0], rax
0x18012e2a6  lea     rdx, [rsp+218h+var_1E0]
0x18012e2ab  mov     rcx, r13
0x18012e2ae  call    ??$emplace_back@PEAVCHwQueue@NDXGI@@@?$vector@V?$unique_ptr@VCHwQueue@NDXGI@@UHwQueueRemoveFromContext@CCastableCommandQueue@@@std@@V?$allocator@V?$unique_ptr@VCHwQueue@NDXGI@@UHwQueueRemoveFromContext@CCastableCommandQueue@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCHwQueue@NDXGI@@UHwQueueRemoveFromContext@CCastableCommandQueue@@@1@$$QEAPEAVCHwQueue@NDXGI@@@Z; std::vector<std::unique_ptr<NDXGI::CHwQueue,CCastableCommandQueue::HwQueueRemoveFromContext>>::emplace_back<NDXGI::CHwQueue *>(NDXGI::CHwQueue * &&)
0x18012e2b3  lea     rdx, [rsp+218h+var_1E8]
0x18012e2b8  mov     rcx, r15
0x18012e2bb  call    ?push_back@?$vector@V?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@2@@Z; std::vector<std::unique_ptr<NDXGI::CHwQueue>>::push_back(std::unique_ptr<NDXGI::CHwQueue> &&)
0x18012e2c0  mov     eax, [rsp+218h+var_1B4]
0x18012e2c4  mov     [rsi+8], eax
0x18012e2c7  movaps  xmm0, [rsp+218h+var_1A8]
0x18012e2cc  movups  xmmword ptr [rsi+14h], xmm0
0x18012e2d0  movaps  xmm1, [rsp+218h+var_198]
0x18012e2d8  movups  xmmword ptr [rsi+24h], xmm1
0x18012e2dc  movaps  xmm0, [rsp+218h+var_188]
0x18012e2e4  movups  xmmword ptr [rsi+34h], xmm0
0x18012e2e8  movaps  xmm1, [rsp+218h+var_178]
0x18012e2f0  movups  xmmword ptr [rsi+44h], xmm1
0x18012e2f4  movaps  xmm0, [rsp+218h+var_168]
0x18012e2fc  movups  xmmword ptr [rsi+54h], xmm0
0x18012e300  movaps  xmm1, [rsp+218h+var_158]
0x18012e308  movups  xmmword ptr [rsi+64h], xmm1
0x18012e30c  movaps  xmm0, [rsp+218h+var_148]
0x18012e314  movups  xmmword ptr [rsi+74h], xmm0
0x18012e318  movaps  xmm1, [rsp+218h+var_138]
0x18012e320  movups  xmmword ptr [rsi+84h], xmm1
0x18012e327  mov     rax, [rsp+218h+var_120]
0x18012e32f  mov     [rsi+0A0h], rax
0x18012e336  mov     eax, [rsp+218h+var_118]
0x18012e33d  mov     [rsi+0A8h], eax
0x18012e343  movups  xmm0, [rsp+218h+var_110]
0x18012e34b  movups  xmmword ptr [rsi+0B0h], xmm0
0x18012e352  movups  xmm1, [rsp+218h+var_100]
0x18012e35a  movups  xmmword ptr [rsi+0C0h], xmm1
0x18012e361  movups  xmm0, [rsp+218h+var_F0]
0x18012e369  movups  xmmword ptr [rsi+0D0h], xmm0
0x18012e370  movsd   xmm1, [rsp+218h+var_E0]
0x18012e379  movsd   qword ptr [rsi+0E0h], xmm1
0x18012e381  mov     rax, [rsp+218h+var_D8]
0x18012e389  mov     [rsi+0E8h], rax
0x18012e390  movups  xmm0, [rsp+218h+var_D0]
0x18012e398  movups  xmmword ptr [rsi+0F0h], xmm0
0x18012e39f  movups  xmm1, [rsp+218h+var_C0]
0x18012e3a7  movups  xmmword ptr [rsi+100h], xmm1
0x18012e3ae  movups  xmm0, [rsp+218h+var_B0]
0x18012e3b6  movups  xmmword ptr [rsi+110h], xmm0
0x18012e3bd  movups  xmm1, [rsp+218h+var_A0]
0x18012e3c5  movups  xmmword ptr [rsi+120h], xmm1
0x18012e3cc  movups  xmm0, [rsp+218h+var_90]
0x18012e3d4  movups  xmmword ptr [rsi+130h], xmm0
0x18012e3db  movsd   xmm1, [rsp+218h+var_80]
0x18012e3e4  movsd   qword ptr [rsi+140h], xmm1
0x18012e3ec  lea     rcx, [rsp+218h+var_1E8]
0x18012e3f1  call    ??1?$unique_ptr@VCHwQueue@NDXGI@@U?$default_delete@VCHwQueue@NDXGI@@@std@@@std@@QEAA@XZ; std::unique_ptr<NDXGI::CHwQueue>::~unique_ptr<NDXGI::CHwQueue>(void)
0x18012e3f6  nop
0x18012e3f7  mov     rcx, rdi; _Smtx_t *
0x18012e3fa  call    _Smtx_unlock_exclusive
0x18012e3ff  xor     eax, eax
0x18012e401  jmp     short loc_18012E41A
0x18012e403  mov     ebx, 8007000Eh
0x18012e408  jmp     short loc_18012E40E
0x18012e40a  mov     ebx, dword ptr [rsp+218h+var_1E8]
0x18012e40e  mov     rcx, [rsp+218h+var_1D8]; _Smtx_t *
0x18012e413  call    _Smtx_unlock_exclusive
0x18012e418  mov     eax, ebx
0x18012e41a  mov     rcx, [rsp+218h+var_38]
0x18012e422  xor     rcx, rsp; StackCookie
0x18012e425  call    __security_check_cookie
0x18012e42a  mov     rbx, [rsp+218h+arg_10]
0x18012e432  add     rsp, 1F0h
0x18012e439  pop     r15
0x18012e43b  pop     r14
0x18012e43d  pop     r13
0x18012e43f  pop     rdi
0x18012e440  pop     rsi
0x18012e441  retn
```

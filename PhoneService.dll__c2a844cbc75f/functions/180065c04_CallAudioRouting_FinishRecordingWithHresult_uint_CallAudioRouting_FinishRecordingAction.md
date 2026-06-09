# CallAudioRouting::_FinishRecordingWithHresult(uint,CallAudioRouting::FinishRecordingAction)

- ea: `0x180065c04`
- end: `0x180065f70`
- name: `?_FinishRecordingWithHresult@CallAudioRouting@@AEAAJIW4FinishRecordingAction@1@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180064f80`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x180009094`
- `0x1800091a8`
- `0x180010664`
- `0x1800107d8`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180064dac`
- `0x180065030`
- `0x180065238`
- `0x1800659fc`
- `0x180065c04`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065c9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065c9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065cdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065df2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065cdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065df2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065c55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065c55`

## string_xrefs

- `0x180065c49`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180065ccc`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180065ddf`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180065e75`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180065ed3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_FinishRecordingWithHresult(__int64 a1, unsigned int a2, char a3)
{
  int v3; // r13d
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  BackTraceCollection *v8; // rcx
  unsigned int v9; // ebx
  struct CallAudioRouting::CellularAudioState *v10; // r15
  _QWORD *v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // r8
  BackTraceCollection *v14; // rcx
  __int64 v15; // r9
  BackTraceCollection *v16; // rcx
  char *v17; // rdx
  BackTraceCollection *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  int v21; // eax
  BackTraceCollection *v22; // rcx
  int v23; // eax
  BackTraceCollection *v24; // rcx
  __int64 v25; // r9
  int v26; // eax
  BackTraceCollection *v27; // rcx
  _QWORD *v29; // [rsp+30h] [rbp-40h] BYREF
  struct CallAudioRouting::CellularAudioState *v30; // [rsp+38h] [rbp-38h] BYREF
  volatile __int32 *v31; // [rsp+40h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-28h] BYREF
  __int16 v33; // [rsp+58h] [rbp-18h] BYREF
  __int64 v34; // [rsp+5Ah] [rbp-16h]
  int v35; // [rsp+62h] [rbp-Eh]
  __int16 v36; // [rsp+66h] [rbp-Ah]

  v3 = a3;
  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2592);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v31, a1 + 128);
  v7 = 0;
  Block[0] = &v33;
  v29 = 0;
  Block[1] = &v33;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v30 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState((CallAudioRouting *)a1, a2, &v30) )
  {
    v9 = -2147023728;
    BackTraceCollection::Capture(v8, -2147023728);
    Log_HREvent_17(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2603);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    if ( Block[0] != &v33 )
      operator delete(Block[0]);
    goto LABEL_44;
  }
  v10 = v30;
  v11 = (_QWORD *)*((_QWORD *)v30 + 8);
  if ( v11 )
  {
    (*(void (__fastcall **)(_QWORD))(*v11 + 8LL))(*((_QWORD *)v30 + 8));
    v29 = v11;
    v7 = v11;
  }
  v12 = -1;
  if ( v10 != (struct CallAudioRouting::CellularAudioState *)-144LL )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v10 + v13 + 72) );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(Block) )
  {
    v9 = -2147024882;
    BackTraceCollection::Capture(v14, -2147024882);
    v15 = 2606;
LABEL_20:
    Log_HREvent_17(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v15);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    goto LABEL_21;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           Block,
                           L"\\") )
  {
    v9 = -2147024882;
    BackTraceCollection::Capture(v16, -2147024882);
    v15 = 2607;
    goto LABEL_20;
  }
  v17 = (char *)v10 + 664;
  if ( v10 != (struct CallAudioRouting::CellularAudioState *)-664LL )
  {
    do
      ++v12;
    while ( *(_WORD *)&v17[2 * v12] );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           Block,
                           v17) )
  {
    v9 = -2147024882;
    BackTraceCollection::Capture(v18, -2147024882);
    v15 = 2608;
    goto LABEL_20;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( (_BYTE)v3 )
  {
    if ( v3 != 1 )
    {
      if ( v3 == 2 )
      {
        v21 = CallAudioRouting::_FinishRecordingSaveMetadata((CallAudioRouting *)a1, a2, (const WCHAR **)Block);
        v9 = v21;
        if ( v21 < 0 )
        {
          BackTraceCollection::Capture(v22, v21);
          Log_HREvent_17(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2622);
LABEL_21:
          if ( Block[0] != &v33 )
            operator delete(Block[0]);
          if ( v7 )
          {
            v19 = *v7;
            v20 = v7;
LABEL_25:
            (*(void (__fastcall **)(_QWORD *))(v19 + 16))(v20);
            goto LABEL_44;
          }
          goto LABEL_44;
        }
      }
LABEL_39:
      if ( Block[0] != &v33 )
        operator delete(Block[0]);
      if ( v29 )
        (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      v9 = 0;
      goto LABEL_44;
    }
    v23 = CallAudioRouting::_FinishRecordingFinish(a1, a2, &v29);
    v9 = v23;
    if ( v23 >= 0 )
      goto LABEL_39;
    BackTraceCollection::Capture(v24, v23);
    v25 = 2618;
  }
  else
  {
    v26 = CallAudioRouting::_FinishRecordingStop(a1, a2, &v29);
    v9 = v26;
    if ( v26 >= 0 )
      goto LABEL_39;
    BackTraceCollection::Capture(v27, v26);
    v25 = 2614;
  }
  Log_HREvent_17(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v25);
  if ( Block[0] != &v33 )
    operator delete(Block[0]);
  v20 = v29;
  if ( v29 )
  {
    v19 = *v29;
    goto LABEL_25;
  }
LABEL_44:
  utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(&v31);
  return v9;
}

```

## disassembly

```asm
0x180065c04  mov     [rsp-38h+arg_10], rbx
0x180065c09  push    rbp
0x180065c0a  push    rsi
0x180065c0b  push    rdi
0x180065c0c  push    r12
0x180065c0e  push    r13
0x180065c10  push    r14
0x180065c12  push    r15
0x180065c14  mov     rbp, rsp
0x180065c17  sub     rsp, 70h
0x180065c1b  mov     rax, cs:__security_cookie
0x180065c22  xor     rax, rsp
0x180065c25  mov     [rbp+var_8], rax
0x180065c29  movsx   r13d, r8b
0x180065c2d  mov     r12d, edx
0x180065c30  mov     rsi, rcx
0x180065c33  call    cs:__imp_GetCurrentThreadId
0x180065c39  lea     r14, [rsi+58h]
0x180065c3d  cmp     [r14+10h], eax
0x180065c41  jnz     short loc_180065C65
0x180065c43  mov     r8d, 0A20h
0x180065c49  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180065c50  call    Log_AssertionEvent_9
0x180065c55  call    cs:__imp_GetCurrentThreadId
0x180065c5b  cmp     [rsi+68h], eax
0x180065c5e  jnz     short loc_180065C65
0x180065c60  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180065c65  lea     rdx, [rsi+80h]
0x180065c6c  lea     rcx, [rbp+var_30]
0x180065c70  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x180065c75  xor     edi, edi
0x180065c77  lea     rax, [rbp+var_18]
0x180065c7b  mov     [rbp+Block], rax
0x180065c7f  mov     rcx, r14; lpCriticalSection
0x180065c82  lea     rax, [rbp+var_18]
0x180065c86  mov     [rbp+var_40], rdi
0x180065c8a  mov     [rbp+var_20], rax
0x180065c8e  mov     [rbp+var_16], rdi
0x180065c92  mov     [rbp+var_E], edi
0x180065c95  mov     [rbp+var_A], di
0x180065c99  mov     [rbp+var_18], di
0x180065c9d  call    cs:__imp_EnterCriticalSection
0x180065ca3  lea     r8, [rbp+var_38]; struct CallAudioRouting::CellularAudioState **
0x180065ca7  mov     [rbp+var_38], rdi
0x180065cab  mov     edx, r12d; unsigned int
0x180065cae  mov     rcx, rsi; this
0x180065cb1  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180065cb6  test    eax, eax
0x180065cb8  jnz     short loc_180065D07
0x180065cba  mov     ebx, 80070490h
0x180065cbf  mov     edx, ebx; int
0x180065cc1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065cc6  mov     r9d, 0A2Bh
0x180065ccc  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180065cd3  xor     edx, edx
0x180065cd5  mov     ecx, ebx
0x180065cd7  call    Log_HREvent_17
0x180065cdc  mov     rcx, r14; lpCriticalSection
0x180065cdf  call    cs:__imp_LeaveCriticalSection
0x180065ce5  mov     rcx, [rbp+Block]; Block
0x180065ce9  lea     rax, [rbp+var_18]
0x180065ced  cmp     rcx, rax
0x180065cf0  jz      loc_180065F41
0x180065cf6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180065cfd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065d02  jmp     loc_180065F41
0x180065d07  mov     r15, [rbp+var_38]
0x180065d0b  xor     eax, eax
0x180065d0d  mov     rbx, [r15+40h]
0x180065d11  test    rbx, rbx
0x180065d14  jz      short loc_180065D2E
0x180065d16  mov     rax, [rbx]
0x180065d19  mov     rcx, rbx
0x180065d1c  mov     rax, [rax+8]
0x180065d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d25  xor     eax, eax
0x180065d27  mov     [rbp+var_40], rbx
0x180065d2b  mov     rdi, rbx
0x180065d2e  lea     rdx, [r15+90h]
0x180065d35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180065d39  test    rdx, rdx
0x180065d3c  jz      short loc_180065D4D
0x180065d3e  mov     r8, rbx
0x180065d41  inc     r8
0x180065d44  cmp     [rdx+r8*2], ax
0x180065d49  jnz     short loc_180065D41
0x180065d4b  jmp     short loc_180065D50
0x180065d4d  mov     r8, rax
0x180065d50  lea     rcx, [rbp+Block]
0x180065d54  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180065d59  test    al, al
0x180065d5b  jnz     short loc_180065D71
0x180065d5d  mov     ebx, 8007000Eh
0x180065d62  mov     edx, ebx; int
0x180065d64  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065d69  mov     r9d, 0A2Eh
0x180065d6f  jmp     short loc_180065DDF
0x180065d71  mov     r8d, 1
0x180065d77  lea     rdx, asc_18009A8CC; "\\"
0x180065d7e  lea     rcx, [rbp+Block]
0x180065d82  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180065d87  test    al, al
0x180065d89  jnz     short loc_180065D9F
0x180065d8b  mov     ebx, 8007000Eh
0x180065d90  mov     edx, ebx; int
0x180065d92  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065d97  mov     r9d, 0A2Fh
0x180065d9d  jmp     short loc_180065DDF
0x180065d9f  lea     rdx, [r15+298h]
0x180065da6  xor     r15d, r15d
0x180065da9  test    rdx, rdx
0x180065dac  jz      short loc_180065DBA
0x180065dae  inc     rbx
0x180065db1  cmp     [rdx+rbx*2], r15w
0x180065db6  jnz     short loc_180065DAE
0x180065db8  jmp     short loc_180065DBD
0x180065dba  mov     rbx, r15
0x180065dbd  mov     r8, rbx
0x180065dc0  lea     rcx, [rbp+Block]
0x180065dc4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180065dc9  test    al, al
0x180065dcb  jnz     short loc_180065E2E
0x180065dcd  mov     ebx, 8007000Eh
0x180065dd2  mov     edx, ebx; int
0x180065dd4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065dd9  mov     r9d, 0A30h
0x180065ddf  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180065de6  xor     edx, edx
0x180065de8  mov     ecx, ebx
0x180065dea  call    Log_HREvent_17
0x180065def  mov     rcx, r14; lpCriticalSection
0x180065df2  call    cs:__imp_LeaveCriticalSection
0x180065df8  mov     rcx, [rbp+Block]; Block
0x180065dfc  lea     rax, [rbp+var_18]
0x180065e00  cmp     rcx, rax
0x180065e03  jz      short loc_180065E11
0x180065e05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180065e0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065e11  test    rdi, rdi
0x180065e14  jz      loc_180065F41
0x180065e1a  mov     rax, [rdi]
0x180065e1d  mov     rcx, rdi
0x180065e20  mov     rax, [rax+10h]
0x180065e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e29  jmp     loc_180065F41
0x180065e2e  mov     rcx, r14; lpCriticalSection
0x180065e31  call    cs:__imp_LeaveCriticalSection
0x180065e37  mov     r8d, r13d
0x180065e3a  test    r13b, r13b
0x180065e3d  jz      short loc_180065EB1
0x180065e3f  sub     r8d, 1
0x180065e43  jz      short loc_180065E8D
0x180065e45  cmp     r8d, 1
0x180065e49  jnz     loc_180065F10
0x180065e4f  lea     r8, [rbp+Block]
0x180065e53  mov     edx, r12d; unsigned int
0x180065e56  mov     rcx, rsi; this
0x180065e59  call    ?_FinishRecordingSaveMetadata@CallAudioRouting@@AEAAJIAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CallAudioRouting::_FinishRecordingSaveMetadata(uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180065e5e  mov     ebx, eax
0x180065e60  test    eax, eax
0x180065e62  jns     loc_180065F10
0x180065e68  mov     edx, eax; int
0x180065e6a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065e6f  mov     r9d, 0A3Eh
0x180065e75  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180065e7c  mov     edx, 1
0x180065e81  mov     ecx, ebx
0x180065e83  call    Log_HREvent_17
0x180065e88  jmp     loc_180065DF8
0x180065e8d  lea     r8, [rbp+var_40]
0x180065e91  mov     edx, r12d
0x180065e94  mov     rcx, rsi
0x180065e97  call    ?_FinishRecordingFinish@CallAudioRouting@@AEAAJIAEBV?$ComPtr@UILowLagMediaRecording@Capture@Media@Windows@@@WRL@Microsoft@@@Z; CallAudioRouting::_FinishRecordingFinish(uint,Microsoft::WRL::ComPtr<Windows::Media::Capture::ILowLagMediaRecording> const &)
0x180065e9c  mov     ebx, eax
0x180065e9e  test    eax, eax
0x180065ea0  jns     short loc_180065F10
0x180065ea2  mov     edx, eax; int
0x180065ea4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065ea9  mov     r9d, 0A3Ah
0x180065eaf  jmp     short loc_180065ED3
0x180065eb1  lea     r8, [rbp+var_40]
0x180065eb5  mov     edx, r12d
0x180065eb8  mov     rcx, rsi
0x180065ebb  call    ?_FinishRecordingStop@CallAudioRouting@@AEAAJIAEBV?$ComPtr@UILowLagMediaRecording@Capture@Media@Windows@@@WRL@Microsoft@@@Z; CallAudioRouting::_FinishRecordingStop(uint,Microsoft::WRL::ComPtr<Windows::Media::Capture::ILowLagMediaRecording> const &)
0x180065ec0  mov     ebx, eax
0x180065ec2  test    eax, eax
0x180065ec4  jns     short loc_180065F10
0x180065ec6  mov     edx, eax; int
0x180065ec8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180065ecd  mov     r9d, 0A36h
0x180065ed3  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180065eda  mov     edx, 1
0x180065edf  mov     ecx, ebx
0x180065ee1  call    Log_HREvent_17
0x180065ee6  mov     rcx, [rbp+Block]; Block
0x180065eea  lea     rax, [rbp+var_18]
0x180065eee  cmp     rcx, rax
0x180065ef1  jz      short loc_180065EFF
0x180065ef3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180065efa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065eff  mov     rcx, [rbp+var_40]
0x180065f03  test    rcx, rcx
0x180065f06  jz      short loc_180065F41
0x180065f08  mov     rax, [rcx]
0x180065f0b  jmp     loc_180065E20
0x180065f10  mov     rcx, [rbp+Block]; Block
0x180065f14  lea     rax, [rbp+var_18]
0x180065f18  cmp     rcx, rax
0x180065f1b  jz      short loc_180065F29
0x180065f1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180065f24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180065f29  mov     rcx, [rbp+var_40]
0x180065f2d  test    rcx, rcx
0x180065f30  jz      short loc_180065F3E
0x180065f32  mov     rax, [rcx]
0x180065f35  mov     rax, [rax+10h]
0x180065f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f3e  mov     ebx, r15d
0x180065f41  lea     rcx, [rbp+var_30]
0x180065f45  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x180065f4a  mov     eax, ebx
0x180065f4c  mov     rcx, [rbp+var_8]
0x180065f50  xor     rcx, rsp; StackCookie
0x180065f53  call    __security_check_cookie
0x180065f58  mov     rbx, [rsp+70h+arg_10]
0x180065f60  add     rsp, 70h
0x180065f64  pop     r15
0x180065f66  pop     r14
0x180065f68  pop     r13
0x180065f6a  pop     r12
0x180065f6c  pop     rdi
0x180065f6d  pop     rsi
0x180065f6e  pop     rbp
0x180065f6f  retn
```

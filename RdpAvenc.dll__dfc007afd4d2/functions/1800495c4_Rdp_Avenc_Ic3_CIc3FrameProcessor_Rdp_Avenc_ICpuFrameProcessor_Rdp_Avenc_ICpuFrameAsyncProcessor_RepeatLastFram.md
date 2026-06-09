# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RepeatLastFrameThreadProc(void)

- ea: `0x1800495c4`
- end: `0x180049af1`
- name: `?RepeatLastFrameThreadProc@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAXXZ`
- size: `1325`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180047ad0`

## callees

- `0x180004b8c`
- `0x1800065a4`
- `0x1800103c0`
- `0x180010bc8`
- `0x180047b44`
- `0x180047ba8`
- `0x180047ca4`
- `0x180048f2c`
- `0x18004936c`
- `0x1800495c4`
- `0x18004f6f4`
- `0x180054f34`
- `0x180058a88`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049abb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049abb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800496be`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004989e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800496be`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18004989e`

## string_xrefs

- `0x180049770`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::RepeatLastFrameThreadProc`
- `0x1800499b1`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncProcessor>::RepeatLastFrameThreadProc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RepeatLastFrameThreadProc(
        __int64 a1)
{
  __int64 v2; // r14
  _QWORD *v3; // rax
  __int64 v4; // rsi
  char *v5; // rsi
  char *v6; // rcx
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // r8d
  int v10; // r9d
  struct Rdp::Avenc::Ic3::CDsStreamSample *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rdx
  char v14; // bl
  __int64 v15; // r8
  char *v16; // rcx
  char *v17; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v18; // rcx
  struct IVirtualVideoSink *Sink; // r15
  unsigned __int64 v20; // r13
  void (__fastcall ***v21)(_QWORD); // rax
  void (__fastcall ***v22)(_QWORD); // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  char v25; // bl
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v32; // [rsp+60h] [rbp-49h] BYREF
  const char *v33; // [rsp+68h] [rbp-41h] BYREF
  int v34; // [rsp+70h] [rbp-39h] BYREF
  int v35; // [rsp+74h] [rbp-35h] BYREF
  const char *v36; // [rsp+78h] [rbp-31h] BYREF
  const char *v37; // [rsp+80h] [rbp-29h] BYREF
  const char *v38; // [rsp+88h] [rbp-21h] BYREF
  __int64 v39; // [rsp+90h] [rbp-19h] BYREF
  char v40; // [rsp+98h] [rbp-11h]
  __int64 v41; // [rsp+A0h] [rbp-9h] BYREF
  char v42[8]; // [rsp+A8h] [rbp-1h] BYREF
  Rdp::Avenc::Ic3::CDsStreamSample *v43; // [rsp+B0h] [rbp+7h]
  void *v44; // [rsp+B8h] [rbp+Fh]
  int v45; // [rsp+110h] [rbp+67h] BYREF
  int v46; // [rsp+118h] [rbp+6Fh] BYREF
  int v47; // [rsp+120h] [rbp+77h] BYREF
  int v48; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = a1 + 256;
  v39 = a1 + 256;
  v40 = 0;
  if ( (unsigned int)mtx_do_lock(a1 + 256) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v40 = 1;
  if ( !*(_BYTE *)(a1 + 432) )
  {
    do
    {
      v32 = 18;
      v3 = (_QWORD *)std::_To_absolute_time<__int64,std::ratio<1,1000>>(v42, &v32);
      if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                           (RTL_CONDITION_VARIABLE *)(a1 + 336),
                           &v39,
                           v3) == 1 )
      {
        v4 = *(_QWORD *)(a1 + 208);
        if ( v4 )
        {
          v5 = *(char **)(v4 + 280);
          v33 = v5;
          if ( v5 )
          {
            v6 = &v5[*(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8];
            (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( *(_QWORD *)(a1 + 240) )
            {
              v32 = 0;
              GetSystemTimePreciseAsFileTime(&v32);
              v7 = (unsigned int)v32
                 + ((unsigned __int64)HIDWORD(v32) << 32)
                 - *(_QWORD *)(a1 + 424)
                 - 116444736000000000LL;
              if ( v7 - 180001 <= 0x2F8315E )
              {
                v43 = (Rdp::Avenc::Ic3::CDsStreamSample *)operator new(0xA8u);
                v8 = Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(
                       v43,
                       *(const struct Rdp::Avenc::Ic3::CDsStreamSample **)(a1 + 240),
                       v7);
                v11 = (struct Rdp::Avenc::Ic3::CDsStreamSample *)v8;
                if ( v8 )
                {
                  v12 = v8 + *(int *)(*(_QWORD *)(v8 + 8) + 4LL) + 8LL;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
                }
                if ( (unsigned int)dword_1800C1058 > 5 )
                {
                  v32 = v7;
                  v36 = (const char *)*((_QWORD *)v11 + 16);
                  v13 = *(_QWORD *)(a1 + 176);
                  v45 = *(_DWORD *)(*(_QWORD *)(v13 + 104) + 136LL);
                  v46 = *(_DWORD *)(v13 + 128);
                  v37 = "RepeatFrame";
                  v38 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICp"
                        "uFrameAsyncProcessor>::RepeatLastFrameThreadProc";
                  v47 = 672;
                  v33 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                    (unsigned int)&dword_1800C1058,
                    (unsigned int)&byte_1800B0877,
                    v9,
                    v10,
                    (__int64)&v33,
                    (__int64)&v47,
                    (__int64)&v38,
                    (__int64)&v37,
                    (__int64)&v46,
                    (__int64)&v45,
                    (__int64)&v36,
                    (__int64)&v32);
                }
                v14 = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                        a1,
                        *((_QWORD *)v11 + 16),
                        *((_QWORD *)v11 + 17));
                Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(
                  (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)v5,
                  v11);
                if ( v14 )
                {
                  LOBYTE(v15) = 1;
                  Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
                    a1,
                    *((_QWORD *)v11 + 16),
                    v15);
                }
                v16 = (char *)v11 + *(int *)(*((_QWORD *)v11 + 1) + 4LL) + 8;
                (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
              }
            }
          }
          if ( v5 )
          {
            v17 = &v5[*(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8];
            (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
        else
        {
          v18 = *(Rdp::Avenc::Ic3::CVideoSourceProvider **)(a1 + 216);
          if ( v18 )
          {
            Sink = Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(v18);
            if ( Sink )
            {
              if ( *(_QWORD *)(a1 + 248) )
              {
                v32 = 0;
                GetSystemTimePreciseAsFileTime(&v32);
                v20 = (unsigned int)v32
                    + ((unsigned __int64)HIDWORD(v32) << 32)
                    - *(_QWORD *)(a1 + 424)
                    - 116444736000000000LL;
                if ( v20 - 180001 <= 0x2F8315E )
                {
                  v44 = operator new(0xD0u);
                  v21 = (void (__fastcall ***)(_QWORD))Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(v44, a1 + 248, v20);
                  v22 = v21;
                  v32 = (__int64)v21;
                  if ( v21 )
                    (**v21)(v21);
                  v22[24] = (void (__fastcall **)(_QWORD))((*(__int64 (__fastcall **)(struct IVirtualVideoSink *))(*(_QWORD *)Sink + 16LL))(Sink)
                                                         - (_QWORD)v22[25]);
                  v23 = ((__int64 (__fastcall *)(_QWORD))(*v22)[8])(v22);
                  v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v22[2] + 200LL))(*v22[2]);
                  v25 = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                          a1,
                          (char *)v22[10] + v24,
                          v23);
                  if ( (unsigned int)dword_1800C1058 > 5 )
                  {
                    v33 = (const char *)v20;
                    v41 = ((__int64 (__fastcall *)(_QWORD))(*v22)[8])(v22);
                    v26 = *(_QWORD *)(a1 + 176);
                    v48 = *(_DWORD *)(*(_QWORD *)(v26 + 104) + 136LL);
                    v34 = *(_DWORD *)(v26 + 128);
                    v38 = "RepeatFrame";
                    v37 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::I"
                          "CpuFrameAsyncProcessor>::RepeatLastFrameThreadProc";
                    v35 = 712;
                    v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                      (unsigned int)&dword_1800C1058,
                      (unsigned int)byte_1800B08ED,
                      v27,
                      v28,
                      (__int64)&v36,
                      (__int64)&v35,
                      (__int64)&v37,
                      (__int64)&v38,
                      (__int64)&v34,
                      (__int64)&v48,
                      (__int64)&v41,
                      (__int64)&v33);
                  }
                  (*(void (__fastcall **)(struct IVirtualVideoSink *, void (__fastcall ***)(_QWORD)))(*(_QWORD *)Sink + 128LL))(
                    Sink,
                    v22);
                  if ( v25 )
                  {
                    v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v22[2] + 200LL))(*v22[2]);
                    LOBYTE(v30) = 1;
                    Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
                      a1,
                      (char *)v22[10] + v29,
                      v30);
                  }
                  (*v22)[1](v22);
                }
              }
            }
          }
        }
      }
    }
    while ( !*(_BYTE *)(a1 + 432) );
    v2 = v39;
  }
  if ( (*(_DWORD *)(v2 + 76))-- == 1 )
  {
    *(_DWORD *)(v2 + 72) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
  }
}

```

## disassembly

```asm
0x1800495c4  push    rbp
0x1800495c6  push    rbx
0x1800495c7  push    rsi
0x1800495c8  push    rdi
0x1800495c9  push    r12
0x1800495cb  push    r13
0x1800495cd  push    r14
0x1800495cf  push    r15
0x1800495d1  lea     rbp, [rsp-1Fh]
0x1800495d6  sub     rsp, 0C8h
0x1800495dd  mov     rdi, rcx
0x1800495e0  lea     r14, [rcx+100h]
0x1800495e7  mov     [rbp+57h+var_70], r14
0x1800495eb  xor     r12d, r12d
0x1800495ee  mov     [rbp+57h+var_68], r12b
0x1800495f2  mov     rcx, r14
0x1800495f5  call    mtx_do_lock
0x1800495fa  test    eax, eax
0x1800495fc  jnz     loc_180049AE6
0x180049602  mov     eax, [r14+4Ch]
0x180049606  cmp     eax, 7FFFFFFFh
0x18004960b  jz      loc_180049AD5
0x180049611  mov     [rbp+57h+var_68], 1
0x180049615  cmp     [rdi+1B0h], r12b
0x18004961c  jnz     loc_180049AA8
0x180049622  mov     rbx, 0FE624E212AC18000h
0x18004962c  lea     r13, aRepeatframe; "RepeatFrame"
0x180049633  mov     [rbp+57h+var_A0], 12h
0x18004963b  lea     rdx, [rbp+57h+var_A0]
0x18004963f  lea     rcx, [rbp+57h+var_58]
0x180049643  call    ??$_To_absolute_time@_JU?$ratio@$00$0DOI@@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@0@@Z
0x180049648  mov     r8, rax
0x18004964b  lea     rdx, [rbp+57h+var_70]
0x18004964f  lea     rcx, [rdi+150h]
0x180049656  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x18004965b  cmp     eax, 1
0x18004965e  jnz     loc_180049A8D
0x180049664  mov     rsi, [rdi+0D0h]
0x18004966b  test    rsi, rsi
0x18004966e  jz      loc_180049868
0x180049674  mov     rsi, [rsi+118h]
0x18004967b  mov     [rbp+57h+var_98], rsi
0x18004967f  test    rsi, rsi
0x180049682  jz      short loc_1800496A0
0x180049684  mov     rax, [rsi+8]
0x180049688  movsxd  rcx, dword ptr [rax+4]
0x18004968c  add     rcx, 8
0x180049690  add     rcx, rsi
0x180049693  mov     rax, [rcx]
0x180049696  mov     rax, [rax+8]
0x18004969a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004969f  nop
0x1800496a0  test    rsi, rsi
0x1800496a3  jz      loc_18004983F
0x1800496a9  cmp     [rdi+0F0h], r12
0x1800496b0  jz      loc_18004983F
0x1800496b6  mov     [rbp+57h+var_A0], r12
0x1800496ba  lea     rcx, [rbp+57h+var_A0]
0x1800496be  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800496c4  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x1800496c7  shl     rax, 20h
0x1800496cb  sub     rax, [rdi+1A8h]
0x1800496d2  mov     ecx, dword ptr [rbp+57h+var_A0]
0x1800496d5  add     rbx, rax
0x1800496d8  add     rbx, rcx
0x1800496db  lea     rax, [rbx-2BF21h]
0x1800496e2  cmp     rax, 2F8315Eh
0x1800496e8  ja      loc_18004983F
0x1800496ee  mov     ecx, 0A8h; Size
0x1800496f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800496f8  mov     [rbp+57h+var_50], rax
0x1800496fc  mov     r8, rbx; unsigned __int64
0x1800496ff  mov     rdx, [rdi+0F0h]; struct Rdp::Avenc::Ic3::CDsStreamSample *
0x180049706  mov     rcx, rax; this
0x180049709  call    ??0CDsStreamSample@Ic3@Avenc@Rdp@@QEAA@PEBV0123@_K@Z; Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(Rdp::Avenc::Ic3::CDsStreamSample const *,unsigned __int64)
0x18004970e  mov     r15, rax
0x180049711  test    rax, rax
0x180049714  jz      short loc_180049731
0x180049716  mov     rcx, [rax+8]
0x18004971a  movsxd  rcx, dword ptr [rcx+4]
0x18004971e  add     rcx, 8
0x180049722  add     rcx, rax
0x180049725  mov     rdx, [rcx]
0x180049728  mov     rax, [rdx+8]
0x18004972c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049731  mov     eax, cs:dword_1800C1058
0x180049737  cmp     eax, 5
0x18004973a  jbe     loc_1800497E8
0x180049740  mov     [rbp+57h+var_A0], rbx
0x180049744  mov     rax, [r15+80h]
0x18004974b  mov     [rbp+57h+var_88], rax
0x18004974f  mov     rdx, [rdi+0B0h]
0x180049756  mov     rax, [rdx+68h]
0x18004975a  mov     ecx, [rax+88h]
0x180049760  mov     [rbp+57h+arg_0], ecx
0x180049763  mov     eax, [rdx+80h]
0x180049769  mov     [rbp+57h+arg_8], eax
0x18004976c  mov     [rbp+57h+var_80], r13
0x180049770  lea     rax, aRdpAvencIc3Cic_12; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180049777  mov     [rbp+57h+var_78], rax
0x18004977b  mov     [rbp+57h+arg_10], 2A0h
0x180049782  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180049789  mov     [rbp+57h+var_98], rax
0x18004978d  lea     rax, [rbp+57h+var_A0]
0x180049791  mov     [rsp+100h+var_A8], rax
0x180049796  lea     rax, [rbp+57h+var_88]
0x18004979a  mov     [rsp+100h+var_B0], rax
0x18004979f  lea     rax, [rbp+57h+arg_0]
0x1800497a3  mov     [rsp+100h+var_B8], rax
0x1800497a8  lea     rax, [rbp+57h+arg_8]
0x1800497ac  mov     [rsp+100h+var_C0], rax
0x1800497b1  lea     rax, [rbp+57h+var_80]
0x1800497b5  mov     [rsp+100h+var_C8], rax
0x1800497ba  lea     rax, [rbp+57h+var_78]
0x1800497be  mov     [rsp+100h+var_D0], rax
0x1800497c3  lea     rax, [rbp+57h+arg_10]
0x1800497c7  mov     [rsp+100h+var_D8], rax
0x1800497cc  lea     rax, [rbp+57h+var_98]
0x1800497d0  mov     [rsp+100h+var_E0], rax
0x1800497d5  lea     rdx, byte_1800B0877
0x1800497dc  lea     rcx, dword_1800C1058
0x1800497e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800497e8  mov     r8, [r15+88h]
0x1800497ef  mov     rdx, [r15+80h]
0x1800497f6  mov     rcx, rdi
0x1800497f9  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x1800497fe  mov     bl, al
0x180049800  mov     rdx, r15; struct Rdp::Avenc::Ic3::CDsStreamSample *
0x180049803  mov     rcx, rsi; this
0x180049806  call    ?ProcessFrame@CDsSourceStreamProcessingSession@Ic3@Avenc@Rdp@@QEAAJPEAVCDsStreamSample@234@@Z; Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(Rdp::Avenc::Ic3::CDsStreamSample *)
0x18004980b  test    bl, bl
0x18004980d  jz      short loc_180049821
0x18004980f  mov     r8b, 1
0x180049812  mov     rdx, [r15+80h]
0x180049819  mov     rcx, rdi
0x18004981c  call    ?RaiseFirstFrameDoneEvent@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAX_K_N@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(unsigned __int64,bool)
0x180049821  mov     rax, [r15+8]
0x180049825  movsxd  rcx, dword ptr [rax+4]
0x180049829  add     rcx, 8
0x18004982d  add     rcx, r15
0x180049830  mov     rax, [rcx]
0x180049833  mov     rax, [rax+10h]
0x180049837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004983c  xor     r12d, r12d
0x18004983f  test    rsi, rsi
0x180049842  jz      loc_180049A8D
0x180049848  mov     rax, [rsi+8]
0x18004984c  movsxd  rcx, dword ptr [rax+4]
0x180049850  add     rcx, 8
0x180049854  add     rcx, rsi
0x180049857  mov     rax, [rcx]
0x18004985a  mov     rax, [rax+10h]
0x18004985e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049863  jmp     loc_180049A8D
0x180049868  mov     rcx, [rdi+0D8h]; this
0x18004986f  test    rcx, rcx
0x180049872  jz      loc_180049A8D
0x180049878  call    ?GetSink@CVideoSourceProvider@Ic3@Avenc@Rdp@@QEAAPEAVIVirtualVideoSink@@XZ; Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(void)
0x18004987d  mov     r15, rax
0x180049880  test    rax, rax
0x180049883  jz      loc_180049A8D
0x180049889  cmp     [rdi+0F8h], r12
0x180049890  jz      loc_180049A8D
0x180049896  mov     [rbp+57h+var_A0], r12
0x18004989a  lea     rcx, [rbp+57h+var_A0]
0x18004989e  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800498a4  mov     r13d, dword ptr [rbp+57h+var_A0+4]
0x1800498a8  shl     r13, 20h
0x1800498ac  sub     r13, [rdi+1A8h]
0x1800498b3  mov     ecx, dword ptr [rbp+57h+var_A0]
0x1800498b6  add     r13, rbx
0x1800498b9  add     r13, rcx
0x1800498bc  lea     rax, [r13-2BF21h]
0x1800498c3  cmp     rax, 2F8315Eh
0x1800498c9  ja      loc_180049A86
0x1800498cf  mov     ecx, 0D0h; Size
0x1800498d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800498d9  mov     [rbp+57h+var_48], rax
0x1800498dd  lea     rdx, [rdi+0F8h]
0x1800498e4  mov     r8, r13
0x1800498e7  mov     rcx, rax
0x1800498ea  call    ??0CVirtualFrame@Ic3@Avenc@Rdp@@QEAA@AEBV?$com_ptr_t@VCVirtualFrame@Ic3@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@_K@Z; Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(wil::com_ptr_t<Rdp::Avenc::Ic3::CVirtualFrame,wil::err_exception_policy> const &,unsigned __int64)
0x1800498ef  mov     rsi, rax
0x1800498f2  mov     [rbp+57h+var_A0], rax
0x1800498f6  test    rax, rax
0x1800498f9  jz      short loc_18004990A
0x1800498fb  mov     rcx, [rax]
0x1800498fe  mov     rax, [rcx]
0x180049901  mov     rcx, rsi
0x180049904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049909  nop
0x18004990a  mov     rax, [r15]
0x18004990d  mov     rcx, r15
0x180049910  mov     rax, [rax+10h]
0x180049914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049919  sub     rax, [rsi+0C8h]
0x180049920  mov     [rsi+0C0h], rax
0x180049927  mov     rax, [rsi]
0x18004992a  mov     rcx, rsi
0x18004992d  mov     rax, [rax+40h]
0x180049931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049936  mov     rbx, rax
0x180049939  mov     rcx, [rsi+10h]
0x18004993d  mov     rcx, [rcx]
0x180049940  mov     rdx, [rcx]
0x180049943  mov     rax, [rdx+0C8h]
0x18004994a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004994f  mov     rdx, [rsi+50h]
0x180049953  add     rdx, rax
0x180049956  mov     r8, rbx
0x180049959  mov     rcx, rdi
0x18004995c  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x180049961  mov     bl, al
0x180049963  mov     ecx, cs:dword_1800C1058
0x180049969  cmp     ecx, 5
0x18004996c  jbe     loc_180049A2B
0x180049972  mov     [rbp+57h+var_98], r13
0x180049976  mov     rcx, [rsi]
0x180049979  mov     rax, [rcx+40h]
0x18004997d  mov     rcx, rsi
0x180049980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049985  mov     [rbp+57h+var_60], rax
0x180049989  mov     rdx, [rdi+0B0h]
0x180049990  mov     rax, [rdx+68h]
0x180049994  mov     ecx, [rax+88h]
0x18004999a  mov     [rbp+57h+arg_18], ecx
0x18004999d  mov     eax, [rdx+80h]
0x1800499a3  mov     [rbp+57h+var_90], eax
0x1800499a6  lea     r13, aRepeatframe; "RepeatFrame"
0x1800499ad  mov     [rbp+57h+var_78], r13
0x1800499b1  lea     rax, aRdpAvencIc3Cic_12; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x1800499b8  mov     [rbp+57h+var_80], rax
0x1800499bc  mov     [rbp+57h+var_8C], 2C8h
0x1800499c3  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800499ca  mov     [rbp+57h+var_88], rax
0x1800499ce  lea     rax, [rbp+57h+var_98]
0x1800499d2  mov     [rsp+100h+var_A8], rax
0x1800499d7  lea     rax, [rbp+57h+var_60]
0x1800499db  mov     [rsp+100h+var_B0], rax
0x1800499e0  lea     rax, [rbp+57h+arg_18]
0x1800499e4  mov     [rsp+100h+var_B8], rax
0x1800499e9  lea     rax, [rbp+57h+var_90]
0x1800499ed  mov     [rsp+100h+var_C0], rax
0x1800499f2  lea     rax, [rbp+57h+var_78]
0x1800499f6  mov     [rsp+100h+var_C8], rax
0x1800499fb  lea     rax, [rbp+57h+var_80]
0x1800499ff  mov     [rsp+100h+var_D0], rax
0x180049a04  lea     rax, [rbp+57h+var_8C]
0x180049a08  mov     [rsp+100h+var_D8], rax
0x180049a0d  lea     rax, [rbp+57h+var_88]
0x180049a11  mov     [rsp+100h+var_E0], rax
0x180049a16  lea     rdx, byte_1800B08ED
0x180049a1d  lea     rcx, dword_1800C1058
0x180049a24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180049a29  jmp     short loc_180049A32
0x180049a2b  lea     r13, aRepeatframe; "RepeatFrame"
0x180049a32  mov     rax, [r15]
0x180049a35  mov     rdx, rsi
0x180049a38  mov     rcx, r15
0x180049a3b  mov     rax, [rax+80h]
0x180049a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a47  test    bl, bl
0x180049a49  jz      short loc_180049A74
0x180049a4b  mov     rax, [rsi+10h]
0x180049a4f  mov     rcx, [rax]
0x180049a52  mov     rax, [rcx]
0x180049a55  mov     rax, [rax+0C8h]
0x180049a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a61  mov     rdx, [rsi+50h]
0x180049a65  add     rdx, rax
0x180049a68  mov     r8b, 1
0x180049a6b  mov     rcx, rdi
0x180049a6e  call    ?RaiseFirstFrameDoneEvent@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAX_K_N@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(unsigned __int64,bool)
0x180049a73  nop
0x180049a74  mov     rax, [rsi]
0x180049a77  mov     rcx, rsi
0x180049a7a  mov     rax, [rax+8]
0x180049a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a83  nop
0x180049a84  jmp     short loc_180049A8D
0x180049a86  lea     r13, aRepeatframe; "RepeatFrame"
0x180049a8d  cmp     [rdi+1B0h], r12b
0x180049a94  mov     rbx, 0FE624E212AC18000h
0x180049a9e  jz      loc_180049633
0x180049aa4  mov     r14, [rbp+57h+var_70]
0x180049aa8  sub     dword ptr [r14+4Ch], 1
0x180049aad  jnz     short loc_180049AC1
0x180049aaf  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180049ab7  lea     rcx, [r14+10h]; SRWLock
0x180049abb  call    cs:__imp_ReleaseSRWLockExclusive
0x180049ac1  add     rsp, 0C8h
0x180049ac8  pop     r15
0x180049aca  pop     r14
0x180049acc  pop     r13
0x180049ace  pop     r12
0x180049ad0  pop     rdi
0x180049ad1  pop     rsi
0x180049ad2  pop     rbx
0x180049ad3  pop     rbp
0x180049ad4  retn
  ... truncated ...
```

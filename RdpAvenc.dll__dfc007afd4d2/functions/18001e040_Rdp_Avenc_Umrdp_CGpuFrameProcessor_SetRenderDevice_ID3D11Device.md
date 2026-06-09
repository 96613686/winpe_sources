# Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice(ID3D11Device *)

- ea: `0x18001e040`
- end: `0x18001e4f4`
- name: `?SetRenderDevice@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@UEAAJPEAUID3D11Device@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CGpuFrameProcessor *__hidden this, struct ID3D11Device *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001f30`
- `0x1800153f8`
- `0x180015480`
- `0x18001ce50`
- `0x18001d494`
- `0x18001e040`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e09a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e09a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4a2`

## string_xrefs

- `0x18001e166`: `Source texture has incompatible mode with Rdp surface`
- `0x18001e21f`: `Source texture has incompatible mode with Rdp surface. Id %d`
- `0x18001e38b`: `SetRenderDevice: create new RdpSurface`
- `0x18001e448`: `SetRenderDevice: create new RdpSurface. Id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice(
        Rdp::Avenc::Umrdp::CGpuFrameProcessor *this,
        struct ID3D11Device *a2,
        int a3,
        int a4)
{
  char v6; // bl
  bool v7; // si
  bool v8; // r15
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  __int64 v12; // rsi
  __int64 v13; // rcx
  char *v14; // r13
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  const char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  bool v21; // di
  char v22; // al
  int v23; // r8d
  int v24; // edx
  __int64 result; // rax
  int v26; // [rsp+20h] [rbp-78h]
  int v27; // [rsp+20h] [rbp-78h]
  int v28; // [rsp+28h] [rbp-70h]
  int v29; // [rsp+28h] [rbp-70h]
  const char *v30; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v31[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v33; // [rsp+A0h] [rbp+8h] BYREF
  int v34; // [rsp+A8h] [rbp+10h] BYREF
  int v35; // [rsp+B0h] [rbp+18h] BYREF
  const char *v36; // [rsp+B8h] [rbp+20h] BYREF

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v26,
      v28,
      12,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      CurrentThreadId);
  }
  try
  {
    v12 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = a2;
    if ( a2 )
      ((void (__fastcall *)(struct ID3D11Device *))a2->lpVtbl->AddRef)(a2);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = *((_QWORD *)this + 1);
    if ( v13 )
    {
      v14 = (char *)this + 24;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v13 + 24LL))(
             v13,
             (char *)this + 32,
             (char *)this + 24) )
      {
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          v19 = *(_QWORD *)v14;
          v33 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v14 + 120LL) + 196LL);
          v34 = *(_DWORD *)(v19 + 128);
          v36 = "SetRenderDevice: re-use RdpSurface";
          v31[0] = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice";
          v35 = 425;
          v30 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&dword_1800AD844,
            v15,
            v16,
            (__int64)&v30,
            (__int64)&v35,
            (__int64)v31,
            (__int64)&v36,
            (__int64)&v34,
            (__int64)&v33);
        }
        v29 = *(_DWORD *)(*(_QWORD *)v14 + 128LL);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"SetRenderDevice: re-use RdpSurface. Id %d",
          "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
          0x1ACu);
        (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 32LL))(
          *((_QWORD *)this + 1),
          (char *)this + 32);
      }
      else
      {
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          v17 = *(_QWORD *)v14;
          v33 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v14 + 120LL) + 196LL);
          v34 = *(_DWORD *)(v17 + 128);
          v36 = "Source texture has incompatible mode with Rdp surface";
          v30 = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice";
          v35 = 406;
          v31[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800AD899,
            v15,
            v16,
            (__int64)v31,
            (__int64)&v35,
            (__int64)&v30,
            (__int64)&v36,
            (__int64)&v34,
            (__int64)&v33);
        }
        v29 = *(_DWORD *)(*(_QWORD *)v14 + 128LL);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"Source texture has incompatible mode with Rdp surface. Id %d",
          "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
          0x199u);
        Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface((char *)this - 80);
        Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface((Rdp::Avenc::Umrdp::CGpuFrameProcessor *)((char *)this - 80));
      }
    }
    else
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        v20 = *((_QWORD *)this + 3);
        v33 = *(_DWORD *)(*(_QWORD *)(v20 + 120) + 196LL);
        v34 = *(_DWORD *)(v20 + 128);
        v36 = "SetRenderDevice: create new RdpSurface";
        v31[0] = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice";
        v35 = 446;
        v30 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800AD7EF,
          a3,
          a4,
          (__int64)&v30,
          (__int64)&v35,
          (__int64)v31,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)&v33);
      }
      v29 = *(_DWORD *)(*((_QWORD *)this + 3) + 128LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"SetRenderDevice: create new RdpSurface. Id %d",
        "Rdp::Avenc::Umrdp::CGpuFrameProcessor::SetRenderDevice",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
        0x1C1u);
      Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface((Rdp::Avenc::Umrdp::CGpuFrameProcessor *)((char *)this - 80));
    }
    *((_BYTE *)this + 49) = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = GetCurrentThreadId();
      LOBYTE(v23) = v21;
      LOBYTE(v24) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        v23,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v27,
        v29,
        13,
        &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
        v22);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CE,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18001e040  push    rbx
0x18001e042  push    rsi
0x18001e043  push    rdi
0x18001e044  push    r12
0x18001e046  push    r13
0x18001e048  push    r14
0x18001e04a  push    r15
0x18001e04c  sub     rsp, 60h
0x18001e050  mov     rdi, rdx
0x18001e053  mov     r14, rcx
0x18001e056  lea     rcx, WPP_GLOBAL_Control
0x18001e05d  mov     rax, cs:WPP_GLOBAL_Control
0x18001e064  mov     bl, 1
0x18001e066  cmp     rax, rcx
0x18001e069  jz      short loc_18001E07B
0x18001e06b  test    [rax+1Ch], bl
0x18001e06e  jz      short loc_18001E07B
0x18001e070  cmp     byte ptr [rax+19h], 4
0x18001e074  jb      short loc_18001E07B
0x18001e076  mov     sil, bl
0x18001e079  jmp     short loc_18001E07E
0x18001e07b  xor     sil, sil
0x18001e07e  lea     rax, WPP_RECORDER_INITIALIZED
0x18001e085  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001e08c  setnz   r15b
0x18001e090  test    sil, sil
0x18001e093  jnz     short loc_18001E09A
0x18001e095  test    r15b, r15b
0x18001e098  jz      short loc_18001E0D1
0x18001e09a  call    cs:__imp_GetCurrentThreadId
0x18001e0a0  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001e0a4  lea     r13, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001e0ab  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x18001e0b0  mov     [rsp+98h+var_68], 0Ch; __int16
0x18001e0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0be  mov     r9, [rcx+28h]; int
0x18001e0c2  mov     r8b, r15b; int
0x18001e0c5  mov     dl, sil; int
0x18001e0c8  mov     rcx, [rcx+10h]; int
0x18001e0cc  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001e0d1  lea     r12, [r14+20h]
0x18001e0d5  mov     rsi, [r12]
0x18001e0d9  mov     [r12], rdi
0x18001e0dd  test    rdi, rdi
0x18001e0e0  jz      short loc_18001E0F1
0x18001e0e2  mov     rax, [rdi]
0x18001e0e5  mov     rcx, rdi
0x18001e0e8  mov     rax, [rax+8]
0x18001e0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0f1  test    rsi, rsi
0x18001e0f4  jz      short loc_18001E106
0x18001e0f6  mov     rax, [rsi]
0x18001e0f9  mov     rcx, rsi
0x18001e0fc  mov     rax, [rax+10h]
0x18001e100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e105  nop
0x18001e106  lea     r15, [r14-50h]
0x18001e10a  mov     rcx, [r15+58h]
0x18001e10e  test    rcx, rcx
0x18001e111  jz      loc_18001E356
0x18001e117  lea     r13, [r14+18h]
0x18001e11b  mov     rax, [rcx]
0x18001e11e  mov     r8, r13
0x18001e121  mov     rdx, r12
0x18001e124  mov     rax, [rax+18h]
0x18001e128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e12d  test    al, al
0x18001e12f  mov     eax, cs:dword_1800C1058
0x18001e135  jnz     loc_18001E247
0x18001e13b  cmp     eax, 4
0x18001e13e  jbe     loc_18001E1F5
0x18001e144  mov     rdx, [r13+0]
0x18001e148  mov     rax, [rdx+78h]
0x18001e14c  mov     ecx, [rax+0C4h]
0x18001e152  mov     [rsp+98h+arg_0], ecx
0x18001e159  mov     eax, [rdx+80h]
0x18001e15f  mov     [rsp+98h+arg_8], eax
0x18001e166  lea     rax, aSourceTextureH; "Source texture has incompatible mode wi"...
0x18001e16d  mov     [rsp+98h+arg_18], rax
0x18001e175  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e17c  mov     [rsp+98h+var_48], rdi
0x18001e181  mov     [rsp+98h+arg_10], 196h
0x18001e18c  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e193  mov     [rsp+98h+var_40], rsi
0x18001e198  lea     rax, [rsp+98h+arg_0]
0x18001e1a0  mov     [rsp+98h+var_50], rax
0x18001e1a5  lea     rax, [rsp+98h+arg_8]
0x18001e1ad  mov     qword ptr [rsp+98h+var_58], rax
0x18001e1b2  lea     rax, [rsp+98h+arg_18]
0x18001e1ba  mov     [rsp+98h+MessageGuid], rax
0x18001e1bf  lea     rax, [rsp+98h+var_48]
0x18001e1c4  mov     qword ptr [rsp+98h+var_68], rax
0x18001e1c9  lea     rax, [rsp+98h+arg_10]
0x18001e1d1  mov     qword ptr [rsp+98h+var_70], rax
0x18001e1d6  lea     rax, [rsp+98h+var_40]
0x18001e1db  mov     qword ptr [rsp+98h+var_78], rax
0x18001e1e0  lea     rdx, byte_1800AD899
0x18001e1e7  lea     rcx, dword_1800C1058
0x18001e1ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e1f3  jmp     short loc_18001E203
0x18001e1f5  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e1fc  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e203  mov     rax, [r13+0]
0x18001e207  mov     edx, [rax+80h]
0x18001e20d  mov     [rsp+98h+var_70], edx
0x18001e211  mov     [rsp+98h+var_78], 199h; unsigned int
0x18001e219  mov     r9, rsi; char *
0x18001e21c  mov     r8, rdi; char *
0x18001e21f  lea     rdx, aSourceTextureH_0; "Source texture has incompatible mode wi"...
0x18001e226  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e22d  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e232  mov     rcx, r15
0x18001e235  call    ?DestroyRdpSurface@?$CFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Umrdp@Avenc@Rdp@@IEAAXXZ; Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface(void)
0x18001e23a  mov     rcx, r15; this
0x18001e23d  call    ?CreateRdpSurface@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface(void)
0x18001e242  jmp     loc_18001E351
0x18001e247  cmp     eax, 4
0x18001e24a  jbe     loc_18001E301
0x18001e250  mov     rdx, [r13+0]
0x18001e254  mov     rax, [rdx+78h]
0x18001e258  mov     ecx, [rax+0C4h]
0x18001e25e  mov     [rsp+98h+arg_0], ecx
0x18001e265  mov     eax, [rdx+80h]
0x18001e26b  mov     [rsp+98h+arg_8], eax
0x18001e272  lea     rax, aSetrenderdevic_3; "SetRenderDevice: re-use RdpSurface"
0x18001e279  mov     [rsp+98h+arg_18], rax
0x18001e281  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e288  mov     [rsp+98h+var_40], rdi
0x18001e28d  mov     [rsp+98h+arg_10], 1A9h
0x18001e298  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e29f  mov     [rsp+98h+var_48], rsi
0x18001e2a4  lea     rax, [rsp+98h+arg_0]
0x18001e2ac  mov     [rsp+98h+var_50], rax
0x18001e2b1  lea     rax, [rsp+98h+arg_8]
0x18001e2b9  mov     qword ptr [rsp+98h+var_58], rax
0x18001e2be  lea     rax, [rsp+98h+arg_18]
0x18001e2c6  mov     [rsp+98h+MessageGuid], rax
0x18001e2cb  lea     rax, [rsp+98h+var_40]
0x18001e2d0  mov     qword ptr [rsp+98h+var_68], rax
0x18001e2d5  lea     rax, [rsp+98h+arg_10]
0x18001e2dd  mov     qword ptr [rsp+98h+var_70], rax
0x18001e2e2  lea     rax, [rsp+98h+var_48]
0x18001e2e7  mov     qword ptr [rsp+98h+var_78], rax
0x18001e2ec  lea     rdx, dword_1800AD844
0x18001e2f3  lea     rcx, dword_1800C1058
0x18001e2fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e2ff  jmp     short loc_18001E30F
0x18001e301  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e308  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e30f  mov     rax, [r13+0]
0x18001e313  mov     ecx, [rax+80h]
0x18001e319  mov     [rsp+98h+var_70], ecx
0x18001e31d  mov     [rsp+98h+var_78], 1ACh; unsigned int
0x18001e325  mov     r9, rsi; char *
0x18001e328  mov     r8, rdi; char *
0x18001e32b  lea     rdx, aSetrenderdevic_1; "SetRenderDevice: re-use RdpSurface. Id "...
0x18001e332  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e339  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e33e  mov     rcx, [r14+8]
0x18001e342  mov     rax, [rcx]
0x18001e345  mov     rdx, r12
0x18001e348  mov     rax, [rax+20h]
0x18001e34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e351  jmp     loc_18001E463
0x18001e356  mov     eax, cs:dword_1800C1058
0x18001e35c  cmp     eax, 4
0x18001e35f  jbe     loc_18001E41A
0x18001e365  lea     r12, [r14+18h]
0x18001e369  mov     rdx, [r12]
0x18001e36d  mov     rax, [rdx+78h]
0x18001e371  mov     ecx, [rax+0C4h]
0x18001e377  mov     [rsp+98h+arg_0], ecx
0x18001e37e  mov     eax, [rdx+80h]
0x18001e384  mov     [rsp+98h+arg_8], eax
0x18001e38b  lea     rax, aSetrenderdevic_0; "SetRenderDevice: create new RdpSurface"
0x18001e392  mov     [rsp+98h+arg_18], rax
0x18001e39a  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e3a1  mov     [rsp+98h+var_40], rdi
0x18001e3a6  mov     [rsp+98h+arg_10], 1BEh
0x18001e3b1  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e3b8  mov     [rsp+98h+var_48], rsi
0x18001e3bd  lea     rax, [rsp+98h+arg_0]
0x18001e3c5  mov     [rsp+98h+var_50], rax
0x18001e3ca  lea     rax, [rsp+98h+arg_8]
0x18001e3d2  mov     qword ptr [rsp+98h+var_58], rax
0x18001e3d7  lea     rax, [rsp+98h+arg_18]
0x18001e3df  mov     [rsp+98h+MessageGuid], rax
0x18001e3e4  lea     rax, [rsp+98h+var_40]
0x18001e3e9  mov     qword ptr [rsp+98h+var_68], rax
0x18001e3ee  lea     rax, [rsp+98h+arg_10]
0x18001e3f6  mov     qword ptr [rsp+98h+var_70], rax
0x18001e3fb  lea     rax, [rsp+98h+var_48]
0x18001e400  mov     qword ptr [rsp+98h+var_78], rax
0x18001e405  lea     rdx, byte_1800AD7EF
0x18001e40c  lea     rcx, dword_1800C1058
0x18001e413  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e418  jmp     short loc_18001E42C
0x18001e41a  lea     r12, [r14+18h]
0x18001e41e  lea     rdi, aRdpAvencUmrdpC_27; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001e425  lea     rsi, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001e42c  mov     rax, [r12]
0x18001e430  mov     ecx, [rax+80h]
0x18001e436  mov     [rsp+98h+var_70], ecx; int
0x18001e43a  mov     [rsp+98h+var_78], 1C1h; int
0x18001e442  mov     r9, rsi; char *
0x18001e445  mov     r8, rdi; char *
0x18001e448  lea     rdx, aSetrenderdevic_2; "SetRenderDevice: create new RdpSurface."...
0x18001e44f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e456  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e45b  mov     rcx, r15; this
0x18001e45e  call    ?CreateRdpSurface@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface(void)
0x18001e463  mov     [r14+31h], bl
0x18001e467  mov     rax, cs:WPP_GLOBAL_Control
0x18001e46e  lea     rcx, WPP_GLOBAL_Control
0x18001e475  cmp     rax, rcx
0x18001e478  jz      short loc_18001E485
0x18001e47a  test    [rax+1Ch], bl
0x18001e47d  jz      short loc_18001E485
0x18001e47f  cmp     byte ptr [rax+19h], 4
0x18001e483  jnb     short loc_18001E487
0x18001e485  xor     bl, bl
0x18001e487  lea     rax, WPP_RECORDER_INITIALIZED
0x18001e48e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001e495  setnz   dil
0x18001e499  test    bl, bl
0x18001e49b  jnz     short loc_18001E4A2
0x18001e49d  test    dil, dil
0x18001e4a0  jz      short loc_18001E4D8
0x18001e4a2  call    cs:__imp_GetCurrentThreadId
0x18001e4a8  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001e4ac  lea     rax, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001e4b3  mov     [rsp+98h+MessageGuid], rax; MessageGuid
0x18001e4b8  mov     [rsp+98h+var_68], 0Dh; __int16
0x18001e4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4c6  mov     r9, [rcx+28h]; int
0x18001e4ca  mov     r8b, dil; int
0x18001e4cd  mov     dl, bl; int
0x18001e4cf  mov     rcx, [rcx+10h]; int
0x18001e4d3  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001e4d8  xor     eax, eax
0x18001e4da  jmp     short loc_18001E4E3
0x18001e4dc  mov     eax, [rsp+98h+arg_0]
0x18001e4e3  add     rsp, 60h
0x18001e4e7  pop     r15
0x18001e4e9  pop     r14
0x18001e4eb  pop     r13
0x18001e4ed  pop     r12
0x18001e4ef  pop     rdi
0x18001e4f0  pop     rsi
0x18001e4f1  pop     rbx
0x18001e4f2  retn
```

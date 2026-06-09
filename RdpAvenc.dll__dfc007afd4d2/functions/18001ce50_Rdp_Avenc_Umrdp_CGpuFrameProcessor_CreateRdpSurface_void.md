# Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface(void)

- ea: `0x18001ce50`
- end: `0x18001d287`
- name: `?CreateRdpSurface@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ`
- size: `1079`
- prototype: `void __fastcall(Rdp::Avenc::Umrdp::CGpuFrameProcessor *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d6d0`
- `0x18001e040`

## callees

- `0x180001f30`
- `0x1800021e4`
- `0x1800153f8`
- `0x18001c3f4`
- `0x18001c514`
- `0x18001ce50`
- `0x180089010`

## string_xrefs

- `0x18001ced1`: `Create shared buffer Rdp surface`
- `0x18001ce78`: `Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface`
- `0x18001cf26`: `Create shared buffer Rdp surface. Id %d, Readback %d`
- `0x18001d054`: `Create Dx texture Rdp surface`
- `0x18001d0ad`: `Create Dx texture Rdp surface. Id %d, Readback %d`
- `0x18001d1fa`: `RdpSurface::SendCreate complete`
- `0x18001d261`: `RdpSurface::SendCreate complete. Id %d`

## pseudocode

```c
void __fastcall Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface(
        Rdp::Avenc::Umrdp::CGpuFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char *v4; // rbx
  __int64 v6; // rdx
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rdx
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rsi
  volatile signed __int32 *v17; // rsi
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // [rsp+28h] [rbp-58h]
  __int64 v22; // [rsp+28h] [rbp-58h]
  __int64 v23; // [rsp+30h] [rbp-50h]
  const char *v24; // [rsp+60h] [rbp-20h] BYREF
  const char *v25; // [rsp+68h] [rbp-18h] BYREF
  const char *v26; // [rsp+70h] [rbp-10h] BYREF
  volatile signed __int32 *v27; // [rsp+78h] [rbp-8h]
  int v28; // [rsp+C0h] [rbp+40h] BYREF
  int v29; // [rsp+C8h] [rbp+48h] BYREF
  int v30; // [rsp+D0h] [rbp+50h] BYREF
  const char *v31; // [rsp+D8h] [rbp+58h] BYREF

  v4 = (char *)this + 104;
  if ( *((_BYTE *)this + 136) )
  {
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v6 = *(_QWORD *)v4;
      v28 = *((unsigned __int8 *)this + 136);
      v25 = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface";
      v26 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
      v29 = *(_DWORD *)(*(_QWORD *)(v6 + 120) + 196LL);
      v30 = *(_DWORD *)(v6 + 128);
      v24 = "Create shared buffer Rdp surface";
      LODWORD(v31) = 562;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800AD702,
        a3,
        a4,
        (__int64)&v26,
        (__int64)&v31,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
    LODWORD(v23) = *((unsigned __int8 *)this + 136);
    LODWORD(v21) = *(_DWORD *)(*(_QWORD *)v4 + 128LL);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Create shared buffer Rdp surface. Id %d, Readback %d",
      "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
      0x236u,
      v21,
      v23);
    v7 = (__int64 *)std::make_shared<Rdp::Avenc::Umrdp::CRdpSharedSurface,wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &>(
                      &v26,
                      *(_QWORD *)v4 + 120LL,
                      v4);
    v8 = *v7;
    v9 = v7[1];
    *v7 = 0;
    v7[1] = 0;
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 11) = v8;
    *((_QWORD *)this + 12) = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v11 = v27;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    v4 = (char *)this + 104;
  }
  else
  {
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v12 = *(_QWORD *)v4;
      v28 = *((unsigned __int8 *)this + 136);
      v25 = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface";
      v24 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
      v29 = *(_DWORD *)(*(_QWORD *)(v12 + 120) + 196LL);
      v30 = *(_DWORD *)(v12 + 128);
      v26 = "Create Dx texture Rdp surface";
      LODWORD(v31) = 579;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800AD69C,
        a3,
        a4,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
    LODWORD(v23) = *((unsigned __int8 *)this + 136);
    LODWORD(v21) = *(_DWORD *)(*(_QWORD *)v4 + 128LL);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Create Dx texture Rdp surface. Id %d, Readback %d",
      "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
      0x247u,
      v21,
      v23);
    v13 = (__int64 *)std::make_shared<Rdp::Avenc::Umrdp::CRdpSharedTextureSurface,wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &>(
                       &v26,
                       *(_QWORD *)v4 + 120LL,
                       v4);
    v14 = *v13;
    v15 = v13[1];
    *v13 = 0;
    v13[1] = 0;
    v16 = (volatile signed __int32 *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 11) = v14;
    *((_QWORD *)this + 12) = v15;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          v4 = (char *)this + 104;
        }
      }
    }
    v17 = v27;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11), (char *)this + 112);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11));
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v4 = (char *)this + 104;
    v26 = "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface";
    v20 = *((_QWORD *)this + 13);
    v25 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp";
    v28 = *(_DWORD *)(*(_QWORD *)(v20 + 120) + 196LL);
    v29 = *(_DWORD *)(v20 + 128);
    v31 = "RdpSurface::SendCreate complete";
    v30 = 603;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800AD647,
      v18,
      v19,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v28);
  }
  LODWORD(v22) = *(_DWORD *)(*(_QWORD *)v4 + 128LL);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RdpSurface::SendCreate complete. Id %d",
    "Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
    0x25Eu,
    v22);
}

```

## disassembly

```asm
0x18001ce50  mov     r11, rsp
0x18001ce53  push    rbp
0x18001ce54  push    rbx
0x18001ce55  push    rsi
0x18001ce56  push    rdi
0x18001ce57  push    r12
0x18001ce59  push    r14
0x18001ce5b  push    r15
0x18001ce5d  mov     rbp, rsp
0x18001ce60  sub     rsp, 80h
0x18001ce67  cmp     byte ptr [rcx+88h], 0
0x18001ce6e  lea     rbx, [rcx+68h]
0x18001ce72  mov     eax, cs:dword_1800C1058
0x18001ce78  lea     r15, aRdpAvencUmrdpC_19; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001ce7f  mov     r14, rcx
0x18001ce82  lea     r12, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001ce89  jz      loc_18001D012
0x18001ce8f  cmp     eax, 4
0x18001ce92  jbe     loc_18001CF23
0x18001ce98  movzx   eax, byte ptr [rcx+88h]
0x18001ce9f  mov     rdx, [rbx]
0x18001cea2  mov     [rbp+arg_0], eax
0x18001cea5  mov     [rbp+var_18], r15
0x18001cea9  mov     [rbp+var_10], r12
0x18001cead  mov     rax, [rdx+78h]
0x18001ceb1  mov     ecx, [rax+0C4h]
0x18001ceb7  mov     [rbp+arg_8], ecx
0x18001ceba  lea     rcx, dword_1800C1058
0x18001cec1  mov     eax, [rdx+80h]
0x18001cec7  lea     rdx, word_1800AD702
0x18001cece  mov     [rbp+arg_10], eax
0x18001ced1  lea     rax, aCreateSharedBu_0; "Create shared buffer Rdp surface"
0x18001ced8  mov     [rbp+var_20], rax
0x18001cedc  lea     rax, [rbp+arg_0]
0x18001cee0  mov     [r11-68h], rax
0x18001cee4  lea     rax, [rbp+arg_8]
0x18001cee8  mov     [r11-70h], rax
0x18001ceec  lea     rax, [rbp+arg_10]
0x18001cef0  mov     [r11-78h], rax
0x18001cef4  lea     rax, [rbp+var_20]
0x18001cef8  mov     [r11-80h], rax
0x18001cefc  lea     rax, [rbp+var_18]
0x18001cf00  mov     [rsp+80h+var_50], rax
0x18001cf05  lea     rax, [rbp+arg_18]
0x18001cf09  mov     [rsp+80h+var_58], rax
0x18001cf0e  lea     rax, [rbp+var_10]
0x18001cf12  mov     qword ptr [rsp+80h+var_60], rax
0x18001cf17  mov     dword ptr [rbp+arg_18], 232h
0x18001cf1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001cf23  mov     rcx, [rbx]
0x18001cf26  lea     rdx, aCreateSharedBu_3; "Create shared buffer Rdp surface. Id %d"...
0x18001cf2d  movzx   eax, byte ptr [r14+88h]
0x18001cf35  mov     r9, r12; char *
0x18001cf38  mov     dword ptr [rsp+80h+var_50], eax
0x18001cf3c  mov     r8, r15; char *
0x18001cf3f  mov     eax, [rcx+80h]
0x18001cf45  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001cf4c  mov     dword ptr [rsp+80h+var_58], eax
0x18001cf50  mov     [rsp+80h+var_60], 236h; unsigned int
0x18001cf58  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001cf5d  mov     rdx, [rbx]
0x18001cf60  lea     rcx, [rbp+var_10]
0x18001cf64  add     rdx, 78h ; 'x'
0x18001cf68  mov     r8, rbx
0x18001cf6b  call    ??$make_shared@VCRdpSharedSurface@Umrdp@Avenc@Rdp@@AEBV?$com_ptr_t@VCUmrdpProcessor@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@AEAV?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@6@@std@@YA?AV?$shared_ptr@VCRdpSharedSurface@Umrdp@Avenc@Rdp@@@0@AEBV?$com_ptr_t@VCUmrdpProcessor@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@AEAV?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@3@@Z; std::make_shared<Rdp::Avenc::Umrdp::CRdpSharedSurface,wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &>(wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &)
0x18001cf70  or      edi, 0FFFFFFFFh
0x18001cf73  mov     rcx, [rax]
0x18001cf76  mov     rdx, [rax+8]
0x18001cf7a  mov     qword ptr [rax], 0
0x18001cf81  mov     qword ptr [rax+8], 0
0x18001cf89  mov     rbx, [r14+60h]
0x18001cf8d  mov     [r14+58h], rcx
0x18001cf91  mov     [r14+60h], rdx
0x18001cf95  test    rbx, rbx
0x18001cf98  jz      short loc_18001CFCD
0x18001cf9a  mov     eax, edi
0x18001cf9c  lock xadd [rbx+8], eax
0x18001cfa1  add     eax, edi
0x18001cfa3  jnz     short loc_18001CFCD
0x18001cfa5  mov     rax, [rbx]
0x18001cfa8  mov     rcx, rbx
0x18001cfab  mov     rax, [rax]
0x18001cfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfb3  mov     eax, edi
0x18001cfb5  lock xadd [rbx+0Ch], eax
0x18001cfba  add     eax, edi
0x18001cfbc  jnz     short loc_18001CFCD
0x18001cfbe  mov     rax, [rbx]
0x18001cfc1  mov     rcx, rbx
0x18001cfc4  mov     rax, [rax+8]
0x18001cfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfcd  mov     rbx, [rbp+var_8]
0x18001cfd1  test    rbx, rbx
0x18001cfd4  jz      short loc_18001D009
0x18001cfd6  mov     eax, edi
0x18001cfd8  lock xadd [rbx+8], eax
0x18001cfdd  add     eax, edi
0x18001cfdf  jnz     short loc_18001D009
0x18001cfe1  mov     rax, [rbx]
0x18001cfe4  mov     rcx, rbx
0x18001cfe7  mov     rax, [rax]
0x18001cfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfef  mov     eax, edi
0x18001cff1  lock xadd [rbx+0Ch], eax
0x18001cff6  add     eax, edi
0x18001cff8  jnz     short loc_18001D009
0x18001cffa  mov     rax, [rbx]
0x18001cffd  mov     rcx, rbx
0x18001d000  mov     rax, [rax+8]
0x18001d004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d009  lea     rbx, [r14+68h]
0x18001d00d  jmp     loc_18001D194
0x18001d012  cmp     eax, 4
0x18001d015  jbe     loc_18001D0AA
0x18001d01b  movzx   eax, byte ptr [rcx+88h]
0x18001d022  mov     rdx, [rbx]
0x18001d025  mov     [rbp+arg_0], eax
0x18001d028  mov     [rbp+var_18], r15
0x18001d02c  mov     [rbp+var_20], r12
0x18001d030  mov     rax, [rdx+78h]
0x18001d034  mov     ecx, [rax+0C4h]
0x18001d03a  mov     [rbp+arg_8], ecx
0x18001d03d  lea     rcx, dword_1800C1058
0x18001d044  mov     eax, [rdx+80h]
0x18001d04a  lea     rdx, dword_1800AD69C
0x18001d051  mov     [rbp+arg_10], eax
0x18001d054  lea     rax, aCreateDxTextur; "Create Dx texture Rdp surface"
0x18001d05b  mov     [rbp+var_10], rax
0x18001d05f  lea     rax, [rbp+arg_0]
0x18001d063  mov     [rsp+80h+var_30], rax
0x18001d068  lea     rax, [rbp+arg_8]
0x18001d06c  mov     [rsp+80h+var_38], rax
0x18001d071  lea     rax, [rbp+arg_10]
0x18001d075  mov     [rsp+80h+var_40], rax
0x18001d07a  lea     rax, [rbp+var_10]
0x18001d07e  mov     [rsp+80h+var_48], rax
0x18001d083  lea     rax, [rbp+var_18]
0x18001d087  mov     [rsp+80h+var_50], rax
0x18001d08c  lea     rax, [rbp+arg_18]
0x18001d090  mov     [rsp+80h+var_58], rax
0x18001d095  lea     rax, [rbp+var_20]
0x18001d099  mov     qword ptr [rsp+80h+var_60], rax
0x18001d09e  mov     dword ptr [rbp+arg_18], 243h
0x18001d0a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d0aa  mov     rcx, [rbx]
0x18001d0ad  lea     rdx, aCreateDxTextur_0; "Create Dx texture Rdp surface. Id %d, R"...
0x18001d0b4  movzx   eax, byte ptr [r14+88h]
0x18001d0bc  mov     r9, r12; char *
0x18001d0bf  mov     dword ptr [rsp+80h+var_50], eax
0x18001d0c3  mov     r8, r15; char *
0x18001d0c6  mov     eax, [rcx+80h]
0x18001d0cc  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001d0d3  mov     dword ptr [rsp+80h+var_58], eax
0x18001d0d7  mov     [rsp+80h+var_60], 247h; unsigned int
0x18001d0df  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001d0e4  mov     rdx, [rbx]
0x18001d0e7  lea     rcx, [rbp+var_10]
0x18001d0eb  add     rdx, 78h ; 'x'
0x18001d0ef  mov     r8, rbx
0x18001d0f2  call    ??$make_shared@VCRdpSharedTextureSurface@Umrdp@Avenc@Rdp@@AEBV?$com_ptr_t@VCUmrdpProcessor@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@AEAV?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@6@@std@@YA?AV?$shared_ptr@VCRdpSharedTextureSurface@Umrdp@Avenc@Rdp@@@0@AEBV?$com_ptr_t@VCUmrdpProcessor@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@AEAV?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@3@@Z; std::make_shared<Rdp::Avenc::Umrdp::CRdpSharedTextureSurface,wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &>(wil::com_ptr_t<Rdp::Avenc::Umrdp::CUmrdpProcessor,wil::err_exception_policy> const &,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy> &)
0x18001d0f7  or      edi, 0FFFFFFFFh
0x18001d0fa  mov     rcx, [rax]
0x18001d0fd  mov     rdx, [rax+8]
0x18001d101  mov     qword ptr [rax], 0
0x18001d108  mov     qword ptr [rax+8], 0
0x18001d110  mov     rsi, [r14+60h]
0x18001d114  mov     [r14+58h], rcx
0x18001d118  mov     [r14+60h], rdx
0x18001d11c  test    rsi, rsi
0x18001d11f  jz      short loc_18001D158
0x18001d121  mov     eax, edi
0x18001d123  lock xadd [rsi+8], eax
0x18001d128  add     eax, edi
0x18001d12a  jnz     short loc_18001D158
0x18001d12c  mov     rax, [rsi]
0x18001d12f  mov     rcx, rsi
0x18001d132  mov     rax, [rax]
0x18001d135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d13a  mov     eax, edi
0x18001d13c  lock xadd [rsi+0Ch], eax
0x18001d141  add     eax, edi
0x18001d143  jnz     short loc_18001D158
0x18001d145  mov     rax, [rsi]
0x18001d148  mov     rcx, rsi
0x18001d14b  mov     rax, [rax+8]
0x18001d14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d154  lea     rbx, [r14+68h]
0x18001d158  mov     rsi, [rbp+var_8]
0x18001d15c  test    rsi, rsi
0x18001d15f  jz      short loc_18001D194
0x18001d161  mov     eax, edi
0x18001d163  lock xadd [rsi+8], eax
0x18001d168  add     eax, edi
0x18001d16a  jnz     short loc_18001D194
0x18001d16c  mov     rax, [rsi]
0x18001d16f  mov     rcx, rsi
0x18001d172  mov     rax, [rax]
0x18001d175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d17a  mov     eax, edi
0x18001d17c  lock xadd [rsi+0Ch], eax
0x18001d181  add     eax, edi
0x18001d183  jnz     short loc_18001D194
0x18001d185  mov     rax, [rsi]
0x18001d188  mov     rcx, rsi
0x18001d18b  mov     rax, [rax+8]
0x18001d18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d194  mov     rcx, [r14+58h]
0x18001d198  lea     rdx, [r14+70h]
0x18001d19c  mov     rax, [rcx]
0x18001d19f  mov     rax, [rax+20h]
0x18001d1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a8  mov     rcx, [r14+58h]
0x18001d1ac  mov     rax, [rcx]
0x18001d1af  mov     rax, [rax+38h]
0x18001d1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b8  mov     eax, cs:dword_1800C1058
0x18001d1be  cmp     eax, 4
0x18001d1c1  jbe     loc_18001D247
0x18001d1c7  lea     rbx, [r14+68h]
0x18001d1cb  mov     [rbp+var_10], r15
0x18001d1cf  mov     rdx, [rbx]
0x18001d1d2  mov     [rbp+var_18], r12
0x18001d1d6  mov     rax, [rdx+78h]
0x18001d1da  mov     ecx, [rax+0C4h]
0x18001d1e0  mov     [rbp+arg_0], ecx
0x18001d1e3  lea     rcx, dword_1800C1058
0x18001d1ea  mov     eax, [rdx+80h]
0x18001d1f0  lea     rdx, byte_1800AD647
0x18001d1f7  mov     [rbp+arg_8], eax
0x18001d1fa  lea     rax, aRdpsurfaceSend; "RdpSurface::SendCreate complete"
0x18001d201  mov     [rbp+arg_18], rax
0x18001d205  lea     rax, [rbp+arg_0]
0x18001d209  mov     [rsp+80h+var_38], rax
0x18001d20e  lea     rax, [rbp+arg_8]
0x18001d212  mov     [rsp+80h+var_40], rax
0x18001d217  lea     rax, [rbp+arg_18]
0x18001d21b  mov     [rsp+80h+var_48], rax
0x18001d220  lea     rax, [rbp+var_10]
0x18001d224  mov     [rsp+80h+var_50], rax
0x18001d229  lea     rax, [rbp+arg_10]
0x18001d22d  mov     [rsp+80h+var_58], rax
0x18001d232  lea     rax, [rbp+var_18]
0x18001d236  mov     qword ptr [rsp+80h+var_60], rax
0x18001d23b  mov     [rbp+arg_10], 25Bh
0x18001d242  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d247  mov     rax, [rbx]
0x18001d24a  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001d251  mov     r9, r12; char *
0x18001d254  mov     r8, r15; char *
0x18001d257  mov     edx, [rax+80h]
0x18001d25d  mov     dword ptr [rsp+80h+var_58], edx
0x18001d261  lea     rdx, aRdpsurfaceSend_0; "RdpSurface::SendCreate complete. Id %d"
0x18001d268  mov     [rsp+80h+var_60], 25Eh; unsigned int
0x18001d270  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001d275  add     rsp, 80h
0x18001d27c  pop     r15
0x18001d27e  pop     r14
0x18001d280  pop     r12
0x18001d282  pop     rdi
0x18001d283  pop     rsi
0x18001d284  pop     rbx
0x18001d285  pop     rbp
0x18001d286  retn
```

# Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor(Rdp::Avenc::ICpuFrameProcessor * *,IPropertyStore *)

- ea: `0x180061f20`
- end: `0x1800621e6`
- name: `?CreateCpuFrameProcessor@CYuvMonitorContext@Yuv@Avenc@Rdp@@UEAAJPEAPEAUICpuFrameProcessor@34@PEAUIPropertyStore@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvMonitorContext *__hidden this, struct Rdp::Avenc::ICpuFrameProcessor **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000406c`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x1800153f8`
- `0x180061aec`
- `0x180061f20`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006219e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006219e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006213c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006213c`

## string_xrefs

- `0x180062014`: `Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor`
- `0x180062118`: `Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor`
- `0x180062005`: `Create Cpu Yuv frame processor`
- `0x18006211f`: `CreateCpuYuvFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor(
        Rdp::Avenc::Yuv::CYuvMonitorContext *this,
        struct Rdp::Avenc::ICpuFrameProcessor **a2,
        struct IPropertyStore *a3)
{
  __int64 v4; // rax
  int v5; // r8d
  int v6; // r9d
  struct Rdp::Avenc::ICpuFrameProcessor *v7; // r12
  char *v8; // rcx
  __int64 v9; // rbx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-B8h]
  bool v13[8]; // [rsp+28h] [rbp-B0h]
  const char *v14; // [rsp+30h] [rbp-A8h]
  __int64 v15; // [rsp+30h] [rbp-A8h]
  __int64 v16; // [rsp+38h] [rbp-A0h]
  __int64 v17; // [rsp+40h] [rbp-98h]
  __int64 v18; // [rsp+48h] [rbp-90h]
  __int64 v19; // [rsp+50h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-58h] BYREF
  int v21; // [rsp+84h] [rbp-54h] BYREF
  char *v22; // [rsp+88h] [rbp-50h] BYREF
  const char *v23; // [rsp+90h] [rbp-48h] BYREF
  const char *v24; // [rsp+98h] [rbp-40h] BYREF
  _QWORD v25[2]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  Rdp::Avenc::Yuv::CCpuYuvFrameProcessor *v28; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
        (const char *)0x80004003LL,
        v12);
    LOBYTE(v12) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
      (const char *)0x8000FFFFLL,
      v12,
      (bool)"Monitor context is not started",
      v14);
    v28 = (Rdp::Avenc::Yuv::CCpuYuvFrameProcessor *)operator new(0xA0u);
    v4 = Rdp::Avenc::Yuv::CCpuYuvFrameProcessor::CCpuYuvFrameProcessor(
           v28,
           (Rdp::Avenc::Yuv::CYuvMonitorContext *)((char *)this - 80));
    v7 = (struct Rdp::Avenc::ICpuFrameProcessor *)v4;
    v25[1] = v4;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v22 = (char *)this + 40;
      LODWORD(v28) = *(_DWORD *)(*((_QWORD *)this + 4) + 152LL);
      v20 = *((_DWORD *)this + 14);
      v23 = "Create Cpu Yuv frame processor";
      v24 = "Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor";
      v21 = 159;
      v25[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B4C33,
        v5,
        v6,
        (__int64)v25,
        (__int64)&v21,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v22);
    }
    LODWORD(v19) = *((unsigned __int8 *)this + 50);
    LODWORD(v18) = *((unsigned __int8 *)this + 49);
    LODWORD(v17) = *((unsigned __int8 *)this + 48);
    LODWORD(v16) = *((unsigned __int16 *)this + 23);
    LODWORD(v15) = *((unsigned __int16 *)this + 22);
    *(_DWORD *)v13 = *((_DWORD *)this + 10);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"CreateCpuYuvFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Yuv::CYuvMonitorContext::CreateCpuFrameProcessor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
      0xA1u,
      *(_QWORD *)v13,
      v15,
      v16,
      v17,
      v18,
      v19,
      *((unsigned __int8 *)this + 51),
      *((unsigned __int8 *)this + 52),
      *((unsigned __int8 *)this + 53),
      *((unsigned __int8 *)this + 54),
      *((unsigned __int8 *)this + 55));
    AcquireSRWLockExclusive((PSRWLOCK)this + 16);
    if ( v7 )
      v8 = (char *)v7 + 80;
    else
      v8 = 0;
    v9 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v8;
    if ( v8 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v7 )
      v7 = (struct Rdp::Avenc::ICpuFrameProcessor *)((char *)v7 + 152);
    *a2 = v7;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA8,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180061f20  mov     [rsp+arg_0], rbx
0x180061f25  mov     [rsp+arg_10], rsi
0x180061f2a  mov     [rsp+arg_8], rdx
0x180061f2f  push    rdi
0x180061f30  push    r12
0x180061f32  push    r13
0x180061f34  push    r14
0x180061f36  push    r15
0x180061f38  sub     rsp, 0B0h
0x180061f3f  mov     rax, rdx
0x180061f42  mov     r15, rcx
0x180061f45  mov     rcx, [rsp+0D8h]; this
0x180061f4d  test    rax, rax
0x180061f50  jz      loc_1800621CD
0x180061f56  cmp     byte ptr [r15+10h], 0
0x180061f5b  setz    al
0x180061f5e  mov     rcx, [rsp+0D8h]; this
0x180061f66  lea     rdx, aMonitorContext; "Monitor context is not started"
0x180061f6d  mov     qword ptr [rsp+0D8h+var_B0], rdx; bool
0x180061f72  mov     byte ptr [rsp+0D8h+var_B8], al; int
0x180061f76  mov     r9d, 8000FFFFh; char *
0x180061f7c  lea     r13, aOnecoreuapTerm_38; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180061f83  mov     r8, r13; unsigned int
0x180061f86  mov     edx, 98h; void *
0x180061f8b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180061f90  mov     ecx, 0A0h; Size
0x180061f95  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061f9a  mov     [rsp+0D8h+arg_18], rax
0x180061fa2  lea     rdx, [r15-50h]; struct Rdp::Avenc::Yuv::CYuvMonitorContext *
0x180061fa6  mov     rcx, rax; this
0x180061fa9  call    ??0CCpuYuvFrameProcessor@Yuv@Avenc@Rdp@@QEAA@PEAVCYuvMonitorContext@123@@Z; Rdp::Avenc::Yuv::CCpuYuvFrameProcessor::CCpuYuvFrameProcessor(Rdp::Avenc::Yuv::CYuvMonitorContext *)
0x180061fae  mov     r12, rax
0x180061fb1  mov     [rsp+0D8h+var_30], rax
0x180061fb9  test    rax, rax
0x180061fbc  jz      short loc_180061FCE
0x180061fbe  mov     rcx, [rax]
0x180061fc1  mov     rax, [rcx+8]
0x180061fc5  mov     rcx, r12
0x180061fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fcd  nop
0x180061fce  mov     eax, cs:dword_1800C1058
0x180061fd4  cmp     eax, 4
0x180061fd7  jbe     loc_1800620A4
0x180061fdd  lea     rax, [r15+28h]
0x180061fe1  mov     [rsp+0D8h+var_50], rax
0x180061fe9  mov     rax, [r15+20h]
0x180061fed  mov     ecx, [rax+98h]
0x180061ff3  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x180061ffa  mov     eax, [r15+38h]
0x180061ffe  mov     [rsp+0D8h+var_58], eax
0x180062005  lea     rax, aCreateCpuYuvFr; "Create Cpu Yuv frame processor"
0x18006200c  mov     [rsp+0D8h+var_48], rax
0x180062014  lea     rax, aRdpAvencYuvCyu; "Rdp::Avenc::Yuv::CYuvMonitorContext::Cr"...
0x18006201b  mov     [rsp+0D8h+var_40], rax
0x180062023  mov     [rsp+0D8h+var_54], 9Fh
0x18006202e  mov     [rsp+0D8h+var_38], r13
0x180062036  lea     rax, [rsp+0D8h+var_50]
0x18006203e  mov     [rsp+0D8h+var_88], rax
0x180062043  lea     rax, [rsp+0D8h+arg_18]
0x18006204b  mov     [rsp+0D8h+var_90], rax
0x180062050  lea     rax, [rsp+0D8h+var_58]
0x180062058  mov     [rsp+0D8h+var_98], rax
0x18006205d  lea     rax, [rsp+0D8h+var_48]
0x180062065  mov     [rsp+0D8h+var_A0], rax
0x18006206a  lea     rax, [rsp+0D8h+var_40]
0x180062072  mov     [rsp+0D8h+var_A8], rax
0x180062077  lea     rax, [rsp+0D8h+var_54]
0x18006207f  mov     qword ptr [rsp+0D8h+var_B0], rax
0x180062084  lea     rax, [rsp+0D8h+var_38]
0x18006208c  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180062091  lea     rdx, byte_1800B4C33
0x180062098  lea     rcx, dword_1800C1058
0x18006209f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800620a4  lea     r8, [r15+28h]
0x1800620a8  movzx   eax, byte ptr [r15+37h]
0x1800620ad  movzx   ecx, byte ptr [r15+36h]
0x1800620b2  movzx   edx, byte ptr [r15+35h]
0x1800620b7  movzx   r9d, byte ptr [r15+34h]
0x1800620bc  movzx   r10d, byte ptr [r15+33h]
0x1800620c1  movzx   r11d, byte ptr [r15+32h]
0x1800620c6  movzx   ebx, byte ptr [r15+31h]
0x1800620cb  movzx   edi, byte ptr [r15+30h]
0x1800620d0  movzx   esi, word ptr [r15+2Eh]
0x1800620d5  movzx   r14d, word ptr [r15+2Ch]
0x1800620da  mov     [rsp+0D8h+var_60], eax
0x1800620de  mov     [rsp+0D8h+var_68], ecx
0x1800620e2  mov     [rsp+0D8h+var_70], edx
0x1800620e6  mov     [rsp+0D8h+var_78], r9d
0x1800620eb  mov     [rsp+0D8h+var_80], r10d
0x1800620f0  mov     dword ptr [rsp+0D8h+var_88], r11d
0x1800620f5  mov     dword ptr [rsp+0D8h+var_90], ebx
0x1800620f9  mov     dword ptr [rsp+0D8h+var_98], edi
0x1800620fd  mov     dword ptr [rsp+0D8h+var_A0], esi
0x180062101  mov     dword ptr [rsp+0D8h+var_A8], r14d
0x180062106  mov     eax, [r8]
0x180062109  mov     dword ptr [rsp+0D8h+var_B0], eax
0x18006210d  mov     [rsp+0D8h+var_B8], 0A1h; unsigned int
0x180062115  mov     r9, r13; char *
0x180062118  lea     r8, aRdpAvencYuvCyu; "Rdp::Avenc::Yuv::CYuvMonitorContext::Cr"...
0x18006211f  lea     rdx, aCreatecpuyuvfr; "CreateCpuYuvFrameProcessor: Id {%08lX-%"...
0x180062126  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18006212d  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180062132  lea     rdi, [r15+80h]
0x180062139  mov     rcx, rdi; SRWLock
0x18006213c  call    cs:__imp_AcquireSRWLockExclusive
0x180062142  test    r12, r12
0x180062145  jz      short loc_18006214E
0x180062147  lea     rcx, [r12+50h]
0x18006214c  jmp     short loc_180062150
0x18006214e  xor     ecx, ecx
0x180062150  mov     rbx, [r15+90h]
0x180062157  mov     [r15+90h], rcx
0x18006215e  test    rcx, rcx
0x180062161  jz      short loc_18006216F
0x180062163  mov     rax, [rcx]
0x180062166  mov     rax, [rax+8]
0x18006216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006216f  test    rbx, rbx
0x180062172  jz      short loc_180062184
0x180062174  mov     rax, [rbx]
0x180062177  mov     rcx, rbx
0x18006217a  mov     rax, [rax+10h]
0x18006217e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062183  nop
0x180062184  test    r12, r12
0x180062187  jz      short loc_180062190
0x180062189  add     r12, 98h
0x180062190  mov     rax, [rsp+0D8h+arg_8]
0x180062198  mov     [rax], r12
0x18006219b  mov     rcx, rdi; SRWLock
0x18006219e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800621a4  nop
0x1800621a5  xor     eax, eax
0x1800621a7  jmp     short loc_1800621B0
0x1800621a9  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x1800621b0  lea     r11, [rsp+0D8h+var_28]
0x1800621b8  mov     rbx, [r11+30h]
0x1800621bc  mov     rsi, [r11+40h]
0x1800621c0  mov     rsp, r11
0x1800621c3  pop     r15
0x1800621c5  pop     r14
0x1800621c7  pop     r13
0x1800621c9  pop     r12
0x1800621cb  pop     rdi
0x1800621cc  retn
0x1800621cd  mov     r9d, 80004003h; char *
0x1800621d3  lea     r8, aOnecoreuapTerm_38; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800621da  mov     edx, 97h; void *
0x1800621df  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

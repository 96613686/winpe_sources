# CMidiClientPipe::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x140021310`
- end: `0x14002145f`
- name: `?SendMidiMessage@CMidiClientPipe@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `335`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140002270`
- `0x14000984c`
- `0x14000a6b4`
- `0x140021310`
- `0x140047084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140021404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002143b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140021404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002143b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400213c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400213c8`

## string_xrefs

- `0x1400213e8`: `avcore\midi2\service\exe\midiclientpipe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiClientPipe::SendMidiMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  int v12; // r12d
  RTL_SRWLOCK *v13; // rbx
  __int64 v14; // rcx
  int v15; // edi
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-41h]
  unsigned int v19; // [rsp+60h] [rbp-1h] BYREF
  __int64 v20; // [rsp+68h] [rbp+7h] BYREF
  __int64 v21; // [rsp+70h] [rbp+Fh] BYREF
  const wchar_t *v22; // [rsp+78h] [rbp+17h] BYREF
  __int64 v23; // [rsp+80h] [rbp+1Fh] BYREF
  int v24[2]; // [rsp+88h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]
  __int64 v26; // [rsp+C0h] [rbp+5Fh] BYREF

  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v12 = a5;
  if ( *v9 > 5u )
  {
    v20 = a5;
    LODWORD(v26) = a4;
    v21 = a3;
    v19 = a2;
    v22 = L"Sending MIDI Message to client.";
    v23 = a1;
    *(_QWORD *)v24 = "CMidiClientPipe::SendMidiMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)byte_14008853D,
      v10,
      v11,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v19,
      (__int64)&v21,
      (__int64)&v26,
      (__int64)&v20);
  }
  v13 = (RTL_SRWLOCK *)(a1 + 120);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 120));
  v26 = a1 + 120;
  v14 = *(_QWORD *)(a1 + 136);
  if ( !v14 )
  {
    v15 = -2147467260;
    v16 = 253;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)v15,
      v18);
    if ( v13 )
      ReleaseSRWLockShared(v13);
    return (unsigned int)v15;
  }
  v18 = v12;
  v15 = CMidiXProc::SendMidiMessage(v14, *(_DWORD *)(a1 + 172) | a2, a3, a4);
  if ( v15 < 0 )
  {
    v16 = 255;
    goto LABEL_5;
  }
  if ( v13 )
    ReleaseSRWLockShared(v13);
  return 0;
}

```

## disassembly

```asm
0x140021310  mov     [rsp-8+arg_8], rbx
0x140021315  mov     [rsp-8+arg_10], rsi
0x14002131a  push    rbp
0x14002131b  push    rdi
0x14002131c  push    r12
0x14002131e  push    r14
0x140021320  push    r15
0x140021322  lea     rbp, [rsp-2Fh]
0x140021327  sub     rsp, 90h
0x14002132e  mov     r14d, r9d
0x140021331  mov     r15, r8
0x140021334  mov     esi, edx
0x140021336  mov     rdi, rcx
0x140021339  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14002133e  mov     rcx, [rax+8]
0x140021342  mov     eax, [rcx]
0x140021344  mov     r12, [rbp+4Fh+arg_20]
0x140021348  cmp     eax, 5
0x14002134b  jbe     short loc_1400213C1
0x14002134d  mov     [rbp+4Fh+var_48], r12
0x140021351  mov     dword ptr [rbp+4Fh+arg_0], r14d
0x140021355  mov     [rbp+4Fh+var_40], r15
0x140021359  mov     [rbp+4Fh+var_50], esi
0x14002135c  lea     rax, aSendingMidiMes_0; "Sending MIDI Message to client."
0x140021363  mov     [rbp+4Fh+var_38], rax
0x140021367  mov     [rbp+4Fh+var_30], rdi
0x14002136b  lea     rax, aCmidiclientpip_0; "CMidiClientPipe::SendMidiMessage"
0x140021372  mov     qword ptr [rbp+4Fh+var_28], rax
0x140021376  lea     rax, [rbp+4Fh+var_48]
0x14002137a  mov     [rsp+0B0h+var_60], rax
0x14002137f  lea     rax, [rbp+4Fh+arg_0]
0x140021383  mov     [rsp+0B0h+var_68], rax
0x140021388  lea     rax, [rbp+4Fh+var_40]
0x14002138c  mov     [rsp+0B0h+var_70], rax
0x140021391  lea     rax, [rbp+4Fh+var_50]
0x140021395  mov     [rsp+0B0h+var_78], rax
0x14002139a  lea     rax, [rbp+4Fh+var_38]
0x14002139e  mov     [rsp+0B0h+var_80], rax
0x1400213a3  lea     rax, [rbp+4Fh+var_30]
0x1400213a7  mov     [rsp+0B0h+var_88], rax
0x1400213ac  lea     rax, [rbp+4Fh+var_28]
0x1400213b0  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1400213b5  lea     rdx, byte_14008853D
0x1400213bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400213c1  lea     rbx, [rdi+78h]
0x1400213c5  mov     rcx, rbx; SRWLock
0x1400213c8  call    cs:__imp_AcquireSRWLockShared
0x1400213ce  mov     [rbp+4Fh+arg_0], rbx
0x1400213d2  mov     rcx, [rdi+88h]
0x1400213d9  test    rcx, rcx
0x1400213dc  jnz     short loc_14002140E
0x1400213de  mov     edi, 80004004h
0x1400213e3  mov     edx, 0FDh; void *
0x1400213e8  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x1400213ef  mov     r9d, edi; char *
0x1400213f2  mov     rcx, [rbp+57h]; this
0x1400213f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400213fb  nop
0x1400213fc  test    rbx, rbx
0x1400213ff  jz      short loc_14002140A
0x140021401  mov     rcx, rbx; SRWLock
0x140021404  call    cs:__imp_ReleaseSRWLockShared
0x14002140a  mov     eax, edi
0x14002140c  jmp     short loc_140021443
0x14002140e  or      esi, [rdi+0ACh]
0x140021414  mov     qword ptr [rsp+0B0h+var_90], r12
0x140021419  mov     r9d, r14d
0x14002141c  mov     r8, r15
0x14002141f  mov     edx, esi
0x140021421  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x140021426  mov     edi, eax
0x140021428  test    eax, eax
0x14002142a  jns     short loc_140021433
0x14002142c  mov     edx, 0FFh
0x140021431  jmp     short loc_1400213E8
0x140021433  test    rbx, rbx
0x140021436  jz      short loc_140021441
0x140021438  mov     rcx, rbx; SRWLock
0x14002143b  call    cs:__imp_ReleaseSRWLockShared
0x140021441  xor     eax, eax
0x140021443  lea     r11, [rsp+0B0h+var_20]
0x14002144b  mov     rbx, [r11+38h]
0x14002144f  mov     rsi, [r11+40h]
0x140021453  mov     rsp, r11
0x140021456  pop     r15
0x140021458  pop     r14
0x14002145a  pop     r12
0x14002145c  pop     rdi
0x14002145d  pop     rbp
0x14002145e  retn
```

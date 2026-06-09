# CMidi2LoopbackMidiBidi::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180012dc0`
- end: `0x18001304d`
- name: `?SendMidiMessage@CMidi2LoopbackMidiBidi@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `653`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800017d0`
- `0x18000a024`
- `0x18000bfe4`
- `0x18000ccd8`
- `0x18000f0a4`
- `0x180010848`
- `0x180012dc0`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall CMidi2LoopbackMidiBidi::SendMidiMessage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v8; // rdx
  struct TransportState *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rax
  __int64 Device; // r14
  __int64 v16; // rcx
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  const char *v20; // rax
  __int64 *v21; // rdx
  const char **v22; // rax
  struct TransportState *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rbx
  volatile signed __int32 *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // r14
  const char *v29; // rax
  int v30; // [rsp+20h] [rbp-60h]
  const char **v31; // [rsp+30h] [rbp-50h]
  const char *v32; // [rsp+40h] [rbp-40h] BYREF
  __int64 v33; // [rsp+48h] [rbp-38h] BYREF
  const char *v34; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v35[40]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  const wchar_t *v37; // [rsp+C0h] [rbp+40h] BYREF

  if ( !a3 )
  {
    v8 = 163;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidibidi.cpp",
      (const char *)0x80070057LL,
      v30);
    return 2147942487LL;
  }
  if ( a4 < 4 )
  {
    v8 = 164;
    goto LABEL_3;
  }
  if ( *(_BYTE *)(a1 + 24) )
  {
    v10 = TransportState::Current();
    v11 = *((_QWORD *)v10 + 3);
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
    v12 = *((_QWORD *)v10 + 2);
    v13 = (volatile signed __int32 *)*((_QWORD *)v10 + 3);
    v14 = std::wstring::wstring(v35, a1 + 32);
    Device = MidiLoopbackDeviceTable::GetDevice(v12, v14);
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    if ( Device )
    {
      v16 = *(_QWORD *)(Device + 472);
      goto LABEL_15;
    }
    v17 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 2u )
    {
      v37 = L"Send A to B : Unable to find endpoint device in table";
      v20 = (const char *)(a1 + 80);
      if ( *(_QWORD *)(a1 + 104) > 7u )
        v20 = *(const char **)v20;
      v32 = v20;
      v21 = qword_180057F00;
      v34 = "CMidi2LoopbackMidiBidi::SendMidiMessage";
      v31 = &v32;
      v22 = &v34;
LABEL_34:
      v33 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (_DWORD)v21,
        v18,
        v19,
        (__int64)v22,
        (__int64)&v33,
        (__int64)v31,
        (__int64)&v37);
      return 2147500037LL;
    }
    return 2147500037LL;
  }
  v23 = TransportState::Current();
  v24 = *((_QWORD *)v23 + 3);
  if ( v24 )
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
  v25 = *((_QWORD *)v23 + 2);
  v26 = (volatile signed __int32 *)*((_QWORD *)v23 + 3);
  v27 = std::wstring::wstring(v35, a1 + 32);
  v28 = MidiLoopbackDeviceTable::GetDevice(v25, v27);
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  if ( !v28 )
  {
    v17 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 2u )
    {
      v37 = L"Send B to A : Unable to find endpoint device in table";
      v29 = (const char *)(a1 + 80);
      if ( *(_QWORD *)(a1 + 104) > 7u )
        v29 = *(const char **)v29;
      v34 = v29;
      v21 = qword_180057EC0;
      v32 = "CMidi2LoopbackMidiBidi::SendMidiMessage";
      v31 = &v34;
      v22 = &v32;
      goto LABEL_34;
    }
    return 2147500037LL;
  }
  v16 = *(_QWORD *)(v28 + 464);
LABEL_15:
  if ( v16 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v16 + 24LL))(
             v16,
             0,
             a3,
             a4,
             a5,
             *(_QWORD *)(a1 + 72));
  else
    return 0;
}

```

## disassembly

```asm
0x180012dc0  mov     [rsp-28h+arg_0], rbx
0x180012dc5  mov     [rsp-28h+arg_8], rsi
0x180012dca  push    rbp
0x180012dcb  push    rdi
0x180012dcc  push    r12
0x180012dce  push    r14
0x180012dd0  push    r15
0x180012dd2  mov     rbp, rsp
0x180012dd5  sub     rsp, 80h
0x180012ddc  mov     r15d, r9d
0x180012ddf  mov     r12, r8
0x180012de2  mov     rsi, rcx
0x180012de5  test    r8, r8
0x180012de8  jnz     short loc_180012E0E
0x180012dea  mov     edx, 0A3h; void *
0x180012def  mov     rcx, [rbp+28h]; this
0x180012df3  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\loopbackmidit"...
0x180012dfa  mov     ebx, 80070057h
0x180012dff  mov     r9d, ebx; char *
0x180012e02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e07  mov     eax, ebx
0x180012e09  jmp     loc_180013031
0x180012e0e  cmp     r15d, 4
0x180012e12  jnb     short loc_180012E1B
0x180012e14  mov     edx, 0A4h
0x180012e19  jmp     short loc_180012DEF
0x180012e1b  cmp     byte ptr [rcx+18h], 0
0x180012e1f  jz      loc_180012F3F
0x180012e25  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012e2a  mov     rcx, [rax+18h]
0x180012e2e  test    rcx, rcx
0x180012e31  jz      short loc_180012E37
0x180012e33  lock inc dword ptr [rcx+8]
0x180012e37  mov     rbx, [rax+10h]
0x180012e3b  lea     rdx, [rsi+20h]
0x180012e3f  mov     rdi, [rax+18h]
0x180012e43  lea     rcx, [rbp+var_28]
0x180012e47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012e4c  mov     rdx, rax
0x180012e4f  mov     rcx, rbx
0x180012e52  call    ?GetDevice@MidiLoopbackDeviceTable@@QEAAPEAVMidiLoopbackDevice@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MidiLoopbackDeviceTable::GetDevice(std::wstring)
0x180012e57  mov     r14, rax
0x180012e5a  test    rdi, rdi
0x180012e5d  jz      short loc_180012E95
0x180012e5f  or      ebx, 0FFFFFFFFh
0x180012e62  mov     ecx, ebx
0x180012e64  lock xadd [rdi+8], ecx
0x180012e69  add     ecx, ebx
0x180012e6b  jnz     short loc_180012E95
0x180012e6d  mov     rdx, [rdi]
0x180012e70  mov     rcx, rdi
0x180012e73  mov     rax, [rdx]
0x180012e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e7b  mov     eax, ebx
0x180012e7d  lock xadd [rdi+0Ch], eax
0x180012e82  add     eax, ebx
0x180012e84  jnz     short loc_180012E95
0x180012e86  mov     rax, [rdi]
0x180012e89  mov     rcx, rdi
0x180012e8c  mov     rax, [rax+8]
0x180012e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e95  test    r14, r14
0x180012e98  jz      short loc_180012ED8
0x180012e9a  mov     rcx, [r14+1D8h]
0x180012ea1  test    rcx, rcx
0x180012ea4  jz      short loc_180012ED1
0x180012ea6  mov     rdx, [rsi+48h]
0x180012eaa  mov     r9d, r15d
0x180012ead  mov     rax, [rcx]
0x180012eb0  mov     r8, r12
0x180012eb3  mov     [rsp+80h+var_58], rdx
0x180012eb8  mov     rdx, [rbp+arg_20]
0x180012ebc  mov     [rsp+80h+var_60], rdx
0x180012ec1  xor     edx, edx
0x180012ec3  mov     rax, [rax+18h]
0x180012ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ecc  jmp     loc_180013031
0x180012ed1  xor     eax, eax
0x180012ed3  jmp     loc_180013031
0x180012ed8  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180012edd  mov     rcx, [rax+8]
0x180012ee1  mov     eax, [rcx]
0x180012ee3  cmp     eax, 2
0x180012ee6  jbe     loc_18001302C
0x180012eec  lea     rax, aSendAToBUnable; "Send A to B : Unable to find endpoint d"...
0x180012ef3  mov     [rbp+arg_10], rax
0x180012ef7  lea     rax, [rsi+50h]
0x180012efb  cmp     qword ptr [rax+18h], 7
0x180012f00  jbe     short loc_180012F05
0x180012f02  mov     rax, [rax]
0x180012f05  mov     [rbp+var_40], rax
0x180012f09  lea     rdx, qword_180057F00
0x180012f10  lea     rax, aCmidi2loopback_0; "CMidi2LoopbackMidiBidi::SendMidiMessage"
0x180012f17  mov     [rbp+var_30], rax
0x180012f1b  lea     rax, [rbp+arg_10]
0x180012f1f  mov     [rsp+80h+var_48], rax
0x180012f24  lea     rax, [rbp+var_40]
0x180012f28  mov     [rsp+80h+var_50], rax
0x180012f2d  lea     rax, [rbp+var_38]
0x180012f31  mov     [rsp+80h+var_58], rax
0x180012f36  lea     rax, [rbp+var_30]
0x180012f3a  jmp     loc_18001301E
0x180012f3f  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012f44  mov     rcx, [rax+18h]
0x180012f48  test    rcx, rcx
0x180012f4b  jz      short loc_180012F51
0x180012f4d  lock inc dword ptr [rcx+8]
0x180012f51  mov     rbx, [rax+10h]
0x180012f55  lea     rdx, [rsi+20h]
0x180012f59  mov     rdi, [rax+18h]
0x180012f5d  lea     rcx, [rbp+var_28]
0x180012f61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180012f66  mov     rdx, rax
0x180012f69  mov     rcx, rbx
0x180012f6c  call    ?GetDevice@MidiLoopbackDeviceTable@@QEAAPEAVMidiLoopbackDevice@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MidiLoopbackDeviceTable::GetDevice(std::wstring)
0x180012f71  mov     r14, rax
0x180012f74  test    rdi, rdi
0x180012f77  jz      short loc_180012FAF
0x180012f79  or      ebx, 0FFFFFFFFh
0x180012f7c  mov     ecx, ebx
0x180012f7e  lock xadd [rdi+8], ecx
0x180012f83  add     ecx, ebx
0x180012f85  jnz     short loc_180012FAF
0x180012f87  mov     rdx, [rdi]
0x180012f8a  mov     rcx, rdi
0x180012f8d  mov     rax, [rdx]
0x180012f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f95  mov     eax, ebx
0x180012f97  lock xadd [rdi+0Ch], eax
0x180012f9c  add     eax, ebx
0x180012f9e  jnz     short loc_180012FAF
0x180012fa0  mov     rax, [rdi]
0x180012fa3  mov     rcx, rdi
0x180012fa6  mov     rax, [rax+8]
0x180012faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012faf  test    r14, r14
0x180012fb2  jz      short loc_180012FC0
0x180012fb4  mov     rcx, [r14+1D0h]
0x180012fbb  jmp     loc_180012EA1
0x180012fc0  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180012fc5  mov     rcx, [rax+8]
0x180012fc9  mov     eax, [rcx]
0x180012fcb  cmp     eax, 2
0x180012fce  jbe     short loc_18001302C
0x180012fd0  lea     rax, aSendBToAUnable; "Send B to A : Unable to find endpoint d"...
0x180012fd7  mov     [rbp+arg_10], rax
0x180012fdb  lea     rax, [rsi+50h]
0x180012fdf  cmp     qword ptr [rax+18h], 7
0x180012fe4  jbe     short loc_180012FE9
0x180012fe6  mov     rax, [rax]
0x180012fe9  mov     [rbp+var_30], rax
0x180012fed  lea     rdx, qword_180057EC0
0x180012ff4  lea     rax, aCmidi2loopback_0; "CMidi2LoopbackMidiBidi::SendMidiMessage"
0x180012ffb  mov     [rbp+var_40], rax
0x180012fff  lea     rax, [rbp+arg_10]
0x180013003  mov     [rsp+80h+var_48], rax
0x180013008  lea     rax, [rbp+var_30]
0x18001300c  mov     [rsp+80h+var_50], rax
0x180013011  lea     rax, [rbp+var_38]
0x180013015  mov     [rsp+80h+var_58], rax
0x18001301a  lea     rax, [rbp+var_40]
0x18001301e  mov     [rsp+80h+var_60], rax
0x180013023  mov     [rbp+var_38], rsi
0x180013027  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001302c  mov     eax, 80004005h
0x180013031  lea     r11, [rsp+80h+var_s0]
0x180013039  mov     rbx, [r11+30h]
0x18001303d  mov     rsi, [r11+38h]
0x180013041  mov     rsp, r11
0x180013044  pop     r15
0x180013046  pop     r14
0x180013048  pop     r12
0x18001304a  pop     rdi
0x18001304b  pop     rbp
0x18001304c  retn
```

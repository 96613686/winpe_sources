# CMidi2VirtualMidiBidi::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18001b5f0`
- end: `0x18001b761`
- name: `?SendMidiMessage@CMidi2VirtualMidiBidi@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `369`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001ab8`
- `0x180009784`
- `0x18000b5f8`
- `0x18001b5f0`
- `0x180021010`

## string_xrefs

- `0x18001b6c6`: `No linked connections`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiBidi::SendMidiMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _DWORD *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  _QWORD *v14; // rax
  int v15; // [rsp+20h] [rbp-31h]
  int v16; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+68h] [rbp+17h] BYREF
  __int64 v18; // [rsp+70h] [rbp+1Fh] BYREF
  _QWORD *v19; // [rsp+78h] [rbp+27h] BYREF
  const wchar_t *v20; // [rsp+80h] [rbp+2Fh] BYREF
  __int64 v21; // [rsp+88h] [rbp+37h] BYREF
  int v22[2]; // [rsp+90h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]
  unsigned int v24; // [rsp+C0h] [rbp+6Fh] BYREF

  if ( a3 )
  {
    if ( a4 >= 4 )
    {
      v9 = *(_QWORD *)(a1 + 32);
      if ( v9 )
      {
        v15 = a5;
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, a2);
        if ( v7 < 0 )
        {
          v8 = 175;
          goto LABEL_15;
        }
      }
      else if ( !*(_BYTE *)(a1 + 104) )
      {
        v11 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
        if ( *v11 > 5u )
        {
          v24 = a4;
          v17 = a1 + 88;
          v18 = a5;
          v16 = *(unsigned __int8 *)(a1 + 104);
          v14 = (_QWORD *)(a1 + 56);
          if ( *(_QWORD *)(a1 + 80) > 7u )
            v14 = (_QWORD *)*v14;
          v19 = v14;
          v21 = a1;
          v20 = L"No linked connections";
          *(_QWORD *)v22 = "CMidi2VirtualMidiBidi::SendMidiMessage";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
            (_DWORD)v11,
            (unsigned int)byte_18002708D,
            v12,
            v13,
            (__int64)v22,
            (__int64)&v21,
            (__int64)&v20,
            (__int64)&v19,
            (__int64)&v16,
            (__int64)&v24,
            (__int64)&v18,
            (__int64)&v17);
        }
        v7 = -2147418113;
        v8 = 201;
        goto LABEL_15;
      }
      return 0;
    }
    v7 = -2147024809;
    v8 = 171;
  }
  else
  {
    v7 = -2147024809;
    v8 = 170;
  }
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidibidi.cpp",
    (const char *)(unsigned int)v7,
    v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b5f0  mov     [rsp-8+arg_0], rbx
0x18001b5f5  mov     [rsp-8+arg_8], rdi
0x18001b5fa  push    rbp
0x18001b5fb  lea     rbp, [rsp-4Fh]
0x18001b600  sub     rsp, 0A0h
0x18001b607  mov     edi, r9d
0x18001b60a  mov     r10d, edx
0x18001b60d  mov     rbx, rcx
0x18001b610  test    r8, r8
0x18001b613  jnz     short loc_18001B624
0x18001b615  mov     ebx, 80070057h
0x18001b61a  mov     edx, 0AAh
0x18001b61f  jmp     loc_18001B737
0x18001b624  cmp     edi, 4
0x18001b627  jnb     short loc_18001B638
0x18001b629  mov     ebx, 80070057h
0x18001b62e  mov     edx, 0ABh
0x18001b633  jmp     loc_18001B737
0x18001b638  mov     rcx, [rcx+20h]
0x18001b63c  test    rcx, rcx
0x18001b63f  jz      short loc_18001B672
0x18001b641  mov     rdx, [rbx+30h]
0x18001b645  mov     rax, [rcx]
0x18001b648  mov     [rsp+0A0h+var_78], rdx
0x18001b64d  mov     rdx, [rbp+4Fh+arg_20]
0x18001b651  mov     qword ptr [rsp+0A0h+var_80], rdx
0x18001b656  mov     edx, r10d
0x18001b659  mov     rax, [rax+18h]
0x18001b65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b662  mov     ebx, eax
0x18001b664  test    eax, eax
0x18001b666  jns     short loc_18001B678
0x18001b668  mov     edx, 0AFh
0x18001b66d  jmp     loc_18001B737
0x18001b672  cmp     byte ptr [rbx+68h], 0
0x18001b676  jz      short loc_18001B67F
0x18001b678  xor     eax, eax
0x18001b67a  jmp     loc_18001B74C
0x18001b67f  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001b684  mov     rcx, [rax+8]
0x18001b688  mov     eax, [rcx]
0x18001b68a  cmp     eax, 5
0x18001b68d  jbe     loc_18001B72D
0x18001b693  lea     rax, [rbx+58h]
0x18001b697  mov     [rbp+4Fh+arg_10], edi
0x18001b69a  mov     [rbp+4Fh+var_38], rax
0x18001b69e  mov     rax, [rbp+4Fh+arg_20]
0x18001b6a2  mov     [rbp+4Fh+var_30], rax
0x18001b6a6  movzx   eax, byte ptr [rbx+68h]
0x18001b6aa  mov     [rbp+4Fh+var_40], eax
0x18001b6ad  lea     rax, [rbx+38h]
0x18001b6b1  cmp     qword ptr [rax+18h], 7
0x18001b6b6  jbe     short loc_18001B6BB
0x18001b6b8  mov     rax, [rax]
0x18001b6bb  mov     [rbp+4Fh+var_28], rax
0x18001b6bf  lea     rdx, byte_18002708D
0x18001b6c6  lea     rax, aNoLinkedConnec; "No linked connections"
0x18001b6cd  mov     [rbp+4Fh+var_18], rbx
0x18001b6d1  mov     [rbp+4Fh+var_20], rax
0x18001b6d5  lea     rax, aCmidi2virtualm_1; "CMidi2VirtualMidiBidi::SendMidiMessage"
0x18001b6dc  mov     qword ptr [rbp+4Fh+var_10], rax
0x18001b6e0  lea     rax, [rbp+4Fh+var_38]
0x18001b6e4  mov     [rsp+0A0h+var_48], rax
0x18001b6e9  lea     rax, [rbp+4Fh+var_30]
0x18001b6ed  mov     [rsp+0A0h+var_50], rax
0x18001b6f2  lea     rax, [rbp+4Fh+arg_10]
0x18001b6f6  mov     [rsp+0A0h+var_58], rax
0x18001b6fb  lea     rax, [rbp+4Fh+var_40]
0x18001b6ff  mov     [rsp+0A0h+var_60], rax
0x18001b704  lea     rax, [rbp+4Fh+var_28]
0x18001b708  mov     [rsp+0A0h+var_68], rax
0x18001b70d  lea     rax, [rbp+4Fh+var_20]
0x18001b711  mov     [rsp+0A0h+var_70], rax
0x18001b716  lea     rax, [rbp+4Fh+var_18]
0x18001b71a  mov     [rsp+0A0h+var_78], rax
0x18001b71f  lea     rax, [rbp+4Fh+var_10]
0x18001b723  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18001b728  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U4@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@64AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18001b72d  mov     ebx, 8000FFFFh
0x18001b732  mov     edx, 0C9h; void *
0x18001b737  mov     rcx, [rbp+57h]; this
0x18001b73b  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001b742  mov     r9d, ebx; char *
0x18001b745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b74a  mov     eax, ebx
0x18001b74c  lea     r11, [rsp+0A0h+var_s0]
0x18001b754  mov     rbx, [r11+10h]
0x18001b758  mov     rdi, [r11+18h]
0x18001b75c  mov     rsp, r11
0x18001b75f  pop     rbp
0x18001b760  retn
```

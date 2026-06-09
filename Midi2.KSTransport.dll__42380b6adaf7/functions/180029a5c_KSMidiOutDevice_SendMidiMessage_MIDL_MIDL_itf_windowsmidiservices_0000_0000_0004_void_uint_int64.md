# KSMidiOutDevice::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x180029a5c`
- end: `0x180029bee`
- name: `?SendMidiMessage@KSMidiOutDevice@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180015d10`

## callees

- `0x18000a814`
- `0x18001fdb0`
- `0x1800270a8`
- `0x180029a5c`
- `0x18002a0d0`
- `0x18003d298`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029ac4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180029ac4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029a8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029a8e`

## pseudocode

```c
__int64 __fastcall KSMidiOutDevice::SendMidiMessage(__int64 a1, unsigned int a2, void *a3, unsigned int a4, __int64 a5)
{
  RTL_SRWLOCK *v9; // rbx
  int v10; // edi
  __int64 v11; // rdx
  __int64 v13; // rcx
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // ebx
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
  {
    v9 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockShared((PSRWLOCK)(a1 + 8));
    if ( !a4 )
    {
      v10 = -2147024809;
      v11 = 629;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v10,
        v19);
      goto LABEL_5;
    }
    if ( *(_BYTE *)(a1 + 20) )
    {
      v10 = -2147024890;
      v11 = 630;
      goto LABEL_4;
    }
    v13 = *(_QWORD *)(a1 + 88);
    if ( v13 )
    {
      v19 = a5;
      v10 = CMidiXProc::SendMidiMessage(v13, a2, a3, a4);
      v14 = retaddr;
      if ( v10 >= 0 )
        goto LABEL_5;
      v15 = 635;
    }
    else
    {
      v10 = KSMidiOutDevice::WritePacketMidiData((KSMidiOutDevice *)a1, a3, a4, a5);
      v14 = retaddr;
      if ( v10 >= 0 )
      {
LABEL_5:
        if ( v9 )
          ReleaseSRWLockShared(v9);
        return (unsigned int)v10;
      }
      v15 = 642;
    }
    wil::details::in1diag3::_Log_Hr(
      v14,
      (void *)v15,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v10,
      v19);
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)0x80070057LL,
      v19);
    return (unsigned int)v10;
  }
  v16 = *(_QWORD *)(a1 + 88);
  if ( v16 )
  {
    v19 = a5;
    v17 = CMidiXProc::SendMidiMessage(v16, a2, a3, a4);
    if ( v17 < 0 )
    {
      v18 = 654;
LABEL_23:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v17,
        v19);
    }
  }
  else
  {
    v17 = KSMidiOutDevice::WritePacketMidiData((KSMidiOutDevice *)a1, a3, a4, a5);
    if ( v17 < 0 )
    {
      v18 = 661;
      goto LABEL_23;
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180029a5c  push    rbx
0x180029a5e  push    rbp
0x180029a5f  push    rsi
0x180029a60  push    rdi
0x180029a61  push    r14
0x180029a63  sub     rsp, 40h
0x180029a67  mov     esi, r9d
0x180029a6a  mov     rbp, r8
0x180029a6d  mov     r14d, edx
0x180029a70  mov     rdi, rcx
0x180029a73  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180029a7a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180029a7f  test    al, al
0x180029a81  jz      loc_180029B54
0x180029a87  lea     rbx, [rdi+8]
0x180029a8b  mov     rcx, rbx; SRWLock
0x180029a8e  call    cs:__imp_AcquireSRWLockShared
0x180029a94  mov     [rsp+68h+var_38], rbx
0x180029a99  test    esi, esi
0x180029a9b  jnz     short loc_180029AD1
0x180029a9d  mov     edi, 80070057h
0x180029aa2  mov     edx, 275h; void *
0x180029aa7  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029aae  mov     r9d, edi; char *
0x180029ab1  mov     rcx, [rsp+68h]; this
0x180029ab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029abb  nop
0x180029abc  test    rbx, rbx
0x180029abf  jz      short loc_180029ACA
0x180029ac1  mov     rcx, rbx; SRWLock
0x180029ac4  call    cs:__imp_ReleaseSRWLockShared
0x180029aca  mov     eax, edi
0x180029acc  jmp     loc_180029BE3
0x180029ad1  cmp     byte ptr [rdi+14h], 0
0x180029ad5  jz      short loc_180029AE3
0x180029ad7  mov     edi, 80070006h
0x180029adc  mov     edx, 276h
0x180029ae1  jmp     short loc_180029AA7
0x180029ae3  mov     rcx, [rdi+58h]
0x180029ae7  test    rcx, rcx
0x180029aea  jz      short loc_180029B28
0x180029aec  mov     rax, [rsp+68h+arg_20]
0x180029af4  mov     qword ptr [rsp+68h+var_48], rax; int
0x180029af9  mov     r9d, esi
0x180029afc  mov     r8, rbp
0x180029aff  mov     edx, r14d
0x180029b02  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x180029b07  mov     edi, eax
0x180029b09  mov     rcx, [rsp+68h]; this
0x180029b0e  test    eax, eax
0x180029b10  jns     short loc_180029ABC
0x180029b12  mov     edx, 27Bh; void *
0x180029b17  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029b1e  mov     r9d, edi; char *
0x180029b21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029b26  jmp     short loc_180029ABC
0x180029b28  mov     r9, [rsp+68h+arg_20]; __int64
0x180029b30  mov     r8d, esi; unsigned int
0x180029b33  mov     rdx, rbp; void *
0x180029b36  mov     rcx, rdi; this
0x180029b39  call    ?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z; KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)
0x180029b3e  mov     edi, eax
0x180029b40  mov     rcx, [rsp+68h]
0x180029b45  test    eax, eax
0x180029b47  jns     loc_180029ABC
0x180029b4d  mov     edx, 282h
0x180029b52  jmp     short loc_180029B17
0x180029b54  test    esi, esi
0x180029b56  jnz     short loc_180029B7B
0x180029b58  mov     rcx, [rsp+68h]; this
0x180029b5d  mov     edi, 80070057h
0x180029b62  mov     r9d, edi; char *
0x180029b65  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029b6c  mov     edx, 289h; void *
0x180029b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b76  jmp     loc_180029ACA
0x180029b7b  mov     rcx, [rdi+58h]
0x180029b7f  test    rcx, rcx
0x180029b82  jz      short loc_180029BAC
0x180029b84  mov     rax, [rsp+68h+arg_20]
0x180029b8c  mov     qword ptr [rsp+68h+var_48], rax
0x180029b91  mov     r9d, esi
0x180029b94  mov     r8, rbp
0x180029b97  mov     edx, r14d
0x180029b9a  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x180029b9f  mov     ebx, eax
0x180029ba1  test    eax, eax
0x180029ba3  jns     short loc_180029BE1
0x180029ba5  mov     edx, 28Eh
0x180029baa  jmp     short loc_180029BCD
0x180029bac  mov     r9, [rsp+68h+arg_20]; __int64
0x180029bb4  mov     r8d, esi; unsigned int
0x180029bb7  mov     rdx, rbp; void *
0x180029bba  mov     rcx, rdi; this
0x180029bbd  call    ?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z; KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)
0x180029bc2  mov     ebx, eax
0x180029bc4  test    eax, eax
0x180029bc6  jns     short loc_180029BE1
0x180029bc8  mov     edx, 295h; void *
0x180029bcd  mov     r9d, ebx; char *
0x180029bd0  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029bd7  mov     rcx, [rsp+68h]; this
0x180029bdc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029be1  mov     eax, ebx
0x180029be3  add     rsp, 40h
0x180029be7  pop     r14
0x180029be9  pop     rdi
0x180029bea  pop     rsi
0x180029beb  pop     rbp
0x180029bec  pop     rbx
0x180029bed  retn
```

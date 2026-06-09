# Rdp::Avenc::CProcessorBase<Rdp::Avenc::SinkWriter::CMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::RemoveMonitor(_GUID const &)

- ea: `0x180035250`
- end: `0x180035404`
- name: `?RemoveMonitor@?$CProcessorBase@VCMonitorContext@SinkWriter@Avenc@Rdp@@UIFileIoControlEvents1@34@UIFileIoChannelEvents@34@UISerializePropertyBag@34@@Avenc@Rdp@@QEAAXAEBU_GUID@@@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800356a0`

## callees

- `0x180002be0`
- `0x1800153f8`
- `0x180029180`
- `0x180035250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800353fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800353d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800353d6`

## string_xrefs

- `0x18003539e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x1800352c2`: `Remove monitor context`
- `0x180035386`: `MonitorRemove: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180035392`: `Rdp::Avenc::CProcessorBase<class Rdp::Avenc::SinkWriter::CMonitorContext,struct Rdp::Avenc::IFileIoControlEvents1,struct Rdp::Avenc::IFileIoChannelEvents,struct Rdp::Avenc::ISerializePropertyBag>::RemoveMonitor`

## pseudocode

```c
void __fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::SinkWriter::CMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::RemoveMonitor(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  __int64 v6; // [rsp+28h] [rbp-51h]
  __int64 v7; // [rsp+30h] [rbp-49h]
  __int64 v8; // [rsp+38h] [rbp-41h]
  __int64 v9; // [rsp+40h] [rbp-39h]
  __int64 v10; // [rsp+48h] [rbp-31h]
  __int64 v11; // [rsp+50h] [rbp-29h]
  int v12; // [rsp+58h] [rbp-21h]
  int v13; // [rsp+60h] [rbp-19h]
  int v14; // [rsp+68h] [rbp-11h]
  int v15; // [rsp+70h] [rbp-9h]
  int v16; // [rsp+78h] [rbp-1h]
  const char *v17; // [rsp+80h] [rbp+7h] BYREF
  __int64 v18; // [rsp+88h] [rbp+Fh] BYREF
  const char *v19; // [rsp+90h] [rbp+17h] BYREF
  int v20; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v21; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v22; // [rsp+F0h] [rbp+77h] BYREF
  int *v23; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v20 = *(_DWORD *)(a1 + 160);
    v21 = a2;
    v22 = "Remove monitor context";
    v23 = &xmmword_1800C21A0;
    v17 = "RdpAvenc";
    v19 = "Checkpoint";
    v18 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800AEF8D,
      a3,
      a4,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v16 = *(unsigned __int8 *)(a2 + 15);
  v15 = *(unsigned __int8 *)(a2 + 14);
  v14 = *(unsigned __int8 *)(a2 + 13);
  v13 = *(unsigned __int8 *)(a2 + 12);
  v12 = *(unsigned __int8 *)(a2 + 11);
  LODWORD(v11) = *(unsigned __int8 *)(a2 + 10);
  LODWORD(v10) = *(unsigned __int8 *)(a2 + 9);
  LODWORD(v9) = *(unsigned __int8 *)(a2 + 8);
  LODWORD(v8) = *(unsigned __int16 *)(a2 + 6);
  LODWORD(v7) = *(unsigned __int16 *)(a2 + 4);
  LODWORD(v6) = *(_DWORD *)a2;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"MonitorRemove: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
    "Rdp::Avenc::CProcessorBase<class Rdp::Avenc::SinkWriter::CMonitorContext,struct Rdp::Avenc::IFileIoControlEvents1,st"
    "ruct Rdp::Avenc::IFileIoChannelEvents,struct Rdp::Avenc::ISerializePropertyBag>::RemoveMonitor",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
    0x18Eu,
    v6,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12,
    v13,
    v14,
    v15,
    v16);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 144));
  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::erase(
    a1 + 128,
    a2);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 144));
}

```

## disassembly

```asm
0x180035250  push    rbp
0x180035252  push    rbx
0x180035253  push    rsi
0x180035254  push    rdi
0x180035255  push    r14
0x180035257  push    r15
0x180035259  lea     rbp, [rsp-2Fh]
0x18003525e  sub     rsp, 0A8h
0x180035265  mov     eax, cs:dword_1800C1058
0x18003526b  mov     r14, rdx
0x18003526e  mov     r15, rcx
0x180035271  cmp     eax, 4
0x180035274  jbe     loc_18003533E
0x18003527a  mov     rdx, cs:qword_1800C1070
0x180035281  mov     rcx, 470000000000h
0x18003528b  mov     rax, cs:qword_1800C1068
0x180035292  test    rcx, rax
0x180035295  jz      loc_18003533E
0x18003529b  mov     rax, rdx
0x18003529e  and     rax, rcx
0x1800352a1  cmp     rax, rdx
0x1800352a4  jnz     loc_18003533E
0x1800352aa  mov     eax, [r15+0A0h]
0x1800352b1  lea     rdx, byte_1800AEF8D
0x1800352b8  mov     [rbp+57h+arg_0], eax
0x1800352bb  lea     rcx, dword_1800C1058
0x1800352c2  lea     rax, aRemoveMonitorC; "Remove monitor context"
0x1800352c9  mov     [rbp+57h+arg_8], r14
0x1800352cd  mov     [rbp+57h+arg_10], rax
0x1800352d1  lea     rax, xmmword_1800C21A0
0x1800352d8  mov     [rbp+57h+arg_18], rax
0x1800352dc  lea     rax, aRdpavenc; "RdpAvenc"
0x1800352e3  mov     [rbp+57h+var_50], rax
0x1800352e7  lea     rax, aCheckpoint; "Checkpoint"
0x1800352ee  mov     [rbp+57h+var_40], rax
0x1800352f2  lea     rax, [rbp+57h+arg_8]
0x1800352f6  mov     [rsp+0D0h+var_80], rax
0x1800352fb  lea     rax, [rbp+57h+arg_0]
0x1800352ff  mov     [rsp+0D0h+var_88], rax
0x180035304  lea     rax, [rbp+57h+arg_10]
0x180035308  mov     [rsp+0D0h+var_90], rax
0x18003530d  lea     rax, [rbp+57h+arg_18]
0x180035311  mov     [rsp+0D0h+var_98], rax
0x180035316  lea     rax, [rbp+57h+var_50]
0x18003531a  mov     [rsp+0D0h+var_A0], rax
0x18003531f  lea     rax, [rbp+57h+var_48]
0x180035323  mov     [rsp+0D0h+var_A8], rax
0x180035328  lea     rax, [rbp+57h+var_40]
0x18003532c  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180035331  mov     [rbp+57h+var_48], 1000000h
0x180035339  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18003533e  movzx   eax, byte ptr [r14+0Fh]
0x180035343  movzx   ecx, byte ptr [r14+0Eh]
0x180035348  movzx   edx, byte ptr [r14+0Dh]
0x18003534d  movzx   r8d, byte ptr [r14+0Ch]
0x180035352  movzx   r9d, byte ptr [r14+0Bh]
0x180035357  movzx   r10d, byte ptr [r14+0Ah]
0x18003535c  movzx   r11d, byte ptr [r14+9]
0x180035361  movzx   ebx, byte ptr [r14+8]
0x180035366  movzx   edi, word ptr [r14+6]
0x18003536b  movzx   esi, word ptr [r14+4]
0x180035370  mov     [rsp+0D0h+var_58], eax
0x180035374  mov     eax, [r14]
0x180035377  mov     [rsp+0D0h+var_60], ecx
0x18003537b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180035382  mov     [rsp+0D0h+var_68], edx
0x180035386  lea     rdx, aMonitorremoveI; "MonitorRemove: Id {%08lX-%04hX-%04hX-%0"...
0x18003538d  mov     [rsp+0D0h+var_70], r8d
0x180035392  lea     r8, aRdpAvencCproce_7; "Rdp::Avenc::CProcessorBase<class Rdp::A"...
0x180035399  mov     [rsp+0D0h+var_78], r9d
0x18003539e  lea     r9, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800353a5  mov     dword ptr [rsp+0D0h+var_80], r10d
0x1800353aa  mov     dword ptr [rsp+0D0h+var_88], r11d
0x1800353af  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1800353b3  mov     dword ptr [rsp+0D0h+var_98], edi
0x1800353b7  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800353bb  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800353bf  mov     [rsp+0D0h+var_B0], 18Eh; unsigned int
0x1800353c7  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800353cc  lea     rbx, [r15+90h]
0x1800353d3  mov     rcx, rbx; SRWLock
0x1800353d6  call    cs:__imp_AcquireSRWLockExclusive
0x1800353dc  lea     rcx, [r15+80h]
0x1800353e3  mov     rdx, r14
0x1800353e6  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@UGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::erase(_GUID const &)
0x1800353eb  mov     rcx, rbx
0x1800353ee  add     rsp, 0A8h
0x1800353f5  pop     r15
0x1800353f7  pop     r14
0x1800353f9  pop     rdi
0x1800353fa  pop     rsi
0x1800353fb  pop     rbx
0x1800353fc  pop     rbp
0x1800353fd  jmp     cs:__imp_ReleaseSRWLockExclusive
```

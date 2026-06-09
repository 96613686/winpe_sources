# Rdp::Avenc::CProcessorBase<Rdp::Avenc::Ic3::CMonitorContext,>::RemoveMonitor(_GUID const &)

- ea: `0x180044740`
- end: `0x1800448ec`
- name: `?RemoveMonitor@?$CProcessorBase@VCMonitorContext@Ic3@Avenc@Rdp@@$$V@Avenc@Rdp@@QEAAXAEBU_GUID@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044ec0`

## callees

- `0x180002be0`
- `0x1800153f8`
- `0x180029180`
- `0x180044740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800448e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800448c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800448c0`

## string_xrefs

- `0x18004488e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x1800447b2`: `Remove monitor context`
- `0x180044876`: `MonitorRemove: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180044882`: `Rdp::Avenc::CProcessorBase<class Rdp::Avenc::Ic3::CMonitorContext>::RemoveMonitor`

## pseudocode

```c
void __fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::Ic3::CMonitorContext,>::RemoveMonitor(
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
    v20 = *(_DWORD *)(a1 + 136);
    v21 = a2;
    v22 = "Remove monitor context";
    v23 = &xmmword_1800C21A0;
    v17 = "RdpAvenc";
    v19 = "Checkpoint";
    v18 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800B0357,
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
    "Rdp::Avenc::CProcessorBase<class Rdp::Avenc::Ic3::CMonitorContext>::RemoveMonitor",
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
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 120));
  std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::erase(
    a1 + 104,
    a2);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 120));
}

```

## disassembly

```asm
0x180044740  push    rbp
0x180044742  push    rbx
0x180044743  push    rsi
0x180044744  push    rdi
0x180044745  push    r14
0x180044747  push    r15
0x180044749  lea     rbp, [rsp-2Fh]
0x18004474e  sub     rsp, 0A8h
0x180044755  mov     eax, cs:dword_1800C1058
0x18004475b  mov     r14, rdx
0x18004475e  mov     r15, rcx
0x180044761  cmp     eax, 4
0x180044764  jbe     loc_18004482E
0x18004476a  mov     rdx, cs:qword_1800C1070
0x180044771  mov     rcx, 470000000000h
0x18004477b  mov     rax, cs:qword_1800C1068
0x180044782  test    rcx, rax
0x180044785  jz      loc_18004482E
0x18004478b  mov     rax, rdx
0x18004478e  and     rax, rcx
0x180044791  cmp     rax, rdx
0x180044794  jnz     loc_18004482E
0x18004479a  mov     eax, [r15+88h]
0x1800447a1  lea     rdx, byte_1800B0357
0x1800447a8  mov     [rbp+57h+arg_0], eax
0x1800447ab  lea     rcx, dword_1800C1058
0x1800447b2  lea     rax, aRemoveMonitorC; "Remove monitor context"
0x1800447b9  mov     [rbp+57h+arg_8], r14
0x1800447bd  mov     [rbp+57h+arg_10], rax
0x1800447c1  lea     rax, xmmword_1800C21A0
0x1800447c8  mov     [rbp+57h+arg_18], rax
0x1800447cc  lea     rax, aRdpavenc; "RdpAvenc"
0x1800447d3  mov     [rbp+57h+var_50], rax
0x1800447d7  lea     rax, aCheckpoint; "Checkpoint"
0x1800447de  mov     [rbp+57h+var_40], rax
0x1800447e2  lea     rax, [rbp+57h+arg_8]
0x1800447e6  mov     [rsp+0D0h+var_80], rax
0x1800447eb  lea     rax, [rbp+57h+arg_0]
0x1800447ef  mov     [rsp+0D0h+var_88], rax
0x1800447f4  lea     rax, [rbp+57h+arg_10]
0x1800447f8  mov     [rsp+0D0h+var_90], rax
0x1800447fd  lea     rax, [rbp+57h+arg_18]
0x180044801  mov     [rsp+0D0h+var_98], rax
0x180044806  lea     rax, [rbp+57h+var_50]
0x18004480a  mov     [rsp+0D0h+var_A0], rax
0x18004480f  lea     rax, [rbp+57h+var_48]
0x180044813  mov     [rsp+0D0h+var_A8], rax
0x180044818  lea     rax, [rbp+57h+var_40]
0x18004481c  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180044821  mov     [rbp+57h+var_48], 1000000h
0x180044829  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004482e  movzx   eax, byte ptr [r14+0Fh]
0x180044833  movzx   ecx, byte ptr [r14+0Eh]
0x180044838  movzx   edx, byte ptr [r14+0Dh]
0x18004483d  movzx   r8d, byte ptr [r14+0Ch]
0x180044842  movzx   r9d, byte ptr [r14+0Bh]
0x180044847  movzx   r10d, byte ptr [r14+0Ah]
0x18004484c  movzx   r11d, byte ptr [r14+9]
0x180044851  movzx   ebx, byte ptr [r14+8]
0x180044856  movzx   edi, word ptr [r14+6]
0x18004485b  movzx   esi, word ptr [r14+4]
0x180044860  mov     [rsp+0D0h+var_58], eax
0x180044864  mov     eax, [r14]
0x180044867  mov     [rsp+0D0h+var_60], ecx
0x18004486b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180044872  mov     [rsp+0D0h+var_68], edx
0x180044876  lea     rdx, aMonitorremoveI; "MonitorRemove: Id {%08lX-%04hX-%04hX-%0"...
0x18004487d  mov     [rsp+0D0h+var_70], r8d
0x180044882  lea     r8, aRdpAvencCproce_1; "Rdp::Avenc::CProcessorBase<class Rdp::A"...
0x180044889  mov     [rsp+0D0h+var_78], r9d
0x18004488e  lea     r9, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180044895  mov     dword ptr [rsp+0D0h+var_80], r10d
0x18004489a  mov     dword ptr [rsp+0D0h+var_88], r11d
0x18004489f  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1800448a3  mov     dword ptr [rsp+0D0h+var_98], edi
0x1800448a7  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800448ab  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800448af  mov     [rsp+0D0h+var_B0], 18Eh; unsigned int
0x1800448b7  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800448bc  lea     rcx, [r15+78h]; SRWLock
0x1800448c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800448c6  lea     rcx, [r15+68h]
0x1800448ca  mov     rdx, r14
0x1800448cd  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@UGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::erase(_GUID const &)
0x1800448d2  lea     rcx, [r15+78h]
0x1800448d6  add     rsp, 0A8h
0x1800448dd  pop     r15
0x1800448df  pop     r14
0x1800448e1  pop     rdi
0x1800448e2  pop     rsi
0x1800448e3  pop     rbx
0x1800448e4  pop     rbp
0x1800448e5  jmp     cs:__imp_ReleaseSRWLockExclusive
```

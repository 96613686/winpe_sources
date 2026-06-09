# SendAggregatedCopyStatsTelemetry

- ea: `0x14001efa4`
- end: `0x14001f304`
- name: `SendAggregatedCopyStatsTelemetry`
- size: `864`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001fe80`

## callees

- `0x140001724`
- `0x140004054`
- `0x14000405c`
- `0x140005c20`
- `0x14001efa4`
- `0x14001fbd0`
- `0x140020748`
- `0x14002085c`

## pseudocode

```c
void SendAggregatedCopyStatsTelemetry()
{
  struct CCopyControl *Instance; // rax
  struct CCopyControl *v1; // rax
  struct CCopyControl *v2; // rax
  struct CCopyControl *v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v5; // [rsp+110h] [rbp-80h] BYREF
  int v6; // [rsp+114h] [rbp-7Ch] BYREF
  int v7; // [rsp+118h] [rbp-78h] BYREF
  int v8; // [rsp+11Ch] [rbp-74h] BYREF
  int v9; // [rsp+120h] [rbp-70h] BYREF
  int v10; // [rsp+124h] [rbp-6Ch] BYREF
  int v11; // [rsp+128h] [rbp-68h] BYREF
  int v12; // [rsp+12Ch] [rbp-64h] BYREF
  int v13; // [rsp+130h] [rbp-60h] BYREF
  int v14; // [rsp+134h] [rbp-5Ch] BYREF
  int v15; // [rsp+138h] [rbp-58h] BYREF
  int v16; // [rsp+13Ch] [rbp-54h] BYREF
  int v17; // [rsp+140h] [rbp-50h] BYREF
  int v18; // [rsp+144h] [rbp-4Ch] BYREF
  int v19; // [rsp+148h] [rbp-48h] BYREF
  int v20; // [rsp+14Ch] [rbp-44h] BYREF
  int v21; // [rsp+150h] [rbp-40h] BYREF
  int v22; // [rsp+154h] [rbp-3Ch] BYREF
  int v23; // [rsp+158h] [rbp-38h] BYREF
  int v24; // [rsp+15Ch] [rbp-34h] BYREF
  int v25; // [rsp+160h] [rbp-30h] BYREF
  __int64 v26; // [rsp+168h] [rbp-28h] BYREF
  __int64 v27; // [rsp+170h] [rbp-20h] BYREF
  __int64 v28; // [rsp+178h] [rbp-18h] BYREF
  __int64 v29; // [rsp+180h] [rbp-10h] BYREF
  __int64 v30; // [rsp+188h] [rbp-8h] BYREF
  __int64 v31; // [rsp+190h] [rbp+0h] BYREF
  __int64 v32; // [rsp+198h] [rbp+8h] BYREF
  __int64 v33; // [rsp+1A0h] [rbp+10h] BYREF
  __int64 v34; // [rsp+1A8h] [rbp+18h] BYREF
  __int64 v35; // [rsp+1B0h] [rbp+20h]
  __int64 v36; // [rsp+1B8h] [rbp+28h] BYREF
  __int64 v37; // [rsp+1C0h] [rbp+30h]
  __int64 v38; // [rsp+1C8h] [rbp+38h] BYREF
  __int64 v39; // [rsp+1D0h] [rbp+40h]
  __int64 v40; // [rsp+1D8h] [rbp+48h] BYREF
  __int64 v41; // [rsp+1E0h] [rbp+50h]

  std::chrono::steady_clock::now(&v26);
  if ( (v26 - qword_14003DBA8) / 60000000000LL >= 58 )
  {
    qword_14003DBA8 = v26;
    v40 = 0;
    v41 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v34 = 0;
    v35 = 0;
    Instance = CCopyControl::GetInstance();
    CCopyControl::GetStats(Instance, 0, &v40);
    v1 = CCopyControl::GetInstance();
    CCopyControl::GetStats(v1, 2, &v36);
    v2 = CCopyControl::GetInstance();
    CCopyControl::GetStats(v2, 1, &v38);
    v3 = CCopyControl::GetInstance();
    CCopyControl::GetStats(v3, 3, &v34);
    v4 = g_pcsAsimovLock;
    if ( g_pcsAsimovLock )
    {
      CommonUtil::CMpCriticalSection::lock(g_pcsAsimovLock);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
        && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider
                                                                                                 + 24LL) )
      {
        v5 = v35;
        v6 = HIDWORD(v34);
        v7 = v34;
        v8 = HIDWORD(v35);
        v9 = v37;
        v10 = HIDWORD(v36);
        v11 = v36;
        v12 = HIDWORD(v37);
        v13 = HIDWORD(v38);
        v14 = v38;
        v15 = HIDWORD(v39);
        v16 = HIDWORD(v40);
        v17 = v40;
        v18 = HIDWORD(v41);
        v33 = 0x2000000;
        v19 = *((_DWORD *)g_aAsimov + 18);
        v20 = *((_DWORD *)g_aAsimov + 17);
        v21 = *((_DWORD *)g_aAsimov + 16);
        v22 = *((unsigned __int8 *)g_aAsimov + 60);
        v23 = *((unsigned __int8 *)g_aAsimov + 59);
        v24 = *((unsigned __int8 *)g_aAsimov + 58);
        v25 = *((unsigned __int8 *)g_aAsimov + 57);
        LODWORD(v26) = *((unsigned __int8 *)g_aAsimov + 56);
        v27 = *((_QWORD *)g_aAsimov + 6);
        v28 = *((_QWORD *)g_aAsimov + 5);
        v29 = *((_QWORD *)g_aAsimov + 4);
        v30 = *((_QWORD *)g_aAsimov + 3);
        v31 = *((_QWORD *)g_aAsimov + 2);
        v32 = *((_QWORD *)g_aAsimov + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          g_hMpAsimovProvider,
          (int)&byte_140036567,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v12,
          (__int64)&v11,
          (__int64)&v10,
          (__int64)&v9,
          (__int64)&v8,
          (__int64)&v7,
          (__int64)&v6,
          (__int64)&v5);
      }
      CommonUtil::CMpCriticalSection::unlock(v4);
    }
  }
}

```

## disassembly

```asm
0x14001efa4  mov     [rsp-8+arg_0], rbx
0x14001efa9  mov     [rsp-8+arg_8], rdi
0x14001efae  push    rbp
0x14001efaf  lea     rbp, [rsp-60h]
0x14001efb4  sub     rsp, 1F0h
0x14001efbb  mov     rax, cs:__security_cookie
0x14001efc2  xor     rax, rsp
0x14001efc5  mov     [rbp+60h+var_8], rax
0x14001efc9  lea     rcx, [rbp+60h+var_88]
0x14001efcd  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14001efd2  mov     rcx, [rbp+60h+var_88]
0x14001efd6  mov     r8, 0DF8475800h
0x14001efe0  mov     rax, rcx
0x14001efe3  sub     rax, cs:qword_14003DBA8
0x14001efea  cqo
0x14001efec  idiv    r8
0x14001efef  cmp     eax, 3Ah ; ':'
0x14001eff2  jl      loc_14001F2E3
0x14001eff8  xor     edi, edi
0x14001effa  mov     cs:qword_14003DBA8, rcx
0x14001f001  mov     [rbp+60h+var_18], rdi
0x14001f005  mov     [rbp+60h+var_10], rdi
0x14001f009  mov     [rbp+60h+var_38], rdi
0x14001f00d  mov     [rbp+60h+var_30], rdi
0x14001f011  mov     [rbp+60h+var_28], rdi
0x14001f015  mov     [rbp+60h+var_20], rdi
0x14001f019  mov     [rbp+60h+var_48], rdi
0x14001f01d  mov     [rbp+60h+var_40], rdi
0x14001f021  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f026  lea     r8, [rbp+60h+var_18]
0x14001f02a  xor     edx, edx
0x14001f02c  mov     rcx, rax
0x14001f02f  call    ?GetStats@CCopyControl@@QEAAXW4tagMPCOPYFILEAPI@@AEAUCopyStats@1@_N@Z; CCopyControl::GetStats(tagMPCOPYFILEAPI,CCopyControl::CopyStats &,bool)
0x14001f034  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f039  lea     r8, [rbp+60h+var_38]
0x14001f03d  mov     rcx, rax
0x14001f040  lea     edx, [rdi+2]
0x14001f043  call    ?GetStats@CCopyControl@@QEAAXW4tagMPCOPYFILEAPI@@AEAUCopyStats@1@_N@Z; CCopyControl::GetStats(tagMPCOPYFILEAPI,CCopyControl::CopyStats &,bool)
0x14001f048  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f04d  lea     r8, [rbp+60h+var_28]
0x14001f051  mov     rcx, rax
0x14001f054  lea     edx, [rdi+1]
0x14001f057  call    ?GetStats@CCopyControl@@QEAAXW4tagMPCOPYFILEAPI@@AEAUCopyStats@1@_N@Z; CCopyControl::GetStats(tagMPCOPYFILEAPI,CCopyControl::CopyStats &,bool)
0x14001f05c  call    ?GetInstance@CCopyControl@@SAAEAV1@XZ; CCopyControl::GetInstance(void)
0x14001f061  lea     r8, [rbp+60h+var_48]
0x14001f065  mov     rcx, rax
0x14001f068  lea     edx, [rdi+3]
0x14001f06b  call    ?GetStats@CCopyControl@@QEAAXW4tagMPCOPYFILEAPI@@AEAUCopyStats@1@_N@Z; CCopyControl::GetStats(tagMPCOPYFILEAPI,CCopyControl::CopyStats &,bool)
0x14001f070  mov     rbx, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x14001f077  test    rbx, rbx
0x14001f07a  jz      loc_14001F2E3
0x14001f080  mov     rcx, rbx; lpCriticalSection
0x14001f083  call    ?lock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::lock(void)
0x14001f088  mov     r8, cs:g_hMpAsimovProvider
0x14001f08f  cmp     dword ptr [r8], 5
0x14001f093  jbe     loc_14001F2DB
0x14001f099  mov     rcx, 400000000000h
0x14001f0a3  test    [r8+10h], rcx
0x14001f0a7  jz      loc_14001F2DB
0x14001f0ad  mov     rax, [r8+18h]
0x14001f0b1  and     rax, rcx
0x14001f0b4  cmp     rax, [r8+18h]
0x14001f0b8  jnz     loc_14001F2DB
0x14001f0be  mov     eax, dword ptr [rbp+60h+var_40]
0x14001f0c1  nop
0x14001f0c2  mov     dword ptr [rbp+60h+var_E0], eax
0x14001f0c5  mov     eax, dword ptr [rbp+60h+var_48+4]
0x14001f0c8  nop
0x14001f0c9  mov     dword ptr [rbp+60h+var_E0+4], eax
0x14001f0cc  mov     eax, dword ptr [rbp+60h+var_48]
0x14001f0cf  nop
0x14001f0d0  mov     dword ptr [rbp+60h+var_D8], eax
0x14001f0d3  mov     eax, dword ptr [rbp+60h+var_40+4]
0x14001f0d6  nop
0x14001f0d7  mov     dword ptr [rbp+60h+var_D8+4], eax
0x14001f0da  mov     eax, dword ptr [rbp+60h+var_30]
0x14001f0dd  nop
0x14001f0de  mov     [rbp+60h+var_D0], eax
0x14001f0e1  mov     eax, dword ptr [rbp+60h+var_38+4]
0x14001f0e4  nop
0x14001f0e5  mov     [rbp+60h+var_CC], eax
0x14001f0e8  mov     eax, dword ptr [rbp+60h+var_38]
0x14001f0eb  nop
0x14001f0ec  mov     [rbp+60h+var_C8], eax
0x14001f0ef  mov     eax, dword ptr [rbp+60h+var_30+4]
0x14001f0f2  nop
0x14001f0f3  mov     [rbp+60h+var_C4], eax
0x14001f0f6  mov     eax, dword ptr [rbp+60h+var_28+4]
0x14001f0f9  nop
0x14001f0fa  mov     [rbp+60h+var_C0], eax
0x14001f0fd  mov     eax, dword ptr [rbp+60h+var_28]
0x14001f100  nop
0x14001f101  mov     [rbp+60h+var_BC], eax
0x14001f104  mov     eax, dword ptr [rbp+60h+var_20+4]
0x14001f107  nop
0x14001f108  mov     [rbp+60h+var_B8], eax
0x14001f10b  mov     eax, dword ptr [rbp+60h+var_18+4]
0x14001f10e  nop
0x14001f10f  mov     [rbp+60h+var_B4], eax
0x14001f112  mov     eax, dword ptr [rbp+60h+var_18]
0x14001f115  nop
0x14001f116  mov     [rbp+60h+var_B0], eax
0x14001f119  mov     eax, dword ptr [rbp+60h+var_10+4]
0x14001f11c  nop
0x14001f11d  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x14001f124  mov     [rbp+60h+var_AC], eax
0x14001f127  mov     [rbp+60h+var_50], 2000000h
0x14001f12f  mov     eax, [rcx+48h]
0x14001f132  mov     [rbp+60h+var_A8], eax
0x14001f135  mov     eax, [rcx+44h]
0x14001f138  mov     [rbp+60h+var_A4], eax
0x14001f13b  mov     eax, [rcx+40h]
0x14001f13e  mov     [rbp+60h+var_A0], eax
0x14001f141  movzx   eax, byte ptr [rcx+3Ch]
0x14001f145  mov     [rbp+60h+var_9C], eax
0x14001f148  movzx   eax, byte ptr [rcx+3Bh]
0x14001f14c  mov     [rbp+60h+var_98], eax
0x14001f14f  movzx   eax, byte ptr [rcx+3Ah]
0x14001f153  mov     [rbp+60h+var_94], eax
0x14001f156  movzx   eax, byte ptr [rcx+39h]
0x14001f15a  mov     [rbp+60h+var_90], eax
0x14001f15d  movzx   eax, byte ptr [rcx+38h]
0x14001f161  mov     dword ptr [rbp+60h+var_88], eax
0x14001f164  mov     rax, [rcx+30h]
0x14001f168  mov     [rbp+60h+var_80], rax
0x14001f16c  mov     rax, [rcx+28h]
0x14001f170  mov     [rbp+60h+var_78], rax
0x14001f174  mov     rax, [rcx+20h]
0x14001f178  mov     [rbp+60h+var_70], rax
0x14001f17c  mov     rax, [rcx+18h]
0x14001f180  mov     [rbp+60h+var_68], rax
0x14001f184  mov     rax, [rcx+10h]
0x14001f188  mov     [rbp+60h+var_60], rax
0x14001f18c  mov     rax, [rcx+8]
0x14001f190  mov     [rbp+60h+var_58], rax
0x14001f194  lea     rax, [rbp+60h+var_E0]
0x14001f198  mov     [rsp+1F0h+var_F0], rax; __int64
0x14001f1a0  lea     rax, [rbp+60h+var_E0+4]
0x14001f1a4  mov     [rsp+1F0h+var_F8], rax; __int64
0x14001f1ac  lea     rax, [rbp+60h+var_D8]
0x14001f1b0  mov     [rsp+1F0h+var_100], rax; __int64
0x14001f1b8  lea     rax, [rbp+60h+var_D8+4]
0x14001f1bc  mov     [rsp+1F0h+var_108], rax; __int64
0x14001f1c4  lea     rax, [rbp+60h+var_D0]
0x14001f1c8  mov     [rsp+1F0h+var_110], rax; __int64
0x14001f1d0  lea     rdx, byte_140036567; int
0x14001f1d7  lea     rax, [rbp+60h+var_CC]
0x14001f1db  mov     rcx, r8; int
0x14001f1de  mov     [rsp+1F0h+var_118], rax; __int64
0x14001f1e6  lea     rax, [rbp+60h+var_C8]
0x14001f1ea  mov     [rsp+1F0h+var_120], rax; __int64
0x14001f1f2  lea     rax, [rbp+60h+var_C4]
0x14001f1f6  mov     [rsp+1F0h+var_128], rax; __int64
0x14001f1fe  lea     rax, [rbp+60h+var_C0]
0x14001f202  mov     [rsp+1F0h+var_130], rax; __int64
0x14001f20a  lea     rax, [rbp+60h+var_BC]
0x14001f20e  mov     [rsp+1F0h+var_138], rax; __int64
0x14001f216  lea     rax, [rbp+60h+var_B8]
0x14001f21a  mov     [rsp+1F0h+var_140], rax; __int64
0x14001f222  lea     rax, [rbp+60h+var_B4]
0x14001f226  mov     [rsp+1F0h+var_148], rax; __int64
0x14001f22e  lea     rax, [rbp+60h+var_B0]
0x14001f232  mov     [rsp+1F0h+var_150], rax; __int64
0x14001f23a  lea     rax, [rbp+60h+var_AC]
0x14001f23e  mov     [rsp+1F0h+var_158], rax; __int64
0x14001f246  lea     rax, [rbp+60h+var_A8]
0x14001f24a  mov     [rsp+1F0h+var_160], rax; __int64
0x14001f252  lea     rax, [rbp+60h+var_A4]
0x14001f256  mov     [rsp+1F0h+var_168], rax; __int64
0x14001f25e  lea     rax, [rbp+60h+var_A0]
0x14001f262  mov     [rsp+1F0h+var_170], rax; __int64
0x14001f26a  lea     rax, [rbp+60h+var_9C]
0x14001f26e  mov     [rsp+1F0h+var_178], rax; __int64
0x14001f273  lea     rax, [rbp+60h+var_98]
0x14001f277  mov     [rsp+1F0h+var_180], rax; __int64
0x14001f27c  lea     rax, [rbp+60h+var_94]
0x14001f280  mov     [rsp+1F0h+var_188], rax; __int64
0x14001f285  lea     rax, [rbp+60h+var_90]
0x14001f289  mov     [rsp+1F0h+var_190], rax; __int64
0x14001f28e  lea     rax, [rbp+60h+var_88]
0x14001f292  mov     [rsp+1F0h+var_198], rax; __int64
0x14001f297  lea     rax, [rbp+60h+var_80]
0x14001f29b  mov     [rsp+1F0h+var_1A0], rax; __int64
0x14001f2a0  lea     rax, [rbp+60h+var_78]
0x14001f2a4  mov     [rsp+1F0h+var_1A8], rax; __int64
0x14001f2a9  lea     rax, [rbp+60h+var_70]
0x14001f2ad  mov     [rsp+1F0h+var_1B0], rax; __int64
0x14001f2b2  lea     rax, [rbp+60h+var_68]
0x14001f2b6  mov     [rsp+1F0h+var_1B8], rax; __int64
0x14001f2bb  lea     rax, [rbp+60h+var_60]
0x14001f2bf  mov     [rsp+1F0h+var_1C0], rax; __int64
0x14001f2c4  lea     rax, [rbp+60h+var_58]
0x14001f2c8  mov     [rsp+1F0h+var_1C8], rax; __int64
0x14001f2cd  lea     rax, [rbp+60h+var_50]
0x14001f2d1  mov     [rsp+1F0h+var_1D0], rax; __int64
0x14001f2d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@555555555555555555555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001f2db  mov     rcx, rbx; lpCriticalSection
0x14001f2de  call    ?unlock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::unlock(void)
0x14001f2e3  mov     rcx, [rbp+60h+var_8]
0x14001f2e7  xor     rcx, rsp; StackCookie
0x14001f2ea  call    __security_check_cookie
0x14001f2ef  lea     r11, [rsp+1F0h+var_s0]
0x14001f2f7  mov     rbx, [r11+10h]
0x14001f2fb  mov     rdi, [r11+18h]
0x14001f2ff  mov     rsp, r11
0x14001f302  pop     rbp
0x14001f303  retn
```

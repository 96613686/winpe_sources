# wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18001097c`
- end: `0x18001103c`
- name: `?ReportStopActivity@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `1728`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18000da00`
- `0x1800115ac`

## callees

- `0x180001a34`
- `0x180001a44`
- `0x180001a54`
- `0x180001c6c`
- `0x180002d34`
- `0x180002e00`
- `0x18000e010`
- `0x18000e028`
- `0x18000ea48`
- `0x1800102f8`
- `0x18001097c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ee4`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18001097c  mov     [rsp+arg_8], edx
0x180010980  mov     [rsp+arg_0], rcx
0x180010985  sub     rsp, 268h
0x18001098c  cmp     [rsp+268h+arg_8], 0
0x180010994  jge     loc_180011007
0x18001099a  xor     eax, eax
0x18001099c  test    eax, eax
0x18001099e  jz      loc_180011007
0x1800109a4  xor     eax, eax
0x1800109a6  cmp     eax, 1
0x1800109a9  jz      loc_180011007
0x1800109af  mov     rcx, [rsp+268h+arg_0]
0x1800109b7  call    ?GetFailureInfo@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x1800109bc  mov     [rsp+268h+var_160], rax
0x1800109c4  cmp     [rsp+268h+var_160], 0
0x1800109cd  jz      loc_180010E04
0x1800109d3  mov     rax, [rsp+268h+var_160]
0x1800109db  mov     [rsp+268h+var_1C8], rax
0x1800109e3  mov     rax, [rsp+268h+arg_0]
0x1800109eb  mov     [rsp+268h+var_140], rax
0x1800109f3  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x1800109f8  mov     [rsp+268h+var_170], rax
0x180010a00  mov     rax, [rsp+268h+var_170]
0x180010a08  mov     [rsp+268h+var_158], rax
0x180010a10  mov     [rsp+268h+var_1C0], 0
0x180010a1b  mov     rax, [rsp+268h+var_158]
0x180010a23  mov     eax, [rax]
0x180010a25  mov     [rsp+268h+var_1C0], eax
0x180010a2c  mov     eax, [rsp+268h+var_1C0]
0x180010a33  mov     [rsp+268h+var_1B8], eax
0x180010a3a  mov     eax, [rsp+268h+var_1B8]
0x180010a41  cmp     eax, 2
0x180010a44  jbe     loc_180010DEB
0x180010a4a  mov     rdx, cs:qword_180020F3B
0x180010a51  mov     rcx, [rsp+268h+var_170]
0x180010a59  call    _tlgKeywordOn
0x180010a5e  movzx   eax, al
0x180010a61  test    eax, eax
0x180010a63  jz      loc_180010DEB
0x180010a69  mov     rax, [rsp+268h+var_1C8]
0x180010a71  mov     rdx, [rax+78h]
0x180010a75  lea     rcx, [rsp+268h+var_60]
0x180010a7d  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010a82  mov     [rsp+268h+var_138], rax
0x180010a8a  mov     rax, [rsp+268h+var_1C8]
0x180010a92  mov     rdx, [rax+70h]
0x180010a96  lea     rcx, [rsp+268h+var_58]
0x180010a9e  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010aa3  mov     [rsp+268h+var_130], rax
0x180010aab  mov     rax, [rsp+268h+var_1C8]
0x180010ab3  mov     eax, [rax+68h]
0x180010ab6  mov     [rsp+268h+var_1B4], eax
0x180010abd  lea     rdx, [rsp+268h+var_1B4]
0x180010ac5  lea     rcx, [rsp+268h+var_1B0]
0x180010acd  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010ad2  nop
0x180010ad3  lea     rax, [rsp+268h+var_1B0]
0x180010adb  mov     [rsp+268h+var_128], rax
0x180010ae3  mov     rax, [rsp+268h+var_1C8]
0x180010aeb  mov     rdx, [rax+60h]
0x180010aef  lea     rcx, [rsp+268h+var_50]
0x180010af7  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010afc  mov     [rsp+268h+var_120], rax
0x180010b04  mov     rax, [rsp+268h+var_1C8]
0x180010b0c  mov     rdx, [rax+58h]
0x180010b10  lea     rcx, [rsp+268h+var_48]
0x180010b18  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010b1d  mov     [rsp+268h+var_118], rax
0x180010b25  mov     rax, [rsp+268h+var_1C8]
0x180010b2d  mov     eax, [rax+50h]
0x180010b30  mov     [rsp+268h+var_1AC], eax
0x180010b37  lea     rdx, [rsp+268h+var_1AC]
0x180010b3f  lea     rcx, [rsp+268h+var_1A8]
0x180010b47  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010b4c  nop
0x180010b4d  lea     rax, [rsp+268h+var_1A8]
0x180010b55  mov     [rsp+268h+var_110], rax
0x180010b5d  mov     rax, [rsp+268h+var_1C8]
0x180010b65  mov     rdx, [rax+48h]
0x180010b69  lea     rcx, [rsp+268h+var_40]
0x180010b71  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010b76  mov     [rsp+268h+var_108], rax
0x180010b7e  mov     rax, [rsp+268h+var_1C8]
0x180010b86  mov     eax, [rax+20h]
0x180010b89  mov     [rsp+268h+var_1A4], eax
0x180010b90  lea     rdx, [rsp+268h+var_1A4]
0x180010b98  lea     rcx, [rsp+268h+var_1A0]
0x180010ba0  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010ba5  nop
0x180010ba6  lea     rax, [rsp+268h+var_1A0]
0x180010bae  mov     [rsp+268h+var_100], rax
0x180010bb6  mov     rax, [rsp+268h+var_1C8]
0x180010bbe  mov     rdx, [rax+18h]
0x180010bc2  lea     rcx, [rsp+268h+var_38]
0x180010bca  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010bcf  mov     [rsp+268h+var_F8], rax
0x180010bd7  mov     rax, [rsp+268h+var_1C8]
0x180010bdf  mov     eax, [rax]
0x180010be1  mov     [rsp+268h+var_19C], eax
0x180010be8  lea     rdx, [rsp+268h+var_19C]
0x180010bf0  lea     rcx, [rsp+268h+var_198]
0x180010bf8  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010bfd  nop
0x180010bfe  lea     rax, [rsp+268h+var_198]
0x180010c06  mov     [rsp+268h+var_F0], rax
0x180010c0e  mov     rax, [rsp+268h+var_1C8]
0x180010c16  mov     rdx, [rax+80h]
0x180010c1d  lea     rcx, [rsp+268h+var_30]
0x180010c25  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010c2a  mov     [rsp+268h+var_E8], rax
0x180010c32  mov     rax, [rsp+268h+var_1C8]
0x180010c3a  add     rax, 40h ; '@'
0x180010c3e  mov     rdx, rax
0x180010c41  lea     rcx, [rsp+268h+var_194]
0x180010c49  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010c4e  nop
0x180010c4f  lea     rax, [rsp+268h+var_194]
0x180010c57  mov     [rsp+268h+var_E0], rax
0x180010c5f  mov     rax, [rsp+268h+var_1C8]
0x180010c67  mov     rdx, [rax+38h]
0x180010c6b  lea     rcx, [rsp+268h+var_28]
0x180010c73  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010c78  mov     [rsp+268h+var_D8], rax
0x180010c80  mov     rax, [rsp+268h+var_1C8]
0x180010c88  mov     eax, [rax+8]
0x180010c8b  mov     [rsp+268h+var_190], eax
0x180010c92  lea     rdx, [rsp+268h+var_190]
0x180010c9a  lea     rcx, [rsp+268h+var_18C]
0x180010ca2  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010ca7  nop
0x180010ca8  lea     rax, [rsp+268h+var_18C]
0x180010cb0  mov     [rsp+268h+var_D0], rax
0x180010cb8  mov     [rsp+268h+var_150], 1000000h
0x180010cc4  lea     rdx, [rsp+268h+var_150]
0x180010ccc  lea     rcx, [rsp+268h+var_148]
0x180010cd4  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180010cd9  nop
0x180010cda  lea     rax, [rsp+268h+var_148]
0x180010ce2  mov     [rsp+268h+var_C8], rax
0x180010cea  mov     rcx, [rsp+268h+var_140]
0x180010cf2  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180010cf7  mov     [rsp+268h+var_C0], rax
0x180010cff  mov     rax, [rsp+268h+var_138]
0x180010d07  mov     [rsp+268h+var_1D8], rax
0x180010d0f  mov     rax, [rsp+268h+var_130]
0x180010d17  mov     [rsp+268h+var_1E0], rax
0x180010d1f  mov     rax, [rsp+268h+var_128]
0x180010d27  mov     [rsp+268h+var_1E8], rax
0x180010d2f  mov     rax, [rsp+268h+var_120]
0x180010d37  mov     [rsp+268h+var_1F0], rax
0x180010d3c  mov     rax, [rsp+268h+var_118]
0x180010d44  mov     [rsp+268h+var_1F8], rax
0x180010d49  mov     rax, [rsp+268h+var_110]
0x180010d51  mov     [rsp+268h+var_200], rax
0x180010d56  mov     rax, [rsp+268h+var_108]
0x180010d5e  mov     [rsp+268h+var_208], rax
0x180010d63  mov     rax, [rsp+268h+var_100]
0x180010d6b  mov     [rsp+268h+var_210], rax
0x180010d70  mov     rax, [rsp+268h+var_F8]
0x180010d78  mov     [rsp+268h+var_218], rax
0x180010d7d  mov     rax, [rsp+268h+var_F0]
0x180010d85  mov     [rsp+268h+var_220], rax
0x180010d8a  mov     rax, [rsp+268h+var_E8]
0x180010d92  mov     [rsp+268h+var_228], rax
0x180010d97  mov     rax, [rsp+268h+var_E0]
0x180010d9f  mov     [rsp+268h+var_230], rax
0x180010da4  mov     rax, [rsp+268h+var_D8]
0x180010dac  mov     [rsp+268h+var_238], rax
0x180010db1  mov     rax, [rsp+268h+var_D0]
0x180010db9  mov     [rsp+268h+var_240], rax
0x180010dbe  mov     rax, [rsp+268h+var_C8]
0x180010dc6  mov     [rsp+268h+var_248], rax
0x180010dcb  xor     r9d, r9d
0x180010dce  mov     r8, [rsp+268h+var_C0]
0x180010dd6  lea     rdx, byte_180020F38
0x180010ddd  mov     rcx, [rsp+268h+var_170]
0x180010de5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010dea  nop
0x180010deb  xor     eax, eax
0x180010ded  test    eax, eax
0x180010def  jnz     loc_1800109F3
0x180010df5  xor     eax, eax
0x180010df7  test    eax, eax
0x180010df9  jnz     loc_1800109E3
0x180010dff  jmp     loc_180011007
0x180010e04  mov     rax, [rsp+268h+arg_0]
0x180010e0c  mov     [rsp+268h+var_A0], rax
0x180010e14  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x180010e19  mov     [rsp+268h+var_168], rax
0x180010e21  mov     rax, [rsp+268h+var_168]
0x180010e29  mov     [rsp+268h+var_B8], rax
0x180010e31  mov     [rsp+268h+var_1BC], 0
0x180010e3c  mov     rax, [rsp+268h+var_B8]
0x180010e44  mov     eax, [rax]
0x180010e46  mov     [rsp+268h+var_1BC], eax
0x180010e4d  mov     eax, [rsp+268h+var_1BC]
0x180010e54  mov     [rsp+268h+var_188], eax
0x180010e5b  mov     eax, [rsp+268h+var_188]
0x180010e62  cmp     eax, 2
0x180010e65  jbe     loc_180010FF3
0x180010e6b  mov     rdx, cs:qword_180021052
0x180010e72  mov     rcx, [rsp+268h+var_168]
0x180010e7a  call    _tlgKeywordOn
0x180010e7f  movzx   eax, al
0x180010e82  test    eax, eax
0x180010e84  jz      loc_180010FF3
0x180010e8a  mov     rax, [rsp+268h+arg_0]
0x180010e92  mov     rcx, [rax+110h]
0x180010e99  call    ?GetCallContext@?$ActivityData@VControllerHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAPEAVStoredCallContextInfo@details@3@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControllerHostLogging,_TlgReflectorTag_Param0IsProviderType>::GetCallContext(void)
0x180010e9e  mov     rdx, [rax+10h]
0x180010ea2  lea     rcx, [rsp+268h+var_20]
0x180010eaa  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010eaf  mov     [rsp+268h+var_98], rax
0x180010eb7  mov     rax, [rsp+268h+arg_0]
0x180010ebf  mov     rcx, [rax+110h]
0x180010ec6  call    ?GetCallContext@?$ActivityData@VControllerHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAPEAVStoredCallContextInfo@details@3@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControllerHostLogging,_TlgReflectorTag_Param0IsProviderType>::GetCallContext(void)
0x180010ecb  mov     rdx, [rax+8]
0x180010ecf  lea     rcx, [rsp+268h+var_18]
0x180010ed7  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180010edc  mov     [rsp+268h+var_90], rax
0x180010ee4  call    cs:__imp_GetCurrentThreadId
0x180010eea  mov     [rsp+268h+var_184], eax
0x180010ef1  lea     rdx, [rsp+268h+var_184]
0x180010ef9  lea     rcx, [rsp+268h+var_180]
0x180010f01  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010f06  nop
0x180010f07  lea     rax, [rsp+268h+var_180]
0x180010f0f  mov     [rsp+268h+var_88], rax
0x180010f17  mov     eax, [rsp+268h+arg_8]
0x180010f1e  mov     [rsp+268h+var_17C], eax
0x180010f25  lea     rdx, [rsp+268h+var_17C]
0x180010f2d  lea     rcx, [rsp+268h+var_178]
0x180010f35  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180010f3a  nop
0x180010f3b  lea     rax, [rsp+268h+var_178]
0x180010f43  mov     [rsp+268h+var_80], rax
0x180010f4b  mov     [rsp+268h+var_B0], 1000000h
0x180010f57  lea     rdx, [rsp+268h+var_B0]
0x180010f5f  lea     rcx, [rsp+268h+var_A8]
0x180010f67  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180010f6c  nop
0x180010f6d  lea     rax, [rsp+268h+var_A8]
0x180010f75  mov     [rsp+268h+var_78], rax
0x180010f7d  mov     rcx, [rsp+268h+var_A0]
0x180010f85  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180010f8a  mov     [rsp+268h+var_70], rax
0x180010f92  mov     rax, [rsp+268h+var_98]
0x180010f9a  mov     [rsp+268h+var_228], rax
0x180010f9f  mov     rax, [rsp+268h+var_90]
0x180010fa7  mov     [rsp+268h+var_230], rax
0x180010fac  mov     rax, [rsp+268h+var_88]
0x180010fb4  mov     [rsp+268h+var_238], rax
0x180010fb9  mov     rax, [rsp+268h+var_80]
0x180010fc1  mov     [rsp+268h+var_240], rax
0x180010fc6  mov     rax, [rsp+268h+var_78]
0x180010fce  mov     [rsp+268h+var_248], rax
0x180010fd3  xor     r9d, r9d
0x180010fd6  mov     r8, [rsp+268h+var_70]
0x180010fde  lea     rdx, byte_18002104F
0x180010fe5  mov     rcx, [rsp+268h+var_168]
0x180010fed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010ff2  nop
0x180010ff3  xor     eax, eax
0x180010ff5  test    eax, eax
0x180010ff7  jnz     loc_180010E14
0x180010ffd  xor     eax, eax
0x180010fff  test    eax, eax
0x180011001  jnz     loc_180010E04
0x180011007  mov     rax, [rsp+268h+arg_0]
0x18001100f  mov     rax, [rax]
0x180011012  mov     rax, [rax+8]
0x180011016  mov     [rsp+268h+var_68], rax
0x18001101e  mov     rcx, [rsp+268h+arg_0]
0x180011026  mov     rax, [rsp+268h+var_68]
0x18001102e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011033  nop
0x180011034  add     rsp, 268h
0x18001103b  retn
```

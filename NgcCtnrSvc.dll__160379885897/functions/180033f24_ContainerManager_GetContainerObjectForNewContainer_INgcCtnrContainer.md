# ContainerManager::GetContainerObjectForNewContainer(INgcCtnrContainer * *)

- ea: `0x180033f24`
- end: `0x18003417b`
- name: `?GetContainerObjectForNewContainer@ContainerManager@@QEAAJPEAPEAUINgcCtnrContainer@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(ContainerManager *__hidden this, struct INgcCtnrContainer **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800327c8`

## callees

- `0x180001008`
- `0x18000c688`
- `0x18001ced8`
- `0x180023278`
- `0x180023a88`
- `0x180029980`
- `0x180033b94`
- `0x180033f24`
- `0x180055e5c`
- `0x1800597b8`
- `0x18005a124`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800340b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003412b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800340b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003412b`

## string_xrefs

- `0x180033f95`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180034068`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x1800340cc`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerManager::GetContainerObjectForNewContainer(
        ContainerManager *this,
        struct INgcCtnrContainer **a2)
{
  bool v4; // bl
  bool DoesTpmSupportNgcIsoCtnr; // r15
  NgcUtils *v6; // rcx
  bool IsNgcInVsmEnabled; // r14
  NgcUtils *v8; // rcx
  __int64 v9; // rdx
  bool IsSecureBioEnabled; // di
  __int64 v11; // r8
  int exists; // eax
  __int64 v13; // rcx
  __int64 v14; // r9
  int started; // eax
  LPVOID v16; // rcx
  HRESULT v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  LPVOID v20; // rcx
  struct INgcCtnrContainer *v21; // rax
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  bool v25; // [rsp+50h] [rbp-20h] BYREF
  char v26; // [rsp+51h] [rbp-1Fh] BYREF
  int v27; // [rsp+52h] [rbp-1Eh] BYREF
  LPVOID v28; // [rsp+58h] [rbp-18h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  bool v31; // [rsp+B0h] [rbp+40h] BYREF
  bool v32; // [rsp+B8h] [rbp+48h] BYREF

  v28 = 0;
  v4 = 0;
  DoesTpmSupportNgcIsoCtnr = NgcUtils::DoesTpmSupportNgcIsoCtnr(this);
  IsNgcInVsmEnabled = NgcUtils::IsNgcInVsmEnabled(v6);
  IsSecureBioEnabled = NgcUtils::IsSecureBioEnabled(v8);
  LOBYTE(v11) = 1;
  v31 = 1;
  if ( DoesTpmSupportNgcIsoCtnr )
  {
    if ( IsSecureBioEnabled )
    {
      exists = ContainerManager::ExistsVtl0Container(this, &v31);
      if ( exists >= 0 )
      {
        LOBYTE(v11) = v31;
        v4 = !v31;
        goto LABEL_6;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
        (const char *)(unsigned int)exists,
        ppv);
      LOBYTE(v11) = v31;
    }
    v4 = IsNgcInVsmEnabled;
  }
LABEL_6:
  if ( (unsigned int)dword_1800BE0B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0x400000000000LL) )
  {
    v29 = 0x1000000;
    v31 = IsNgcInVsmEnabled;
    v32 = v4;
    v25 = IsSecureBioEnabled;
    v26 = v11;
    LOBYTE(v27) = DoesTpmSupportNgcIsoCtnr;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      v13,
      (__int64)byte_1800A7109,
      v11,
      v14,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v29);
  }
  if ( v4 )
  {
    if ( (((unsigned __int64)ProcessHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (started = StartTrustlet(), started >= 0) )
    {
      v20 = v28;
      v28 = 0;
      if ( v20 )
        (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, v9, v11);
      v17 = CoCreateInstance(
              &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
              0,
              1u,
              &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
              &v28);
      v18 = v17;
      if ( v17 < 0 )
      {
        v19 = 503;
        goto LABEL_17;
      }
LABEL_23:
      v21 = (struct INgcCtnrContainer *)v28;
      v28 = 0;
      *a2 = v21;
      v18 = 0;
      goto LABEL_24;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1E9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      (const char *)(unsigned int)started,
      ppv);
  }
  v16 = v28;
  v28 = 0;
  if ( v16 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v16 + 16LL))(v16, v9, v11);
  v17 = CoCreateInstance(
          &GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317,
          0,
          1u,
          &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
          &v28);
  v18 = v17;
  if ( v17 >= 0 )
    goto LABEL_23;
  v19 = 517;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
    (const char *)(unsigned int)v17,
    ppva);
LABEL_24:
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v28);
  return v18;
}

```

## disassembly

```asm
0x180033f24  mov     [rsp-28h+arg_0], rbx
0x180033f29  mov     [rsp-28h+arg_8], rsi
0x180033f2e  push    rbp
0x180033f2f  push    rdi
0x180033f30  push    r12
0x180033f32  push    r14
0x180033f34  push    r15
0x180033f36  mov     rbp, rsp
0x180033f39  sub     rsp, 70h
0x180033f3d  mov     r12, rdx
0x180033f40  mov     rsi, rcx
0x180033f43  mov     [rbp+var_18], 0
0x180033f4b  xor     bl, bl
0x180033f4d  call    ?DoesTpmSupportNgcIsoCtnr@NgcUtils@@YA_NXZ; NgcUtils::DoesTpmSupportNgcIsoCtnr(void)
0x180033f52  mov     r15b, al
0x180033f55  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x180033f5a  mov     r14b, al
0x180033f5d  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x180033f62  mov     dil, al
0x180033f65  mov     eax, 1
0x180033f6a  mov     r8b, al
0x180033f6d  mov     [rbp+arg_10], al
0x180033f70  test    r15b, r15b
0x180033f73  jz      short loc_180033FB8
0x180033f75  test    dil, dil
0x180033f78  jz      short loc_180033FAF
0x180033f7a  lea     rdx, [rbp+arg_10]; bool *
0x180033f7e  mov     rcx, rsi; this
0x180033f81  call    ?ExistsVtl0Container@ContainerManager@@QEAAJPEA_N@Z; ContainerManager::ExistsVtl0Container(bool *)
0x180033f86  mov     rcx, [rbp+28h]; this
0x180033f8a  test    eax, eax
0x180033f8c  jns     loc_1800340E1
0x180033f92  mov     r9d, eax; char *
0x180033f95  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180033f9c  mov     edx, 1C9h; void *
0x180033fa1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033fa6  mov     r8b, [rbp+arg_10]
0x180033faa  mov     eax, 1
0x180033faf  movzx   ebx, bl
0x180033fb2  test    r14b, r14b
0x180033fb5  cmovnz  ebx, eax
0x180033fb8  mov     eax, cs:dword_1800BE0B8
0x180033fbe  cmp     eax, 5
0x180033fc1  jbe     short loc_18003403A
0x180033fc3  mov     rdx, 400000000000h
0x180033fcd  lea     rcx, dword_1800BE0B8
0x180033fd4  call    _tlgKeywordOn
0x180033fd9  test    al, al
0x180033fdb  jz      short loc_18003403A
0x180033fdd  mov     [rbp+var_10], 1000000h
0x180033fe5  mov     [rbp+arg_10], r14b
0x180033fe9  mov     [rbp+arg_18], bl
0x180033fec  mov     [rbp+var_20], dil
0x180033ff0  mov     [rbp+var_1F], r8b
0x180033ff4  mov     byte ptr [rbp+var_1E], r15b
0x180033ff8  lea     rax, [rbp+var_10]
0x180033ffc  mov     [rsp+70h+var_28], rax
0x180034001  lea     rax, [rbp+arg_10]
0x180034005  mov     [rsp+70h+var_30], rax
0x18003400a  lea     rax, [rbp+arg_18]
0x18003400e  mov     [rsp+70h+var_38], rax
0x180034013  lea     rax, [rbp+var_20]
0x180034017  mov     [rsp+70h+var_40], rax
0x18003401c  lea     rax, [rbp+var_1F]
0x180034020  mov     [rsp+70h+var_48], rax
0x180034025  lea     rax, [rbp+var_1E]
0x180034029  mov     [rsp+70h+ppv], rax; int
0x18003402e  lea     rdx, byte_1800A7109
0x180034035  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18003403a  test    bl, bl
0x18003403c  jz      short loc_18003407A
0x18003403e  mov     rax, cs:ProcessHandle
0x180034045  inc     rax
0x180034048  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003404e  jnz     loc_1800340F0
0x180034054  call    ?StartTrustlet@@YAJXZ; StartTrustlet(void)
0x180034059  mov     rcx, [rbp+28h]; this
0x18003405d  test    eax, eax
0x18003405f  jns     loc_1800340F0
0x180034065  mov     r9d, eax; char *
0x180034068  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003406f  mov     edx, 1E9h; void *
0x180034074  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034079  nop
0x18003407a  mov     rcx, [rbp+var_18]
0x18003407e  mov     [rbp+var_18], 0
0x180034086  test    rcx, rcx
0x180034089  jz      short loc_180034098
0x18003408b  mov     rax, [rcx]
0x18003408e  mov     rax, [rax+10h]
0x180034092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034097  nop
0x180034098  lea     rax, [rbp+var_18]
0x18003409c  mov     [rsp+70h+ppv], rax; int
0x1800340a1  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x1800340a8  xor     edx, edx; pUnkOuter
0x1800340aa  lea     r8d, [rdx+1]; dwClsContext
0x1800340ae  lea     rcx, _GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317; rclsid
0x1800340b5  call    cs:__imp_CoCreateInstance
0x1800340bc  nop     dword ptr [rax+rax+00h]
0x1800340c1  mov     ebx, eax
0x1800340c3  test    eax, eax
0x1800340c5  jns     short loc_180034144
0x1800340c7  mov     edx, 205h; void *
0x1800340cc  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800340d3  mov     r9d, eax; char *
0x1800340d6  mov     rcx, [rbp+28h]; this
0x1800340da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800340df  jmp     short loc_180034156
0x1800340e1  mov     r8b, [rbp+arg_10]
0x1800340e5  test    r8b, r8b
0x1800340e8  setz    bl
0x1800340eb  jmp     loc_180033FB8
0x1800340f0  mov     rcx, [rbp+var_18]
0x1800340f4  mov     [rbp+var_18], 0
0x1800340fc  test    rcx, rcx
0x1800340ff  jz      short loc_18003410E
0x180034101  mov     rax, [rcx]
0x180034104  mov     rax, [rax+10h]
0x180034108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003410d  nop
0x18003410e  lea     rax, [rbp+var_18]
0x180034112  mov     [rsp+70h+ppv], rax; ppv
0x180034117  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x18003411e  xor     edx, edx; pUnkOuter
0x180034120  lea     r8d, [rdx+1]; dwClsContext
0x180034124  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x18003412b  call    cs:__imp_CoCreateInstance
0x180034132  nop     dword ptr [rax+rax+00h]
0x180034137  mov     ebx, eax
0x180034139  test    eax, eax
0x18003413b  jns     short loc_180034144
0x18003413d  mov     edx, 1F7h
0x180034142  jmp     short loc_1800340CC
0x180034144  mov     rax, [rbp+var_18]
0x180034148  mov     [rbp+var_18], 0
0x180034150  mov     [r12], rax
0x180034154  xor     ebx, ebx
0x180034156  lea     rcx, [rbp+var_18]
0x18003415a  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18003415f  mov     eax, ebx
0x180034161  lea     r11, [rsp+70h+var_s0]
0x180034166  mov     rbx, [r11+30h]
0x18003416a  mov     rsi, [r11+38h]
0x18003416e  mov     rsp, r11
0x180034171  pop     r15
0x180034173  pop     r14
0x180034175  pop     r12
0x180034177  pop     rdi
0x180034178  pop     rbp
0x180034179  retn
```

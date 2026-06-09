# PolicyTelemetry::StaleAccountCleanupEvaluation::Stop(uint,bool)

- ea: `0x18001f78c`
- end: `0x18001fa62`
- name: `?Stop@StaleAccountCleanupEvaluation@PolicyTelemetry@@QEAAXI_N@Z`
- size: `726`
- prototype: `void __fastcall(PolicyTelemetry::StaleAccountCleanupEvaluation *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001f490`

## callees

- `0x180001b0c`
- `0x180001b38`
- `0x18000278c`
- `0x180003530`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001f78c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f99f`

## pseudocode

```c
void __fastcall PolicyTelemetry::StaleAccountCleanupEvaluation::Stop(
        PolicyTelemetry::StaleAccountCleanupEvaluation *this,
        int a2,
        char a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  _BYTE v18[4]; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  DWORD v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  int v22; // [rsp+C0h] [rbp-70h] BYREF
  int v23; // [rsp+C4h] [rbp-6Ch] BYREF
  int v24; // [rsp+C8h] [rbp-68h] BYREF
  int v25; // [rsp+CCh] [rbp-64h] BYREF
  __int64 v26; // [rsp+D0h] [rbp-60h] BYREF
  const WCHAR *v27; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp-50h] BYREF
  const WCHAR *v29; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v31; // [rsp+F8h] [rbp-38h] BYREF
  const WCHAR *v32; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v34; // [rsp+110h] [rbp-20h] BYREF
  __int64 v35; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v37; // [rsp+140h] [rbp+10h]
  __int64 v38; // [rsp+148h] [rbp+18h]
  int *v39; // [rsp+150h] [rbp+20h]
  __int64 v40; // [rsp+158h] [rbp+28h]
  DWORD *v41; // [rsp+160h] [rbp+30h]
  __int64 v42; // [rsp+168h] [rbp+38h]
  int *v43; // [rsp+170h] [rbp+40h]
  __int64 v44; // [rsp+178h] [rbp+48h]
  _BYTE *v45; // [rsp+180h] [rbp+50h]
  __int64 v46; // [rsp+188h] [rbp+58h]

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v11, v9) )
    {
      v27 = (const WCHAR *)*((_QWORD *)v8 + 15);
      v28 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
      v13 = *((_QWORD *)this + 34);
      v23 = v8[26];
      v29 = (const WCHAR *)*((_QWORD *)v8 + 12);
      v30 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
      v24 = v8[20];
      v31 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
      v25 = v8[8];
      v32 = (const WCHAR *)*((_QWORD *)v8 + 3);
      v19 = *v8;
      v33 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
      v20 = v8[16];
      v34 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
      v21 = v8[2];
      v35 = 0x1000000;
      v26 = 0x1000000;
      v18[0] = a3;
      v22 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v12,
        (__int64)&byte_18002E75F,
        v13 + 8,
        v12,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v21,
        &v34,
        (__int64)&v20,
        &v33,
        (__int64)&v19,
        &v32,
        (__int64)&v25,
        &v31,
        (__int64)&v24,
        &v30,
        &v29,
        (__int64)&v23,
        &v28,
        &v27,
        (__int64)&v22,
        (__int64)v18);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = SharedPCAccountManagerLogging::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v11, v12) )
    {
      v18[0] = a3;
      v21 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v46 = 1;
      v44 = 4;
      v19 = *(_DWORD *)(v17 + 72);
      v26 = 0x1000000;
      v45 = v18;
      v43 = &v21;
      v41 = &v20;
      v39 = &v19;
      v37 = &v26;
      v42 = 4;
      v40 = 4;
      v38 = 8;
      tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)byte_18002E913, (const GUID *)(v17 + 8), 0, 7u, &v36);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x18001f78c  mov     [rsp-8+arg_8], rbx
0x18001f791  mov     [rsp-8+arg_10], rsi
0x18001f796  push    rbp
0x18001f797  push    rdi
0x18001f798  push    r14
0x18001f79a  lea     rbp, [rsp-70h]
0x18001f79f  sub     rsp, 1A0h
0x18001f7a6  mov     rax, cs:__security_cookie
0x18001f7ad  xor     rax, rsp
0x18001f7b0  mov     [rbp+80h+var_20], rax
0x18001f7b4  mov     rdi, [rcx+110h]
0x18001f7bb  mov     sil, r8b
0x18001f7be  mov     r14d, edx
0x18001f7c1  mov     rbx, rcx
0x18001f7c4  mov     eax, [rdi+48h]
0x18001f7c7  test    eax, eax
0x18001f7c9  jns     loc_18001F965
0x18001f7cf  add     rdi, 50h ; 'P'
0x18001f7d3  cmp     eax, [rdi+8]
0x18001f7d6  jnz     loc_18001F965
0x18001f7dc  test    rdi, rdi
0x18001f7df  jz      loc_18001F965
0x18001f7e5  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f7ea  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001f7ef  mov     r9, rax
0x18001f7f2  mov     ecx, [rax]
0x18001f7f4  cmp     ecx, 5
0x18001f7f7  jbe     loc_18001FA36
0x18001f7fd  mov     rdx, 400000000000h
0x18001f807  mov     rcx, rax
0x18001f80a  call    _tlgKeywordOn
0x18001f80f  test    al, al
0x18001f811  jz      loc_18001FA36
0x18001f817  mov     rax, [rdi+78h]
0x18001f81b  lea     rdx, byte_18002E75F
0x18001f822  mov     [rbp+80h+var_D8], rax
0x18001f826  mov     rcx, r9
0x18001f829  mov     rax, [rdi+70h]
0x18001f82d  mov     [rbp+80h+var_D0], rax
0x18001f831  mov     eax, [rdi+68h]
0x18001f834  mov     r8, [rbx+110h]
0x18001f83b  mov     [rbp+80h+var_EC], eax
0x18001f83e  add     r8, 8
0x18001f842  mov     rax, [rdi+60h]
0x18001f846  mov     [rbp+80h+var_C8], rax
0x18001f84a  mov     rax, [rdi+58h]
0x18001f84e  mov     [rbp+80h+var_C0], rax
0x18001f852  mov     eax, [rdi+50h]
0x18001f855  mov     [rbp+80h+var_E8], eax
0x18001f858  mov     rax, [rdi+48h]
0x18001f85c  mov     [rbp+80h+var_B8], rax
0x18001f860  mov     eax, [rdi+20h]
0x18001f863  mov     [rbp+80h+var_E4], eax
0x18001f866  mov     rax, [rdi+18h]
0x18001f86a  mov     [rbp+80h+var_B0], rax
0x18001f86e  mov     eax, [rdi]
0x18001f870  mov     [rbp+80h+var_FC], eax
0x18001f873  mov     rax, [rdi+80h]
0x18001f87a  mov     [rbp+80h+var_A8], rax
0x18001f87e  mov     eax, [rdi+40h]
0x18001f881  mov     [rbp+80h+var_F8], eax
0x18001f884  mov     rax, [rdi+38h]
0x18001f888  mov     [rbp+80h+var_A0], rax
0x18001f88c  mov     eax, [rdi+8]
0x18001f88f  mov     [rbp+80h+var_F4], eax
0x18001f892  mov     eax, 1000000h
0x18001f897  mov     [rbp+80h+var_98], rax
0x18001f89b  mov     [rbp+80h+var_E0], rax
0x18001f89f  lea     rax, [rbp+80h+var_100]
0x18001f8a3  mov     [rsp+1B0h+var_108], rax
0x18001f8ab  lea     rax, [rbp+80h+var_F0]
0x18001f8af  mov     [rsp+1B0h+var_110], rax
0x18001f8b7  lea     rax, [rbp+80h+var_D8]
0x18001f8bb  mov     [rsp+1B0h+var_118], rax
0x18001f8c3  lea     rax, [rbp+80h+var_D0]
0x18001f8c7  mov     [rsp+1B0h+var_120], rax
0x18001f8cf  lea     rax, [rbp+80h+var_EC]
0x18001f8d3  mov     [rsp+1B0h+var_128], rax
0x18001f8db  lea     rax, [rbp+80h+var_C8]
0x18001f8df  mov     [rsp+1B0h+var_130], rax
0x18001f8e7  lea     rax, [rbp+80h+var_C0]
0x18001f8eb  mov     [rsp+1B0h+var_138], rax
0x18001f8f0  lea     rax, [rbp+80h+var_E8]
0x18001f8f4  mov     [rsp+1B0h+var_140], rax
0x18001f8f9  lea     rax, [rbp+80h+var_B8]
0x18001f8fd  mov     [rsp+1B0h+var_148], rax
0x18001f902  lea     rax, [rbp+80h+var_E4]
0x18001f906  mov     [rsp+1B0h+var_150], rax
0x18001f90b  lea     rax, [rbp+80h+var_B0]
0x18001f90f  mov     [rsp+1B0h+var_158], rax
0x18001f914  lea     rax, [rbp+80h+var_FC]
0x18001f918  mov     [rsp+1B0h+var_160], rax
0x18001f91d  lea     rax, [rbp+80h+var_A8]
0x18001f921  mov     [rsp+1B0h+var_168], rax
0x18001f926  lea     rax, [rbp+80h+var_F8]
0x18001f92a  mov     [rsp+1B0h+var_170], rax
0x18001f92f  lea     rax, [rbp+80h+var_A0]
0x18001f933  mov     [rsp+1B0h+var_178], rax
0x18001f938  lea     rax, [rbp+80h+var_F4]
0x18001f93c  mov     [rsp+1B0h+var_180], rax
0x18001f941  lea     rax, [rbp+80h+var_98]
0x18001f945  mov     [rsp+1B0h+var_188], rax
0x18001f94a  lea     rax, [rbp+80h+var_E0]
0x18001f94e  mov     [rsp+1B0h+var_190], rax
0x18001f953  mov     [rbp+80h+var_100], sil
0x18001f957  mov     [rbp+80h+var_F0], r14d
0x18001f95b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18001f960  jmp     loc_18001FA36
0x18001f965  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f96a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001f96f  mov     rdi, rax
0x18001f972  mov     ecx, [rax]
0x18001f974  cmp     ecx, 5
0x18001f977  jbe     loc_18001FA36
0x18001f97d  mov     rdx, 400000000000h
0x18001f987  mov     rcx, rax
0x18001f98a  call    _tlgKeywordOn
0x18001f98f  test    al, al
0x18001f991  jz      loc_18001FA36
0x18001f997  mov     [rbp+80h+var_100], sil
0x18001f99b  mov     [rbp+80h+var_F4], r14d
0x18001f99f  call    cs:__imp_GetCurrentThreadId
0x18001f9a5  mov     r8, [rbx+110h]
0x18001f9ac  lea     rdx, byte_18002E913
0x18001f9b3  mov     [rbp+80h+var_F8], eax
0x18001f9b6  xor     r9d, r9d
0x18001f9b9  mov     rcx, rdi
0x18001f9bc  mov     [rbp+80h+var_28], 1
0x18001f9c4  mov     [rbp+80h+var_38], 4
0x18001f9cc  mov     eax, [r8+48h]
0x18001f9d0  add     r8, 8
0x18001f9d4  mov     [rbp+80h+var_FC], eax
0x18001f9d7  mov     eax, 1000000h
0x18001f9dc  mov     [rbp+80h+var_E0], rax
0x18001f9e0  lea     rax, [rbp+80h+var_100]
0x18001f9e4  mov     [rbp+80h+var_30], rax
0x18001f9e8  lea     rax, [rbp+80h+var_F4]
0x18001f9ec  mov     [rbp+80h+var_40], rax
0x18001f9f0  lea     rax, [rbp+80h+var_F8]
0x18001f9f4  mov     [rbp+80h+var_50], rax
0x18001f9f8  lea     rax, [rbp+80h+var_FC]
0x18001f9fc  mov     [rbp+80h+var_60], rax
0x18001fa00  lea     rax, [rbp+80h+var_E0]
0x18001fa04  mov     [rbp+80h+var_70], rax
0x18001fa08  lea     rax, [rbp+80h+var_90]
0x18001fa0c  mov     [rsp+1B0h+var_188], rax
0x18001fa11  mov     dword ptr [rsp+1B0h+var_190], 7
0x18001fa19  mov     [rbp+80h+var_48], 4
0x18001fa21  mov     [rbp+80h+var_58], 4
0x18001fa29  mov     [rbp+80h+var_68], 8
0x18001fa31  call    _tlgWriteTransfer_EventWriteTransfer
0x18001fa36  mov     rcx, rbx
0x18001fa39  call    ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001fa3e  mov     rcx, [rbp+80h+var_20]
0x18001fa42  xor     rcx, rsp; StackCookie
0x18001fa45  call    __security_check_cookie
0x18001fa4a  lea     r11, [rsp+1B0h+var_10]
0x18001fa52  mov     rbx, [r11+28h]
0x18001fa56  mov     rsi, [r11+30h]
0x18001fa5a  mov     rsp, r11
0x18001fa5d  pop     r14
0x18001fa5f  pop     rdi
0x18001fa60  pop     rbp
0x18001fa61  retn
```

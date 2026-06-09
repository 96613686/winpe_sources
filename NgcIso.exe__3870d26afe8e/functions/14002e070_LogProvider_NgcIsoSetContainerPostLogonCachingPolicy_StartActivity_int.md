# LogProvider::NgcIsoSetContainerPostLogonCachingPolicy::StartActivity(int)

- ea: `0x14002e070`
- end: `0x14002e2c5`
- name: `?StartActivity@NgcIsoSetContainerPostLogonCachingPolicy@LogProvider@@QEAAXH@Z`
- size: `597`
- prototype: `void __fastcall(LogProvider::NgcIsoSetContainerPostLogonCachingPolicy *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140029e90`

## callees

- `0x140001c98`
- `0x1400033f4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002e070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e255`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoSetContainerPostLogonCachingPolicy::StartActivity(
        LogProvider::NgcIsoSetContainerPostLogonCachingPolicy *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33[3]; // [rsp+128h] [rbp-18h] BYREF
  int v34; // [rsp+150h] [rbp+10h] BYREF
  DWORD v35; // [rsp+160h] [rbp+20h] BYREF
  int v36; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LogProvider::Provider();
    if ( *(_DWORD *)v9 > 4u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v26 = *((_QWORD *)v6 + 14);
      v17 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v18 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v19 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v20 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v21 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v22 = v6[2];
      v24 = v10;
      v35 = v6[17];
      v36 = v6[4];
      v25 = *((_QWORD *)v6 + 15);
      v34 = a2;
      v33[0] = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&byte_140084EB7,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v23,
        (__int64)v33,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&word_140085036,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x14002e070  mov     [rsp-8+arg_8], rbx
0x14002e075  push    rbp
0x14002e076  push    rsi
0x14002e077  push    rdi
0x14002e078  lea     rbp, [rsp+10h]
0x14002e07d  sub     rsp, 130h
0x14002e084  mov     rdi, [rcx+110h]
0x14002e08b  mov     esi, edx
0x14002e08d  mov     rbx, rcx
0x14002e090  mov     eax, [rdi+48h]
0x14002e093  test    eax, eax
0x14002e095  jns     loc_14002E23E
0x14002e09b  add     rdi, 50h ; 'P'
0x14002e09f  cmp     eax, [rdi+8]
0x14002e0a2  jnz     loc_14002E23E
0x14002e0a8  test    rdi, rdi
0x14002e0ab  jz      loc_14002E23E
0x14002e0b1  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002e0b6  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e0bb  mov     r9, rax
0x14002e0be  mov     ecx, [rax]
0x14002e0c0  cmp     ecx, 4
0x14002e0c3  jbe     loc_14002E2AB
0x14002e0c9  mov     rax, [rdi+70h]
0x14002e0cd  lea     rdx, byte_140084EB7
0x14002e0d4  mov     rcx, [rdi+30h]
0x14002e0d8  mov     [rbp+var_50], rax
0x14002e0dc  mov     eax, [rdi+68h]
0x14002e0df  mov     [rbp+var_80], eax
0x14002e0e2  mov     rax, [rdi+60h]
0x14002e0e6  mov     r8, [rbx+110h]
0x14002e0ed  mov     [rbp+var_48], rax
0x14002e0f1  add     r8, 8
0x14002e0f5  mov     rax, [rdi+58h]
0x14002e0f9  mov     [rbp+var_40], rax
0x14002e0fd  mov     eax, [rdi+50h]
0x14002e100  mov     [rbp+var_7C], eax
0x14002e103  mov     rax, [rdi+48h]
0x14002e107  mov     [rbp+var_38], rax
0x14002e10b  mov     eax, [rdi+20h]
0x14002e10e  mov     [rbp+var_78], eax
0x14002e111  mov     rax, [rdi+18h]
0x14002e115  mov     [rbp+var_30], rax
0x14002e119  mov     eax, [rdi]
0x14002e11b  mov     [rbp+var_74], eax
0x14002e11e  mov     rax, [rdi+80h]
0x14002e125  mov     [rbp+var_28], rax
0x14002e129  mov     eax, [rdi+40h]
0x14002e12c  mov     [rbp+var_70], eax
0x14002e12f  mov     rax, [rdi+38h]
0x14002e133  mov     [rbp+var_20], rax
0x14002e137  mov     eax, [rdi+8]
0x14002e13a  mov     [rbp+var_6C], eax
0x14002e13d  lea     rax, [rbp+arg_0]
0x14002e141  mov     [rsp+140h+var_88], rax
0x14002e149  lea     rax, [rbp+var_60]
0x14002e14d  mov     [rsp+140h+var_90], rax
0x14002e155  lea     rax, [rbp+arg_10]
0x14002e159  mov     [rsp+140h+var_98], rax
0x14002e161  lea     rax, [rbp+arg_18]
0x14002e165  mov     [rsp+140h+var_A0], rax
0x14002e16d  lea     rax, [rbp+var_58]
0x14002e171  mov     [rsp+140h+var_A8], rax
0x14002e179  lea     rax, [rbp+var_50]
0x14002e17d  mov     [rsp+140h+var_B0], rax
0x14002e185  lea     rax, [rbp+var_80]
0x14002e189  mov     [rsp+140h+var_B8], rax
0x14002e191  lea     rax, [rbp+var_48]
0x14002e195  mov     [rsp+140h+var_C0], rax
0x14002e19d  lea     rax, [rbp+var_40]
0x14002e1a1  mov     [rsp+140h+var_C8], rax
0x14002e1a6  lea     rax, [rbp+var_7C]
0x14002e1aa  mov     [rsp+140h+var_D0], rax
0x14002e1af  lea     rax, [rbp+var_38]
0x14002e1b3  mov     [rsp+140h+var_D8], rax
0x14002e1b8  lea     rax, [rbp+var_78]
0x14002e1bc  mov     [rsp+140h+var_E0], rax
0x14002e1c1  lea     rax, [rbp+var_30]
0x14002e1c5  mov     [rsp+140h+var_E8], rax
0x14002e1ca  lea     rax, [rbp+var_74]
0x14002e1ce  mov     [rsp+140h+var_F0], rax
0x14002e1d3  lea     rax, [rbp+var_28]
0x14002e1d7  mov     [rsp+140h+var_F8], rax
0x14002e1dc  lea     rax, [rbp+var_70]
0x14002e1e0  mov     [rsp+140h+var_100], rax
0x14002e1e5  lea     rax, [rbp+var_20]
0x14002e1e9  mov     [rsp+140h+var_108], rax
0x14002e1ee  lea     rax, [rbp+var_6C]
0x14002e1f2  mov     [rbp+var_60], rcx
0x14002e1f6  mov     ecx, [rdi+44h]
0x14002e1f9  mov     [rsp+140h+var_110], rax
0x14002e1fe  lea     rax, [rbp+var_18]
0x14002e202  mov     [rbp+arg_10], ecx
0x14002e205  mov     ecx, [rdi+10h]
0x14002e208  mov     [rbp+arg_18], ecx
0x14002e20b  mov     rcx, [rdi+78h]
0x14002e20f  mov     [rsp+140h+var_118], rax
0x14002e214  lea     rax, [rbp+var_68]
0x14002e218  mov     [rbp+var_58], rcx
0x14002e21c  mov     rcx, r9
0x14002e21f  mov     [rsp+140h+var_120], rax
0x14002e224  mov     [rbp+arg_0], esi
0x14002e227  mov     [rbp+var_18], 1000000h
0x14002e22f  mov     [rbp+var_68], 0
0x14002e237  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14002e23c  jmp     short loc_14002E2AB
0x14002e23e  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002e243  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002e248  mov     rdi, rax
0x14002e24b  mov     ecx, [rax]
0x14002e24d  cmp     ecx, 4
0x14002e250  jbe     short loc_14002E2AB
0x14002e252  mov     [rbp+arg_0], esi
0x14002e255  call    cs:__imp_GetCurrentThreadId
0x14002e25b  mov     r8, [rbx+110h]
0x14002e262  lea     rdx, word_140085036
0x14002e269  mov     [rbp+arg_10], eax
0x14002e26c  lea     rax, [rbp+arg_0]
0x14002e270  mov     [rsp+140h+var_108], rax
0x14002e275  lea     rax, [rbp+arg_10]
0x14002e279  mov     [rsp+140h+var_110], rax
0x14002e27e  lea     rax, [rbp+arg_18]
0x14002e282  mov     ecx, [r8+48h]
0x14002e286  add     r8, 8
0x14002e28a  mov     [rsp+140h+var_118], rax
0x14002e28f  lea     rax, [rbp+var_68]
0x14002e293  mov     [rbp+arg_18], ecx
0x14002e296  mov     rcx, rdi
0x14002e299  mov     [rsp+140h+var_120], rax
0x14002e29e  mov     [rbp+var_68], 0
0x14002e2a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002e2ab  mov     rcx, rbx
0x14002e2ae  mov     rbx, [rsp+140h+arg_8]
0x14002e2b6  add     rsp, 130h
0x14002e2bd  pop     rdi
0x14002e2be  pop     rsi
0x14002e2bf  pop     rbp
0x14002e2c0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

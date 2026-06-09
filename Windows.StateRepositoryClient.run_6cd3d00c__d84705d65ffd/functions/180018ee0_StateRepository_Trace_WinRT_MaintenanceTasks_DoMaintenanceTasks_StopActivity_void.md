# StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::StopActivity(void)

- ea: `0x180018ee0`
- end: `0x18001910c`
- name: `?StopActivity@DoMaintenanceTasks@MaintenanceTasks@WinRT@Trace@StateRepository@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001c10`
- `0x180001f24`
- `0x18000719c`
- `0x1800185d4`
- `0x180018ee0`
- `0x180019218`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190ad`

## pseudocode

```c
void __fastcall StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::StopActivity(
        StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = StateRepository::Tracing::Client::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&word_180030416,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = StateRepository::Tracing::Client::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)byte_180030563,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x180018ee0  push    rbp
0x180018ee2  push    rbx
0x180018ee3  push    rdi
0x180018ee4  lea     rbp, [rsp+10h]
0x180018ee9  sub     rsp, 130h
0x180018ef0  mov     rdi, [rcx+110h]
0x180018ef7  mov     rbx, rcx
0x180018efa  mov     eax, [rdi+48h]
0x180018efd  test    eax, eax
0x180018eff  jns     loc_180019099
0x180018f05  add     rdi, 50h ; 'P'
0x180018f09  cmp     eax, [rdi+8]
0x180018f0c  jnz     loc_180019099
0x180018f12  test    rdi, rdi
0x180018f15  jz      loc_180019099
0x180018f1b  call    ?zInternalStop@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018f20  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180018f25  mov     r9, rax
0x180018f28  mov     ecx, [rax]
0x180018f2a  cmp     ecx, 5
0x180018f2d  jbe     loc_1800190FA
0x180018f33  mov     rax, [rdi+70h]
0x180018f37  lea     rdx, word_180030416
0x180018f3e  mov     rcx, [rdi+30h]
0x180018f42  mov     [rbp+var_60], rax
0x180018f46  mov     eax, [rdi+68h]
0x180018f49  mov     r8, [rbx+110h]
0x180018f50  mov     dword ptr [rbp+arg_10], eax
0x180018f53  add     r8, 8
0x180018f57  mov     rax, [rdi+60h]
0x180018f5b  mov     [rbp+var_58], rax
0x180018f5f  mov     rax, [rdi+58h]
0x180018f63  mov     [rbp+var_50], rax
0x180018f67  mov     eax, [rdi+50h]
0x180018f6a  mov     [rbp+arg_18], eax
0x180018f6d  mov     rax, [rdi+48h]
0x180018f71  mov     [rbp+var_48], rax
0x180018f75  mov     eax, [rdi+20h]
0x180018f78  mov     [rbp+var_80], eax
0x180018f7b  mov     rax, [rdi+18h]
0x180018f7f  mov     [rbp+var_40], rax
0x180018f83  mov     eax, [rdi]
0x180018f85  mov     [rbp+var_7C], eax
0x180018f88  mov     rax, [rdi+80h]
0x180018f8f  mov     [rbp+var_38], rax
0x180018f93  mov     eax, [rdi+40h]
0x180018f96  mov     [rbp+var_78], eax
0x180018f99  mov     rax, [rdi+38h]
0x180018f9d  mov     [rbp+var_30], rax
0x180018fa1  mov     eax, [rdi+8]
0x180018fa4  mov     [rbp+var_74], eax
0x180018fa7  lea     rax, [rbp+var_70]
0x180018fab  mov     [rsp+140h+var_90], rax
0x180018fb3  lea     rax, [rbp+arg_0]
0x180018fb7  mov     [rsp+140h+var_98], rax
0x180018fbf  lea     rax, [rbp+arg_8]
0x180018fc3  mov     [rsp+140h+var_A0], rax
0x180018fcb  lea     rax, [rbp+var_68]
0x180018fcf  mov     [rsp+140h+var_A8], rax
0x180018fd7  lea     rax, [rbp+var_60]
0x180018fdb  mov     [rsp+140h+var_B0], rax
0x180018fe3  lea     rax, [rbp+arg_10]
0x180018fe7  mov     [rsp+140h+var_B8], rax
0x180018fef  lea     rax, [rbp+var_58]
0x180018ff3  mov     [rsp+140h+var_C0], rax
0x180018ffb  lea     rax, [rbp+var_50]
0x180018fff  mov     [rsp+140h+var_C8], rax
0x180019004  lea     rax, [rbp+arg_18]
0x180019008  mov     [rsp+140h+var_D0], rax
0x18001900d  lea     rax, [rbp+var_48]
0x180019011  mov     [rsp+140h+var_D8], rax
0x180019016  lea     rax, [rbp+var_80]
0x18001901a  mov     [rsp+140h+var_E0], rax
0x18001901f  lea     rax, [rbp+var_40]
0x180019023  mov     [rsp+140h+var_E8], rax
0x180019028  lea     rax, [rbp+var_7C]
0x18001902c  mov     [rsp+140h+var_F0], rax
0x180019031  lea     rax, [rbp+var_38]
0x180019035  mov     [rsp+140h+var_F8], rax
0x18001903a  lea     rax, [rbp+var_78]
0x18001903e  mov     [rsp+140h+var_100], rax
0x180019043  lea     rax, [rbp+var_30]
0x180019047  mov     [rsp+140h+var_108], rax
0x18001904c  lea     rax, [rbp+var_74]
0x180019050  mov     [rbp+var_70], rcx
0x180019054  mov     ecx, [rdi+44h]
0x180019057  mov     [rsp+140h+var_110], rax
0x18001905c  lea     rax, [rbp+var_28]
0x180019060  mov     [rbp+arg_0], ecx
0x180019063  mov     ecx, [rdi+10h]
0x180019066  mov     [rbp+arg_8], ecx
0x180019069  mov     rcx, [rdi+78h]
0x18001906d  mov     [rsp+140h+var_118], rax
0x180019072  lea     rax, [rbp+var_20]
0x180019076  mov     [rbp+var_68], rcx
0x18001907a  mov     rcx, r9
0x18001907d  mov     [rsp+140h+var_120], rax
0x180019082  mov     [rbp+var_28], 1000000h
0x18001908a  mov     [rbp+var_20], 0
0x180019092  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019097  jmp     short loc_1800190FA
0x180019099  call    ?zInternalStop@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001909e  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x1800190a3  mov     rdi, rax
0x1800190a6  mov     ecx, [rax]
0x1800190a8  cmp     ecx, 5
0x1800190ab  jbe     short loc_1800190FA
0x1800190ad  call    cs:__imp_GetCurrentThreadId
0x1800190b3  mov     r8, [rbx+110h]
0x1800190ba  lea     rdx, byte_180030563
0x1800190c1  mov     [rbp+arg_0], eax
0x1800190c4  lea     rax, [rbp+arg_0]
0x1800190c8  mov     [rsp+140h+var_110], rax
0x1800190cd  lea     rax, [rbp+arg_8]
0x1800190d1  mov     [rsp+140h+var_118], rax
0x1800190d6  lea     rax, [rbp+arg_10]
0x1800190da  mov     ecx, [r8+48h]
0x1800190de  add     r8, 8
0x1800190e2  mov     [rbp+arg_8], ecx
0x1800190e5  mov     rcx, rdi
0x1800190e8  mov     [rsp+140h+var_120], rax
0x1800190ed  mov     [rbp+arg_10], 0
0x1800190f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800190fa  mov     rcx, rbx
0x1800190fd  add     rsp, 130h
0x180019104  pop     rdi
0x180019105  pop     rbx
0x180019106  pop     rbp
0x180019107  jmp     ?IgnoreCurrentThread@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

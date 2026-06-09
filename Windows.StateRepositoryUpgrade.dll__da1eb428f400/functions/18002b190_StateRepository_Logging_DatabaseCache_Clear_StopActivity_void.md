# StateRepository::Logging::DatabaseCache::Clear::StopActivity(void)

- ea: `0x18002b190`
- end: `0x18002b3bc`
- name: `?StopActivity@Clear@DatabaseCache@Logging@StateRepository@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(StateRepository::Logging::DatabaseCache::Clear *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001ddc`
- `0x180002160`
- `0x18000c984`
- `0x18002a938`
- `0x18002b190`
- `0x18002b43c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b35d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b35d`

## pseudocode

```c
void __fastcall StateRepository::Logging::DatabaseCache::Clear::StopActivity(
        StateRepository::Logging::DatabaseCache::Clear *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v27[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v28; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = StateRepository::Tracing::Service::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v19 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v30) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v31 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v6;
      v28 = v4[17];
      v29 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&byte_1800462EF,
        v7 + 8,
        (_DWORD)v5,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v17);
    }
  }
  else
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = StateRepository::Tracing::Service::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v11 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&byte_18004642F,
        v11 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18002b190  push    rbp
0x18002b192  push    rbx
0x18002b193  push    rdi
0x18002b194  lea     rbp, [rsp+10h]
0x18002b199  sub     rsp, 130h
0x18002b1a0  mov     rdi, [rcx+110h]
0x18002b1a7  mov     rbx, rcx
0x18002b1aa  mov     eax, [rdi+48h]
0x18002b1ad  test    eax, eax
0x18002b1af  jns     loc_18002B349
0x18002b1b5  add     rdi, 50h ; 'P'
0x18002b1b9  cmp     eax, [rdi+8]
0x18002b1bc  jnz     loc_18002B349
0x18002b1c2  test    rdi, rdi
0x18002b1c5  jz      loc_18002B349
0x18002b1cb  call    ?zInternalStop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002b1d0  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002b1d5  mov     r9, rax
0x18002b1d8  mov     ecx, [rax]
0x18002b1da  cmp     ecx, 5
0x18002b1dd  jbe     loc_18002B3AA
0x18002b1e3  mov     rax, [rdi+70h]
0x18002b1e7  lea     rdx, byte_1800462EF
0x18002b1ee  mov     rcx, [rdi+30h]
0x18002b1f2  mov     [rbp+var_60], rax
0x18002b1f6  mov     eax, [rdi+68h]
0x18002b1f9  mov     r8, [rbx+110h]
0x18002b200  mov     dword ptr [rbp+arg_10], eax
0x18002b203  add     r8, 8
0x18002b207  mov     rax, [rdi+60h]
0x18002b20b  mov     [rbp+var_58], rax
0x18002b20f  mov     rax, [rdi+58h]
0x18002b213  mov     [rbp+var_50], rax
0x18002b217  mov     eax, [rdi+50h]
0x18002b21a  mov     [rbp+arg_18], eax
0x18002b21d  mov     rax, [rdi+48h]
0x18002b221  mov     [rbp+var_48], rax
0x18002b225  mov     eax, [rdi+20h]
0x18002b228  mov     [rbp+var_80], eax
0x18002b22b  mov     rax, [rdi+18h]
0x18002b22f  mov     [rbp+var_40], rax
0x18002b233  mov     eax, [rdi]
0x18002b235  mov     [rbp+var_7C], eax
0x18002b238  mov     rax, [rdi+80h]
0x18002b23f  mov     [rbp+var_38], rax
0x18002b243  mov     eax, [rdi+40h]
0x18002b246  mov     [rbp+var_78], eax
0x18002b249  mov     rax, [rdi+38h]
0x18002b24d  mov     [rbp+var_30], rax
0x18002b251  mov     eax, [rdi+8]
0x18002b254  mov     [rbp+var_74], eax
0x18002b257  lea     rax, [rbp+var_70]
0x18002b25b  mov     [rsp+140h+var_90], rax
0x18002b263  lea     rax, [rbp+arg_0]
0x18002b267  mov     [rsp+140h+var_98], rax
0x18002b26f  lea     rax, [rbp+arg_8]
0x18002b273  mov     [rsp+140h+var_A0], rax
0x18002b27b  lea     rax, [rbp+var_68]
0x18002b27f  mov     [rsp+140h+var_A8], rax
0x18002b287  lea     rax, [rbp+var_60]
0x18002b28b  mov     [rsp+140h+var_B0], rax
0x18002b293  lea     rax, [rbp+arg_10]
0x18002b297  mov     [rsp+140h+var_B8], rax
0x18002b29f  lea     rax, [rbp+var_58]
0x18002b2a3  mov     [rsp+140h+var_C0], rax
0x18002b2ab  lea     rax, [rbp+var_50]
0x18002b2af  mov     [rsp+140h+var_C8], rax
0x18002b2b4  lea     rax, [rbp+arg_18]
0x18002b2b8  mov     [rsp+140h+var_D0], rax
0x18002b2bd  lea     rax, [rbp+var_48]
0x18002b2c1  mov     [rsp+140h+var_D8], rax
0x18002b2c6  lea     rax, [rbp+var_80]
0x18002b2ca  mov     [rsp+140h+var_E0], rax
0x18002b2cf  lea     rax, [rbp+var_40]
0x18002b2d3  mov     [rsp+140h+var_E8], rax
0x18002b2d8  lea     rax, [rbp+var_7C]
0x18002b2dc  mov     [rsp+140h+var_F0], rax
0x18002b2e1  lea     rax, [rbp+var_38]
0x18002b2e5  mov     [rsp+140h+var_F8], rax
0x18002b2ea  lea     rax, [rbp+var_78]
0x18002b2ee  mov     [rsp+140h+var_100], rax
0x18002b2f3  lea     rax, [rbp+var_30]
0x18002b2f7  mov     [rsp+140h+var_108], rax
0x18002b2fc  lea     rax, [rbp+var_74]
0x18002b300  mov     [rbp+var_70], rcx
0x18002b304  mov     ecx, [rdi+44h]
0x18002b307  mov     [rsp+140h+var_110], rax
0x18002b30c  lea     rax, [rbp+var_28]
0x18002b310  mov     [rbp+arg_0], ecx
0x18002b313  mov     ecx, [rdi+10h]
0x18002b316  mov     [rbp+arg_8], ecx
0x18002b319  mov     rcx, [rdi+78h]
0x18002b31d  mov     [rsp+140h+var_118], rax
0x18002b322  lea     rax, [rbp+var_20]
0x18002b326  mov     [rbp+var_68], rcx
0x18002b32a  mov     rcx, r9
0x18002b32d  mov     [rsp+140h+var_120], rax
0x18002b332  mov     [rbp+var_28], 1000000h
0x18002b33a  mov     [rbp+var_20], 0
0x18002b342  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b347  jmp     short loc_18002B3AA
0x18002b349  call    ?zInternalStop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002b34e  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002b353  mov     rdi, rax
0x18002b356  mov     ecx, [rax]
0x18002b358  cmp     ecx, 5
0x18002b35b  jbe     short loc_18002B3AA
0x18002b35d  call    cs:__imp_GetCurrentThreadId
0x18002b363  mov     r8, [rbx+110h]
0x18002b36a  lea     rdx, byte_18004642F
0x18002b371  mov     [rbp+arg_0], eax
0x18002b374  lea     rax, [rbp+arg_0]
0x18002b378  mov     [rsp+140h+var_110], rax
0x18002b37d  lea     rax, [rbp+arg_8]
0x18002b381  mov     [rsp+140h+var_118], rax
0x18002b386  lea     rax, [rbp+arg_10]
0x18002b38a  mov     ecx, [r8+48h]
0x18002b38e  add     r8, 8
0x18002b392  mov     [rbp+arg_8], ecx
0x18002b395  mov     rcx, rdi
0x18002b398  mov     [rsp+140h+var_120], rax
0x18002b39d  mov     [rbp+arg_10], 0
0x18002b3a5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002b3aa  mov     rcx, rbx
0x18002b3ad  add     rsp, 130h
0x18002b3b4  pop     rdi
0x18002b3b5  pop     rbx
0x18002b3b6  pop     rbp
0x18002b3b7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

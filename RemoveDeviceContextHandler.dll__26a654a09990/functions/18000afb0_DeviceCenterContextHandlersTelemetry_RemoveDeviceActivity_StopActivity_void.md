# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StopActivity(void)

- ea: `0x18000afb0`
- end: `0x18000b290`
- name: `?StopActivity@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x1800018dc`
- `0x180008214`
- `0x180008814`
- `0x180009170`
- `0x18000afb0`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b01f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b1b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b01f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b1b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b1f1`

## pseudocode

```c
void __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StopActivity(
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B8h] [rbp-68h] BYREF
  int v20; // [rsp+BCh] [rbp-64h] BYREF
  int v21; // [rsp+C0h] [rbp-60h] BYREF
  int v22; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 v23; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+100h] [rbp-20h] BYREF
  _QWORD v31[11]; // [rsp+108h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = DeviceCenterContextHandlersLogging::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = *((_QWORD *)v4 + 15);
        v24 = *((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = *((_QWORD *)v4 + 12);
        v26 = *((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = *((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = *((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = *((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31[0] = 0x1000000;
        v18 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)byte_180011119,
          v9 + 8,
          (_DWORD)v7,
          (__int64)&v18,
          (__int64)v31,
          (__int64)&SRWLock,
          (__int64)&v30,
          (__int64)&v16,
          (__int64)&v29,
          (__int64)&v22,
          (__int64)&v28,
          (__int64)&v21,
          (__int64)&v27,
          (__int64)&v20,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v19,
          (__int64)&v24,
          (__int64)&v23);
      }
    }
  }
  else
  {
    wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = DeviceCenterContextHandlersLogging::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v31[10] = 4;
        v31[8] = 4;
        v16 = *(_DWORD *)(v15 + 72);
        v31[9] = &SRWLock;
        v31[7] = &v16;
        v31[5] = &v18;
        v18 = 0;
        v31[6] = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, byte_180011245, v15 + 8);
      }
    }
  }
  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000afb0  mov     [rsp-8+arg_8], rbx
0x18000afb5  mov     [rsp-8+arg_10], rdi
0x18000afba  push    rbp
0x18000afbb  lea     rbp, [rsp-50h]
0x18000afc0  sub     rsp, 170h
0x18000afc7  mov     rax, cs:__security_cookie
0x18000afce  xor     rax, rsp
0x18000afd1  mov     [rbp+50h+var_10], rax
0x18000afd5  mov     rdi, [rcx+110h]
0x18000afdc  mov     rbx, rcx
0x18000afdf  mov     eax, [rdi+48h]
0x18000afe2  test    eax, eax
0x18000afe4  jns     loc_18000B193
0x18000afea  add     rdi, 50h ; 'P'
0x18000afee  cmp     eax, [rdi+8]
0x18000aff1  jnz     loc_18000B193
0x18000aff7  test    rdi, rdi
0x18000affa  jz      loc_18000B193
0x18000b000  lea     rdx, [rbp+50h+SRWLock]
0x18000b004  call    ?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b009  mov     rax, [rbx+110h]
0x18000b010  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000b014  mov     dword ptr [rax], 2
0x18000b01a  test    rcx, rcx
0x18000b01d  jz      short loc_18000B025
0x18000b01f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b025  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000b02a  mov     r9, rax
0x18000b02d  mov     ecx, [rax]
0x18000b02f  cmp     ecx, 5
0x18000b032  jbe     loc_18000B267
0x18000b038  mov     rax, [rax+18h]
0x18000b03c  mov     rdx, 200000000000h
0x18000b046  mov     rcx, [r9+10h]
0x18000b04a  test    rdx, rcx
0x18000b04d  jz      loc_18000B267
0x18000b053  mov     rcx, rax
0x18000b056  and     rcx, rdx
0x18000b059  cmp     rcx, rax
0x18000b05c  jnz     loc_18000B267
0x18000b062  mov     rax, [rdi+78h]
0x18000b066  lea     rdx, byte_180011119
0x18000b06d  mov     r8, [rbx+110h]
0x18000b074  mov     rcx, r9
0x18000b077  mov     [rbp+50h+var_A8], rax
0x18000b07b  add     r8, 8
0x18000b07f  mov     rax, [rdi+70h]
0x18000b083  mov     [rbp+50h+var_A0], rax
0x18000b087  mov     eax, [rdi+68h]
0x18000b08a  mov     [rbp+50h+var_B8], eax
0x18000b08d  mov     rax, [rdi+60h]
0x18000b091  mov     [rbp+50h+var_98], rax
0x18000b095  mov     rax, [rdi+58h]
0x18000b099  mov     [rbp+50h+var_90], rax
0x18000b09d  mov     eax, [rdi+50h]
0x18000b0a0  mov     [rbp+50h+var_B4], eax
0x18000b0a3  mov     rax, [rdi+48h]
0x18000b0a7  mov     [rbp+50h+var_88], rax
0x18000b0ab  mov     eax, [rdi+20h]
0x18000b0ae  mov     [rbp+50h+var_B0], eax
0x18000b0b1  mov     rax, [rdi+18h]
0x18000b0b5  mov     [rbp+50h+var_80], rax
0x18000b0b9  mov     eax, [rdi]
0x18000b0bb  mov     [rbp+50h+var_AC], eax
0x18000b0be  mov     rax, [rdi+80h]
0x18000b0c5  mov     [rbp+50h+var_78], rax
0x18000b0c9  mov     eax, [rdi+40h]
0x18000b0cc  mov     [rbp+50h+var_D0], eax
0x18000b0cf  mov     rax, [rdi+38h]
0x18000b0d3  mov     [rbp+50h+var_70], rax
0x18000b0d7  mov     eax, [rdi+8]
0x18000b0da  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b0dd  lea     rax, [rbp+50h+var_A8]
0x18000b0e1  mov     [rsp+170h+var_D8], rax
0x18000b0e9  lea     rax, [rbp+50h+var_A0]
0x18000b0ed  mov     [rsp+170h+var_E0], rax
0x18000b0f5  lea     rax, [rbp+50h+var_B8]
0x18000b0f9  mov     [rsp+170h+var_E8], rax
0x18000b101  lea     rax, [rbp+50h+var_98]
0x18000b105  mov     [rsp+170h+var_F0], rax
0x18000b10d  lea     rax, [rbp+50h+var_90]
0x18000b111  mov     [rsp+170h+var_F8], rax
0x18000b116  lea     rax, [rbp+50h+var_B4]
0x18000b11a  mov     [rsp+170h+var_100], rax
0x18000b11f  lea     rax, [rbp+50h+var_88]
0x18000b123  mov     [rsp+170h+var_108], rax
0x18000b128  lea     rax, [rbp+50h+var_B0]
0x18000b12c  mov     [rsp+170h+var_110], rax
0x18000b131  lea     rax, [rbp+50h+var_80]
0x18000b135  mov     [rsp+170h+var_118], rax
0x18000b13a  lea     rax, [rbp+50h+var_AC]
0x18000b13e  mov     [rsp+170h+var_120], rax
0x18000b143  lea     rax, [rbp+50h+var_78]
0x18000b147  mov     [rsp+170h+var_128], rax
0x18000b14c  lea     rax, [rbp+50h+var_D0]
0x18000b150  mov     [rsp+170h+var_130], rax
0x18000b155  lea     rax, [rbp+50h+var_70]
0x18000b159  mov     [rsp+170h+var_138], rax
0x18000b15e  lea     rax, [rbp+50h+SRWLock]
0x18000b162  mov     [rsp+170h+var_140], rax
0x18000b167  lea     rax, [rbp+50h+var_68]
0x18000b16b  mov     [rsp+170h+var_148], rax
0x18000b170  lea     rax, [rbp+50h+var_C0]
0x18000b174  mov     [rsp+170h+var_150], rax
0x18000b179  mov     [rbp+50h+var_68], 1000000h
0x18000b181  mov     [rbp+50h+var_C0], 0
0x18000b189  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000b18e  jmp     loc_18000B267
0x18000b193  lea     rdx, [rbp+50h+var_C0]
0x18000b197  call    ?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b19c  mov     rax, [rbx+110h]
0x18000b1a3  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000b1a7  mov     dword ptr [rax], 2
0x18000b1ad  test    rcx, rcx
0x18000b1b0  jz      short loc_18000B1B8
0x18000b1b2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b1b8  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000b1bd  mov     rdi, rax
0x18000b1c0  mov     ecx, [rax]
0x18000b1c2  cmp     ecx, 5
0x18000b1c5  jbe     loc_18000B267
0x18000b1cb  mov     rax, [rax+18h]
0x18000b1cf  mov     rdx, 200000000000h
0x18000b1d9  mov     rcx, [rdi+10h]
0x18000b1dd  test    rdx, rcx
0x18000b1e0  jz      loc_18000B267
0x18000b1e6  mov     rcx, rax
0x18000b1e9  and     rcx, rdx
0x18000b1ec  cmp     rcx, rax
0x18000b1ef  jnz     short loc_18000B267
0x18000b1f1  call    cs:__imp_GetCurrentThreadId
0x18000b1f7  mov     r8, [rbx+110h]
0x18000b1fe  lea     rdx, byte_180011245
0x18000b205  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000b208  xor     r9d, r9d
0x18000b20b  mov     rcx, rdi
0x18000b20e  mov     [rbp+50h+var_18], 4
0x18000b216  mov     [rbp+50h+var_28], 4
0x18000b21e  mov     eax, [r8+48h]
0x18000b222  add     r8, 8
0x18000b226  mov     [rbp+50h+var_D0], eax
0x18000b229  lea     rax, [rbp+50h+SRWLock]
0x18000b22d  mov     [rbp+50h+var_20], rax
0x18000b231  lea     rax, [rbp+50h+var_D0]
0x18000b235  mov     [rbp+50h+var_30], rax
0x18000b239  lea     rax, [rbp+50h+var_C0]
0x18000b23d  mov     [rbp+50h+var_40], rax
0x18000b241  lea     rax, [rbp+50h+var_60]
0x18000b245  mov     [rsp+170h+var_148], rax
0x18000b24a  mov     dword ptr [rsp+170h+var_150], 5
0x18000b252  mov     [rbp+50h+var_C0], 0
0x18000b25a  mov     [rbp+50h+var_38], 8
0x18000b262  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b267  mov     rcx, rbx
0x18000b26a  call    ?IgnoreCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b26f  mov     rcx, [rbp+50h+var_10]
0x18000b273  xor     rcx, rsp; StackCookie
0x18000b276  call    __security_check_cookie
0x18000b27b  lea     r11, [rsp+170h+var_s0]
0x18000b283  mov     rbx, [r11+18h]
0x18000b287  mov     rdi, [r11+20h]
0x18000b28b  mov     rsp, r11
0x18000b28e  pop     rbp
0x18000b28f  retn
```

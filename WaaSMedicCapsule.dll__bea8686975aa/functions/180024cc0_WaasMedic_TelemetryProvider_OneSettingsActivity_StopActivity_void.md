# WaasMedic::TelemetryProvider::OneSettingsActivity::StopActivity(void)

- ea: `0x180024cc0`
- end: `0x180024f9e`
- name: `?StopActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `734`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::OneSettingsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180001008`
- `0x1800017ac`
- `0x180003bb0`
- `0x180016c9c`
- `0x1800241f8`
- `0x180024274`
- `0x180024cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024d2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ebf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024d2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024efe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024efe`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::OneSettingsActivity::StopActivity(
        WaasMedic::TelemetryProvider::OneSettingsActivity *this)
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
  __int64 v12; // rdi
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
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WaasMedic::TelemetryProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
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
        v31 = 0x1000000;
        v18 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&dword_180088AEC,
          v9 + 8,
          (_DWORD)v7,
          (__int64)&v18,
          (__int64)&v31,
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WaasMedic::TelemetryProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        v18 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v12,
          (unsigned __int8 *)&unk_180088F08,
          (const GUID *)(v15 + 8),
          0,
          5u,
          &v32);
      }
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180024cc0  mov     [rsp-8+arg_8], rbx
0x180024cc5  mov     [rsp-8+arg_10], rdi
0x180024cca  push    rbp
0x180024ccb  lea     rbp, [rsp-50h]
0x180024cd0  sub     rsp, 170h
0x180024cd7  mov     rax, cs:__security_cookie
0x180024cde  xor     rax, rsp
0x180024ce1  mov     [rbp+50h+var_10], rax
0x180024ce5  mov     rdi, [rcx+110h]
0x180024cec  mov     rbx, rcx
0x180024cef  mov     eax, [rdi+48h]
0x180024cf2  test    eax, eax
0x180024cf4  jns     loc_180024EA0
0x180024cfa  add     rdi, 50h ; 'P'
0x180024cfe  cmp     eax, [rdi+8]
0x180024d01  jnz     loc_180024EA0
0x180024d07  test    rdi, rdi
0x180024d0a  jz      loc_180024EA0
0x180024d10  lea     rdx, [rbp+50h+SRWLock]
0x180024d14  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024d19  mov     rax, [rbx+110h]
0x180024d20  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x180024d24  mov     dword ptr [rax], 2
0x180024d2a  test    rcx, rcx
0x180024d2d  jz      short loc_180024D35
0x180024d2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180024d35  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180024d3a  mov     r9, rax
0x180024d3d  mov     ecx, [rax]
0x180024d3f  cmp     ecx, 5
0x180024d42  jbe     loc_180024F75
0x180024d48  mov     rax, [rax+18h]
0x180024d4c  mov     rdx, 400000000000h
0x180024d56  mov     rcx, [r9+10h]
0x180024d5a  test    rdx, rcx
0x180024d5d  jz      loc_180024F75
0x180024d63  mov     rcx, rax
0x180024d66  and     rcx, rdx
0x180024d69  cmp     rcx, rax
0x180024d6c  jnz     loc_180024F75
0x180024d72  mov     rax, [rdi+78h]
0x180024d76  lea     rdx, dword_180088AEC
0x180024d7d  mov     r8, [rbx+110h]
0x180024d84  mov     rcx, r9
0x180024d87  mov     [rbp+50h+var_A8], rax
0x180024d8b  add     r8, 8
0x180024d8f  mov     rax, [rdi+70h]
0x180024d93  mov     [rbp+50h+var_A0], rax
0x180024d97  mov     eax, [rdi+68h]
0x180024d9a  mov     [rbp+50h+var_B8], eax
0x180024d9d  mov     rax, [rdi+60h]
0x180024da1  mov     [rbp+50h+var_98], rax
0x180024da5  mov     rax, [rdi+58h]
0x180024da9  mov     [rbp+50h+var_90], rax
0x180024dad  mov     eax, [rdi+50h]
0x180024db0  mov     [rbp+50h+var_B4], eax
0x180024db3  mov     rax, [rdi+48h]
0x180024db7  mov     [rbp+50h+var_88], rax
0x180024dbb  mov     eax, [rdi+20h]
0x180024dbe  mov     [rbp+50h+var_B0], eax
0x180024dc1  mov     rax, [rdi+18h]
0x180024dc5  mov     [rbp+50h+var_80], rax
0x180024dc9  mov     eax, [rdi]
0x180024dcb  mov     [rbp+50h+var_AC], eax
0x180024dce  mov     rax, [rdi+80h]
0x180024dd5  mov     [rbp+50h+var_78], rax
0x180024dd9  mov     eax, [rdi+40h]
0x180024ddc  mov     [rbp+50h+var_D0], eax
0x180024ddf  mov     rax, [rdi+38h]
0x180024de3  mov     [rbp+50h+var_70], rax
0x180024de7  mov     eax, [rdi+8]
0x180024dea  mov     dword ptr [rbp+50h+SRWLock], eax
0x180024ded  mov     eax, 1000000h
0x180024df2  mov     [rbp+50h+var_68], rax
0x180024df6  mov     [rbp+50h+var_C0], rax
0x180024dfa  lea     rax, [rbp+50h+var_A8]
0x180024dfe  mov     [rsp+170h+var_D8], rax
0x180024e06  lea     rax, [rbp+50h+var_A0]
0x180024e0a  mov     [rsp+170h+var_E0], rax
0x180024e12  lea     rax, [rbp+50h+var_B8]
0x180024e16  mov     [rsp+170h+var_E8], rax
0x180024e1e  lea     rax, [rbp+50h+var_98]
0x180024e22  mov     [rsp+170h+var_F0], rax
0x180024e2a  lea     rax, [rbp+50h+var_90]
0x180024e2e  mov     [rsp+170h+var_F8], rax
0x180024e33  lea     rax, [rbp+50h+var_B4]
0x180024e37  mov     [rsp+170h+var_100], rax
0x180024e3c  lea     rax, [rbp+50h+var_88]
0x180024e40  mov     [rsp+170h+var_108], rax
0x180024e45  lea     rax, [rbp+50h+var_B0]
0x180024e49  mov     [rsp+170h+var_110], rax
0x180024e4e  lea     rax, [rbp+50h+var_80]
0x180024e52  mov     [rsp+170h+var_118], rax
0x180024e57  lea     rax, [rbp+50h+var_AC]
0x180024e5b  mov     [rsp+170h+var_120], rax
0x180024e60  lea     rax, [rbp+50h+var_78]
0x180024e64  mov     [rsp+170h+var_128], rax
0x180024e69  lea     rax, [rbp+50h+var_D0]
0x180024e6d  mov     [rsp+170h+var_130], rax
0x180024e72  lea     rax, [rbp+50h+var_70]
0x180024e76  mov     [rsp+170h+var_138], rax
0x180024e7b  lea     rax, [rbp+50h+SRWLock]
0x180024e7f  mov     [rsp+170h+var_140], rax
0x180024e84  lea     rax, [rbp+50h+var_68]
0x180024e88  mov     [rsp+170h+var_148], rax
0x180024e8d  lea     rax, [rbp+50h+var_C0]
0x180024e91  mov     [rsp+170h+var_150], rax
0x180024e96  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180024e9b  jmp     loc_180024F75
0x180024ea0  lea     rdx, [rbp+50h+var_C0]
0x180024ea4  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024ea9  mov     rax, [rbx+110h]
0x180024eb0  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x180024eb4  mov     dword ptr [rax], 2
0x180024eba  test    rcx, rcx
0x180024ebd  jz      short loc_180024EC5
0x180024ebf  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ec5  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180024eca  mov     rdi, rax
0x180024ecd  mov     ecx, [rax]
0x180024ecf  cmp     ecx, 5
0x180024ed2  jbe     loc_180024F75
0x180024ed8  mov     rax, [rax+18h]
0x180024edc  mov     rdx, 400000000000h
0x180024ee6  mov     rcx, [rdi+10h]
0x180024eea  test    rdx, rcx
0x180024eed  jz      loc_180024F75
0x180024ef3  mov     rcx, rax
0x180024ef6  and     rcx, rdx
0x180024ef9  cmp     rcx, rax
0x180024efc  jnz     short loc_180024F75
0x180024efe  call    cs:__imp_GetCurrentThreadId
0x180024f04  mov     r8, [rbx+110h]
0x180024f0b  lea     rdx, unk_180088F08
0x180024f12  mov     dword ptr [rbp+50h+SRWLock], eax
0x180024f15  xor     r9d, r9d
0x180024f18  mov     rcx, rdi
0x180024f1b  mov     [rbp+50h+var_18], 4
0x180024f23  mov     [rbp+50h+var_28], 4
0x180024f2b  mov     eax, [r8+48h]
0x180024f2f  add     r8, 8
0x180024f33  mov     [rbp+50h+var_D0], eax
0x180024f36  mov     eax, 1000000h
0x180024f3b  mov     [rbp+50h+var_C0], rax
0x180024f3f  lea     rax, [rbp+50h+SRWLock]
0x180024f43  mov     [rbp+50h+var_20], rax
0x180024f47  lea     rax, [rbp+50h+var_D0]
0x180024f4b  mov     [rbp+50h+var_30], rax
0x180024f4f  lea     rax, [rbp+50h+var_C0]
0x180024f53  mov     [rbp+50h+var_40], rax
0x180024f57  lea     rax, [rbp+50h+var_60]
0x180024f5b  mov     [rsp+170h+var_148], rax
0x180024f60  mov     dword ptr [rsp+170h+var_150], 5
0x180024f68  mov     [rbp+50h+var_38], 8
0x180024f70  call    _tlgWriteTransfer_EventWriteTransfer
0x180024f75  mov     rcx, rbx
0x180024f78  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180024f7d  mov     rcx, [rbp+50h+var_10]
0x180024f81  xor     rcx, rsp; StackCookie
0x180024f84  call    __security_check_cookie
0x180024f89  lea     r11, [rsp+170h+var_s0]
0x180024f91  mov     rbx, [r11+18h]
0x180024f95  mov     rdi, [r11+20h]
0x180024f99  mov     rsp, r11
0x180024f9c  pop     rbp
0x180024f9d  retn
```

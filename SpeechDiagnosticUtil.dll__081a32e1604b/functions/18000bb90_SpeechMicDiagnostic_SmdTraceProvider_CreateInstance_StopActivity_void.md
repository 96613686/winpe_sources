# SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StopActivity(void)

- ea: `0x18000bb90`
- end: `0x18000be13`
- name: `?StopActivity@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016e4`
- `0x1800023a4`
- `0x1800068cc`
- `0x18000872c`
- `0x180008c58`
- `0x18000bb90`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000bbea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000bd8f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000bbea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000bd8f`
- `KERNEL32!GetCurrentThreadId` at `0x18000bdab`
- `KERNEL32!GetCurrentThreadId` at `0x18000bdab`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StopActivity(
        SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // r9d
  _DWORD *v7; // rdi
  __int64 v8; // r8
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v13; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v14; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v5 > 5u )
    {
      v13 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = *((_QWORD *)v4 + 15);
      v15 = *((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = *((_QWORD *)v4 + 12);
      v17 = *((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = *((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = *((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = *((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = *((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&unk_180015AA0,
        *((_QWORD *)this + 34) + 8,
        v6,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v11,
        (__int64)&v20,
        (__int64)&v10,
        (__int64)&v19,
        (__int64)&v9,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        (__int64)&v13);
    }
  }
  else
  {
    wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
    if ( *v7 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v8 + 72);
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)byte_180015BE9,
        v8 + 8,
        0,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000bb90  push    rbp
0x18000bb92  push    rbx
0x18000bb93  push    rdi
0x18000bb94  lea     rbp, [rsp+10h]
0x18000bb99  sub     rsp, 130h
0x18000bba0  mov     rbx, rcx
0x18000bba3  mov     rdi, [rcx+110h]
0x18000bbaa  mov     eax, [rdi+48h]
0x18000bbad  test    eax, eax
0x18000bbaf  jns     loc_18000BD70
0x18000bbb5  add     rdi, 50h ; 'P'
0x18000bbb9  cmp     eax, [rdi+8]
0x18000bbbc  jnz     loc_18000BD70
0x18000bbc2  test    rdi, rdi
0x18000bbc5  jz      loc_18000BD70
0x18000bbcb  lea     rdx, [rbp+SRWLock]
0x18000bbcf  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000bbd4  mov     rax, [rbx+110h]
0x18000bbdb  mov     dword ptr [rax], 2
0x18000bbe1  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000bbe5  test    rcx, rcx
0x18000bbe8  jz      short loc_18000BBF6
0x18000bbea  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bbf1  nop     dword ptr [rax+rax+00h]
0x18000bbf6  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000bbfb  mov     rcx, [rax+8]
0x18000bbff  mov     eax, [rcx]
0x18000bc01  cmp     eax, 5
0x18000bc04  jbe     loc_18000BE01
0x18000bc0a  mov     rax, [rdi+30h]
0x18000bc0e  mov     [rbp+var_70], rax
0x18000bc12  mov     eax, [rdi+44h]
0x18000bc15  mov     dword ptr [rbp+SRWLock], eax
0x18000bc18  mov     eax, [rdi+10h]
0x18000bc1b  mov     [rbp+arg_8], eax
0x18000bc1e  mov     rax, [rdi+78h]
0x18000bc22  mov     [rbp+var_68], rax
0x18000bc26  mov     rax, [rdi+70h]
0x18000bc2a  mov     [rbp+var_60], rax
0x18000bc2e  mov     eax, [rdi+68h]
0x18000bc31  mov     dword ptr [rbp+arg_10], eax
0x18000bc34  mov     rax, [rdi+60h]
0x18000bc38  mov     [rbp+var_58], rax
0x18000bc3c  mov     rax, [rdi+58h]
0x18000bc40  mov     [rbp+var_50], rax
0x18000bc44  mov     eax, [rdi+50h]
0x18000bc47  mov     [rbp+arg_18], eax
0x18000bc4a  mov     rax, [rdi+48h]
0x18000bc4e  mov     [rbp+var_48], rax
0x18000bc52  mov     eax, [rdi+20h]
0x18000bc55  mov     [rbp+var_80], eax
0x18000bc58  mov     rax, [rdi+18h]
0x18000bc5c  mov     [rbp+var_40], rax
0x18000bc60  mov     eax, [rdi]
0x18000bc62  mov     [rbp+var_7C], eax
0x18000bc65  mov     rax, [rdi+80h]
0x18000bc6c  mov     [rbp+var_38], rax
0x18000bc70  mov     eax, [rdi+40h]
0x18000bc73  mov     [rbp+var_78], eax
0x18000bc76  mov     rax, [rdi+38h]
0x18000bc7a  mov     [rbp+var_30], rax
0x18000bc7e  mov     eax, [rdi+8]
0x18000bc81  mov     [rbp+var_74], eax
0x18000bc84  mov     [rbp+var_28], 1000000h
0x18000bc8c  mov     [rbp+var_20], 0
0x18000bc94  mov     r8, [rbx+110h]
0x18000bc9b  add     r8, 8
0x18000bc9f  lea     rax, [rbp+var_70]
0x18000bca3  mov     [rsp+140h+var_90], rax
0x18000bcab  lea     rax, [rbp+SRWLock]
0x18000bcaf  mov     [rsp+140h+var_98], rax
0x18000bcb7  lea     rax, [rbp+arg_8]
0x18000bcbb  mov     [rsp+140h+var_A0], rax
0x18000bcc3  lea     rax, [rbp+var_68]
0x18000bcc7  mov     [rsp+140h+var_A8], rax
0x18000bccf  lea     rax, [rbp+var_60]
0x18000bcd3  mov     [rsp+140h+var_B0], rax
0x18000bcdb  lea     rax, [rbp+arg_10]
0x18000bcdf  mov     [rsp+140h+var_B8], rax
0x18000bce7  lea     rax, [rbp+var_58]
0x18000bceb  mov     [rsp+140h+var_C0], rax
0x18000bcf3  lea     rax, [rbp+var_50]
0x18000bcf7  mov     [rsp+140h+var_C8], rax
0x18000bcfc  lea     rax, [rbp+arg_18]
0x18000bd00  mov     [rsp+140h+var_D0], rax
0x18000bd05  lea     rax, [rbp+var_48]
0x18000bd09  mov     [rsp+140h+var_D8], rax
0x18000bd0e  lea     rax, [rbp+var_80]
0x18000bd12  mov     [rsp+140h+var_E0], rax
0x18000bd17  lea     rax, [rbp+var_40]
0x18000bd1b  mov     [rsp+140h+var_E8], rax
0x18000bd20  lea     rax, [rbp+var_7C]
0x18000bd24  mov     [rsp+140h+var_F0], rax
0x18000bd29  lea     rax, [rbp+var_38]
0x18000bd2d  mov     [rsp+140h+var_F8], rax
0x18000bd32  lea     rax, [rbp+var_78]
0x18000bd36  mov     [rsp+140h+var_100], rax
0x18000bd3b  lea     rax, [rbp+var_30]
0x18000bd3f  mov     [rsp+140h+var_108], rax
0x18000bd44  lea     rax, [rbp+var_74]
0x18000bd48  mov     [rsp+140h+var_110], rax
0x18000bd4d  lea     rax, [rbp+var_28]
0x18000bd51  mov     [rsp+140h+var_118], rax
0x18000bd56  lea     rax, [rbp+var_20]
0x18000bd5a  mov     [rsp+140h+var_120], rax
0x18000bd5f  lea     rdx, unk_180015AA0
0x18000bd66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000bd6b  jmp     loc_18000BE01
0x18000bd70  lea     rdx, [rbp+SRWLock]
0x18000bd74  call    ?LockExclusive@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000bd79  mov     rax, [rbx+110h]
0x18000bd80  mov     dword ptr [rax], 2
0x18000bd86  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000bd8a  test    rcx, rcx
0x18000bd8d  jz      short loc_18000BD9B
0x18000bd8f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bd96  nop     dword ptr [rax+rax+00h]
0x18000bd9b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000bda0  mov     rdi, [rax+8]
0x18000bda4  mov     eax, [rdi]
0x18000bda6  cmp     eax, 5
0x18000bda9  jbe     short loc_18000BE01
0x18000bdab  call    cs:__imp_GetCurrentThreadId
0x18000bdb2  nop     dword ptr [rax+rax+00h]
0x18000bdb7  mov     dword ptr [rbp+SRWLock], eax
0x18000bdba  mov     r8, [rbx+110h]
0x18000bdc1  mov     eax, [r8+48h]
0x18000bdc5  mov     [rbp+arg_8], eax
0x18000bdc8  mov     [rbp+arg_10], 0
0x18000bdd0  add     r8, 8
0x18000bdd4  lea     rax, [rbp+SRWLock]
0x18000bdd8  mov     [rsp+140h+var_110], rax
0x18000bddd  lea     rax, [rbp+arg_8]
0x18000bde1  mov     [rsp+140h+var_118], rax
0x18000bde6  lea     rax, [rbp+arg_10]
0x18000bdea  mov     [rsp+140h+var_120], rax
0x18000bdef  xor     r9d, r9d
0x18000bdf2  lea     rdx, byte_180015BE9
0x18000bdf9  mov     rcx, rdi
0x18000bdfc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000be01  mov     rcx, rbx
0x18000be04  add     rsp, 130h
0x18000be0b  pop     rdi
0x18000be0c  pop     rbx
0x18000be0d  pop     rbp
0x18000be0e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

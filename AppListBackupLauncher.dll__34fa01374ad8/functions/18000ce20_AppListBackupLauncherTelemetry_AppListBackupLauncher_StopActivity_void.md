# AppListBackupLauncherTelemetry::AppListBackupLauncher::StopActivity(void)

- ea: `0x18000ce20`
- end: `0x18000d15e`
- name: `?StopActivity@AppListBackupLauncher@AppListBackupLauncherTelemetry@@MEAAXXZ`
- size: `830`
- prototype: `void __fastcall(AppListBackupLauncherTelemetry::AppListBackupLauncher *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000117c`
- `0x180001a4c`
- `0x180002300`
- `0x1800091f0`
- `0x180009e0c`
- `0x18000ce20`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d01f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d01f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d05e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d05e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0e6`

## string_xrefs

- `0x18000d101`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall AppListBackupLauncherTelemetry::AppListBackupLauncher::StopActivity(
        AppListBackupLauncherTelemetry::AppListBackupLauncher *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B8h] [rbp-68h] BYREF
  int v19; // [rsp+BCh] [rbp-64h] BYREF
  int v20; // [rsp+C0h] [rbp-60h] BYREF
  int v21; // [rsp+C4h] [rbp-5Ch] BYREF
  int *v22; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-50h] BYREF
  int *v24; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-38h] BYREF
  int *v27; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = AppListBackupLauncherTelemetry::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v22 = (int *)*((_QWORD *)v4 + 15);
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = (int *)*((_QWORD *)v4 + 12);
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = (int *)*((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)word_180014F92,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          &v29,
          (__int64)&v15,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          (__int64)&v19,
          &v25,
          &v24,
          (__int64)&v18,
          &v23,
          &v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = AppListBackupLauncherTelemetry::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, &byte_1800153D7, v11 + 8, 0, 5, v31);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x18000ce20  mov     [rsp-8+arg_8], rbx
0x18000ce25  mov     [rsp-8+arg_10], rdi
0x18000ce2a  push    rbp
0x18000ce2b  lea     rbp, [rsp-50h]
0x18000ce30  sub     rsp, 170h
0x18000ce37  mov     rax, cs:__security_cookie
0x18000ce3e  xor     rax, rsp
0x18000ce41  mov     [rbp+50h+var_10], rax
0x18000ce45  mov     rbx, rcx
0x18000ce48  mov     rdi, [rcx+110h]
0x18000ce4f  mov     eax, [rdi+48h]
0x18000ce52  test    eax, eax
0x18000ce54  jns     loc_18000D000
0x18000ce5a  add     rdi, 50h ; 'P'
0x18000ce5e  cmp     eax, [rdi+8]
0x18000ce61  jnz     loc_18000D000
0x18000ce67  test    rdi, rdi
0x18000ce6a  jz      loc_18000D000
0x18000ce70  lea     rdx, [rbp+50h+SRWLock]
0x18000ce74  call    ?LockExclusive@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ce79  mov     rax, [rbx+110h]
0x18000ce80  mov     dword ptr [rax], 2
0x18000ce86  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000ce8a  test    rcx, rcx
0x18000ce8d  jz      short loc_18000CE95
0x18000ce8f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ce95  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000ce9a  mov     r9, rax
0x18000ce9d  mov     ecx, [rax]
0x18000ce9f  cmp     ecx, 5
0x18000cea2  jbe     loc_18000D0D6
0x18000cea8  mov     rax, [rax+18h]
0x18000ceac  mov     rcx, [r9+10h]
0x18000ceb0  mov     rdx, 400000000000h
0x18000ceba  test    rdx, rcx
0x18000cebd  jz      loc_18000D0D6
0x18000cec3  mov     rcx, rax
0x18000cec6  and     rcx, rdx
0x18000cec9  cmp     rcx, rax
0x18000cecc  jnz     loc_18000D0D6
0x18000ced2  mov     rax, [rdi+78h]
0x18000ced6  mov     [rbp+50h+var_A8], rax
0x18000ceda  mov     rax, [rdi+70h]
0x18000cede  mov     [rbp+50h+var_A0], rax
0x18000cee2  mov     eax, [rdi+68h]
0x18000cee5  mov     [rbp+50h+var_B8], eax
0x18000cee8  mov     rax, [rdi+60h]
0x18000ceec  mov     [rbp+50h+var_98], rax
0x18000cef0  mov     rax, [rdi+58h]
0x18000cef4  mov     [rbp+50h+var_90], rax
0x18000cef8  mov     eax, [rdi+50h]
0x18000cefb  mov     [rbp+50h+var_B4], eax
0x18000cefe  mov     rax, [rdi+48h]
0x18000cf02  mov     [rbp+50h+var_88], rax
0x18000cf06  mov     eax, [rdi+20h]
0x18000cf09  mov     [rbp+50h+var_B0], eax
0x18000cf0c  mov     rax, [rdi+18h]
0x18000cf10  mov     [rbp+50h+var_80], rax
0x18000cf14  mov     eax, [rdi]
0x18000cf16  mov     [rbp+50h+var_AC], eax
0x18000cf19  mov     rax, [rdi+80h]
0x18000cf20  mov     [rbp+50h+var_78], rax
0x18000cf24  mov     eax, [rdi+40h]
0x18000cf27  mov     [rbp+50h+var_D0], eax
0x18000cf2a  mov     rax, [rdi+38h]
0x18000cf2e  mov     [rbp+50h+var_70], rax
0x18000cf32  mov     eax, [rdi+8]
0x18000cf35  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000cf38  mov     eax, 1000000h
0x18000cf3d  mov     [rbp+50h+var_68], rax
0x18000cf41  mov     [rbp+50h+var_C0], rax
0x18000cf45  mov     r8, [rbx+110h]
0x18000cf4c  add     r8, 8
0x18000cf50  lea     rax, [rbp+50h+var_A8]
0x18000cf54  mov     [rsp+170h+var_D8], rax
0x18000cf5c  lea     rax, [rbp+50h+var_A0]
0x18000cf60  mov     [rsp+170h+var_E0], rax
0x18000cf68  lea     rax, [rbp+50h+var_B8]
0x18000cf6c  mov     [rsp+170h+var_E8], rax
0x18000cf74  lea     rax, [rbp+50h+var_98]
0x18000cf78  mov     [rsp+170h+var_F0], rax
0x18000cf80  lea     rax, [rbp+50h+var_90]
0x18000cf84  mov     [rsp+170h+var_F8], rax
0x18000cf89  lea     rax, [rbp+50h+var_B4]
0x18000cf8d  mov     [rsp+170h+var_100], rax
0x18000cf92  lea     rax, [rbp+50h+var_88]
0x18000cf96  mov     [rsp+170h+var_108], rax
0x18000cf9b  lea     rax, [rbp+50h+var_B0]
0x18000cf9f  mov     [rsp+170h+var_110], rax
0x18000cfa4  lea     rax, [rbp+50h+var_80]
0x18000cfa8  mov     [rsp+170h+var_118], rax
0x18000cfad  lea     rax, [rbp+50h+var_AC]
0x18000cfb1  mov     [rsp+170h+var_120], rax
0x18000cfb6  lea     rax, [rbp+50h+var_78]
0x18000cfba  mov     [rsp+170h+var_128], rax
0x18000cfbf  lea     rax, [rbp+50h+var_D0]
0x18000cfc3  mov     [rsp+170h+var_130], rax
0x18000cfc8  lea     rax, [rbp+50h+var_70]
0x18000cfcc  mov     [rsp+170h+var_138], rax
0x18000cfd1  lea     rax, [rbp+50h+SRWLock]
0x18000cfd5  mov     [rsp+170h+var_140], rax
0x18000cfda  lea     rax, [rbp+50h+var_68]
0x18000cfde  mov     [rsp+170h+var_148], rax
0x18000cfe3  lea     rax, [rbp+50h+var_C0]
0x18000cfe7  mov     [rsp+170h+var_150], rax
0x18000cfec  lea     rdx, word_180014F92
0x18000cff3  mov     rcx, r9
0x18000cff6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000cffb  jmp     loc_18000D0D6
0x18000d000  lea     rdx, [rbp+50h+var_C0]
0x18000d004  call    ?LockExclusive@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d009  mov     rax, [rbx+110h]
0x18000d010  mov     dword ptr [rax], 2
0x18000d016  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000d01a  test    rcx, rcx
0x18000d01d  jz      short loc_18000D025
0x18000d01f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d025  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000d02a  mov     rdi, rax
0x18000d02d  mov     ecx, [rax]
0x18000d02f  cmp     ecx, 5
0x18000d032  jbe     loc_18000D0D6
0x18000d038  mov     rax, [rax+18h]
0x18000d03c  mov     rcx, [rdi+10h]
0x18000d040  mov     rdx, 400000000000h
0x18000d04a  test    rdx, rcx
0x18000d04d  jz      loc_18000D0D6
0x18000d053  mov     rcx, rax
0x18000d056  and     rcx, rdx
0x18000d059  cmp     rcx, rax
0x18000d05c  jnz     short loc_18000D0D6
0x18000d05e  call    cs:__imp_GetCurrentThreadId
0x18000d064  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000d067  mov     r8, [rbx+110h]
0x18000d06e  mov     eax, [r8+48h]
0x18000d072  mov     [rbp+50h+var_D0], eax
0x18000d075  mov     eax, 1000000h
0x18000d07a  mov     [rbp+50h+var_C0], rax
0x18000d07e  lea     rax, [rbp+50h+SRWLock]
0x18000d082  mov     [rbp+50h+var_20], rax
0x18000d086  mov     [rbp+50h+var_18], 4
0x18000d08e  lea     rax, [rbp+50h+var_D0]
0x18000d092  mov     [rbp+50h+var_30], rax
0x18000d096  mov     [rbp+50h+var_28], 4
0x18000d09e  lea     rax, [rbp+50h+var_C0]
0x18000d0a2  mov     [rbp+50h+var_40], rax
0x18000d0a6  mov     [rbp+50h+var_38], 8
0x18000d0ae  add     r8, 8
0x18000d0b2  lea     rax, [rbp+50h+var_60]
0x18000d0b6  mov     [rsp+170h+var_148], rax
0x18000d0bb  mov     dword ptr [rsp+170h+var_150], 5
0x18000d0c3  xor     r9d, r9d
0x18000d0c6  lea     rdx, byte_1800153D7
0x18000d0cd  mov     rcx, rdi
0x18000d0d0  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d0d5  nop
0x18000d0d6  cmp     dword ptr [rbx+138h], 0
0x18000d0dd  jz      short loc_18000D13D
0x18000d0df  add     rbx, 120h
0x18000d0e6  call    cs:__imp_GetCurrentThreadId
0x18000d0ec  cmp     [rbx+18h], eax
0x18000d0ef  jz      short loc_18000D10D
0x18000d0f1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000d0f8  test    rax, rax
0x18000d0fb  jz      short loc_18000D10D
0x18000d0fd  mov     rdx, [rbp+58h]
0x18000d101  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000d108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d10d  mov     dword ptr [rbx+18h], 0
0x18000d114  mov     rcx, [rbx]
0x18000d117  jmp     short loc_18000D125
0x18000d119  cmp     rax, rbx
0x18000d11c  jz      short loc_18000D12F
0x18000d11e  lea     rcx, [rax+10h]
0x18000d122  mov     [rbx], rcx
0x18000d125  mov     rax, [rcx]
0x18000d128  test    rax, rax
0x18000d12b  jnz     short loc_18000D119
0x18000d12d  jmp     short loc_18000D136
0x18000d12f  mov     rax, [rbx+10h]
0x18000d133  mov     [rcx], rax
0x18000d136  mov     qword ptr [rbx], 0
0x18000d13d  mov     rcx, [rbp+50h+var_10]
0x18000d141  xor     rcx, rsp; StackCookie
0x18000d144  call    __security_check_cookie
0x18000d149  lea     r11, [rsp+170h+var_s0]
0x18000d151  mov     rbx, [r11+18h]
0x18000d155  mov     rdi, [r11+20h]
0x18000d159  mov     rsp, r11
0x18000d15c  pop     rbp
0x18000d15d  retn
```

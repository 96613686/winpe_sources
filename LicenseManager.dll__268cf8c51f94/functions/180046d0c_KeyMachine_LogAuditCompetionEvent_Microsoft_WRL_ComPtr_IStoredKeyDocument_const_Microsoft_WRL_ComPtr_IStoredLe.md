# KeyMachine::LogAuditCompetionEvent(Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &,unsigned __int64)

- ea: `0x180046d0c`
- end: `0x180046f7f`
- name: `?LogAuditCompetionEvent@KeyMachine@@IEAAXAEBV?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@AEBV?$ComPtr@UIStoredLeaseDocument@@@34@_K@Z`
- size: `627`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180042c70`
- `0x1800444c0`

## callees

- `0x180002478`
- `0x180013b50`
- `0x180046d0c`
- `0x180046f88`
- `0x1800593bc`
- `0x1800626ec`
- `0x180076e64`
- `0x180085944`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046f2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046f2d`
- `ext-ms-win-core-licensemanager-l1-1-0!AuditLicenseUsageCompleted` at `0x180046ef6`
- `ext-ms-win-core-licensemanager-l1-1-0!AuditLicenseUsageCompleted` at `0x180046ef6`

## string_xrefs

- `0x180046d6a`: `KeyMachine::LogAuditCompetionEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KeyMachine::LogAuditCompetionEvent(__int64 a1, __int64 *a2, _QWORD *a3, __int64 a4)
{
  int v4; // r14d
  __int64 v7; // r10
  int v8; // ecx
  _QWORD *v9; // rdi
  _QWORD *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // ecx
  int Format; // [rsp+20h] [rbp-58h]
  int Formata; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+50h] [rbp-28h] BYREF
  _DWORD v25[3]; // [rsp+54h] [rbp-24h] BYREF
  __int128 v26; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+C8h] [rbp+50h] BYREF

  if ( a4 )
  {
    v4 = a4;
    v7 = *a2;
    if ( *a2 )
    {
      v24 = 0;
      if ( *a3 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a3 + 96LL))(*a3, &v24);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            (const char *)(unsigned int)v14,
            Format);
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 96LL))(v7, &v24);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x253,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            (const char *)(unsigned int)v15,
            Format);
      }
      if ( v24 )
      {
        EnterCriticalSection(&SequenceLock);
        v28 = &SequenceLock;
        if ( (unsigned __int8)IsCompareContentIdPresent(v16) )
        {
          v17 = *(_QWORD *)(a1 + 296);
          v18 = (_QWORD *)(a1 + 200);
          if ( *(_QWORD *)(a1 + 224) > 7u )
            v18 = (_QWORD *)*v18;
          v19 = (_QWORD *)(a1 + 168);
          if ( *(_QWORD *)(a1 + 192) > 7u )
            v19 = (_QWORD *)*v19;
          v26 = *(_OWORD *)(a1 + 312);
          Formata = v17;
          v20 = AuditLicenseUsageCompleted(v19, v18, *(unsigned int *)(a1 + 284), *(_QWORD *)(a1 + 272));
          v21 = (unsigned int)retaddr;
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x25E,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              (const char *)(unsigned int)v20,
              Formata);
        }
        else
        {
          KeyMachine::DoAuditLeaseUsage((_DWORD)a3, a1 + 168, v4, a1 + 312, a1 + 328);
        }
        SetLastAuditEventId(v21);
        LeaveCriticalSection(&SequenceLock);
      }
    }
    else
    {
      v8 = *(_DWORD *)(a1 + 256);
      v9 = (_QWORD *)(a1 + 168);
      if ( *(_QWORD *)(a1 + 192) <= 7u )
        v10 = (_QWORD *)(a1 + 168);
      else
        v10 = (_QWORD *)*v9;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        0x240u,
        "KeyMachine::LogAuditCompetionEvent",
        (wchar_t *)L"DoLicenseInUseAuditing for %s has time and no key and usage 0x%08x",
        v10,
        v8);
      if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
      {
        LOBYTE(v28) = *a3 != 0;
        v25[0] = *(_DWORD *)(a1 + 256);
        if ( *(_QWORD *)(a1 + 192) > 7u )
          v9 = (_QWORD *)*v9;
        *(_QWORD *)&v26 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v11,
          (unsigned int)&word_1800D6D3E,
          v12,
          v13,
          (__int64)&v26,
          (__int64)v25,
          (__int64)&v28);
      }
    }
  }
}

```

## disassembly

```asm
0x180046d0c  test    r9, r9
0x180046d0f  jz      locret_180046F3F
0x180046d15  push    rbp
0x180046d16  push    rbx
0x180046d17  push    rsi
0x180046d18  push    rdi
0x180046d19  push    r12
0x180046d1b  push    r14
0x180046d1d  mov     rbp, rsp
0x180046d20  sub     rsp, 78h
0x180046d24  mov     r14, r9
0x180046d27  mov     rsi, r8
0x180046d2a  mov     rbx, rcx
0x180046d2d  mov     r10, [rdx]
0x180046d30  test    r10, r10
0x180046d33  jnz     loc_180046E00
0x180046d39  mov     ecx, [rcx+100h]
0x180046d3f  lea     rdi, [rbx+0A8h]
0x180046d46  cmp     qword ptr [rdi+18h], 7
0x180046d4b  jbe     short loc_180046D52
0x180046d4d  mov     rax, [rdi]
0x180046d50  jmp     short loc_180046D55
0x180046d52  mov     rax, rdi
0x180046d55  mov     dword ptr [rsp+78h+var_48], ecx
0x180046d59  mov     [rsp+78h+var_50], rax
0x180046d5e  lea     rax, aDolicenseinuse; "DoLicenseInUseAuditing for %s has time "...
0x180046d65  mov     [rsp+78h+Format], rax; Format
0x180046d6a  lea     r9, aKeymachineLoga_0; "KeyMachine::LogAuditCompetionEvent"
0x180046d71  mov     r8d, 240h; unsigned int
0x180046d77  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180046d7e  mov     ecx, 1; unsigned int
0x180046d83  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180046d88  mov     eax, cs:dword_1800F11D0
0x180046d8e  cmp     eax, 5
0x180046d91  jbe     loc_180046F33
0x180046d97  mov     rdx, 400000000000h
0x180046da1  lea     rcx, dword_1800F11D0
0x180046da8  call    _tlgKeywordOn
0x180046dad  test    al, al
0x180046daf  jz      loc_180046F33
0x180046db5  cmp     qword ptr [rsi], 0
0x180046db9  setnz   byte ptr [rbp+arg_18]
0x180046dbd  mov     eax, [rbx+100h]
0x180046dc3  mov     [rbp+var_24], eax
0x180046dc6  cmp     qword ptr [rdi+18h], 7
0x180046dcb  jbe     short loc_180046DD0
0x180046dcd  mov     rdi, [rdi]
0x180046dd0  mov     qword ptr [rbp+var_18], rdi
0x180046dd4  lea     rax, [rbp+arg_18]
0x180046dd8  mov     [rsp+78h+var_48], rax
0x180046ddd  lea     rax, [rbp+var_24]
0x180046de1  mov     [rsp+78h+var_50], rax
0x180046de6  lea     rax, [rbp+var_18]
0x180046dea  mov     [rsp+78h+Format], rax
0x180046def  lea     rdx, word_1800D6D3E
0x180046df6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180046dfb  jmp     loc_180046F33
0x180046e00  mov     [rbp+var_28], 0
0x180046e07  mov     rcx, [r8]
0x180046e0a  lea     rdx, [rbp+var_28]
0x180046e0e  test    rcx, rcx
0x180046e11  jz      short loc_180046E2D
0x180046e13  mov     rax, [rcx]
0x180046e16  mov     rax, [rax+60h]
0x180046e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e1f  mov     rcx, [rbp+30h]; this
0x180046e23  test    eax, eax
0x180046e25  js      loc_180046F55
0x180046e2b  jmp     short loc_180046E48
0x180046e2d  mov     rax, [r10]
0x180046e30  mov     rcx, r10
0x180046e33  mov     rax, [rax+60h]
0x180046e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e3c  mov     rcx, [rbp+30h]; this
0x180046e40  test    eax, eax
0x180046e42  js      loc_180046F40
0x180046e48  cmp     [rbp+var_28], 0
0x180046e4c  jz      loc_180046F33
0x180046e52  lea     r12, ?SequenceLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SequenceLock
0x180046e59  mov     rcx, r12; lpCriticalSection
0x180046e5c  call    cs:__imp_EnterCriticalSection
0x180046e62  mov     [rbp+arg_18], r12
0x180046e66  lea     rdi, [rbx+148h]
0x180046e6d  call    IsCompareContentIdPresent
0x180046e72  test    al, al
0x180046e74  jz      loc_180046F06
0x180046e7a  cmp     qword ptr [rdi+10h], 0
0x180046e7f  jnz     short loc_180046E85
0x180046e81  xor     edi, edi
0x180046e83  jmp     short loc_180046E8F
0x180046e85  cmp     qword ptr [rdi+18h], 7
0x180046e8a  jbe     short loc_180046E8F
0x180046e8c  mov     rdi, [rdi]
0x180046e8f  mov     rax, [rbx+128h]
0x180046e96  lea     rdx, [rbx+0C8h]
0x180046e9d  cmp     qword ptr [rdx+18h], 7
0x180046ea2  jbe     short loc_180046EA7
0x180046ea4  mov     rdx, [rdx]
0x180046ea7  lea     rcx, [rbx+0A8h]
0x180046eae  cmp     qword ptr [rcx+18h], 7
0x180046eb3  jbe     short loc_180046EB8
0x180046eb5  mov     rcx, [rcx]
0x180046eb8  movups  xmm0, xmmword ptr [rbx+138h]
0x180046ebf  movdqu  [rbp+var_18], xmm0
0x180046ec4  lea     r8, ?AuditLogSequenceId@@3KA; ulong AuditLogSequenceId
0x180046ecb  mov     [rsp+78h+var_38], r8
0x180046ed0  mov     [rsp+78h+var_40], r14
0x180046ed5  mov     [rsp+78h+var_48], rdi
0x180046eda  lea     r8, [rbp+var_18]
0x180046ede  mov     [rsp+78h+var_50], r8
0x180046ee3  mov     [rsp+78h+Format], rax; int
0x180046ee8  mov     r9, [rbx+110h]
0x180046eef  mov     r8d, [rbx+11Ch]
0x180046ef6  call    cs:__imp_AuditLicenseUsageCompleted
0x180046efc  mov     rcx, [rbp+30h]; this
0x180046f00  test    eax, eax
0x180046f02  js      short loc_180046F6A
0x180046f04  jmp     short loc_180046F24
0x180046f06  lea     r9, [rbx+138h]
0x180046f0d  lea     rdx, [rbx+0A8h]
0x180046f14  mov     [rsp+78h+Format], rdi
0x180046f19  mov     r8, r14
0x180046f1c  mov     rcx, rsi
0x180046f1f  call    ?DoAuditLeaseUsage@KeyMachine@@KAXAEBV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@AEBVContentIdString@@_KAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; KeyMachine::DoAuditLeaseUsage(Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &,ContentIdString const &,unsigned __int64,_GUID const &,std::wstring const &,ulong &)
0x180046f24  call    ?SetLastAuditEventId@@YAXK@Z; SetLastAuditEventId(ulong)
0x180046f29  nop
0x180046f2a  mov     rcx, r12; lpCriticalSection
0x180046f2d  call    cs:__imp_LeaveCriticalSection
0x180046f33  add     rsp, 78h
0x180046f37  pop     r14
0x180046f39  pop     r12
0x180046f3b  pop     rdi
0x180046f3c  pop     rsi
0x180046f3d  pop     rbx
0x180046f3e  pop     rbp
0x180046f3f  retn
0x180046f40  mov     r9d, eax; char *
0x180046f43  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180046f4a  mov     edx, 253h; void *
0x180046f4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046f55  mov     r9d, eax; char *
0x180046f58  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180046f5f  mov     edx, 24Fh; void *
0x180046f64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046f6a  mov     r9d, eax; char *
0x180046f6d  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180046f74  mov     edx, 25Eh; void *
0x180046f79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

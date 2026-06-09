# CApplication::SendAppClosureNotification(void)

- ea: `0x18003988c`
- end: `0x1800399c5`
- name: `?SendAppClosureNotification@CApplication@@QEAAXXZ`
- size: `313`
- prototype: `void __fastcall(CApplication *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002fc28`

## callees

- `0x18001b750`
- `0x18001d0b0`
- `0x18001f8d4`
- `0x180027f10`
- `0x180031960`
- `0x18003988c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800398b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800399a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800399a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039971`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x18003998e`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x18003998e`

## pseudocode

```c
void __fastcall CApplication::SendAppClosureNotification(CApplication *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rcx
  __int64 Next; // rax
  __int64 v5; // rbx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ecx
  DWORD CurrentProcessId; // eax
  __int64 v11; // rdx
  int v12; // [rsp+40h] [rbp-19h] BYREF
  __int64 v13; // [rsp+48h] [rbp-11h] BYREF
  __int64 v14; // [rsp+50h] [rbp-9h] BYREF
  void *v15; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v16[5]; // [rsp+60h] [rbp+7h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v13 = *((_QWORD *)this + 9);
  while ( v13 )
  {
    Next = ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(v3, &v13);
    v5 = *(_QWORD *)Next;
    if ( *(_DWORD *)(*(_QWORD *)Next + 456LL) && !*(_DWORD *)(v5 + 416) )
    {
      v6 = AudioSrvPolicyManagerTelemetryProvider::Provider();
      if ( *(_DWORD *)v6 > 4u && (unsigned __int8)tlgKeywordOn(v6, 0x20000) )
      {
        v9 = *(_DWORD *)(v5 + 160);
        v14 = *((_QWORD *)this + 87);
        v15 = (void *)*((_QWORD *)this + 3);
        v12 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v7,
          byte_1800573DD,
          v7,
          v8,
          &v15,
          (__int64)&v14,
          (__int64)&v12);
      }
      memset((char *)v16 + 4, 0, 29);
      v16[0] = 0x1000000000021LL;
      CurrentProcessId = GetCurrentProcessId();
      v11 = *(unsigned int *)(v5 + 160);
      v16[1] = CurrentProcessId;
      LODWORD(v16[3]) = 1;
      GenerateMediaEvent(v16, v11);
    }
  }
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18003988c  push    rbp
0x18003988e  push    rbx
0x18003988f  push    rsi
0x180039890  push    rdi
0x180039891  lea     rbp, [rsp-3Fh]
0x180039896  sub     rsp, 98h
0x18003989d  mov     rax, cs:__security_cookie
0x1800398a4  xor     rax, rsp
0x1800398a7  mov     [rbp+57h+var_28], rax
0x1800398ab  lea     rdi, [rcx+20h]
0x1800398af  mov     rsi, rcx
0x1800398b2  mov     rcx, rdi; lpCriticalSection
0x1800398b5  call    cs:__imp_EnterCriticalSection
0x1800398bb  mov     rax, [rsi+48h]
0x1800398bf  mov     [rbp+57h+var_68], rax
0x1800398c3  test    rax, rax
0x1800398c6  jz      loc_18003999F
0x1800398cc  lea     rdx, [rbp+57h+var_68]
0x1800398d0  call    ?GetNext@?$CAtlList@PEAVCProcess@@V?$CElementTraits@PEAVCProcess@@@ATL@@@ATL@@QEAAAEAPEAVCProcess@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(__POSITION * &)
0x1800398d5  mov     rbx, [rax]
0x1800398d8  cmp     dword ptr [rbx+1C8h], 0
0x1800398df  jz      loc_180039994
0x1800398e5  cmp     dword ptr [rbx+1A0h], 0
0x1800398ec  jnz     loc_180039994
0x1800398f2  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x1800398f7  mov     r8, rax
0x1800398fa  mov     ecx, [rax]
0x1800398fc  cmp     ecx, 4
0x1800398ff  jbe     short loc_180039958
0x180039901  mov     edx, 20000h
0x180039906  mov     rcx, rax
0x180039909  call    _tlgKeywordOn
0x18003990e  test    al, al
0x180039910  jz      short loc_180039958
0x180039912  mov     rax, [rsi+2B8h]
0x180039919  lea     rdx, byte_1800573DD
0x180039920  mov     ecx, [rbx+0A0h]
0x180039926  mov     [rbp+57h+var_60], rax
0x18003992a  mov     rax, [rsi+18h]
0x18003992e  mov     [rbp+57h+var_58], rax
0x180039932  lea     rax, [rbp+57h+var_70]
0x180039936  mov     [rsp+0B0h+var_80], rax
0x18003993b  lea     rax, [rbp+57h+var_60]
0x18003993f  mov     [rsp+0B0h+var_88], rax
0x180039944  lea     rax, [rbp+57h+var_58]
0x180039948  mov     [rbp+57h+var_70], ecx
0x18003994b  mov     rcx, r8
0x18003994e  mov     [rsp+0B0h+var_90], rax
0x180039953  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180039958  xorps   xmm0, xmm0
0x18003995b  mov     [rbp+57h+var_50], 21h ; '!'
0x180039962  movups  [rbp+57h+var_4C], xmm0
0x180039966  mov     dword ptr [rbp+57h+var_4C], 10000h
0x18003996d  movups  [rbp+57h+var_4C+0Dh], xmm0
0x180039971  call    cs:__imp_GetCurrentProcessId
0x180039977  mov     edx, [rbx+0A0h]
0x18003997d  lea     rcx, [rbp+57h+var_50]
0x180039981  mov     eax, eax
0x180039983  mov     qword ptr [rbp+57h+var_4C+4], rax
0x180039987  mov     [rbp+57h+var_38], 1
0x18003998e  call    cs:__imp_GenerateMediaEvent
0x180039994  cmp     [rbp+57h+var_68], 0
0x180039999  jnz     loc_1800398CC
0x18003999f  test    rdi, rdi
0x1800399a2  jz      short loc_1800399AD
0x1800399a4  mov     rcx, rdi; lpCriticalSection
0x1800399a7  call    cs:__imp_LeaveCriticalSection
0x1800399ad  mov     rcx, [rbp+57h+var_28]
0x1800399b1  xor     rcx, rsp; StackCookie
0x1800399b4  call    __security_check_cookie
0x1800399b9  add     rsp, 98h
0x1800399c0  pop     rdi
0x1800399c1  pop     rsi
0x1800399c2  pop     rbx
0x1800399c3  pop     rbp
0x1800399c4  retn
```

# DiagnosticServer::ServiceHandler(ulong,ulong,void *)

- ea: `0x1800058ec`
- end: `0x180005a1d`
- name: `?ServiceHandler@DiagnosticServer@@IEAAKKKPEAX@Z`
- size: `305`
- prototype: `unsigned int __fastcall(DiagnosticServer *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180005e70`

## callees

- `0x18000140c`
- `0x180001720`
- `0x1800058ec`
- `0x180005eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005915`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005915`

## string_xrefs

- `0x18000596d`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005982`: `DiagnosticServer::ServiceHandler`
- `0x180005991`: `Service Handler handling SCM calls`

## pseudocode

```c
__int64 __fastcall DiagnosticServer::ServiceHandler(
        struct _RTL_CRITICAL_SECTION *this,
        int a2,
        unsigned int a3,
        void *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v15; // [rsp+60h] [rbp-20h] BYREF
  const char *v16; // [rsp+68h] [rbp-18h] BYREF
  const char *v17; // [rsp+70h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+78h] [rbp-8h] BYREF
  int v19; // [rsp+B0h] [rbp+30h] BYREF
  int v20; // [rsp+B8h] [rbp+38h]
  unsigned int v21; // [rsp+C0h] [rbp+40h]
  void *v22; // [rsp+C8h] [rbp+48h]

  v22 = a4;
  v21 = a3;
  v4 = this + 2;
  v7 = 0;
  EnterCriticalSection(this + 2);
  switch ( a2 )
  {
    case 1:
      goto LABEL_9;
    case 4:
      break;
    case 5:
LABEL_9:
      DiagnosticServer::StopService((DiagnosticServer *)this);
      break;
    case 32:
      v7 = 1115;
      if ( HIDWORD(this->LockSemaphore) != 3 )
        v7 = 0;
      break;
    default:
      v7 = 120;
      break;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v9, v8, v10) )
  {
    v21 = v7;
    v15 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v20 = a2;
    v16 = "DiagnosticServer::ServiceHandler";
    v17 = "Service Handler handling SCM calls";
    v18 = this + 3;
    LODWORD(v22) = 322;
    v19 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (__int64)word_18002E8AA,
      v12,
      v13,
      &v18,
      (__int64)&v19,
      &v17,
      &v16,
      &v15);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return v7;
}

```

## disassembly

```asm
0x1800058ec  mov     [rsp-28h+arg_18], r9
0x1800058f1  mov     [rsp-28h+arg_10], r8d
0x1800058f6  push    rbp
0x1800058f7  push    rbx
0x1800058f8  push    rsi
0x1800058f9  push    rdi
0x1800058fa  push    r14
0x1800058fc  mov     rbp, rsp
0x1800058ff  sub     rsp, 80h
0x180005906  lea     rsi, [rcx+50h]
0x18000590a  mov     rdi, rcx
0x18000590d  mov     rcx, rsi; lpCriticalSection
0x180005910  mov     r14d, edx
0x180005913  xor     ebx, ebx
0x180005915  call    cs:__imp_EnterCriticalSection
0x18000591b  mov     eax, r14d
0x18000591e  sub     eax, 1
0x180005921  jz      short loc_180005949
0x180005923  sub     eax, 3
0x180005926  jz      short loc_180005951
0x180005928  sub     eax, 1
0x18000592b  jz      short loc_180005949
0x18000592d  cmp     eax, 1Bh
0x180005930  jz      short loc_180005939
0x180005932  mov     ebx, 78h ; 'x'
0x180005937  jmp     short loc_180005951
0x180005939  xor     eax, eax
0x18000593b  mov     ebx, 45Bh
0x180005940  cmp     dword ptr [rdi+1Ch], 3
0x180005944  cmovnz  ebx, eax
0x180005947  jmp     short loc_180005951
0x180005949  mov     rcx, rdi; this
0x18000594c  call    ?StopService@DiagnosticServer@@IEAAXXZ; DiagnosticServer::StopService(void)
0x180005951  mov     eax, cs:dword_180039000
0x180005957  cmp     eax, 5
0x18000595a  jbe     loc_1800059FF
0x180005960  call    _tlgKeywordOn
0x180005965  test    al, al
0x180005967  jz      loc_1800059FF
0x18000596d  lea     rax, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180005974  mov     [rbp+arg_10], ebx
0x180005977  mov     [rbp+var_20], rax
0x18000597b  lea     rdx, word_18002E8AA
0x180005982  lea     rax, aDiagnosticserv_0; "DiagnosticServer::ServiceHandler"
0x180005989  mov     [rbp+arg_8], r14d
0x18000598d  mov     [rbp+var_18], rax
0x180005991  lea     rax, aServiceHandler; "Service Handler handling SCM calls"
0x180005998  mov     [rbp+var_10], rax
0x18000599c  lea     rax, [rdi+78h]
0x1800059a0  mov     [rbp+var_8], rax
0x1800059a4  lea     rax, [rbp+arg_10]
0x1800059a8  mov     [rsp+80h+var_28], rax
0x1800059ad  lea     rax, [rbp+arg_8]
0x1800059b1  mov     [rsp+80h+var_30], rax
0x1800059b6  lea     rax, [rbp+arg_18]
0x1800059ba  mov     [rsp+80h+var_38], rax
0x1800059bf  lea     rax, [rbp+var_20]
0x1800059c3  mov     [rsp+80h+var_40], rax
0x1800059c8  lea     rax, [rbp+var_18]
0x1800059cc  mov     [rsp+80h+var_48], rax
0x1800059d1  lea     rax, [rbp+var_10]
0x1800059d5  mov     [rsp+80h+var_50], rax
0x1800059da  lea     rax, [rbp+arg_0]
0x1800059de  mov     [rsp+80h+var_58], rax
0x1800059e3  lea     rax, [rbp+var_8]
0x1800059e7  mov     [rsp+80h+var_60], rax
0x1800059ec  mov     dword ptr [rbp+arg_18], 142h
0x1800059f3  mov     [rbp+arg_0], 0
0x1800059fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800059ff  test    rsi, rsi
0x180005a02  jz      short loc_180005A0D
0x180005a04  mov     rcx, rsi; lpCriticalSection
0x180005a07  call    cs:__imp_LeaveCriticalSection
0x180005a0d  mov     eax, ebx
0x180005a0f  add     rsp, 80h
0x180005a16  pop     r14
0x180005a18  pop     rdi
0x180005a19  pop     rsi
0x180005a1a  pop     rbx
0x180005a1b  pop     rbp
0x180005a1c  retn
```

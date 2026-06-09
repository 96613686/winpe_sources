# NTPSync::SyncTimeOverNetworkAsync(void)

- ea: `0x18000d330`
- end: `0x18000d5e2`
- name: `?SyncTimeOverNetworkAsync@NTPSync@@AEAAJXZ`
- size: `690`
- prototype: `__int64 __fastcall(NTPSync *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task`

## callees

- `0x180001010`
- `0x180001218`
- `0x180001270`
- `0x1800012f0`
- `0x18000131c`
- `0x1800013ac`
- `0x180009194`
- `0x18000d330`
- `0x18000d640`
- `0x18001020c`
- `0x1800102c4`
- `0x180010514`
- `0x180010578`
- `0x180010800`
- `0x180010ac0`

## string_xrefs

- `0x18000d3db`: `onecore\base\time\autotime\timeservice\ntpsync.cpp`

## pseudocode

```c
__int64 __fastcall NTPSync::SyncTimeOverNetworkAsync(NTPSync *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  _QWORD *v5; // rax
  __int64 result; // rax
  unsigned __int16 *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  char v11; // si
  unsigned int v12; // r15d
  unsigned int v13; // r14d
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  int v17; // r9d
  unsigned int v18; // eax
  int v19; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  _QWORD *v21; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v22; // [rsp+68h] [rbp+38h] BYREF

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
  {
    v5 = (_QWORD *)(*(_QWORD *)this + 24LL);
    if ( *(_QWORD *)(*(_QWORD *)this + 48LL) > 7u )
      v5 = (_QWORD *)*v5;
    v21 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v2,
      (unsigned int)&byte_180016FFF,
      v3,
      v4,
      (__int64)&v21);
  }
  if ( !*(_BYTE *)(*(_QWORD *)this + 5LL) )
    return 0;
  if ( *(_BYTE *)(*(_QWORD *)this + 7LL) )
    WpW32TimeEnableServiceLogging();
  else
    WpW32TimeDisableServiceLogging();
  v7 = (unsigned __int16 *)(*(_QWORD *)this + 24LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 48LL) > 7u )
    v7 = *(unsigned __int16 **)v7;
  v8 = WpW32TimeSetTimerServers(v7);
  v9 = v8;
  if ( v8 >= 0 )
  {
    result = WpW32TimeStartService();
    if ( (int)result < 0 )
      return result;
    v11 = 0;
    v12 = 15000;
    v13 = 0;
    while ( 1 )
    {
      if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
      {
        LOBYTE(v21) = v11;
        v22 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v10,
          (unsigned int)byte_180016F13,
          v14,
          v15,
          (__int64)&v22,
          (__int64)&v21);
      }
      LOBYTE(v10) = v11;
      v16 = WpW32TimeSyncNow(v10);
      v9 = v16;
      if ( v16 + 2095972095 <= 1 )
      {
        if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
        {
          LODWORD(v21) = v12;
          v22 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18001C010,
            (unsigned int)byte_180017049,
            0,
            v17,
            (__int64)&v22,
            (__int64)&v21);
        }
        if ( (unsigned __int8)wil::slim_event_t<1>::wait(*((_QWORD *)this + 2), v12) )
        {
          if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18001C010,
              word_180016F42,
              0,
              0);
          WpW32TimeStopService(0);
          return 2147500036LL;
        }
        v18 = 2 * v12;
        v10 = 120000;
        v11 = 0;
        v12 = 120000;
        if ( v18 < 0x1D4C0 )
          v12 = v18;
      }
      else
      {
        if ( v16 != -2095972092 || *(_BYTE *)(*(_QWORD *)this + 8LL) )
        {
LABEL_34:
          if ( (unsigned int)dword_18001C010 > 4 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
            {
              LODWORD(v21) = v9;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_18001C010,
                (unsigned int)word_180016FD2,
                0,
                0,
                (__int64)&v21);
            }
          }
          WpW32TimeStopService(0);
          return v9;
        }
        v10 = (unsigned int)dword_18001C010;
        v11 = 1;
        if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
        {
          LODWORD(v21) = -2095972092;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18001C010,
            (unsigned int)&word_180016FA6,
            0,
            0,
            (__int64)&v21);
        }
      }
      if ( ++v13 >= 6 )
        goto LABEL_34;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEA,
    (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\ntpsync.cpp",
    (const char *)(unsigned int)v8,
    v19);
  return v9;
}

```

## disassembly

```asm
0x18000d330  mov     [rsp-28h+arg_10], rbx
0x18000d335  mov     [rsp-28h+arg_18], rsi
0x18000d33a  push    rbp
0x18000d33b  push    rdi
0x18000d33c  push    r13
0x18000d33e  push    r14
0x18000d340  push    r15
0x18000d342  mov     rbp, rsp
0x18000d345  sub     rsp, 30h
0x18000d349  mov     eax, cs:dword_18001C010
0x18000d34f  lea     r13, dword_18001C010
0x18000d356  mov     rdi, rcx
0x18000d359  cmp     eax, 4
0x18000d35c  jbe     short loc_18000D399
0x18000d35e  mov     edx, 200h
0x18000d363  mov     rcx, r13
0x18000d366  call    _tlgKeywordOn
0x18000d36b  test    al, al
0x18000d36d  jz      short loc_18000D399
0x18000d36f  mov     rax, [rdi]
0x18000d372  add     rax, 18h
0x18000d376  cmp     qword ptr [rax+18h], 7
0x18000d37b  jbe     short loc_18000D380
0x18000d37d  mov     rax, [rax]
0x18000d380  mov     [rbp+arg_0], rax
0x18000d384  lea     rdx, byte_180016FFF
0x18000d38b  lea     rax, [rbp+arg_0]
0x18000d38f  mov     qword ptr [rsp+30h+var_10], rax; int
0x18000d394  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000d399  mov     rax, [rdi]
0x18000d39c  cmp     byte ptr [rax+5], 0
0x18000d3a0  jnz     short loc_18000D3A9
0x18000d3a2  xor     eax, eax
0x18000d3a4  jmp     loc_18000D5CB
0x18000d3a9  cmp     byte ptr [rax+7], 0
0x18000d3ad  jz      short loc_18000D3B6
0x18000d3af  call    WpW32TimeEnableServiceLogging
0x18000d3b4  jmp     short loc_18000D3BB
0x18000d3b6  call    WpW32TimeDisableServiceLogging
0x18000d3bb  mov     rcx, [rdi]
0x18000d3be  add     rcx, 18h
0x18000d3c2  cmp     qword ptr [rcx+18h], 7
0x18000d3c7  jbe     short loc_18000D3CC
0x18000d3c9  mov     rcx, [rcx]; unsigned __int16 *
0x18000d3cc  call    WpW32TimeSetTimerServers
0x18000d3d1  mov     ebx, eax
0x18000d3d3  test    eax, eax
0x18000d3d5  jns     short loc_18000D3F6
0x18000d3d7  mov     rcx, [rbp+28h]; this
0x18000d3db  lea     r8, aOnecoreBaseTim_4; "onecore\\base\\time\\autotime\\timeserv"...
0x18000d3e2  mov     r9d, eax; char *
0x18000d3e5  mov     edx, 0EAh; void *
0x18000d3ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3ef  mov     eax, ebx
0x18000d3f1  jmp     loc_18000D5CB
0x18000d3f6  call    WpW32TimeStartService
0x18000d3fb  test    eax, eax
0x18000d3fd  js      loc_18000D5CB
0x18000d403  xor     sil, sil
0x18000d406  mov     r15d, 3A98h
0x18000d40c  xor     r14d, r14d
0x18000d40f  mov     eax, cs:dword_18001C010
0x18000d415  cmp     eax, 4
0x18000d418  jbe     short loc_18000D451
0x18000d41a  mov     edx, 200h
0x18000d41f  mov     rcx, r13
0x18000d422  call    _tlgKeywordOn
0x18000d427  test    al, al
0x18000d429  jz      short loc_18000D451
0x18000d42b  lea     rax, [rbp+arg_0]
0x18000d42f  mov     byte ptr [rbp+arg_0], sil
0x18000d433  mov     [rsp+30h+var_8], rax
0x18000d438  lea     rdx, byte_180016F13
0x18000d43f  lea     rax, [rbp+arg_8]
0x18000d443  mov     [rbp+arg_8], r14d
0x18000d447  mov     qword ptr [rsp+30h+var_10], rax
0x18000d44c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000d451  mov     cl, sil
0x18000d454  call    WpW32TimeSyncNow
0x18000d459  mov     ebx, eax
0x18000d45b  lea     ecx, [rax+7CEDFEFFh]
0x18000d461  cmp     ecx, 1
0x18000d464  jbe     short loc_18000D4CC
0x18000d466  cmp     eax, 83120104h
0x18000d46b  jnz     loc_18000D545
0x18000d471  mov     rcx, [rdi]
0x18000d474  cmp     byte ptr [rcx+8], 0
0x18000d478  jnz     loc_18000D545
0x18000d47e  mov     ecx, cs:dword_18001C010
0x18000d484  mov     sil, 1
0x18000d487  cmp     ecx, 3
0x18000d48a  jbe     loc_18000D538
0x18000d490  mov     edx, 200h
0x18000d495  mov     rcx, r13
0x18000d498  call    _tlgKeywordOn
0x18000d49d  test    al, al
0x18000d49f  jz      loc_18000D538
0x18000d4a5  lea     rax, [rbp+arg_0]
0x18000d4a9  mov     dword ptr [rbp+arg_0], 83120104h
0x18000d4b0  xor     r9d, r9d
0x18000d4b3  mov     qword ptr [rsp+30h+var_10], rax
0x18000d4b8  xor     r8d, r8d
0x18000d4bb  lea     rdx, word_180016FA6
0x18000d4c2  mov     rcx, r13
0x18000d4c5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d4ca  jmp     short loc_18000D538
0x18000d4cc  mov     eax, cs:dword_18001C010
0x18000d4d2  cmp     eax, 3
0x18000d4d5  jbe     short loc_18000D513
0x18000d4d7  mov     edx, 200h
0x18000d4dc  mov     rcx, r13
0x18000d4df  call    _tlgKeywordOn
0x18000d4e4  test    al, al
0x18000d4e6  jz      short loc_18000D513
0x18000d4e8  lea     rax, [rbp+arg_0]
0x18000d4ec  mov     dword ptr [rbp+arg_0], r15d
0x18000d4f0  mov     [rsp+30h+var_8], rax
0x18000d4f5  lea     rdx, byte_180017049
0x18000d4fc  lea     rax, [rbp+arg_8]
0x18000d500  mov     [rbp+arg_8], ebx
0x18000d503  xor     r8d, r8d
0x18000d506  mov     qword ptr [rsp+30h+var_10], rax
0x18000d50b  mov     rcx, r13
0x18000d50e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d513  mov     rcx, [rdi+10h]
0x18000d517  mov     edx, r15d
0x18000d51a  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x18000d51f  test    al, al
0x18000d521  jnz     short loc_18000D58E
0x18000d523  lea     eax, [r15+r15]
0x18000d527  mov     ecx, 1D4C0h
0x18000d52c  xor     sil, sil
0x18000d52f  mov     r15d, ecx
0x18000d532  cmp     eax, ecx
0x18000d534  cmovb   r15d, eax
0x18000d538  inc     r14d
0x18000d53b  cmp     r14d, 6
0x18000d53f  jb      loc_18000D40F
0x18000d545  mov     eax, cs:dword_18001C010
0x18000d54b  cmp     eax, 4
0x18000d54e  jbe     short loc_18000D582
0x18000d550  mov     edx, 200h
0x18000d555  mov     rcx, r13
0x18000d558  call    _tlgKeywordOn
0x18000d55d  test    al, al
0x18000d55f  jz      short loc_18000D582
0x18000d561  lea     rax, [rbp+arg_0]
0x18000d565  mov     dword ptr [rbp+arg_0], ebx
0x18000d568  xor     r9d, r9d
0x18000d56b  mov     qword ptr [rsp+30h+var_10], rax
0x18000d570  xor     r8d, r8d
0x18000d573  lea     rdx, word_180016FD2
0x18000d57a  mov     rcx, r13
0x18000d57d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d582  xor     ecx, ecx
0x18000d584  call    WpW32TimeStopService
0x18000d589  jmp     loc_18000D3EF
0x18000d58e  mov     eax, cs:dword_18001C010
0x18000d594  cmp     eax, 3
0x18000d597  jbe     short loc_18000D5BF
0x18000d599  mov     edx, 200h
0x18000d59e  mov     rcx, r13
0x18000d5a1  call    _tlgKeywordOn
0x18000d5a6  test    al, al
0x18000d5a8  jz      short loc_18000D5BF
0x18000d5aa  xor     r9d, r9d
0x18000d5ad  lea     rdx, word_180016F42
0x18000d5b4  xor     r8d, r8d
0x18000d5b7  mov     rcx, r13
0x18000d5ba  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000d5bf  xor     ecx, ecx
0x18000d5c1  call    WpW32TimeStopService
0x18000d5c6  mov     eax, 80004004h
0x18000d5cb  mov     rbx, [rsp+30h+arg_10]
0x18000d5d0  mov     rsi, [rsp+30h+arg_18]
0x18000d5d5  add     rsp, 30h
0x18000d5d9  pop     r15
0x18000d5db  pop     r14
0x18000d5dd  pop     r13
0x18000d5df  pop     rdi
0x18000d5e0  pop     rbp
0x18000d5e1  retn
```

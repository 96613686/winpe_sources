# CWorkflowSession::AllowRequestUI(uchar *)

- ea: `0x180019080`
- end: `0x18001927d`
- name: `?AllowRequestUI@CWorkflowSession@@UEAAJPEAE@Z`
- size: `509`
- prototype: `__int64 __fastcall(CWorkflowSession *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000183c`
- `0x180010aec`
- `0x180010b0c`
- `0x1800166a8`
- `0x180019080`
- `0x18001a7c0`
- `0x180021df4`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019126`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019126`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800190be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800190be`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800191e3`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800191e3`

## string_xrefs

- `0x18001909d`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x1800191bb`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x1800191f1`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`

## pseudocode

```c
__int64 __fastcall CWorkflowSession::AllowRequestUI(CWorkflowSession *this, bool *a2)
{
  unsigned int LastError; // ebx
  ULONGLONG v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int CallerOrSelfProcessHandle; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-40h]
  HANDLE hProcess; // [rsp+40h] [rbp-20h] BYREF
  ULONGLONG v19; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  bool v22; // [rsp+98h] [rbp+38h] BYREF
  WINBOOL pbDebuggerPresent; // [rsp+A0h] [rbp+40h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF

  if ( a2 )
  {
    *a2 = 1;
    v5 = GetTickCount64() - *((_QWORD *)this + 15);
    if ( v5 > 0x1388 )
    {
      if ( !IsDebuggerPresent() )
      {
        *a2 = 0;
        hProcess = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hProcess,
          0);
        CallerOrSelfProcessHandle = GetCallerOrSelfProcessHandle(0x400u, &hProcess);
        LastError = CallerOrSelfProcessHandle;
        if ( CallerOrSelfProcessHandle >= 0 )
        {
          pbDebuggerPresent = 0;
          if ( CheckRemoteDebuggerPresent(hProcess, &pbDebuggerPresent) )
          {
            *a2 = pbDebuggerPresent != 0;
            if ( (unsigned int)dword_180083038 > 5 )
            {
              v24 = *((_DWORD *)this + 82);
              v22 = *a2;
              v19 = *((_QWORD *)this + 15);
              v20[0] = v5;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
                v14,
                (__int64)word_180070312,
                v15,
                (__int64)v16,
                (__int64)&v19,
                (__int64)v20,
                (__int64)&v22,
                (__int64)&v24);
            }
            LastError = 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x30C,
                          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
                          v16);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x308,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
            (const char *)(unsigned int)CallerOrSelfProcessHandle,
            v17);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        return LastError;
      }
      if ( (unsigned int)dword_180083038 > 5 )
      {
        v24 = *((_DWORD *)this + 82);
        v22 = *a2;
        v19 = *((_QWORD *)this + 15);
        v20[0] = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)&unk_1800703A8,
          v10,
          v11,
          (__int64)&v19,
          (__int64)v20,
          (__int64)&v22,
          (__int64)&v24);
      }
    }
    else if ( (unsigned int)dword_180083038 > 5 )
    {
      v8 = *((unsigned int *)this + 82);
      v22 = *a2;
      v20[0] = *((_QWORD *)this + 15);
      v24 = v8;
      v19 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)byte_180070425,
        v6,
        v7,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v24);
    }
    return 0;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E2,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
    (const char *)0x80004003LL,
    v17);
  return LastError;
}

```

## disassembly

```asm
0x180019080  push    rbp
0x180019082  push    rbx
0x180019083  push    rsi
0x180019084  push    rdi
0x180019085  push    r14
0x180019087  mov     rbp, rsp
0x18001908a  sub     rsp, 60h
0x18001908e  mov     rdi, rdx
0x180019091  mov     r14, rcx
0x180019094  test    rdx, rdx
0x180019097  jnz     short loc_1800190BB
0x180019099  mov     rcx, [rbp+28h]; this
0x18001909d  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x1800190a4  mov     ebx, 80004003h
0x1800190a9  mov     edx, 2E2h; void *
0x1800190ae  mov     r9d, ebx; char *
0x1800190b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190b6  jmp     loc_180019270
0x1800190bb  mov     byte ptr [rdx], 1
0x1800190be  call    cs:__imp_GetTickCount64
0x1800190c4  mov     rsi, rax
0x1800190c7  sub     rsi, [r14+78h]
0x1800190cb  cmp     rsi, 1388h
0x1800190d2  ja      short loc_180019126
0x1800190d4  mov     ecx, cs:dword_180083038
0x1800190da  cmp     ecx, 5
0x1800190dd  jbe     loc_180019186
0x1800190e3  mov     al, [rdi]
0x1800190e5  lea     rdx, byte_180070425
0x1800190ec  mov     ecx, [r14+148h]
0x1800190f3  mov     [rbp+arg_8], al
0x1800190f6  mov     rax, [r14+78h]
0x1800190fa  mov     [rbp+var_10], rax
0x1800190fe  lea     rax, [rbp+arg_18]
0x180019102  mov     [rsp+60h+var_28], rax
0x180019107  lea     rax, [rbp+arg_8]
0x18001910b  mov     [rsp+60h+var_30], rax
0x180019110  lea     rax, [rbp+var_18]
0x180019114  mov     [rsp+60h+var_38], rax
0x180019119  lea     rax, [rbp+var_10]
0x18001911d  mov     [rbp+arg_18], ecx
0x180019120  mov     [rbp+var_18], rsi
0x180019124  jmp     short loc_18001917C
0x180019126  call    cs:__imp_IsDebuggerPresent
0x18001912c  test    eax, eax
0x18001912e  jz      short loc_18001918D
0x180019130  mov     eax, cs:dword_180083038
0x180019136  cmp     eax, 5
0x180019139  jbe     short loc_180019186
0x18001913b  mov     eax, [r14+148h]
0x180019142  lea     rdx, unk_1800703A8
0x180019149  mov     [rbp+arg_18], eax
0x18001914c  mov     al, [rdi]
0x18001914e  mov     [rbp+arg_8], al
0x180019151  mov     rax, [r14+78h]
0x180019155  mov     [rbp+var_18], rax
0x180019159  lea     rax, [rbp+arg_18]
0x18001915d  mov     [rsp+60h+var_28], rax
0x180019162  lea     rax, [rbp+arg_8]
0x180019166  mov     [rsp+60h+var_30], rax
0x18001916b  lea     rax, [rbp+var_10]
0x18001916f  mov     [rsp+60h+var_38], rax
0x180019174  lea     rax, [rbp+var_18]
0x180019178  mov     [rbp+var_10], rsi
0x18001917c  mov     [rsp+60h+var_40], rax
0x180019181  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180019186  xor     eax, eax
0x180019188  jmp     loc_180019272
0x18001918d  xor     edx, edx
0x18001918f  mov     byte ptr [rdi], 0
0x180019192  lea     rcx, [rbp+hProcess]
0x180019196  mov     [rbp+hProcess], 0
0x18001919e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800191a3  lea     rdx, [rbp+hProcess]; void **
0x1800191a7  mov     ecx, 400h; unsigned int
0x1800191ac  call    ?GetCallerOrSelfProcessHandle@@YAJKPEAPEAX@Z; GetCallerOrSelfProcessHandle(ulong,void * *)
0x1800191b1  mov     ebx, eax
0x1800191b3  test    eax, eax
0x1800191b5  jns     short loc_1800191D4
0x1800191b7  mov     rcx, [rbp+28h]; this
0x1800191bb  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x1800191c2  mov     r9d, eax; char *
0x1800191c5  mov     edx, 308h; void *
0x1800191ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800191cf  jmp     loc_180019267
0x1800191d4  mov     rcx, [rbp+hProcess]; hProcess
0x1800191d8  lea     rdx, [rbp+pbDebuggerPresent]; pbDebuggerPresent
0x1800191dc  mov     [rbp+pbDebuggerPresent], 0
0x1800191e3  call    cs:__imp_CheckRemoteDebuggerPresent
0x1800191e9  test    eax, eax
0x1800191eb  jnz     short loc_180019206
0x1800191ed  mov     rcx, [rbp+28h]; this
0x1800191f1  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x1800191f8  mov     edx, 30Ch; void *
0x1800191fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019202  mov     ebx, eax
0x180019204  jmp     short loc_180019267
0x180019206  cmp     [rbp+pbDebuggerPresent], 0
0x18001920a  setnz   al
0x18001920d  mov     [rdi], al
0x18001920f  mov     eax, cs:dword_180083038
0x180019215  cmp     eax, 5
0x180019218  jbe     short loc_180019265
0x18001921a  mov     eax, [r14+148h]
0x180019221  lea     rdx, word_180070312
0x180019228  mov     [rbp+arg_18], eax
0x18001922b  mov     al, [rdi]
0x18001922d  mov     [rbp+arg_8], al
0x180019230  mov     rax, [r14+78h]
0x180019234  mov     [rbp+var_18], rax
0x180019238  lea     rax, [rbp+arg_18]
0x18001923c  mov     [rsp+60h+var_28], rax
0x180019241  lea     rax, [rbp+arg_8]
0x180019245  mov     [rsp+60h+var_30], rax
0x18001924a  lea     rax, [rbp+var_10]
0x18001924e  mov     [rsp+60h+var_38], rax
0x180019253  lea     rax, [rbp+var_18]
0x180019257  mov     [rsp+60h+var_40], rax
0x18001925c  mov     [rbp+var_10], rsi
0x180019260  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180019265  xor     ebx, ebx
0x180019267  lea     rcx, [rbp+hProcess]
0x18001926b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019270  mov     eax, ebx
0x180019272  add     rsp, 60h
0x180019276  pop     r14
0x180019278  pop     rdi
0x180019279  pop     rsi
0x18001927a  pop     rbx
0x18001927b  pop     rbp
0x18001927c  retn
```

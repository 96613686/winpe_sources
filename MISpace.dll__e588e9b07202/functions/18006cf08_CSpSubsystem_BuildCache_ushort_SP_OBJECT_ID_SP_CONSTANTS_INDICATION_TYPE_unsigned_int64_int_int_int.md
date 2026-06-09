# CSpSubsystem::BuildCache(ushort,_SP_OBJECT_ID *,SP_CONSTANTS::INDICATION_TYPE,unsigned __int64,int,int,int)

- ea: `0x18006cf08`
- end: `0x18006d1a0`
- name: `?BuildCache@CSpSubsystem@@QEAA?AW4_MI_Result@@GPEAU_SP_OBJECT_ID@@W4INDICATION_TYPE@SP_CONSTANTS@@_KHHH@Z`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023550`
- `0x18007dc10`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180013938`
- `0x18006cf08`
- `0x180078854`
- `0x180078a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cfc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cfc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d085`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006cfb8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006cfb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006d144`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006cf83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006cf83`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006d077`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006d077`

## string_xrefs

- `0x18006cf28`: `CSpSubsystem::BuildCache`
- `0x18006d01b`: `CSpSubsystem::BuildCache`
- `0x18006d0ff`: `CSpSubsystem::BuildCache`
- `0x18006d14a`: `CSpSubsystem::BuildCache`

## pseudocode

```c
__int64 __fastcall CSpSubsystem::BuildCache(
        RTL_SRWLOCK *a1,
        unsigned __int16 a2,
        _DWORD *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned int a8)
{
  enum _MI_Result updated; // ebx
  int v13; // r12d
  int v14; // esi
  int v15; // ecx
  DWORD LastError; // ebx
  int v17; // r8d
  int v18; // r9d
  char *v19; // rdx
  const char *v21; // [rsp+40h] [rbp-10h] BYREF
  const char *v22; // [rsp+48h] [rbp-8h] BYREF
  int v23; // [rsp+80h] [rbp+30h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v23 = 633;
    v21 = "CSpSubsystem::BuildCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_180310A95,
      (_DWORD)a3,
      a4,
      (__int64)&v21,
      (__int64)&v23);
  }
  updated = MI_RESULT_OK;
  if ( *((_DWORD *)a1[1].Ptr + 8) == 2 )
  {
    v13 = 0;
    if ( a7 )
    {
      AcquireSRWLockExclusive(a1 + 4);
      v13 = 1;
    }
    if ( !a3 || ((*a3 - 5) & 0xFFFFFFF7) == 0 )
    {
      updated = (unsigned int)CSpSubsystem::_UpdateLeveledDiscoverCache((CSpSubsystem *)a1, a2, (int)a3, a4);
      if ( updated && (unsigned int)dword_180397B68 > 2 )
      {
        v23 = updated;
        v22 = "CSpSubsystem::BuildCache";
        LODWORD(v21) = 691;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)a1,
          (unsigned int)byte_180310C39,
          (_DWORD)a3,
          a4,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v23);
      }
      goto LABEL_35;
    }
    v14 = a6;
    if ( !a6 || SetThreadToken(0, a1[6].Ptr) )
    {
      CSpSubsystem::_UpdateRootedDiscoverCache(a1, a3, a4, a8, a5);
      if ( !v14 || RevertToSelf() )
      {
LABEL_35:
        if ( v13 )
          ReleaseSRWLockExclusive(a1 + 4);
        goto LABEL_37;
      }
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_180397B68 <= 3 )
            goto LABEL_20;
          v23 = 122;
          v19 = (char *)&word_18030EF26;
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_20;
          v23 = LastError;
          v19 = (char *)&word_18030FC3E;
        }
      }
      else
      {
        v15 = dword_180397B68;
        if ( (unsigned int)dword_180397B68 <= 4 )
          goto LABEL_20;
        v23 = 0;
        v19 = (char *)qword_180310218;
      }
      LODWORD(v21) = 679;
      goto LABEL_19;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError == 122 )
      {
        if ( (unsigned int)dword_180397B68 > 3 )
        {
          v23 = 122;
          v19 = byte_18030ECE9;
          goto LABEL_18;
        }
      }
      else if ( (unsigned int)dword_180397B68 > 2 )
      {
        v23 = LastError;
        v19 = byte_1803104DD;
        goto LABEL_18;
      }
    }
    else
    {
      v15 = dword_180397B68;
      if ( (unsigned int)dword_180397B68 > 4 )
      {
        v23 = 0;
        v19 = byte_18030FD4B;
LABEL_18:
        LODWORD(v21) = 664;
LABEL_19:
        v22 = "CSpSubsystem::BuildCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v15,
          (_DWORD)v19,
          v17,
          v18,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v23);
      }
    }
LABEL_20:
    updated = MI_FROM_WIN32(LastError);
    goto LABEL_35;
  }
LABEL_37:
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v23 = 702;
    v22 = "CSpSubsystem::BuildCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)qword_1803119B8,
      (_DWORD)a3,
      a4,
      (__int64)&v22,
      (__int64)&v23);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18006cf08  mov     r11, rsp
0x18006cf0b  mov     [r11+10h], rbx
0x18006cf0f  mov     [r11+18h], rsi
0x18006cf13  push    rbp
0x18006cf14  push    rdi
0x18006cf15  push    r12
0x18006cf17  push    r14
0x18006cf19  push    r15
0x18006cf1b  mov     rbp, rsp
0x18006cf1e  sub     rsp, 50h
0x18006cf22  mov     eax, cs:dword_180397B68
0x18006cf28  lea     r12, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006cf2f  mov     r15d, r9d
0x18006cf32  mov     r14, r8
0x18006cf35  movzx   esi, dx
0x18006cf38  mov     rdi, rcx
0x18006cf3b  cmp     eax, 5
0x18006cf3e  jbe     short loc_18006CF67
0x18006cf40  lea     rax, [rbp+arg_0]
0x18006cf44  mov     [rbp+arg_0], 279h
0x18006cf4b  mov     [r11-50h], rax
0x18006cf4f  lea     rdx, byte_180310A95
0x18006cf56  lea     rax, [rbp+var_10]
0x18006cf5a  mov     [rbp+var_10], r12
0x18006cf5e  mov     [r11-58h], rax
0x18006cf62  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006cf67  mov     rax, [rdi+8]
0x18006cf6b  xor     ebx, ebx
0x18006cf6d  cmp     dword ptr [rax+20h], 2
0x18006cf71  jnz     loc_18006D151
0x18006cf77  xor     r12d, r12d
0x18006cf7a  cmp     [rbp+arg_30], ebx
0x18006cf7d  jz      short loc_18006CF8D
0x18006cf7f  lea     rcx, [rdi+20h]; SRWLock
0x18006cf83  call    cs:__imp_AcquireSRWLockExclusive
0x18006cf89  lea     r12d, [rbx+1]
0x18006cf8d  test    r14, r14
0x18006cf90  jz      loc_18006D0E3
0x18006cf96  mov     eax, [r14]
0x18006cf99  sub     eax, 5
0x18006cf9c  test    eax, 0FFFFFFF7h
0x18006cfa1  jz      loc_18006D0E3
0x18006cfa7  mov     esi, [rbp+arg_28]
0x18006cfaa  test    esi, esi
0x18006cfac  jz      loc_18006D054
0x18006cfb2  mov     rdx, [rdi+30h]; Token
0x18006cfb6  xor     ecx, ecx; Thread
0x18006cfb8  call    cs:__imp_SetThreadToken
0x18006cfbe  test    eax, eax
0x18006cfc0  jnz     loc_18006D054
0x18006cfc6  call    cs:__imp_GetLastError
0x18006cfcc  mov     ebx, eax
0x18006cfce  test    eax, eax
0x18006cfd0  jnz     short loc_18006CFE9
0x18006cfd2  mov     ecx, cs:dword_180397B68
0x18006cfd8  cmp     ecx, 4
0x18006cfdb  jbe     short loc_18006D046
0x18006cfdd  mov     [rbp+arg_0], eax
0x18006cfe0  lea     rdx, byte_18030FD4B
0x18006cfe7  jmp     short loc_18006D014
0x18006cfe9  mov     eax, cs:dword_180397B68
0x18006cfef  cmp     ebx, 7Ah ; 'z'
0x18006cff2  jnz     short loc_18006D005
0x18006cff4  cmp     eax, 3
0x18006cff7  jbe     short loc_18006D046
0x18006cff9  mov     [rbp+arg_0], ebx
0x18006cffc  lea     rdx, byte_18030ECE9
0x18006d003  jmp     short loc_18006D014
0x18006d005  cmp     eax, 2
0x18006d008  jbe     short loc_18006D046
0x18006d00a  mov     [rbp+arg_0], ebx
0x18006d00d  lea     rdx, byte_1803104DD
0x18006d014  mov     dword ptr [rbp+var_10], 298h
0x18006d01b  lea     rax, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006d022  mov     [rbp+var_8], rax
0x18006d026  lea     rax, [rbp+arg_0]
0x18006d02a  mov     [rsp+50h+var_20], rax
0x18006d02f  lea     rax, [rbp+var_10]
0x18006d033  mov     [rsp+50h+var_28], rax
0x18006d038  lea     rax, [rbp+var_8]
0x18006d03c  mov     [rsp+50h+var_30], rax
0x18006d041  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006d046  mov     ecx, ebx; unsigned int
0x18006d048  call    ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
0x18006d04d  mov     ebx, eax
0x18006d04f  jmp     loc_18006D13B
0x18006d054  mov     rax, [rbp+arg_20]
0x18006d058  mov     r8d, r15d
0x18006d05b  mov     r9d, [rbp+arg_38]
0x18006d05f  mov     rdx, r14
0x18006d062  mov     rcx, rdi
0x18006d065  mov     [rsp+50h+var_30], rax
0x18006d06a  call    ?_UpdateRootedDiscoverCache@CSpSubsystem@@IEAAXPEAU_SP_OBJECT_ID@@W4INDICATION_TYPE@SP_CONSTANTS@@H_K@Z; CSpSubsystem::_UpdateRootedDiscoverCache(_SP_OBJECT_ID *,SP_CONSTANTS::INDICATION_TYPE,int,unsigned __int64)
0x18006d06f  test    esi, esi
0x18006d071  jz      loc_18006D13B
0x18006d077  call    cs:__imp_RevertToSelf
0x18006d07d  test    eax, eax
0x18006d07f  jnz     loc_18006D13B
0x18006d085  call    cs:__imp_GetLastError
0x18006d08b  mov     ebx, eax
0x18006d08d  test    eax, eax
0x18006d08f  jnz     short loc_18006D0A8
0x18006d091  mov     ecx, cs:dword_180397B68
0x18006d097  cmp     ecx, 4
0x18006d09a  jbe     short loc_18006D046
0x18006d09c  mov     [rbp+arg_0], eax
0x18006d09f  lea     rdx, qword_180310218
0x18006d0a6  jmp     short loc_18006D0D7
0x18006d0a8  mov     eax, cs:dword_180397B68
0x18006d0ae  cmp     ebx, 7Ah ; 'z'
0x18006d0b1  jnz     short loc_18006D0C4
0x18006d0b3  cmp     eax, 3
0x18006d0b6  jbe     short loc_18006D046
0x18006d0b8  mov     [rbp+arg_0], ebx
0x18006d0bb  lea     rdx, word_18030EF26
0x18006d0c2  jmp     short loc_18006D0D7
0x18006d0c4  cmp     eax, 2
0x18006d0c7  jbe     loc_18006D046
0x18006d0cd  mov     [rbp+arg_0], ebx
0x18006d0d0  lea     rdx, word_18030FC3E
0x18006d0d7  mov     dword ptr [rbp+var_10], 2A7h
0x18006d0de  jmp     loc_18006D01B
0x18006d0e3  movzx   edx, si; unsigned __int16
0x18006d0e6  mov     rcx, rdi; this
0x18006d0e9  call    ?_UpdateLeveledDiscoverCache@CSpSubsystem@@IEAA?AW4_MI_Result@@G@Z; CSpSubsystem::_UpdateLeveledDiscoverCache(ushort)
0x18006d0ee  mov     ebx, eax
0x18006d0f0  test    eax, eax
0x18006d0f2  jz      short loc_18006D13B
0x18006d0f4  mov     eax, cs:dword_180397B68
0x18006d0fa  cmp     eax, 2
0x18006d0fd  jbe     short loc_18006D13B
0x18006d0ff  lea     rax, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006d106  mov     [rbp+arg_0], ebx
0x18006d109  mov     [rbp+var_8], rax
0x18006d10d  lea     rdx, byte_180310C39
0x18006d114  lea     rax, [rbp+arg_0]
0x18006d118  mov     dword ptr [rbp+var_10], 2B3h
0x18006d11f  mov     [rsp+50h+var_20], rax
0x18006d124  lea     rax, [rbp+var_10]
0x18006d128  mov     [rsp+50h+var_28], rax
0x18006d12d  lea     rax, [rbp+var_8]
0x18006d131  mov     [rsp+50h+var_30], rax
0x18006d136  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006d13b  test    r12d, r12d
0x18006d13e  jz      short loc_18006D14A
0x18006d140  lea     rcx, [rdi+20h]; SRWLock
0x18006d144  call    cs:__imp_ReleaseSRWLockExclusive
0x18006d14a  lea     r12, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006d151  mov     eax, cs:dword_180397B68
0x18006d157  cmp     eax, 5
0x18006d15a  jbe     short loc_18006D185
0x18006d15c  lea     rax, [rbp+arg_0]
0x18006d160  mov     [rbp+arg_0], 2BEh
0x18006d167  mov     [rsp+50h+var_28], rax
0x18006d16c  lea     rdx, qword_1803119B8
0x18006d173  lea     rax, [rbp+var_8]
0x18006d177  mov     [rbp+var_8], r12
0x18006d17b  mov     [rsp+50h+var_30], rax
0x18006d180  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006d185  lea     r11, [rsp+50h+var_s0]
0x18006d18a  mov     eax, ebx
0x18006d18c  mov     rbx, [r11+38h]
0x18006d190  mov     rsi, [r11+40h]
0x18006d194  mov     rsp, r11
0x18006d197  pop     r15
0x18006d199  pop     r14
0x18006d19b  pop     r12
0x18006d19d  pop     rdi
0x18006d19e  pop     rbp
0x18006d19f  retn
```

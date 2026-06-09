# CSpWmiDataHandle::_UnRegisterIndications(void)

- ea: `0x18005b700`
- end: `0x18005b8b8`
- name: `?_UnRegisterIndications@CSpWmiDataHandle@@AEAAXXZ`
- size: `440`
- prototype: `void __fastcall(CSpWmiDataHandle *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800547a0`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x18005b700`
- `0x18005bde4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b78d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b78d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b7a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005b7a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b7c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b7e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b7c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b7e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b802`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b873`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b802`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b873`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b77f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b77f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b75c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b75c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b7f0`

## pseudocode

```c
void __fastcall CSpWmiDataHandle::_UnRegisterIndications(CSpWmiDataHandle *this, __int64 a2, int a3, int a4)
{
  BOOL v5; // edi
  int v6; // r8d
  int v7; // r9d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  MI_CancellationReason v10; // edx
  DWORD v11; // ecx
  int *v12; // rdx
  void *v13; // rcx
  int v14; // [rsp+70h] [rbp+30h] BYREF
  const char *v15; // [rsp+78h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+40h] BYREF
  const char *v17; // [rsp+88h] [rbp+48h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v14 = 1603;
    v15 = "CSpWmiDataHandle::_UnRegisterIndications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_18030750D,
      a3,
      a4,
      (__int64)&v15,
      (__int64)&v14);
  }
  v5 = 0;
  TokenHandle = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 24);
  if ( *((_DWORD *)this + 88) )
    v5 = *((_DWORD *)this + 89) == 0;
  *((_DWORD *)this + 89) = 1;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 24);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) || (LastError = GetLastError()) == 0 || LastError == 1008 )
    {
      if ( SetThreadToken(0, *((HANDLE *)this + 41)) )
      {
        MI_Operation_Cancel((MI_Operation *)((char *)this + 304), v10);
        SetThreadToken(0, TokenHandle);
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v11 = WaitForSingleObject(*((HANDLE *)this + 43), 0x7530u);
    if ( v11 )
    {
      if ( v11 == 122 )
      {
        if ( (unsigned int)dword_180397B68 <= 3 )
          goto LABEL_20;
        v14 = 122;
        v12 = (int *)&byte_180307FCF;
      }
      else
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_20;
        v14 = v11;
        v12 = &dword_1803094E4;
      }
      LODWORD(v15) = 1681;
      v17 = "CSpWmiDataHandle::_UnRegisterIndications";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (_DWORD)v12,
        v6,
        v7,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
LABEL_20:
  v13 = (void *)*((_QWORD *)this + 46);
  if ( v13 )
    WaitForSingleObject(v13, 0xFFFFFFFF);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v14 = 1692;
    v15 = "CSpWmiDataHandle::_UnRegisterIndications";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)byte_180306FFD,
      v6,
      v7,
      (__int64)&v15,
      (__int64)&v14);
  }
}

```

## disassembly

```asm
0x18005b700  push    rbp
0x18005b702  push    rbx
0x18005b703  push    rsi
0x18005b704  push    rdi
0x18005b705  push    r15
0x18005b707  mov     rbp, rsp
0x18005b70a  sub     rsp, 40h
0x18005b70e  mov     eax, cs:dword_180397B68
0x18005b714  lea     r15, aCspwmidatahand; "CSpWmiDataHandle::_UnRegisterIndication"...
0x18005b71b  mov     rbx, rcx
0x18005b71e  cmp     eax, 5
0x18005b721  jbe     short loc_18005B74C
0x18005b723  lea     rax, [rbp+arg_0]
0x18005b727  mov     [rbp+arg_0], 643h
0x18005b72e  mov     [rsp+40h+var_18], rax
0x18005b733  lea     rdx, byte_18030750D
0x18005b73a  lea     rax, [rbp+arg_8]
0x18005b73e  mov     [rbp+arg_8], r15
0x18005b742  mov     [rsp+40h+var_20], rax
0x18005b747  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005b74c  lea     rsi, [rbx+0C0h]
0x18005b753  xor     edi, edi
0x18005b755  mov     rcx, rsi; SRWLock
0x18005b758  mov     [rbp+TokenHandle], rdi
0x18005b75c  call    cs:__imp_AcquireSRWLockExclusive
0x18005b762  lea     eax, [rdi+1]
0x18005b765  cmp     [rbx+160h], edi
0x18005b76b  jz      short loc_18005B776
0x18005b76d  cmp     [rbx+164h], edi
0x18005b773  cmovz   edi, eax
0x18005b776  mov     rcx, rsi; SRWLock
0x18005b779  mov     [rbx+164h], eax
0x18005b77f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b785  test    edi, edi
0x18005b787  jz      loc_18005B864
0x18005b78d  call    cs:__imp_GetCurrentThread
0x18005b793  xor     r8d, r8d; OpenAsSelf
0x18005b796  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005b79a  mov     rcx, rax; ThreadHandle
0x18005b79d  lea     edx, [r8+0Ch]; DesiredAccess
0x18005b7a1  call    cs:__imp_OpenThreadToken
0x18005b7a7  test    eax, eax
0x18005b7a9  jnz     short loc_18005B7BC
0x18005b7ab  call    cs:__imp_GetLastError
0x18005b7b1  test    eax, eax
0x18005b7b3  jz      short loc_18005B7BC
0x18005b7b5  cmp     eax, 3F0h
0x18005b7ba  jnz     short loc_18005B7E7
0x18005b7bc  mov     rdx, [rbx+148h]; Token
0x18005b7c3  xor     ecx, ecx; Thread
0x18005b7c5  call    cs:__imp_SetThreadToken
0x18005b7cb  test    eax, eax
0x18005b7cd  jz      short loc_18005B7E7
0x18005b7cf  lea     rcx, [rbx+130h]; operation
0x18005b7d6  call    MI_Operation_Cancel
0x18005b7db  mov     rdx, [rbp+TokenHandle]; Token
0x18005b7df  xor     ecx, ecx; Thread
0x18005b7e1  call    cs:__imp_SetThreadToken
0x18005b7e7  mov     rcx, [rbp+TokenHandle]; hObject
0x18005b7eb  test    rcx, rcx
0x18005b7ee  jz      short loc_18005B7F6
0x18005b7f0  call    cs:__imp_CloseHandle
0x18005b7f6  mov     rcx, [rbx+158h]; hHandle
0x18005b7fd  mov     edx, 7530h; dwMilliseconds
0x18005b802  call    cs:__imp_WaitForSingleObject
0x18005b808  mov     ecx, eax
0x18005b80a  test    eax, eax
0x18005b80c  jz      short loc_18005B864
0x18005b80e  mov     eax, cs:dword_180397B68
0x18005b814  cmp     ecx, 7Ah ; 'z'
0x18005b817  jnz     short loc_18005B82A
0x18005b819  cmp     eax, 3
0x18005b81c  jbe     short loc_18005B864
0x18005b81e  mov     [rbp+arg_0], ecx
0x18005b821  lea     rdx, byte_180307FCF
0x18005b828  jmp     short loc_18005B839
0x18005b82a  cmp     eax, 2
0x18005b82d  jbe     short loc_18005B864
0x18005b82f  mov     [rbp+arg_0], ecx
0x18005b832  lea     rdx, dword_1803094E4
0x18005b839  lea     rax, [rbp+arg_0]
0x18005b83d  mov     dword ptr [rbp+arg_8], 691h
0x18005b844  mov     [rsp+40h+var_10], rax
0x18005b849  lea     rax, [rbp+arg_8]
0x18005b84d  mov     [rsp+40h+var_18], rax
0x18005b852  lea     rax, [rbp+arg_18]
0x18005b856  mov     [rsp+40h+var_20], rax
0x18005b85b  mov     [rbp+arg_18], r15
0x18005b85f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005b864  mov     rcx, [rbx+170h]; hHandle
0x18005b86b  test    rcx, rcx
0x18005b86e  jz      short loc_18005B879
0x18005b870  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005b873  call    cs:__imp_WaitForSingleObject
0x18005b879  mov     eax, cs:dword_180397B68
0x18005b87f  cmp     eax, 5
0x18005b882  jbe     short loc_18005B8AD
0x18005b884  lea     rax, [rbp+arg_0]
0x18005b888  mov     [rbp+arg_0], 69Ch
0x18005b88f  mov     [rsp+40h+var_18], rax
0x18005b894  lea     rdx, byte_180306FFD
0x18005b89b  lea     rax, [rbp+arg_8]
0x18005b89f  mov     [rbp+arg_8], r15
0x18005b8a3  mov     [rsp+40h+var_20], rax
0x18005b8a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005b8ad  add     rsp, 40h
0x18005b8b1  pop     r15
0x18005b8b3  pop     rdi
0x18005b8b4  pop     rsi
0x18005b8b5  pop     rbx
0x18005b8b6  pop     rbp
0x18005b8b7  retn
```

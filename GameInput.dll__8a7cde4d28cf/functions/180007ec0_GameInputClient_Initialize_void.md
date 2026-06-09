# GameInputClient::Initialize(void)

- ea: `0x180007ec0`
- end: `0x18000841e`
- name: `?Initialize@GameInputClient@@AEAAJXZ`
- size: `1374`
- prototype: `int(GameInputClient *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000739c`

## callees

- `0x180001304`
- `0x180007ec0`
- `0x18000b700`
- `0x180026848`
- `0x18002be20`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x180007f18`
- `ntdll!NtUpdateWnfStateData` at `0x180007f18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800082e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800082e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007f32`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007f32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000818a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000818a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082fe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000808b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000817a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000808b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000817a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083ef`

## pseudocode

```c
__int64 __fastcall GameInputClient::Initialize(GameInputClient *this)
{
  char *v1; // rdi
  HANDLE EventW; // rbx
  HANDLE v3; // rax
  signed int LastError; // ebx
  int v5; // r8d
  int v6; // r9d
  bool v8; // bl
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  char *v15; // rdx
  _QWORD *v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 v19; // rcx
  __int64 (__fastcall *v20)(__int64, __int64, void (__fastcall *)(struct ISIPCEndpoint *, int, _QWORD *, void **, GameInputClient *), void *, char *, char *, char *); // r12
  __int64 v21; // rax
  void (*v22)(void *, bool); // rdx
  DWORD v23; // eax
  int v24; // r8d
  int v25; // r9d
  int v26; // [rsp+60h] [rbp-19h] BYREF
  int v27; // [rsp+64h] [rbp-15h] BYREF
  PSID hMem; // [rsp+68h] [rbp-11h] BYREF
  const char *v29; // [rsp+70h] [rbp-9h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp-1h] BYREF

  v1 = (char *)GameInputClient::s_singleton;
  if ( !byte_180069913 )
    NtUpdateWnfStateData(&WNF_INPT_GAMEINPUT_CLIENT_ACTIVITY, 0, 0, 0, 0, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (HANDLE)*((_QWORD *)v1 + 24);
  if ( EventW == v3 )
  {
    EventW = (HANDLE)*((_QWORD *)v1 + 24);
  }
  else
  {
    if ( v3 )
      CloseHandle(*((HANDLE *)v1 + 24));
    *((_QWORD *)v1 + 24) = EventW;
  }
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v26 = LastError;
      v29 = "onecore\\xbox\\gameinput\\client\\gameinputclient.cpp";
      v27 = 1387;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&unk_1800594B8,
        v5,
        v6,
        (__int64)&v29,
        (__int64)&v27,
        (__int64)&v26);
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)LastError;
  }
  v8 = 0;
  if ( byte_180069914 && qword_1800696F8 )
    v8 = (unsigned int)qword_1800696F8(262147) != 0;
  hMem = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( byte_180069913 )
  {
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 3u, 0x5Au, 0, NtCurrentPeb()->SessionId, 0, 0, 0, 0, 0, &hMem) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v14 = qword_180069018;
        if ( (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
        {
          v26 = 1429;
          v15 = byte_180059C6B;
LABEL_27:
          v29 = "onecore\\xbox\\gameinput\\client\\gameinputclient.cpp";
          v27 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v14,
            (_DWORD)v15,
            v12,
            v13,
            (__int64)&v29,
            (__int64)&v26,
            (__int64)&v27);
          goto LABEL_28;
        }
      }
      goto LABEL_28;
    }
  }
  else if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v14 = qword_180069018;
      if ( (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
      {
        v26 = 1444;
        v15 = byte_180059BDB;
        goto LABEL_27;
      }
    }
LABEL_28:
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147418113;
    }
LABEL_32:
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)LastError;
  }
  v16 = v1 + 176;
  v17 = *((_QWORD *)v1 + 22);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *v16 = 0;
  }
  LOBYTE(v11) = v8;
  LastError = SipcClient::Create(v17, v9, v10, v11, hMem, v1 + 176);
  if ( LastError < 0 )
    goto LABEL_32;
  v18 = *v16;
  v19 = *((_QWORD *)v1 + 23);
  v20 = *(__int64 (__fastcall **)(__int64, __int64, void (__fastcall *)(struct ISIPCEndpoint *, int, _QWORD *, void **, GameInputClient *), void *, char *, char *, char *))(*(_QWORD *)*v16 + 24LL);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)v1 + 23) = 0;
  }
  LastError = v20(
                v18,
                5000000,
                GameInputClient::OnSipcBufferStatus,
                &GameInputClient::OnSipcEndpointStatus,
                v1,
                v1 + 200,
                v1 + 184);
  if ( LastError < 0 )
    goto LABEL_32;
  v21 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 40LL))(*v16);
  *((_QWORD *)v1 + 31) = v1;
  *((_QWORD *)v1 + 30) = GameInputClient::OnDispatchRequest;
  *((_QWORD *)v1 + 32) = v21;
  _mm_mfence();
  GameInputDispatcher::s_dispatchThreadId = 0;
  _mm_mfence();
  LastError = GameInputDispatcher::StartThread((GameInputDispatcher *)(v1 + 208));
  if ( LastError < 0 )
    goto LABEL_32;
  if ( *((_DWORD *)v1 + 50) && (v23 = WaitForSingleObject(*((HANDLE *)v1 + 24), 0x7D0u)) != 0 )
  {
    if ( v23 != 258 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v14 = qword_180069018;
        if ( (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
        {
          v26 = 1476;
          v15 = (char *)&word_1800593FE;
          goto LABEL_27;
        }
      }
      goto LABEL_28;
    }
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v27 = 1460;
      v29 = "onecore\\xbox\\gameinput\\client\\gameinputclient.cpp";
      v26 = 1475;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&word_180059B5E,
        v24,
        v25,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v27);
    }
    if ( hMem )
      LocalFree(hMem);
    return 2147943860LL;
  }
  else
  {
    PixLogger::Initialize((PixLogger *)(v1 + 288), v22, v1);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x180007ec0  push    rbp
0x180007ec2  push    rbx
0x180007ec3  push    rsi
0x180007ec4  push    rdi
0x180007ec5  push    r12
0x180007ec7  push    r13
0x180007ec9  push    r14
0x180007ecb  push    r15
0x180007ecd  lea     rbp, [rsp-1Fh]
0x180007ed2  sub     rsp, 98h
0x180007ed9  mov     rax, cs:__security_cookie
0x180007ee0  xor     rax, rsp
0x180007ee3  mov     [rbp+57h+var_50], rax
0x180007ee7  mov     rdi, cs:?s_singleton@GameInputClient@@0PEAV1@EA; GameInputClient * GameInputClient::s_singleton
0x180007eee  xor     r13d, r13d
0x180007ef1  cmp     cs:byte_180069913, r13b
0x180007ef8  jnz     short loc_180007F24
0x180007efa  mov     [rsp+0D0h+nSubAuthority4], r13d
0x180007eff  lea     rcx, WNF_INPT_GAMEINPUT_CLIENT_ACTIVITY
0x180007f06  mov     [rsp+0D0h+nSubAuthority3], r13d
0x180007f0b  xor     r9d, r9d
0x180007f0e  xor     r8d, r8d
0x180007f11  mov     qword ptr [rsp+0D0h+nSubAuthority2], r13
0x180007f16  xor     edx, edx
0x180007f18  call    cs:__imp_NtUpdateWnfStateData
0x180007f1f  nop     dword ptr [rax+rax+00h]
0x180007f24  xor     r9d, r9d; lpName
0x180007f27  xor     r8d, r8d; bInitialState
0x180007f2a  xor     ecx, ecx; lpEventAttributes
0x180007f2c  lea     esi, [r9+1]
0x180007f30  mov     edx, esi; bManualReset
0x180007f32  call    cs:__imp_CreateEventW
0x180007f39  nop     dword ptr [rax+rax+00h]
0x180007f3e  mov     rbx, rax
0x180007f41  mov     rax, [rdi+0C0h]
0x180007f48  cmp     rbx, rax
0x180007f4b  jz      short loc_180007F6A
0x180007f4d  test    rax, rax
0x180007f50  jz      short loc_180007F61
0x180007f52  mov     rcx, rax; hObject
0x180007f55  call    cs:__imp_CloseHandle
0x180007f5c  nop     dword ptr [rax+rax+00h]
0x180007f61  mov     [rdi+0C0h], rbx
0x180007f68  jmp     short loc_180007F6D
0x180007f6a  mov     rbx, rax
0x180007f6d  test    rbx, rbx
0x180007f70  jnz     loc_180008006
0x180007f76  call    cs:__imp_GetLastError
0x180007f7d  nop     dword ptr [rax+rax+00h]
0x180007f82  mov     ebx, eax
0x180007f84  mov     eax, cs:dword_180069000
0x180007f8a  cmp     eax, 2
0x180007f8d  jbe     short loc_180007FE9
0x180007f8f  mov     rcx, cs:qword_180069018
0x180007f96  mov     rax, cs:qword_180069010
0x180007f9d  test    sil, al
0x180007fa0  jz      short loc_180007FE9
0x180007fa2  mov     rax, rcx
0x180007fa5  and     rax, rsi
0x180007fa8  cmp     rax, rcx
0x180007fab  jnz     short loc_180007FE9
0x180007fad  lea     rax, aOnecoreXboxGam_46; "onecore\\xbox\\gameinput\\client\\gamei"...
0x180007fb4  mov     [rbp+57h+var_70], ebx
0x180007fb7  mov     [rbp+57h+var_60], rax
0x180007fbb  lea     rdx, unk_1800594B8
0x180007fc2  lea     rax, [rbp+57h+var_70]
0x180007fc6  mov     [rbp+57h+var_6C], 56Bh
0x180007fcd  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180007fd2  lea     rax, [rbp+57h+var_6C]
0x180007fd6  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180007fdb  lea     rax, [rbp+57h+var_60]
0x180007fdf  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x180007fe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007fe9  test    ebx, ebx
0x180007feb  jnz     short loc_180007FF4
0x180007fed  mov     ebx, 8000FFFFh
0x180007ff2  jmp     short loc_180007FFF
0x180007ff4  jle     short loc_180007FFF
0x180007ff6  movzx   ebx, bx
0x180007ff9  or      ebx, 80070000h
0x180007fff  mov     eax, ebx
0x180008001  jmp     loc_1800083FD
0x180008006  cmp     cs:byte_180069914, r13b
0x18000800d  movzx   ebx, r13b
0x180008011  jz      short loc_18000802E
0x180008013  mov     rax, cs:qword_1800696F8
0x18000801a  test    rax, rax
0x18000801d  jz      short loc_18000802E
0x18000801f  mov     ecx, 40003h
0x180008024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008029  test    eax, eax
0x18000802b  cmovnz  ebx, esi
0x18000802e  xor     r9d, r9d; nSubAuthority1
0x180008031  mov     [rbp+57h+hMem], r13
0x180008035  cmp     cs:byte_180069913, r13b
0x18000803c  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180008040  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180008046  jz      loc_180008146
0x18000804c  mov     rax, gs:60h
0x180008055  lea     rcx, [rbp+57h+hMem]
0x180008059  mov     [rsp+0D0h+pSid], rcx; pSid
0x18000805e  lea     r8d, [r9+5Ah]; nSubAuthority0
0x180008062  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x180008067  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000806b  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x180008070  mov     dl, 3; nSubAuthorityCount
0x180008072  mov     eax, [rax+2C0h]
0x180008078  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x18000807d  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180008082  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180008087  mov     [rsp+0D0h+nSubAuthority2], eax; nSubAuthority2
0x18000808b  call    cs:__imp_AllocateAndInitializeSid
0x180008092  nop     dword ptr [rax+rax+00h]
0x180008097  test    eax, eax
0x180008099  jnz     loc_1800081E0
0x18000809f  call    cs:__imp_GetLastError
0x1800080a6  nop     dword ptr [rax+rax+00h]
0x1800080ab  mov     ebx, eax
0x1800080ad  mov     eax, cs:dword_180069000
0x1800080b3  cmp     eax, 2
0x1800080b6  jbe     short loc_180008112
0x1800080b8  mov     rcx, cs:qword_180069018
0x1800080bf  mov     rax, cs:qword_180069010
0x1800080c6  test    sil, al
0x1800080c9  jz      short loc_180008112
0x1800080cb  mov     rax, rcx
0x1800080ce  and     rax, rsi
0x1800080d1  cmp     rax, rcx
0x1800080d4  jnz     short loc_180008112
0x1800080d6  mov     [rbp+57h+var_70], 595h
0x1800080dd  lea     rdx, byte_180059C6B
0x1800080e4  lea     rax, aOnecoreXboxGam_46; "onecore\\xbox\\gameinput\\client\\gamei"...
0x1800080eb  mov     [rbp+57h+var_60], rax
0x1800080ef  lea     rax, [rbp+57h+var_6C]
0x1800080f3  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x1800080f8  lea     rax, [rbp+57h+var_70]
0x1800080fc  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180008101  lea     rax, [rbp+57h+var_60]
0x180008105  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x18000810a  mov     [rbp+57h+var_6C], ebx
0x18000810d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008112  test    ebx, ebx
0x180008114  jnz     short loc_18000811D
0x180008116  mov     ebx, 8000FFFFh
0x18000811b  jmp     short loc_180008128
0x18000811d  jle     short loc_180008128
0x18000811f  movzx   ebx, bx
0x180008122  or      ebx, 80070000h
0x180008128  mov     rcx, [rbp+57h+hMem]; hMem
0x18000812c  test    rcx, rcx
0x18000812f  jz      loc_180007FFF
0x180008135  call    cs:__imp_LocalFree
0x18000813c  nop     dword ptr [rax+rax+00h]
0x180008141  jmp     loc_180007FFF
0x180008146  lea     rax, [rbp+57h+hMem]
0x18000814a  mov     r8d, 12h; nSubAuthority0
0x180008150  mov     [rsp+0D0h+pSid], rax; pSid
0x180008155  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180008159  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x18000815e  mov     dl, sil; nSubAuthorityCount
0x180008161  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x180008166  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x18000816b  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180008170  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180008175  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x18000817a  call    cs:__imp_AllocateAndInitializeSid
0x180008181  nop     dword ptr [rax+rax+00h]
0x180008186  test    eax, eax
0x180008188  jnz     short loc_1800081E0
0x18000818a  call    cs:__imp_GetLastError
0x180008191  nop     dword ptr [rax+rax+00h]
0x180008196  mov     ebx, eax
0x180008198  mov     eax, cs:dword_180069000
0x18000819e  cmp     eax, 2
0x1800081a1  jbe     loc_180008112
0x1800081a7  mov     rcx, cs:qword_180069018
0x1800081ae  mov     rax, cs:qword_180069010
0x1800081b5  test    sil, al
0x1800081b8  jz      loc_180008112
0x1800081be  mov     rax, rcx
0x1800081c1  and     rax, rsi
0x1800081c4  cmp     rax, rcx
0x1800081c7  jnz     loc_180008112
0x1800081cd  mov     [rbp+57h+var_70], 5A4h
0x1800081d4  lea     rdx, byte_180059BDB
0x1800081db  jmp     loc_1800080E4
0x1800081e0  lea     rsi, [rdi+0B0h]
0x1800081e7  mov     rcx, [rsi]
0x1800081ea  test    rcx, rcx
0x1800081ed  jz      short loc_1800081FE
0x1800081ef  mov     rax, [rcx]
0x1800081f2  mov     rax, [rax+10h]
0x1800081f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081fb  mov     [rsi], r13
0x1800081fe  mov     rax, [rbp+57h+hMem]
0x180008202  mov     r9b, bl
0x180008205  mov     qword ptr [rsp+0D0h+nSubAuthority3], rsi
0x18000820a  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x18000820f  call    ?Create@SipcClient@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@EEPEAXPEAPEAUISIPCClient@@@Z; SipcClient::Create(_GUID const &,SIPC_SERVICE_BOUNDARY,uchar,uchar,void *,ISIPCClient * *)
0x180008214  mov     ebx, eax
0x180008216  test    eax, eax
0x180008218  js      loc_180008128
0x18000821e  mov     r14, [rsi]
0x180008221  lea     rbx, [rdi+0B8h]
0x180008228  mov     rcx, [rbx]
0x18000822b  mov     rax, [r14]
0x18000822e  mov     r12, [rax+18h]
0x180008232  test    rcx, rcx
0x180008235  jz      short loc_180008246
0x180008237  mov     rax, [rcx]
0x18000823a  mov     rax, [rax+10h]
0x18000823e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008243  mov     [rbx], r13
0x180008246  mov     qword ptr [rsp+0D0h+nSubAuthority4], rbx
0x18000824b  lea     r15, [rdi+0C8h]
0x180008252  mov     qword ptr [rsp+0D0h+nSubAuthority3], r15
0x180008257  lea     r9, ?OnSipcEndpointStatus@GameInputClient@@CAXPEAUISIPCEndpoint@@W4SIPC_ENDPOINT_STATUS@@PEAX@Z; GameInputClient::OnSipcEndpointStatus(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *)
0x18000825e  lea     r8, ?OnSipcBufferStatus@GameInputClient@@CAXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@2PEAX@Z; GameInputClient::OnSipcBufferStatus(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *)
0x180008265  mov     qword ptr [rsp+0D0h+nSubAuthority2], rdi
0x18000826a  mov     edx, 4C4B40h
0x18000826f  mov     rcx, r14
0x180008272  mov     rax, r12
0x180008275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827a  mov     ebx, eax
0x18000827c  test    eax, eax
0x18000827e  js      loc_180008128
0x180008284  mov     rcx, [rsi]
0x180008287  lea     rbx, [rdi+0D0h]
0x18000828e  mov     rax, [rcx]
0x180008291  mov     rax, [rax+28h]
0x180008295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829a  mov     [rbx+28h], rdi
0x18000829e  lea     rcx, ?OnDispatchRequest@GameInputClient@@CA_N_KPEAX@Z; GameInputClient::OnDispatchRequest(unsigned __int64,void *)
0x1800082a5  mov     [rbx+20h], rcx
0x1800082a9  nop
0x1800082aa  mov     [rbx+30h], rax
0x1800082ae  mfence
0x1800082b1  nop
0x1800082b2  mov     cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A, r13d; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x1800082b9  mfence
0x1800082bc  mov     rcx, rbx; this
0x1800082bf  call    ?StartThread@GameInputDispatcher@@AEAAJXZ; GameInputDispatcher::StartThread(void)
0x1800082c4  mov     ebx, eax
0x1800082c6  test    eax, eax
0x1800082c8  js      loc_180008128
0x1800082ce  cmp     [r15], r13d
0x1800082d1  jz      loc_1800083D7
0x1800082d7  mov     rcx, [rdi+0C0h]; hHandle
0x1800082de  mov     edx, 7D0h; dwMilliseconds
0x1800082e3  call    cs:__imp_WaitForSingleObject
0x1800082ea  nop     dword ptr [rax+rax+00h]
0x1800082ef  test    eax, eax
0x1800082f1  jz      loc_1800083D7
0x1800082f7  cmp     eax, 102h
0x1800082fc  jz      short loc_180008353
0x1800082fe  call    cs:__imp_GetLastError
0x180008305  nop     dword ptr [rax+rax+00h]
0x18000830a  mov     ebx, eax
0x18000830c  mov     eax, cs:dword_180069000
0x180008312  cmp     eax, 2
0x180008315  jbe     loc_180008112
0x18000831b  mov     rcx, cs:qword_180069018
0x180008322  mov     rax, cs:qword_180069010
0x180008329  test    al, 1
0x18000832b  jz      loc_180008112
0x180008331  mov     rax, rcx
0x180008334  and     eax, 1
0x180008337  cmp     rax, rcx
0x18000833a  jnz     loc_180008112
0x180008340  mov     [rbp+57h+var_70], 5C4h
0x180008347  lea     rdx, word_1800593FE
0x18000834e  jmp     loc_1800080E4
0x180008353  mov     eax, cs:dword_180069000
0x180008359  cmp     eax, 2
0x18000835c  jbe     short loc_1800083BB
0x18000835e  mov     rcx, cs:qword_180069018
0x180008365  mov     rax, cs:qword_180069010
0x18000836c  test    al, 1
0x18000836e  jz      short loc_1800083BB
0x180008370  mov     rax, rcx
0x180008373  and     eax, 1
0x180008376  cmp     rax, rcx
0x180008379  jnz     short loc_1800083BB
0x18000837b  lea     rax, aOnecoreXboxGam_46; "onecore\\xbox\\gameinput\\client\\gamei"...
0x180008382  mov     [rbp+57h+var_6C], 5B4h
0x180008389  mov     [rbp+57h+var_60], rax
0x18000838d  lea     rdx, word_180059B5E
0x180008394  lea     rax, [rbp+57h+var_6C]
0x180008398  mov     [rbp+57h+var_70], 5C3h
0x18000839f  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x1800083a4  lea     rax, [rbp+57h+var_70]
0x1800083a8  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x1800083ad  lea     rax, [rbp+57h+var_60]
0x1800083b1  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x1800083b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800083bb  mov     rcx, [rbp+57h+hMem]; hMem
0x1800083bf  test    rcx, rcx
0x1800083c2  jz      short loc_1800083D0
0x1800083c4  call    cs:__imp_LocalFree
0x1800083cb  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

# WSManHttpListenerRequest::GetData(void)

- ea: `0x180056878`
- end: `0x1800572da`
- name: `?GetData@WSManHttpListenerRequest@@IEAAXXZ`
- size: `2658`
- prototype: `void __fastcall(WSManHttpListenerRequest *__hidden this)`
- caller_count: `5`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054c30`
- `0x18008a000`
- `0x18008a930`
- `0x18016dc20`
- `0x18016e190`

## callees

- `0x180005d10`
- `0x1800224f0`
- `0x18002dd20`
- `0x18004e7e4`
- `0x180056878`
- `0x180075e00`
- `0x180077514`
- `0x180089dd0`
- `0x180089e68`
- `0x18008a930`
- `0x18008d16c`
- `0x18008e040`
- `0x1800b8294`
- `0x1800c78c0`
- `0x1800da074`
- `0x1800e43f4`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x18011a6d4`
- `0x18011ae5c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800568eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800568eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800568f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800568f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056a28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056a28`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800571d3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800571d3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800570ca`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800570ca`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180057173`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180057173`

## string_xrefs

- `0x1800569ee`: `Failed to retrieve server configuration settings`
- `0x1800569a7`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180057066`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005711a`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
void __fastcall WSManHttpListenerRequest::GetData(WSManHttpListenerRequest *this)
{
  DWORD v2; // ecx
  _BYTE *v3; // r13
  char *v4; // r15
  unsigned int *v5; // rbx
  unsigned int *v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdi
  unsigned int v9; // eax
  int v10; // ecx
  PVOID *v11; // rcx
  unsigned int v12; // r14d
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // r8d
  __int64 v17; // rdx
  struct _SecHandle *v18; // r10
  const unsigned __int16 *v19; // r8
  unsigned int v20; // edx
  unsigned int v21; // ebx
  __int64 v22; // rdx
  unsigned int v23; // r8d
  unsigned int v24; // eax
  unsigned int TotalEncryptedSizeInternalSsl; // eax
  __int64 v26; // rax
  const CHAR *v27; // r15
  unsigned int v28; // r14d
  Spinlock *v29; // r12
  void *v30; // r10
  ULONG v31; // ebx
  unsigned __int64 v32; // rcx
  __int64 v33; // rcx
  int EntityBufferLength; // [rsp+20h] [rbp-60h]
  void **v35; // [rsp+40h] [rbp-40h] BYREF
  signed __int32 v36[3]; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-2Ch]
  char v38; // [rsp+58h] [rbp-28h]
  const wchar_t *v39; // [rsp+60h] [rbp-20h]
  const wchar_t *v40; // [rsp+68h] [rbp-18h]
  const wchar_t *v41; // [rsp+70h] [rbp-10h]
  const wchar_t *v42; // [rsp+78h] [rbp-8h]
  unsigned int v43; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int *v44; // [rsp+C8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  CWSManCriticalSection::Acquire((WSManHttpListenerRequest *)((char *)this + 5328));
  *((_DWORD *)this + 71) = 2;
  v2 = *((_DWORD *)this + 1332);
  if ( v2 )
    SetLastError(v2);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5336));
  v3 = (char *)this + 312;
  v4 = (char *)this + 176;
  if ( *((_BYTE *)this + 312) && *(_QWORD *)v4 )
  {
    v5 = (unsigned int *)((char *)this + 192);
LABEL_79:
    if ( *(_QWORD *)v4 )
      goto LABEL_85;
    *((_QWORD *)this + 23) = 0;
    if ( *v3 )
      *v5 = *((_DWORD *)this + 1324);
    if ( !PacketPool::GetPacket((PacketPool *)(*((_QWORD *)this + 10) + 592LL), *v5, (struct Packet **)this + 22) )
    {
LABEL_85:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        EntityBufferLength = *((_DWORD *)this + 46);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      }
      if ( *((_QWORD *)this + 23) > (unsigned __int64)*v5 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x19CFu, L"6607", 0x54Fu, 0);
        WSManHttpListenerRequest::SendHttpError(
          this,
          0x1F7u,
          1,
          0,
          0,
          0xDu,
          L"There was an error in the packet length calculation",
          &Class);
      }
      v26 = *(_QWORD *)v4;
      v27 = *(const CHAR **)(*(_QWORD *)v4 + 40LL);
      if ( v27 )
      {
        v28 = *(_DWORD *)(v26 + 48);
      }
      else
      {
        v28 = 0;
        v27 = Buf1;
      }
      StartThreadpoolIo(*((PTP_IO *)this + 13));
      Spinlock::SharedAcquire(*((Spinlock **)this + 11));
      v29 = (Spinlock *)*((_QWORD *)this + 11);
      v30 = (void *)**((_QWORD **)this + 12);
      if ( v30 )
      {
        v32 = *((_QWORD *)this + 23);
        if ( v32 >= v28 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x19E3u,
            L"6627",
            0x54Fu,
            0);
          v32 = *((_QWORD *)this + 23);
          v30 = (void *)**((_QWORD **)this + 12);
        }
        v31 = HttpReceiveRequestEntityBody(
                v30,
                *(_QWORD *)(*((_QWORD *)this + 19) + 16LL),
                0,
                (PVOID)&v27[v32],
                v28 - *((_DWORD *)this + 46),
                0,
                (LPOVERLAPPED)(((unsigned __int64)this + 40) & -(__int64)(this != 0)));
      }
      else
      {
        v31 = 1115;
      }
      Spinlock::Release(v29);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 342, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this, v31);
      if ( v31 != 997 && v31 )
      {
        CancelThreadpoolIo(*((PTP_IO *)this + 13));
        if ( *v3 && v31 == 38 )
        {
          WSManHttpListenerRequest::GetDataComplete(this, 38, 0);
        }
        else if ( v31 == 1229 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
          v33 = *((_QWORD *)this + 1);
          if ( v33 )
          {
            (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int))(*(_QWORD *)v33 + 16LL))(
              v33,
              0,
              1229,
              0,
              EntityBufferLength);
            *((_QWORD *)this + 1) = 0;
          }
          WSManHttpListenerRequest::Finished(this, 0, 0);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v31);
          WSManHttpListenerRequest::SendHttpError(
            this,
            0x1F7u,
            1,
            0,
            0,
            v31,
            L"Failed to retrieve the request body",
            &Class);
        }
      }
    }
    else
    {
      WSManHttpListenerRequest::SendHttpError(
        this,
        0x1F4u,
        1,
        0,
        0,
        0xEu,
        L"Not enough memory to carry out the request",
        &Class);
    }
    return;
  }
  v36[0] = 0;
  v35 = &CErrorContext::`vftable';
  v36[2] = 0;
  v37 = -1;
  v39 = &Class;
  v40 = &Class;
  v41 = &Class;
  v42 = &Class;
  v38 = 1;
  _InterlockedIncrement(v36);
  v6 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, void ***, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL)
                                                                           + 112LL))(
                         *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
                         &v35,
                         *((_QWORD *)this + 55));
  v44 = v6;
  if ( !v6 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x195Cu, L"6492", 0x54Fu, 0);
    v7 = v37;
    if ( v37 == -1 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\CErrorContext.h", 0x2Du, L"45", 0x54Fu, 0);
      v7 = v37;
    }
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x1F4u,
      1,
      0,
      0,
      v7,
      L"Failed to retrieve server configuration settings",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
    return;
  }
  v8 = *((_QWORD *)this + 574);
  if ( (GetTickCount64() - v8) / 0x3E8 > v6[24] )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 333, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x1F4u,
      1,
      0,
      0,
      0x5B4u,
      L"Request took too long to retrieve so rejecting it",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
    return;
  }
  if ( *(_QWORD *)v4 )
    goto LABEL_58;
  if ( !WSManHttpListenerRequest::IsChunkedRequest(this, (bool *)this + 312) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x1F4u,
      1,
      0,
      0,
      0xDu,
      L"Failed to determine if the packet is in a chunked format",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
    return;
  }
  if ( !*v3 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 392, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v12 = 0;
    v43 = 0;
    v13 = *((_QWORD *)this + 19);
    v14 = *(unsigned __int16 *)(v13 + 328);
    if ( (_WORD)v14 )
    {
      if ( v14 > *(_DWORD *)(*((_QWORD *)this + 10) + 928LL) )
        goto LABEL_45;
      if ( !(unsigned int)StringToDword(*(const char **)(v13 + 336), &v43) )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_48:
          WSManHttpListenerRequest::SendHttpError(
            this,
            0x19Bu,
            1,
            0,
            0,
            0xDu,
            L"Request has invalid or missing content length header",
            &Class);
          AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
          return;
        }
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 393, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_45:
        if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200) != 0 )
          WPP_SF_(v11[2], 338, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
        goto LABEL_48;
      }
      v12 = v43;
    }
    else
    {
      if ( v11 == &WPP_GLOBAL_Control || (*((_DWORD *)v11 + 7) & 0x400) == 0 )
      {
LABEL_54:
        if ( v12 )
        {
          *((_DWORD *)this + 48) = v12;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v12);
          goto LABEL_58;
        }
        goto LABEL_45;
      }
      WPP_SF_(v11[2], 394, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_54;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 335, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  v9 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 48LL))(v6);
  v10 = 4096;
  if ( v9 < 0x1000 )
    v10 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 48LL))(v6);
  *((_DWORD *)this + 1324) = v10;
  *((_DWORD *)this + 48) = v10;
  if ( *((_BYTE *)this + 408) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 336, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::Send401(this, 0, 0);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
    return;
  }
LABEL_58:
  v15 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 48LL))(v6);
  v43 = v15;
  if ( WSManHttpListenerRequest::IsEncryptionUsed(this) )
  {
    v17 = *((_QWORD *)this + 14);
    v18 = (struct _SecHandle *)(v17 + 80);
    if ( v17 == -80 )
    {
      v19 = L"4841";
      v20 = 4841;
LABEL_61:
      v21 = 1359;
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", v20, v19, 0x54Fu, 0);
LABEL_68:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      WSManHttpListenerRequest::SendHttpError(
        this,
        0x1F7u,
        1,
        0,
        0,
        v21,
        L"Failed to determine total size of encrypted request",
        &Class);
      AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
      return;
    }
    v22 = *(int *)(v17 + 180);
    if ( (int)v22 >= 3 )
    {
      v19 = L"4844";
      v20 = 4844;
      goto LABEL_61;
    }
    v23 = *((_DWORD *)this + 1138);
    v24 = qword_18027B0C0[15 * v22];
    if ( (_DWORD)v22 == 2 )
      TotalEncryptedSizeInternalSsl = EncryptDecryptHelper::GetTotalEncryptedSizeInternalSsl(
                                        (EncryptDecryptHelper *)&v43,
                                        v18,
                                        v15,
                                        "UTF-16",
                                        0,
                                        v24,
                                        v23,
                                        &v43);
    else
      TotalEncryptedSizeInternalSsl = EncryptDecryptHelper::GetTotalEncryptedSizeInternalNego(
                                        (EncryptDecryptHelper *)&v43,
                                        v18,
                                        v15,
                                        "UTF-16",
                                        v24,
                                        v23,
                                        &v43);
    v21 = TotalEncryptedSizeInternalSsl;
    if ( TotalEncryptedSizeInternalSsl )
      goto LABEL_68;
    v16 = v43;
  }
  v5 = (unsigned int *)((char *)this + 192);
  if ( *((_DWORD *)this + 48) <= v16 )
  {
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  WSManHttpListenerRequest::SendHttpError(this, 0x19Du, 1, 0, 0, 0xDu, L"Request is too large", &Class);
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v44);
}

```

## disassembly

```asm
0x180056878  mov     [rsp-38h+arg_10], rbx
0x18005687d  push    rbp
0x18005687e  push    rsi
0x18005687f  push    rdi
0x180056880  push    r12
0x180056882  push    r13
0x180056884  push    r14
0x180056886  push    r15
0x180056888  mov     rbp, rsp
0x18005688b  sub     rsp, 80h
0x180056892  mov     rsi, rcx
0x180056895  lea     r14, WPP_GLOBAL_Control
0x18005689c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800568a3  cmp     rcx, r14
0x1800568a6  jz      short loc_1800568C9
0x1800568a8  test    dword ptr [rcx+1Ch], 400h
0x1800568af  jz      short loc_1800568C9
0x1800568b1  mov     edx, 149h
0x1800568b6  mov     r9, rsi
0x1800568b9  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x1800568c0  mov     rcx, [rcx+10h]
0x1800568c4  call    WPP_SF_q
0x1800568c9  lea     rbx, [rsi+14D0h]
0x1800568d0  mov     rcx, rbx; this
0x1800568d3  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x1800568d8  mov     dword ptr [rsi+11Ch], 2
0x1800568e2  mov     ecx, [rbx]; dwErrCode
0x1800568e4  xor     r12d, r12d
0x1800568e7  test    ecx, ecx
0x1800568e9  jz      short loc_1800568F3
0x1800568eb  call    cs:__imp_SetLastError
0x1800568f1  jmp     short loc_1800568FD
0x1800568f3  lea     rcx, [rbx+8]; lpCriticalSection
0x1800568f7  call    cs:__imp_LeaveCriticalSection
0x1800568fd  lea     r13, [rsi+138h]
0x180056904  lea     rcx, Class
0x18005690b  lea     r15, [rsi+0B0h]
0x180056912  cmp     [r13+0], r12b
0x180056916  jz      short loc_18005692E
0x180056918  cmp     [r15], r12
0x18005691b  jz      short loc_18005692E
0x18005691d  lea     rbx, [rsi+0C0h]
0x180056924  mov     edi, 200h
0x180056929  jmp     loc_180056F93
0x18005692e  mov     [rbp+var_38], r12d
0x180056932  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180056939  mov     [rbp+var_40], rax
0x18005693d  mov     [rbp+var_30], r12d
0x180056941  or      edi, 0FFFFFFFFh
0x180056944  mov     [rbp+var_2C], edi
0x180056947  mov     [rbp+var_20], rcx
0x18005694b  mov     [rbp+var_18], rcx
0x18005694f  mov     [rbp+var_10], rcx
0x180056953  mov     [rbp+var_8], rcx
0x180056957  mov     [rbp+var_28], 1
0x18005695b  lock inc [rbp+var_38]
0x18005695f  mov     rax, [rsi+50h]
0x180056963  mov     rcx, [rax+10h]
0x180056967  mov     rax, [rcx]
0x18005696a  mov     r8, [rsi+1B8h]
0x180056971  lea     rdx, [rbp+var_40]
0x180056975  mov     rax, [rax+70h]
0x180056979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005697e  mov     rbx, rax
0x180056981  mov     [rbp+arg_8], rax
0x180056985  test    rax, rax
0x180056988  jnz     loc_180056A21
0x18005698e  mov     qword ptr [rsp+80h+EntityBufferLength], r12; struct IRequestContext *
0x180056993  mov     ebx, 54Fh
0x180056998  mov     r9d, ebx; unsigned int
0x18005699b  lea     r8, a6492; "6492"
0x1800569a2  mov     edx, 195Ch; unsigned int
0x1800569a7  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x1800569ae  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800569b3  mov     eax, [rbp+var_2C]
0x1800569b6  cmp     eax, edi
0x1800569b8  jnz     short loc_1800569DD
0x1800569ba  mov     qword ptr [rsp+80h+EntityBufferLength], r12; struct IRequestContext *
0x1800569bf  mov     r9d, ebx; unsigned int
0x1800569c2  lea     r8, a45; "45"
0x1800569c9  mov     edx, 2Dh ; '-'; unsigned int
0x1800569ce  lea     rcx, aOnecoreAdminWm_46; "onecore\\admin\\wmi\\wmx\\stdlib\\CErro"...
0x1800569d5  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800569da  mov     eax, [rbp+var_2C]
0x1800569dd  mov     edx, 1F4h; unsigned __int16
0x1800569e2  lea     rcx, Class
0x1800569e9  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x1800569ee  lea     rcx, aFailedToRetrie_2; "Failed to retrieve server configuration"...
0x1800569f5  mov     [rsp+80h+Overlapped], rcx; unsigned __int16 *
0x1800569fa  mov     dword ptr [rsp+80h+BytesReturned], eax; unsigned int
0x1800569fe  mov     qword ptr [rsp+80h+EntityBufferLength], r12; char *
0x180056a03  xor     r9d, r9d; unsigned int
0x180056a06  mov     r8b, 1; bool
0x180056a09  mov     rcx, rsi; this
0x180056a0c  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x180056a11  nop
0x180056a12  lea     rcx, [rbp+arg_8]
0x180056a16  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180056a1b  nop
0x180056a1c  jmp     loc_1800572BF
0x180056a21  mov     rdi, [rsi+11F0h]
0x180056a28  call    cs:__imp_GetTickCount64
0x180056a2e  mov     r9, rax
0x180056a31  sub     r9, rdi
0x180056a34  mov     ecx, [rbx+60h]
0x180056a37  mov     rax, 624DD2F1A9FBE77h
0x180056a41  mul     r9
0x180056a44  sub     r9, rdx
0x180056a47  shr     r9, 1
0x180056a4a  add     r9, rdx
0x180056a4d  shr     r9, 9
0x180056a51  cmp     r9, rcx
0x180056a54  jbe     short loc_180056AC8
0x180056a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a5d  cmp     rcx, r14
0x180056a60  jz      short loc_180056A80
0x180056a62  test    dword ptr [rcx+1Ch], 400h
0x180056a69  jz      short loc_180056A80
0x180056a6b  mov     edx, 14Dh
0x180056a70  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056a77  mov     rcx, [rcx+10h]
0x180056a7b  call    WPP_SF_
0x180056a80  mov     edx, 1F4h; unsigned __int16
0x180056a85  lea     rcx, Class
0x180056a8c  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x180056a91  lea     rax, aRequestTookToo; "Request took too long to retrieve so re"...
0x180056a98  mov     [rsp+80h+Overlapped], rax; unsigned __int16 *
0x180056a9d  mov     dword ptr [rsp+80h+BytesReturned], 5B4h; unsigned int
0x180056aa5  mov     qword ptr [rsp+80h+EntityBufferLength], r12; char *
0x180056aaa  xor     r9d, r9d; unsigned int
0x180056aad  mov     r8b, 1; bool
0x180056ab0  mov     rcx, rsi; this
0x180056ab3  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x180056ab8  nop
0x180056ab9  lea     rcx, [rbp+arg_8]
0x180056abd  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180056ac2  nop
0x180056ac3  jmp     loc_180056A1C
0x180056ac8  cmp     [r15], r12
0x180056acb  jnz     loc_180056DAA
0x180056ad1  mov     rdx, r13; bool *
0x180056ad4  mov     rcx, rsi; this
0x180056ad7  call    ?IsChunkedRequest@WSManHttpListenerRequest@@AEAA_NPEA_N@Z; WSManHttpListenerRequest::IsChunkedRequest(bool *)
0x180056adc  test    al, al
0x180056ade  jnz     short loc_180056B53
0x180056ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ae7  cmp     rcx, r14
0x180056aea  jz      short loc_180056B0B
0x180056aec  mov     edi, 200h
0x180056af1  test    [rcx+1Ch], edi
0x180056af4  jz      short loc_180056B0B
0x180056af6  mov     edx, 14Eh
0x180056afb  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056b02  mov     rcx, [rcx+10h]
0x180056b06  call    WPP_SF_
0x180056b0b  mov     edx, 1F4h; unsigned __int16
0x180056b10  lea     rcx, Class
0x180056b17  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x180056b1c  lea     rax, aFailedToDeterm; "Failed to determine if the packet is in"...
0x180056b23  mov     [rsp+80h+Overlapped], rax; unsigned __int16 *
0x180056b28  mov     dword ptr [rsp+80h+BytesReturned], 0Dh; unsigned int
0x180056b30  mov     qword ptr [rsp+80h+EntityBufferLength], r12; char *
0x180056b35  xor     r9d, r9d; unsigned int
0x180056b38  mov     r8b, 1; bool
0x180056b3b  mov     rcx, rsi; this
0x180056b3e  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x180056b43  nop
0x180056b44  lea     rcx, [rbp+arg_8]
0x180056b48  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180056b4d  nop
0x180056b4e  jmp     loc_180056A1C
0x180056b53  cmp     [r13+0], r12b
0x180056b57  jz      loc_180056C11
0x180056b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b64  cmp     rcx, r14
0x180056b67  jz      short loc_180056B87
0x180056b69  test    dword ptr [rcx+1Ch], 400h
0x180056b70  jz      short loc_180056B87
0x180056b72  mov     edx, 14Fh
0x180056b77  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056b7e  mov     rcx, [rcx+10h]
0x180056b82  call    WPP_SF_
0x180056b87  mov     rax, [rbx]
0x180056b8a  mov     rcx, rbx
0x180056b8d  mov     rax, [rax+30h]
0x180056b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b96  mov     ecx, 1000h
0x180056b9b  cmp     eax, ecx
0x180056b9d  jnb     short loc_180056BB0
0x180056b9f  mov     rax, [rbx]
0x180056ba2  mov     rcx, rbx
0x180056ba5  mov     rax, [rax+30h]
0x180056ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bae  mov     ecx, eax
0x180056bb0  mov     [rsi+14B0h], ecx
0x180056bb6  mov     [rsi+0C0h], ecx
0x180056bbc  cmp     [rsi+198h], r12b
0x180056bc3  jz      loc_180056DAA
0x180056bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bd0  cmp     rcx, r14
0x180056bd3  jz      short loc_180056BF4
0x180056bd5  mov     edi, 200h
0x180056bda  test    [rcx+1Ch], edi
0x180056bdd  jz      short loc_180056BF4
0x180056bdf  mov     edx, 150h
0x180056be4  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056beb  mov     rcx, [rcx+10h]
0x180056bef  call    WPP_SF_
0x180056bf4  xor     r8d, r8d; unsigned int
0x180056bf7  xor     edx, edx; char *
0x180056bf9  mov     rcx, rsi; this
0x180056bfc  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x180056c01  nop
0x180056c02  lea     rcx, [rbp+arg_8]
0x180056c06  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180056c0b  nop
0x180056c0c  jmp     loc_180056A1C
0x180056c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c18  cmp     rcx, r14
0x180056c1b  jz      short loc_180056C45
0x180056c1d  test    dword ptr [rcx+1Ch], 400h
0x180056c24  jz      short loc_180056C45
0x180056c26  mov     edx, 188h
0x180056c2b  mov     r9, rsi
0x180056c2e  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056c35  mov     rcx, [rcx+10h]
0x180056c39  call    WPP_SF_q
0x180056c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c45  mov     r14d, r12d
0x180056c48  mov     [rbp+arg_0], r12d
0x180056c4c  mov     r8, [rsi+98h]
0x180056c53  movzx   eax, word ptr [r8+148h]
0x180056c5b  mov     edi, 200h
0x180056c60  test    ax, ax
0x180056c63  jz      loc_180056D33
0x180056c69  mov     rdx, [rsi+50h]
0x180056c6d  cmp     eax, [rdx+3A0h]
0x180056c73  ja      short loc_180056CBF
0x180056c75  lea     rdx, [rbp+arg_0]; unsigned int *
0x180056c79  mov     rcx, [r8+150h]; String
0x180056c80  call    ?StringToDword@@YAHPEBDPEAK@Z; StringToDword(char const *,ulong *)
0x180056c85  test    eax, eax
0x180056c87  jnz     loc_180056D2D
0x180056c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c94  lea     rax, WPP_GLOBAL_Control
0x180056c9b  cmp     rcx, rax
0x180056c9e  jz      short loc_180056CE5
0x180056ca0  test    [rcx+1Ch], edi
0x180056ca3  jz      short loc_180056CC6
0x180056ca5  lea     edx, [rdi-77h]
0x180056ca8  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056caf  mov     rcx, [rcx+10h]
0x180056cb3  call    WPP_SF_
0x180056cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180056cbf  lea     rax, WPP_GLOBAL_Control
0x180056cc6  cmp     rcx, rax
0x180056cc9  jz      short loc_180056CE5
0x180056ccb  test    [rcx+1Ch], edi
0x180056cce  jz      short loc_180056CE5
0x180056cd0  mov     edx, 152h
0x180056cd5  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056cdc  mov     rcx, [rcx+10h]
0x180056ce0  call    WPP_SF_
0x180056ce5  mov     edx, 19Bh; unsigned __int16
0x180056cea  lea     rcx, Class
0x180056cf1  mov     [rsp+80h+var_48], rcx; unsigned __int16 *
0x180056cf6  lea     rax, aRequestHasInva; "Request has invalid or missing content "...
0x180056cfd  mov     [rsp+80h+Overlapped], rax; unsigned __int16 *
0x180056d02  mov     dword ptr [rsp+80h+BytesReturned], 0Dh; unsigned int
0x180056d0a  mov     qword ptr [rsp+80h+EntityBufferLength], r12; char *
0x180056d0f  xor     r9d, r9d; unsigned int
0x180056d12  mov     r8b, 1; bool
0x180056d15  mov     rcx, rsi; this
0x180056d18  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x180056d1d  nop
0x180056d1e  lea     rcx, [rbp+arg_8]
0x180056d22  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180056d27  nop
0x180056d28  jmp     loc_180056A1C
0x180056d2d  mov     r14d, [rbp+arg_0]
0x180056d31  jmp     short loc_180056D5D
0x180056d33  lea     rax, WPP_GLOBAL_Control
0x180056d3a  cmp     rcx, rax
0x180056d3d  jz      short loc_180056D6B
0x180056d3f  test    dword ptr [rcx+1Ch], 400h
0x180056d46  jz      short loc_180056D6B
0x180056d48  mov     edx, 18Ah
0x180056d4d  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180056d54  mov     rcx, [rcx+10h]
0x180056d58  call    WPP_SF_
0x180056d5d  lea     rax, WPP_GLOBAL_Control
0x180056d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d6b  test    r14d, r14d
0x180056d6e  jz      loc_180056CC6
0x180056d74  mov     [rsi+0C0h], r14d
0x180056d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d82  cmp     rcx, rax
0x180056d85  jz      short loc_180056DAF
0x180056d87  test    dword ptr [rcx+1Ch], 400h
0x180056d8e  jz      short loc_180056DAF
  ... truncated ...
```

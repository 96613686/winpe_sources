# CDplDuck::Unseal(void)

- ea: `0x1800cb36c`
- end: `0x1800cb969`
- name: `?Unseal@CDplDuck@@AEAAJXZ`
- size: `1533`
- prototype: `__int64 __fastcall(CDplDuck *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b0088`
- `0x1800be8a8`

## callees

- `0x180005045`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180087d68`
- `0x180088190`
- `0x180089c04`
- `0x180089d38`
- `0x1800962c0`
- `0x1800b494c`
- `0x1800cb36c`
- `0x1800cb970`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb7d1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb6be`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb6be`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cb670`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cb670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cb65a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cb65a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb6f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cb6f4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800cb71a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800cb769`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800cb71a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800cb769`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800cb73e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800cb73e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb8b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb8b0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800cb7a5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800cb7a5`

## pseudocode

```c
__int64 __fastcall CDplDuck::Unseal(CDplDuck *this)
{
  __int64 v1; // rax
  void *v2; // rdi
  int v4; // ecx
  unsigned int v5; // ebx
  int v6; // r8d
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  HANDLE CurrentThread; // rax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int LastError; // eax
  DWORD v19; // eax
  __int64 v20; // rcx
  signed int v21; // eax
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  char dwCreationFlags; // [rsp+20h] [rbp-30h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+30h] BYREF
  void *Thread; // [rsp+88h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp+40h] BYREF
  void *lpParameter; // [rsp+98h] [rbp+48h] BYREF

  v1 = *((_QWORD *)this + 2);
  v2 = 0;
  TokenHandle = 0;
  Thread = 0;
  ThreadId = 0;
  Handles[0] = 0;
  Handles[1] = *(HANDLE *)(v1 + 160);
  lpParameter = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 219);
  if ( !(unsigned int)CDplUser::IsCurrentLockOwner(*((CDplUser **)this + 16)) )
  {
    dwCreationFlags = -31;
LABEL_3:
    v5 = -2147418113;
    v6 = -2147418113;
LABEL_4:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 39, dwCreationFlags);
    goto LABEL_45;
  }
  if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 96LL) )
  {
    dwCreationFlags = -28;
    goto LABEL_3;
  }
  v5 = 0;
  if ( !*((_QWORD *)this + 12) )
  {
    v7 = *((_QWORD *)this + 16);
    if ( !*(_DWORD *)(v7 + 252) )
    {
      fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 38);
      v5 = DplibpMemAllocEx(64, 0, 0, &lpParameter);
      v9 = fnEfsLogTrace1String1Dword(
             g_hPublisher,
             (unsigned int)EFS_TRACE_COMPLETE_EVENT,
             (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
             (unsigned int)&sourceString,
             v5,
             39,
             38);
      v2 = lpParameter;
      if ( v9 < 0 )
        goto LABEL_45;
      memset_0(lpParameter, 0, 0x40u);
      _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
      fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 49);
      v5 = CDplService::DuplicateSvcString(
             *(const unsigned __int16 **)(*((_QWORD *)this + 16) + 104LL),
             0xFFFFFFFFFFFFFFFFuLL,
             0xFFFFFFFFFFFFFFFFuLL,
             1,
             (unsigned __int16 **)v2 + 2);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v5,
                  39,
                  49) < 0 )
        goto LABEL_45;
      fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 53);
      v5 = CDplService::DuplicateSvcBuffer(
             *((const unsigned __int8 **)this + 10),
             *((unsigned int *)this + 22),
             v12,
             v13,
             (unsigned __int8 **)v2 + 3);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v5,
                  39,
                  53) < 0 )
        goto LABEL_45;
      *((_DWORD *)v2 + 8) = *((_DWORD *)this + 22);
      *(_QWORD *)v2 = this;
      CDplProtectorBase::AddRef(this);
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
      {
        Thread = CreateThread(0, 0, CDplDuck::_UnsealWorker, v2, 4u, &ThreadId);
        if ( Thread )
        {
          if ( SetThreadToken(&Thread, TokenHandle) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
            CDplProtectorBase::AddRef(*((CDplProtectorBase **)this + 2));
            if ( ResumeThread(Thread) == -1 )
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
              TerminateThread(Thread, 0xFFFFFFFF);
              _InterlockedDecrement((volatile signed __int32 *)v2 + 2);
              CDplServiceImpl::Release(*((CDplServiceImpl **)this + 2));
              dwCreationFlags = -118;
            }
            else
            {
              Handles[0] = Thread;
              v19 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
              if ( !v19 )
              {
                fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 161);
                v5 = *((_DWORD *)v2 + 3);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            v5,
                            39,
                            161) >= 0 )
                {
                  *((_QWORD *)this + 12) = *((_QWORD *)v2 + 6);
                  *((_DWORD *)this + 26) = *((_DWORD *)v2 + 9);
                  *((_DWORD *)this + 27) = *((_DWORD *)v2 + 10);
                  *((_QWORD *)v2 + 6) = 0;
                  *((_DWORD *)this + 31) = *((_DWORD *)v2 + 14);
                }
                goto LABEL_45;
              }
              if ( v19 == 1 )
              {
                v5 = -2147023659;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023659, 39, 181);
                goto LABEL_45;
              }
              if ( v19 != -1 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v20);
                dwCreationFlags = -66;
                goto LABEL_3;
              }
              v21 = GetLastError();
              v5 = v21;
              if ( v21 > 0 )
                v5 = (unsigned __int16)v21 | 0x80070000;
              dwCreationFlags = -71;
            }
          }
          else
          {
            v17 = GetLastError();
            v5 = v17;
            if ( v17 > 0 )
              v5 = (unsigned __int16)v17 | 0x80070000;
            TerminateThread(Thread, 0xFFFFFFFF);
            dwCreationFlags = 98;
          }
        }
        else
        {
          v16 = GetLastError();
          v5 = v16;
          if ( v16 > 0 )
            v5 = (unsigned __int16)v16 | 0x80070000;
          dwCreationFlags = 81;
        }
      }
      else
      {
        v15 = GetLastError();
        v5 = v15;
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
        dwCreationFlags = 71;
      }
      v6 = v5;
      goto LABEL_4;
    }
    if ( *((_DWORD *)this + 31) || *(_DWORD *)(v7 + 368) )
    {
      dwCreationFlags = 12;
      goto LABEL_14;
    }
    fnEfsLogTrace1Strings(v4, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 19);
    v8 = CDplDuck::UnsealSilently(this, 0);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v8,
                39,
                19) < 0 )
    {
      dwCreationFlags = 25;
LABEL_14:
      v5 = -2147024891;
      v6 = -2147024891;
      goto LABEL_4;
    }
  }
LABEL_45:
  if ( Thread )
  {
    CloseHandle(Thread);
    Thread = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 2, 0xFFFFFFFF) == 1 )
  {
    v22 = (void *)*((_QWORD *)v2 + 6);
    if ( v22 )
      DplibMemFree(v22);
    *((_QWORD *)v2 + 6) = 0;
    v23 = (void *)*((_QWORD *)v2 + 3);
    if ( v23 )
      DplibMemFree(v23);
    *((_QWORD *)v2 + 3) = 0;
    v24 = (void *)*((_QWORD *)v2 + 2);
    if ( v24 )
      DplibMemFree(v24);
    *((_QWORD *)v2 + 2) = 0;
    *(_QWORD *)v2 = ReleaseIf<CDplKeyPair>(*(CDplKey **)v2);
    DplibMemFree(v2);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v5,
    39,
    216);
  return v5;
}

```

## disassembly

```asm
0x1800cb36c  push    rbp
0x1800cb36e  push    rbx
0x1800cb36f  push    rsi
0x1800cb370  push    rdi
0x1800cb371  push    r14
0x1800cb373  mov     rbp, rsp
0x1800cb376  sub     rsp, 50h
0x1800cb37a  mov     rax, [rcx+10h]
0x1800cb37e  lea     r8, sourceString
0x1800cb385  xor     edi, edi
0x1800cb387  mov     [rsp+50h+dwCreationFlags], 1CDBh
0x1800cb38f  mov     [rbp+TokenHandle], rdi
0x1800cb393  mov     rsi, rcx
0x1800cb396  mov     [rbp+Thread], rdi
0x1800cb39a  mov     [rbp+ThreadId], edi
0x1800cb39d  mov     [rbp+Handles], rdi
0x1800cb3a1  lea     r14d, [rdi+27h]
0x1800cb3a5  mov     rdx, [rax+0A0h]
0x1800cb3ac  mov     r9d, r14d
0x1800cb3af  mov     [rbp+var_8], rdx
0x1800cb3b3  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800cb3ba  mov     [rbp+lpParameter], rdi
0x1800cb3be  call    fnEfsLogTrace1Strings
0x1800cb3c3  mov     rcx, [rsi+80h]; this
0x1800cb3ca  call    ?IsCurrentLockOwner@CDplUser@@AEAAHXZ; CDplUser::IsCurrentLockOwner(void)
0x1800cb3cf  test    eax, eax
0x1800cb3d1  jnz     short loc_1800CB401
0x1800cb3d3  mov     [rsp+50h+dwCreationFlags], 1CE1h
0x1800cb3db  mov     ebx, 8000FFFFh
0x1800cb3e0  mov     r8d, 8000FFFFh
0x1800cb3e6  mov     rcx, cs:g_hPublisher
0x1800cb3ed  lea     rdx, EFS_TRACE_ERROR
0x1800cb3f4  mov     r9d, r14d
0x1800cb3f7  call    fnEfsLogTrace1
0x1800cb3fc  jmp     loc_1800CB890
0x1800cb401  mov     rax, [rsi+10h]
0x1800cb405  cmp     [rax+60h], rdi
0x1800cb409  jnz     short loc_1800CB415
0x1800cb40b  mov     [rsp+50h+dwCreationFlags], 1CE4h
0x1800cb413  jmp     short loc_1800CB3DB
0x1800cb415  xor     ebx, ebx
0x1800cb417  cmp     [rsi+60h], rbx
0x1800cb41b  jnz     loc_1800CB890
0x1800cb421  mov     rax, [rsi+80h]
0x1800cb428  cmp     [rax+0FCh], ebx
0x1800cb42e  jz      loc_1800CB4CA
0x1800cb434  cmp     [rsi+7Ch], ebx
0x1800cb437  jnz     short loc_1800CB4B2
0x1800cb439  cmp     [rax+170h], ebx
0x1800cb43f  jnz     short loc_1800CB4B2
0x1800cb441  mov     r14d, 1D13h
0x1800cb447  lea     r9d, [rbx+27h]
0x1800cb44b  lea     r8, sourceString
0x1800cb452  mov     [rsp+50h+dwCreationFlags], r14d
0x1800cb457  lea     rdx, EFS_TRACE_START_EVENT
0x1800cb45e  call    fnEfsLogTrace1Strings
0x1800cb463  xor     edx, edx; void *
0x1800cb465  mov     rcx, rsi; this
0x1800cb468  call    ?UnsealSilently@CDplDuck@@AEAAJPEAX@Z; CDplDuck::UnsealSilently(void *)
0x1800cb46d  mov     rcx, cs:g_hPublisher
0x1800cb474  lea     r9, sourceString
0x1800cb47b  mov     [rsp+50h+var_20], r14d
0x1800cb480  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cb487  lea     r14d, [rbx+27h]
0x1800cb48b  mov     dword ptr [rsp+50h+lpThreadId], r14d
0x1800cb490  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cb497  mov     [rsp+50h+dwCreationFlags], eax
0x1800cb49b  call    fnEfsLogTrace1String1Dword
0x1800cb4a0  test    eax, eax
0x1800cb4a2  jns     loc_1800CB890
0x1800cb4a8  mov     [rsp+50h+dwCreationFlags], 1D19h
0x1800cb4b0  jmp     short loc_1800CB4BA
0x1800cb4b2  mov     [rsp+50h+dwCreationFlags], 1D0Ch
0x1800cb4ba  mov     ebx, 80070005h
0x1800cb4bf  mov     r8d, 80070005h
0x1800cb4c5  jmp     loc_1800CB3E6
0x1800cb4ca  mov     edi, 1D26h
0x1800cb4cf  lea     r8, sourceString
0x1800cb4d6  mov     r9d, r14d
0x1800cb4d9  mov     [rsp+50h+dwCreationFlags], edi
0x1800cb4dd  lea     rdx, EFS_TRACE_START_EVENT
0x1800cb4e4  call    fnEfsLogTrace1Strings
0x1800cb4e9  xor     edx, edx
0x1800cb4eb  lea     r9, [rbp+lpParameter]
0x1800cb4ef  xor     r8d, r8d
0x1800cb4f2  lea     ecx, [rdx+40h]
0x1800cb4f5  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800cb4fa  mov     rcx, cs:g_hPublisher
0x1800cb501  lea     r9, sourceString
0x1800cb508  mov     [rsp+50h+var_20], edi
0x1800cb50c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cb513  mov     dword ptr [rsp+50h+lpThreadId], r14d
0x1800cb518  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cb51f  mov     [rsp+50h+dwCreationFlags], eax
0x1800cb523  mov     ebx, eax
0x1800cb525  call    fnEfsLogTrace1String1Dword
0x1800cb52a  mov     rdi, [rbp+lpParameter]
0x1800cb52e  test    eax, eax
0x1800cb530  js      loc_1800CB890
0x1800cb536  xor     edx, edx; Val
0x1800cb538  mov     rcx, rdi; void *
0x1800cb53b  lea     r8d, [rdx+40h]; Size
0x1800cb53f  call    memset_0
0x1800cb544  lock inc dword ptr [rdi+8]
0x1800cb548  mov     r14d, 1D31h
0x1800cb54e  lea     r8, sourceString
0x1800cb555  mov     r9d, 27h ; '''
0x1800cb55b  mov     [rsp+50h+dwCreationFlags], r14d
0x1800cb560  lea     rdx, EFS_TRACE_START_EVENT
0x1800cb567  call    fnEfsLogTrace1Strings
0x1800cb56c  mov     rcx, [rsi+80h]
0x1800cb573  lea     rax, [rdi+10h]
0x1800cb577  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1800cb57b  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned __int16 **
0x1800cb580  mov     r9d, 1; int
0x1800cb586  mov     r8, rdx; unsigned __int64
0x1800cb589  mov     rcx, [rcx+68h]; unsigned __int16 *
0x1800cb58d  call    ?DuplicateSvcString@CDplService@@SAJPEBG_K1HPEAPEAG@Z; CDplService::DuplicateSvcString(ushort const *,unsigned __int64,unsigned __int64,int,ushort * *)
0x1800cb592  mov     rcx, cs:g_hPublisher
0x1800cb599  lea     r9, sourceString
0x1800cb5a0  mov     [rsp+50h+var_20], r14d
0x1800cb5a5  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cb5ac  mov     r14d, 27h ; '''
0x1800cb5b2  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cb5b9  mov     dword ptr [rsp+50h+lpThreadId], r14d
0x1800cb5be  mov     ebx, eax
0x1800cb5c0  mov     [rsp+50h+dwCreationFlags], eax
0x1800cb5c4  call    fnEfsLogTrace1String1Dword
0x1800cb5c9  test    eax, eax
0x1800cb5cb  js      loc_1800CB890
0x1800cb5d1  mov     r14d, 1D35h
0x1800cb5d7  lea     r8, sourceString
0x1800cb5de  mov     r9d, 27h ; '''
0x1800cb5e4  mov     [rsp+50h+dwCreationFlags], r14d
0x1800cb5e9  lea     rdx, EFS_TRACE_START_EVENT
0x1800cb5f0  call    fnEfsLogTrace1Strings
0x1800cb5f5  mov     edx, [rsi+58h]; Size
0x1800cb5f8  lea     rax, [rdi+18h]
0x1800cb5fc  mov     rcx, [rsi+50h]; Src
0x1800cb600  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned __int8 **
0x1800cb605  call    ?DuplicateSvcBuffer@CDplService@@SAJPEBE_KHHPEAPEAE@Z; CDplService::DuplicateSvcBuffer(uchar const *,unsigned __int64,int,int,uchar * *)
0x1800cb60a  mov     rcx, cs:g_hPublisher
0x1800cb611  lea     r9, sourceString
0x1800cb618  mov     [rsp+50h+var_20], r14d
0x1800cb61d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cb624  mov     r14d, 27h ; '''
0x1800cb62a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cb631  mov     dword ptr [rsp+50h+lpThreadId], r14d
0x1800cb636  mov     ebx, eax
0x1800cb638  mov     [rsp+50h+dwCreationFlags], eax
0x1800cb63c  call    fnEfsLogTrace1String1Dword
0x1800cb641  test    eax, eax
0x1800cb643  js      loc_1800CB890
0x1800cb649  mov     eax, [rsi+58h]
0x1800cb64c  mov     rcx, rsi; this
0x1800cb64f  mov     [rdi+20h], eax
0x1800cb652  mov     [rdi], rsi
0x1800cb655  call    ?AddRef@CDplProtectorBase@@IEAAJXZ; CDplProtectorBase::AddRef(void)
0x1800cb65a  call    cs:__imp_GetCurrentThread
0x1800cb660  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800cb664  mov     edx, 0F01FFh; DesiredAccess
0x1800cb669  mov     rcx, rax; ThreadHandle
0x1800cb66c  lea     r8d, [r14-26h]; OpenAsSelf
0x1800cb670  call    cs:__imp_OpenThreadToken
0x1800cb676  test    eax, eax
0x1800cb678  jnz     short loc_1800CB69F
0x1800cb67a  call    cs:__imp_GetLastError
0x1800cb680  mov     ebx, eax
0x1800cb682  test    eax, eax
0x1800cb684  jle     short loc_1800CB68F
0x1800cb686  movzx   ebx, ax
0x1800cb689  or      ebx, 80070000h
0x1800cb68f  mov     [rsp+50h+dwCreationFlags], 1D47h
0x1800cb697  mov     r8d, ebx
0x1800cb69a  jmp     loc_1800CB3E6
0x1800cb69f  lea     rax, [rbp+ThreadId]
0x1800cb6a3  mov     r9, rdi; lpParameter
0x1800cb6a6  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x1800cb6ab  lea     r8, ?_UnsealWorker@CDplDuck@@CAKPEAX@Z; lpStartAddress
0x1800cb6b2  xor     edx, edx; dwStackSize
0x1800cb6b4  mov     [rsp+50h+dwCreationFlags], 4; dwCreationFlags
0x1800cb6bc  xor     ecx, ecx; lpThreadAttributes
0x1800cb6be  call    cs:__imp_CreateThread
0x1800cb6c4  mov     [rbp+Thread], rax
0x1800cb6c8  test    rax, rax
0x1800cb6cb  jnz     short loc_1800CB6EC
0x1800cb6cd  call    cs:__imp_GetLastError
0x1800cb6d3  mov     ebx, eax
0x1800cb6d5  test    eax, eax
0x1800cb6d7  jle     short loc_1800CB6E2
0x1800cb6d9  movzx   ebx, ax
0x1800cb6dc  or      ebx, 80070000h
0x1800cb6e2  mov     [rsp+50h+dwCreationFlags], 1D51h
0x1800cb6ea  jmp     short loc_1800CB697
0x1800cb6ec  mov     rdx, [rbp+TokenHandle]; Token
0x1800cb6f0  lea     rcx, [rbp+Thread]; Thread
0x1800cb6f4  call    cs:__imp_SetThreadToken
0x1800cb6fa  test    eax, eax
0x1800cb6fc  jnz     short loc_1800CB72D
0x1800cb6fe  call    cs:__imp_GetLastError
0x1800cb704  mov     ebx, eax
0x1800cb706  test    eax, eax
0x1800cb708  jle     short loc_1800CB713
0x1800cb70a  movzx   ebx, ax
0x1800cb70d  or      ebx, 80070000h
0x1800cb713  mov     rcx, [rbp+Thread]; hThread
0x1800cb717  or      edx, 0FFFFFFFFh; dwExitCode
0x1800cb71a  call    cs:__imp_TerminateThread
0x1800cb720  mov     [rsp+50h+dwCreationFlags], 1D62h
0x1800cb728  jmp     loc_1800CB697
0x1800cb72d  lock inc dword ptr [rdi+8]
0x1800cb731  mov     rcx, [rsi+10h]; this
0x1800cb735  call    ?AddRef@CDplProtectorBase@@IEAAJXZ; CDplProtectorBase::AddRef(void)
0x1800cb73a  mov     rcx, [rbp+Thread]; hThread
0x1800cb73e  call    cs:__imp_ResumeThread
0x1800cb744  or      r14d, 0FFFFFFFFh
0x1800cb748  cmp     eax, r14d
0x1800cb74b  jnz     short loc_1800CB78F
0x1800cb74d  call    cs:__imp_GetLastError
0x1800cb753  mov     ebx, eax
0x1800cb755  test    eax, eax
0x1800cb757  jle     short loc_1800CB762
0x1800cb759  movzx   ebx, ax
0x1800cb75c  or      ebx, 80070000h
0x1800cb762  mov     rcx, [rbp+Thread]; hThread
0x1800cb766  mov     edx, r14d; dwExitCode
0x1800cb769  call    cs:__imp_TerminateThread
0x1800cb76f  lock dec dword ptr [rdi+8]
0x1800cb773  mov     rcx, [rsi+10h]; this
0x1800cb777  call    ?Release@CDplServiceImpl@@QEAAJXZ; CDplServiceImpl::Release(void)
0x1800cb77c  mov     [rsp+50h+dwCreationFlags], 1D8Ah
0x1800cb784  mov     r14d, 27h ; '''
0x1800cb78a  jmp     loc_1800CB697
0x1800cb78f  mov     rax, [rbp+Thread]
0x1800cb793  lea     rdx, [rbp+Handles]; lpHandles
0x1800cb797  xor     r8d, r8d; bWaitAll
0x1800cb79a  mov     [rbp+Handles], rax
0x1800cb79e  mov     r9d, r14d; dwMilliseconds
0x1800cb7a1  lea     ecx, [r8+2]; nCount
0x1800cb7a5  call    cs:__imp_WaitForMultipleObjects
0x1800cb7ab  test    eax, eax
0x1800cb7ad  jz      short loc_1800CB80E
0x1800cb7af  cmp     eax, 1
0x1800cb7b2  jz      short loc_1800CB7F0
0x1800cb7b4  cmp     eax, r14d
0x1800cb7b7  jz      short loc_1800CB7D1
0x1800cb7b9  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x1800cb7be  mov     [rsp+50h+dwCreationFlags], 1DBEh
0x1800cb7c6  mov     r14d, 27h ; '''
0x1800cb7cc  jmp     loc_1800CB3DB
0x1800cb7d1  call    cs:__imp_GetLastError
0x1800cb7d7  mov     ebx, eax
0x1800cb7d9  test    eax, eax
0x1800cb7db  jle     short loc_1800CB7E6
0x1800cb7dd  movzx   ebx, ax
0x1800cb7e0  or      ebx, 80070000h
0x1800cb7e6  mov     [rsp+50h+dwCreationFlags], 1DB9h
0x1800cb7ee  jmp     short loc_1800CB784
0x1800cb7f0  mov     ebx, 800704D5h
0x1800cb7f5  mov     [rsp+50h+dwCreationFlags], 1DB5h
0x1800cb7fd  mov     r14d, 27h ; '''
0x1800cb803  mov     r8d, 800704D5h
0x1800cb809  jmp     loc_1800CB3E6
0x1800cb80e  mov     r14d, 1DA1h
0x1800cb814  lea     r8, sourceString
0x1800cb81b  mov     r9d, 27h ; '''
0x1800cb821  mov     [rsp+50h+dwCreationFlags], r14d
0x1800cb826  lea     rdx, EFS_TRACE_START_EVENT
0x1800cb82d  call    fnEfsLogTrace1Strings
0x1800cb832  mov     ebx, [rdi+0Ch]
0x1800cb835  lea     r9, sourceString
0x1800cb83c  mov     rcx, cs:g_hPublisher
0x1800cb843  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cb84a  mov     [rsp+50h+var_20], r14d
0x1800cb84f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cb856  mov     r14d, 27h ; '''
0x1800cb85c  mov     dword ptr [rsp+50h+lpThreadId], r14d
0x1800cb861  mov     [rsp+50h+dwCreationFlags], ebx
0x1800cb865  call    fnEfsLogTrace1String1Dword
0x1800cb86a  test    eax, eax
0x1800cb86c  js      short loc_1800CB890
0x1800cb86e  mov     rax, [rdi+30h]
0x1800cb872  mov     [rsi+60h], rax
0x1800cb876  mov     eax, [rdi+24h]
0x1800cb879  mov     [rsi+68h], eax
0x1800cb87c  mov     eax, [rdi+28h]
0x1800cb87f  mov     [rsi+6Ch], eax
0x1800cb882  mov     qword ptr [rdi+30h], 0
0x1800cb88a  mov     eax, [rdi+38h]
0x1800cb88d  mov     [rsi+7Ch], eax
0x1800cb890  mov     rcx, [rbp+Thread]; hObject
0x1800cb894  test    rcx, rcx
0x1800cb897  jz      short loc_1800CB8A7
0x1800cb899  call    cs:__imp_CloseHandle
0x1800cb89f  mov     [rbp+Thread], 0
0x1800cb8a7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800cb8ab  test    rcx, rcx
0x1800cb8ae  jz      short loc_1800CB8BE
0x1800cb8b0  call    cs:__imp_CloseHandle
0x1800cb8b6  mov     [rbp+TokenHandle], 0
  ... truncated ...
```

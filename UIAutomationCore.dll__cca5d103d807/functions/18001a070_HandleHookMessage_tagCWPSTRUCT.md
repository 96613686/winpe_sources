# HandleHookMessage(tagCWPSTRUCT * &)

- ea: `0x18001a070`
- end: `0x18001a7cc`
- name: `?HandleHookMessage@@YAJAEAPEAUtagCWPSTRUCT@@@Z`
- size: `1884`
- prototype: `__int64 __fastcall(struct tagCWPSTRUCT **)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180019fe0`

## callees

- `0x18001a070`
- `0x18001a7d4`
- `0x18001c4c8`
- `0x1800220f0`
- `0x180022140`
- `0x1800288d0`
- `0x180029d54`
- `0x18002f580`
- `0x18005bad0`
- `0x180069888`
- `0x180083ed0`
- `0x1800984e0`
- `0x18015f090`
- `0x1801601f0`
- `0x1801b2ef4`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1801e9240`
- `0x1801e9258`
- `0x1801ef320`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001a269`
- `msvcp_win!_Mtx_unlock` at `0x18001a38e`
- `msvcp_win!_Mtx_unlock` at `0x18001a269`
- `msvcp_win!_Mtx_unlock` at `0x18001a38e`
- `msvcp_win!_Mtx_lock` at `0x18001a11e`
- `msvcp_win!_Mtx_lock` at `0x18001a11e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a6fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a711`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a6fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001a711`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a770`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a770`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18001a2de`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x18001a2de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a296`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a296`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a2b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a2b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a2ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a2ee`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x18001a5eb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RegisterWindowMessageW` at `0x18001a5eb`
- `ext-ms-win-ntuser-message-l1-1-2!ReplyMessage` at `0x18001a2be`
- `ext-ms-win-ntuser-message-l1-1-2!ReplyMessage` at `0x18001a2be`

## string_xrefs

- `0x18001a36f`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a47e`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a61c`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a661`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a678`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a6bc`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a6db`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a73a`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x18001a353`: `onecore\windows\accessibletech\common\basicuiautils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HandleHookMessage(struct tagCWPSTRUCT **a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 *v5; // rbx
  __int64 result; // rax
  int v7; // edi
  __int64 v8; // rbx
  _QWORD *v9; // r8
  unsigned int *v10; // rbx
  void **v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  char v16; // al
  DWORD CurrentProcessId; // edi
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // edi
  int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rdi
  unsigned __int64 v27; // rbx
  size_t v28; // rbx
  __int64 v29; // rcx
  char HasProcessedHookConnectionString; // bl
  __int64 v31; // rcx
  ChannelBasedServerConnectionManager *v32; // rcx
  int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // r15
  char *v36; // r14
  size_t v37; // rbx
  int v38; // [rsp+20h] [rbp-1018h]
  int v39; // [rsp+20h] [rbp-1018h]
  int v40; // [rsp+20h] [rbp-1018h]
  int v41; // [rsp+20h] [rbp-1018h]
  int v42; // [rsp+20h] [rbp-1018h]
  unsigned int *v43; // [rsp+40h] [rbp-FF8h]
  __int128 v44; // [rsp+50h] [rbp-FE8h] BYREF
  unsigned __int64 v45; // [rsp+60h] [rbp-FD8h]
  __int64 v46; // [rsp+68h] [rbp-FD0h]
  unsigned __int16 Src; // [rsp+70h] [rbp-FC8h] BYREF
  char v48[3998]; // [rsp+72h] [rbp-FC6h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1038h] [rbp+0h]

  try
  {
    if ( dword_1803A1A10 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 88LL) )
    {
      Init_thread_header(&dword_1803A1A10);
      if ( dword_1803A1A10 == -1 )
      {
        Msg = RegisterWindowMessageW(L"UiaServerConnection_HookMessage");
        Init_thread_footer(&dword_1803A1A10);
      }
    }
    if ( Msg )
    {
      v5 = (__int64 *)*a1;
      if ( *((_DWORD *)v5 + 4) != Msg )
        return 0;
      v7 = *((_DWORD *)v5 + 2);
      v8 = *v5;
      if ( v7 )
      {
        if ( _Mtx_lock((_Mtx_t)&InProcHookMessageManager::s_payloadMap) )
        {
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( (_DWORD)qword_18039E19C == 0x7FFFFFFF )
        {
          LODWORD(qword_18039E19C) = 2147483646;
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        _mm_lfence();
        v9 = (_QWORD *)*((_QWORD *)qword_18039E1B8
                       + 2
                       * (qword_18039E1D0
                        & (0x100000001B3LL
                         * (BYTE3(v8)
                          ^ (0x100000001B3LL
                           * (BYTE2(v8)
                            ^ (0x100000001B3LL
                             * (BYTE1(v8) ^ (0x100000001B3LL * ((unsigned __int8)v8 ^ 0xCBF29CE484222325uLL)))))))))
                       + 1);
        if ( v9 == (_QWORD *)qword_18039E1A8 )
        {
LABEL_10:
          v9 = 0;
        }
        else
        {
          while ( (_DWORD)v8 != *((_DWORD *)v9 + 4) )
          {
            if ( v9 == *((_QWORD **)qword_18039E1B8
                       + 2
                       * (qword_18039E1D0
                        & (0x100000001B3LL
                         * (BYTE3(v8)
                          ^ (0x100000001B3LL
                           * (BYTE2(v8)
                            ^ (0x100000001B3LL
                             * (BYTE1(v8) ^ (0x100000001B3LL * ((unsigned __int8)v8 ^ 0xCBF29CE484222325uLL)))))))))) )
              goto LABEL_10;
            v9 = (_QWORD *)v9[1];
          }
        }
        if ( !v9 )
          v9 = (_QWORD *)qword_18039E1A8;
        if ( v9 == (_QWORD *)qword_18039E1A8 )
        {
          _Mtx_unlock((_Mtx_t)&InProcHookMessageManager::s_payloadMap);
          v16 = 0;
          v10 = v43;
        }
        else
        {
          v10 = (unsigned int *)v9[3];
          _mm_lfence();
          v11 = (void **)((char *)qword_18039E1B8
                        + 16
                        * (qword_18039E1D0
                         & (0x100000001B3LL
                          * (*((unsigned __int8 *)v9 + 19)
                           ^ (0x100000001B3LL
                            * (*((unsigned __int8 *)v9 + 18)
                             ^ (0x100000001B3LL
                              * (*((unsigned __int8 *)v9 + 17)
                               ^ (0x100000001B3LL * (*((unsigned __int8 *)v9 + 16) ^ 0xCBF29CE484222325uLL))))))))));
          v12 = *v11;
          if ( v11[1] == v9 )
          {
            if ( v12 == v9 )
            {
              v13 = qword_18039E1A8;
              *v11 = (void *)qword_18039E1A8;
            }
            else
            {
              v13 = v9[1];
            }
            v11[1] = (void *)v13;
          }
          else if ( v12 == v9 )
          {
            *v11 = (void *)*v9;
          }
          v14 = *v9;
          --qword_18039E1B0;
          *(_QWORD *)v9[1] = v14;
          *(_QWORD *)(v14 + 8) = v9[1];
          operator delete(v9);
          _Mtx_unlock((_Mtx_t)&InProcHookMessageManager::s_payloadMap);
          v16 = 1;
        }
        if ( v16 )
        {
          if ( v7 == 3 )
          {
            if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
              McTemplateU0q_EventWriteTransfer(v15, ProcessIncomingRequest_ContextChange_Stop, *v10);
            AcquireSRWLockExclusive((PSRWLOCK)v10 + 4);
            if ( *((_QWORD *)v10 + 2) )
            {
              *((_BYTE *)v10 + 40) = 1;
              if ( v10 != (unsigned int *)-32LL )
                ReleaseSRWLockExclusive((PSRWLOCK)v10 + 4);
              ReplyMessage(1);
              v10[6] = (*((__int64 (__fastcall **)(_QWORD))v10 + 1))(*((_QWORD *)v10 + 2));
              v10[11] = 1;
              WakeByAddressSingle(v10 + 11);
            }
            else
            {
              v10[6] = -2146233083;
              if ( v10 != (unsigned int *)-32LL )
                ReleaseSRWLockExclusive((PSRWLOCK)v10 + 4);
            }
            return 0;
          }
          v20 = v7 - 1;
          if ( v20 )
          {
            if ( v20 == 1 )
            {
              InProcProxyEventManager::TranslateWinEvents((__int64)v10);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8D6,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)0x80004005LL,
              v38);
            result = 2147500037LL;
          }
          else
          {
            v44 = *(_OWORD *)(v10 + 6);
            LOBYTE(v38) = *((_BYTE *)v10 + 40);
            v21 = HookBasedServerConnection::CreateProxyNode(*((_QWORD *)v10 + 1), &v44, v10[4], v10[5]);
            v23 = v21;
            if ( v21 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x8C1,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
                (const char *)(unsigned int)v21,
                v38);
              result = v23;
            }
            else
            {
              v40 = v10[5];
              v24 = ChannelBasedServerConnectionManager::AddNodeToPendingObjects(v22, 0, *(_QWORD *)v10, v10[4]);
              v25 = v24;
              if ( v24 >= 0 )
                return 0;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x8C9,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
                (const char *)(unsigned int)v24,
                v40);
              result = v25;
            }
          }
        }
        else
        {
          result = 0;
        }
      }
      else
      {
        CurrentProcessId = GetCurrentProcessId();
        Src = 0;
        memset_0(v48, 0, sizeof(v48));
        if ( (_DWORD)v8 )
        {
          v38 = CurrentProcessId;
          v18 = StringCchPrintfW(&Src, 0x7D0u, L"%ws_%d_%04Ix", L"%ws");
          v19 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x62,
              (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
              (const char *)(unsigned int)v18,
              CurrentProcessId);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8A6,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
              (const char *)v19,
              v39);
            return v19;
          }
        }
        else
        {
          Src = 0;
        }
        v44 = 0;
        v26 = -1;
        v27 = -1;
        do
          ++v27;
        while ( *(_WORD *)&v48[2 * v27 - 2] );
        if ( v27 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlength_error("string too long");
        if ( v27 > 7 )
        {
          v35 = std::wstring::_Calculate_growth(v27, 7, 0x7FFFFFFFFFFFFFFELL);
          v36 = (char *)std::allocator<unsigned short>::allocate(&v44, v35 + 1);
          *(_QWORD *)&v44 = v36;
          v45 = v27;
          v46 = v35;
          v37 = 2 * v27;
          memcpy_0(v36, &Src, v37);
          *(_WORD *)&v36[v37] = 0;
        }
        else
        {
          v45 = v27;
          v46 = 7;
          v28 = 2 * v27;
          memcpy_0(&v44, &Src, v28);
          *(_WORD *)((char *)&v44 + v28) = 0;
        }
        HasProcessedHookConnectionString = ChannelBasedServerConnectionManager::HasProcessedHookConnectionString(
                                             v29,
                                             &v44);
        std::wstring::_Tidy_deallocate(&v44);
        if ( HasProcessedHookConnectionString )
        {
          result = 0;
        }
        else
        {
          std::wstring::wstring(&v44, &Src);
          ChannelBasedServerConnectionManager::AddProcessedHookConnectionString(v31, &v44);
          std::wstring::_Tidy_deallocate(&v44);
          v33 = OverlappedIOManager::Init((OverlappedIOManager *)qword_18039E090);
          if ( v33 < 0 )
          {
            v34 = 1401;
          }
          else
          {
            do
              ++v26;
            while ( *(_WORD *)&v48[2 * v26 - 2] );
            if ( !v26 )
              return 0;
            v33 = ChannelBasedServerConnectionManager::SetupConnectionEvents(v32, &Src, 0);
            if ( v33 >= 0 )
              return 0;
            v34 = 1406;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
            (const char *)(unsigned int)v33,
            v38);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8B1,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
            (const char *)(unsigned int)v33,
            v41);
          result = (unsigned int)v33;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x866,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)0x80004005LL,
        v38);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x871,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)0x80004005LL,
        v42);
      result = 2147500037LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8DB,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x18001a070  mov     [rsp+arg_8], rbx
0x18001a075  mov     [rsp+arg_10], rsi
0x18001a07a  push    rdi
0x18001a07b  push    r14
0x18001a07d  push    r15
0x18001a07f  mov     eax, 1020h
0x18001a084  call    _alloca_probe
0x18001a089  sub     rsp, rax
0x18001a08c  mov     rax, cs:__security_cookie
0x18001a093  xor     rax, rsp
0x18001a096  mov     [rsp+1038h+var_28], rax
0x18001a09e  mov     rbx, rcx
0x18001a0a1  mov     edx, cs:_tls_index
0x18001a0a7  mov     rax, gs:58h
0x18001a0b0  mov     ecx, 58h ; 'X'
0x18001a0b5  mov     rax, [rax+rdx*8]
0x18001a0b9  mov     edx, [rcx+rax]
0x18001a0bc  cmp     cs:dword_1803A1A10, edx
0x18001a0c2  jg      loc_18001A5CB
0x18001a0c8  mov     eax, cs:Msg
0x18001a0ce  test    eax, eax
0x18001a0d0  jz      loc_18001A6AE
0x18001a0d6  mov     rbx, [rbx]
0x18001a0d9  cmp     [rbx+10h], eax
0x18001a0dc  jz      short loc_18001A109
0x18001a0de  xor     eax, eax
0x18001a0e0  mov     rcx, [rsp+1038h+var_28]
0x18001a0e8  xor     rcx, rsp; StackCookie
0x18001a0eb  call    __security_check_cookie
0x18001a0f0  lea     r11, [rsp+1038h+var_18]
0x18001a0f8  mov     rbx, [r11+28h]
0x18001a0fc  mov     rsi, [r11+30h]
0x18001a100  mov     rsp, r11
0x18001a103  pop     r15
0x18001a105  pop     r14
0x18001a107  pop     rdi
0x18001a108  retn
0x18001a109  mov     edi, [rbx+8]
0x18001a10c  mov     rbx, [rbx]
0x18001a10f  test    edi, edi
0x18001a111  jz      loc_18001A2EC
0x18001a117  lea     rcx, ?s_payloadMap@InProcHookMessageManager@@0V?$ThreadSafeMap@I_J@@A; _Mtx_t
0x18001a11e  call    cs:__imp__Mtx_lock
0x18001a124  test    eax, eax
0x18001a126  jnz     loc_18001A6F6
0x18001a12c  cmp     dword ptr cs:qword_18039E19C, 7FFFFFFFh
0x18001a136  jz      loc_18001A702
0x18001a13c  mov     rax, rbx
0x18001a13f  shr     rax, 18h
0x18001a143  movzx   r8d, al
0x18001a147  mov     rax, rbx
0x18001a14a  shr     rax, 10h
0x18001a14e  movzx   edx, al
0x18001a151  mov     rax, rbx
0x18001a154  shr     rax, 8
0x18001a158  movzx   ecx, al
0x18001a15b  movzx   r9d, bl
0x18001a15f  lfence
0x18001a162  mov     r11, 0CBF29CE484222325h
0x18001a16c  xor     r9, r11
0x18001a16f  mov     r10, 100000001B3h
0x18001a179  imul    r9, r10
0x18001a17d  xor     r9, rcx
0x18001a180  imul    r9, r10
0x18001a184  xor     r9, rdx
0x18001a187  imul    r9, r10
0x18001a18b  xor     r9, r8
0x18001a18e  imul    r9, r10
0x18001a192  and     r9, cs:qword_18039E1D0
0x18001a199  add     r9, r9
0x18001a19c  mov     rax, cs:qword_18039E1B8
0x18001a1a3  mov     r8, [rax+r9*8+8]
0x18001a1a8  mov     rcx, cs:qword_18039E1A8
0x18001a1af  cmp     r8, rcx
0x18001a1b2  jnz     loc_18001A3A7
0x18001a1b8  xor     esi, esi
0x18001a1ba  mov     r8d, esi
0x18001a1bd  test    r8, r8
0x18001a1c0  jz      loc_18001A4B3
0x18001a1c6  cmp     r8, rcx
0x18001a1c9  jz      loc_18001A387
0x18001a1cf  mov     rbx, [r8+18h]
0x18001a1d3  lfence
0x18001a1d6  movzx   edx, byte ptr [r8+10h]
0x18001a1db  xor     rdx, r11
0x18001a1de  imul    rdx, r10
0x18001a1e2  movzx   eax, byte ptr [r8+11h]
0x18001a1e7  xor     rdx, rax
0x18001a1ea  imul    rdx, r10
0x18001a1ee  movzx   eax, byte ptr [r8+12h]
0x18001a1f3  xor     rdx, rax
0x18001a1f6  imul    rdx, r10
0x18001a1fa  movzx   eax, byte ptr [r8+13h]
0x18001a1ff  xor     rdx, rax
0x18001a202  imul    rdx, r10
0x18001a206  and     rdx, cs:qword_18039E1D0
0x18001a20d  shl     rdx, 4
0x18001a211  add     rdx, cs:qword_18039E1B8
0x18001a218  mov     rax, [rdx]
0x18001a21b  cmp     [rdx+8], r8
0x18001a21f  jnz     loc_18001A718
0x18001a225  cmp     rax, r8
0x18001a228  jnz     loc_18001A608
0x18001a22e  mov     rax, cs:qword_18039E1A8
0x18001a235  mov     [rdx], rax
0x18001a238  mov     [rdx+8], rax
0x18001a23c  mov     rdx, [r8]
0x18001a23f  dec     cs:qword_18039E1B0
0x18001a246  mov     rax, [r8+8]
0x18001a24a  mov     [rax], rdx
0x18001a24d  mov     rax, [r8+8]
0x18001a251  mov     [rdx+8], rax
0x18001a255  mov     edx, 20h ; ' '
0x18001a25a  mov     rcx, r8; Block
0x18001a25d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a262  lea     rcx, ?s_payloadMap@InProcHookMessageManager@@0V?$ThreadSafeMap@I_J@@A; _Mtx_t
0x18001a269  call    cs:__imp__Mtx_unlock
0x18001a26f  mov     al, 1
0x18001a271  test    al, al
0x18001a273  jz      loc_18001A3A0
0x18001a279  cmp     edi, 3
0x18001a27c  jnz     loc_18001A3B8
0x18001a282  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18001a289  jnz     loc_18001A755
0x18001a28f  lea     rdi, [rbx+20h]
0x18001a293  mov     rcx, rdi; SRWLock
0x18001a296  call    cs:__imp_AcquireSRWLockExclusive
0x18001a29c  cmp     qword ptr [rbx+10h], 0
0x18001a2a1  jz      loc_18001A690
0x18001a2a7  mov     byte ptr [rbx+28h], 1
0x18001a2ab  test    rdi, rdi
0x18001a2ae  jz      short loc_18001A2B9
0x18001a2b0  mov     rcx, rdi; SRWLock
0x18001a2b3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a2b9  mov     ecx, 1; lResult
0x18001a2be  call    cs:__imp_ReplyMessage
0x18001a2c4  mov     rcx, [rbx+10h]
0x18001a2c8  mov     rax, [rbx+8]
0x18001a2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d1  mov     [rbx+18h], eax
0x18001a2d4  lea     rcx, [rbx+2Ch]; Address
0x18001a2d8  mov     dword ptr [rcx], 1
0x18001a2de  call    cs:__imp_WakeByAddressSingle
0x18001a2e4  nop
0x18001a2e5  xor     eax, eax
0x18001a2e7  jmp     loc_18001A0E0
0x18001a2ec  xor     esi, esi
0x18001a2ee  call    cs:__imp_GetCurrentProcessId
0x18001a2f4  mov     edi, eax
0x18001a2f6  mov     ebx, ebx
0x18001a2f8  mov     [rsp+1038h+Src], si
0x18001a2fd  xor     edx, edx; Val
0x18001a2ff  mov     r8d, 0F9Eh; Size
0x18001a305  lea     rcx, [rsp+1038h+var_FC6]; void *
0x18001a30a  call    memset_0
0x18001a30f  test    rbx, rbx
0x18001a312  jz      loc_18001A4BB
0x18001a318  mov     [rsp+1038h+var_1010], rbx
0x18001a31d  mov     [rsp+1038h+var_1018], edi; int
0x18001a321  lea     r9, aWs; "%ws"
0x18001a328  lea     r8, aWsD04ix; "%ws_%d_%04Ix"
0x18001a32f  mov     edx, 7D0h; unsigned __int64
0x18001a334  lea     rcx, [rsp+1038h+Src]; unsigned __int16 *
0x18001a339  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a33e  mov     ebx, eax
0x18001a340  test    eax, eax
0x18001a342  jns     loc_18001A4C0
0x18001a348  mov     rcx, [rsp+1038h]; this
0x18001a350  mov     r9d, eax; char *
0x18001a353  lea     r8, aOnecoreWindows_70; "onecore\\windows\\accessibletech\\commo"...
0x18001a35a  mov     edx, 62h ; 'b'; void *
0x18001a35f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a364  mov     rcx, [rsp+1038h]; this
0x18001a36c  mov     r9d, ebx; char *
0x18001a36f  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18001a376  mov     edx, 8A6h; void *
0x18001a37b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a380  mov     eax, ebx
0x18001a382  jmp     loc_18001A0E0
0x18001a387  lea     rcx, ?s_payloadMap@InProcHookMessageManager@@0V?$ThreadSafeMap@I_J@@A; _Mtx_t
0x18001a38e  call    cs:__imp__Mtx_unlock
0x18001a394  xor     al, al
0x18001a396  mov     rbx, [rsp+1038h+var_FF8]
0x18001a39b  jmp     loc_18001A271
0x18001a3a0  xor     eax, eax
0x18001a3a2  jmp     loc_18001A0E0
0x18001a3a7  mov     rdx, [rax+r9*8]
0x18001a3ab  cmp     ebx, [r8+10h]
0x18001a3af  jnz     short loc_18001A3DB
0x18001a3b1  xor     esi, esi
0x18001a3b3  jmp     loc_18001A1BD
0x18001a3b8  test    edi, edi
0x18001a3ba  jz      loc_18001A2EE
0x18001a3c0  sub     edi, 1
0x18001a3c3  jz      short loc_18001A3EA
0x18001a3c5  cmp     edi, 1
0x18001a3c8  jnz     loc_18001A72C
0x18001a3ce  mov     rcx, rbx; __int64
0x18001a3d1  call    ?TranslateWinEvents@InProcProxyEventManager@@SAX_J@Z; InProcProxyEventManager::TranslateWinEvents(__int64)
0x18001a3d6  jmp     loc_18001A2E5
0x18001a3db  cmp     r8, rdx
0x18001a3de  jz      loc_18001A1B8
0x18001a3e4  mov     r8, [r8+8]
0x18001a3e8  jmp     short loc_18001A3AB
0x18001a3ea  mov     [rsp+1038h+var_FF8], rsi
0x18001a3ef  movups  xmm0, xmmword ptr [rbx+18h]
0x18001a3f3  movaps  [rsp+1038h+var_FE8], xmm0
0x18001a3f8  lea     rax, [rsp+1038h+var_FF8]
0x18001a3fd  mov     [rsp+1038h+var_1008], rax
0x18001a402  movzx   eax, byte ptr [rbx+28h]
0x18001a406  mov     byte ptr [rsp+1038h+var_1018], al; int
0x18001a40a  mov     r9d, [rbx+14h]
0x18001a40e  mov     r8d, [rbx+10h]
0x18001a412  lea     rdx, [rsp+1038h+var_FE8]
0x18001a417  mov     rcx, [rbx+8]
0x18001a41b  call    ?CreateProxyNode@HookBasedServerConnection@@SAJPEAUHWND__@@UInProcProxyRequest@@HH_N2PEAPEAVIUiaNode@@@Z; HookBasedServerConnection::CreateProxyNode(HWND__ *,InProcProxyRequest,int,int,bool,bool,IUiaNode * *)
0x18001a420  mov     edi, eax
0x18001a422  test    eax, eax
0x18001a424  js      loc_18001A611
0x18001a42a  mov     eax, [rbx+18h]
0x18001a42d  mov     dword ptr [rsp+1038h+var_1010], eax
0x18001a431  mov     eax, [rbx+14h]
0x18001a434  mov     [rsp+1038h+var_1018], eax; int
0x18001a438  mov     r9d, [rbx+10h]
0x18001a43c  mov     r8, [rbx]
0x18001a43f  mov     rdx, [rsp+1038h+var_FF8]
0x18001a444  call    ?AddNodeToPendingObjects@ChannelBasedServerConnectionManager@@QEAAJPEAVIUiaNode@@PEAVProviderEntryPoint@@JJW4InProcProxy@@@Z; ChannelBasedServerConnectionManager::AddNodeToPendingObjects(IUiaNode *,ProviderEntryPoint *,long,long,InProcProxy)
0x18001a449  mov     ebx, eax
0x18001a44b  test    eax, eax
0x18001a44d  js      short loc_18001A473
0x18001a44f  mov     rcx, [rsp+1038h+var_FF8]
0x18001a454  test    rcx, rcx
0x18001a457  jz      loc_18001A2E5
0x18001a45d  mov     [rsp+1038h+var_FF8], rsi
0x18001a462  mov     rax, [rcx]
0x18001a465  mov     rax, [rax+10h]
0x18001a469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a46e  jmp     loc_18001A2E5
0x18001a473  mov     rcx, [rsp+1038h]; this
0x18001a47b  mov     r9d, ebx; char *
0x18001a47e  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18001a485  mov     edx, 8C9h; void *
0x18001a48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a48f  nop
0x18001a490  mov     rcx, [rsp+1038h+var_FF8]
0x18001a495  test    rcx, rcx
0x18001a498  jz      short loc_18001A4AC
0x18001a49a  mov     [rsp+1038h+var_FF8], rsi
0x18001a49f  mov     rax, [rcx]
0x18001a4a2  mov     rax, [rax+10h]
0x18001a4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4ab  nop
0x18001a4ac  mov     eax, ebx
0x18001a4ae  jmp     loc_18001A0E0
0x18001a4b3  mov     r8, rcx
0x18001a4b6  jmp     loc_18001A1C6
0x18001a4bb  mov     [rsp+1038h+Src], si
0x18001a4c0  xorps   xmm0, xmm0
0x18001a4c3  movups  [rsp+1038h+var_FE8], xmm0
0x18001a4c8  lea     rax, [rsp+1038h+Src]
0x18001a4cd  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a4d4  mov     rbx, rdi
0x18001a4d7  nop     word ptr [rax+rax+00000000h]
0x18001a4e0  inc     rbx
0x18001a4e3  cmp     word ptr [rax+rbx*2], 0
0x18001a4e8  jnz     short loc_18001A4E0
0x18001a4ea  mov     r8, 7FFFFFFFFFFFFFFEh
0x18001a4f4  cmp     rbx, r8
0x18001a4f7  ja      loc_18001A769
0x18001a4fd  cmp     rbx, 7
0x18001a501  ja      loc_18001A776
0x18001a507  mov     [rsp+1038h+var_FD8], rbx
0x18001a50c  mov     [rsp+1038h+var_FD0], 7
0x18001a515  add     rbx, rbx
0x18001a518  mov     r8, rbx; Size
0x18001a51b  lea     rdx, [rsp+1038h+Src]; Src
0x18001a520  lea     rcx, [rsp+1038h+var_FE8]; void *
0x18001a525  call    memcpy_0
0x18001a52a  mov     word ptr [rsp+rbx+1038h+var_FE8], si
0x18001a52f  lea     rdx, [rsp+1038h+var_FE8]
0x18001a534  call    ?HasProcessedHookConnectionString@ChannelBasedServerConnectionManager@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ChannelBasedServerConnectionManager::HasProcessedHookConnectionString(std::wstring const &)
0x18001a539  movzx   ebx, al
0x18001a53c  lea     rcx, [rsp+1038h+var_FE8]
0x18001a541  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a546  test    bl, bl
0x18001a548  jnz     short loc_18001A5C4
0x18001a54a  lea     rdx, [rsp+1038h+Src]
0x18001a54f  lea     rcx, [rsp+1038h+var_FE8]
0x18001a554  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001a559  nop
0x18001a55a  lea     rdx, [rsp+1038h+var_FE8]
0x18001a55f  call    ?AddProcessedHookConnectionString@ChannelBasedServerConnectionManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ChannelBasedServerConnectionManager::AddProcessedHookConnectionString(std::wstring const &)
0x18001a564  nop
0x18001a565  lea     rcx, [rsp+1038h+var_FE8]
0x18001a56a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a56f  lea     rcx, qword_18039E090; this
0x18001a576  call    ?Init@OverlappedIOManager@@QEAAJXZ; OverlappedIOManager::Init(void)
0x18001a57b  mov     ebx, eax
0x18001a57d  test    eax, eax
0x18001a57f  js      loc_18001A651
  ... truncated ...
```

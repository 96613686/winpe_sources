# CRepubCacheBackingStore::Shutdown(void)

- ea: `0x18004e190`
- end: `0x18004e592`
- name: `?Shutdown@CRepubCacheBackingStore@@UEAAKXZ`
- size: `1026`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180004374`
- `0x180008290`
- `0x180015c28`
- `0x180018170`
- `0x18001911c`
- `0x18001f2e0`
- `0x180042a74`
- `0x18004c684`
- `0x18004e190`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e36f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e36f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e362`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e362`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e25d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e25d`
- `ESENT!JetTerm2` at `0x18004e51b`
- `ESENT!JetTerm2` at `0x18004e51b`
- `ESENT!JetStopServiceInstance` at `0x18004e464`
- `ESENT!JetStopServiceInstance` at `0x18004e464`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubCacheBackingStore::Shutdown(CRepubCacheBackingStore *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  struct _TP_TIMER *v3; // rcx
  unsigned int v4; // eax
  CHostedCacheMsgEncoding *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  _BYTE v9[56]; // [rsp+20h] [rbp-38h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 247, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v2 + 108) & 4) != 0
      && *((_BYTE *)v2 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v2 + 12), 248, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v9, (RTL_SRWLOCK *)this + 2);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 249, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  *((_DWORD *)this + 44) = 5;
  *((_BYTE *)this + 50572) = 1;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6324);
  if ( v3 )
    SetThreadpoolTimer(v3, 0, 0, 0);
  LockSentry<ReadersWriterLock,0>::Unlock(v9);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 250, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  CThreadpoolEnvironment::CleanupGroupMembers((CRepubCacheBackingStore *)((char *)this + 50712), 1);
  CThreadpoolEnvironment::CleanupGroupMembers((CRepubCacheBackingStore *)((char *)this + 50824), 1);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 251, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  ObjectHandle::Wait((CRepubCacheBackingStore *)((char *)this + 200), 0xEA60u);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 252, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  CThreadpoolEnvironment::CleanupGroupMembers((CRepubCacheBackingStore *)((char *)this + 50600), 1);
  if ( *((_QWORD *)this + 6324) )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 253, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 6324), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 6324));
    *((_QWORD *)this + 6324) = 0;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 254, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v9, (RTL_SRWLOCK *)this + 2);
  if ( *((_QWORD *)this + 27) != -1 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 255, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    v4 = CRepubCacheBackingStore::DetachAllDatabases(this);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_48;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 256, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v4);
    }
    v5 = WPP_GLOBAL_Control;
LABEL_48:
    if ( *((_BYTE *)this + 50573) )
    {
      if ( v5 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v5 + 108) & 4) != 0
        && *((_BYTE *)v5 + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)v5 + 12), 257, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      }
      v6 = JetStopServiceInstance(*((_QWORD *)this + 27));
      if ( v6
        && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 258, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v6);
      }
      LockSentry<ReadersWriterLock,0>::Unlock(v9);
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 259, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      }
      ObjectHandle::Wait((CRepubCacheBackingStore *)((char *)this + 50576), 0xFFFFFFFF);
      LockSentry<ReadersWriterLock,0>::Relock(v9);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v5 + 108) & 4) != 0
      && *((_BYTE *)v5 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v5 + 12), 260, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    v7 = JetTerm2(*((_QWORD *)this + 27), 1u);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 261, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v7);
      }
    }
    else if ( ITnoLoggingMgr::s_spLoggingMgr )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)ITnoLoggingMgr::s_spLoggingMgr + 368LL))(
        ITnoLoggingMgr::s_spLoggingMgr,
        0);
    }
    *((_QWORD *)this + 27) = -1;
  }
  LockSentry<ReadersWriterLock,0>::Unlock(v9);
  return 0;
}

```

## disassembly

```asm
0x18004e190  push    rbx
0x18004e192  push    rbp
0x18004e193  push    rsi
0x18004e194  push    rdi
0x18004e195  push    r14
0x18004e197  sub     rsp, 30h
0x18004e19b  mov     rbx, rcx
0x18004e19e  lea     rbp, WPP_GLOBAL_Control
0x18004e1a5  mov     sil, 4
0x18004e1a8  lea     r14, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004e1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1b6  cmp     rcx, rbp
0x18004e1b9  jz      short loc_18004E201
0x18004e1bb  test    [rcx+6Ch], sil
0x18004e1bf  jz      short loc_18004E1DF
0x18004e1c1  cmp     [rcx+69h], sil
0x18004e1c5  jb      short loc_18004E1DF
0x18004e1c7  mov     edx, 0F7h
0x18004e1cc  mov     r8, r14
0x18004e1cf  mov     rcx, [rcx+60h]
0x18004e1d3  call    WPP_SF_
0x18004e1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1df  cmp     rcx, rbp
0x18004e1e2  jz      short loc_18004E201
0x18004e1e4  test    [rcx+6Ch], sil
0x18004e1e8  jz      short loc_18004E201
0x18004e1ea  cmp     [rcx+69h], sil
0x18004e1ee  jb      short loc_18004E201
0x18004e1f0  mov     edx, 0F8h
0x18004e1f5  mov     r8, r14
0x18004e1f8  mov     rcx, [rcx+60h]
0x18004e1fc  call    WPP_SF_
0x18004e201  lea     rdx, [rbx+10h]
0x18004e205  lea     rcx, [rsp+58h+var_38]
0x18004e20a  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18004e20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e216  cmp     rcx, rbp
0x18004e219  jz      short loc_18004E238
0x18004e21b  test    [rcx+6Ch], sil
0x18004e21f  jz      short loc_18004E238
0x18004e221  cmp     [rcx+69h], sil
0x18004e225  jb      short loc_18004E238
0x18004e227  mov     edx, 0F9h
0x18004e22c  mov     r8, r14
0x18004e22f  mov     rcx, [rcx+60h]
0x18004e233  call    WPP_SF_
0x18004e238  mov     dword ptr [rbx+0B0h], 5
0x18004e242  mov     byte ptr [rbx+0C58Ch], 1
0x18004e249  mov     rcx, [rbx+0C5A0h]; pti
0x18004e250  test    rcx, rcx
0x18004e253  jz      short loc_18004E263
0x18004e255  xor     r9d, r9d; msWindowLength
0x18004e258  xor     r8d, r8d; msPeriod
0x18004e25b  xor     edx, edx; pftDueTime
0x18004e25d  call    cs:__imp_SetThreadpoolTimer
0x18004e263  lea     rcx, [rsp+58h+var_38]
0x18004e268  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18004e26d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e274  cmp     rcx, rbp
0x18004e277  jz      short loc_18004E296
0x18004e279  test    [rcx+6Ch], sil
0x18004e27d  jz      short loc_18004E296
0x18004e27f  cmp     [rcx+69h], sil
0x18004e283  jb      short loc_18004E296
0x18004e285  mov     edx, 0FAh
0x18004e28a  mov     r8, r14
0x18004e28d  mov     rcx, [rcx+60h]
0x18004e291  call    WPP_SF_
0x18004e296  lea     rcx, [rbx+0C618h]; this
0x18004e29d  mov     dl, 1; bool
0x18004e29f  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18004e2a4  lea     rcx, [rbx+0C688h]; this
0x18004e2ab  mov     dl, 1; bool
0x18004e2ad  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18004e2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e2b9  cmp     rcx, rbp
0x18004e2bc  jz      short loc_18004E2DB
0x18004e2be  test    [rcx+6Ch], sil
0x18004e2c2  jz      short loc_18004E2DB
0x18004e2c4  cmp     [rcx+69h], sil
0x18004e2c8  jb      short loc_18004E2DB
0x18004e2ca  mov     edx, 0FBh
0x18004e2cf  mov     r8, r14
0x18004e2d2  mov     rcx, [rcx+60h]
0x18004e2d6  call    WPP_SF_
0x18004e2db  lea     rcx, [rbx+0C8h]; this
0x18004e2e2  mov     edx, 0EA60h; unsigned int
0x18004e2e7  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x18004e2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e2f3  cmp     rcx, rbp
0x18004e2f6  jz      short loc_18004E315
0x18004e2f8  test    [rcx+6Ch], sil
0x18004e2fc  jz      short loc_18004E315
0x18004e2fe  cmp     [rcx+69h], sil
0x18004e302  jb      short loc_18004E315
0x18004e304  mov     edx, 0FCh
0x18004e309  mov     r8, r14
0x18004e30c  mov     rcx, [rcx+60h]
0x18004e310  call    WPP_SF_
0x18004e315  lea     rcx, [rbx+0C5A8h]; this
0x18004e31c  mov     dl, 1; bool
0x18004e31e  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18004e323  cmp     qword ptr [rbx+0C5A0h], 0
0x18004e32b  jz      short loc_18004E380
0x18004e32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e334  cmp     rcx, rbp
0x18004e337  jz      short loc_18004E356
0x18004e339  test    [rcx+6Ch], sil
0x18004e33d  jz      short loc_18004E356
0x18004e33f  cmp     [rcx+69h], sil
0x18004e343  jb      short loc_18004E356
0x18004e345  mov     edx, 0FDh
0x18004e34a  mov     r8, r14
0x18004e34d  mov     rcx, [rcx+60h]
0x18004e351  call    WPP_SF_
0x18004e356  mov     edx, 1; fCancelPendingCallbacks
0x18004e35b  mov     rcx, [rbx+0C5A0h]; pti
0x18004e362  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004e368  mov     rcx, [rbx+0C5A0h]; pti
0x18004e36f  call    cs:__imp_CloseThreadpoolTimer
0x18004e375  mov     qword ptr [rbx+0C5A0h], 0
0x18004e380  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e387  cmp     rcx, rbp
0x18004e38a  jz      short loc_18004E3A9
0x18004e38c  test    [rcx+6Ch], sil
0x18004e390  jz      short loc_18004E3A9
0x18004e392  cmp     [rcx+69h], sil
0x18004e396  jb      short loc_18004E3A9
0x18004e398  mov     edx, 0FEh
0x18004e39d  mov     r8, r14
0x18004e3a0  mov     rcx, [rcx+60h]
0x18004e3a4  call    WPP_SF_
0x18004e3a9  lea     rdx, [rbx+10h]
0x18004e3ad  lea     rcx, [rsp+58h+var_38]
0x18004e3b2  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18004e3b7  nop
0x18004e3b8  cmp     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x18004e3c0  jz      loc_18004E57B
0x18004e3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e3cd  cmp     rcx, rbp
0x18004e3d0  jz      short loc_18004E3EF
0x18004e3d2  test    [rcx+6Ch], sil
0x18004e3d6  jz      short loc_18004E3EF
0x18004e3d8  cmp     [rcx+69h], sil
0x18004e3dc  jb      short loc_18004E3EF
0x18004e3de  mov     edx, 0FFh
0x18004e3e3  mov     r8, r14
0x18004e3e6  mov     rcx, [rcx+60h]
0x18004e3ea  call    WPP_SF_
0x18004e3ef  mov     rcx, rbx; this
0x18004e3f2  call    ?DetachAllDatabases@CRepubCacheBackingStore@@AEAAKXZ; CRepubCacheBackingStore::DetachAllDatabases(void)
0x18004e3f7  test    eax, eax
0x18004e3f9  jz      short loc_18004E427
0x18004e3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e402  cmp     rcx, rbp
0x18004e405  jz      short loc_18004E42E
0x18004e407  test    [rcx+6Ch], sil
0x18004e40b  jz      short loc_18004E42E
0x18004e40d  cmp     byte ptr [rcx+69h], 1
0x18004e411  jb      short loc_18004E42E
0x18004e413  mov     edx, 100h
0x18004e418  mov     r9d, eax
0x18004e41b  mov     r8, r14
0x18004e41e  mov     rcx, [rcx+60h]
0x18004e422  call    WPP_SF_d
0x18004e427  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e42e  cmp     byte ptr [rbx+0C58Dh], 0
0x18004e435  jz      loc_18004E4ED
0x18004e43b  cmp     rcx, rbp
0x18004e43e  jz      short loc_18004E45D
0x18004e440  test    [rcx+6Ch], sil
0x18004e444  jz      short loc_18004E45D
0x18004e446  cmp     [rcx+69h], sil
0x18004e44a  jb      short loc_18004E45D
0x18004e44c  mov     edx, 101h
0x18004e451  mov     r8, r14
0x18004e454  mov     rcx, [rcx+60h]
0x18004e458  call    WPP_SF_
0x18004e45d  mov     rcx, [rbx+0D8h]; instance
0x18004e464  call    cs:__imp_JetStopServiceInstance
0x18004e46a  test    eax, eax
0x18004e46c  jz      short loc_18004E49A
0x18004e46e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e475  cmp     rcx, rbp
0x18004e478  jz      short loc_18004E49A
0x18004e47a  test    [rcx+6Ch], sil
0x18004e47e  jz      short loc_18004E49A
0x18004e480  cmp     byte ptr [rcx+69h], 1
0x18004e484  jb      short loc_18004E49A
0x18004e486  mov     edx, 102h
0x18004e48b  mov     r9d, eax
0x18004e48e  mov     r8, r14
0x18004e491  mov     rcx, [rcx+60h]
0x18004e495  call    WPP_SF_d
0x18004e49a  lea     rcx, [rsp+58h+var_38]
0x18004e49f  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18004e4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4ab  cmp     rcx, rbp
0x18004e4ae  jz      short loc_18004E4CD
0x18004e4b0  test    [rcx+6Ch], sil
0x18004e4b4  jz      short loc_18004E4CD
0x18004e4b6  cmp     [rcx+69h], sil
0x18004e4ba  jb      short loc_18004E4CD
0x18004e4bc  mov     edx, 103h
0x18004e4c1  mov     r8, r14
0x18004e4c4  mov     rcx, [rcx+60h]
0x18004e4c8  call    WPP_SF_
0x18004e4cd  lea     rcx, [rbx+0C590h]; this
0x18004e4d4  or      edx, 0FFFFFFFFh; unsigned int
0x18004e4d7  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x18004e4dc  lea     rcx, [rsp+58h+var_38]
0x18004e4e1  call    ?Relock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Relock(void)
0x18004e4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e4ed  cmp     rcx, rbp
0x18004e4f0  jz      short loc_18004E50F
0x18004e4f2  test    [rcx+6Ch], sil
0x18004e4f6  jz      short loc_18004E50F
0x18004e4f8  cmp     [rcx+69h], sil
0x18004e4fc  jb      short loc_18004E50F
0x18004e4fe  mov     edx, 104h
0x18004e503  mov     r8, r14
0x18004e506  mov     rcx, [rcx+60h]
0x18004e50a  call    WPP_SF_
0x18004e50f  mov     edx, 1; grbit
0x18004e514  mov     rcx, [rbx+0D8h]; instance
0x18004e51b  call    cs:__imp_JetTerm2
0x18004e521  test    eax, eax
0x18004e523  jz      short loc_18004E553
0x18004e525  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e52c  cmp     rcx, rbp
0x18004e52f  jz      short loc_18004E570
0x18004e531  test    [rcx+6Ch], sil
0x18004e535  jz      short loc_18004E570
0x18004e537  cmp     byte ptr [rcx+69h], 1
0x18004e53b  jb      short loc_18004E570
0x18004e53d  mov     edx, 105h
0x18004e542  mov     r9d, eax
0x18004e545  mov     r8, r14
0x18004e548  mov     rcx, [rcx+60h]
0x18004e54c  call    WPP_SF_d
0x18004e551  jmp     short loc_18004E570
0x18004e553  mov     rcx, cs:?s_spLoggingMgr@ITnoLoggingMgr@@0V?$auto_ptr@VITnoLoggingMgr@@@std@@A; std::auto_ptr<ITnoLoggingMgr> ITnoLoggingMgr::s_spLoggingMgr
0x18004e55a  test    rcx, rcx
0x18004e55d  jz      short loc_18004E570
0x18004e55f  xor     edx, edx
0x18004e561  mov     rax, [rcx]
0x18004e564  mov     rax, [rax+170h]
0x18004e56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e570  mov     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x18004e57b  lea     rcx, [rsp+58h+var_38]
0x18004e580  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18004e585  xor     eax, eax
0x18004e587  add     rsp, 30h
0x18004e58b  pop     r14
0x18004e58d  pop     rdi
0x18004e58e  pop     rsi
0x18004e58f  pop     rbp
0x18004e590  pop     rbx
0x18004e591  retn
```

# CPubCacheBackingStore::Shutdown(void)

- ea: `0x18005c500`
- end: `0x18005c93f`
- name: `?Shutdown@CPubCacheBackingStore@@UEAAKXZ`
- size: `1087`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x180011db0`
- `0x180015c28`
- `0x180018170`
- `0x18001911c`
- `0x18001f2e0`
- `0x18004c684`
- `0x180052888`
- `0x1800576ac`
- `0x180057cf0`
- `0x18005c500`
- `0x18005cf68`
- `0x180159010`

## import_xrefs

- `ESENT!JetTerm2` at `0x18005c832`
- `ESENT!JetTerm2` at `0x18005c832`
- `ESENT!JetStopServiceInstance` at `0x18005c77b`
- `ESENT!JetStopServiceInstance` at `0x18005c77b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPubCacheBackingStore::Shutdown(CPubCacheBackingStore *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  __int64 *v3; // rax
  __int64 *v4; // rbx
  unsigned int v5; // eax
  CHostedCacheMsgEncoding *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  CHostedCacheMsgEncoding *v10; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v13[72]; // [rsp+30h] [rbp-48h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 115, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v2 + 108) & 4) != 0
      && *((_BYTE *)v2 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v2 + 12), 116, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, (RTL_SRWLOCK *)this + 2);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 117, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  *((_DWORD *)this + 49) = 5;
  *((_BYTE *)this + 4948) = 1;
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 118, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  ObjectHandle::Wait((CPubCacheBackingStore *)((char *)this + 232), 0xEA60u);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 119, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  CThreadpoolEnvironment::CleanupGroupMembers((CPubCacheBackingStore *)((char *)this + 4968), 1u);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 120, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, (RTL_SRWLOCK *)this + 2);
  while ( *((_QWORD *)this + 636) )
  {
    std::list<unsigned short const *>::list<unsigned short const *>(v12, **((_QWORD **)this + 635) + 16LL);
    std::list<std::list<unsigned short const *>>::pop_front((char *)this + 5080);
    v3 = (__int64 *)v12[0];
    v4 = *(__int64 **)v12[0];
    while ( v4 != v3 )
    {
      operator delete((void *)v4[2]);
      v4 = (__int64 *)*v4;
      v3 = (__int64 *)v12[0];
    }
    std::list<unsigned short const *>::~list<unsigned short const *>(v12);
  }
  if ( *((_QWORD *)this + 33) != -1 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 121, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
    v5 = CPubCacheBackingStore::DetachAllDatabases(this);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_41;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 122, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v5);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_41:
    if ( *((_BYTE *)this + 4949) )
    {
      if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v6 + 108) & 4) != 0
        && *((_BYTE *)v6 + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)v6 + 12), 123, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      }
      v7 = JetStopServiceInstance(*((_QWORD *)this + 33));
      if ( v7
        && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 124, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v7);
      }
      LockSentry<ReadersWriterLock,0>::Unlock(v13);
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 125, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      }
      ObjectHandle::Wait((CPubCacheBackingStore *)((char *)this + 4952), 0xFFFFFFFF);
      LockSentry<ReadersWriterLock,0>::Relock(v13);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v6 + 108) & 4) != 0
      && *((_BYTE *)v6 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v6 + 12), 126, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
    v8 = JetTerm2(*((_QWORD *)this + 33), 1u);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 127, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v8);
      }
    }
    else if ( ITnoLoggingMgr::s_spLoggingMgr )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)ITnoLoggingMgr::s_spLoggingMgr + 368LL))(
        ITnoLoggingMgr::s_spLoggingMgr,
        0);
    }
    *((_QWORD *)this + 33) = -1;
  }
  if ( !*((_BYTE *)this + 200) )
    goto LABEL_78;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 128, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  v9 = CPubCacheBackingStore::FlushAll(this);
  if ( !v9 )
    goto LABEL_78;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_83;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 129, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v9);
LABEL_78:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 108) & 4) != 0
    && *((_BYTE *)v10 + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)v10 + 12), 130, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
LABEL_83:
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  return 0;
}

```

## disassembly

```asm
0x18005c500  push    rbx
0x18005c502  push    rbp
0x18005c503  push    rsi
0x18005c504  push    rdi
0x18005c505  push    r14
0x18005c507  push    r15
0x18005c509  sub     rsp, 48h
0x18005c50d  mov     rdi, rcx
0x18005c510  lea     r14, WPP_GLOBAL_Control
0x18005c517  mov     bpl, 4
0x18005c51a  lea     r15, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005c521  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c528  cmp     rcx, r14
0x18005c52b  jz      short loc_18005C573
0x18005c52d  test    [rcx+6Ch], bpl
0x18005c531  jz      short loc_18005C551
0x18005c533  cmp     [rcx+69h], bpl
0x18005c537  jb      short loc_18005C551
0x18005c539  mov     edx, 73h ; 's'
0x18005c53e  mov     r8, r15
0x18005c541  mov     rcx, [rcx+60h]
0x18005c545  call    WPP_SF_
0x18005c54a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c551  cmp     rcx, r14
0x18005c554  jz      short loc_18005C573
0x18005c556  test    [rcx+6Ch], bpl
0x18005c55a  jz      short loc_18005C573
0x18005c55c  cmp     [rcx+69h], bpl
0x18005c560  jb      short loc_18005C573
0x18005c562  mov     edx, 74h ; 't'
0x18005c567  mov     r8, r15
0x18005c56a  mov     rcx, [rcx+60h]
0x18005c56e  call    WPP_SF_
0x18005c573  lea     rdx, [rdi+10h]
0x18005c577  lea     rcx, [rsp+78h+var_48]
0x18005c57c  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18005c581  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c588  cmp     rcx, r14
0x18005c58b  jz      short loc_18005C5AA
0x18005c58d  test    [rcx+6Ch], bpl
0x18005c591  jz      short loc_18005C5AA
0x18005c593  cmp     [rcx+69h], bpl
0x18005c597  jb      short loc_18005C5AA
0x18005c599  mov     edx, 75h ; 'u'
0x18005c59e  mov     r8, r15
0x18005c5a1  mov     rcx, [rcx+60h]
0x18005c5a5  call    WPP_SF_
0x18005c5aa  mov     dword ptr [rdi+0C4h], 5
0x18005c5b4  mov     byte ptr [rdi+1354h], 1
0x18005c5bb  lea     rcx, [rsp+78h+var_48]
0x18005c5c0  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18005c5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5cc  cmp     rcx, r14
0x18005c5cf  jz      short loc_18005C5EE
0x18005c5d1  test    [rcx+6Ch], bpl
0x18005c5d5  jz      short loc_18005C5EE
0x18005c5d7  cmp     [rcx+69h], bpl
0x18005c5db  jb      short loc_18005C5EE
0x18005c5dd  mov     edx, 76h ; 'v'
0x18005c5e2  mov     r8, r15
0x18005c5e5  mov     rcx, [rcx+60h]
0x18005c5e9  call    WPP_SF_
0x18005c5ee  lea     rcx, [rdi+0E8h]; this
0x18005c5f5  mov     edx, 0EA60h; unsigned int
0x18005c5fa  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x18005c5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c606  cmp     rcx, r14
0x18005c609  jz      short loc_18005C628
0x18005c60b  test    [rcx+6Ch], bpl
0x18005c60f  jz      short loc_18005C628
0x18005c611  cmp     [rcx+69h], bpl
0x18005c615  jb      short loc_18005C628
0x18005c617  mov     edx, 77h ; 'w'
0x18005c61c  mov     r8, r15
0x18005c61f  mov     rcx, [rcx+60h]
0x18005c623  call    WPP_SF_
0x18005c628  lea     rcx, [rdi+1368h]; this
0x18005c62f  mov     dl, 1; bool
0x18005c631  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18005c636  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c63d  cmp     rcx, r14
0x18005c640  jz      short loc_18005C65F
0x18005c642  test    [rcx+6Ch], bpl
0x18005c646  jz      short loc_18005C65F
0x18005c648  cmp     [rcx+69h], bpl
0x18005c64c  jb      short loc_18005C65F
0x18005c64e  mov     edx, 78h ; 'x'
0x18005c653  mov     r8, r15
0x18005c656  mov     rcx, [rcx+60h]
0x18005c65a  call    WPP_SF_
0x18005c65f  lea     rdx, [rdi+10h]
0x18005c663  lea     rcx, [rsp+78h+var_48]
0x18005c668  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18005c66d  nop
0x18005c66e  cmp     qword ptr [rdi+13E0h], 0
0x18005c676  jbe     short loc_18005C6CF
0x18005c678  lea     rsi, [rdi+13D8h]
0x18005c67f  mov     rax, [rsi]
0x18005c682  mov     rdx, [rax]
0x18005c685  add     rdx, 10h
0x18005c689  lea     rcx, [rsp+78h+var_58]
0x18005c68e  call    ??0?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@AEBV01@@Z; std::list<ushort const *>::list<ushort const *>(std::list<ushort const *> const &)
0x18005c693  mov     rcx, rsi
0x18005c696  call    ?pop_front@?$list@V?$list@PEBGV?$allocator@PEBG@std@@@std@@V?$allocator@V?$list@PEBGV?$allocator@PEBG@std@@@std@@@2@@std@@QEAAXXZ; std::list<std::list<ushort const *>>::pop_front(void)
0x18005c69b  mov     rax, [rsp+78h+var_58]
0x18005c6a0  mov     rbx, [rax]
0x18005c6a3  cmp     rbx, rax
0x18005c6a6  jz      short loc_18005C6BB
0x18005c6a8  mov     rcx, [rbx+10h]; Block
0x18005c6ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c6b1  mov     rbx, [rbx]
0x18005c6b4  mov     rax, [rsp+78h+var_58]
0x18005c6b9  jmp     short loc_18005C6A3
0x18005c6bb  lea     rcx, [rsp+78h+var_58]
0x18005c6c0  call    ??1?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::list<ushort const *>::~list<ushort const *>(void)
0x18005c6c5  cmp     qword ptr [rdi+13E0h], 0
0x18005c6cd  ja      short loc_18005C67F
0x18005c6cf  cmp     qword ptr [rdi+108h], 0FFFFFFFFFFFFFFFFh
0x18005c6d7  jz      loc_18005C892
0x18005c6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c6e4  cmp     rcx, r14
0x18005c6e7  jz      short loc_18005C706
0x18005c6e9  test    [rcx+6Ch], bpl
0x18005c6ed  jz      short loc_18005C706
0x18005c6ef  cmp     [rcx+69h], bpl
0x18005c6f3  jb      short loc_18005C706
0x18005c6f5  mov     edx, 79h ; 'y'
0x18005c6fa  mov     r8, r15
0x18005c6fd  mov     rcx, [rcx+60h]
0x18005c701  call    WPP_SF_
0x18005c706  mov     rcx, rdi; this
0x18005c709  call    ?DetachAllDatabases@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::DetachAllDatabases(void)
0x18005c70e  test    eax, eax
0x18005c710  jz      short loc_18005C73E
0x18005c712  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c719  cmp     rcx, r14
0x18005c71c  jz      short loc_18005C745
0x18005c71e  test    [rcx+6Ch], bpl
0x18005c722  jz      short loc_18005C745
0x18005c724  cmp     byte ptr [rcx+69h], 1
0x18005c728  jb      short loc_18005C745
0x18005c72a  mov     edx, 7Ah ; 'z'
0x18005c72f  mov     r9d, eax
0x18005c732  mov     r8, r15
0x18005c735  mov     rcx, [rcx+60h]
0x18005c739  call    WPP_SF_d
0x18005c73e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c745  cmp     byte ptr [rdi+1355h], 0
0x18005c74c  jz      loc_18005C804
0x18005c752  cmp     rcx, r14
0x18005c755  jz      short loc_18005C774
0x18005c757  test    [rcx+6Ch], bpl
0x18005c75b  jz      short loc_18005C774
0x18005c75d  cmp     [rcx+69h], bpl
0x18005c761  jb      short loc_18005C774
0x18005c763  mov     edx, 7Bh ; '{'
0x18005c768  mov     r8, r15
0x18005c76b  mov     rcx, [rcx+60h]
0x18005c76f  call    WPP_SF_
0x18005c774  mov     rcx, [rdi+108h]; instance
0x18005c77b  call    cs:__imp_JetStopServiceInstance
0x18005c781  test    eax, eax
0x18005c783  jz      short loc_18005C7B1
0x18005c785  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c78c  cmp     rcx, r14
0x18005c78f  jz      short loc_18005C7B1
0x18005c791  test    [rcx+6Ch], bpl
0x18005c795  jz      short loc_18005C7B1
0x18005c797  cmp     byte ptr [rcx+69h], 1
0x18005c79b  jb      short loc_18005C7B1
0x18005c79d  mov     edx, 7Ch ; '|'
0x18005c7a2  mov     r9d, eax
0x18005c7a5  mov     r8, r15
0x18005c7a8  mov     rcx, [rcx+60h]
0x18005c7ac  call    WPP_SF_d
0x18005c7b1  lea     rcx, [rsp+78h+var_48]
0x18005c7b6  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18005c7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7c2  cmp     rcx, r14
0x18005c7c5  jz      short loc_18005C7E4
0x18005c7c7  test    [rcx+6Ch], bpl
0x18005c7cb  jz      short loc_18005C7E4
0x18005c7cd  cmp     [rcx+69h], bpl
0x18005c7d1  jb      short loc_18005C7E4
0x18005c7d3  mov     edx, 7Dh ; '}'
0x18005c7d8  mov     r8, r15
0x18005c7db  mov     rcx, [rcx+60h]
0x18005c7df  call    WPP_SF_
0x18005c7e4  lea     rcx, [rdi+1358h]; this
0x18005c7eb  or      edx, 0FFFFFFFFh; unsigned int
0x18005c7ee  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x18005c7f3  lea     rcx, [rsp+78h+var_48]
0x18005c7f8  call    ?Relock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Relock(void)
0x18005c7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c804  cmp     rcx, r14
0x18005c807  jz      short loc_18005C826
0x18005c809  test    [rcx+6Ch], bpl
0x18005c80d  jz      short loc_18005C826
0x18005c80f  cmp     [rcx+69h], bpl
0x18005c813  jb      short loc_18005C826
0x18005c815  mov     edx, 7Eh ; '~'
0x18005c81a  mov     r8, r15
0x18005c81d  mov     rcx, [rcx+60h]
0x18005c821  call    WPP_SF_
0x18005c826  mov     edx, 1; grbit
0x18005c82b  mov     rcx, [rdi+108h]; instance
0x18005c832  call    cs:__imp_JetTerm2
0x18005c838  test    eax, eax
0x18005c83a  jz      short loc_18005C86A
0x18005c83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c843  cmp     rcx, r14
0x18005c846  jz      short loc_18005C887
0x18005c848  test    [rcx+6Ch], bpl
0x18005c84c  jz      short loc_18005C887
0x18005c84e  cmp     byte ptr [rcx+69h], 1
0x18005c852  jb      short loc_18005C887
0x18005c854  mov     edx, 7Fh
0x18005c859  mov     r9d, eax
0x18005c85c  mov     r8, r15
0x18005c85f  mov     rcx, [rcx+60h]
0x18005c863  call    WPP_SF_d
0x18005c868  jmp     short loc_18005C887
0x18005c86a  mov     rcx, cs:?s_spLoggingMgr@ITnoLoggingMgr@@0V?$auto_ptr@VITnoLoggingMgr@@@std@@A; std::auto_ptr<ITnoLoggingMgr> ITnoLoggingMgr::s_spLoggingMgr
0x18005c871  test    rcx, rcx
0x18005c874  jz      short loc_18005C887
0x18005c876  xor     edx, edx
0x18005c878  mov     rax, [rcx]
0x18005c87b  mov     rax, [rax+170h]
0x18005c882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c887  mov     qword ptr [rdi+108h], 0FFFFFFFFFFFFFFFFh
0x18005c892  cmp     byte ptr [rdi+0C8h], 0
0x18005c899  jz      short loc_18005C8FC
0x18005c89b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c8a2  cmp     rcx, r14
0x18005c8a5  jz      short loc_18005C8C4
0x18005c8a7  test    [rcx+6Ch], bpl
0x18005c8ab  jz      short loc_18005C8C4
0x18005c8ad  cmp     [rcx+69h], bpl
0x18005c8b1  jb      short loc_18005C8C4
0x18005c8b3  mov     edx, 80h
0x18005c8b8  mov     r8, r15
0x18005c8bb  mov     rcx, [rcx+60h]
0x18005c8bf  call    WPP_SF_
0x18005c8c4  mov     rcx, rdi; this
0x18005c8c7  call    ?FlushAll@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::FlushAll(void)
0x18005c8cc  test    eax, eax
0x18005c8ce  jz      short loc_18005C8FC
0x18005c8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c8d7  cmp     rcx, r14
0x18005c8da  jz      short loc_18005C926
0x18005c8dc  test    [rcx+6Ch], bpl
0x18005c8e0  jz      short loc_18005C903
0x18005c8e2  cmp     byte ptr [rcx+69h], 1
0x18005c8e6  jb      short loc_18005C903
0x18005c8e8  mov     edx, 81h
0x18005c8ed  mov     r9d, eax
0x18005c8f0  mov     r8, r15
0x18005c8f3  mov     rcx, [rcx+60h]
0x18005c8f7  call    WPP_SF_d
0x18005c8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c903  cmp     rcx, r14
0x18005c906  jz      short loc_18005C926
0x18005c908  test    [rcx+6Ch], bpl
0x18005c90c  jz      short loc_18005C926
0x18005c90e  cmp     [rcx+69h], bpl
0x18005c912  jb      short loc_18005C926
0x18005c914  mov     edx, 82h
0x18005c919  mov     r8, r15
0x18005c91c  mov     rcx, [rcx+60h]
0x18005c920  call    WPP_SF_
0x18005c925  nop
0x18005c926  lea     rcx, [rsp+78h+var_48]
0x18005c92b  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18005c930  xor     eax, eax
0x18005c932  add     rsp, 48h
0x18005c936  pop     r15
0x18005c938  pop     r14
0x18005c93a  pop     rdi
0x18005c93b  pop     rsi
0x18005c93c  pop     rbp
0x18005c93d  pop     rbx
0x18005c93e  retn
```

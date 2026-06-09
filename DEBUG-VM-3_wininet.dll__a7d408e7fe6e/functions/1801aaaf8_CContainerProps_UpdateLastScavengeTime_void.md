# CContainerProps::UpdateLastScavengeTime(void)

- ea: `0x1801aaaf8`
- end: `0x1801aad3a`
- name: `?UpdateLastScavengeTime@CContainerProps@@QEAAJXZ`
- size: `578`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801ad900`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180086300`
- `0x180097e10`
- `0x1800e28e0`
- `0x1800eed94`
- `0x1800fa844`
- `0x18012ad34`
- `0x18014a7a0`
- `0x1801aaaf8`
- `0x1801e1790`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801aab6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801aab6b`
- `ESENT!JetCommitTransaction` at `0x1801aad11`
- `ESENT!JetCommitTransaction` at `0x1801aad11`
- `ESENT!JetUpdate` at `0x1801aacf6`
- `ESENT!JetUpdate` at `0x1801aacf6`
- `ESENT!JetPrepareUpdate` at `0x1801aac8c`
- `ESENT!JetPrepareUpdate` at `0x1801aacd4`
- `ESENT!JetPrepareUpdate` at `0x1801aac8c`
- `ESENT!JetPrepareUpdate` at `0x1801aacd4`
- `ESENT!JetRollback` at `0x1801aac61`
- `ESENT!JetRollback` at `0x1801aac61`
- `ESENT!JetBeginTransaction` at `0x1801aac22`
- `ESENT!JetBeginTransaction` at `0x1801aac22`

## pseudocode

```c
__int64 __fastcall CContainerProps::UpdateLastScavengeTime(CContainerProps *this)
{
  int v2; // eax
  unsigned int v3; // r9d
  int v4; // ebx
  unsigned int v5; // edi
  JET_SESID *v7; // rsi
  JET_ERR v8; // eax
  int v9; // eax
  JET_ERR v10; // eax
  JET_ERR v11; // eax
  JET_ERR v12; // eax
  CJetContext *v13; // [rsp+38h] [rbp-28h] BYREF
  char *v14; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-10h] BYREF

  v14 = (char *)this + 32;
  v13 = 0;
  v15 = 0;
  SystemTimeAsFileTime = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 27, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, this);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  AutoCritSec::Lock((AutoCritSec *)&v14);
  v2 = CCacheStore::AcquireContainerContext(*((CCacheStore **)this + 3), &v13);
  v4 = v2;
  if ( v2 < 0
    || (v7 = (JET_SESID *)v13, v2 = CJetContext::SetCurrentIndex(v13, 0, L"ContainerIdIndex", v3), v4 = v2, v2 < 0)
    || (v8 = JetBeginTransaction(v7[2]), v2 = HRESULTFromJET_ERR(v8, 1), v4 = v2, v2 < 0) )
  {
    v5 = v2;
    goto LABEL_5;
  }
  v9 = SeekToContainer((struct CJetContext *)v7, *((_QWORD *)this + 1));
  v4 = v9;
  if ( v9 < 0 )
    goto LABEL_13;
  if ( v9 )
  {
    v4 = -2147418113;
    goto LABEL_17;
  }
  v10 = JetPrepareUpdate(v7[2], v7[4], 2u);
  v9 = HRESULTFromJET_ERR(v10, 1);
  v4 = v9;
  if ( v9 < 0 )
  {
LABEL_13:
    v5 = v9;
LABEL_14:
    JetRollback(v7[2], 0);
    goto LABEL_5;
  }
  v4 = CJetContext::SetBasicColumn((CJetContext *)v7, 0xBu, &SystemTimeAsFileTime, 8u);
  if ( v4 < 0 || (v11 = JetUpdate(v7[2], v7[4], 0, 0, 0), v4 = HRESULTFromJET_ERR(v11, 1), v4 < 0) )
  {
    v5 = v4;
    JetPrepareUpdate(v7[2], v7[4], 3u);
    goto LABEL_14;
  }
  v12 = JetCommitTransaction(v7[2], 1u);
  v4 = HRESULTFromJET_ERR(v12, 1);
  if ( v4 < 0 )
  {
LABEL_17:
    v5 = v4;
    goto LABEL_14;
  }
  AutoCritSec::Unlock((AutoCritSec *)&v14);
  v5 = v4;
LABEL_5:
  CCacheStore::ReleaseContainerContext(*((CCacheStore **)this + 3), &v13);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 28, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v4);
  if ( (_DWORD)v15 )
    AutoCritSec::Unlock((AutoCritSec *)&v14);
  return v5;
}

```

## disassembly

```asm
0x1801aaaf8  mov     [rsp-18h+arg_8], rbx
0x1801aaafd  mov     [rsp-18h+arg_10], rsi
0x1801aab02  push    rbp
0x1801aab03  push    rdi
0x1801aab04  push    r14
0x1801aab06  mov     rbp, rsp
0x1801aab09  sub     rsp, 60h
0x1801aab0d  mov     rax, cs:__security_cookie
0x1801aab14  xor     rax, rsp
0x1801aab17  mov     [rbp+var_8], rax
0x1801aab1b  lea     rax, [rcx+20h]
0x1801aab1f  mov     [rbp+var_2C], 0
0x1801aab26  mov     [rbp+var_20], rax
0x1801aab2a  mov     r14, rcx
0x1801aab2d  mov     [rbp+var_28], 0
0x1801aab35  mov     [rbp+var_18], 0
0x1801aab3d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801aab45  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aab4c  jz      short loc_1801AAB67
0x1801aab4e  mov     edx, 1Bh
0x1801aab53  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aab5a  mov     ecx, 40Ch
0x1801aab5f  mov     r9, r14
0x1801aab62  call    WPP_SF_q
0x1801aab67  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801aab6b  call    cs:__imp_GetSystemTimeAsFileTime
0x1801aab71  lea     rcx, [rbp+var_20]; this
0x1801aab75  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1801aab7a  mov     rcx, [r14+18h]; this
0x1801aab7e  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801aab82  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x1801aab87  mov     ebx, eax
0x1801aab89  test    eax, eax
0x1801aab8b  jns     short loc_1801AABF7
0x1801aab8d  mov     [rbp+var_2C], 328h
0x1801aab94  mov     edi, eax
0x1801aab96  mov     rcx, [r14+18h]; this
0x1801aab9a  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801aab9e  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1801aaba3  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aabaa  jz      short loc_1801AABC5
0x1801aabac  mov     edx, 1Ch
0x1801aabb1  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aabb8  mov     ecx, 40Ch
0x1801aabbd  mov     r9d, ebx
0x1801aabc0  call    WPP_SF_d
0x1801aabc5  cmp     dword ptr [rbp+var_18], 0
0x1801aabc9  jz      short loc_1801AABD4
0x1801aabcb  lea     rcx, [rbp+var_20]; this
0x1801aabcf  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aabd4  mov     eax, edi
0x1801aabd6  mov     rcx, [rbp+var_8]
0x1801aabda  xor     rcx, rsp; StackCookie
0x1801aabdd  call    __security_check_cookie
0x1801aabe2  lea     r11, [rsp+60h+var_s0]
0x1801aabe7  mov     rbx, [r11+28h]
0x1801aabeb  mov     rsi, [r11+30h]
0x1801aabef  mov     rsp, r11
0x1801aabf2  pop     r14
0x1801aabf4  pop     rdi
0x1801aabf5  pop     rbp
0x1801aabf6  retn
0x1801aabf7  mov     rsi, [rbp+var_28]
0x1801aabfb  lea     r8, aContaineridind; "ContainerIdIndex"
0x1801aac02  mov     rcx, rsi; this
0x1801aac05  xor     edx, edx; unsigned int
0x1801aac07  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801aac0c  mov     ebx, eax
0x1801aac0e  test    eax, eax
0x1801aac10  jns     short loc_1801AAC1E
0x1801aac12  mov     [rbp+var_2C], 32Ch
0x1801aac19  jmp     loc_1801AAB94
0x1801aac1e  mov     rcx, [rsi+10h]; sesid
0x1801aac22  call    cs:__imp_JetBeginTransaction
0x1801aac28  mov     edi, 1
0x1801aac2d  mov     ecx, eax; int
0x1801aac2f  mov     edx, edi; int
0x1801aac31  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aac36  mov     ebx, eax
0x1801aac38  test    eax, eax
0x1801aac3a  js      loc_1801AAB94
0x1801aac40  mov     rdx, [r14+8]; unsigned __int64
0x1801aac44  mov     rcx, rsi; struct CJetContext *
0x1801aac47  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1801aac4c  mov     ebx, eax
0x1801aac4e  test    eax, eax
0x1801aac50  jns     short loc_1801AAC6C
0x1801aac52  mov     [rbp+var_2C], 336h
0x1801aac59  mov     edi, eax
0x1801aac5b  mov     rcx, [rsi+10h]; sesid
0x1801aac5f  xor     edx, edx; grbit
0x1801aac61  call    cs:__imp_JetRollback
0x1801aac67  jmp     loc_1801AAB96
0x1801aac6c  jz      short loc_1801AAC7E
0x1801aac6e  mov     ebx, 8000FFFFh
0x1801aac73  mov     [rbp+var_2C], 338h
0x1801aac7a  mov     edi, ebx
0x1801aac7c  jmp     short loc_1801AAC5B
0x1801aac7e  mov     rdx, [rsi+20h]; tableid
0x1801aac82  mov     r8d, 2; prep
0x1801aac88  mov     rcx, [rsi+10h]; sesid
0x1801aac8c  call    cs:__imp_JetPrepareUpdate
0x1801aac92  mov     ecx, eax; int
0x1801aac94  mov     edx, edi; int
0x1801aac96  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aac9b  mov     ebx, eax
0x1801aac9d  test    eax, eax
0x1801aac9f  js      short loc_1801AAC59
0x1801aaca1  mov     r9d, 8; unsigned int
0x1801aaca7  lea     r8, [rbp+SystemTimeAsFileTime]; void *
0x1801aacab  mov     rcx, rsi; this
0x1801aacae  lea     edx, [r9+3]; unsigned int
0x1801aacb2  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801aacb7  mov     ebx, eax
0x1801aacb9  test    eax, eax
0x1801aacbb  jns     short loc_1801AACDF
0x1801aacbd  mov     [rbp+var_2C], 341h
0x1801aacc4  mov     rdx, [rsi+20h]; tableid
0x1801aacc8  mov     r8d, 3; prep
0x1801aacce  mov     rcx, [rsi+10h]; sesid
0x1801aacd2  mov     edi, ebx
0x1801aacd4  call    cs:__imp_JetPrepareUpdate
0x1801aacda  jmp     loc_1801AAC5B
0x1801aacdf  mov     rdx, [rsi+20h]; tableid
0x1801aace3  xor     r9d, r9d; cbBookmark
0x1801aace6  mov     rcx, [rsi+10h]; sesid
0x1801aacea  xor     r8d, r8d; pvBookmark
0x1801aaced  mov     [rsp+60h+pcbActual], 0; pcbActual
0x1801aacf6  call    cs:__imp_JetUpdate
0x1801aacfc  mov     ecx, eax; int
0x1801aacfe  mov     edx, edi; int
0x1801aad00  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aad05  mov     ebx, eax
0x1801aad07  test    eax, eax
0x1801aad09  js      short loc_1801AACC4
0x1801aad0b  mov     rcx, [rsi+10h]; sesid
0x1801aad0f  mov     edx, edi; grbit
0x1801aad11  call    cs:__imp_JetCommitTransaction
0x1801aad17  mov     ecx, eax; int
0x1801aad19  mov     edx, edi; int
0x1801aad1b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aad20  mov     ebx, eax
0x1801aad22  test    eax, eax
0x1801aad24  js      loc_1801AAC7A
0x1801aad2a  lea     rcx, [rbp+var_20]; this
0x1801aad2e  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aad33  mov     edi, ebx
0x1801aad35  jmp     loc_1801AAB96
```

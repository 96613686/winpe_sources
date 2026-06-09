# CReader::TransactionTimeoutCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18002e7c0`
- end: `0x18002eb36`
- name: `?TransactionTimeoutCallback@CReader@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `886`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180001900`
- `0x18000278c`
- `0x1800075d0`
- `0x18000f800`
- `0x180010af0`
- `0x180012380`
- `0x1800123a0`
- `0x18001364c`
- `0x180014d30`
- `0x1800153f0`
- `0x180015558`
- `0x180017118`
- `0x180028b78`
- `0x180029d68`
- `0x18002e7c0`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e861`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e861`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReader::TransactionTimeoutCallback(PTP_CALLBACK_INSTANCE Instance, CReader *Context, PTP_TIMER Timer)
{
  CReader *v4; // rbx
  CReader *v5; // r13
  const struct CReader::ActiveState *v6; // rdx
  __int64 v7; // rcx
  CMutex *v8; // r12
  __int64 v9; // rcx
  CMutex *v10; // rbx
  __int64 v11; // rcx
  const unsigned __int8 *v12; // r8
  const unsigned __int8 *v13; // r9
  unsigned int v14; // r15d
  unsigned int v15; // esi
  unsigned int v16; // edx
  __int64 v17; // r15
  __int64 v18; // rcx
  const unsigned __int8 *v19; // rcx
  unsigned __int16 *v20; // rax
  __int64 v21; // rcx
  CReader *v22; // rbx
  const void *v23; // [rsp+20h] [rbp-C8h]
  unsigned int v24; // [rsp+28h] [rbp-C0h]
  _BYTE v25[8]; // [rsp+30h] [rbp-B8h] BYREF
  CReader *v26; // [rsp+38h] [rbp-B0h]
  ulong v27; // [rsp+40h] [rbp-A8h] BYREF
  CReader *v28; // [rsp+48h] [rbp-A0h]
  unsigned __int16 *v29[4]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 v30[16]; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int16 v31[16]; // [rsp+90h] [rbp-58h] BYREF

  v4 = Context;
  v28 = Context;
  v26 = Context;
  v5 = Context;
  WppTraceIndent(Instance, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
  }
  CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
  SetThreadpoolTimer(Timer, 0, 0, 0);
  if ( v4 )
  {
    try
    {
      try
      {
        CReader::TryLatchReader(v4, v6);
      }
      catch ( ulong v27 )
      {
        if ( v27 != 1460 )
          throw;
        v4 = v28;
        v5 = v28;
      }
      v8 = (CReader *)((char *)v4 + 328);
      if ( (unsigned int)CMutex::IsGrabbedByMe((CReader *)((char *)v4 + 328)) )
      {
        v10 = (CReader *)((char *)v4 + 240);
        if ( (unsigned int)CMutex::IsGrabbed(v10) )
        {
          memset(v31, 0, 30);
          memset(v30, 0, 30);
          v14 = 0;
          COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)v25, qword_18004BA60, v12, v13);
          v15 = 0;
          v16 = HIDWORD(qword_18004B0A8);
          while ( v15 < v16 )
          {
            v17 = *((_QWORD *)Block + (int)v15);
            if ( v17 )
            {
              if ( (unsigned int)CMutex::IsGrabbedBy(v10, *(void **)(v17 + 72)) )
              {
                v14 = *(_DWORD *)(v17 + 168);
                break;
              }
              v16 = HIDWORD(qword_18004B0A8);
            }
            v14 = 0;
            ++v15;
          }
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v25);
          StringCchPrintfW(v31, 0xFu, L"%i", v14);
          StringCchPrintfW(v30, 0xFu, L"%i", g_dwTransactionTimeoutDelay);
          WppTraceIndent(v18, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
              WPP_pszIndent);
          }
          CMutex::Take(v10, 0);
          CReader::Dispose(v26, 1);
          v20 = (unsigned __int16 *)&Data;
          if ( *((_DWORD *)v5 + 7) )
            v20 = (unsigned __int16 *)*((_QWORD *)v5 + 2);
          v29[0] = v20;
          v29[1] = v30;
          v29[2] = v31;
          v29[3] = 0;
          CalaisMessageLog(v19, 2u, 0x26Fu, (const unsigned __int16 **)v29, v23, v24);
        }
        else
        {
          WppTraceIndent(v11, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
              WPP_pszIndent);
          }
        }
      }
      else
      {
        WppTraceIndent(v9, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
            WPP_pszIndent);
        }
        v10 = (CReader *)((char *)v4 + 240);
      }
      if ( (unsigned int)CMutex::IsGrabbedByMe(v8) )
        CMutex::Share(v8);
      if ( (unsigned int)CMutex::IsGrabbedByMe(v10) )
        CMutex::Share(v10);
    }
    catch ( ... )
    {
      WppTraceIndent(v21, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
          WPP_pszIndent);
      }
      v22 = v26;
      if ( (unsigned int)CMutex::IsGrabbedByMe((CReader *)((char *)v26 + 328)) )
        CMutex::Share((CReader *)((char *)v22 + 328));
      if ( (unsigned int)CMutex::IsGrabbedByMe((CReader *)((char *)v22 + 240)) )
        CMutex::Share((CReader *)((char *)v22 + 240));
    }
  }
  else
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
  }
}

```

## disassembly

```asm
0x18002e7c0  mov     [rsp+arg_0], rbx
0x18002e7c5  push    rsi
0x18002e7c6  push    r12
0x18002e7c8  push    r13
0x18002e7ca  push    r14
0x18002e7cc  push    r15
0x18002e7ce  sub     rsp, 0C0h
0x18002e7d5  mov     rax, cs:__security_cookie
0x18002e7dc  xor     rax, rsp
0x18002e7df  mov     [rsp+0E8h+var_38], rax
0x18002e7e7  mov     rsi, r8
0x18002e7ea  mov     rbx, rdx
0x18002e7ed  mov     [rsp+0E8h+var_A0], rdx
0x18002e7f2  mov     [rsp+0E8h+var_B0], rdx
0x18002e7f7  mov     r13, rdx
0x18002e7fa  mov     edx, 2
0x18002e7ff  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e804  lea     r14, WPP_GLOBAL_Control
0x18002e80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e812  cmp     rcx, r14
0x18002e815  jz      short loc_18002E83F
0x18002e817  test    byte ptr [rcx+1Ch], 10h
0x18002e81b  jz      short loc_18002E83F
0x18002e81d  cmp     byte ptr [rcx+19h], 4
0x18002e821  jb      short loc_18002E83F
0x18002e823  mov     edx, 19h
0x18002e828  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e82f  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18002e836  mov     rcx, [rcx+10h]
0x18002e83a  call    WPP_SF_s
0x18002e83f  mov     eax, 1
0x18002e844  lock xadd cs:dword_18004BF90, eax
0x18002e84c  inc     eax
0x18002e84e  movsxd  rcx, eax; lpTlsValue
0x18002e851  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x18002e856  xor     r9d, r9d; msWindowLength
0x18002e859  xor     r8d, r8d; msPeriod
0x18002e85c  xor     edx, edx; pftDueTime
0x18002e85e  mov     rcx, rsi; pti
0x18002e861  call    cs:__imp_SetThreadpoolTimer
0x18002e867  test    rbx, rbx
0x18002e86a  jz      loc_18002EACF
0x18002e870  mov     rcx, rbx; this
0x18002e873  call    ?TryLatchReader@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::TryLatchReader(CReader::ActiveState const *)
0x18002e878  nop
0x18002e879  jmp     short loc_18002E88A
0x18002e87b  lea     r14, WPP_GLOBAL_Control
0x18002e882  mov     rbx, [rsp+0E8h+var_A0]
0x18002e887  mov     r13, rbx
0x18002e88a  lea     r12, [rbx+148h]
0x18002e891  mov     rcx, r12; this
0x18002e894  call    ?IsGrabbedByMe@CMutex@@QEAAHXZ; CMutex::IsGrabbedByMe(void)
0x18002e899  test    eax, eax
0x18002e89b  jnz     short loc_18002E8E5
0x18002e89d  lea     edx, [rax+2]
0x18002e8a0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8ac  cmp     rcx, r14
0x18002e8af  jz      short loc_18002E8D9
0x18002e8b1  test    byte ptr [rcx+1Ch], 10h
0x18002e8b5  jz      short loc_18002E8D9
0x18002e8b7  cmp     byte ptr [rcx+19h], 4
0x18002e8bb  jb      short loc_18002E8D9
0x18002e8bd  mov     edx, 1Ah
0x18002e8c2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e8c9  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18002e8d0  mov     rcx, [rcx+10h]
0x18002e8d4  call    WPP_SF_s
0x18002e8d9  add     rbx, 0F0h
0x18002e8e0  jmp     loc_18002EAA2
0x18002e8e5  add     rbx, 0F0h
0x18002e8ec  mov     rcx, rbx; this
0x18002e8ef  call    ?IsGrabbed@CMutex@@QEAAHXZ; CMutex::IsGrabbed(void)
0x18002e8f4  test    eax, eax
0x18002e8f6  jz      loc_18002EA64
0x18002e8fc  xorps   xmm0, xmm0
0x18002e8ff  xor     eax, eax
0x18002e901  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x18002e909  movups  xmmword ptr [rsp+0E8h+var_58+0Eh], xmm0
0x18002e911  xorps   xmm1, xmm1
0x18002e914  movups  xmmword ptr [rsp+0E8h+var_78], xmm1
0x18002e919  movups  xmmword ptr [rsp+0E8h+var_78+0Eh], xmm1
0x18002e91e  xor     r15d, r15d
0x18002e921  mov     rdx, cs:qword_18004BA60; struct CCriticalSectionObject *
0x18002e928  lea     rcx, [rsp+0E8h+var_B8]; this
0x18002e92d  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002e932  nop
0x18002e933  xor     esi, esi
0x18002e935  mov     edx, dword ptr cs:qword_18004B0A8+4
0x18002e93b  cmp     esi, edx
0x18002e93d  jnb     short loc_18002E971
0x18002e93f  movsxd  rcx, esi
0x18002e942  mov     rax, cs:Block
0x18002e949  mov     r15, [rax+rcx*8]
0x18002e94d  test    r15, r15
0x18002e950  jz      loc_18002EA5A
0x18002e956  mov     rdx, [r15+48h]; void *
0x18002e95a  mov     rcx, rbx; this
0x18002e95d  call    ?IsGrabbedBy@CMutex@@QEAAHPEAX@Z; CMutex::IsGrabbedBy(void *)
0x18002e962  test    eax, eax
0x18002e964  jz      loc_18002EA54
0x18002e96a  mov     r15d, [r15+0A8h]
0x18002e971  lea     rcx, [rsp+0E8h+var_B8]; this
0x18002e976  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002e97b  mov     r9d, r15d
0x18002e97e  lea     r8, aI; "%i"
0x18002e985  mov     esi, 0Fh
0x18002e98a  mov     edx, esi; unsigned __int64
0x18002e98c  lea     rcx, [rsp+0E8h+var_58]; unsigned __int16 *
0x18002e994  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e999  mov     r9d, cs:?g_dwTransactionTimeoutDelay@@3KA; ulong g_dwTransactionTimeoutDelay
0x18002e9a0  lea     r8, aI; "%i"
0x18002e9a7  mov     edx, esi; unsigned __int64
0x18002e9a9  lea     rcx, [rsp+0E8h+var_78]; unsigned __int16 *
0x18002e9ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e9b3  lea     edx, [rsi-0Dh]
0x18002e9b6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e9bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9c2  cmp     rcx, r14
0x18002e9c5  jz      short loc_18002E9ED
0x18002e9c7  test    byte ptr [rcx+1Ch], 10h
0x18002e9cb  jz      short loc_18002E9ED
0x18002e9cd  cmp     byte ptr [rcx+19h], 4
0x18002e9d1  jb      short loc_18002E9ED
0x18002e9d3  lea     edx, [rsi+0Ch]
0x18002e9d6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e9dd  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18002e9e4  mov     rcx, [rcx+10h]
0x18002e9e8  call    WPP_SF_s
0x18002e9ed  xor     edx, edx; bool
0x18002e9ef  mov     rcx, rbx; this
0x18002e9f2  call    ?Take@CMutex@@QEAAX_N@Z; CMutex::Take(bool)
0x18002e9f7  mov     edx, 1; unsigned int
0x18002e9fc  mov     rcx, [rsp+0E8h+var_B0]; this
0x18002ea01  call    ?Dispose@CReader@@IEAAXK@Z; CReader::Dispose(ulong)
0x18002ea06  cmp     dword ptr [r13+1Ch], 0
0x18002ea0b  lea     rax, Data
0x18002ea12  jbe     short loc_18002EA18
0x18002ea14  mov     rax, [r13+10h]
0x18002ea18  mov     [rsp+0E8h+var_98], rax
0x18002ea1d  lea     rax, [rsp+0E8h+var_78]
0x18002ea22  mov     [rsp+0E8h+var_90], rax
0x18002ea27  lea     rax, [rsp+0E8h+var_58]
0x18002ea2f  mov     [rsp+0E8h+var_88], rax
0x18002ea34  mov     [rsp+0E8h+var_80], 0
0x18002ea3d  mov     edx, 2; unsigned __int16
0x18002ea42  lea     r9, [rsp+0E8h+var_98]; unsigned __int16 **
0x18002ea47  mov     r8d, 26Fh; unsigned int
0x18002ea4d  call    ?CalaisMessageLog@@YAXPEBEGKPEAPEBGPEBXK@Z; CalaisMessageLog(uchar const *,ushort,ulong,ushort const * *,void const *,ulong)
0x18002ea52  jmp     short loc_18002EAA2
0x18002ea54  mov     edx, dword ptr cs:qword_18004B0A8+4
0x18002ea5a  xor     r15d, r15d
0x18002ea5d  inc     esi
0x18002ea5f  jmp     loc_18002E93B
0x18002ea64  mov     edx, 2
0x18002ea69  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ea6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea75  cmp     rcx, r14
0x18002ea78  jz      short loc_18002EAA2
0x18002ea7a  test    byte ptr [rcx+1Ch], 10h
0x18002ea7e  jz      short loc_18002EAA2
0x18002ea80  cmp     byte ptr [rcx+19h], 4
0x18002ea84  jb      short loc_18002EAA2
0x18002ea86  mov     edx, 1Ch
0x18002ea8b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002ea92  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18002ea99  mov     rcx, [rcx+10h]
0x18002ea9d  call    WPP_SF_s
0x18002eaa2  mov     rcx, r12; this
0x18002eaa5  call    ?IsGrabbedByMe@CMutex@@QEAAHXZ; CMutex::IsGrabbedByMe(void)
0x18002eaaa  test    eax, eax
0x18002eaac  jz      short loc_18002EAB6
0x18002eaae  mov     rcx, r12; this
0x18002eab1  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18002eab6  mov     rcx, rbx; this
0x18002eab9  call    ?IsGrabbedByMe@CMutex@@QEAAHXZ; CMutex::IsGrabbedByMe(void)
0x18002eabe  test    eax, eax
0x18002eac0  jz      short loc_18002EACB
0x18002eac2  mov     rcx, rbx; this
0x18002eac5  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18002eaca  nop
0x18002eacb  jmp     short loc_18002EB0D
0x18002eacd  jmp     short loc_18002EB0D
0x18002eacf  mov     edx, 2
0x18002ead4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ead9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eae0  cmp     rcx, r14
0x18002eae3  jz      short loc_18002EB0D
0x18002eae5  test    byte ptr [rcx+1Ch], 10h
0x18002eae9  jz      short loc_18002EB0D
0x18002eaeb  cmp     byte ptr [rcx+19h], 4
0x18002eaef  jb      short loc_18002EB0D
0x18002eaf1  mov     edx, 1Eh
0x18002eaf6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002eafd  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18002eb04  mov     rcx, [rcx+10h]
0x18002eb08  call    WPP_SF_s
0x18002eb0d  mov     rcx, [rsp+0E8h+var_38]
0x18002eb15  xor     rcx, rsp; StackCookie
0x18002eb18  call    __security_check_cookie
0x18002eb1d  mov     rbx, [rsp+0E8h+arg_0]
0x18002eb25  add     rsp, 0C0h
0x18002eb2c  pop     r15
0x18002eb2e  pop     r14
0x18002eb30  pop     r13
0x18002eb32  pop     r12
0x18002eb34  pop     rsi
0x18002eb35  retn
```

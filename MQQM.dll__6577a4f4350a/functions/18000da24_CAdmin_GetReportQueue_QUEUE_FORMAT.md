# CAdmin::GetReportQueue(QUEUE_FORMAT *)

- ea: `0x18000da24`
- end: `0x18000dc72`
- name: `?GetReportQueue@CAdmin@@QEAAJPEAUQUEUE_FORMAT@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(CAdmin *__hidden this, struct QUEUE_FORMAT *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180008f44`
- `0x180056568`
- `0x180058970`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18000da24`
- `0x180017e5c`
- `0x18002c61c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18000db8a`
- `msvcrt!free` at `0x18000dbb1`
- `msvcrt!free` at `0x18000dbbd`
- `msvcrt!free` at `0x18000dbcc`
- `msvcrt!free` at `0x18000db8a`
- `msvcrt!free` at `0x18000dbb1`
- `msvcrt!free` at `0x18000dbbd`
- `msvcrt!free` at `0x18000dbcc`
- `KERNEL32!LeaveCriticalSection` at `0x18000db94`
- `KERNEL32!LeaveCriticalSection` at `0x18000dbfd`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc4c`
- `KERNEL32!LeaveCriticalSection` at `0x18000db94`
- `KERNEL32!LeaveCriticalSection` at `0x18000dbfd`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc4c`
- `mqsec!DeleteFalconKeyValue` at `0x18000db44`
- `mqsec!DeleteFalconKeyValue` at `0x18000db62`
- `mqsec!DeleteFalconKeyValue` at `0x18000db44`
- `mqsec!DeleteFalconKeyValue` at `0x18000db62`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAdmin::GetReportQueue(CAdmin *this, struct QUEUE_FORMAT *a2)
{
  int QueueProperties; // eax
  int v4; // edi
  void *v6[11]; // [rsp+40h] [rbp-98h] BYREF
  void *Block; // [rsp+98h] [rbp-40h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids);
  CCriticalSection::Lock((CCriticalSection *)&g_csReadWriteRequests);
  if ( !Admin )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids);
    LogMsgHR(-1072824317, (wchar_t *)L"admin", 0x28u);
    LeaveCriticalSection(&g_csReadWriteRequests);
    return 3222142979LL;
  }
  if ( !dword_180128664 )
  {
LABEL_15:
    *(_BYTE *)a2 = word_18013A758;
    *((_BYTE *)a2 + 1) = *(&word_18013A758 + 1);
    *(_OWORD *)((char *)a2 + 2) = xmmword_18013A75A;
    *((_OWORD *)a2 + 1) = *(__int128 *)((char *)&xmmword_18013A75A + 14);
    LeaveCriticalSection(&g_csReadWriteRequests);
    return 0;
  }
  dword_180128664 = 0;
  Block = 0;
  QueueProperties = QmpGetQueueProperties(
                      (const struct QUEUE_FORMAT *)&word_18013A758,
                      (struct _QueueProps *)v6,
                      0,
                      0,
                      0,
                      0);
  v4 = QueueProperties;
  if ( QueueProperties >= 0 )
  {
    free(v6[1]);
    free(v6[0]);
    goto LABEL_14;
  }
  if ( QueueProperties == -1072824301 )
  {
    dword_180128664 = 1;
LABEL_14:
    free(Block);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids);
  LogMsgHR(v4, (wchar_t *)L"admin", 0x1Eu);
  word_18013A758 = 0;
  Admin = 0;
  DeleteFalconKeyValue(L"ReportQueueGuid");
  dword_18013A778 = 0;
  CQueueMgr::m_fReportQM = 0;
  DeleteFalconKeyValue(L"PropagateFlag");
  LogMsgHR(-1072824317, (wchar_t *)L"admin", 0x23u);
  free(Block);
  LeaveCriticalSection(&g_csReadWriteRequests);
  return 3222142979LL;
}

```

## disassembly

```asm
0x18000da24  push    rbx
0x18000da26  push    rbp
0x18000da27  push    rdi
0x18000da28  push    r15
0x18000da2a  sub     rsp, 0B8h
0x18000da31  mov     rax, cs:__security_cookie
0x18000da38  xor     rax, rsp
0x18000da3b  mov     [rsp+0D8h+var_38], rax
0x18000da43  mov     rbx, rdx
0x18000da46  lea     r15, WPP_GLOBAL_Control
0x18000da4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da54  cmp     rcx, r15
0x18000da57  jz      short loc_18000DA74
0x18000da59  test    byte ptr [rcx+1Ch], 4
0x18000da5d  jz      short loc_18000DA74
0x18000da5f  mov     edx, 0Ch
0x18000da64  lea     r8, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids
0x18000da6b  mov     rcx, [rcx+10h]
0x18000da6f  call    WPP_SF_
0x18000da74  lea     rbp, ?g_csReadWriteRequests@@3VCCriticalSection@@A; CCriticalSection g_csReadWriteRequests
0x18000da7b  mov     [rsp+0D8h+var_A8], rbp
0x18000da80  mov     rcx, rbp; this
0x18000da83  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000da88  nop
0x18000da89  cmp     cs:?Admin@@3VCAdmin@@A, 0; CAdmin Admin
0x18000da90  jz      loc_18000DC08
0x18000da96  cmp     cs:dword_180128664, 0
0x18000da9d  jz      loc_18000DBD3
0x18000daa3  mov     cs:dword_180128664, 0
0x18000daad  mov     [rsp+0D8h+Block], 0
0x18000dab9  mov     [rsp+0D8h+var_B0], 0; bool
0x18000dabe  mov     [rsp+0D8h+var_B8], 0; bool
0x18000dac3  xor     r9d, r9d; bool
0x18000dac6  xor     r8d, r8d; bool
0x18000dac9  lea     rdx, [rsp+0D8h+var_98]; struct _QueueProps *
0x18000dace  lea     rcx, word_18013A758; struct QUEUE_FORMAT *
0x18000dad5  call    ?QmpGetQueueProperties@@YAJPEBUQUEUE_FORMAT@@PEAU_QueueProps@@_N222@Z; QmpGetQueueProperties(QUEUE_FORMAT const *,_QueueProps *,bool,bool,bool,bool)
0x18000dada  mov     edi, eax
0x18000dadc  test    eax, eax
0x18000dade  jns     loc_18000DBAC
0x18000dae4  cmp     eax, 0C00E0013h
0x18000dae9  jz      loc_18000DBA0
0x18000daef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daf6  cmp     rcx, r15
0x18000daf9  jz      short loc_18000DB16
0x18000dafb  test    byte ptr [rcx+1Ch], 4
0x18000daff  jz      short loc_18000DB16
0x18000db01  mov     edx, 0Dh
0x18000db06  lea     r8, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids
0x18000db0d  mov     rcx, [rcx+10h]
0x18000db11  call    WPP_SF_
0x18000db16  mov     r8d, 1Eh; unsigned __int16
0x18000db1c  lea     rdx, aAdmin; "admin"
0x18000db23  mov     ecx, edi; int
0x18000db25  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000db2a  mov     cs:word_18013A758, 0
0x18000db33  mov     cs:?Admin@@3VCAdmin@@A, 0; CAdmin Admin
0x18000db3d  lea     rcx, aReportqueuegui; "ReportQueueGuid"
0x18000db44  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x18000db4a  mov     cs:dword_18013A778, 0
0x18000db54  mov     cs:?m_fReportQM@CQueueMgr@@0_NA, 0; bool CQueueMgr::m_fReportQM
0x18000db5b  lea     rcx, aPropagateflag; "PropagateFlag"
0x18000db62  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x18000db68  mov     r8d, 23h ; '#'; unsigned __int16
0x18000db6e  lea     rdx, aAdmin; "admin"
0x18000db75  mov     ebx, 0C00E0003h
0x18000db7a  mov     ecx, ebx; int
0x18000db7c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000db81  nop
0x18000db82  mov     rcx, [rsp+0D8h+Block]; Block
0x18000db8a  call    cs:__imp_free
0x18000db90  nop
0x18000db91  mov     rcx, rbp; lpCriticalSection
0x18000db94  call    cs:__imp_LeaveCriticalSection
0x18000db9a  nop
0x18000db9b  jmp     loc_18000DC53
0x18000dba0  mov     cs:dword_180128664, 1
0x18000dbaa  jmp     short loc_18000DBC4
0x18000dbac  mov     rcx, [rsp+0D8h+var_90]; Block
0x18000dbb1  call    cs:__imp_free
0x18000dbb7  nop
0x18000dbb8  mov     rcx, [rsp+0D8h+var_98]; Block
0x18000dbbd  call    cs:__imp_free
0x18000dbc3  nop
0x18000dbc4  mov     rcx, [rsp+0D8h+Block]; Block
0x18000dbcc  call    cs:__imp_free
0x18000dbd2  nop
0x18000dbd3  mov     al, byte ptr cs:word_18013A758
0x18000dbd9  mov     [rbx], al
0x18000dbdb  mov     al, byte ptr cs:word_18013A758+1
0x18000dbe1  mov     [rbx+1], al
0x18000dbe4  movups  xmm0, cs:xmmword_18013A75A
0x18000dbeb  movups  xmmword ptr [rbx+2], xmm0
0x18000dbef  movups  xmm1, cs:xmmword_18013A75A+0Eh
0x18000dbf6  movups  xmmword ptr [rbx+10h], xmm1
0x18000dbfa  mov     rcx, rbp; lpCriticalSection
0x18000dbfd  call    cs:__imp_LeaveCriticalSection
0x18000dc03  nop
0x18000dc04  xor     eax, eax
0x18000dc06  jmp     short loc_18000DC55
0x18000dc08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc0f  cmp     rcx, r15
0x18000dc12  jz      short loc_18000DC2F
0x18000dc14  test    byte ptr [rcx+1Ch], 4
0x18000dc18  jz      short loc_18000DC2F
0x18000dc1a  mov     edx, 0Eh
0x18000dc1f  lea     r8, WPP_007980389d1c3f502f0b41fe86b75671_Traceguids
0x18000dc26  mov     rcx, [rcx+10h]
0x18000dc2a  call    WPP_SF_
0x18000dc2f  mov     r8d, 28h ; '('; unsigned __int16
0x18000dc35  lea     rdx, aAdmin; "admin"
0x18000dc3c  mov     ebx, 0C00E0003h
0x18000dc41  mov     ecx, ebx; int
0x18000dc43  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000dc48  nop
0x18000dc49  mov     rcx, rbp; lpCriticalSection
0x18000dc4c  call    cs:__imp_LeaveCriticalSection
0x18000dc52  nop
0x18000dc53  mov     eax, ebx
0x18000dc55  mov     rcx, [rsp+0D8h+var_38]
0x18000dc5d  xor     rcx, rsp; StackCookie
0x18000dc60  call    __security_check_cookie
0x18000dc65  add     rsp, 0B8h
0x18000dc6c  pop     r15
0x18000dc6e  pop     rdi
0x18000dc6f  pop     rbp
0x18000dc70  pop     rbx
0x18000dc71  retn
```

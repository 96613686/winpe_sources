# OnDemand::OnDemandInterfaceInfo::~OnDemandInterfaceInfo(void)

- ea: `0x18008f840`
- end: `0x18008faa7`
- name: `??1OnDemandInterfaceInfo@OnDemand@@QEAA@XZ`
- size: `615`
- prototype: `void __fastcall(OnDemand::OnDemandInterfaceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180092930`

## callees

- `0x180007f90`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x18008f840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f96b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fa07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f96b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fa07`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f8ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f949`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f9e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f8ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f949`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f9e5`

## pseudocode

```c
void __fastcall OnDemand::OnDemandInterfaceInfo::~OnDemandInterfaceInfo(OnDemand::OnDemandInterfaceInfo *this)
{
  __int64 v2; // rcx
  void *v3; // rdx
  DWORD LastError; // eax
  void *v5; // rdx
  DWORD v6; // eax
  void *v7; // rdx
  DWORD v8; // eax

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
      "OnDemand::OnDemandInterfaceInfo::~OnDemandInterfaceInfo");
    v2 = WPP_GLOBAL_Control;
  }
  v3 = (void *)*((_QWORD *)this + 394);
  if ( v3 )
  {
    if ( DeleteTimerQueueTimer(0, v3, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_S(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
          (char *)this + 532);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
           && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, LastError);
    }
    *((_QWORD *)this + 394) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  v5 = (void *)*((_QWORD *)this + 395);
  if ( v5 )
  {
    if ( DeleteTimerQueueTimer(0, v5, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_S(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
          (char *)this + 532);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
           && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v6);
    }
    *((_QWORD *)this + 395) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  v7 = (void *)*((_QWORD *)this + 396);
  if ( v7 )
  {
    if ( DeleteTimerQueueTimer(0, v7, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
           && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids, v8);
    }
    *((_QWORD *)this + 396) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && *(_BYTE *)(v2 + 25) >= 5u && (*(_BYTE *)(v2 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v2 + 16),
      17,
      (unsigned int)WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids,
      (unsigned int)"OnDemand::OnDemandInterfaceInfo::~OnDemandInterfaceInfo",
      0);
}

```

## disassembly

```asm
0x18008f840  mov     [rsp+arg_0], rbx
0x18008f845  mov     [rsp+arg_8], rbp
0x18008f84a  push    r14
0x18008f84c  sub     rsp, 30h
0x18008f850  mov     rbx, rcx
0x18008f853  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f85a  lea     rbp, WPP_GLOBAL_Control
0x18008f861  lea     r14, WPP_7ef1a219358f3e78125012fa23bc8b03_Traceguids
0x18008f868  cmp     rcx, rbp
0x18008f86b  jz      short loc_18008F898
0x18008f86d  cmp     byte ptr [rcx+19h], 5
0x18008f871  jb      short loc_18008F898
0x18008f873  test    byte ptr [rcx+1Ch], 1
0x18008f877  jz      short loc_18008F898
0x18008f879  mov     rcx, [rcx+10h]
0x18008f87d  lea     r9, aOndemandOndema_0; "OnDemand::OnDemandInterfaceInfo::~OnDem"...
0x18008f884  mov     edx, 0Ah
0x18008f889  mov     r8, r14
0x18008f88c  call    WPP_SF_s
0x18008f891  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f898  mov     rdx, [rbx+0C50h]; Timer
0x18008f89f  test    rdx, rdx
0x18008f8a2  jz      loc_18008F934
0x18008f8a8  xor     r8d, r8d; CompletionEvent
0x18008f8ab  xor     ecx, ecx; TimerQueue
0x18008f8ad  call    cs:__imp_DeleteTimerQueueTimer
0x18008f8b3  test    eax, eax
0x18008f8b5  jnz     short loc_18008F8F2
0x18008f8b7  mov     rax, cs:WPP_GLOBAL_Control
0x18008f8be  cmp     rax, rbp
0x18008f8c1  jz      short loc_18008F922
0x18008f8c3  cmp     byte ptr [rax+19h], 3
0x18008f8c7  jb      short loc_18008F922
0x18008f8c9  test    byte ptr [rax+1Ch], 1
0x18008f8cd  jz      short loc_18008F922
0x18008f8cf  call    cs:__imp_GetLastError
0x18008f8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f8dc  mov     edx, 0Bh
0x18008f8e1  mov     r9d, eax
0x18008f8e4  mov     r8, r14
0x18008f8e7  mov     rcx, [rcx+10h]
0x18008f8eb  call    WPP_SF_d
0x18008f8f0  jmp     short loc_18008F922
0x18008f8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f8f9  cmp     rcx, rbp
0x18008f8fc  jz      short loc_18008F922
0x18008f8fe  cmp     byte ptr [rcx+19h], 4
0x18008f902  jb      short loc_18008F922
0x18008f904  test    byte ptr [rcx+1Ch], 1
0x18008f908  jz      short loc_18008F922
0x18008f90a  mov     rcx, [rcx+10h]
0x18008f90e  lea     r9, [rbx+214h]
0x18008f915  mov     edx, 0Ch
0x18008f91a  mov     r8, r14
0x18008f91d  call    WPP_SF_S
0x18008f922  mov     qword ptr [rbx+0C50h], 0
0x18008f92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f934  mov     rdx, [rbx+0C58h]; Timer
0x18008f93b  test    rdx, rdx
0x18008f93e  jz      loc_18008F9D0
0x18008f944  xor     r8d, r8d; CompletionEvent
0x18008f947  xor     ecx, ecx; TimerQueue
0x18008f949  call    cs:__imp_DeleteTimerQueueTimer
0x18008f94f  test    eax, eax
0x18008f951  jnz     short loc_18008F98E
0x18008f953  mov     rax, cs:WPP_GLOBAL_Control
0x18008f95a  cmp     rax, rbp
0x18008f95d  jz      short loc_18008F9BE
0x18008f95f  cmp     byte ptr [rax+19h], 3
0x18008f963  jb      short loc_18008F9BE
0x18008f965  test    byte ptr [rax+1Ch], 1
0x18008f969  jz      short loc_18008F9BE
0x18008f96b  call    cs:__imp_GetLastError
0x18008f971  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f978  mov     edx, 0Dh
0x18008f97d  mov     r9d, eax
0x18008f980  mov     r8, r14
0x18008f983  mov     rcx, [rcx+10h]
0x18008f987  call    WPP_SF_d
0x18008f98c  jmp     short loc_18008F9BE
0x18008f98e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f995  cmp     rcx, rbp
0x18008f998  jz      short loc_18008F9BE
0x18008f99a  cmp     byte ptr [rcx+19h], 4
0x18008f99e  jb      short loc_18008F9BE
0x18008f9a0  test    byte ptr [rcx+1Ch], 1
0x18008f9a4  jz      short loc_18008F9BE
0x18008f9a6  mov     rcx, [rcx+10h]
0x18008f9aa  lea     r9, [rbx+214h]
0x18008f9b1  mov     edx, 0Eh
0x18008f9b6  mov     r8, r14
0x18008f9b9  call    WPP_SF_S
0x18008f9be  mov     qword ptr [rbx+0C58h], 0
0x18008f9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f9d0  mov     rdx, [rbx+0C60h]; Timer
0x18008f9d7  test    rdx, rdx
0x18008f9da  jz      loc_18008FA65
0x18008f9e0  xor     r8d, r8d; CompletionEvent
0x18008f9e3  xor     ecx, ecx; TimerQueue
0x18008f9e5  call    cs:__imp_DeleteTimerQueueTimer
0x18008f9eb  test    eax, eax
0x18008f9ed  jnz     short loc_18008FA2A
0x18008f9ef  mov     rax, cs:WPP_GLOBAL_Control
0x18008f9f6  cmp     rax, rbp
0x18008f9f9  jz      short loc_18008FA53
0x18008f9fb  cmp     byte ptr [rax+19h], 3
0x18008f9ff  jb      short loc_18008FA53
0x18008fa01  test    byte ptr [rax+1Ch], 1
0x18008fa05  jz      short loc_18008FA53
0x18008fa07  call    cs:__imp_GetLastError
0x18008fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa14  mov     edx, 0Fh
0x18008fa19  mov     r9d, eax
0x18008fa1c  mov     r8, r14
0x18008fa1f  mov     rcx, [rcx+10h]
0x18008fa23  call    WPP_SF_d
0x18008fa28  jmp     short loc_18008FA53
0x18008fa2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa31  cmp     rcx, rbp
0x18008fa34  jz      short loc_18008FA53
0x18008fa36  cmp     byte ptr [rcx+19h], 4
0x18008fa3a  jb      short loc_18008FA53
0x18008fa3c  test    byte ptr [rcx+1Ch], 1
0x18008fa40  jz      short loc_18008FA53
0x18008fa42  mov     rcx, [rcx+10h]
0x18008fa46  mov     edx, 10h
0x18008fa4b  mov     r8, r14
0x18008fa4e  call    WPP_SF_
0x18008fa53  mov     qword ptr [rbx+0C60h], 0
0x18008fa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fa65  cmp     rcx, rbp
0x18008fa68  jz      short loc_18008FA96
0x18008fa6a  cmp     byte ptr [rcx+19h], 5
0x18008fa6e  jb      short loc_18008FA96
0x18008fa70  test    byte ptr [rcx+1Ch], 1
0x18008fa74  jz      short loc_18008FA96
0x18008fa76  mov     rcx, [rcx+10h]
0x18008fa7a  lea     r9, aOndemandOndema_0; "OnDemand::OnDemandInterfaceInfo::~OnDem"...
0x18008fa81  mov     edx, 11h
0x18008fa86  mov     [rsp+38h+var_18], 0
0x18008fa8e  mov     r8, r14
0x18008fa91  call    WPP_SF_sL
0x18008fa96  mov     rbx, [rsp+38h+arg_0]
0x18008fa9b  mov     rbp, [rsp+38h+arg_8]
0x18008faa0  add     rsp, 30h
0x18008faa4  pop     r14
0x18008faa6  retn
```

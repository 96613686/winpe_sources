# CUserModeHangReport::_OnWerReportingStart(int *,void *)

- ea: `0x140026f70`
- end: `0x140027115`
- name: `?_OnWerReportingStart@CUserModeHangReport@@EEAAHPEAHPEAX@Z`
- size: `421`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140014ee4`
- `0x140014f14`
- `0x140022b58`
- `0x140023e8c`
- `0x140026f70`
- `0x14002840c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026fc6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140027031`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026fc6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140027031`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140027009`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140027009`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14002707f`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14002707f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14002705e`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14002705e`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::_OnWerReportingStart(CUserModeHangReport *this, int *a2, void *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  void *v8; // rcx
  struct _TP_WAIT *v9; // rcx
  void *v10; // rcx
  HWND v11; // rcx
  HWND Window; // rax
  int v13; // eax

  *a2 = 0;
  if ( !CHangReport::_CheckIfCanceled(this, a3) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 0x83C5) != 0
      || (int)CUserModeHangReport::AcquireReportingLocks(this, v5, v6, v7) >= 0 )
    {
      *((_DWORD *)this + 6229) = (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 8) == 0;
      v9 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
      if ( v9 )
        SetThreadpoolWait(v9, 0, 0);
      v10 = *(void **)(*((_QWORD *)this + 3054) + 1720LL);
      if ( v10 && *((_DWORD *)this + 6229) )
        SetEvent(v10);
      v11 = *(HWND *)(*((_QWORD *)this + 3054) + 1448LL);
      if ( v11 )
      {
        if ( *((_DWORD *)this + 10548) )
        {
          Window = GetWindow(v11, 4u);
          if ( Window )
            SendMessageW(Window, *((_DWORD *)this + 10548), 2u, 0);
        }
      }
      if ( (*(_DWORD *)(*((_QWORD *)this + 3054) + 1440LL) & 0x83C4) == 0 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
        }
        v13 = CUserModeHangReport::_SetBucketingParameters(this, 1);
        if ( v13 < 0
          && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
            (unsigned int)v13);
        }
      }
    }
    else
    {
      v8 = (void *)*((_QWORD *)this + 3089);
      if ( (unsigned __int64)v8 + 1 > 1 )
        SetEvent(v8);
      *a2 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140026f70  mov     [rsp+arg_0], rbx
0x140026f75  push    rdi
0x140026f76  sub     rsp, 20h
0x140026f7a  mov     rdi, rdx
0x140026f7d  mov     dword ptr [rdx], 0
0x140026f83  mov     rdx, r8; void *
0x140026f86  mov     rbx, rcx
0x140026f89  call    ?_CheckIfCanceled@CHangReport@@IEAAHPEAX@Z; CHangReport::_CheckIfCanceled(void *)
0x140026f8e  test    eax, eax
0x140026f90  jnz     loc_140027107
0x140026f96  mov     rax, [rbx+5F70h]
0x140026f9d  test    dword ptr [rax+5A0h], 83C5h
0x140026fa7  jnz     short loc_140026FDD
0x140026fa9  mov     rcx, rbx; this
0x140026fac  call    ?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ; CUserModeHangReport::AcquireReportingLocks(void)
0x140026fb1  test    eax, eax
0x140026fb3  jns     short loc_140026FDD
0x140026fb5  mov     rcx, [rbx+6088h]; hEvent
0x140026fbc  lea     rax, [rcx+1]
0x140026fc0  cmp     rax, 1
0x140026fc4  jbe     short loc_140026FD2
0x140026fc6  call    cs:__imp_SetEvent
0x140026fcd  nop     dword ptr [rax+rax+00h]
0x140026fd2  mov     dword ptr [rdi], 1
0x140026fd8  jmp     loc_140027107
0x140026fdd  mov     rax, [rbx+5F70h]
0x140026fe4  mov     ecx, [rax+5A0h]
0x140026fea  shr     ecx, 3
0x140026fed  not     ecx
0x140026fef  and     ecx, 1
0x140026ff2  mov     [rbx+6154h], ecx
0x140026ff8  mov     rcx, [rbx+60B0h]; pwa
0x140026fff  test    rcx, rcx
0x140027002  jz      short loc_140027015
0x140027004  xor     r8d, r8d; pftTimeout
0x140027007  xor     edx, edx; h
0x140027009  call    cs:__imp_SetThreadpoolWait
0x140027010  nop     dword ptr [rax+rax+00h]
0x140027015  mov     rax, [rbx+5F70h]
0x14002701c  mov     rcx, [rax+6B8h]; hEvent
0x140027023  test    rcx, rcx
0x140027026  jz      short loc_14002703D
0x140027028  cmp     dword ptr [rbx+6154h], 0
0x14002702f  jz      short loc_14002703D
0x140027031  call    cs:__imp_SetEvent
0x140027038  nop     dword ptr [rax+rax+00h]
0x14002703d  mov     rax, [rbx+5F70h]
0x140027044  mov     rcx, [rax+5A8h]; hWnd
0x14002704b  test    rcx, rcx
0x14002704e  jz      short loc_14002708B
0x140027050  cmp     dword ptr [rbx+0A4D0h], 0
0x140027057  jz      short loc_14002708B
0x140027059  mov     edx, 4; uCmd
0x14002705e  call    cs:__imp_GetWindow
0x140027065  nop     dword ptr [rax+rax+00h]
0x14002706a  test    rax, rax
0x14002706d  jz      short loc_14002708B
0x14002706f  mov     edx, [rbx+0A4D0h]; Msg
0x140027075  xor     r9d, r9d; lParam
0x140027078  mov     rcx, rax; hWnd
0x14002707b  lea     r8d, [r9+2]; wParam
0x14002707f  call    cs:__imp_SendMessageW
0x140027086  nop     dword ptr [rax+rax+00h]
0x14002708b  mov     rax, [rbx+5F70h]
0x140027092  test    dword ptr [rax+5A0h], 83C4h
0x14002709c  jnz     short loc_140027107
0x14002709e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270a5  lea     rdi, WPP_GLOBAL_Control
0x1400270ac  cmp     rcx, rdi
0x1400270af  jz      short loc_1400270CC
0x1400270b1  test    byte ptr [rcx+1Ch], 8
0x1400270b5  jz      short loc_1400270CC
0x1400270b7  mov     rcx, [rcx+10h]
0x1400270bb  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400270c2  mov     edx, 20h ; ' '
0x1400270c7  call    WPP_SF_
0x1400270cc  mov     edx, 1; int
0x1400270d1  mov     rcx, rbx; this
0x1400270d4  call    ?_SetBucketingParameters@CUserModeHangReport@@AEAAJH@Z; CUserModeHangReport::_SetBucketingParameters(int)
0x1400270d9  test    eax, eax
0x1400270db  jns     short loc_140027107
0x1400270dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400270e4  cmp     rcx, rdi
0x1400270e7  jz      short loc_140027107
0x1400270e9  test    byte ptr [rcx+1Ch], 1
0x1400270ed  jz      short loc_140027107
0x1400270ef  mov     rcx, [rcx+10h]
0x1400270f3  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400270fa  mov     edx, 21h ; '!'
0x1400270ff  mov     r9d, eax
0x140027102  call    WPP_SF_d
0x140027107  mov     rbx, [rsp+28h+arg_0]
0x14002710c  xor     eax, eax
0x14002710e  add     rsp, 20h
0x140027112  pop     rdi
0x140027113  retn
```

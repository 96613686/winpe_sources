# CUserModeHangReport::_OnWerReportingStart(int *,void *)

- ea: `0x140025670`
- end: `0x1400257f6`
- name: `?_OnWerReportingStart@CUserModeHangReport@@EEAAHPEAHPEAX@Z`
- size: `390`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14001444c`
- `0x140014474`
- `0x14002152c`
- `0x1400227ec`
- `0x140025670`
- `0x140026a70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400256c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140025725`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400256c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140025725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140025703`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140025703`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x140025767`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x140025767`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14002574c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x14002574c`

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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
        }
        v13 = CUserModeHangReport::_SetBucketingParameters(this, 1);
        if ( v13 < 0
          && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
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
0x140025670  mov     [rsp+arg_0], rbx
0x140025675  push    rdi
0x140025676  sub     rsp, 20h
0x14002567a  mov     rdi, rdx
0x14002567d  mov     dword ptr [rdx], 0
0x140025683  mov     rdx, r8; void *
0x140025686  mov     rbx, rcx
0x140025689  call    ?_CheckIfCanceled@CHangReport@@IEAAHPEAX@Z; CHangReport::_CheckIfCanceled(void *)
0x14002568e  test    eax, eax
0x140025690  jnz     loc_1400257E9
0x140025696  mov     rax, [rbx+5F70h]
0x14002569d  test    dword ptr [rax+5A0h], 83C5h
0x1400256a7  jnz     short loc_1400256D7
0x1400256a9  mov     rcx, rbx; this
0x1400256ac  call    ?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ; CUserModeHangReport::AcquireReportingLocks(void)
0x1400256b1  test    eax, eax
0x1400256b3  jns     short loc_1400256D7
0x1400256b5  mov     rcx, [rbx+6088h]; hEvent
0x1400256bc  lea     rax, [rcx+1]
0x1400256c0  cmp     rax, 1
0x1400256c4  jbe     short loc_1400256CC
0x1400256c6  call    cs:__imp_SetEvent
0x1400256cc  mov     dword ptr [rdi], 1
0x1400256d2  jmp     loc_1400257E9
0x1400256d7  mov     rax, [rbx+5F70h]
0x1400256de  mov     ecx, [rax+5A0h]
0x1400256e4  shr     ecx, 3
0x1400256e7  not     ecx
0x1400256e9  and     ecx, 1
0x1400256ec  mov     [rbx+6154h], ecx
0x1400256f2  mov     rcx, [rbx+60B0h]; pwa
0x1400256f9  test    rcx, rcx
0x1400256fc  jz      short loc_140025709
0x1400256fe  xor     r8d, r8d; pftTimeout
0x140025701  xor     edx, edx; h
0x140025703  call    cs:__imp_SetThreadpoolWait
0x140025709  mov     rax, [rbx+5F70h]
0x140025710  mov     rcx, [rax+6B8h]; hEvent
0x140025717  test    rcx, rcx
0x14002571a  jz      short loc_14002572B
0x14002571c  cmp     dword ptr [rbx+6154h], 0
0x140025723  jz      short loc_14002572B
0x140025725  call    cs:__imp_SetEvent
0x14002572b  mov     rax, [rbx+5F70h]
0x140025732  mov     rcx, [rax+5A8h]; hWnd
0x140025739  test    rcx, rcx
0x14002573c  jz      short loc_14002576D
0x14002573e  cmp     dword ptr [rbx+0A4D0h], 0
0x140025745  jz      short loc_14002576D
0x140025747  mov     edx, 4; uCmd
0x14002574c  call    cs:__imp_GetWindow
0x140025752  test    rax, rax
0x140025755  jz      short loc_14002576D
0x140025757  mov     edx, [rbx+0A4D0h]; Msg
0x14002575d  xor     r9d, r9d; lParam
0x140025760  mov     rcx, rax; hWnd
0x140025763  lea     r8d, [r9+2]; wParam
0x140025767  call    cs:__imp_SendMessageW
0x14002576d  mov     rax, [rbx+5F70h]
0x140025774  test    dword ptr [rax+5A0h], 83C4h
0x14002577e  jnz     short loc_1400257E9
0x140025780  mov     rcx, cs:WPP_GLOBAL_Control
0x140025787  lea     rdi, WPP_GLOBAL_Control
0x14002578e  cmp     rcx, rdi
0x140025791  jz      short loc_1400257AE
0x140025793  test    byte ptr [rcx+1Ch], 8
0x140025797  jz      short loc_1400257AE
0x140025799  mov     rcx, [rcx+10h]
0x14002579d  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400257a4  mov     edx, 20h ; ' '
0x1400257a9  call    WPP_SF_
0x1400257ae  mov     edx, 1; int
0x1400257b3  mov     rcx, rbx; this
0x1400257b6  call    ?_SetBucketingParameters@CUserModeHangReport@@AEAAJH@Z; CUserModeHangReport::_SetBucketingParameters(int)
0x1400257bb  test    eax, eax
0x1400257bd  jns     short loc_1400257E9
0x1400257bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400257c6  cmp     rcx, rdi
0x1400257c9  jz      short loc_1400257E9
0x1400257cb  test    byte ptr [rcx+1Ch], 1
0x1400257cf  jz      short loc_1400257E9
0x1400257d1  mov     rcx, [rcx+10h]
0x1400257d5  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400257dc  mov     edx, 21h ; '!'
0x1400257e1  mov     r9d, eax
0x1400257e4  call    WPP_SF_d
0x1400257e9  mov     rbx, [rsp+28h+arg_0]
0x1400257ee  xor     eax, eax
0x1400257f0  add     rsp, 20h
0x1400257f4  pop     rdi
0x1400257f5  retn
```

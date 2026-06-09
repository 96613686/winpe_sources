# RemotePushSubscription::ProcessResult(RemotePushSubscription::BatchResultSet &)

- ea: `0x180016034`
- end: `0x180016194`
- name: `?ProcessResult@RemotePushSubscription@@AEAAXAEAVBatchResultSet@1@@Z`
- size: `352`
- prototype: `void __fastcall(RemotePushSubscription *__hidden this, struct RemotePushSubscription::BatchResultSet *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017730`

## callees

- `0x180016034`
- `0x18001619c`
- `0x180020e4c`
- `0x180023548`
- `0x180038fb4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016151`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RemotePushSubscription::ProcessResult(
        RemotePushSubscription *this,
        struct RemotePushSubscription::BatchResultSet *a2)
{
  __int64 v4; // rdi
  unsigned int v5; // ecx
  __int64 v6; // rdx
  unsigned int v7; // r8d
  RemotePushSubscription *v8; // [rsp+20h] [rbp-48h] BYREF
  char v9; // [rsp+28h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  int v12; // [rsp+48h] [rbp-20h]
  int v13; // [rsp+4Ch] [rbp-1Ch]
  int v14; // [rsp+50h] [rbp-18h]

  if ( !*((_BYTE *)this + 344) )
  {
    LODWORD(v4) = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 || (v4 = *((unsigned int *)a2 + 1), (_DWORD)v4) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids,
          (unsigned int)v4);
      }
      if ( *((_QWORD *)this + 4) )
      {
        *((_DWORD *)this + 85) = GetCurrentThreadId();
        v8 = this;
        v9 = 1;
        (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD))this + 4))(0, *((_QWORD *)this + 5), (unsigned int)v4);
        tlx::_UndoSolo__RemotePushSubscription::ProcessResult_::_14_::_lambda_1___::__UndoSolo__RemotePushSubscription::ProcessResult_::_14_::_lambda_1___(&v8);
      }
    }
    else
    {
      while ( (unsigned int)v4 < *((_DWORD *)a2 + 6) )
      {
        v5 = *((_DWORD *)a2 + 7);
        v6 = *(unsigned int *)(*((_QWORD *)a2 + 1) + 4 * v4);
        if ( (unsigned int)v6 > v5 || (v7 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 4 * v4), v7 > v5 - (unsigned int)v6) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids, 13);
          }
          pExceptionObject = 0;
          v11 = 0;
          v12 = 13;
          v13 = -1;
          v14 = 340;
          throw (EvtException *)&pExceptionObject;
        }
        RemotePushSubscription::InvokeCallbackForEvent(this, (unsigned __int8 *const)(*((_QWORD *)a2 + 4) + v6), v7);
        v4 = (unsigned int)(v4 + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x180016034  mov     [rsp+arg_0], rbx
0x180016039  mov     [rsp+arg_8], rsi
0x18001603e  push    rdi
0x18001603f  sub     rsp, 60h
0x180016043  mov     rbx, rdx
0x180016046  mov     rsi, rcx
0x180016049  cmp     byte ptr [rcx+158h], 0
0x180016050  jnz     loc_180016184
0x180016056  mov     edi, [rdx]
0x180016058  test    edi, edi
0x18001605a  jnz     loc_180016113
0x180016060  mov     edi, [rdx+4]
0x180016063  test    edi, edi
0x180016065  jnz     loc_180016113
0x18001606b  cmp     edi, [rbx+18h]
0x18001606e  jnb     loc_180016184
0x180016074  mov     ecx, [rbx+1Ch]
0x180016077  mov     rax, [rbx+8]
0x18001607b  mov     edx, [rax+rdi*4]
0x18001607e  cmp     edx, ecx
0x180016080  ja      short loc_1800160A1
0x180016082  mov     rax, [rbx+10h]
0x180016086  mov     r8d, [rax+rdi*4]; unsigned int
0x18001608a  sub     ecx, edx
0x18001608c  cmp     r8d, ecx
0x18001608f  ja      short loc_1800160A1
0x180016091  add     rdx, [rbx+20h]; unsigned __int8 *
0x180016095  mov     rcx, rsi; this
0x180016098  call    ?InvokeCallbackForEvent@RemotePushSubscription@@AEAAXQEAEK@Z; RemotePushSubscription::InvokeCallbackForEvent(uchar * const,ulong)
0x18001609d  inc     edi
0x18001609f  jmp     short loc_18001606B
0x1800160a1  lea     rax, WPP_GLOBAL_Control
0x1800160a8  mov     ebx, 0Dh
0x1800160ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160b4  cmp     rcx, rax
0x1800160b7  jz      short loc_1800160DB
0x1800160b9  test    byte ptr [rcx+1Ch], 40h
0x1800160bd  jz      short loc_1800160DB
0x1800160bf  cmp     byte ptr [rcx+19h], 2
0x1800160c3  jb      short loc_1800160DB
0x1800160c5  lea     edx, [rbx+9]
0x1800160c8  mov     r9d, ebx
0x1800160cb  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x1800160d2  mov     rcx, [rcx+10h]
0x1800160d6  call    WPP_SF_D
0x1800160db  xorps   xmm0, xmm0
0x1800160de  movdqu  [rsp+68h+pExceptionObject], xmm0
0x1800160e4  mov     [rsp+68h+var_28], 0
0x1800160ed  mov     [rsp+68h+var_20], ebx
0x1800160f1  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x1800160f9  mov     [rsp+68h+var_18], 154h
0x180016101  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016108  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001610d  call    _CxxThrowException_0
0x180016113  lea     rax, WPP_GLOBAL_Control
0x18001611a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016121  cmp     rcx, rax
0x180016124  jz      short loc_18001614A
0x180016126  test    byte ptr [rcx+1Ch], 40h
0x18001612a  jz      short loc_18001614A
0x18001612c  cmp     byte ptr [rcx+19h], 3
0x180016130  jb      short loc_18001614A
0x180016132  mov     edx, 15h
0x180016137  mov     r9d, edi
0x18001613a  lea     r8, WPP_ace92e4ac21938b1819d9fbab7cc40fd_Traceguids
0x180016141  mov     rcx, [rcx+10h]
0x180016145  call    WPP_SF_D
0x18001614a  cmp     qword ptr [rsi+20h], 0
0x18001614f  jz      short loc_180016184
0x180016151  call    cs:__imp_GetCurrentThreadId
0x180016157  mov     [rsi+154h], eax
0x18001615d  mov     [rsp+68h+var_48], rsi
0x180016162  mov     [rsp+68h+var_40], 1
0x180016167  mov     r8d, edi
0x18001616a  mov     rdx, [rsi+28h]
0x18001616e  xor     ecx, ecx
0x180016170  mov     rax, [rsi+20h]
0x180016174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016179  nop
0x18001617a  lea     rcx, [rsp+68h+var_48]
0x18001617f  call    tlx___UndoSolo__RemotePushSubscription__ProcessResult____14____lambda_1_______UndoSolo__RemotePushSubscription__ProcessResult____14____lambda_1___
0x180016184  mov     rbx, [rsp+68h+arg_0]
0x180016189  mov     rsi, [rsp+68h+arg_8]
0x18001618e  add     rsp, 60h
0x180016192  pop     rdi
0x180016193  retn
```

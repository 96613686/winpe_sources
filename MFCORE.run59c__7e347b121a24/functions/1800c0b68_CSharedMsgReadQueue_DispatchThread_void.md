# CSharedMsgReadQueue::DispatchThread(void)

- ea: `0x1800c0b68`
- end: `0x1800c0d42`
- name: `?DispatchThread@CSharedMsgReadQueue@@AEAAIXZ`
- size: `474`
- prototype: `unsigned int __fastcall(CSharedMsgReadQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18032cfd0`

## callees

- `0x18004d118`
- `0x18006b388`
- `0x1800c0b68`
- `0x1800c0f1c`
- `0x18012add8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800c0bb6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800c0bb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0d31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0c3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c0bce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c0bce`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c0b92`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c0b92`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c0c58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c0c58`
- `RTWorkQ!RtwqInvokeCallback` at `0x1800c0c0f`
- `RTWorkQ!RtwqInvokeCallback` at `0x1800c0c0f`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800c0d07`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800c0d07`
- `AVRT!AvSetMmThreadPriority` at `0x1800c0d1e`
- `AVRT!AvSetMmThreadPriority` at `0x1800c0d1e`

## pseudocode

```c
__int64 __fastcall CSharedMsgReadQueue::DispatchThread(CSharedMsgReadQueue *this)
{
  DWORD v2; // eax
  unsigned int i; // esi
  __int64 v5; // rbx
  const WCHAR *v6; // rax
  HANDLE v7; // rax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  Handles[0] = *((HANDLE *)this + 5);
  Handles[1] = *((HANDLE *)this + 16);
  CoInitializeEx(0, 0);
  while ( 1 )
  {
    while ( 1 )
    {
      v2 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
      if ( v2 )
        break;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      if ( g_wppLevels >= 0x20u )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          &WPP_00b8b8f1bf333a785a062a301fa38367_Traceguids,
          this,
          *((_QWORD *)this + 25));
      if ( *((_QWORD *)this + 25) )
      {
        for ( i = 0; i < 2; ++i )
        {
          if ( (unsigned int)CSharedMsgReadQueue::TryReadMsg(this) )
          {
            RtwqInvokeCallback(*((IRtwqAsyncResult **)this + 25));
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 16LL))(*((_QWORD *)this + 25));
            *((_QWORD *)this + 25) = 0;
            break;
          }
          if ( g_wppLevels >= 8u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_00b8b8f1bf333a785a062a301fa38367_Traceguids, this);
          _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 3) + 20LL), 1);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    }
    if ( v2 != 1 || *((_DWORD *)this + 46) != 1 )
      break;
    v5 = *((_QWORD *)this + 24);
    v6 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(v5);
    v7 = AvSetMmThreadCharacteristicsW(v6, (LPDWORD)(v5 + 24));
    if ( v7 )
      AvSetMmThreadPriority(v7, *(AVRT_PRIORITY *)(v5 + 28));
    SetEvent(*((HANDLE *)this + 17));
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800c0b68  mov     r11, rsp
0x1800c0b6b  mov     [r11+8], rbx
0x1800c0b6f  mov     [r11+10h], rsi
0x1800c0b73  push    rdi
0x1800c0b74  sub     rsp, 40h
0x1800c0b78  mov     rax, [rcx+28h]
0x1800c0b7c  mov     rdi, rcx
0x1800c0b7f  mov     [r11-18h], rax
0x1800c0b83  xor     edx, edx; dwCoInit
0x1800c0b85  mov     rax, [rcx+80h]
0x1800c0b8c  xor     ecx, ecx; pvReserved
0x1800c0b8e  mov     [r11-10h], rax
0x1800c0b92  call    cs:__imp_CoInitializeEx
0x1800c0b99  nop     dword ptr [rax+rax+00h]
0x1800c0b9e  xor     r8d, r8d; bWaitAll
0x1800c0ba1  mov     [rsp+48h+bAlertable], 0; bAlertable
0x1800c0ba9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800c0bad  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800c0bb2  lea     ecx, [r8+2]; nCount
0x1800c0bb6  call    cs:__imp_WaitForMultipleObjectsEx
0x1800c0bbd  nop     dword ptr [rax+rax+00h]
0x1800c0bc2  test    eax, eax
0x1800c0bc4  jnz     loc_1800C0C4F
0x1800c0bca  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800c0bce  call    cs:__imp_EnterCriticalSection
0x1800c0bd5  nop     dword ptr [rax+rax+00h]
0x1800c0bda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800c0be1  jnb     loc_1800C0C77
0x1800c0be7  cmp     qword ptr [rdi+0C8h], 0
0x1800c0bef  jz      short loc_1800C0C3A
0x1800c0bf1  xor     esi, esi
0x1800c0bf3  cmp     esi, 2
0x1800c0bf6  jnb     short loc_1800C0C3A
0x1800c0bf8  mov     rcx, rdi; this
0x1800c0bfb  call    ?TryReadMsg@CSharedMsgReadQueue@@AEAAHXZ; CSharedMsgReadQueue::TryReadMsg(void)
0x1800c0c00  test    eax, eax
0x1800c0c02  jz      loc_1800C0CA7
0x1800c0c08  mov     rcx, [rdi+0C8h]; result
0x1800c0c0f  call    cs:__imp_RtwqInvokeCallback
0x1800c0c16  nop     dword ptr [rax+rax+00h]
0x1800c0c1b  mov     rcx, [rdi+0C8h]
0x1800c0c22  mov     rax, [rcx]
0x1800c0c25  mov     rax, [rax+10h]
0x1800c0c29  call    cs:__guard_dispatch_icall_fptr
0x1800c0c2f  mov     qword ptr [rdi+0C8h], 0
0x1800c0c3a  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800c0c3e  call    cs:__imp_LeaveCriticalSection
0x1800c0c45  nop     dword ptr [rax+rax+00h]
0x1800c0c4a  jmp     loc_1800C0B9E
0x1800c0c4f  cmp     eax, 1
0x1800c0c52  jz      loc_1800C0CE2
0x1800c0c58  call    cs:__imp_CoUninitialize
0x1800c0c5f  nop     dword ptr [rax+rax+00h]
0x1800c0c64  mov     rbx, [rsp+48h+arg_0]
0x1800c0c69  xor     eax, eax
0x1800c0c6b  mov     rsi, [rsp+48h+arg_8]
0x1800c0c70  add     rsp, 40h
0x1800c0c74  pop     rdi
0x1800c0c75  retn
0x1800c0c77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0c7e  lea     r8, WPP_00b8b8f1bf333a785a062a301fa38367_Traceguids
0x1800c0c85  mov     rax, [rdi+0C8h]
0x1800c0c8c  mov     edx, 40h ; '@'
0x1800c0c91  mov     r9, rdi
0x1800c0c94  mov     qword ptr [rsp+48h+bAlertable], rax
0x1800c0c99  mov     rcx, [rcx+10h]
0x1800c0c9d  call    WPP_SF_qq
0x1800c0ca2  jmp     loc_1800C0BE7
0x1800c0ca7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800c0cae  jb      short loc_1800C0CCF
0x1800c0cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0cb7  lea     r8, WPP_00b8b8f1bf333a785a062a301fa38367_Traceguids
0x1800c0cbe  mov     edx, 41h ; 'A'
0x1800c0cc3  mov     r9, rdi
0x1800c0cc6  mov     rcx, [rcx+10h]
0x1800c0cca  call    WPP_SF_q
0x1800c0ccf  mov     rcx, [rdi+18h]
0x1800c0cd3  mov     eax, 1
0x1800c0cd8  inc     esi
0x1800c0cda  xchg    eax, [rcx+14h]
0x1800c0cdd  jmp     loc_1800C0BF3
0x1800c0ce2  mov     eax, [rdi+0B8h]
0x1800c0ce8  cmp     eax, 1
0x1800c0ceb  jnz     loc_1800C0C58
0x1800c0cf1  mov     rbx, [rdi+0C0h]
0x1800c0cf8  mov     rcx, rbx
0x1800c0cfb  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800c0d00  mov     rcx, rax; TaskName
0x1800c0d03  lea     rdx, [rbx+18h]; TaskIndex
0x1800c0d07  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800c0d0e  nop     dword ptr [rax+rax+00h]
0x1800c0d13  test    rax, rax
0x1800c0d16  jz      short loc_1800C0D2A
0x1800c0d18  mov     edx, [rbx+1Ch]; Priority
0x1800c0d1b  mov     rcx, rax; AvrtHandle
0x1800c0d1e  call    cs:__imp_AvSetMmThreadPriority
0x1800c0d25  nop     dword ptr [rax+rax+00h]
0x1800c0d2a  mov     rcx, [rdi+88h]; hEvent
0x1800c0d31  call    cs:__imp_SetEvent
0x1800c0d38  nop     dword ptr [rax+rax+00h]
0x1800c0d3d  jmp     loc_1800C0B9E
```

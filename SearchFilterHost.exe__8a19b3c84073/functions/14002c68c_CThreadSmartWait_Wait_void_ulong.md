# CThreadSmartWait::Wait(void *,ulong)

- ea: `0x14002c68c`
- end: `0x14002c8d5`
- name: `?Wait@CThreadSmartWait@@QEAAXPEAXK@Z`
- size: `585`
- prototype: `void __fastcall(CThreadSmartWait *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002c8dc`

## callees

- `0x1400274ec`
- `0x14002b0a4`
- `0x14002c68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c74b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c74b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c6a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c7f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c6a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002c7f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14002c7bb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14002c7bb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x14002c7a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x14002c7a1`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14002c7f0`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x14002c7f0`

## pseudocode

```c
void __fastcall CThreadSmartWait::Wait(CThreadSmartWait *this, char *a2, unsigned int a3)
{
  DWORD TickCount; // eax
  __int64 v7; // r9
  DWORD v8; // ebx
  DWORD v9; // ecx
  DWORD v10; // esi
  HANDLE *v11; // r15
  HANDLE EventW; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbp
  __int64 v16; // rcx
  DWORD v17; // r14d
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // edx
  unsigned int v21; // ecx
  HANDLE pHandles[2]; // [rsp+30h] [rbp-88h] BYREF
  tagMSG Msg; // [rsp+40h] [rbp-78h] BYREF

  TickCount = GetTickCount();
  v7 = *((unsigned int *)this + 4);
  v8 = *((_DWORD *)&CThreadSmartWait::m_sdwSleep + v7);
  v9 = *((_DWORD *)&CThreadSmartWait::m_sdwPeriod + v7);
  if ( v8 < v9 && v8 )
    v8 = v9 - (v9 - v8) / a3;
  if ( TickCount - *((_DWORD *)this + 5) >= *((_DWORD *)&CThreadSmartWait::m_sdwPeriod + *((unsigned int *)this + 4))
    || *((_DWORD *)&CThreadSmartWait::m_sdwSleep + *((unsigned int *)this + 4)) >= *((_DWORD *)&CThreadSmartWait::m_sdwPeriod
                                                                                   + *((unsigned int *)this + 4)) )
  {
    *((_DWORD *)this + 5) = TickCount;
    v10 = 0;
    *(_OWORD *)pHandles = 0;
    if ( (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      pHandles[0] = a2;
      v10 = 1;
    }
    v11 = (HANDLE *)((char *)this + 40);
    if ( ((*((_QWORD *)this + 5) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 40,
        EventW);
    }
    if ( (char *)*v11 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v13 = v10++;
      pHandles[v13] = *v11;
    }
    while ( v8 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
          goto LABEL_35;
        DispatchMessageW(&Msg);
      }
      if ( (byte_14006B841 & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v14, MSSearchTraceId_BackoffThreadWait_Start, v8);
      v15 = MsgWaitForMultipleObjects(v10, pHandles, 0, v8, 0x1CFFu);
      v17 = GetTickCount();
      if ( (byte_14006B841 & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v16, MSSearchTraceId_BackoffThreadWait_Stop, (unsigned int)v15);
      if ( *((_DWORD *)&CThreadSmartWait::m_sdwSleep + *((unsigned int *)this + 4)) < *((_DWORD *)&CThreadSmartWait::m_sdwPeriod
                                                                                      + *((unsigned int *)this + 4)) )
      {
        v18 = *((unsigned int *)this + 4);
        v19 = v17 - *((_DWORD *)this + 5);
        v20 = *((_DWORD *)&CThreadSmartWait::m_sdwSleep + v18);
        if ( v20 )
          v21 = *((_DWORD *)&CThreadSmartWait::m_sdwPeriod + v18)
              - (*((_DWORD *)&CThreadSmartWait::m_sdwPeriod + v18) - v20) / a3;
        else
          v21 = 0;
        if ( v19 >= v21 )
          break;
        v8 = v21 - v19;
      }
      else if ( (char *)*v11 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v8 = *((_DWORD *)&CThreadSmartWait::m_sdwSleep + *((unsigned int *)this + 4));
      }
      else
      {
        v8 = -1;
      }
      if ( (_DWORD)v15 != 258 )
      {
        if ( (unsigned int)v15 >= v10 )
        {
          if ( (_DWORD)v15 != v10 )
            break;
        }
        else if ( pHandles[v15] == a2 )
        {
          break;
        }
      }
    }
  }
LABEL_35:
  *((_BYTE *)this + 28) = 0;
}

```

## disassembly

```asm
0x14002c68c  push    rbx
0x14002c68e  push    rbp
0x14002c68f  push    rsi
0x14002c690  push    rdi
0x14002c691  push    r12
0x14002c693  push    r13
0x14002c695  push    r14
0x14002c697  push    r15
0x14002c699  sub     rsp, 78h
0x14002c69d  mov     r12d, r8d
0x14002c6a0  mov     r13, rdx
0x14002c6a3  mov     rdi, rcx
0x14002c6a6  call    cs:__imp_GetTickCount
0x14002c6ac  mov     r9d, [rdi+10h]
0x14002c6b0  lea     r8, __ImageBase
0x14002c6b7  mov     r11d, eax
0x14002c6ba  mov     esi, eax
0x14002c6bc  sub     r11d, [rdi+14h]
0x14002c6c0  mov     ebx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+r9*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14002c6c8  mov     ecx, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+r9*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x14002c6d0  cmp     ebx, ecx
0x14002c6d2  jnb     short loc_14002C6E5
0x14002c6d4  test    ebx, ebx
0x14002c6d6  jz      short loc_14002C6E5
0x14002c6d8  xor     edx, edx
0x14002c6da  mov     eax, ecx
0x14002c6dc  sub     eax, ebx
0x14002c6de  mov     ebx, ecx
0x14002c6e0  div     r12d
0x14002c6e3  sub     ebx, eax
0x14002c6e5  mov     eax, [rdi+10h]
0x14002c6e8  cmp     r11d, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x14002c6f0  jnb     short loc_14002C70E
0x14002c6f2  mov     ecx, [rdi+10h]
0x14002c6f5  mov     eax, [rdi+10h]
0x14002c6f8  mov     eax, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14002c700  cmp     eax, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rcx*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x14002c708  jb      loc_14002C8C0
0x14002c70e  mov     [rdi+14h], esi
0x14002c711  lea     rax, [r13-1]
0x14002c715  xor     esi, esi
0x14002c717  xorps   xmm0, xmm0
0x14002c71a  movups  xmmword ptr [rsp+0B8h+pHandles], xmm0
0x14002c71f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c723  ja      short loc_14002C72F
0x14002c725  mov     [rsp+0B8h+pHandles], r13
0x14002c72a  mov     esi, 1
0x14002c72f  lea     r15, [rdi+28h]
0x14002c733  mov     rax, [r15]
0x14002c736  inc     rax
0x14002c739  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002c73f  jnz     short loc_14002C75C
0x14002c741  xor     r9d, r9d; lpName
0x14002c744  xor     r8d, r8d; bInitialState
0x14002c747  xor     edx, edx; bManualReset
0x14002c749  xor     ecx, ecx; lpEventAttributes
0x14002c74b  call    cs:__imp_CreateEventW
0x14002c751  mov     rdx, rax
0x14002c754  mov     rcx, r15
0x14002c757  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14002c75c  mov     rcx, [r15]
0x14002c75f  lea     rax, [rcx-1]
0x14002c763  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c767  ja      short loc_14002C772
0x14002c769  mov     eax, esi
0x14002c76b  inc     esi
0x14002c76d  mov     [rsp+rax*8+0B8h+pHandles], rcx
0x14002c772  test    ebx, ebx
0x14002c774  jz      loc_14002C8C0
0x14002c77a  xorps   xmm0, xmm0
0x14002c77d  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x14002c782  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x14002c787  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x14002c78c  xor     r9d, r9d; wMsgFilterMax
0x14002c78f  mov     [rsp+0B8h+wRemoveMsg], 1; wRemoveMsg
0x14002c797  xor     r8d, r8d; wMsgFilterMin
0x14002c79a  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x14002c79f  xor     edx, edx; hWnd
0x14002c7a1  call    cs:__imp_PeekMessageW
0x14002c7a7  test    eax, eax
0x14002c7a9  jz      short loc_14002C7C3
0x14002c7ab  cmp     [rsp+0B8h+Msg.message], 12h
0x14002c7b0  jz      loc_14002C8C0
0x14002c7b6  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x14002c7bb  call    cs:__imp_DispatchMessageW
0x14002c7c1  jmp     short loc_14002C78C
0x14002c7c3  test    cs:byte_14006B841, 2
0x14002c7ca  jz      short loc_14002C7DB
0x14002c7cc  mov     r8d, ebx
0x14002c7cf  lea     rdx, MSSearchTraceId_BackoffThreadWait_Start
0x14002c7d6  call    McTemplateU0q_EventWriteTransfer
0x14002c7db  mov     r9d, ebx; dwMilliseconds
0x14002c7de  mov     [rsp+0B8h+wRemoveMsg], 1CFFh; dwWakeMask
0x14002c7e6  xor     r8d, r8d; fWaitAll
0x14002c7e9  lea     rdx, [rsp+0B8h+pHandles]; pHandles
0x14002c7ee  mov     ecx, esi; nCount
0x14002c7f0  call    cs:__imp_MsgWaitForMultipleObjects
0x14002c7f6  mov     ebp, eax
0x14002c7f8  call    cs:__imp_GetTickCount
0x14002c7fe  test    cs:byte_14006B841, 2
0x14002c805  mov     r14d, eax
0x14002c808  jz      short loc_14002C819
0x14002c80a  mov     r8d, ebp
0x14002c80d  lea     rdx, MSSearchTraceId_BackoffThreadWait_Stop
0x14002c814  call    McTemplateU0q_EventWriteTransfer
0x14002c819  mov     ecx, [rdi+10h]
0x14002c81c  lea     r8, __ImageBase
0x14002c823  mov     eax, [rdi+10h]
0x14002c826  mov     eax, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14002c82e  cmp     eax, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rcx*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x14002c836  jb      short loc_14002C856
0x14002c838  mov     rax, [r15]
0x14002c83b  dec     rax
0x14002c83e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c842  ja      short loc_14002C849
0x14002c844  or      ebx, 0FFFFFFFFh
0x14002c847  jmp     short loc_14002C89D
0x14002c849  mov     eax, [rdi+10h]
0x14002c84c  mov     ebx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14002c854  jmp     short loc_14002C89D
0x14002c856  mov     eax, [rdi+10h]
0x14002c859  sub     r14d, [rdi+14h]
0x14002c85d  mov     edx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14002c865  test    edx, edx
0x14002c867  jz      short loc_14002C87E
0x14002c869  mov     ecx, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x14002c871  mov     eax, ecx
0x14002c873  sub     eax, edx
0x14002c875  xor     edx, edx
0x14002c877  div     r12d
0x14002c87a  sub     ecx, eax
0x14002c87c  jmp     short loc_14002C880
0x14002c87e  xor     ecx, ecx
0x14002c880  mov     [rsp+0B8h+arg_0], ecx
0x14002c887  mov     eax, [rsp+0B8h+arg_0]
0x14002c88e  cmp     r14d, eax
0x14002c891  jnb     short loc_14002C8C0
0x14002c893  mov     ebx, [rsp+0B8h+arg_0]
0x14002c89a  sub     ebx, r14d
0x14002c89d  cmp     ebp, 102h
0x14002c8a3  jz      loc_14002C772
0x14002c8a9  cmp     ebp, esi
0x14002c8ab  jnb     short loc_14002C8BA
0x14002c8ad  cmp     [rsp+rbp*8+0B8h+pHandles], r13
0x14002c8b2  jnz     loc_14002C772
0x14002c8b8  jmp     short loc_14002C8C0
0x14002c8ba  jz      loc_14002C772
0x14002c8c0  mov     byte ptr [rdi+1Ch], 0
0x14002c8c4  add     rsp, 78h
0x14002c8c8  pop     r15
0x14002c8ca  pop     r14
0x14002c8cc  pop     r13
0x14002c8ce  pop     r12
0x14002c8d0  pop     rdi
0x14002c8d1  pop     rsi
0x14002c8d2  pop     rbp
0x14002c8d3  pop     rbx
0x14002c8d4  retn
```

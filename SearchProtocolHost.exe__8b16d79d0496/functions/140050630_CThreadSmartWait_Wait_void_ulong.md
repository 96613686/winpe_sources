# CThreadSmartWait::Wait(void *,ulong)

- ea: `0x140050630`
- end: `0x140050879`
- name: `?Wait@CThreadSmartWait@@QEAAXPEAXK@Z`
- size: `585`
- prototype: `void __fastcall(CThreadSmartWait *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140050880`

## callees

- `0x140037ca8`
- `0x140039d48`
- `0x140050630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400506ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400506ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005064a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005079c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005064a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14005079c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14005075f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x14005075f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x140050745`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x140050745`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x140050794`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x140050794`

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
  struct tagMSG Msg; // [rsp+40h] [rbp-78h] BYREF

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
      if ( (byte_140097A01 & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v14, MSSearchTraceId_BackoffThreadWait_Start, v8);
      v15 = MsgWaitForMultipleObjects(v10, pHandles, 0, v8, 0x1CFFu);
      v17 = GetTickCount();
      if ( (byte_140097A01 & 2) != 0 )
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
0x140050630  push    rbx
0x140050632  push    rbp
0x140050633  push    rsi
0x140050634  push    rdi
0x140050635  push    r12
0x140050637  push    r13
0x140050639  push    r14
0x14005063b  push    r15
0x14005063d  sub     rsp, 78h
0x140050641  mov     r12d, r8d
0x140050644  mov     r13, rdx
0x140050647  mov     rdi, rcx
0x14005064a  call    cs:__imp_GetTickCount
0x140050650  mov     r9d, [rdi+10h]
0x140050654  lea     r8, __ImageBase
0x14005065b  mov     r11d, eax
0x14005065e  mov     esi, eax
0x140050660  sub     r11d, [rdi+14h]
0x140050664  mov     ebx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+r9*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x14005066c  mov     ecx, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+r9*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x140050674  cmp     ebx, ecx
0x140050676  jnb     short loc_140050689
0x140050678  test    ebx, ebx
0x14005067a  jz      short loc_140050689
0x14005067c  xor     edx, edx
0x14005067e  mov     eax, ecx
0x140050680  sub     eax, ebx
0x140050682  mov     ebx, ecx
0x140050684  div     r12d
0x140050687  sub     ebx, eax
0x140050689  mov     eax, [rdi+10h]
0x14005068c  cmp     r11d, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x140050694  jnb     short loc_1400506B2
0x140050696  mov     ecx, [rdi+10h]
0x140050699  mov     eax, [rdi+10h]
0x14005069c  mov     eax, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x1400506a4  cmp     eax, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rcx*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x1400506ac  jb      loc_140050864
0x1400506b2  mov     [rdi+14h], esi
0x1400506b5  lea     rax, [r13-1]
0x1400506b9  xor     esi, esi
0x1400506bb  xorps   xmm0, xmm0
0x1400506be  movups  xmmword ptr [rsp+0B8h+pHandles], xmm0
0x1400506c3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400506c7  ja      short loc_1400506D3
0x1400506c9  mov     [rsp+0B8h+pHandles], r13
0x1400506ce  mov     esi, 1
0x1400506d3  lea     r15, [rdi+28h]
0x1400506d7  mov     rax, [r15]
0x1400506da  inc     rax
0x1400506dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400506e3  jnz     short loc_140050700
0x1400506e5  xor     r9d, r9d; lpName
0x1400506e8  xor     r8d, r8d; bInitialState
0x1400506eb  xor     edx, edx; bManualReset
0x1400506ed  xor     ecx, ecx; lpEventAttributes
0x1400506ef  call    cs:__imp_CreateEventW
0x1400506f5  mov     rdx, rax
0x1400506f8  mov     rcx, r15
0x1400506fb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140050700  mov     rcx, [r15]
0x140050703  lea     rax, [rcx-1]
0x140050707  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005070b  ja      short loc_140050716
0x14005070d  mov     eax, esi
0x14005070f  inc     esi
0x140050711  mov     [rsp+rax*8+0B8h+pHandles], rcx
0x140050716  test    ebx, ebx
0x140050718  jz      loc_140050864
0x14005071e  xorps   xmm0, xmm0
0x140050721  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x140050726  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x14005072b  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x140050730  xor     r9d, r9d; wMsgFilterMax
0x140050733  mov     [rsp+0B8h+wRemoveMsg], 1; wRemoveMsg
0x14005073b  xor     r8d, r8d; wMsgFilterMin
0x14005073e  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x140050743  xor     edx, edx; hWnd
0x140050745  call    cs:__imp_PeekMessageW
0x14005074b  test    eax, eax
0x14005074d  jz      short loc_140050767
0x14005074f  cmp     [rsp+0B8h+Msg.message], 12h
0x140050754  jz      loc_140050864
0x14005075a  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x14005075f  call    cs:__imp_DispatchMessageW
0x140050765  jmp     short loc_140050730
0x140050767  test    cs:byte_140097A01, 2
0x14005076e  jz      short loc_14005077F
0x140050770  mov     r8d, ebx
0x140050773  lea     rdx, MSSearchTraceId_BackoffThreadWait_Start
0x14005077a  call    McTemplateU0q_EventWriteTransfer
0x14005077f  mov     r9d, ebx; dwMilliseconds
0x140050782  mov     [rsp+0B8h+wRemoveMsg], 1CFFh; dwWakeMask
0x14005078a  xor     r8d, r8d; fWaitAll
0x14005078d  lea     rdx, [rsp+0B8h+pHandles]; pHandles
0x140050792  mov     ecx, esi; nCount
0x140050794  call    cs:__imp_MsgWaitForMultipleObjects
0x14005079a  mov     ebp, eax
0x14005079c  call    cs:__imp_GetTickCount
0x1400507a2  test    cs:byte_140097A01, 2
0x1400507a9  mov     r14d, eax
0x1400507ac  jz      short loc_1400507BD
0x1400507ae  mov     r8d, ebp
0x1400507b1  lea     rdx, MSSearchTraceId_BackoffThreadWait_Stop
0x1400507b8  call    McTemplateU0q_EventWriteTransfer
0x1400507bd  mov     ecx, [rdi+10h]
0x1400507c0  lea     r8, __ImageBase
0x1400507c7  mov     eax, [rdi+10h]
0x1400507ca  mov     eax, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x1400507d2  cmp     eax, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rcx*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x1400507da  jb      short loc_1400507FA
0x1400507dc  mov     rax, [r15]
0x1400507df  dec     rax
0x1400507e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400507e6  ja      short loc_1400507ED
0x1400507e8  or      ebx, 0FFFFFFFFh
0x1400507eb  jmp     short loc_140050841
0x1400507ed  mov     eax, [rdi+10h]
0x1400507f0  mov     ebx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x1400507f8  jmp     short loc_140050841
0x1400507fa  mov     eax, [rdi+10h]
0x1400507fd  sub     r14d, [rdi+14h]
0x140050801  mov     edx, rva ?m_sdwSleep@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwSleep ...
0x140050809  test    edx, edx
0x14005080b  jz      short loc_140050822
0x14005080d  mov     ecx, rva ?m_sdwPeriod@CThreadSmartWait@@1PAKA[r8+rax*4]; ulong near * CThreadSmartWait::m_sdwPeriod ...
0x140050815  mov     eax, ecx
0x140050817  sub     eax, edx
0x140050819  xor     edx, edx
0x14005081b  div     r12d
0x14005081e  sub     ecx, eax
0x140050820  jmp     short loc_140050824
0x140050822  xor     ecx, ecx
0x140050824  mov     [rsp+0B8h+arg_0], ecx
0x14005082b  mov     eax, [rsp+0B8h+arg_0]
0x140050832  cmp     r14d, eax
0x140050835  jnb     short loc_140050864
0x140050837  mov     ebx, [rsp+0B8h+arg_0]
0x14005083e  sub     ebx, r14d
0x140050841  cmp     ebp, 102h
0x140050847  jz      loc_140050716
0x14005084d  cmp     ebp, esi
0x14005084f  jnb     short loc_14005085E
0x140050851  cmp     [rsp+rbp*8+0B8h+pHandles], r13
0x140050856  jnz     loc_140050716
0x14005085c  jmp     short loc_140050864
0x14005085e  jz      loc_140050716
0x140050864  mov     byte ptr [rdi+1Ch], 0
0x140050868  add     rsp, 78h
0x14005086c  pop     r15
0x14005086e  pop     r14
0x140050870  pop     r13
0x140050872  pop     r12
0x140050874  pop     rdi
0x140050875  pop     rsi
0x140050876  pop     rbp
0x140050877  pop     rbx
0x140050878  retn
```

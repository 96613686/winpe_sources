# WnfSubscriptionData::~WnfSubscriptionData(void)

- ea: `0x180059a20`
- end: `0x180059b4c`
- name: `??1WnfSubscriptionData@@QEAA@XZ`
- size: `300`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059bdc`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180059a20`
- `0x18005a0d4`
- `0x18007e010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180059a94`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180059a94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059a2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059b00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059b00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059b40`

## pseudocode

```c
void __fastcall WnfSubscriptionData::~WnfSubscriptionData(LPCRITICAL_SECTION lpCriticalSection)
{
  PVOID *v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  LPCRITICAL_SECTION OwningThread; // rcx

  EnterCriticalSection(lpCriticalSection);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpCriticalSection[2].LockSemaphore )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_q(v2[2], 13);
    v3 = RtlUnsubscribeWnfNotificationWaitForCompletion(lpCriticalSection[2].LockSemaphore);
    if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids,
        (unsigned int)v3);
    lpCriticalSection[2].LockSemaphore = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 15, &WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids);
  LeaveCriticalSection(lpCriticalSection);
  OwningThread = (LPCRITICAL_SECTION)lpCriticalSection[2].OwningThread;
  if ( OwningThread )
  {
    LOBYTE(v4) = OwningThread != &lpCriticalSection[1];
    (*(void (__fastcall **)(LPCRITICAL_SECTION, __int64))&OwningThread->DebugInfo->EntryCount)(OwningThread, v4);
    lpCriticalSection[2].OwningThread = 0;
  }
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180059a20  mov     [rsp+arg_0], rbx
0x180059a25  push    rdi
0x180059a26  sub     rsp, 20h
0x180059a2a  mov     rbx, rcx
0x180059a2d  call    cs:__imp_EnterCriticalSection
0x180059a34  nop     dword ptr [rax+rax+00h]
0x180059a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a40  lea     rdi, WPP_GLOBAL_Control
0x180059a47  cmp     rcx, rdi
0x180059a4a  jz      short loc_180059A6E
0x180059a4c  test    byte ptr [rcx+1Ch], 20h
0x180059a50  jz      short loc_180059A6E
0x180059a52  mov     rcx, [rcx+10h]
0x180059a56  lea     r8, WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids
0x180059a5d  mov     edx, 0Ch
0x180059a62  call    WPP_SF_
0x180059a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a6e  mov     r9, [rbx+68h]
0x180059a72  test    r9, r9
0x180059a75  jz      short loc_180059ADD
0x180059a77  cmp     rcx, rdi
0x180059a7a  jz      short loc_180059A90
0x180059a7c  test    byte ptr [rcx+1Ch], 8
0x180059a80  jz      short loc_180059A90
0x180059a82  mov     rcx, [rcx+10h]
0x180059a86  mov     edx, 0Dh
0x180059a8b  call    WPP_SF_q
0x180059a90  mov     rcx, [rbx+68h]
0x180059a94  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180059a9b  nop     dword ptr [rax+rax+00h]
0x180059aa0  test    eax, eax
0x180059aa2  jns     short loc_180059ACE
0x180059aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180059aab  cmp     rcx, rdi
0x180059aae  jz      short loc_180059ACE
0x180059ab0  test    byte ptr [rcx+1Ch], 2
0x180059ab4  jz      short loc_180059ACE
0x180059ab6  mov     rcx, [rcx+10h]
0x180059aba  lea     r8, WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids
0x180059ac1  mov     edx, 0Eh
0x180059ac6  mov     r9d, eax
0x180059ac9  call    WPP_SF_d
0x180059ace  mov     qword ptr [rbx+68h], 0
0x180059ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180059add  cmp     rcx, rdi
0x180059ae0  jz      short loc_180059AFD
0x180059ae2  test    byte ptr [rcx+1Ch], 20h
0x180059ae6  jz      short loc_180059AFD
0x180059ae8  mov     rcx, [rcx+10h]
0x180059aec  lea     r8, WPP_d7e5fb4123e1334d4f568fa77d953993_Traceguids
0x180059af3  mov     edx, 0Fh
0x180059af8  call    WPP_SF_
0x180059afd  mov     rcx, rbx; lpCriticalSection
0x180059b00  call    cs:__imp_LeaveCriticalSection
0x180059b07  nop     dword ptr [rax+rax+00h]
0x180059b0c  lea     rdi, [rbx+28h]
0x180059b10  mov     rcx, [rdi+38h]
0x180059b14  test    rcx, rcx
0x180059b17  jz      short loc_180059B33
0x180059b19  mov     rax, [rcx]
0x180059b1c  cmp     rcx, rdi
0x180059b1f  setnz   dl
0x180059b22  mov     rax, [rax+20h]
0x180059b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b2b  mov     qword ptr [rdi+38h], 0
0x180059b33  mov     rcx, rbx
0x180059b36  mov     rbx, [rsp+28h+arg_0]
0x180059b3b  add     rsp, 20h
0x180059b3f  pop     rdi
0x180059b40  jmp     cs:__imp_DeleteCriticalSection
```

# CUserLogonProcessingList::DemandCreateIdentityListenerThread(void)

- ea: `0x18002df1c`
- end: `0x18002e0e4`
- name: `?DemandCreateIdentityListenerThread@CUserLogonProcessingList@@IEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CUserLogonProcessingList *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056a4c`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x18002df1c`
- `0x18002e2b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002df39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e0c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e0c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002df93`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002df93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dfb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserLogonProcessingList::DemandCreateIdentityListenerThread(CUserLogonProcessingList *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  PVOID *v3; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  int v7; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 15) )
  {
LABEL_12:
    v6 = 0;
    if ( !*((_QWORD *)this + 13) )
    {
      v7 = WorkerThreadLauncher((__int64)CUserLogonProcessingList::IdentityListenerThreadEntry, (__int64)this, 7, 0);
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 )
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
          v3 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v6 & 0x80000000) != 0 )
          goto LABEL_26;
      }
      else
      {
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 == &WPP_GLOBAL_Control )
        goto LABEL_29;
      if ( (*((_BYTE *)v3 + 28) & 8) == 0 )
        goto LABEL_26;
      WPP_SF_(v3[2], 248, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      goto LABEL_25;
    }
LABEL_26:
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
      WPP_SF_d(v3[2], 249, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
    goto LABEL_29;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
    (char *)this + 112,
    EventW);
  if ( *((_QWORD *)this + 15) )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 246, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
LABEL_25:
      v3 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    goto LABEL_26;
  }
LABEL_29:
  if ( v2 )
    LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x18002df1c  mov     [rsp+arg_8], rbx
0x18002df21  mov     [rsp+arg_10], rsi
0x18002df26  push    rdi
0x18002df27  push    r14
0x18002df29  push    r15
0x18002df2b  sub     rsp, 20h
0x18002df2f  mov     rdi, rcx
0x18002df32  lea     rsi, [rcx+40h]
0x18002df36  mov     rcx, rsi; lpCriticalSection
0x18002df39  call    cs:__imp_EnterCriticalSection
0x18002df40  nop     dword ptr [rax+rax+00h]
0x18002df45  mov     [rsp+38h+arg_0], rsi
0x18002df4a  lea     r14, WPP_GLOBAL_Control
0x18002df51  lea     r15, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002df58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df5f  cmp     rcx, r14
0x18002df62  jz      short loc_18002DF82
0x18002df64  test    byte ptr [rcx+1Ch], 20h
0x18002df68  jz      short loc_18002DF82
0x18002df6a  mov     edx, 0F5h
0x18002df6f  mov     r8, r15
0x18002df72  mov     rcx, [rcx+10h]
0x18002df76  call    WPP_SF_
0x18002df7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df82  cmp     qword ptr [rdi+78h], 0
0x18002df87  jnz     short loc_18002E007
0x18002df89  xor     r9d, r9d; lpName
0x18002df8c  xor     r8d, r8d; bInitialState
0x18002df8f  xor     edx, edx; bManualReset
0x18002df91  xor     ecx, ecx; lpEventAttributes
0x18002df93  call    cs:__imp_CreateEventW
0x18002df9a  nop     dword ptr [rax+rax+00h]
0x18002df9f  mov     rdx, rax
0x18002dfa2  lea     rcx, [rdi+70h]
0x18002dfa6  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18002dfab  cmp     qword ptr [rdi+78h], 0
0x18002dfb0  jnz     short loc_18002E000
0x18002dfb2  call    cs:__imp_GetLastError
0x18002dfb9  nop     dword ptr [rax+rax+00h]
0x18002dfbe  mov     ebx, eax
0x18002dfc0  test    eax, eax
0x18002dfc2  jle     short loc_18002DFCD
0x18002dfc4  movzx   ebx, ax
0x18002dfc7  or      ebx, 80070000h
0x18002dfcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfd4  cmp     rcx, r14
0x18002dfd7  jz      loc_18002E0B9
0x18002dfdd  test    byte ptr [rcx+1Ch], 40h
0x18002dfe1  jz      loc_18002E099
0x18002dfe7  mov     edx, 0F6h
0x18002dfec  mov     r9d, ebx
0x18002dfef  mov     r8, r15
0x18002dff2  mov     rcx, [rcx+10h]
0x18002dff6  call    WPP_SF_d
0x18002dffb  jmp     loc_18002E092
0x18002e000  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e007  xor     ebx, ebx
0x18002e009  cmp     [rdi+68h], rbx
0x18002e00d  jnz     loc_18002E099
0x18002e013  xor     r9d, r9d
0x18002e016  lea     r8d, [rbx+7]
0x18002e01a  mov     rdx, rdi
0x18002e01d  lea     rcx, ?IdentityListenerThreadEntry@CUserLogonProcessingList@@KAIPEAX@Z; CUserLogonProcessingList::IdentityListenerThreadEntry(void *)
0x18002e024  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x18002e029  mov     ebx, eax
0x18002e02b  test    eax, eax
0x18002e02d  jle     short loc_18002E038
0x18002e02f  movzx   ebx, ax
0x18002e032  or      ebx, 80070000h
0x18002e038  test    ebx, ebx
0x18002e03a  jz      short loc_18002E06F
0x18002e03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e043  cmp     rcx, r14
0x18002e046  jz      short loc_18002E069
0x18002e048  test    byte ptr [rcx+1Ch], 40h
0x18002e04c  jz      short loc_18002E069
0x18002e04e  mov     edx, 0F7h
0x18002e053  mov     r9d, ebx
0x18002e056  mov     r8, r15
0x18002e059  mov     rcx, [rcx+10h]
0x18002e05d  call    WPP_SF_d
0x18002e062  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e069  test    ebx, ebx
0x18002e06b  jns     short loc_18002E076
0x18002e06d  jmp     short loc_18002E099
0x18002e06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e076  cmp     rcx, r14
0x18002e079  jz      short loc_18002E0B9
0x18002e07b  test    byte ptr [rcx+1Ch], 8
0x18002e07f  jz      short loc_18002E099
0x18002e081  mov     edx, 0F8h
0x18002e086  mov     r8, r15
0x18002e089  mov     rcx, [rcx+10h]
0x18002e08d  call    WPP_SF_
0x18002e092  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e099  cmp     rcx, r14
0x18002e09c  jz      short loc_18002E0B9
0x18002e09e  test    byte ptr [rcx+1Ch], 20h
0x18002e0a2  jz      short loc_18002E0B9
0x18002e0a4  mov     edx, 0F9h
0x18002e0a9  mov     r9d, ebx
0x18002e0ac  mov     r8, r15
0x18002e0af  mov     rcx, [rcx+10h]
0x18002e0b3  call    WPP_SF_d
0x18002e0b8  nop
0x18002e0b9  test    rsi, rsi
0x18002e0bc  jz      short loc_18002E0CD
0x18002e0be  mov     rcx, rsi; lpCriticalSection
0x18002e0c1  call    cs:__imp_LeaveCriticalSection
0x18002e0c8  nop     dword ptr [rax+rax+00h]
0x18002e0cd  mov     eax, ebx
0x18002e0cf  mov     rbx, [rsp+38h+arg_8]
0x18002e0d4  mov     rsi, [rsp+38h+arg_10]
0x18002e0d9  add     rsp, 20h
0x18002e0dd  pop     r15
0x18002e0df  pop     r14
0x18002e0e1  pop     rdi
0x18002e0e2  retn
```

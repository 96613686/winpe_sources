# Command_D0EntryPostInterruptsEnabled

- ea: `0x140034404`
- end: `0x140034744`
- name: `Command_D0EntryPostInterruptsEnabled`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140044260`

## callees

- `0x14001ac48`
- `0x140034404`
- `0x14003de14`
- `0x140050148`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034733`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034733`
- `ntoskrnl!ExAllocatePool2` at `0x14003445e`
- `ntoskrnl!ExAllocatePool2` at `0x140034563`
- `ntoskrnl!ExAllocatePool2` at `0x14003445e`
- `ntoskrnl!ExAllocatePool2` at `0x140034563`
- `ntoskrnl!_stricmp` at `0x14003452f`
- `ntoskrnl!_stricmp` at `0x14003452f`
- `ntoskrnl!KeInitializeEvent` at `0x14003449a`
- `ntoskrnl!KeInitializeEvent` at `0x140034609`
- `ntoskrnl!KeInitializeEvent` at `0x140034667`
- `ntoskrnl!KeInitializeEvent` at `0x1400346a0`
- `ntoskrnl!KeInitializeEvent` at `0x1400346d1`
- `ntoskrnl!KeInitializeEvent` at `0x14003449a`
- `ntoskrnl!KeInitializeEvent` at `0x140034609`
- `ntoskrnl!KeInitializeEvent` at `0x140034667`
- `ntoskrnl!KeInitializeEvent` at `0x1400346a0`
- `ntoskrnl!KeInitializeEvent` at `0x1400346d1`

## pseudocode

```c
__int64 __fastcall Command_D0EntryPostInterruptsEnabled(__int64 a1, int a2)
{
  __int64 v4; // rsi
  char *v5; // rbx
  __int64 v6; // rbp
  __int64 Pool2; // rax
  int v8; // edx
  int v9; // r9d
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int16 v12; // ax
  __int16 v13; // cx
  _QWORD *v14; // r15
  bool v15; // zf
  __int64 (__fastcall **v16)(); // r14
  void *v17; // rcx
  unsigned int *v18; // rsi
  __int64 (__fastcall *v19)(); // rcx
  unsigned int v20; // eax

  if ( a2 != 5 )
    return 0;
  v4 = *(_QWORD *)(a1 + 8);
  v5 = 0;
  v6 = *(_QWORD *)(v4 + 88);
  if ( (*(_DWORD *)(v6 + 108) & 0x100) != 0 )
  {
    Pool2 = ExAllocatePool2(64, 128, 1229146200);
    v5 = (char *)Pool2;
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v9 = 27;
      LOBYTE(v8) = 2;
LABEL_17:
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 16), v8, 7, v9, (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
      return 0;
    }
    *(_QWORD *)Pool2 = a1;
    KeInitializeEvent((PRKEVENT)(Pool2 + 104), SynchronizationEvent, 0);
    *((_QWORD *)v5 + 7) = v5;
    *((_QWORD *)v5 + 6) = Command_GetSupportedExtendedCapabilityCommandCompletion;
    v10 = *((_DWORD *)v5 + 11) & 0xFFFF63FF;
    *((_QWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 11) = 0;
    *((_DWORD *)v5 + 11) = v10 | 0x6000;
    *((_QWORD *)v5 + 12) = 0;
    Command_SendInternalCommandSynchronously(a1, v5);
    if ( (*(_BYTE *)(v6 + 112) & 1) != 0 )
      *(_DWORD *)(v4 + 1084) = 2;
  }
  v11 = *(_QWORD *)(a1 + 8);
  v12 = *(_WORD *)(v11 + 648);
  if ( v12 != 4147 && v12 != 6418 && v12 != 6945 && _stricmp((const char *)(v11 + 704), "NVDA") )
    goto LABEL_28;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 728LL) = -1;
  if ( !v5 )
  {
    v5 = (char *)ExAllocatePool2(64, 128, 1229146200);
    if ( !v5 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 0;
      v9 = 28;
      LOBYTE(v8) = 3;
      goto LABEL_17;
    }
  }
  v13 = *(_WORD *)(*(_QWORD *)(a1 + 8) + 648LL);
  if ( v13 == 4147 || v13 == 6418 )
  {
    memset(v5 + 8, 0, 0x78u);
    *(_QWORD *)v5 = a1;
    KeInitializeEvent((PRKEVENT)(v5 + 104), SynchronizationEvent, 0);
    v19 = Command_RenesasGetFirmwareVersionCommandCompletion;
    v18 = (unsigned int *)(v5 + 44);
    v16 = (__int64 (__fastcall **)())(v5 + 48);
    v14 = v5 + 56;
    goto LABEL_25;
  }
  v14 = v5 + 56;
  v15 = v13 == 6945;
  v16 = (__int64 (__fastcall **)())(v5 + 48);
  v17 = v5 + 8;
  v18 = (unsigned int *)(v5 + 44);
  if ( !v15 )
  {
    memset(v17, 0, 0x78u);
    *(_QWORD *)v5 = a1;
    KeInitializeEvent((PRKEVENT)(v5 + 104), SynchronizationEvent, 0);
    v19 = Command_NvidiaGetFirmwareVersionCommandCompletion;
LABEL_25:
    v20 = *v18 & 0xFFFF03FF | 0xC400;
LABEL_26:
    *v14 = v5;
    *v16 = v19;
    *v18 = v20;
    Command_SendInternalCommandSynchronously(a1, v5);
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 728LL) != -1 )
      Etw_ControllerFirmareVersionUpdate();
    goto LABEL_28;
  }
  memset(v17, 0, 0x78u);
  *(_QWORD *)v5 = a1;
  KeInitializeEvent((PRKEVENT)(v5 + 104), SynchronizationEvent, 0);
  *v14 = v5;
  *v16 = Command_ASMediaGetFirmwareVersionLowCommandCompletion;
  *v18 = *v18 & 0xFFFF03FF | 0xD000;
  Command_SendInternalCommandSynchronously(a1, v5);
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 728LL) != -1 )
  {
    memset(v5 + 8, 0, 0x78u);
    *(_QWORD *)v5 = a1;
    KeInitializeEvent((PRKEVENT)(v5 + 104), SynchronizationEvent, 0);
    v19 = Command_ASMediaGetFirmwareVersionHighCommandCompletion;
    v20 = *v18 & 0xFFFF03FF | 0xCC00;
    goto LABEL_26;
  }
LABEL_28:
  if ( v5 )
    ExFreePoolWithTag(v5, 0x49434858u);
  return 0;
}

```

## disassembly

```asm
0x140034404  push    rbx
0x140034406  push    rbp
0x140034407  push    rsi
0x140034408  push    rdi
0x140034409  push    r12
0x14003440b  push    r14
0x14003440d  push    r15
0x14003440f  sub     rsp, 30h
0x140034413  mov     rdi, rcx
0x140034416  cmp     edx, 5
0x140034419  jz      short loc_14003442D
0x14003441b  xor     eax, eax
0x14003441d  add     rsp, 30h
0x140034421  pop     r15
0x140034423  pop     r14
0x140034425  pop     r12
0x140034427  pop     rdi
0x140034428  pop     rsi
0x140034429  pop     rbp
0x14003442a  pop     rbx
0x14003442b  retn
0x14003442d  mov     rsi, [rcx+8]
0x140034431  xor     ebx, ebx
0x140034433  mov     r15d, 80h
0x140034439  mov     rbp, [rsi+58h]
0x14003443d  lea     r12d, [rbx+40h]
0x140034441  lea     r14d, [rbx+1]
0x140034445  test    dword ptr [rbp+6Ch], 100h
0x14003444c  jz      loc_1400344F8
0x140034452  mov     r8d, 49434858h
0x140034458  mov     edx, r15d
0x14003445b  mov     ecx, r12d
0x14003445e  call    cs:__imp_ExAllocatePool2
0x140034465  nop     dword ptr [rax+rax+00h]
0x14003446a  mov     rbx, rax
0x14003446d  test    rax, rax
0x140034470  jnz     short loc_14003448D
0x140034472  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140034479  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034480  jz      short loc_14003441B
0x140034482  lea     r9d, [r15-65h]
0x140034486  mov     dl, 2
0x140034488  jmp     loc_140034591
0x14003448d  lea     rcx, [rax+68h]; Event
0x140034491  mov     [rax], rdi
0x140034494  xor     r8d, r8d; State
0x140034497  mov     edx, r14d; Type
0x14003449a  call    cs:__imp_KeInitializeEvent
0x1400344a1  nop     dword ptr [rax+rax+00h]
0x1400344a6  lea     rax, Command_GetSupportedExtendedCapabilityCommandCompletion
0x1400344ad  mov     [rbx+38h], rbx
0x1400344b1  mov     [rbx+30h], rax
0x1400344b5  mov     rdx, rbx
0x1400344b8  mov     eax, [rbx+2Ch]
0x1400344bb  mov     rcx, rdi
0x1400344be  and     eax, 0FFFF63FFh
0x1400344c3  mov     qword ptr [rbx+50h], 0
0x1400344cb  or      eax, 6000h
0x1400344d0  mov     qword ptr [rbx+58h], 0
0x1400344d8  mov     [rbx+2Ch], eax
0x1400344db  mov     qword ptr [rbx+60h], 0
0x1400344e3  call    Command_SendInternalCommandSynchronously
0x1400344e8  test    [rbp+70h], r14b
0x1400344ec  jz      short loc_1400344F8
0x1400344ee  mov     dword ptr [rsi+43Ch], 2
0x1400344f8  mov     rcx, [rdi+8]
0x1400344fc  mov     ebp, 1033h
0x140034501  mov     esi, 1912h
0x140034506  mov     edx, 1B21h
0x14003450b  movzx   eax, word ptr [rcx+288h]
0x140034512  cmp     ax, bp
0x140034515  jz      short loc_140034543
0x140034517  cmp     ax, si
0x14003451a  jz      short loc_140034543
0x14003451c  cmp     ax, dx
0x14003451f  jz      short loc_140034543
0x140034521  add     rcx, 2C0h; Str1
0x140034528  lea     rdx, Str2; "NVDA"
0x14003452f  call    cs:__imp__stricmp
0x140034536  nop     dword ptr [rax+rax+00h]
0x14003453b  test    eax, eax
0x14003453d  jnz     loc_140034722
0x140034543  mov     rax, [rdi+8]
0x140034547  mov     qword ptr [rax+2D8h], 0FFFFFFFFFFFFFFFFh
0x140034552  test    rbx, rbx
0x140034555  jnz     short loc_1400345B1
0x140034557  mov     r8d, 49434858h
0x14003455d  mov     rdx, r15
0x140034560  mov     rcx, r12
0x140034563  call    cs:__imp_ExAllocatePool2
0x14003456a  nop     dword ptr [rax+rax+00h]
0x14003456f  mov     rbx, rax
0x140034572  test    rax, rax
0x140034575  jnz     short loc_1400345B1
0x140034577  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003457e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034585  jz      loc_14003441B
0x14003458b  lea     r9d, [rbx+1Ch]
0x14003458f  mov     dl, 3
0x140034591  mov     rcx, [rdi+10h]
0x140034595  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x14003459c  mov     r8d, 7
0x1400345a2  mov     [rsp+68h+var_48], rax
0x1400345a7  call    WPP_RECORDER_SF_
0x1400345ac  jmp     loc_14003441B
0x1400345b1  mov     rax, [rdi+8]
0x1400345b5  movzx   ecx, word ptr [rax+288h]
0x1400345bc  cmp     cx, bp
0x1400345bf  jz      loc_1400346B5
0x1400345c5  cmp     cx, si
0x1400345c8  jz      loc_1400346B5
0x1400345ce  mov     eax, 1B21h
0x1400345d3  lea     r12, [rbx+68h]
0x1400345d7  xor     edx, edx; Val
0x1400345d9  lea     r15, [rbx+38h]
0x1400345dd  cmp     cx, ax
0x1400345e0  lea     r14, [rbx+30h]
0x1400345e4  lea     rcx, [rbx+8]; void *
0x1400345e8  lea     rsi, [rbx+2Ch]
0x1400345ec  jnz     loc_140034688
0x1400345f2  lea     ebp, [rdx+78h]
0x1400345f5  mov     r8d, ebp; Size
0x1400345f8  call    memset
0x1400345fd  xor     r8d, r8d; State
0x140034600  mov     [rbx], rdi
0x140034603  lea     edx, [rbp-77h]; Type
0x140034606  mov     rcx, r12; Event
0x140034609  call    cs:__imp_KeInitializeEvent
0x140034610  nop     dword ptr [rax+rax+00h]
0x140034615  lea     rax, Command_ASMediaGetFirmwareVersionLowCommandCompletion
0x14003461c  mov     [r15], rbx
0x14003461f  mov     [r14], rax
0x140034622  mov     rdx, rbx
0x140034625  mov     eax, [rsi]
0x140034627  mov     rcx, rdi
0x14003462a  and     eax, 0FFFFD3FFh
0x14003462f  or      eax, 0D000h
0x140034634  mov     [rsi], eax
0x140034636  call    Command_SendInternalCommandSynchronously
0x14003463b  mov     rax, [rdi+8]
0x14003463f  cmp     qword ptr [rax+2D8h], 0FFFFFFFFFFFFFFFFh
0x140034647  jz      loc_140034722
0x14003464d  lea     rcx, [rbx+8]; void *
0x140034651  mov     r8d, ebp; Size
0x140034654  xor     edx, edx; Val
0x140034656  call    memset
0x14003465b  xor     r8d, r8d; State
0x14003465e  mov     [rbx], rdi
0x140034661  lea     edx, [rbp-77h]; Type
0x140034664  mov     rcx, r12; Event
0x140034667  call    cs:__imp_KeInitializeEvent
0x14003466e  nop     dword ptr [rax+rax+00h]
0x140034673  mov     eax, [rsi]
0x140034675  lea     rcx, Command_ASMediaGetFirmwareVersionHighCommandCompletion
0x14003467c  and     eax, 0FFFFCFFFh
0x140034681  or      eax, 0CC00h
0x140034686  jmp     short loc_1400346FC
0x140034688  mov     r8d, 78h ; 'x'; Size
0x14003468e  call    memset
0x140034693  xor     r8d, r8d; State
0x140034696  mov     [rbx], rdi
0x140034699  mov     rcx, r12; Event
0x14003469c  lea     edx, [r8+1]; Type
0x1400346a0  call    cs:__imp_KeInitializeEvent
0x1400346a7  nop     dword ptr [rax+rax+00h]
0x1400346ac  lea     rcx, Command_NvidiaGetFirmwareVersionCommandCompletion
0x1400346b3  jmp     short loc_1400346F0
0x1400346b5  xor     edx, edx; Val
0x1400346b7  lea     rcx, [rbx+8]; void *
0x1400346bb  lea     r8d, [rdx+78h]; Size
0x1400346bf  call    memset
0x1400346c4  lea     rcx, [rbx+68h]; Event
0x1400346c8  mov     [rbx], rdi
0x1400346cb  xor     r8d, r8d; State
0x1400346ce  mov     edx, r14d; Type
0x1400346d1  call    cs:__imp_KeInitializeEvent
0x1400346d8  nop     dword ptr [rax+rax+00h]
0x1400346dd  lea     rcx, Command_RenesasGetFirmwareVersionCommandCompletion
0x1400346e4  lea     rsi, [rbx+2Ch]
0x1400346e8  lea     r14, [rbx+30h]
0x1400346ec  lea     r15, [rbx+38h]
0x1400346f0  mov     eax, [rsi]
0x1400346f2  and     eax, 0FFFFC7FFh
0x1400346f7  or      eax, 0C400h
0x1400346fc  mov     [r15], rbx
0x1400346ff  mov     rdx, rbx
0x140034702  mov     [r14], rcx
0x140034705  mov     rcx, rdi
0x140034708  mov     [rsi], eax
0x14003470a  call    Command_SendInternalCommandSynchronously
0x14003470f  mov     rdx, [rdi+8]
0x140034713  cmp     qword ptr [rdx+2D8h], 0FFFFFFFFFFFFFFFFh
0x14003471b  jz      short loc_140034722
0x14003471d  call    Etw_ControllerFirmareVersionUpdate
0x140034722  test    rbx, rbx
0x140034725  jz      loc_14003441B
0x14003472b  mov     edx, 49434858h; Tag
0x140034730  mov     rcx, rbx; P
0x140034733  call    cs:__imp_ExFreePoolWithTag
0x14003473a  nop     dword ptr [rax+rax+00h]
0x14003473f  jmp     loc_14003441B
```

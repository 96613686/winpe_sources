# PrjfReleaseUnionContext

- ea: `0x140003e6c`
- end: `0x1400040f7`
- name: `PrjfReleaseUnionContext`
- size: `651`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `29`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140001b3c`
- `0x140002288`
- `0x1400037e0`
- `0x140003d9c`
- `0x14000420c`
- `0x140004640`
- `0x1400047cc`
- `0x140006a58`
- `0x140006ca0`
- `0x1400217a4`
- `0x140022320`
- `0x140024184`
- `0x1400280f0`
- `0x140029650`
- `0x14002aa24`
- `0x14002d3c4`
- `0x14002f134`
- `0x14002f204`
- `0x14002f5f0`
- `0x1400306f8`
- `0x140031780`
- `0x1400333c4`
- `0x140033bd0`
- `0x140035238`
- `0x140035f3c`
- `0x1400368c4`
- `0x140039de8`
- `0x14003cc14`
- `0x14003e0d8`

## callees

- `0x140003e6c`
- `0x140006834`
- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000d128`
- `0x1400442ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400040d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400040d5`
- `ntoskrnl!ObfDereferenceObject` at `0x140003fda`
- `ntoskrnl!ObfDereferenceObject` at `0x140003fda`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140003f57`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140003f82`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140003f57`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140003f82`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140003f07`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140003f07`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140003ebf`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140003ebf`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140003f2d`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140003f2d`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000409c`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000409c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003f6f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003f9e`
- `ntoskrnl!ExDeleteResourceLite` at `0x140004089`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400040c1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003f6f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003f9e`
- `ntoskrnl!ExDeleteResourceLite` at `0x140004089`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400040c1`
- `FLTMGR!FltCloseClientPort` at `0x140003fbe`
- `FLTMGR!FltCloseClientPort` at `0x140003fbe`
- `FLTMGR!FltClose` at `0x140003ee6`
- `FLTMGR!FltClose` at `0x140003ee6`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140003ea4`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140003ef5`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140003ea4`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140003ef5`
- `FLTMGR!FltReleaseResource` at `0x140003ed7`
- `FLTMGR!FltReleaseResource` at `0x140003f48`
- `FLTMGR!FltReleaseResource` at `0x140003ed7`
- `FLTMGR!FltReleaseResource` at `0x140003f48`

## string_xrefs

- `0x140003f1b`: `HandleTable entry found without user-opened handle!`

## pseudocode

```c
void __fastcall PrjfReleaseUnionContext(char *P)
{
  BOOLEAN i; // dl
  void *v3; // r14
  char v4; // di
  PVOID v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  int v10; // edx
  int v11; // r8d
  int v12; // [rsp+80h] [rbp+8h] BYREF

  if ( *((int *)P + 22) <= 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(P);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 22, 0xFFFFFFFF) == 1 )
  {
    FltAcquireResourceExclusive((PERESOURCE)(P + 96));
    for ( i = 1; ; i = v4 )
    {
      v5 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(P + 200), i);
      v6 = v5;
      if ( !v5 )
        break;
      ObDereferenceObjectDeferDelete(*((PVOID *)v5 + 2));
      v3 = (void *)v6[3];
      if ( v3 )
      {
        FltReleaseResource((PERESOURCE)(P + 96));
        FltClose(v3);
        FltAcquireResourceExclusive((PERESOURCE)(P + 96));
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(P + 200), v6);
        v4 = 1;
      }
      else
      {
        v4 = 0;
        MicrosoftTelemetryAssertTriggeredMsgKM("HandleTable entry found without user-opened handle!");
      }
    }
    FltReleaseResource((PERESOURCE)(P + 96));
    if ( !RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(P + 200)) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v7);
    ExDeleteResourceLite((PERESOURCE)(P + 96));
    if ( !RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)P + 4) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v8);
    ExDeleteResourceLite((PERESOURCE)P + 3);
    if ( *((_QWORD *)P + 10) )
    {
      FltCloseClientPort(Globals, (PFLT_PORT *)P + 10);
      *((_QWORD *)P + 10) = 0;
    }
    v9 = (void *)*((_QWORD *)P + 4);
    if ( v9 )
      ObfDereferenceObject(v9);
    if ( (*((_DWORD *)P + 14) & 1) != 0 )
    {
      v12 = 0;
      PrjfClearNegativePathCache(P, &v12);
      if ( (BYTE1(xmmword_14001A3E0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = BYTE1(xmmword_14001A3E0) & 2;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          1033,
          v10,
          v11,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          4,
          9,
          42,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          43,
          v12);
      }
      ExDeleteResourceLite((PERESOURCE)(P + 544));
      RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(P + 648));
    }
    if ( *((_QWORD *)P + 86) )
      PrjfClearMappingTable(P);
    ExDeleteResourceLite((PERESOURCE)(P + 696));
    ExFreePoolWithTag(P, 0x63754A50u);
  }
}

```

## disassembly

```asm
0x140003e6c  mov     [rsp+arg_8], rbx
0x140003e71  mov     [rsp+arg_10], rbp
0x140003e76  push    rsi
0x140003e77  push    rdi
0x140003e78  push    r14
0x140003e7a  sub     rsp, 60h
0x140003e7e  cmp     dword ptr [rcx+58h], 0
0x140003e82  mov     rbx, rcx
0x140003e85  jg      short loc_140003E8C
0x140003e87  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003e8c  or      eax, 0FFFFFFFFh
0x140003e8f  lock xadd [rbx+58h], eax
0x140003e94  cmp     eax, 1
0x140003e97  jnz     loc_1400040E1
0x140003e9d  lea     rsi, [rbx+60h]
0x140003ea1  mov     rcx, rsi; Resource
0x140003ea4  call    cs:__imp_FltAcquireResourceExclusive
0x140003eab  nop     dword ptr [rax+rax+00h]
0x140003eb0  mov     dl, 1
0x140003eb2  lea     rbp, [rbx+0C8h]
0x140003eb9  jmp     short loc_140003F2A
0x140003ebb  mov     rcx, [rdi+10h]; Object
0x140003ebf  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140003ec6  nop     dword ptr [rax+rax+00h]
0x140003ecb  mov     r14, [rdi+18h]
0x140003ecf  test    r14, r14
0x140003ed2  jz      short loc_140003F18
0x140003ed4  mov     rcx, rsi; Resource
0x140003ed7  call    cs:__imp_FltReleaseResource
0x140003ede  nop     dword ptr [rax+rax+00h]
0x140003ee3  mov     rcx, r14; FileHandle
0x140003ee6  call    cs:__imp_FltClose
0x140003eed  nop     dword ptr [rax+rax+00h]
0x140003ef2  mov     rcx, rsi; Resource
0x140003ef5  call    cs:__imp_FltAcquireResourceExclusive
0x140003efc  nop     dword ptr [rax+rax+00h]
0x140003f01  mov     rdx, rdi; Buffer
0x140003f04  mov     rcx, rbp; Table
0x140003f07  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140003f0e  nop     dword ptr [rax+rax+00h]
0x140003f13  mov     dil, 1
0x140003f16  jmp     short loc_140003F27
0x140003f18  xor     dil, dil
0x140003f1b  lea     rcx, aHandletableEnt; "HandleTable entry found without user-op"...
0x140003f22  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140003f27  mov     dl, dil; Restart
0x140003f2a  mov     rcx, rbp; Table
0x140003f2d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140003f34  nop     dword ptr [rax+rax+00h]
0x140003f39  mov     rdi, rax
0x140003f3c  test    rax, rax
0x140003f3f  jnz     loc_140003EBB
0x140003f45  mov     rcx, rsi; Resource
0x140003f48  call    cs:__imp_FltReleaseResource
0x140003f4f  nop     dword ptr [rax+rax+00h]
0x140003f54  mov     rcx, rbp; Table
0x140003f57  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140003f5e  nop     dword ptr [rax+rax+00h]
0x140003f63  test    al, al
0x140003f65  jnz     short loc_140003F6C
0x140003f67  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003f6c  mov     rcx, rsi; Resource
0x140003f6f  call    cs:__imp_ExDeleteResourceLite
0x140003f76  nop     dword ptr [rax+rax+00h]
0x140003f7b  lea     rcx, [rbx+1A0h]; Table
0x140003f82  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140003f89  nop     dword ptr [rax+rax+00h]
0x140003f8e  test    al, al
0x140003f90  jnz     short loc_140003F97
0x140003f92  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003f97  lea     rcx, [rbx+138h]; Resource
0x140003f9e  call    cs:__imp_ExDeleteResourceLite
0x140003fa5  nop     dword ptr [rax+rax+00h]
0x140003faa  lea     rdi, [rbx+50h]
0x140003fae  cmp     qword ptr [rdi], 0
0x140003fb2  jz      short loc_140003FD1
0x140003fb4  mov     rcx, cs:Globals; Filter
0x140003fbb  mov     rdx, rdi; ClientPort
0x140003fbe  call    cs:__imp_FltCloseClientPort
0x140003fc5  nop     dword ptr [rax+rax+00h]
0x140003fca  mov     qword ptr [rdi], 0
0x140003fd1  mov     rcx, [rbx+20h]; Object
0x140003fd5  test    rcx, rcx
0x140003fd8  jz      short loc_140003FE6
0x140003fda  call    cs:__imp_ObfDereferenceObject
0x140003fe1  nop     dword ptr [rax+rax+00h]
0x140003fe6  mov     eax, [rbx+38h]
0x140003fe9  test    al, 1
0x140003feb  jz      loc_1400040A8
0x140003ff1  lea     rdx, [rsp+78h+arg_0]
0x140003ff9  mov     [rsp+78h+arg_0], 0
0x140004004  mov     rcx, rbx
0x140004007  call    PrjfClearNegativePathCache
0x14000400c  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140004012  lea     rax, WPP_RECORDER_INITIALIZED
0x140004019  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004020  setnz   r8b
0x140004024  and     dl, 2
0x140004027  jnz     short loc_14000402E
0x140004029  test    r8b, r8b
0x14000402c  jz      short loc_140004082
0x14000402e  mov     eax, [rsp+78h+arg_0]
0x140004035  mov     ecx, 409h
0x14000403a  mov     r9, cs:WPP_GLOBAL_Control
0x140004041  mov     [rsp+78h+var_28], eax
0x140004045  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000404c  mov     [rsp+78h+var_30], 92Bh
0x140004054  mov     [rsp+78h+var_38], rax
0x140004059  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140004060  mov     r9, [r9+40h]
0x140004064  mov     [rsp+78h+var_40], rax
0x140004069  mov     [rsp+78h+var_48], 2Ah ; '*'
0x140004070  mov     [rsp+78h+var_50], 9
0x140004078  mov     [rsp+78h+var_58], 4
0x14000407d  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140004082  lea     rcx, [rbx+220h]; Resource
0x140004089  call    cs:__imp_ExDeleteResourceLite
0x140004090  nop     dword ptr [rax+rax+00h]
0x140004095  lea     rcx, [rbx+288h]; HashTable
0x14000409c  call    cs:__imp_RtlDeleteHashTable
0x1400040a3  nop     dword ptr [rax+rax+00h]
0x1400040a8  cmp     qword ptr [rbx+2B0h], 0
0x1400040b0  jz      short loc_1400040BA
0x1400040b2  mov     rcx, rbx
0x1400040b5  call    PrjfClearMappingTable
0x1400040ba  lea     rcx, [rbx+2B8h]; Resource
0x1400040c1  call    cs:__imp_ExDeleteResourceLite
0x1400040c8  nop     dword ptr [rax+rax+00h]
0x1400040cd  mov     edx, 63754A50h; Tag
0x1400040d2  mov     rcx, rbx; P
0x1400040d5  call    cs:__imp_ExFreePoolWithTag
0x1400040dc  nop     dword ptr [rax+rax+00h]
0x1400040e1  lea     r11, [rsp+78h+var_18]
0x1400040e6  mov     rbx, [r11+28h]
0x1400040ea  mov     rbp, [r11+30h]
0x1400040ee  mov     rsp, r11
0x1400040f1  pop     r14
0x1400040f3  pop     rdi
0x1400040f4  pop     rsi
0x1400040f5  retn
```

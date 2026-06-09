# Command_SendCommand

- ea: `0x1400216b8`
- end: `0x14002182a`
- name: `Command_SendCommand`
- size: `370`
- prototype: ``
- caller_count: `25`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140001174`
- `0x1400017b8`
- `0x1400018b0`
- `0x140001ab4`
- `0x140023164`
- `0x140023f70`
- `0x1400247c8`
- `0x140024ae0`
- `0x140025720`
- `0x140029b70`
- `0x14002a148`
- `0x14002a734`
- `0x14002aea0`
- `0x140031eb4`
- `0x140033094`
- `0x140033350`
- `0x140036540`
- `0x14003de14`
- `0x140047e70`
- `0x1400484c0`
- `0x14004df60`
- `0x14004ec28`
- `0x14004eee8`
- `0x14004ef78`
- `0x14004f320`

## callees

- `0x140010d40`
- `0x1400110e0`
- `0x14001fb30`
- `0x1400216b8`
- `0x1400218a0`
- `0x1400219b0`
- `0x140021a74`
- `0x14003e8c8`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400216db`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400216db`

## pseudocode

```c
__int64 __fastcall Command_SendCommand(__int64 a1, __int64 a2)
{
  int v4; // edx
  char v5; // si
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rdx
  unsigned int v10; // ebp
  __int64 (__fastcall *v11)(__int64, __int64); // rax

  if ( !(unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(a1 + 8)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 4;
      WPP_RECORDER_SF_qL(
        *(_QWORD *)(a1 + 16),
        v4,
        7,
        58,
        (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
        a2,
        (unsigned __int8)HIBYTE(*(_WORD *)(a2 + 36)) >> 2);
    }
    *(_BYTE *)(a2 + 60) = 0;
    goto LABEL_11;
  }
  v5 = 0;
  if ( KeGetCurrentIrql() == 2 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE *)(v6 + 1041) )
    {
      Controller_LowerAndTrackIrql(v6);
      v5 = 1;
    }
  }
  DynamicLock_Acquire(*(_QWORD *)(a1 + 112));
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL);
  if ( v7 )
  {
    v11 = *(__int64 (__fastcall **)(__int64, __int64))(v7 + 16);
    if ( v11 )
    {
      v10 = v11(v7, a2);
      if ( v10 != 4 )
      {
        DynamicLock_Release(*(_QWORD *)(a1 + 112));
        if ( v5 )
          Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
        v9 = v10;
        return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a2 + 40))(a2, v9, 0);
      }
    }
  }
  if ( *(_DWORD *)(a1 + 36) == 5 )
  {
    DynamicLock_Release(*(_QWORD *)(a1 + 112));
    if ( v5 )
      Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
LABEL_11:
    v9 = 3;
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a2 + 40))(a2, v9, 0);
  }
  Command_InternalSendCommand(a1);
  result = DynamicLock_Release(*(_QWORD *)(a1 + 112));
  if ( v5 )
    return Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
  return result;
}

```

## disassembly

```asm
0x1400216b8  push    rbx
0x1400216ba  push    rbp
0x1400216bb  push    rsi
0x1400216bc  push    rdi
0x1400216bd  sub     rsp, 48h
0x1400216c1  mov     rbx, rcx
0x1400216c4  mov     rdi, rdx
0x1400216c7  mov     rcx, [rcx+8]
0x1400216cb  call    Controller_IsControllerAccessible
0x1400216d0  test    al, al
0x1400216d2  jz      loc_140021784
0x1400216d8  xor     sil, sil
0x1400216db  call    cs:__imp_KeGetCurrentIrql
0x1400216e2  nop     dword ptr [rax+rax+00h]
0x1400216e7  cmp     al, 2
0x1400216e9  jnz     short loc_1400216FC
0x1400216eb  mov     rcx, [rbx+8]
0x1400216ef  cmp     [rcx+411h], sil
0x1400216f6  jnz     loc_1400217E4
0x1400216fc  mov     rcx, [rbx+70h]
0x140021700  call    DynamicLock_Acquire
0x140021705  mov     rax, [rbx+8]
0x140021709  mov     rcx, [rax+0A8h]
0x140021710  test    rcx, rcx
0x140021713  jnz     loc_1400217F1
0x140021719  cmp     dword ptr [rbx+24h], 5
0x14002171d  jz      short loc_140021746
0x14002171f  mov     rdx, rdi
0x140021722  mov     rcx, rbx
0x140021725  call    Command_InternalSendCommand
0x14002172a  mov     rcx, [rbx+70h]
0x14002172e  call    DynamicLock_Release
0x140021733  test    sil, sil
0x140021736  jnz     loc_14002180E
0x14002173c  add     rsp, 48h
0x140021740  pop     rdi
0x140021741  pop     rsi
0x140021742  pop     rbp
0x140021743  pop     rbx
0x140021744  retn
0x140021746  mov     rcx, [rbx+70h]
0x14002174a  call    DynamicLock_Release
0x14002174f  test    sil, sil
0x140021752  jnz     loc_14002181C
0x140021758  mov     edx, 3
0x14002175d  jmp     short loc_140021773
0x14002175f  mov     rcx, [rbx+70h]
0x140021763  call    DynamicLock_Release
0x140021768  test    sil, sil
0x14002176b  jnz     loc_140021800
0x140021771  mov     edx, ebp
0x140021773  mov     rax, [rdi+28h]
0x140021777  xor     r8d, r8d
0x14002177a  mov     rcx, rdi
0x14002177d  call    _guard_dispatch_icall
0x140021782  jmp     short loc_14002173C
0x140021784  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002178b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021792  jnz     short loc_1400217AF
0x140021794  mov     byte ptr [rdi+3Ch], 0
0x140021798  jmp     short loc_140021758
0x14002179a  mov     rdx, rdi
0x14002179d  call    _guard_dispatch_icall
0x1400217a2  mov     ebp, eax
0x1400217a4  cmp     eax, 4
0x1400217a7  jz      loc_140021719
0x1400217ad  jmp     short loc_14002175F
0x1400217af  mov     eax, [rdi+24h]
0x1400217b2  mov     r9d, 3Ah ; ':'
0x1400217b8  mov     rcx, [rbx+10h]
0x1400217bc  mov     dl, 4
0x1400217be  shr     eax, 0Ah
0x1400217c1  and     eax, 3Fh
0x1400217c4  mov     [rsp+68h+var_38], eax
0x1400217c8  lea     r8d, [r9-33h]
0x1400217cc  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x1400217d3  mov     [rsp+68h+var_40], rdi
0x1400217d8  mov     [rsp+68h+var_48], rax
0x1400217dd  call    WPP_RECORDER_SF_qL
0x1400217e2  jmp     short loc_140021794
0x1400217e4  call    Controller_LowerAndTrackIrql
0x1400217e9  mov     sil, 1
0x1400217ec  jmp     loc_1400216FC
0x1400217f1  mov     rax, [rcx+10h]
0x1400217f5  test    rax, rax
0x1400217f8  jz      loc_140021719
0x1400217fe  jmp     short loc_14002179A
0x140021800  mov     rcx, [rbx+8]
0x140021804  call    Controller_RaiseAndTrackIrql
0x140021809  jmp     loc_140021771
0x14002180e  mov     rcx, [rbx+8]
0x140021812  call    Controller_RaiseAndTrackIrql
0x140021817  jmp     loc_14002173C
0x14002181c  mov     rcx, [rbx+8]
0x140021820  call    Controller_RaiseAndTrackIrql
0x140021825  jmp     loc_140021758
```

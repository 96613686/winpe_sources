# FeRefCalloutFlowContext

- ea: `0x14000b0c0`
- end: `0x14000b2a3`
- name: `FeRefCalloutFlowContext`
- size: `483`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000ab30`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14000b0c0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b11e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b1b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b11e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b1b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b0e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b0e3`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b101`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b101`
- `NDIS!NdisReleaseRWLock` at `0x14000b1e2`
- `NDIS!NdisReleaseRWLock` at `0x14000b1e2`

## pseudocode

```c
__int64 __fastcall FeRefCalloutFlowContext(unsigned int a1)
{
  PNPAGED_LOOKASIDE_LIST v1; // rdi
  __int64 v2; // rsi
  KIRQL CurrentIrql; // bl
  __int64 v4; // rcx
  __int64 v5; // rdx
  void *v6; // rax
  __int64 v7; // rbx
  PNPAGED_LOOKASIDE_LIST v8; // rdi
  _DWORD *v9; // r8
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  v1 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = a1;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v1[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v4 = gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0);
    v5 = *(_QWORD *)(v4 + gWfpPerProContext);
    *(_QWORD *)(v5 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v5 = 4;
  }
  if ( (unsigned int)v2 >= gWfpGlobal[3].L.FreeMisses
    || (v4 = 144 * v2, v6 = (void *)(144 * v2 + *(_QWORD *)&gWfpGlobal[3].L.Tag), !*((_DWORD *)v6 + 1)) )
  {
    v6 = gFeCallout;
  }
  if ( v6 == gFeCallout )
  {
    v7 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"FeRefCalloutFlowContext",
        13);
    }
  }
  else if ( *((_DWORD *)v6 + 2) )
  {
    v7 = WfpReportSysErrorAsNtStatus(v4, "FeRefCalloutFlowContext", -1073741811, 1);
  }
  else
  {
    v7 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v6 + 15);
  }
  v8 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v9 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v9 == 4 )
      *v9 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v8[1].L.ListHead.Alignment, &LockState);
  if ( v7 )
    WfpReportError(v7, "FeRefCalloutFlowContext");
  return v7;
}

```

## disassembly

```asm
0x14000b0c0  mov     [rsp+arg_8], rbx
0x14000b0c5  mov     [rsp+arg_10], rsi
0x14000b0ca  push    rdi
0x14000b0cb  sub     rsp, 30h
0x14000b0cf  mov     rdi, cs:gWfpGlobal
0x14000b0d6  xor     eax, eax
0x14000b0d8  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x14000b0dd  mov     [rsp+38h+LockState.Flags], al
0x14000b0e1  mov     esi, ecx
0x14000b0e3  call    cs:__imp_KeGetCurrentIrql
0x14000b0ea  nop     dword ptr [rax+rax+00h]
0x14000b0ef  mov     rcx, [rdi+80h]; Lock
0x14000b0f6  lea     rdx, [rsp+38h+LockState]; LockState
0x14000b0fb  xor     r8d, r8d; Flags
0x14000b0fe  movzx   ebx, al
0x14000b101  call    cs:__imp_NdisAcquireRWLockRead
0x14000b108  nop     dword ptr [rax+rax+00h]
0x14000b10d  cmp     bl, 2
0x14000b110  jz      short loc_14000B152
0x14000b112  cmp     cs:gWfpPerProContext, 0
0x14000b11a  jz      short loc_14000B152
0x14000b11c  xor     ecx, ecx; ProcNumber
0x14000b11e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b125  nop     dword ptr [rax+rax+00h]
0x14000b12a  imul    eax, cs:gWfpPerProContextSize
0x14000b131  mov     ecx, eax
0x14000b133  mov     rax, cs:gWfpPerProContext
0x14000b13a  mov     rdx, [rcx+rax]
0x14000b13e  mov     rax, ds:0FFFFF78000000008h
0x14000b148  mov     [rdx+8], rax
0x14000b14c  mov     dword ptr [rdx], 4
0x14000b152  mov     rdx, cs:gWfpGlobal
0x14000b159  cmp     esi, [rdx+1A0h]
0x14000b15f  jnb     short loc_14000B179
0x14000b161  mov     rax, [rdx+1A8h]
0x14000b168  lea     rcx, [rsi+rsi*8]
0x14000b16c  shl     rcx, 4
0x14000b170  add     rax, rcx
0x14000b173  cmp     dword ptr [rax+4], 0
0x14000b177  jnz     short loc_14000B180
0x14000b179  mov     rax, cs:gFeCallout
0x14000b180  cmp     rax, cs:gFeCallout
0x14000b187  jz      loc_14000B214
0x14000b18d  cmp     dword ptr [rax+8], 0
0x14000b191  jnz     loc_14000B26E
0x14000b197  xor     ebx, ebx
0x14000b199  lock inc dword ptr [rax+3Ch]
0x14000b19d  cmp     cs:gWfpPerProContext, 0
0x14000b1a5  mov     rdi, cs:gWfpGlobal
0x14000b1ac  jz      short loc_14000B1D6
0x14000b1ae  xor     ecx, ecx; ProcNumber
0x14000b1b0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b1b7  nop     dword ptr [rax+rax+00h]
0x14000b1bc  imul    eax, cs:gWfpPerProContextSize
0x14000b1c3  mov     ecx, eax
0x14000b1c5  mov     rax, cs:gWfpPerProContext
0x14000b1cc  mov     r8, [rcx+rax]
0x14000b1d0  cmp     dword ptr [r8], 4
0x14000b1d4  jz      short loc_14000B20B
0x14000b1d6  mov     rcx, [rdi+80h]; Lock
0x14000b1dd  lea     rdx, [rsp+38h+LockState]; LockState
0x14000b1e2  call    cs:__imp_NdisReleaseRWLock
0x14000b1e9  nop     dword ptr [rax+rax+00h]
0x14000b1ee  test    rbx, rbx
0x14000b1f1  jnz     loc_14000B28F
0x14000b1f7  mov     rsi, [rsp+38h+arg_10]
0x14000b1fc  mov     rax, rbx
0x14000b1ff  mov     rbx, [rsp+38h+arg_8]
0x14000b204  add     rsp, 30h
0x14000b208  pop     rdi
0x14000b209  retn
0x14000b20b  mov     dword ptr [r8], 0
0x14000b212  jmp     short loc_14000B1D6
0x14000b214  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b21b  lea     rax, WPP_GLOBAL_Control
0x14000b222  mov     rbx, 0FFFFFFFFC000000Dh
0x14000b229  cmp     rcx, rax
0x14000b22c  jz      loc_14000B19D
0x14000b232  cmp     byte ptr [rcx+29h], 2
0x14000b236  jb      loc_14000B19D
0x14000b23c  test    dword ptr [rcx+2Ch], 1000h
0x14000b243  jz      loc_14000B19D
0x14000b249  mov     rcx, [rcx+18h]
0x14000b24d  lea     r9, aFerefcalloutfl; "FeRefCalloutFlowContext"
0x14000b254  mov     edx, 0Ah
0x14000b259  mov     [rsp+38h+var_18], ebx
0x14000b25d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000b264  call    WPP_SF_sd
0x14000b269  jmp     loc_14000B19D
0x14000b26e  mov     r9d, 1
0x14000b274  lea     rdx, aFerefcalloutfl; "FeRefCalloutFlowContext"
0x14000b27b  mov     r8, 0FFFFFFFFC000000Dh
0x14000b282  call    WfpReportSysErrorAsNtStatus
0x14000b287  mov     rbx, rax
0x14000b28a  jmp     loc_14000B19D
0x14000b28f  lea     rdx, aFerefcalloutfl; "FeRefCalloutFlowContext"
0x14000b296  mov     rcx, rbx
0x14000b299  call    WfpReportError
0x14000b29e  jmp     loc_14000B1F7
```

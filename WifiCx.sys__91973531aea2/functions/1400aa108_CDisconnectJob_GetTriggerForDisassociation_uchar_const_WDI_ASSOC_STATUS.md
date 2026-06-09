# CDisconnectJob::GetTriggerForDisassociation(uchar * const,_WDI_ASSOC_STATUS)

- ea: `0x1400aa108`
- end: `0x1400aa1b8`
- name: `?GetTriggerForDisassociation@CDisconnectJob@@QEAA?AW4_WFC_DISCONNECT_TRIGGER@@QEAEW4_WDI_ASSOC_STATUS@@@Z`
- size: `176`
- prototype: `enum _WFC_DISCONNECT_TRIGGER __high(unsigned __int8 *const, enum _WDI_ASSOC_STATUS)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400295b4`

## callees

- `0x14001e2c0`
- `0x1400aa108`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400aa138`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa138`

## pseudocode

```c
__int64 __fastcall CDisconnectJob::GetTriggerForDisassociation(__int64 a1, const void *a2)
{
  unsigned int v3; // edi
  int v4; // edx
  int v5; // r8d
  int v7; // [rsp+38h] [rbp-10h]

  v3 = 0;
  if ( *(_BYTE *)(a1 + 1112) && RtlCompareMemory(a2, (const void *)(a1 + 1092), 6u) == 6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v7 = *(_DWORD *)(a1 + 1116);
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          v5,
          474,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          a1,
          *(_DWORD *)(a1 + 16),
          v7);
      }
    }
    return *(unsigned int *)(a1 + 1116);
  }
  return v3;
}

```

## disassembly

```asm
0x1400aa108  mov     [rsp+arg_0], rbx
0x1400aa10d  mov     [rsp+arg_8], rsi
0x1400aa112  push    rdi
0x1400aa113  sub     rsp, 40h
0x1400aa117  xor     esi, esi
0x1400aa119  mov     rax, rdx
0x1400aa11c  mov     rbx, rcx
0x1400aa11f  mov     edi, esi
0x1400aa121  cmp     [rcx+458h], sil
0x1400aa128  jz      short loc_1400AA1A5
0x1400aa12a  lea     rdx, [rcx+444h]; Source2
0x1400aa131  mov     rcx, rax; Source1
0x1400aa134  lea     r8d, [rsi+6]; Length
0x1400aa138  call    cs:__imp_RtlCompareMemory
0x1400aa13f  nop     dword ptr [rax+rax+00h]
0x1400aa144  cmp     rax, 6
0x1400aa148  jnz     short loc_1400AA1A5
0x1400aa14a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400aa151  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400aa158  jz      short loc_1400AA19F
0x1400aa15a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa161  mov     dl, 5
0x1400aa163  cmp     [rcx+29h], dl
0x1400aa166  jnb     short loc_1400AA16E
0x1400aa168  cmp     [rcx+48h], si
0x1400aa16c  jz      short loc_1400AA19F
0x1400aa16e  mov     eax, [rbx+45Ch]
0x1400aa174  mov     r9d, 1DAh
0x1400aa17a  mov     rcx, [rcx+40h]
0x1400aa17e  mov     [rsp+48h+var_10], eax
0x1400aa182  mov     eax, [rbx+10h]
0x1400aa185  mov     [rsp+48h+var_18], eax
0x1400aa189  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400aa190  mov     [rsp+48h+var_20], rbx
0x1400aa195  mov     [rsp+48h+var_28], rax
0x1400aa19a  call    WPP_RECORDER_SF_qDD
0x1400aa19f  mov     edi, [rbx+45Ch]
0x1400aa1a5  mov     rbx, [rsp+48h+arg_0]
0x1400aa1aa  mov     eax, edi
0x1400aa1ac  mov     rsi, [rsp+48h+arg_8]
0x1400aa1b1  add     rsp, 40h
0x1400aa1b5  pop     rdi
0x1400aa1b6  retn
```

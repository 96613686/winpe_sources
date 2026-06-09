# CDisconnectJob::GetTriggerForDisassociation(uchar * const,_WDI_ASSOC_STATUS)

- ea: `0x1400c2ba8`
- end: `0x1400c2c58`
- name: `?GetTriggerForDisassociation@CDisconnectJob@@QEAA?AW4_WFC_DISCONNECT_TRIGGER@@QEAEW4_WDI_ASSOC_STATUS@@@Z`
- size: `176`
- prototype: `enum _WFC_DISCONNECT_TRIGGER(CDisconnectJob *__hidden this, unsigned __int8 *const, enum _WDI_ASSOC_STATUS)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140046844`

## callees

- `0x140010730`
- `0x1400c2ba8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c2bd8`
- `ntoskrnl!RtlCompareMemory` at `0x1400c2bd8`

## pseudocode

```c
__int64 __fastcall CDisconnectJob::GetTriggerForDisassociation(
        CDisconnectJob *this,
        unsigned __int8 *const a2,
        enum _WDI_ASSOC_STATUS a3)
{
  unsigned int v4; // edi
  int v5; // edx
  int v6; // r8d

  v4 = 0;
  if ( this->m_WaitingForDisassociate && RtlCompareMemory(a2, this->m_NdisDisassocParameters.MacAddr, 6u) == 6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          v6,
          352,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          this->m_DisconnectTrigger);
    }
    return (unsigned int)this->m_DisconnectTrigger;
  }
  return v4;
}

```

## disassembly

```asm
0x1400c2ba8  mov     [rsp+arg_0], rbx
0x1400c2bad  mov     [rsp+arg_8], rsi
0x1400c2bb2  push    rdi
0x1400c2bb3  sub     rsp, 40h
0x1400c2bb7  xor     esi, esi
0x1400c2bb9  mov     rax, rdx
0x1400c2bbc  mov     rbx, rcx
0x1400c2bbf  mov     edi, esi
0x1400c2bc1  cmp     [rcx+440h], sil
0x1400c2bc8  jz      short loc_1400C2C45
0x1400c2bca  lea     rdx, [rcx+42Ch]; Source2
0x1400c2bd1  mov     rcx, rax; Source1
0x1400c2bd4  lea     r8d, [rsi+6]; Length
0x1400c2bd8  call    cs:__imp_RtlCompareMemory
0x1400c2bdf  nop     dword ptr [rax+rax+00h]
0x1400c2be4  cmp     rax, 6
0x1400c2be8  jnz     short loc_1400C2C45
0x1400c2bea  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c2bf1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c2bf8  jz      short loc_1400C2C3F
0x1400c2bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2c01  mov     dl, 5
0x1400c2c03  cmp     [rcx+29h], dl
0x1400c2c06  jnb     short loc_1400C2C0E
0x1400c2c08  cmp     [rcx+48h], si
0x1400c2c0c  jz      short loc_1400C2C3F
0x1400c2c0e  mov     eax, [rbx+444h]
0x1400c2c14  mov     r9d, 160h
0x1400c2c1a  mov     rcx, [rcx+40h]
0x1400c2c1e  mov     [rsp+48h+var_10], eax
0x1400c2c22  mov     eax, [rbx+10h]
0x1400c2c25  mov     [rsp+48h+var_18], eax
0x1400c2c29  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400c2c30  mov     [rsp+48h+var_20], rbx
0x1400c2c35  mov     [rsp+48h+var_28], rax
0x1400c2c3a  call    WPP_RECORDER_SF_qDL
0x1400c2c3f  mov     edi, [rbx+444h]
0x1400c2c45  mov     rbx, [rsp+48h+arg_0]
0x1400c2c4a  mov     eax, edi
0x1400c2c4c  mov     rsi, [rsp+48h+arg_8]
0x1400c2c51  add     rsp, 40h
0x1400c2c55  pop     rdi
0x1400c2c56  retn
```

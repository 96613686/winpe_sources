# CTxEntryTable::InitializeTxEntry(ushort,ushort,ushort,_WDI_MAC_ADDRESS *)

- ea: `0x14004e080`
- end: `0x14004e305`
- name: `?InitializeTxEntry@CTxEntryTable@@QEAAHGGGPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `645`
- prototype: `__int64 __usercall@<rax>(CTxEntryTable *__hidden this@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, struct _WDI_MAC_ADDRESS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004da7c`
- `0x14004de9c`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14004e080`
- `0x14004e76c`
- `0x14004e87c`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004e13f`
- `ntoskrnl!RtlCompareMemory` at `0x14004e13f`

## pseudocode

```c
__int64 __fastcall CTxEntryTable::InitializeTxEntry(
        CTxEntryTable *this,
        int a2,
        __int16 a3,
        __int16 a4,
        struct _WDI_MAC_ADDRESS *Source1)
{
  __int16 v8; // bp
  unsigned int v9; // ebx
  struct _WFC_TX_ENTRY *v10; // rax
  int v11; // r8d
  struct _WFC_TX_ENTRY *v12; // rcx
  unsigned int v14; // edx
  int v15; // r8d
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+28h] [rbp-70h]
  int Source2; // [rsp+50h] [rbp-48h] BYREF
  __int16 v20; // [rsp+54h] [rbp-44h]

  Source2 = 0;
  v20 = 0;
  v8 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      21,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  if ( !Source1 || v8 == -1 || a3 == -1 || RtlCompareMemory(Source1, &Source2, 6u) == 6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_WORD)a2,
        1,
        22,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    goto LABEL_15;
  }
  v9 = 0;
  if ( !this->m_pTxEntryTable )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v9;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      23,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    goto LABEL_16;
  }
  v10 = CTxEntryTable::AssignTxEntry(this, v8);
  v12 = v10;
  if ( !v10 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDD_MAC_(WPP_GLOBAL_Control->DeviceExtension, a2, v11, 24, v17, v8, a3, a4, (__int64)Source1);
    }
LABEL_15:
    v9 = -1073741823;
    goto LABEL_16;
  }
  v10->PeerId = a4;
  v14 = 0;
  v10->PortId = a3;
  v10->MacAddr = *Source1;
  v10->InOrderNotifPendingBitmask = 0;
  v15 = this->m_QueueingMode != PORT_QUEUEING ? 2 : 0;
  do
  {
    v16 = (int)v14++;
    v12->TidPauseState[v16] = v15;
  }
  while ( v14 < 0x19 );
  v12->TxEntryState = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return v9;
  LOBYTE(v14) = 4;
  WPP_RECORDER_SF_DDD_MAC_(WPP_GLOBAL_Control->DeviceExtension, v14, v15, 25, v17, v8, a3, a4, (__int64)Source1);
LABEL_16:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v18) = v9;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      26,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v18);
  }
  return v9;
}

```

## disassembly

```asm
0x14004e080  mov     [rsp+arg_10], rbx
0x14004e085  push    rbp
0x14004e086  push    rsi
0x14004e087  push    rdi
0x14004e088  push    r12
0x14004e08a  push    r13
0x14004e08c  push    r14
0x14004e08e  push    r15
0x14004e090  sub     rsp, 60h
0x14004e094  mov     rax, cs:__security_cookie
0x14004e09b  xor     rax, rsp
0x14004e09e  mov     [rsp+98h+var_40], rax
0x14004e0a3  mov     rdi, [rsp+98h+Source1]
0x14004e0ab  xor     eax, eax
0x14004e0ad  mov     [rsp+98h+Source2], eax
0x14004e0b1  mov     rsi, rcx
0x14004e0b4  mov     [rsp+98h+var_44], ax
0x14004e0b9  movzx   r15d, r9w
0x14004e0bd  movzx   r14d, r8w
0x14004e0c1  movzx   ebp, dx
0x14004e0c4  xor     r12d, r12d; __annotation("TMF:",
0x14004e0c7  lea     r13, WPP_RECORDER_INITIALIZED
0x14004e0ce  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e0d5  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14004e0dc  lea     ebx, [r12+1]
0x14004e0e1  jz      short loc_14004E110
0x14004e0e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e0ea  cmp     byte ptr [rcx+29h], 5
0x14004e0ee  jnb     short loc_14004E0F7
0x14004e0f0  cmp     [rcx+48h], r12w
0x14004e0f5  jz      short loc_14004E110
0x14004e0f7  mov     rcx, [rcx+40h]
0x14004e0fb  mov     r9d, 15h
0x14004e101  mov     r8d, ebx
0x14004e104  mov     [rsp+98h+var_78], rax
0x14004e109  mov     dl, 5
0x14004e10b  call    WPP_RECORDER_SF_
0x14004e110  test    rdi, rdi
0x14004e113  jz      loc_14004E2CC
0x14004e119  mov     eax, 0FFFFh
0x14004e11e  cmp     bp, ax
0x14004e121  jz      loc_14004E2CC
0x14004e127  cmp     r14w, ax
0x14004e12b  jz      loc_14004E2CC
0x14004e131  mov     r8d, 6; Length
0x14004e137  lea     rdx, [rsp+98h+Source2]; Source2
0x14004e13c  mov     rcx, rdi; Source1
0x14004e13f  call    cs:__imp_RtlCompareMemory
0x14004e146  nop     dword ptr [rax+rax+00h]
0x14004e14b  cmp     rax, 6
0x14004e14f  jz      loc_14004E2CC
0x14004e155  mov     ebx, r12d
0x14004e158  cmp     [rsi+8], r12
0x14004e15c  jnz     short loc_14004E195
0x14004e15e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14004e165  jz      loc_14004E225
0x14004e16b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e172  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14004e179  mov     r9d, 17h
0x14004e17f  mov     [rsp+98h+var_78], rdi
0x14004e184  mov     dl, 2
0x14004e186  mov     rcx, [rcx+40h]
0x14004e18a  lea     r8d, [r9-16h]
0x14004e18e  call    WPP_RECORDER_SF_
0x14004e193  jmp     short loc_14004E1EA
0x14004e195  movzx   edx, bp; unsigned __int16
0x14004e198  mov     rcx, rsi; this
0x14004e19b  call    ?AssignTxEntry@CTxEntryTable@@AEAAPEAU_WFC_TX_ENTRY@@G@Z; CTxEntryTable::AssignTxEntry(ushort)
0x14004e1a0  mov     rcx, rax
0x14004e1a3  test    rax, rax
0x14004e1a6  jnz     loc_14004E24D
0x14004e1ac  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14004e1b3  jz      short loc_14004E1DE
0x14004e1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e1bc  lea     r9d, [rax+18h]
0x14004e1c0  mov     [rsp+98h+var_58], rdi
0x14004e1c5  mov     dl, 2
0x14004e1c7  mov     [rsp+98h+var_60], r15d
0x14004e1cc  mov     [rsp+98h+var_68], r14d
0x14004e1d1  mov     rcx, [rcx+40h]
0x14004e1d5  mov     dword ptr [rsp+98h+var_70], ebp
0x14004e1d9  call    WPP_RECORDER_SF_DDD_MAC_
0x14004e1de  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14004e1e5  mov     ebx, 0C0000001h
0x14004e1ea  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14004e1f1  jz      short loc_14004E225
0x14004e1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e1fa  cmp     byte ptr [rcx+29h], 5
0x14004e1fe  jnb     short loc_14004E207
0x14004e200  cmp     [rcx+48h], r12w
0x14004e205  jz      short loc_14004E225
0x14004e207  mov     rcx, [rcx+40h]
0x14004e20b  mov     r9d, 1Ah
0x14004e211  mov     dword ptr [rsp+98h+var_70], ebx
0x14004e215  mov     dl, 5
0x14004e217  mov     [rsp+98h+var_78], rdi
0x14004e21c  lea     r8d, [r9-19h]
0x14004e220  call    WPP_RECORDER_SF_D
0x14004e225  mov     eax, ebx
0x14004e227  mov     rcx, [rsp+98h+var_40]
0x14004e22c  xor     rcx, rsp; StackCookie
0x14004e22f  call    __security_check_cookie
0x14004e234  mov     rbx, [rsp+98h+arg_10]
0x14004e23c  add     rsp, 60h
0x14004e240  pop     r15
0x14004e242  pop     r14
0x14004e244  pop     r13
0x14004e246  pop     r12
0x14004e248  pop     rdi
0x14004e249  pop     rsi
0x14004e24a  pop     rbp
0x14004e24b  retn
0x14004e24d  mov     [rax+6], r15w
0x14004e252  mov     edx, r12d
0x14004e255  mov     [rax+4], r14w
0x14004e25a  mov     r9d, 19h
0x14004e260  mov     eax, [rdi]
0x14004e262  mov     [rcx+0Ch], eax
0x14004e265  movzx   eax, word ptr [rdi+4]
0x14004e269  mov     [rcx+10h], ax
0x14004e26d  mov     [rcx+14h], r12d
0x14004e271  mov     eax, [rsi+10h]
0x14004e274  dec     eax
0x14004e276  neg     eax
0x14004e278  sbb     r8d, r8d
0x14004e27b  and     r8d, 2
0x14004e27f  movsxd  rax, edx
0x14004e282  inc     edx
0x14004e284  mov     [rcx+rax*4+20h], r8d
0x14004e289  cmp     edx, r9d
0x14004e28c  jb      short loc_14004E27F
0x14004e28e  mov     [rcx+8], r12d
0x14004e292  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14004e299  jz      short loc_14004E225
0x14004e29b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2a2  mov     dl, 4
0x14004e2a4  mov     [rsp+98h+var_58], rdi
0x14004e2a9  mov     [rsp+98h+var_60], r15d
0x14004e2ae  mov     [rsp+98h+var_68], r14d
0x14004e2b3  mov     rcx, [rcx+40h]
0x14004e2b7  mov     dword ptr [rsp+98h+var_70], ebp
0x14004e2bb  call    WPP_RECORDER_SF_DDD_MAC_
0x14004e2c0  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14004e2c7  jmp     loc_14004E1EA
0x14004e2cc  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14004e2d3  jz      loc_14004E1DE
0x14004e2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2e0  lea     rdi, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14004e2e7  mov     r9d, 16h
0x14004e2ed  mov     [rsp+98h+var_78], rdi
0x14004e2f2  mov     r8d, ebx
0x14004e2f5  mov     dl, 2
0x14004e2f7  mov     rcx, [rcx+40h]
0x14004e2fb  call    WPP_RECORDER_SF_
0x14004e300  jmp     loc_14004E1E5
```

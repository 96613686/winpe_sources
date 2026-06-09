# CPeerTable::AddPeer(ushort,ushort,_WDI_MAC_ADDRESS *)

- ea: `0x14004e30c`
- end: `0x14004e57c`
- name: `?AddPeer@CPeerTable@@QEAAHGGPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(CPeerTable *__hidden this, unsigned __int16, unsigned __int16, struct _WDI_MAC_ADDRESS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004dc60`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14004e30c`
- `0x14004ea6c`
- `0x14004eb74`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004e3c0`
- `ntoskrnl!RtlCompareMemory` at `0x14004e3c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e4a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e4a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e474`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e474`

## pseudocode

```c
__int64 __fastcall CPeerTable::AddPeer(CPeerTable *this, int a2, __int16 a3, struct _WDI_MAC_ADDRESS *a4)
{
  __int16 v7; // r15
  unsigned int v8; // esi
  int v9; // r9d
  CNdisSpinLock *m_PeerTableLock; // rdi
  KIRQL v11; // al
  struct _WFC_PEER_TABLE_ENTRY *v12; // rax
  KIRQL OldIrql; // dl
  struct _WFC_PEER_TABLE_ENTRY *v14; // rbx
  int v15; // r8d
  __int64 v17; // [rsp+28h] [rbp-60h]
  int Source2; // [rsp+40h] [rbp-48h] BYREF
  __int16 v19; // [rsp+44h] [rbp-44h]

  Source2 = 0;
  v19 = 0;
  v7 = a2;
  v8 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      33,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
  }
  if ( !a4 || v7 == -1 || a3 == -1 || RtlCompareMemory(a4, &Source2, 6u) == 6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_19;
    v9 = 34;
    goto LABEL_18;
  }
  if ( (a4->Address[0] & 1) != 0
    && (a4->Address[0] != 0xFF
     || a4->Address[1] != 0xFF
     || a4->Address[2] != 0xFF
     || a4->Address[3] != 0xFF
     || a4->Address[4] != 0xFF
     || a4->Address[5] != 0xFF) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_19:
      v8 = -1073741823;
      goto LABEL_29;
    }
    v9 = 35;
LABEL_18:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      v9,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
    goto LABEL_19;
  }
  if ( this->m_pPeerTable )
  {
    m_PeerTableLock = this->m_PeerTableLock;
    v11 = KeAcquireSpinLockRaiseToDpc(&this->m_PeerTableLock->m_SpinLock.SpinLock);
    m_PeerTableLock->m_IsLocked = 1;
    m_PeerTableLock->m_SpinLock.OldIrql = v11;
    v12 = CPeerTable::AssignPeerEntry(this, v7, a3, a4);
    OldIrql = m_PeerTableLock->m_SpinLock.OldIrql;
    v14 = v12;
    m_PeerTableLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_PeerTableLock->m_SpinLock.SpinLock, OldIrql);
    if ( v14 )
      goto LABEL_29;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD_MAC_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        v15,
        37,
        (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
        v7,
        a3,
        (__int64)a4);
    }
    goto LABEL_19;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      36,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
  }
  v8 = -1073741436;
LABEL_29:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v17) = v8;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_WORD)a2,
      1,
      38,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
      v17);
  }
  return v8;
}

```

## disassembly

```asm
0x14004e30c  mov     [rsp+arg_10], rbx
0x14004e311  push    rbp
0x14004e312  push    rsi
0x14004e313  push    rdi
0x14004e314  push    r12
0x14004e316  push    r13
0x14004e318  push    r14
0x14004e31a  push    r15
0x14004e31c  sub     rsp, 50h
0x14004e320  mov     rax, cs:__security_cookie
0x14004e327  xor     rax, rsp
0x14004e32a  mov     [rsp+88h+var_40], rax
0x14004e32f  xor     eax, eax
0x14004e331  movzx   ebp, r8w
0x14004e335  mov     [rsp+88h+Source2], eax
0x14004e339  mov     r14, r9
0x14004e33c  mov     [rsp+88h+var_44], ax
0x14004e341  mov     rbx, rcx
0x14004e344  movzx   r15d, dx
0x14004e348  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e34f  xor     esi, esi
0x14004e351  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14004e358  lea     rdi, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14004e35f  lea     r13d, [rax+1]
0x14004e363  jz      short loc_14004E391
0x14004e365  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e36c  cmp     byte ptr [rcx+29h], 5
0x14004e370  jnb     short loc_14004E378
0x14004e372  cmp     [rcx+48h], si
0x14004e376  jz      short loc_14004E391
0x14004e378  mov     rcx, [rcx+40h]
0x14004e37c  mov     r9d, 21h ; '!'
0x14004e382  mov     r8d, r13d
0x14004e385  mov     [rsp+88h+var_68], rdi
0x14004e38a  mov     dl, 5
0x14004e38c  call    WPP_RECORDER_SF_
0x14004e391  test    r14, r14
0x14004e394  jz      loc_14004E4FA
0x14004e39a  mov     eax, 0FFFFh
0x14004e39f  cmp     r15w, ax
0x14004e3a3  jz      loc_14004E4FA
0x14004e3a9  cmp     bp, ax
0x14004e3ac  jz      loc_14004E4FA
0x14004e3b2  mov     r8d, 6; Length
0x14004e3b8  lea     rdx, [rsp+88h+Source2]; Source2
0x14004e3bd  mov     rcx, r14; Source1
0x14004e3c0  call    cs:__imp_RtlCompareMemory
0x14004e3c7  nop     dword ptr [rax+rax+00h]
0x14004e3cc  cmp     rax, 6
0x14004e3d0  jz      loc_14004E4FA
0x14004e3d6  mov     al, [r14]
0x14004e3d9  test    r13b, al
0x14004e3dc  jz      short loc_14004E435
0x14004e3de  mov     cl, 0FFh
0x14004e3e0  cmp     al, cl
0x14004e3e2  jnz     short loc_14004E402
0x14004e3e4  cmp     [r14+1], cl
0x14004e3e8  jnz     short loc_14004E402
0x14004e3ea  cmp     [r14+2], cl
0x14004e3ee  jnz     short loc_14004E402
0x14004e3f0  cmp     [r14+3], cl
0x14004e3f4  jnz     short loc_14004E402
0x14004e3f6  cmp     [r14+4], cl
0x14004e3fa  jnz     short loc_14004E402
0x14004e3fc  cmp     [r14+5], cl
0x14004e400  jz      short loc_14004E435
0x14004e402  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14004e409  jz      short loc_14004E42B
0x14004e40b  mov     r9d, 23h ; '#'
0x14004e411  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e418  mov     r8d, r13d
0x14004e41b  mov     dl, 2
0x14004e41d  mov     [rsp+88h+var_68], rdi
0x14004e422  mov     rcx, [rcx+40h]
0x14004e426  call    WPP_RECORDER_SF_
0x14004e42b  mov     esi, 0C0000001h
0x14004e430  jmp     loc_14004E519
0x14004e435  cmp     [rbx+10h], rsi
0x14004e439  jnz     short loc_14004E46E
0x14004e43b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14004e442  jz      short loc_14004E464
0x14004e444  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e44b  mov     r9d, 24h ; '$'
0x14004e451  mov     r8d, r13d
0x14004e454  mov     [rsp+88h+var_68], rdi
0x14004e459  mov     dl, 2
0x14004e45b  mov     rcx, [rcx+40h]
0x14004e45f  call    WPP_RECORDER_SF_
0x14004e464  mov     esi, 0C0000184h
0x14004e469  jmp     loc_14004E519
0x14004e46e  mov     rdi, [rbx]
0x14004e471  mov     rcx, rdi; SpinLock
0x14004e474  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004e47b  nop     dword ptr [rax+rax+00h]
0x14004e480  mov     r9, r14; struct _WDI_MAC_ADDRESS *
0x14004e483  mov     [rdi+10h], r13b
0x14004e487  movzx   r8d, bp; unsigned __int16
0x14004e48b  mov     [rdi+8], al
0x14004e48e  movzx   edx, r15w; unsigned __int16
0x14004e492  mov     rcx, rbx; this
0x14004e495  call    ?AssignPeerEntry@CPeerTable@@AEAAPEAU_WFC_PEER_TABLE_ENTRY@@GGPEAU_WDI_MAC_ADDRESS@@@Z; CPeerTable::AssignPeerEntry(ushort,ushort,_WDI_MAC_ADDRESS *)
0x14004e49a  mov     dl, [rdi+8]; NewIrql
0x14004e49d  mov     rcx, rdi; SpinLock
0x14004e4a0  mov     rbx, rax
0x14004e4a3  mov     [rdi+10h], sil
0x14004e4a7  call    cs:__imp_KeReleaseSpinLock
0x14004e4ae  nop     dword ptr [rax+rax+00h]
0x14004e4b3  test    rbx, rbx
0x14004e4b6  jnz     short loc_14004E512
0x14004e4b8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14004e4bf  lea     rdi, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14004e4c6  jz      loc_14004E42B
0x14004e4cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e4d3  lea     r9d, [rbx+25h]
0x14004e4d7  mov     [rsp+88h+var_50], r14
0x14004e4dc  mov     dl, 2
0x14004e4de  mov     [rsp+88h+var_58], ebp
0x14004e4e2  mov     dword ptr [rsp+88h+var_60], r15d
0x14004e4e7  mov     rcx, [rcx+40h]
0x14004e4eb  mov     [rsp+88h+var_68], rdi
0x14004e4f0  call    WPP_RECORDER_SF_DD_MAC_
0x14004e4f5  jmp     loc_14004E42B
0x14004e4fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14004e501  jz      loc_14004E42B
0x14004e507  mov     r9d, 22h ; '"'
0x14004e50d  jmp     loc_14004E411
0x14004e512  lea     rdi, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x14004e519  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14004e520  jz      short loc_14004E554
0x14004e522  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e529  cmp     byte ptr [rcx+29h], 5
0x14004e52d  jnb     short loc_14004E537
0x14004e52f  xor     eax, eax
0x14004e531  cmp     [rcx+48h], ax
0x14004e535  jz      short loc_14004E554
0x14004e537  mov     rcx, [rcx+40h]
0x14004e53b  mov     r9d, 26h ; '&'
0x14004e541  mov     dword ptr [rsp+88h+var_60], esi
0x14004e545  mov     r8d, r13d
0x14004e548  mov     dl, 5
0x14004e54a  mov     [rsp+88h+var_68], rdi
0x14004e54f  call    WPP_RECORDER_SF_D
0x14004e554  mov     eax, esi
0x14004e556  mov     rcx, [rsp+88h+var_40]
0x14004e55b  xor     rcx, rsp; StackCookie
0x14004e55e  call    __security_check_cookie
0x14004e563  mov     rbx, [rsp+88h+arg_10]
0x14004e56b  add     rsp, 50h
0x14004e56f  pop     r15
0x14004e571  pop     r14
0x14004e573  pop     r13
0x14004e575  pop     r12
0x14004e577  pop     rdi
0x14004e578  pop     rsi
0x14004e579  pop     rbp
0x14004e57a  retn
```

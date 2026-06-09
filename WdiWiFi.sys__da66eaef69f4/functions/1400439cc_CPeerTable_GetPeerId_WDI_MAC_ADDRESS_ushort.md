# CPeerTable::GetPeerId(_WDI_MAC_ADDRESS *,ushort)

- ea: `0x1400439cc`
- end: `0x140043cdf`
- name: `?GetPeerId@CPeerTable@@QEAAGPEAU_WDI_MAC_ADDRESS@@G@Z`
- size: `787`
- prototype: `unsigned __int16(CPeerTable *__hidden this, struct _WDI_MAC_ADDRESS *, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140036ec0`
- `0x14005e334`

## callees

- `0x1400175f8`
- `0x140034e04`
- `0x140034ec4`
- `0x1400439cc`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140043a50`
- `ntoskrnl!RtlCompareMemory` at `0x140043b00`
- `ntoskrnl!RtlCompareMemory` at `0x140043a50`
- `ntoskrnl!RtlCompareMemory` at `0x140043b00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043b2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043c9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043b2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140043c9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140043aba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140043aba`

## pseudocode

```c
__int64 __fastcall CPeerTable::GetPeerId(CPeerTable *this, struct _WDI_MAC_ADDRESS *a2, unsigned __int16 a3)
{
  unsigned int v3; // r15d
  unsigned __int16 PeerId; // r12
  struct _WDI_MAC_ADDRESS *v5; // r14
  int v7; // edx
  int v8; // edx
  unsigned int v9; // eax
  CNdisSpinLock *m_PeerTableLock; // rbx
  unsigned int v11; // r13d
  unsigned int v12; // ebp
  KIRQL v13; // al
  unsigned int v14; // edx
  int v15; // r8d
  _WFC_PEER_TABLE_ENTRY *m_pPeerTable; // rcx
  _WFC_PEER_TABLE_ENTRY *v17; // r9
  bool v18; // zf
  KIRQL OldIrql; // dl
  int v20; // edx
  int v22; // r9d
  int v23; // r10d
  __int64 v24; // [rsp+28h] [rbp-50h]
  __int64 Source2; // [rsp+30h] [rbp-48h] BYREF

  v3 = a3;
  LODWORD(Source2) = 0;
  PeerId = -1;
  WORD2(Source2) = 0;
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      45,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
  }
  if ( RtlCompareMemory(v5, &Source2, 6u) == 6 || (_WORD)v3 == 0xFFFF )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return PeerId;
    v22 = 46;
    goto LABEL_24;
  }
  if ( !this->m_pPeerTable )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return PeerId;
    v22 = 47;
LABEL_24:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      v22,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids);
    goto LABEL_16;
  }
  v8 = v5->Address[0];
  if ( (v8 & 1) != 0 )
    v9 = v3;
  else
    v9 = v8 ^ v5->Address[1] ^ v5->Address[2] ^ v5->Address[3] ^ v5->Address[4] ^ v5->Address[5];
  m_PeerTableLock = this->m_PeerTableLock;
  v11 = v9 % this->m_TableSize;
  v12 = v11;
  v13 = KeAcquireSpinLockRaiseToDpc(&this->m_PeerTableLock->m_SpinLock.SpinLock);
  m_PeerTableLock->m_IsLocked = 1;
  m_PeerTableLock->m_SpinLock.OldIrql = v13;
  while ( 1 )
  {
    m_pPeerTable = this->m_pPeerTable;
    if ( !m_pPeerTable[v12].bInUse )
      break;
    v17 = &m_pPeerTable[v12];
    if ( (v5->Address[0] & 1) != 0 )
    {
      if ( v17->PeerAddr.Address[0] != 0xFF
        || m_pPeerTable[v12].PeerAddr.Address[1] != 0xFF
        || m_pPeerTable[v12].PeerAddr.Address[2] != 0xFF
        || m_pPeerTable[v12].PeerAddr.Address[3] != 0xFF
        || m_pPeerTable[v12].PeerAddr.Address[4] != 0xFF
        || m_pPeerTable[v12].PeerAddr.Address[5] != 0xFF )
      {
        goto LABEL_25;
      }
      v18 = m_pPeerTable[v12].PortId == (unsigned __int16)v3;
    }
    else
    {
      v18 = RtlCompareMemory(&v17->PeerAddr, v5, 6u) == 6;
    }
    if ( v18 )
    {
      PeerId = this->m_pPeerTable[v12].PeerId;
      goto LABEL_15;
    }
LABEL_25:
    v14 = (v12 + 1) % this->m_TableSize;
    v12 = v14;
    if ( v14 == v11 )
      goto LABEL_15;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF__MAC_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      v15,
      48,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
      (__int64)v5);
  }
LABEL_15:
  OldIrql = m_PeerTableLock->m_SpinLock.OldIrql;
  m_PeerTableLock->m_IsLocked = 0;
  KeReleaseSpinLock(&m_PeerTableLock->m_SpinLock.SpinLock, OldIrql);
LABEL_16:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v23 = -1073741823;
    if ( PeerId != 0xFFFF )
      v23 = 0;
    LOBYTE(v20) = 5;
    LODWORD(v24) = v23;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      1,
      49,
      (__int64)WPP_9437762af08d3eac72fe4950abce8818_Traceguids,
      v24,
      Source2);
  }
  return PeerId;
}

```

## disassembly

```asm
0x1400439cc  mov     [rsp+arg_18], rbx
0x1400439d1  push    rbp
0x1400439d2  push    rsi
0x1400439d3  push    rdi
0x1400439d4  push    r12
0x1400439d6  push    r13
0x1400439d8  push    r14
0x1400439da  push    r15
0x1400439dc  sub     rsp, 40h
0x1400439e0  mov     rax, cs:__security_cookie
0x1400439e7  xor     rax, rsp
0x1400439ea  mov     [rsp+78h+var_40], rax
0x1400439ef  xor     eax, eax
0x1400439f1  movzx   r15d, r8w
0x1400439f5  mov     r13d, 0FFFFh
0x1400439fb  mov     [rsp+78h+Source2], eax
0x1400439ff  movzx   r12d, r13w
0x140043a03  mov     [rsp+78h+var_44], ax
0x140043a08  mov     r14, rdx
0x140043a0b  mov     rsi, rcx
0x140043a0e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043a15  xor     ebx, ebx
0x140043a17  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043a1e  lea     rbp, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x140043a25  jz      short loc_140043A42
0x140043a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140043a2e  cmp     byte ptr [rcx+29h], 5
0x140043a32  jnb     loc_140043C0C
0x140043a38  cmp     [rcx+48h], bx
0x140043a3c  jnz     loc_140043C0C
0x140043a42  mov     r8d, 6; Length
0x140043a48  lea     rdx, [rsp+78h+Source2]; Source2
0x140043a4d  mov     rcx, r14; Source1
0x140043a50  call    cs:__imp_RtlCompareMemory
0x140043a57  nop     dword ptr [rax+rax+00h]
0x140043a5c  cmp     rax, 6
0x140043a60  jz      loc_140043BB2
0x140043a66  cmp     r15w, r13w
0x140043a6a  jz      loc_140043BB2
0x140043a70  cmp     [rsi+10h], rbx
0x140043a74  jz      loc_140043B9A
0x140043a7a  movzx   edx, byte ptr [r14]
0x140043a7e  test    dl, 1
0x140043a81  jnz     loc_140043C04
0x140043a87  movzx   ecx, byte ptr [r14+4]
0x140043a8c  movzx   eax, byte ptr [r14+5]
0x140043a91  xor     eax, ecx
0x140043a93  movzx   ecx, byte ptr [r14+3]
0x140043a98  xor     eax, ecx
0x140043a9a  movzx   ecx, byte ptr [r14+2]
0x140043a9f  xor     eax, ecx
0x140043aa1  movzx   ecx, byte ptr [r14+1]
0x140043aa6  xor     eax, ecx
0x140043aa8  xor     eax, edx
0x140043aaa  mov     rbx, [rsi]
0x140043aad  xor     edx, edx
0x140043aaf  div     dword ptr [rsi+8]
0x140043ab2  mov     rcx, rbx; SpinLock
0x140043ab5  mov     r13d, edx
0x140043ab8  mov     ebp, edx
0x140043aba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140043ac1  nop     dword ptr [rax+rax+00h]
0x140043ac6  mov     byte ptr [rbx+10h], 1
0x140043aca  mov     dl, 0FFh
0x140043acc  mov     [rbx+8], al
0x140043acf  mov     rcx, [rsi+10h]
0x140043ad3  movsxd  rax, ebp
0x140043ad6  lea     rdi, [rax+rax*2]
0x140043ada  cmp     byte ptr [rcx+rdi*4+0Ah], 0
0x140043adf  jz      loc_140043C59
0x140043ae5  test    byte ptr [r14], 1
0x140043ae9  lea     r9, [rcx+rdi*4]
0x140043aed  jnz     loc_140043C2B
0x140043af3  mov     r8d, 6; Length
0x140043af9  lea     rcx, [r9+4]; Source1
0x140043afd  mov     rdx, r14; Source2
0x140043b00  call    cs:__imp_RtlCompareMemory
0x140043b07  nop     dword ptr [rax+rax+00h]
0x140043b0c  cmp     rax, 6
0x140043b10  jnz     loc_140043BEA
0x140043b16  mov     rax, [rsi+10h]
0x140043b1a  movzx   r12d, word ptr [rax+rdi*4+2]
0x140043b20  mov     dl, [rbx+8]; NewIrql
0x140043b23  mov     rcx, rbx; SpinLock
0x140043b26  mov     byte ptr [rbx+10h], 0
0x140043b2a  call    cs:__imp_KeReleaseSpinLock
0x140043b31  nop     dword ptr [rax+rax+00h]
0x140043b36  lea     rdi, WPP_RECORDER_INITIALIZED
0x140043b3d  lea     rbp, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x140043b44  xor     ebx, ebx
0x140043b46  mov     r13d, 0FFFFh
0x140043b4c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140043b53  jz      short loc_140043B70
0x140043b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140043b5c  cmp     byte ptr [rcx+29h], 5
0x140043b60  jnb     loc_140043CAD
0x140043b66  cmp     [rcx+48h], bx
0x140043b6a  jnz     loc_140043CAD
0x140043b70  movzx   eax, r12w
0x140043b74  mov     rcx, [rsp+78h+var_40]
0x140043b79  xor     rcx, rsp; StackCookie
0x140043b7c  call    __security_check_cookie
0x140043b81  mov     rbx, [rsp+78h+arg_18]
0x140043b89  add     rsp, 40h
0x140043b8d  pop     r15
0x140043b8f  pop     r14
0x140043b91  pop     r13
0x140043b93  pop     r12
0x140043b95  pop     rdi
0x140043b96  pop     rsi
0x140043b97  pop     rbp
0x140043b98  retn
0x140043b9a  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043ba1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140043ba8  jz      short loc_140043B70
0x140043baa  mov     r9d, 2Fh ; '/'
0x140043bb0  jmp     short loc_140043BC8
0x140043bb2  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043bb9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140043bc0  jz      short loc_140043B70
0x140043bc2  mov     r9d, 2Eh ; '.'
0x140043bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140043bcf  mov     r8d, 1
0x140043bd5  mov     dl, 2
0x140043bd7  mov     [rsp+78h+var_58], rbp
0x140043bdc  mov     rcx, [rcx+40h]
0x140043be0  call    WPP_RECORDER_SF_
0x140043be5  jmp     loc_140043B4C
0x140043bea  xor     edx, edx
0x140043bec  lea     eax, [rbp+1]
0x140043bef  div     dword ptr [rsi+8]
0x140043bf2  mov     ebp, edx
0x140043bf4  cmp     edx, r13d
0x140043bf7  mov     dl, 0FFh
0x140043bf9  jnz     loc_140043ACF
0x140043bff  jmp     loc_140043B20
0x140043c04  mov     eax, r15d
0x140043c07  jmp     loc_140043AAA
0x140043c0c  mov     rcx, [rcx+40h]
0x140043c10  mov     r9d, 2Dh ; '-'
0x140043c16  mov     dl, 5
0x140043c18  mov     [rsp+78h+var_58], rbp
0x140043c1d  lea     r8d, [r9-2Ch]
0x140043c21  call    WPP_RECORDER_SF_
0x140043c26  jmp     loc_140043A42
0x140043c2b  cmp     [r9+4], dl
0x140043c2f  jnz     short loc_140043BEA
0x140043c31  cmp     [rcx+rdi*4+5], dl
0x140043c35  jnz     short loc_140043BEA
0x140043c37  cmp     [rcx+rdi*4+6], dl
0x140043c3b  jnz     short loc_140043BEA
0x140043c3d  cmp     [rcx+rdi*4+7], dl
0x140043c41  jnz     short loc_140043BEA
0x140043c43  cmp     [rcx+rdi*4+8], dl
0x140043c47  jnz     short loc_140043BEA
0x140043c49  cmp     [rcx+rdi*4+9], dl
0x140043c4d  jnz     short loc_140043BEA
0x140043c4f  cmp     [rcx+rdi*4], r15w
0x140043c54  jmp     loc_140043B10
0x140043c59  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140043c60  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140043c67  lea     rbp, WPP_9437762af08d3eac72fe4950abce8818_Traceguids
0x140043c6e  jz      short loc_140043C92
0x140043c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140043c77  mov     r9d, 30h ; '0'
0x140043c7d  mov     [rsp+78h+var_50], r14
0x140043c82  mov     dl, 2
0x140043c84  mov     [rsp+78h+var_58], rbp
0x140043c89  mov     rcx, [rcx+40h]
0x140043c8d  call    WPP_RECORDER_SF__MAC_
0x140043c92  mov     dl, [rbx+8]; NewIrql
0x140043c95  mov     rcx, rbx; SpinLock
0x140043c98  mov     byte ptr [rbx+10h], 0
0x140043c9c  call    cs:__imp_KeReleaseSpinLock
0x140043ca3  nop     dword ptr [rax+rax+00h]
0x140043ca8  jmp     loc_140043B44
0x140043cad  mov     rcx, [rcx+40h]
0x140043cb1  cmp     r12w, r13w
0x140043cb5  mov     r9d, 31h ; '1'
0x140043cbb  mov     r10d, 0C0000001h
0x140043cc1  cmovnz  r10d, ebx
0x140043cc5  mov     dl, 5
0x140043cc7  mov     dword ptr [rsp+78h+var_50], r10d
0x140043ccc  mov     [rsp+78h+var_58], rbp
0x140043cd1  lea     r8d, [r9-30h]
0x140043cd5  call    WPP_RECORDER_SF_D
0x140043cda  jmp     loc_140043B70
```

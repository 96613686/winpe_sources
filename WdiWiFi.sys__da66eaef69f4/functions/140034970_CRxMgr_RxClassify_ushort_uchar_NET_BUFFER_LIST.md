# CRxMgr::RxClassify(ushort *,uchar *,_NET_BUFFER_LIST *)

- ea: `0x140034970`
- end: `0x140034dfc`
- name: `?RxClassify@CRxMgr@@AEAAHPEAGPEAEPEAU_NET_BUFFER_LIST@@@Z`
- size: `1164`
- prototype: `__int64 __fastcall(CRxMgr *__hidden this, unsigned __int16 *, unsigned __int8 *, struct _NET_BUFFER_LIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034470`

## callees

- `0x140034970`
- `0x140034e04`
- `0x140034ec4`
- `0x14003d930`
- `0x14009baac`
- `0x1400da4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140034ad3`
- `ntoskrnl!RtlCompareMemory` at `0x140034ad3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034bce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034bce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034a64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034a64`
- `NDIS!NdisGetDataBuffer` at `0x140034a33`
- `NDIS!NdisGetDataBuffer` at `0x140034c36`
- `NDIS!NdisGetDataBuffer` at `0x140034d07`
- `NDIS!NdisGetDataBuffer` at `0x140034a33`
- `NDIS!NdisGetDataBuffer` at `0x140034c36`
- `NDIS!NdisGetDataBuffer` at `0x140034d07`

## pseudocode

```c
__int64 __fastcall CRxMgr::RxClassify(
        CRxMgr *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        struct _NET_BUFFER_LIST *a4)
{
  unsigned __int16 *v6; // rsi
  unsigned int v8; // edi
  PNET_BUFFER FirstNetBuffer; // rbx
  char *DataBuffer; // rax
  unsigned __int16 *v11; // r12
  CNdisSpinLock *m_LockRxPeerTable; // rbx
  CRxPeerTable *p_m_RxPeerTable; // r15
  int v14; // edx
  unsigned int i; // ebp
  __int64 v16; // rax
  char *v17; // r13
  KIRQL OldIrql; // dl
  unsigned __int16 v20; // si
  __int16 v21; // bp
  struct _NET_BUFFER *v22; // r15
  char *v23; // rax
  int v24; // r8d
  int v25; // r9d
  _BYTE *v26; // rcx
  int v27; // edx
  int AlignOffset; // [rsp+20h] [rbp-C8h]
  __int64 v29; // [rsp+28h] [rbp-C0h]
  struct _NET_BUFFER *NetBuffer; // [rsp+60h] [rbp-88h]
  char *v31; // [rsp+68h] [rbp-80h]
  _BYTE Storage[32]; // [rsp+70h] [rbp-78h] BYREF

  v6 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      83,
      (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids);
  }
  if ( *v6 == 0xFFFF || (v8 = 0, *a3 > 0x18u) )
  {
    FirstNetBuffer = a4->FirstNetBuffer;
    NetBuffer = FirstNetBuffer;
    DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, 0x18u, Storage, 1u, 0);
    v11 = (unsigned __int16 *)DataBuffer;
    if ( DataBuffer )
    {
      m_LockRxPeerTable = this->m_RxPeerTable.m_LockRxPeerTable;
      p_m_RxPeerTable = &this->m_RxPeerTable;
      v31 = DataBuffer + 10;
      v8 = -1073676267;
      m_LockRxPeerTable->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_LockRxPeerTable->m_SpinLock.SpinLock);
      m_LockRxPeerTable->m_IsLocked = 1;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v14) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          32,
          (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids);
      }
      for ( i = 0; i < p_m_RxPeerTable->m_TableSize; ++i )
      {
        v16 = i;
        v17 = (char *)p_m_RxPeerTable + v16 * 16;
        if ( p_m_RxPeerTable->m_PeerEntryArray[v16].RxPeerState
          && RtlCompareMemory(&p_m_RxPeerTable->m_PeerEntryArray[v16].PeerAddr, v11 + 5, 6u) == 6 )
        {
          v8 = 0;
          *v6 = *((_WORD *)v17 + 13);
          break;
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v14) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          33,
          (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids,
          v8);
      }
      OldIrql = m_LockRxPeerTable->m_SpinLock.OldIrql;
      m_LockRxPeerTable->m_IsLocked = 0;
      KeReleaseSpinLock(&m_LockRxPeerTable->m_SpinLock.SpinLock, OldIrql);
      if ( v8 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v8;
        v27 = (unsigned __int8)v31[3];
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_DDDDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          1,
          85,
          (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids,
          *v31,
          v31[1],
          v31[2],
          v31[3],
          v31[4],
          v31[5]);
      }
      else
      {
        v20 = *v11;
        if ( (*v11 & 0xC) == 8 && ((v20 >> 4) & 8) != 0 )
        {
          v21 = (v20 >> 9) & 1;
          if ( v21 && (v20 & 0x100) != 0 )
          {
            v22 = NetBuffer;
            v23 = (char *)NdisGetDataBuffer(NetBuffer, 8u, Storage, 1u, 0);
            v26 = v23 + 30;
          }
          else
          {
            v22 = NetBuffer;
            v23 = (char *)NdisGetDataBuffer(NetBuffer, 8u, Storage, 1u, 0);
            v26 = v23 + 24;
          }
          if ( v23 )
          {
            *a3 = *v26 & 0xF;
          }
          else
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_DHHHH(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)a2,
                v24,
                v25,
                AlignOffset,
                v22->DataLength,
                (v20 >> 2) & 3,
                (v20 >> 4) & 0xF,
                v21,
                HIBYTE(v20) & 1);
            v8 = -1073676273;
          }
        }
        else
        {
          *a3 = 16;
        }
      }
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          84,
          (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids,
          FirstNetBuffer->DataLength);
      }
      v8 = -1073676273;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v29) = v8;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      87,
      (__int64)WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids,
      v29);
  }
  return v8;
}

```

## disassembly

```asm
0x140034970  push    rbx
0x140034972  push    rbp
0x140034973  push    rsi
0x140034974  push    rdi
0x140034975  push    r14
0x140034977  push    r15
0x140034979  sub     rsp, 0B8h
0x140034980  mov     rax, cs:__security_cookie
0x140034987  xor     rax, rsp
0x14003498a  mov     [rsp+0E8h+var_58], rax
0x140034992  mov     rbx, r9
0x140034995  mov     r14, r8
0x140034998  mov     rsi, rdx
0x14003499b  mov     rbp, rcx
0x14003499e  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400349a5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400349ac  lea     r15, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x1400349b3  jz      short loc_1400349E2
0x1400349b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400349bc  cmp     byte ptr [rcx+29h], 5
0x1400349c0  jb      loc_140034B76
0x1400349c6  mov     rcx, [rcx+40h]
0x1400349ca  mov     r9d, 53h ; 'S'
0x1400349d0  mov     r8d, 1
0x1400349d6  mov     qword ptr [rsp+0E8h+AlignOffset], r15
0x1400349db  mov     dl, 5
0x1400349dd  call    WPP_RECORDER_SF_
0x1400349e2  mov     eax, 0FFFFh
0x1400349e7  mov     [rsp+0E8h+var_38], r12
0x1400349ef  mov     [rsp+0E8h+var_40], r13
0x1400349f7  cmp     [rsi], ax
0x1400349fa  jz      short loc_140034A0F
0x1400349fc  xor     edi, edi
0x1400349fe  cmp     byte ptr [r14], 18h
0x140034a02  jbe     loc_140034AFF
0x140034a08  lea     rdi, WPP_RECORDER_INITIALIZED
0x140034a0f  mov     rbx, [rbx+8]
0x140034a13  lea     r8, [rsp+0E8h+Storage]; Storage
0x140034a18  mov     rcx, rbx; NetBuffer
0x140034a1b  mov     [rsp+0E8h+NetBuffer], rbx
0x140034a20  mov     r9d, 1; AlignMultiple
0x140034a26  mov     [rsp+0E8h+AlignOffset], 0; AlignOffset
0x140034a2e  mov     edx, 18h; BytesNeeded
0x140034a33  call    cs:__imp_NdisGetDataBuffer
0x140034a3a  nop     dword ptr [rax+rax+00h]
0x140034a3f  mov     r12, rax
0x140034a42  test    rax, rax
0x140034a45  jz      loc_140034AED
0x140034a4b  mov     rbx, [rbp+58h]
0x140034a4f  lea     r13, [rax+0Ah]
0x140034a53  lea     r15, [rbp+58h]
0x140034a57  mov     [rsp+0E8h+var_80], r13
0x140034a5c  mov     rcx, rbx; SpinLock
0x140034a5f  mov     edi, 0C0010015h
0x140034a64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140034a6b  nop     dword ptr [rax+rax+00h]
0x140034a70  mov     [rbx+8], al
0x140034a73  mov     byte ptr [rbx+10h], 1
0x140034a77  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140034a7e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034a85  jz      short loc_140034AA3
0x140034a87  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a8e  cmp     byte ptr [rcx+29h], 5
0x140034a92  jnb     loc_140034D4B
0x140034a98  cmp     word ptr [rcx+48h], 0
0x140034a9d  jnz     loc_140034D4B
0x140034aa3  xor     ebp, ebp
0x140034aa5  cmp     ebp, [r15+14h]
0x140034aa9  jnb     loc_140034B90
0x140034aaf  mov     eax, ebp
0x140034ab1  shl     rax, 4
0x140034ab5  cmp     dword ptr [rax+r15+1Ch], 0
0x140034abb  lea     r13, [rax+r15]
0x140034abf  jz      short loc_140034AE9
0x140034ac1  lea     rcx, [r15+20h]
0x140034ac5  mov     r8d, 6; Length
0x140034acb  add     rcx, rax; Source1
0x140034ace  lea     rdx, [r12+0Ah]; Source2
0x140034ad3  call    cs:__imp_RtlCompareMemory
0x140034ada  nop     dword ptr [rax+rax+00h]
0x140034adf  cmp     rax, 6
0x140034ae3  jz      loc_140034B86
0x140034ae9  inc     ebp
0x140034aeb  jmp     short loc_140034AA5
0x140034aed  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140034af4  jnz     loc_140034D1C
0x140034afa  mov     edi, 0C001000Fh
0x140034aff  lea     r13, WPP_RECORDER_INITIALIZED
0x140034b06  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140034b0d  jz      short loc_140034B43
0x140034b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140034b16  cmp     byte ptr [rcx+29h], 5
0x140034b1a  jnb     short loc_140034B23
0x140034b1c  cmp     word ptr [rcx+48h], 0
0x140034b21  jz      short loc_140034B43
0x140034b23  mov     rcx, [rcx+40h]
0x140034b27  mov     r9d, 57h ; 'W'
0x140034b2d  mov     dword ptr [rsp+0E8h+var_C0], edi
0x140034b31  mov     r8d, 1
0x140034b37  mov     dl, 5
0x140034b39  mov     qword ptr [rsp+0E8h+AlignOffset], r15
0x140034b3e  call    WPP_RECORDER_SF_D
0x140034b43  mov     r13, [rsp+0E8h+var_40]
0x140034b4b  mov     eax, edi
0x140034b4d  mov     r12, [rsp+0E8h+var_38]
0x140034b55  mov     rcx, [rsp+0E8h+var_58]
0x140034b5d  xor     rcx, rsp; StackCookie
0x140034b60  call    __security_check_cookie
0x140034b65  add     rsp, 0B8h
0x140034b6c  pop     r15
0x140034b6e  pop     r14
0x140034b70  pop     rdi
0x140034b71  pop     rsi
0x140034b72  pop     rbp
0x140034b73  pop     rbx
0x140034b74  retn
0x140034b76  cmp     word ptr [rcx+48h], 0
0x140034b7b  jz      loc_1400349E2
0x140034b81  jmp     loc_1400349C6
0x140034b86  movzx   eax, word ptr [r13+1Ah]
0x140034b8b  xor     edi, edi
0x140034b8d  mov     [rsi], ax
0x140034b90  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140034b97  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140034b9e  jz      short loc_140034BBC
0x140034ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ba7  cmp     byte ptr [rcx+29h], 5
0x140034bab  jnb     loc_140034D73
0x140034bb1  cmp     word ptr [rcx+48h], 0
0x140034bb6  jnz     loc_140034D73
0x140034bbc  lea     r15, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x140034bc3  movzx   edx, byte ptr [rbx+8]; NewIrql
0x140034bc7  mov     rcx, rbx; SpinLock
0x140034bca  mov     byte ptr [rbx+10h], 0
0x140034bce  call    cs:__imp_KeReleaseSpinLock
0x140034bd5  nop     dword ptr [rax+rax+00h]
0x140034bda  test    edi, edi
0x140034bdc  jnz     loc_140034C63
0x140034be2  movzx   esi, word ptr [r12]
0x140034be7  movzx   eax, sil
0x140034beb  and     al, 0Ch
0x140034bed  cmp     al, 8
0x140034bef  jnz     short loc_140034BFC
0x140034bf1  movzx   ebx, si
0x140034bf4  shr     bx, 4
0x140034bf8  test    al, bl
0x140034bfa  jnz     short loc_140034C05
0x140034bfc  mov     byte ptr [r14], 10h
0x140034c00  jmp     loc_140034B06
0x140034c05  movzx   ebp, si
0x140034c08  shr     bp, 9
0x140034c0c  and     bp, 1
0x140034c10  jnz     loc_140034CDC
0x140034c16  mov     r15, [rsp+0E8h+NetBuffer]
0x140034c1b  lea     r8, [rsp+0E8h+Storage]; Storage
0x140034c20  mov     rcx, r15; NetBuffer
0x140034c23  mov     [rsp+0E8h+AlignOffset], 0; AlignOffset
0x140034c2b  mov     r9d, 1; AlignMultiple
0x140034c31  mov     edx, 8; BytesNeeded
0x140034c36  call    cs:__imp_NdisGetDataBuffer
0x140034c3d  nop     dword ptr [rax+rax+00h]
0x140034c42  lea     rcx, [rax+18h]
0x140034c46  test    rax, rax
0x140034c49  jz      loc_140034D9F
0x140034c4f  movzx   eax, byte ptr [rcx]
0x140034c52  lea     r15, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x140034c59  and     al, 0Fh
0x140034c5b  mov     [r14], al
0x140034c5e  jmp     loc_140034B06
0x140034c63  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140034c6a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034c71  jz      loc_140034B43
0x140034c77  mov     r9, [rsp+0E8h+var_80]
0x140034c7c  movzx   ecx, byte ptr [r9+4]
0x140034c81  movzx   edx, byte ptr [r9+3]
0x140034c86  movzx   r8d, byte ptr [r9+2]
0x140034c8b  movzx   eax, byte ptr [r9+5]
0x140034c90  movzx   r10d, byte ptr [r9+1]
0x140034c95  movzx   r11d, byte ptr [r9]
0x140034c99  mov     r9d, 55h ; 'U'
0x140034c9f  mov     [rsp+0E8h+var_98], eax
0x140034ca3  mov     [rsp+0E8h+var_A0], ecx
0x140034ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140034cae  mov     [rsp+0E8h+var_A8], edx
0x140034cb2  mov     dl, 2
0x140034cb4  mov     [rsp+0E8h+var_B0], r8d
0x140034cb9  mov     r8d, 1
0x140034cbf  mov     [rsp+0E8h+var_B8], r10d
0x140034cc4  mov     rcx, [rcx+40h]
0x140034cc8  mov     dword ptr [rsp+0E8h+var_C0], r11d
0x140034ccd  mov     qword ptr [rsp+0E8h+AlignOffset], r15
0x140034cd2  call    WPP_RECORDER_SF_DDDDDD
0x140034cd7  jmp     loc_140034AFF
0x140034cdc  bt      si, 8
0x140034ce1  jnb     loc_140034C16
0x140034ce7  mov     r15, [rsp+0E8h+NetBuffer]
0x140034cec  lea     r8, [rsp+0E8h+Storage]; Storage
0x140034cf1  mov     rcx, r15; NetBuffer
0x140034cf4  mov     [rsp+0E8h+AlignOffset], 0; AlignOffset
0x140034cfc  mov     r9d, 1; AlignMultiple
0x140034d02  mov     edx, 8; BytesNeeded
0x140034d07  call    cs:__imp_NdisGetDataBuffer
0x140034d0e  nop     dword ptr [rax+rax+00h]
0x140034d13  lea     rcx, [rax+1Eh]
0x140034d17  jmp     loc_140034C46
0x140034d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d23  mov     r9d, 54h ; 'T'
0x140034d29  mov     eax, [rbx+18h]
0x140034d2c  mov     r8d, 1
0x140034d32  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140034d36  mov     dl, 2
0x140034d38  mov     qword ptr [rsp+0E8h+AlignOffset], r15
0x140034d3d  mov     rcx, [rcx+40h]
0x140034d41  call    WPP_RECORDER_SF_D
0x140034d46  jmp     loc_140034AFA
0x140034d4b  mov     rcx, [rcx+40h]
0x140034d4f  lea     rax, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x140034d56  mov     r9d, 20h ; ' '
0x140034d5c  mov     qword ptr [rsp+0E8h+AlignOffset], rax
0x140034d61  mov     r8d, 1
0x140034d67  mov     dl, 5
0x140034d69  call    WPP_RECORDER_SF_
0x140034d6e  jmp     loc_140034AA3
0x140034d73  mov     rcx, [rcx+40h]
0x140034d77  lea     r15, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x140034d7e  mov     r9d, 21h ; '!'
0x140034d84  mov     dword ptr [rsp+0E8h+var_C0], edi
0x140034d88  mov     r8d, 1
0x140034d8e  mov     qword ptr [rsp+0E8h+AlignOffset], r15
0x140034d93  mov     dl, 5
0x140034d95  call    WPP_RECORDER_SF_D
0x140034d9a  jmp     loc_140034BC3
0x140034d9f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140034da6  jz      short loc_140034DEB
0x140034da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140034daf  movzx   eax, si
0x140034db2  shr     ax, 8
0x140034db6  and     bx, 0Fh
0x140034dba  and     ax, 1
0x140034dbe  shr     si, 2
0x140034dc2  mov     word ptr [rsp+0E8h+var_A0], ax
0x140034dc7  and     si, 3
0x140034dcb  mov     eax, [r15+18h]
0x140034dcf  mov     rcx, [rcx+40h]
0x140034dd3  mov     word ptr [rsp+0E8h+var_A8], bp
0x140034dd8  mov     word ptr [rsp+0E8h+var_B0], bx
0x140034ddd  mov     word ptr [rsp+0E8h+var_B8], si
0x140034de2  mov     dword ptr [rsp+0E8h+var_C0], eax
0x140034de6  call    WPP_RECORDER_SF_DHHHH
0x140034deb  mov     edi, 0C001000Fh
0x140034df0  lea     r15, WPP_dd23c8cc3cd6384979e7e040e77890e5_Traceguids
0x140034df7  jmp     loc_140034B06
```

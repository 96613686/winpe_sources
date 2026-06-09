# TR_CreateSecureObject

- ea: `0x1400389a4`
- end: `0x140038baf`
- name: `TR_CreateSecureObject`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140082ab4`

## callees

- `0x140005a6c`
- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x1400389a4`
- `0x140040230`
- `0x1400472a8`
- `0x140059970`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140038b9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038b9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038b63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038b63`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400389fb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400389fb`

## string_xrefs

- `0x140038b0a`: `TransferRingCreate Failed`
- `0x140038a1a`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall TR_CreateSecureObject(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // r14
  _QWORD *v4; // rdi
  int v5; // esi
  __int64 v6; // rcx
  __int64 RemoteHandle; // rax
  __int64 v8; // rcx
  int v9; // edx
  _QWORD *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  _QWORD v14[8]; // [rsp+50h] [rbp-9h] BYREF

  memset(v14, 0, sizeof(v14));
  LODWORD(v13) = 0;
  v2 = *(_QWORD *)(a1 + 40);
  v12 = 0;
  if ( *(_BYTE *)(v2 + 1041) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\tr.c",
      2010);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 120LL);
  v4 = (_QWORD *)CommonBuffer_AcquireShadowBuffer(*(unsigned int *)(a1 + 20), a1, 828862034);
  if ( !v4 )
    return (unsigned int)-1073741670;
  memset(v14, 0, sizeof(v14));
  v6 = *(_QWORD *)(a1 + 56);
  LODWORD(v14[4]) = 39;
  RemoteHandle = XilEndpoint_GetRemoteHandle(v6);
  v8 = *(_QWORD *)(a1 + 40);
  v14[5] = RemoteHandle;
  LODWORD(v14[6]) = *(_DWORD *)(a1 + 64);
  HIDWORD(v14[6]) = *(_DWORD *)(a1 + 20);
  LOBYTE(v14[7]) = (*(_QWORD *)(v8 + 736) & 0x4000000000000LL) != 0;
  v5 = SecureChannel_SendRequestSynchronously(*(_QWORD *)(v8 + 112), v14, 64, &v12, 24);
  if ( v5 < 0 )
  {
LABEL_11:
    CommonBuffer_ReleaseBuffer(v3, v4);
    return (unsigned int)v5;
  }
  if ( (int)v12 < 0 )
  {
    v5 = v12;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 72LL),
        v9,
        14,
        24,
        (__int64)WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids,
        v12);
    }
    Debug_FreAssertMsg("TransferRingCreate Failed", 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\tr.c", 2067);
    goto LABEL_11;
  }
  *(_QWORD *)(a1 + 296) = *((_QWORD *)&v12 + 1);
  v4[3] = v13;
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v11 = *(_QWORD **)(a1 + 216);
  if ( *v11 != a1 + 208 )
    __fastfail(3u);
  v4[1] = v11;
  *v4 = a1 + 208;
  *v11 = v4;
  *(_QWORD *)(a1 + 216) = v4;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400389a4  mov     [rsp-8+arg_8], rbx
0x1400389a9  mov     [rsp-8+arg_10], rsi
0x1400389ae  push    rbp
0x1400389af  push    rdi
0x1400389b0  push    r14
0x1400389b2  lea     rbp, [rsp-47h]
0x1400389b7  sub     rsp, 0A0h
0x1400389be  mov     rax, cs:__security_cookie
0x1400389c5  xor     rax, rsp
0x1400389c8  mov     [rbp+57h+var_20], rax
0x1400389cc  mov     rbx, rcx
0x1400389cf  mov     esi, 40h ; '@'
0x1400389d4  mov     r8d, esi; Size
0x1400389d7  lea     rcx, [rbp+57h+var_60]; void *
0x1400389db  xor     edx, edx; Val
0x1400389dd  call    memset
0x1400389e2  xor     eax, eax
0x1400389e4  xorps   xmm0, xmm0
0x1400389e7  mov     dword ptr [rbp+57h+var_70], eax
0x1400389ea  mov     rax, [rbx+28h]
0x1400389ee  movups  [rbp+57h+var_80], xmm0
0x1400389f2  cmp     byte ptr [rax+411h], 0
0x1400389f9  jz      short loc_140038A26
0x1400389fb  call    cs:__imp_KeGetCurrentIrql
0x140038a02  nop     dword ptr [rax+rax+00h]
0x140038a07  test    al, al
0x140038a09  jz      short loc_140038A26
0x140038a0b  mov     r9d, 7DAh
0x140038a11  lea     r8, aOnecoreDrivers_19
0x140038a18  xor     edx, edx
0x140038a1a  lea     rcx, aCodePathRequir
0x140038a21  call    Debug_FreAssertMsg
0x140038a26  mov     rax, [rbx+28h]
0x140038a2a  mov     r8d, 31676E52h
0x140038a30  mov     ecx, [rbx+14h]
0x140038a33  mov     rdx, rbx
0x140038a36  mov     r14, [rax+78h]
0x140038a3a  call    CommonBuffer_AcquireShadowBuffer
0x140038a3f  mov     rdi, rax
0x140038a42  test    rax, rax
0x140038a45  jnz     short loc_140038A51
0x140038a47  mov     esi, 0C000009Ah
0x140038a4c  jmp     loc_140038B25
0x140038a51  mov     r8, rsi; Size
0x140038a54  lea     rcx, [rbp+57h+var_60]; void *
0x140038a58  xor     edx, edx; Val
0x140038a5a  call    memset
0x140038a5f  mov     rcx, [rbx+38h]
0x140038a63  mov     [rbp+57h+var_40], 27h ; '''
0x140038a6a  call    XilEndpoint_GetRemoteHandle
0x140038a6f  mov     rcx, [rbx+28h]
0x140038a73  lea     r9, [rbp+57h+var_80]
0x140038a77  mov     [rbp+57h+var_38], rax
0x140038a7b  lea     rdx, [rbp+57h+var_60]
0x140038a7f  mov     eax, [rbx+40h]
0x140038a82  mov     r8d, esi
0x140038a85  mov     [rbp+57h+var_30], eax
0x140038a88  mov     eax, [rbx+14h]
0x140038a8b  mov     [rbp+57h+var_2C], eax
0x140038a8e  mov     rax, [rcx+2E0h]
0x140038a95  shr     rax, 32h
0x140038a99  and     al, 1
0x140038a9b  mov     dword ptr [rsp+0B0h+var_90], 18h
0x140038aa3  mov     [rbp+57h+var_28], al
0x140038aa6  mov     rcx, [rcx+70h]
0x140038aaa  call    SecureChannel_SendRequestSynchronously
0x140038aaf  mov     esi, eax
0x140038ab1  test    eax, eax
0x140038ab3  js      short loc_140038B1A
0x140038ab5  mov     eax, dword ptr [rbp+57h+var_80]
0x140038ab8  test    eax, eax
0x140038aba  jns     loc_140038B4C
0x140038ac0  mov     esi, eax
0x140038ac2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140038ac9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140038ad0  jz      short loc_140038AFB
0x140038ad2  mov     rcx, [rbx+28h]
0x140038ad6  lea     rax, WPP_dd12c690235e31d2d4306bcf93bb1f34_Traceguids
0x140038add  mov     r9d, 18h
0x140038ae3  mov     [rsp+0B0h+var_88], esi
0x140038ae7  mov     dl, 2
0x140038ae9  mov     [rsp+0B0h+var_90], rax
0x140038aee  mov     rcx, [rcx+48h]
0x140038af2  lea     r8d, [r9-0Ah]
0x140038af6  call    WPP_RECORDER_SF_d
0x140038afb  mov     r9d, 813h
0x140038b01  lea     r8, aOnecoreDrivers_19
0x140038b08  xor     edx, edx
0x140038b0a  lea     rcx, aTransferringcr
0x140038b11  call    Debug_FreAssertMsg
0x140038b16  test    esi, esi
0x140038b18  jns     short loc_140038B25
0x140038b1a  mov     rdx, rdi
0x140038b1d  mov     rcx, r14
0x140038b20  call    CommonBuffer_ReleaseBuffer
0x140038b25  mov     eax, esi
0x140038b27  mov     rcx, [rbp+57h+var_20]
0x140038b2b  xor     rcx, rsp; StackCookie
0x140038b2e  call    __security_check_cookie
0x140038b33  lea     r11, [rsp+0B0h+var_10]
0x140038b3b  mov     rbx, [r11+28h]
0x140038b3f  mov     rsi, [r11+30h]
0x140038b43  mov     rsp, r11
0x140038b46  pop     r14
0x140038b48  pop     rdi
0x140038b49  pop     rbp
0x140038b4a  retn
0x140038b4c  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140038b50  lea     rcx, [rbx+60h]; SpinLock
0x140038b54  mov     [rbx+128h], rax
0x140038b5b  mov     rax, [rbp+57h+var_70]
0x140038b5f  mov     [rdi+18h], rax
0x140038b63  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140038b6a  nop     dword ptr [rax+rax+00h]
0x140038b6f  mov     [rbx+68h], al
0x140038b72  lea     rax, [rbx+0D0h]
0x140038b79  mov     rcx, [rax+8]
0x140038b7d  cmp     [rcx], rax
0x140038b80  jz      short loc_140038B89
0x140038b82  mov     ecx, 3
0x140038b87  int     29h; Win8: RtlFailFast(ecx)
0x140038b89  mov     [rdi+8], rcx
0x140038b8d  mov     [rdi], rax
0x140038b90  mov     [rcx], rdi
0x140038b93  lea     rcx, [rbx+60h]; SpinLock
0x140038b97  mov     [rax+8], rdi
0x140038b9b  mov     dl, [rbx+68h]; NewIrql
0x140038b9e  call    cs:__imp_KeReleaseSpinLock
0x140038ba5  nop     dword ptr [rax+rax+00h]
0x140038baa  jmp     loc_140038B25
```

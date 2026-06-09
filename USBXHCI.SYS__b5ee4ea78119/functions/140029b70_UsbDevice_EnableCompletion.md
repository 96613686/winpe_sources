# UsbDevice_EnableCompletion

- ea: `0x140029b70`
- end: `0x140029fc6`
- name: `UsbDevice_EnableCompletion`
- size: `1110`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140002568`
- `0x14000c264`
- `0x14001d02c`
- `0x1400216b8`
- `0x140024f24`
- `0x140029840`
- `0x140029b70`
- `0x140029fcc`
- `0x14002a060`
- `0x14002a148`
- `0x14002b2c0`
- `0x14002b300`
- `0x140031928`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`

## string_xrefs

- `0x140029cbf`: `Enable Slot command returned a SlotId value that is already in use`

## pseudocode

```c
__int64 __fastcall UsbDevice_EnableCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  _QWORD *v6; // r10
  char v7; // al
  __int64 v8; // r15
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 result; // rax
  __int64 v15; // rdi
  char v16; // si
  __int64 v17; // rdx
  __int16 v18; // ax
  int v19; // edx
  int v20; // edx
  __int64 v21; // rbp
  _OWORD v22[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v23; // [rsp+60h] [rbp-48h]

  v3 = *(_QWORD *)(a1 + 48);
  v6 = *(_QWORD **)(v3 + 8);
  if ( (_DWORD)a2 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_q(v6[9], a2, 12, 15, (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids, *(_QWORD *)v3);
    }
    v16 = 1;
    LODWORD(v11) = *(_BYTE *)(v3 + 440) == 0 ? 0xC0000001 : 0;
    goto LABEL_13;
  }
  v7 = *(_BYTE *)(a1 + 60);
  if ( v7 != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 3;
      WPP_RECORDER_SF_D(v6[9], a2, 12, 19, (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids, v7);
    }
    if ( *(_BYTE *)(a1 + 60) != 9 )
      goto LABEL_22;
    memset(v22, 0, sizeof(v22));
    v23 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount > 0x33 )
      {
        LOWORD(v22[0]) = *(_WORD *)(WdfStructures + 408);
        goto LABEL_21;
      }
      v18 = -1;
    }
    else
    {
      v18 = 40;
    }
    LOWORD(v22[0]) = v18;
LABEL_21:
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _OWORD *))(WdfFunctions_01033 + 2128))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 432),
      v22);
    *(_DWORD *)(*((_QWORD *)&v22[0] + 1) + 32LL) |= 2u;
LABEL_22:
    if ( *(_BYTE *)(v3 + 440) )
    {
      Controller_ReportFatalError(*(_QWORD *)(v3 + 8), 2, 4118, 0, 0, 0, 0);
      v16 = 0;
    }
    else
    {
      v16 = 1;
    }
    LODWORD(v11) = -1073741823;
    goto LABEL_13;
  }
  v8 = v6[11];
  v9 = v6[17];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_dq(
      v6[9],
      a2,
      12,
      16,
      (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
      *(_BYTE *)(a1 + 61),
      *(_QWORD *)v3);
  }
  *(_BYTE *)(v3 + 142) = 1;
  *(_BYTE *)(v3 + 143) = *(_BYTE *)(a1 + 61);
  Endpoint_SetLogIdentifier(*(_QWORD *)(v3 + 184));
  v10 = XilDeviceSlot_SetDeviceContext(v9, v3, *(unsigned __int8 *)(v3 + 143));
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = *(_QWORD *)(v8 + 48);
    if ( v12 )
      v13 = v12 + 4LL * *(unsigned __int8 *)(v3 + 143);
    else
      v13 = 0;
    *(_QWORD *)(v3 + 168) = v13;
    LOBYTE(v13) = 1;
    result = UsbDevice_SetAddress(v3, v13);
    v15 = (int)result;
    if ( (int)result < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = *(unsigned __int8 *)(v3 + 143);
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_DD(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v20,
          12,
          18,
          (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
          *(_BYTE *)(v3 + 143),
          result);
      }
      v21 = *(_QWORD *)(*(_QWORD *)(v3 + 8) + 144LL);
      memset((void *)(v3 + 464), 0, 0x60u);
      if ( *(_BYTE *)(v3 + 440) )
      {
        return Controller_ReportFatalErrorEx(*(_QWORD *)(v3 + 8), 2, 4117, 0, v15, 0, 0, 0);
      }
      else
      {
        *(_DWORD *)(v3 + 500) = 10240;
        *(_QWORD *)(v3 + 504) = UsbDevice_DisableCompletionReturnFailure;
        *(_BYTE *)(v3 + 503) = *(_BYTE *)(v3 + 143);
        *(_QWORD *)(v3 + 512) = v3;
        *(_QWORD *)(v3 + 536) = 0;
        *(_QWORD *)(v3 + 544) = 0;
        *(_QWORD *)(v3 + 552) = 0;
        return Command_SendCommand(v21, v3 + 464);
      }
    }
    return result;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = *(unsigned __int8 *)(v3 + 143);
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_DD(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v19,
      12,
      17,
      (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
      *(_BYTE *)(v3 + 143),
      v10);
  }
  Controller_HwVerifierBreakIfEnabled(
    *(_QWORD *)(v3 + 8),
    *(_QWORD *)v3,
    0,
    0x20000,
    (__int64)"Enable Slot command returned a SlotId value that is already in use",
    a1 + 24,
    a3);
  Controller_ReportFatalErrorEx(*(_QWORD *)(v3 + 8), 2, 4116, 0, v11, 0, 0, 0);
  v16 = 1;
LABEL_13:
  LOBYTE(a2) = 1;
  result = Endpoint_Disable(*(_QWORD *)(v3 + 184), a2);
  if ( v16 )
  {
    v17 = *(_QWORD *)(v3 + 432);
    *(_QWORD *)(v3 + 432) = 0;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             v17,
             (unsigned int)v11);
  }
  return result;
}

```

## disassembly

```asm
0x140029b70  mov     [rsp+arg_8], rbx
0x140029b75  push    rbp
0x140029b76  push    rsi
0x140029b77  push    rdi
0x140029b78  push    r12
0x140029b7a  push    r13
0x140029b7c  push    r14
0x140029b7e  push    r15
0x140029b80  sub     rsp, 70h
0x140029b84  mov     rax, cs:__security_cookie
0x140029b8b  xor     rax, rsp
0x140029b8e  mov     [rsp+0A8h+var_40], rax
0x140029b93  mov     rbx, [rcx+30h]
0x140029b97  xor     r13d, r13d
0x140029b9a  mov     r12, r8
0x140029b9d  mov     r14, rcx
0x140029ba0  mov     r10, [rbx+8]
0x140029ba4  cmp     edx, 3
0x140029ba7  jz      loc_140029D44
0x140029bad  movzx   eax, byte ptr [rcx+3Ch]
0x140029bb1  cmp     al, 1
0x140029bb3  jnz     loc_140029F49
0x140029bb9  mov     r15, [r10+58h]
0x140029bbd  mov     rdi, [r10+88h]
0x140029bc4  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029bcb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029bd2  lea     rbp, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x140029bd9  jz      short loc_140029C03
0x140029bdb  movzx   ecx, byte ptr [rcx+3Dh]
0x140029bdf  lea     r9d, [r13+10h]
0x140029be3  mov     rax, [rbx]
0x140029be6  lea     r8d, [r13+0Ch]
0x140029bea  mov     [rsp+0A8h+var_78], rax
0x140029bef  mov     dl, 4
0x140029bf1  mov     dword ptr [rsp+0A8h+var_80], ecx
0x140029bf5  mov     rcx, [r10+48h]
0x140029bf9  mov     [rsp+0A8h+var_88], rbp
0x140029bfe  call    WPP_RECORDER_SF_dq
0x140029c03  mov     byte ptr [rbx+8Eh], 1
0x140029c0a  mov     al, [r14+3Dh]
0x140029c0e  mov     [rbx+8Fh], al
0x140029c14  mov     rcx, [rbx+0B8h]
0x140029c1b  call    Endpoint_SetLogIdentifier
0x140029c20  movzx   r8d, byte ptr [rbx+8Fh]
0x140029c28  mov     rdx, rbx
0x140029c2b  mov     rcx, rdi
0x140029c2e  call    XilDeviceSlot_SetDeviceContext
0x140029c33  movsxd  rdi, eax
0x140029c36  test    eax, eax
0x140029c38  js      short loc_140029C94
0x140029c3a  mov     rcx, [r15+30h]
0x140029c3e  test    rcx, rcx
0x140029c41  jz      loc_140029E63
0x140029c47  movzx   eax, byte ptr [rbx+8Fh]
0x140029c4e  lea     rdx, [rcx+rax*4]
0x140029c52  mov     [rbx+0A8h], rdx
0x140029c59  mov     rcx, rbx
0x140029c5c  mov     dl, 1
0x140029c5e  call    UsbDevice_SetAddress
0x140029c63  movsxd  rdi, eax
0x140029c66  test    eax, eax
0x140029c68  js      loc_140029E6B
0x140029c6e  mov     rcx, [rsp+0A8h+var_40]
0x140029c73  xor     rcx, rsp; StackCookie
0x140029c76  call    __security_check_cookie
0x140029c7b  mov     rbx, [rsp+0A8h+arg_8]
0x140029c83  add     rsp, 70h
0x140029c87  pop     r15
0x140029c89  pop     r14
0x140029c8b  pop     r13
0x140029c8d  pop     r12
0x140029c8f  pop     rdi
0x140029c90  pop     rsi
0x140029c91  pop     rbp
0x140029c92  retn
0x140029c94  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029c9b  jnz     loc_140029E31
0x140029ca1  mov     rdx, [rbx]
0x140029ca4  lea     rax, [r14+18h]
0x140029ca8  mov     rcx, [rbx+8]
0x140029cac  mov     r9d, 20000h
0x140029cb2  mov     [rsp+0A8h+var_78], r12
0x140029cb7  xor     r8d, r8d
0x140029cba  mov     [rsp+0A8h+var_80], rax
0x140029cbf  lea     rax, aEnableSlotComm; "Enable Slot command returned a SlotId v"...
0x140029cc6  mov     [rsp+0A8h+var_88], rax
0x140029ccb  call    Controller_HwVerifierBreakIfEnabled
0x140029cd0  mov     rcx, [rbx+8]
0x140029cd4  xor     r9d, r9d
0x140029cd7  mov     [rsp+0A8h+var_70], r13
0x140029cdc  mov     r8d, 1014h
0x140029ce2  mov     [rsp+0A8h+var_78], r13
0x140029ce7  mov     [rsp+0A8h+var_80], r13
0x140029cec  lea     edx, [r9+2]
0x140029cf0  mov     [rsp+0A8h+var_88], rdi
0x140029cf5  call    Controller_ReportFatalErrorEx
0x140029cfa  mov     sil, 1
0x140029cfd  mov     rcx, [rbx+0B8h]
0x140029d04  mov     dl, 1
0x140029d06  call    Endpoint_Disable
0x140029d0b  test    sil, sil
0x140029d0e  jz      loc_140029C6E
0x140029d14  mov     rdx, [rbx+1B0h]
0x140029d1b  mov     r8d, edi
0x140029d1e  mov     [rbx+1B0h], r13
0x140029d25  mov     rax, cs:WdfFunctions_01033
0x140029d2c  mov     rcx, cs:WdfDriverGlobals
0x140029d33  mov     rax, [rax+838h]
0x140029d3a  call    _guard_dispatch_icall
0x140029d3f  jmp     loc_140029C6E
0x140029d44  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029d4b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029d52  jnz     loc_140029E03
0x140029d58  mov     al, [rbx+1B8h]
0x140029d5e  mov     sil, 1
0x140029d61  neg     al
0x140029d63  sbb     edi, edi
0x140029d65  not     edi
0x140029d67  and     edi, 0C0000001h
0x140029d6d  jmp     short loc_140029CFD
0x140029d6f  xor     eax, eax
0x140029d71  xorps   xmm0, xmm0
0x140029d74  cmp     cs:WdfClientVersionHigherThanFramework, r13b
0x140029d7b  movups  [rsp+0A8h+var_68], xmm0
0x140029d80  mov     [rsp+0A8h+var_48], rax
0x140029d85  movups  [rsp+0A8h+var_58], xmm0
0x140029d8a  jnz     loc_140029F8E
0x140029d90  mov     eax, 28h ; '('
0x140029d95  mov     word ptr [rsp+0A8h+var_68], ax
0x140029d9a  mov     rax, cs:WdfFunctions_01033
0x140029da1  lea     r8, [rsp+0A8h+var_68]
0x140029da6  mov     rdx, [rbx+1B0h]
0x140029dad  mov     rcx, cs:WdfDriverGlobals
0x140029db4  mov     rax, [rax+850h]
0x140029dbb  call    _guard_dispatch_icall
0x140029dc0  mov     rax, qword ptr [rsp+0A8h+var_68+8]
0x140029dc5  or      dword ptr [rax+20h], 2
0x140029dc9  cmp     [rbx+1B8h], r13b
0x140029dd0  jz      loc_140029FB9
0x140029dd6  mov     rcx, [rbx+8]
0x140029dda  xor     r9d, r9d
0x140029ddd  mov     [rsp+0A8h+var_78], r13
0x140029de2  mov     r8d, 1016h
0x140029de8  mov     [rsp+0A8h+var_80], r13
0x140029ded  mov     [rsp+0A8h+var_88], r13
0x140029df2  lea     edx, [r9+2]
0x140029df6  call    Controller_ReportFatalError
0x140029dfb  mov     sil, r13b
0x140029dfe  jmp     loc_140029FBC
0x140029e03  mov     rax, [rbx]
0x140029e06  lea     rbp, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x140029e0d  mov     rcx, [r10+48h]
0x140029e11  mov     r9d, 0Fh
0x140029e17  mov     [rsp+0A8h+var_80], rax
0x140029e1c  mov     dl, 4
0x140029e1e  mov     [rsp+0A8h+var_88], rbp
0x140029e23  lea     r8d, [r9-3]
0x140029e27  call    WPP_RECORDER_SF_q
0x140029e2c  jmp     loc_140029D58
0x140029e31  movzx   edx, byte ptr [rbx+8Fh]
0x140029e38  mov     r9d, 11h
0x140029e3e  mov     rcx, [rbx+8]
0x140029e42  mov     dword ptr [rsp+0A8h+var_78], edi
0x140029e46  mov     dword ptr [rsp+0A8h+var_80], edx
0x140029e4a  mov     dl, 2
0x140029e4c  lea     r8d, [r9-5]
0x140029e50  mov     [rsp+0A8h+var_88], rbp
0x140029e55  mov     rcx, [rcx+48h]
0x140029e59  call    WPP_RECORDER_SF_DD
0x140029e5e  jmp     loc_140029CA1
0x140029e63  mov     rdx, r13
0x140029e66  jmp     loc_140029C52
0x140029e6b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140029e72  jz      short loc_140029EA1
0x140029e74  movzx   edx, byte ptr [rbx+8Fh]
0x140029e7b  mov     r9d, 12h
0x140029e81  mov     rcx, [rbx+8]
0x140029e85  mov     dword ptr [rsp+0A8h+var_78], edi
0x140029e89  mov     dword ptr [rsp+0A8h+var_80], edx
0x140029e8d  mov     dl, 2
0x140029e8f  lea     r8d, [r9-6]
0x140029e93  mov     [rsp+0A8h+var_88], rbp
0x140029e98  mov     rcx, [rcx+48h]
0x140029e9c  call    WPP_RECORDER_SF_DD
0x140029ea1  mov     rax, [rbx+8]
0x140029ea5  lea     rsi, [rbx+1D0h]
0x140029eac  xor     edx, edx; Val
0x140029eae  mov     rcx, rsi; void *
0x140029eb1  mov     rbp, [rax+90h]
0x140029eb8  lea     r8d, [rdx+60h]; Size
0x140029ebc  call    memset
0x140029ec1  cmp     [rbx+1B8h], r13b
0x140029ec8  jz      short loc_140029EF9
0x140029eca  mov     rcx, [rbx+8]
0x140029ece  xor     r9d, r9d
0x140029ed1  mov     [rsp+0A8h+var_70], r13
0x140029ed6  mov     r8d, 1015h
0x140029edc  mov     [rsp+0A8h+var_78], r13
0x140029ee1  mov     [rsp+0A8h+var_80], r13
0x140029ee6  lea     edx, [r9+2]
0x140029eea  mov     [rsp+0A8h+var_88], rdi
0x140029eef  call    Controller_ReportFatalErrorEx
0x140029ef4  jmp     loc_140029C6E
0x140029ef9  lea     rax, UsbDevice_DisableCompletionReturnFailure
0x140029f00  mov     dword ptr [rbx+1F4h], 2800h
0x140029f0a  mov     [rbx+1F8h], rax
0x140029f11  mov     rdx, rsi
0x140029f14  mov     al, [rbx+8Fh]
0x140029f1a  mov     rcx, rbp
0x140029f1d  mov     [rbx+1F7h], al
0x140029f23  mov     [rbx+200h], rbx
0x140029f2a  mov     [rbx+218h], r13
0x140029f31  mov     [rbx+220h], r13
0x140029f38  mov     [rbx+228h], r13
0x140029f3f  call    Command_SendCommand
0x140029f44  jmp     loc_140029C6E
0x140029f49  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029f50  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029f57  jz      short loc_140029F7E
0x140029f59  mov     rcx, [r10+48h]
0x140029f5d  lea     rbp, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x140029f64  mov     r9d, 13h
0x140029f6a  mov     dword ptr [rsp+0A8h+var_80], eax
0x140029f6e  mov     dl, 3
0x140029f70  mov     [rsp+0A8h+var_88], rbp
0x140029f75  lea     r8d, [r9-7]
0x140029f79  call    WPP_RECORDER_SF_D
0x140029f7e  cmp     byte ptr [r14+3Ch], 9
0x140029f83  jnz     loc_140029DC9
0x140029f89  jmp     loc_140029D6F
0x140029f8e  cmp     cs:WdfStructureCount, 33h ; '3'
0x140029f95  jbe     short loc_140029FAF
0x140029f97  mov     rax, cs:WdfStructures
0x140029f9e  movzx   ecx, word ptr [rax+198h]
0x140029fa5  mov     word ptr [rsp+0A8h+var_68], cx
0x140029faa  jmp     loc_140029D9A
0x140029faf  mov     eax, 0FFFFh
0x140029fb4  jmp     loc_140029D95
0x140029fb9  mov     sil, 1
0x140029fbc  mov     edi, 0C0000001h
0x140029fc1  jmp     loc_140029CFD
```

# RootHub_UcxEvtClearHubFeature

- ea: `0x14004a2c0`
- end: `0x14004a5bf`
- name: `RootHub_UcxEvtClearHubFeature`
- size: `767`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14001ac48`
- `0x14001bb78`
- `0x14004a2c0`
- `0x14004b624`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004a332`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a332`

## string_xrefs

- `0x14004a351`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtClearHubFeature(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int16 v4; // ax
  int v5; // edx
  __int64 v6; // rbp
  int v7; // r9d
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // r8
  __int128 v13; // [rsp+70h] [rbp-58h] BYREF
  __int128 v14; // [rsp+80h] [rbp-48h]
  __int64 v15; // [rsp+90h] [rbp-38h]

  v13 = 0;
  v15 = 0;
  v14 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 8) + 1041LL) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\roothub.c",
      977);
  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( !WdfClientVersionHigherThanFramework )
  {
    v4 = 40;
    goto LABEL_9;
  }
  if ( (unsigned int)WdfStructureCount <= 0x33 )
  {
    v4 = -1;
LABEL_9:
    LOWORD(v13) = v4;
    goto LABEL_10;
  }
  LOWORD(v13) = *(_WORD *)(WdfStructures + 408);
LABEL_10:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v13);
  v6 = *((_QWORD *)&v13 + 1);
  if ( *(_WORD *)(*((_QWORD *)&v13 + 1) + 128LL) != 288 || *(_DWORD *)(*((_QWORD *)&v13 + 1) + 132LL) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(unsigned __int8 *)(*((_QWORD *)&v13 + 1) + 134LL);
      v7 = 35;
      v9 = *(unsigned __int8 *)(*((_QWORD *)&v13 + 1) + 133LL);
      goto LABEL_24;
    }
LABEL_25:
    v11 = 3221225473LL;
    *(_DWORD *)(v6 + 4) = -1073741820;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v11);
  }
  if ( *(_WORD *)(*((_QWORD *)&v13 + 1) + 130LL) )
  {
    if ( *(_WORD *)(*((_QWORD *)&v13 + 1) + 130LL) != 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = 38;
        v8 = *(unsigned __int8 *)(*((_QWORD *)&v13 + 1) + 134LL);
        v9 = *(unsigned __int8 *)(*((_QWORD *)&v13 + 1) + 133LL);
LABEL_24:
        WPP_RECORDER_SF_DDDDDDDD(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v8, v9, v7);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 37;
LABEL_20:
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v5,
        11,
        v10,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = 36;
    goto LABEL_20;
  }
  *(_DWORD *)(v6 + 4) = 0;
  v11 = 0;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v11);
}

```

## disassembly

```asm
0x14004a2c0  mov     r11, rsp
0x14004a2c3  mov     [r11+18h], rbx
0x14004a2c7  push    rbp
0x14004a2c8  push    rsi
0x14004a2c9  push    rdi
0x14004a2ca  push    r14
0x14004a2cc  push    r15
0x14004a2ce  sub     rsp, 0A0h
0x14004a2d5  mov     rax, cs:__security_cookie
0x14004a2dc  xor     rax, rsp
0x14004a2df  mov     [rsp+0C8h+var_30], rax
0x14004a2e7  mov     r8, cs:off_14006C130
0x14004a2ee  xor     eax, eax
0x14004a2f0  xorps   xmm0, xmm0
0x14004a2f3  mov     r15, rdx
0x14004a2f6  movups  [rsp+0C8h+var_58], xmm0
0x14004a2fb  mov     [r11-38h], rax
0x14004a2ff  mov     rdx, rcx
0x14004a302  mov     rax, cs:WdfFunctions_01033
0x14004a309  mov     rcx, cs:WdfDriverGlobals
0x14004a310  movups  xmmword ptr [r11-48h], xmm0
0x14004a315  mov     rax, [rax+650h]
0x14004a31c  call    _guard_dispatch_icall
0x14004a321  xor     ebx, ebx
0x14004a323  mov     r14, rax
0x14004a326  mov     rcx, [rax+8]
0x14004a32a  cmp     [rcx+411h], bl
0x14004a330  jz      short loc_14004A35D
0x14004a332  call    cs:__imp_KeGetCurrentIrql
0x14004a339  nop     dword ptr [rax+rax+00h]
0x14004a33e  test    al, al
0x14004a340  jz      short loc_14004A35D
0x14004a342  mov     r9d, 3D1h
0x14004a348  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14004a34f  xor     edx, edx
0x14004a351  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14004a358  call    Debug_FreAssertMsg
0x14004a35d  xor     eax, eax
0x14004a35f  xorps   xmm0, xmm0
0x14004a362  cmp     cs:WdfClientVersionHigherThanFramework, bl
0x14004a368  movups  [rsp+0C8h+var_58], xmm0
0x14004a36d  mov     [rsp+0C8h+var_38], rax
0x14004a375  movups  [rsp+0C8h+var_48], xmm0
0x14004a37d  jz      short loc_14004A3A4
0x14004a37f  cmp     cs:WdfStructureCount, 33h ; '3'
0x14004a386  jbe     short loc_14004A39D
0x14004a388  mov     rax, cs:WdfStructures
0x14004a38f  movzx   ecx, word ptr [rax+198h]
0x14004a396  mov     word ptr [rsp+0C8h+var_58], cx
0x14004a39b  jmp     short loc_14004A3AE
0x14004a39d  mov     eax, 0FFFFh
0x14004a3a2  jmp     short loc_14004A3A9
0x14004a3a4  mov     eax, 28h ; '('
0x14004a3a9  mov     word ptr [rsp+0C8h+var_58], ax
0x14004a3ae  mov     rax, cs:WdfFunctions_01033
0x14004a3b5  lea     r8, [rsp+0C8h+var_58]
0x14004a3ba  mov     rcx, cs:WdfDriverGlobals
0x14004a3c1  mov     rdx, r15
0x14004a3c4  mov     rax, [rax+850h]
0x14004a3cb  call    _guard_dispatch_icall
0x14004a3d0  mov     rbp, qword ptr [rsp+0C8h+var_58+8]
0x14004a3d5  movzx   ecx, byte ptr [rbp+80h]
0x14004a3dc  cmp     cl, 20h ; ' '
0x14004a3df  jnz     loc_14004A4F1
0x14004a3e5  cmp     byte ptr [rbp+81h], 1
0x14004a3ec  jnz     loc_14004A4F1
0x14004a3f2  cmp     [rbp+84h], bx
0x14004a3f9  jnz     loc_14004A4F1
0x14004a3ff  cmp     [rbp+86h], bx
0x14004a406  jnz     loc_14004A4F1
0x14004a40c  movzx   eax, word ptr [rbp+82h]
0x14004a413  test    eax, eax
0x14004a415  jz      loc_14004A4AF
0x14004a41b  cmp     eax, 1
0x14004a41e  jz      short loc_14004A497
0x14004a420  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a427  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a42e  jz      loc_14004A56D
0x14004a434  movzx   eax, byte ptr [rbp+87h]
0x14004a43b  mov     r9d, 26h ; '&'
0x14004a441  movzx   edx, byte ptr [rbp+86h]
0x14004a448  movzx   r8d, byte ptr [rbp+85h]
0x14004a450  movzx   r10d, byte ptr [rbp+84h]
0x14004a458  movzx   r11d, byte ptr [rbp+83h]
0x14004a460  movzx   ebx, byte ptr [rbp+82h]
0x14004a467  mov     [rsp+0C8h+var_68], eax
0x14004a46b  mov     [rsp+0C8h+var_70], edx
0x14004a46f  mov     [rsp+0C8h+var_78], r8d
0x14004a474  mov     [rsp+0C8h+var_80], r10d
0x14004a479  mov     [rsp+0C8h+var_88], r11d
0x14004a47e  mov     [rsp+0C8h+var_90], ebx
0x14004a482  mov     [rsp+0C8h+var_98], 1
0x14004a48a  mov     [rsp+0C8h+var_A0], 20h ; ' '
0x14004a492  jmp     loc_14004A560
0x14004a497  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a49e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a4a5  jz      short loc_14004A4E6
0x14004a4a7  mov     r9d, 25h ; '%'
0x14004a4ad  jmp     short loc_14004A4C5
0x14004a4af  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a4b6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a4bd  jz      short loc_14004A4E6
0x14004a4bf  mov     r9d, 24h ; '$'
0x14004a4c5  mov     rcx, [r14+8]
0x14004a4c9  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14004a4d0  mov     r8d, 0Bh
0x14004a4d6  mov     [rsp+0C8h+var_A8], rax
0x14004a4db  mov     dl, 4
0x14004a4dd  mov     rcx, [rcx+48h]
0x14004a4e1  call    WPP_RECORDER_SF_
0x14004a4e6  mov     [rbp+4], ebx
0x14004a4e9  mov     r8d, ebx
0x14004a4ec  jmp     loc_14004A57A
0x14004a4f1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004a4f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004a4ff  jz      short loc_14004A56D
0x14004a501  movzx   eax, byte ptr [rbp+87h]
0x14004a508  mov     esi, ecx
0x14004a50a  movzx   edx, byte ptr [rbp+86h]
0x14004a511  mov     r9d, 23h ; '#'
0x14004a517  movzx   r8d, byte ptr [rbp+85h]
0x14004a51f  movzx   r10d, byte ptr [rbp+84h]
0x14004a527  movzx   r11d, byte ptr [rbp+83h]
0x14004a52f  movzx   ebx, byte ptr [rbp+82h]
0x14004a536  movzx   edi, byte ptr [rbp+81h]
0x14004a53d  mov     [rsp+0C8h+var_68], eax
0x14004a541  mov     [rsp+0C8h+var_70], edx
0x14004a545  mov     [rsp+0C8h+var_78], r8d
0x14004a54a  mov     [rsp+0C8h+var_80], r10d
0x14004a54f  mov     [rsp+0C8h+var_88], r11d
0x14004a554  mov     [rsp+0C8h+var_90], ebx
0x14004a558  mov     [rsp+0C8h+var_98], edi
0x14004a55c  mov     [rsp+0C8h+var_A0], ecx
0x14004a560  mov     rcx, [r14+8]
0x14004a564  mov     rcx, [rcx+48h]
0x14004a568  call    WPP_RECORDER_SF_DDDDDDDD
0x14004a56d  mov     r8d, 0C0000001h
0x14004a573  mov     dword ptr [rbp+4], 0C0000004h
0x14004a57a  mov     rax, cs:WdfFunctions_01033
0x14004a581  mov     rdx, r15
0x14004a584  mov     rcx, cs:WdfDriverGlobals
0x14004a58b  mov     rax, [rax+838h]
0x14004a592  call    _guard_dispatch_icall
0x14004a597  mov     rcx, [rsp+0C8h+var_30]
0x14004a59f  xor     rcx, rsp; StackCookie
0x14004a5a2  call    __security_check_cookie
0x14004a5a7  mov     rbx, [rsp+0C8h+arg_10]
0x14004a5af  add     rsp, 0A0h
0x14004a5b6  pop     r15
0x14004a5b8  pop     r14
0x14004a5ba  pop     rdi
0x14004a5bb  pop     rsi
0x14004a5bc  pop     rbp
0x14004a5bd  retn
```

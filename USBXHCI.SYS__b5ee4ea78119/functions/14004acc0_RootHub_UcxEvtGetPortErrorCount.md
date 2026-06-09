# RootHub_UcxEvtGetPortErrorCount

- ea: `0x14004acc0`
- end: `0x14004b096`
- name: `RootHub_UcxEvtGetPortErrorCount`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140019d6c`
- `0x14001ac48`
- `0x14001bb78`
- `0x14001f830`
- `0x14001fb30`
- `0x14004acc0`
- `0x14004b624`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004ad3b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004ad3b`

## string_xrefs

- `0x14004ad5a`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall RootHub_UcxEvtGetPortErrorCount(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int16 v6; // ax
  __int64 v7; // rbp
  int v8; // edx
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 v11; // r8
  unsigned __int16 Ulong; // ax
  int v13; // edx
  char v14; // r12
  unsigned int v15; // r15d
  int v16; // r9d
  int v17; // edx
  int v18; // r8d
  __int128 v20; // [rsp+70h] [rbp-68h] BYREF
  __int128 v21; // [rsp+80h] [rbp-58h]
  __int64 v22; // [rsp+90h] [rbp-48h]

  v20 = 0;
  v22 = 0;
  v21 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C130);
  v4 = *(_QWORD *)(v3 + 8);
  v5 = *(_QWORD *)(v4 + 88);
  if ( *(_BYTE *)(v4 + 1041) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\roothub.c",
      3332);
  v20 = 0;
  v22 = 0;
  v21 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v20) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_10;
    }
    v6 = -1;
  }
  else
  {
    v6 = 40;
  }
  LOWORD(v20) = v6;
LABEL_10:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    &v20);
  v7 = *((_QWORD *)&v20 + 1);
  if ( !(unsigned __int8)Controller_IsControllerAccessible(*(_QWORD *)(v3 + 8)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v8,
        11,
        184,
        (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
    }
    *(_DWORD *)(v7 + 4) = -1073713152;
    v9 = 3221225486LL;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v9);
  }
  if ( *(_WORD *)(v7 + 128) != 3491
    || *(_WORD *)(v7 + 130)
    || (v10 = *(unsigned __int16 *)(v7 + 132), !*(_WORD *)(v7 + 132))
    || v10 > *(_DWORD *)(v3 + 16)
    || *(_WORD *)(v7 + 134) != 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = *(unsigned __int8 *)(v7 + 134);
      v16 = 185;
      v18 = *(unsigned __int8 *)(v7 + 133);
      goto LABEL_30;
    }
LABEL_31:
    v9 = 3221225473LL;
    *(_DWORD *)(v7 + 4) = -1073741820;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             a2,
             v9);
  }
  v11 = v10 - 1;
  if ( *(_BYTE *)(120 * v11 + *(_QWORD *)(v3 + 48) + 13) != 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 188;
      v17 = *(unsigned __int8 *)(v7 + 134);
      v18 = *(unsigned __int8 *)(v7 + 133);
LABEL_30:
      WPP_RECORDER_SF_DDDDDDDD(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v17, v18, v16);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  Ulong = XilRegister_ReadUlong(v5, 16 * v11 + 8 + *(_QWORD *)(v3 + 40));
  v14 = Ulong;
  **(_WORD **)(v7 + 40) = Ulong;
  v15 = Ulong;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 4;
    WPP_RECORDER_SF_dD(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v13,
      11,
      186,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
      v10,
      Ulong);
  }
  if ( v15 > 0xA && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_dD(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v13,
      11,
      187,
      (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
      v10,
      v14);
  }
  *(_DWORD *)(v7 + 4) = 0;
  v9 = 0;
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a2,
           v9);
}

```

## disassembly

```asm
0x14004acc0  mov     r11, rsp
0x14004acc3  mov     [r11+18h], rbx
0x14004acc7  push    rbp
0x14004acc8  push    rsi
0x14004acc9  push    rdi
0x14004acca  push    r12
0x14004accc  push    r13
0x14004acce  push    r14
0x14004acd0  push    r15
0x14004acd2  sub     rsp, 0A0h
0x14004acd9  mov     rax, cs:__security_cookie
0x14004ace0  xor     rax, rsp
0x14004ace3  mov     [rsp+0D8h+var_40], rax
0x14004aceb  mov     r8, cs:off_14006C130
0x14004acf2  xor     eax, eax
0x14004acf4  xorps   xmm0, xmm0
0x14004acf7  mov     r13, rdx
0x14004acfa  movups  [rsp+0D8h+var_68], xmm0
0x14004acff  mov     [r11-48h], rax
0x14004ad03  mov     rdx, rcx
0x14004ad06  mov     rax, cs:WdfFunctions_01033
0x14004ad0d  mov     rcx, cs:WdfDriverGlobals
0x14004ad14  movups  xmmword ptr [r11-58h], xmm0
0x14004ad19  mov     rax, [rax+650h]
0x14004ad20  call    _guard_dispatch_icall
0x14004ad25  xor     esi, esi
0x14004ad27  mov     r14, rax
0x14004ad2a  mov     rcx, [rax+8]
0x14004ad2e  mov     rbx, [rcx+58h]
0x14004ad32  cmp     [rcx+411h], sil
0x14004ad39  jz      short loc_14004AD66
0x14004ad3b  call    cs:__imp_KeGetCurrentIrql
0x14004ad42  nop     dword ptr [rax+rax+00h]
0x14004ad47  test    al, al
0x14004ad49  jz      short loc_14004AD66
0x14004ad4b  mov     r9d, 0D04h
0x14004ad51  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14004ad58  xor     edx, edx
0x14004ad5a  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14004ad61  call    Debug_FreAssertMsg
0x14004ad66  xor     eax, eax
0x14004ad68  xorps   xmm0, xmm0
0x14004ad6b  cmp     cs:WdfClientVersionHigherThanFramework, sil
0x14004ad72  movups  [rsp+0D8h+var_68], xmm0
0x14004ad77  mov     [rsp+0D8h+var_48], rax
0x14004ad7f  movups  [rsp+0D8h+var_58], xmm0
0x14004ad87  jz      short loc_14004ADAE
0x14004ad89  cmp     cs:WdfStructureCount, 33h ; '3'
0x14004ad90  jbe     short loc_14004ADA7
0x14004ad92  mov     rax, cs:WdfStructures
0x14004ad99  movzx   ecx, word ptr [rax+198h]
0x14004ada0  mov     word ptr [rsp+0D8h+var_68], cx
0x14004ada5  jmp     short loc_14004ADB8
0x14004ada7  mov     eax, 0FFFFh
0x14004adac  jmp     short loc_14004ADB3
0x14004adae  mov     eax, 28h ; '('
0x14004adb3  mov     word ptr [rsp+0D8h+var_68], ax
0x14004adb8  mov     rax, cs:WdfFunctions_01033
0x14004adbf  lea     r8, [rsp+0D8h+var_68]
0x14004adc4  mov     rcx, cs:WdfDriverGlobals
0x14004adcb  mov     rdx, r13
0x14004adce  mov     rax, [rax+850h]
0x14004add5  call    _guard_dispatch_icall
0x14004adda  mov     rcx, [r14+8]
0x14004adde  mov     rbp, qword ptr [rsp+0D8h+var_68+8]
0x14004ade3  call    Controller_IsControllerAccessible
0x14004ade8  test    al, al
0x14004adea  jnz     short loc_14004AE35
0x14004adec  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004adf3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004adfa  jz      short loc_14004AE23
0x14004adfc  mov     rcx, [r14+8]
0x14004ae00  lea     rsi, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14004ae07  mov     r9d, 0B8h
0x14004ae0d  mov     [rsp+0D8h+var_B8], rsi
0x14004ae12  mov     r8d, 0Bh
0x14004ae18  mov     dl, 4
0x14004ae1a  mov     rcx, [rcx+48h]
0x14004ae1e  call    WPP_RECORDER_SF_
0x14004ae23  mov     dword ptr [rbp+4], 0C0007000h
0x14004ae2a  mov     r8d, 0C000000Eh
0x14004ae30  jmp     loc_14004B04D
0x14004ae35  movzx   r9d, byte ptr [rbp+80h]
0x14004ae3d  cmp     r9b, 0A3h
0x14004ae41  jnz     loc_14004AFC3
0x14004ae47  cmp     byte ptr [rbp+81h], 0Dh
0x14004ae4e  jnz     loc_14004AFC3
0x14004ae54  cmp     [rbp+82h], si
0x14004ae5b  jnz     loc_14004AFC3
0x14004ae61  movzx   edi, word ptr [rbp+84h]
0x14004ae68  test    edi, edi
0x14004ae6a  jz      loc_14004AFC3
0x14004ae70  cmp     edi, [r14+10h]
0x14004ae74  ja      loc_14004AFC3
0x14004ae7a  cmp     word ptr [rbp+86h], 2
0x14004ae82  jnz     loc_14004AFC3
0x14004ae88  mov     rax, [r14+30h]
0x14004ae8c  lea     r8d, [rdi-1]
0x14004ae90  imul    rdx, r8, 78h ; 'x'
0x14004ae94  cmp     byte ptr [rdx+rax+0Dh], 3
0x14004ae99  jnz     loc_14004AF4F
0x14004ae9f  mov     rdx, [r14+28h]
0x14004aea3  mov     rcx, rbx
0x14004aea6  shl     r8, 4
0x14004aeaa  add     r8, 8
0x14004aeae  add     rdx, r8
0x14004aeb1  call    XilRegister_ReadUlong
0x14004aeb6  mov     rcx, [rbp+28h]
0x14004aeba  mov     r12d, eax
0x14004aebd  mov     [rcx], r12w
0x14004aec1  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004aec8  movzx   r15d, r12w
0x14004aecc  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004aed3  lea     rsi, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14004aeda  jz      short loc_14004AF05
0x14004aedc  mov     rcx, [r14+8]
0x14004aee0  mov     r9d, 0BAh
0x14004aee6  mov     [rsp+0D8h+var_A8], r15d
0x14004aeeb  mov     r8d, 0Bh
0x14004aef1  mov     [rsp+0D8h+var_B0], edi
0x14004aef5  mov     dl, 4
0x14004aef7  mov     [rsp+0D8h+var_B8], rsi
0x14004aefc  mov     rcx, [rcx+48h]
0x14004af00  call    WPP_RECORDER_SF_dD
0x14004af05  cmp     r15d, 0Ah
0x14004af09  jbe     short loc_14004AF40
0x14004af0b  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14004af12  jz      short loc_14004AF40
0x14004af14  mov     rcx, [r14+8]
0x14004af18  mov     r9d, 0BBh
0x14004af1e  movzx   eax, r12w
0x14004af22  mov     r8d, 0Bh
0x14004af28  mov     [rsp+0D8h+var_A8], eax
0x14004af2c  mov     dl, 2
0x14004af2e  mov     [rsp+0D8h+var_B0], edi
0x14004af32  mov     rcx, [rcx+48h]
0x14004af36  mov     [rsp+0D8h+var_B8], rsi
0x14004af3b  call    WPP_RECORDER_SF_dD
0x14004af40  mov     dword ptr [rbp+4], 0
0x14004af47  xor     r8d, r8d
0x14004af4a  jmp     loc_14004B04D
0x14004af4f  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004af56  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004af5d  jz      loc_14004B040
0x14004af63  movzx   eax, byte ptr [rbp+87h]
0x14004af6a  mov     r9d, 0BCh
0x14004af70  movzx   edx, byte ptr [rbp+86h]
0x14004af77  movzx   r8d, byte ptr [rbp+85h]
0x14004af7f  movzx   r10d, byte ptr [rbp+84h]
0x14004af87  movzx   r11d, byte ptr [rbp+83h]
0x14004af8f  movzx   ebx, byte ptr [rbp+82h]
0x14004af96  mov     [rsp+0D8h+var_78], eax
0x14004af9a  mov     [rsp+0D8h+var_80], edx
0x14004af9e  mov     [rsp+0D8h+var_88], r8d
0x14004afa3  mov     [rsp+0D8h+var_90], r10d
0x14004afa8  mov     [rsp+0D8h+var_98], r11d
0x14004afad  mov     [rsp+0D8h+var_A0], ebx
0x14004afb1  mov     [rsp+0D8h+var_A8], 0Dh
0x14004afb9  mov     [rsp+0D8h+var_B0], 0A3h
0x14004afc1  jmp     short loc_14004B033
0x14004afc3  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004afca  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004afd1  jz      short loc_14004B040
0x14004afd3  movzx   eax, byte ptr [rbp+87h]
0x14004afda  mov     esi, r9d
0x14004afdd  movzx   edx, byte ptr [rbp+86h]
0x14004afe4  mov     r9d, 0B9h
0x14004afea  movzx   r8d, byte ptr [rbp+85h]
0x14004aff2  movzx   r10d, byte ptr [rbp+84h]
0x14004affa  movzx   r11d, byte ptr [rbp+83h]
0x14004b002  movzx   ebx, byte ptr [rbp+82h]
0x14004b009  movzx   edi, byte ptr [rbp+81h]
0x14004b010  mov     [rsp+0D8h+var_78], eax
0x14004b014  mov     [rsp+0D8h+var_80], edx
0x14004b018  mov     [rsp+0D8h+var_88], r8d
0x14004b01d  mov     [rsp+0D8h+var_90], r10d
0x14004b022  mov     [rsp+0D8h+var_98], r11d
0x14004b027  mov     [rsp+0D8h+var_A0], ebx
0x14004b02b  mov     [rsp+0D8h+var_A8], edi
0x14004b02f  mov     [rsp+0D8h+var_B0], esi
0x14004b033  mov     rcx, [r14+8]
0x14004b037  mov     rcx, [rcx+48h]
0x14004b03b  call    WPP_RECORDER_SF_DDDDDDDD
0x14004b040  mov     r8d, 0C0000001h
0x14004b046  mov     dword ptr [rbp+4], 0C0000004h
0x14004b04d  mov     rax, cs:WdfFunctions_01033
0x14004b054  mov     rdx, r13
0x14004b057  mov     rcx, cs:WdfDriverGlobals
0x14004b05e  mov     rax, [rax+838h]
0x14004b065  call    _guard_dispatch_icall
0x14004b06a  mov     rcx, [rsp+0D8h+var_40]
0x14004b072  xor     rcx, rsp; StackCookie
0x14004b075  call    __security_check_cookie
0x14004b07a  mov     rbx, [rsp+0D8h+arg_10]
0x14004b082  add     rsp, 0A0h
0x14004b089  pop     r15
0x14004b08b  pop     r14
0x14004b08d  pop     r13
0x14004b08f  pop     r12
0x14004b091  pop     rdi
0x14004b092  pop     rsi
0x14004b093  pop     rbp
0x14004b094  retn
```

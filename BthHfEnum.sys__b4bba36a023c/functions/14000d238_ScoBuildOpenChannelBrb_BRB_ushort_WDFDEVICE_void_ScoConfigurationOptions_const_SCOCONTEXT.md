# ScoBuildOpenChannelBrb(_BRB *,ushort,WDFDEVICE__ *,void *,ScoConfigurationOptions const *,_SCOCONTEXT *)

- ea: `0x14000d238`
- end: `0x14000d3d6`
- name: `?ScoBuildOpenChannelBrb@@YAXPEAU_BRB@@GPEAUWDFDEVICE__@@PEAXPEBUScoConfigurationOptions@@PEAU_SCOCONTEXT@@@Z`
- size: `414`
- prototype: `void __fastcall(struct _BRB *, unsigned __int16, struct WDFDEVICE__ *, void *, const struct ScoConfigurationOptions *, struct _SCOCONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14000df64`

## callees

- `0x14000d238`
- `0x140014774`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoBuildOpenChannelBrb(
        struct _BRB *a1,
        USHORT a2,
        struct WDFDEVICE__ *a3,
        void *a4,
        const struct ScoConfigurationOptions *a5,
        struct _SCOCONTEXT *a6)
{
  void *v10; // rax
  __int64 v11; // rax
  int v12; // edx
  int v13; // r8d

  v10 = (void *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *))(WdfFunctions_01015 + 248))(
                  WdfDriverGlobals,
                  a3);
  a1->BrbScoOpenChannel.ChannelHandle = a4;
  a1->BrbScoOpenChannel.ReferenceObject = v10;
  a1->BrbScoOpenChannel.PacketType = a2;
  a1->BrbL2caRegisterServer.BtAddress = *((_QWORD *)a6 + 2);
  a1->BrbGetDeviceInterfaceString.DeviceInterfaceStringCbLength = *((_DWORD *)a5 + 1);
  a1->BrbL2caRegisterServer.IndicationFlags = *((_DWORD *)a5 + 1);
  a1->BrbScoOpenChannel.ContentFormat = *((_WORD *)a5 + 4);
  a1->BrbL2caUnregisterServer.Psm = *((_WORD *)a5 + 5);
  a1->BrbL2caOpenChannel.ConfigOut.Flags = *((_DWORD *)a5 + 3);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          a3,
          off_1400220B0);
  if ( *((_DWORD *)a6 + 26) == 2 && !*(_DWORD *)(v11 + 364) )
    a1->BrbScoOpenChannel.ChannelFlags |= 0x20u;
  LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_DLLDCODECIDDDl(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  a1->BrbScoOpenChannel.CallbackFlags = 1;
  a1->BrbL2caAclTransfer.Timeout = (LONGLONG)BthScoIndicationCallback;
  a1->BrbScoOpenChannel.CallbackContext = a3;
  a1->BrbL2caPing.PingResponseData[18] = 0;
}

```

## disassembly

```asm
0x14000d238  push    rbx
0x14000d23a  push    rbp
0x14000d23b  push    rsi
0x14000d23c  push    rdi
0x14000d23d  sub     rsp, 88h
0x14000d244  mov     rax, cs:WdfFunctions_01015
0x14000d24b  movzx   edi, dx
0x14000d24e  mov     rsi, rcx
0x14000d251  mov     rdx, r8
0x14000d254  mov     rcx, cs:WdfDriverGlobals
0x14000d25b  mov     rbx, r9
0x14000d25e  mov     rbp, r8
0x14000d261  mov     rax, [rax+0F8h]
0x14000d268  call    _guard_dispatch_icall
0x14000d26d  mov     rcx, [rsp+0A8h+arg_20]
0x14000d275  mov     rdx, rbp
0x14000d278  mov     [rsi+0B0h], rbx
0x14000d27f  mov     rbx, [rsp+0A8h+arg_28]
0x14000d287  mov     [rsi+0A8h], rax
0x14000d28e  mov     [rsi+82h], di
0x14000d295  mov     rax, [rbx+10h]
0x14000d299  mov     [rsi+70h], rax
0x14000d29d  mov     eax, [rcx+4]
0x14000d2a0  mov     [rsi+78h], eax
0x14000d2a3  mov     eax, [rcx+4]
0x14000d2a6  mov     [rsi+7Ch], eax
0x14000d2a9  movzx   eax, word ptr [rcx+8]
0x14000d2ad  mov     [rsi+84h], ax
0x14000d2b4  movzx   eax, word ptr [rcx+0Ah]
0x14000d2b8  mov     [rsi+80h], ax
0x14000d2bf  mov     eax, [rcx+0Ch]
0x14000d2c2  mov     [rsi+88h], eax
0x14000d2c8  mov     rax, cs:WdfFunctions_01015
0x14000d2cf  mov     r8, cs:off_1400220B0
0x14000d2d6  mov     rcx, cs:WdfDriverGlobals
0x14000d2dd  mov     rax, [rax+650h]
0x14000d2e4  call    _guard_dispatch_icall
0x14000d2e9  cmp     dword ptr [rbx+68h], 2
0x14000d2ed  jnz     short loc_14000D2FF
0x14000d2ef  cmp     dword ptr [rax+16Ch], 0
0x14000d2f6  jnz     short loc_14000D2FF
0x14000d2f8  or      dword ptr [rsi+8Ch], 20h
0x14000d2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d306  lea     rax, WPP_GLOBAL_Control
0x14000d30d  cmp     rcx, rax
0x14000d310  jz      short loc_14000D323
0x14000d312  mov     eax, [rcx+2Ch]
0x14000d315  test    al, 10h
0x14000d317  jz      short loc_14000D323
0x14000d319  cmp     byte ptr [rcx+29h], 4
0x14000d31d  jb      short loc_14000D323
0x14000d31f  mov     dl, 1
0x14000d321  jmp     short loc_14000D325
0x14000d323  xor     dl, dl
0x14000d325  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d32c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d333  setnz   r8b
0x14000d337  test    dl, dl
0x14000d339  jnz     short loc_14000D340
0x14000d33b  test    r8b, r8b
0x14000d33e  jz      short loc_14000D3A3
0x14000d340  movzx   r9d, word ptr [rsi+80h]
0x14000d348  mov     eax, [rsi+8Ch]
0x14000d34e  movzx   r10d, word ptr [rsi+84h]
0x14000d356  movzx   r11d, word ptr [rsi+82h]
0x14000d35e  shr     eax, 5
0x14000d361  and     eax, 1
0x14000d364  mov     [rsp+0A8h+var_30], eax
0x14000d368  mov     eax, [rsi+88h]
0x14000d36e  mov     [rsp+0A8h+var_38], eax
0x14000d372  mov     eax, [rbx+68h]
0x14000d375  mov     [rsp+0A8h+var_40], r9d
0x14000d37a  mov     r9, [rcx+40h]
0x14000d37e  mov     rcx, [rcx+18h]
0x14000d382  mov     [rsp+0A8h+var_48], eax
0x14000d386  mov     eax, [rsi+78h]
0x14000d389  mov     [rsp+0A8h+var_50], r10d
0x14000d38e  mov     [rsp+0A8h+var_58], eax
0x14000d392  mov     eax, [rsi+7Ch]
0x14000d395  mov     [rsp+0A8h+var_60], eax
0x14000d399  mov     [rsp+0A8h+var_68], r11d
0x14000d39e  call    WPP_RECORDER_AND_TRACE_SF_DLLDCODECIDDDl
0x14000d3a3  lea     rax, BthScoIndicationCallback
0x14000d3aa  mov     dword ptr [rsi+90h], 1
0x14000d3b4  mov     [rsi+98h], rax
0x14000d3bb  mov     [rsi+0A0h], rbp
0x14000d3c2  mov     byte ptr [rsi+0B8h], 0
0x14000d3c9  add     rsp, 88h
0x14000d3d0  pop     rdi
0x14000d3d1  pop     rsi
0x14000d3d2  pop     rbp
0x14000d3d3  pop     rbx
0x14000d3d4  retn
```

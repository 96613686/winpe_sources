# ScoBuildOpenEnchancedChannelBrb(_BRB *,ushort,WDFDEVICE__ *,void *,ScoConfigurationOptions const *,_SCOCONTEXT *)

- ea: `0x14000d3dc`
- end: `0x14000d5ff`
- name: `?ScoBuildOpenEnchancedChannelBrb@@YAXPEAU_BRB@@GPEAUWDFDEVICE__@@PEAXPEBUScoConfigurationOptions@@PEAU_SCOCONTEXT@@@Z`
- size: `547`
- prototype: `void __fastcall(struct _BRB *, unsigned __int16, struct WDFDEVICE__ *, void *, const struct ScoConfigurationOptions *, struct _SCOCONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14000df64`

## callees

- `0x14000d3dc`
- `0x140014e04`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoBuildOpenEnchancedChannelBrb(
        struct _BRB *a1,
        USHORT a2,
        struct WDFDEVICE__ *a3,
        void (__stdcall *a4)(PVOID Context, INDICATION_CODE Indication, PINDICATION_PARAMETERS Parameters),
        const struct ScoConfigurationOptions *a5,
        struct _SCOCONTEXT *a6)
{
  struct WDFDEVICE__ *v6; // r13
  USHORT v7; // r12
  ULONG *v9; // rsi
  _WORD *v10; // r14
  UCHAR *v11; // r15

  v6 = a3;
  v7 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = (UCHAR *)a6 + 59;
    v10 = (_WORD *)((char *)a6 + 54);
    v9 = (ULONG *)((char *)a6 + 44);
    WPP_RECORDER_AND_TRACE_SF_ddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    v9 = (ULONG *)((char *)a6 + 44);
    v10 = (_WORD *)((char *)a6 + 54);
    v11 = (UCHAR *)a6 + 59;
  }
  *((_QWORD *)&a1->BrbAclEnterActiveMode + 27) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, struct WDFDEVICE__ *))(WdfFunctions_01015 + 248))(
                                                   WdfDriverGlobals,
                                                   v6,
                                                   a3);
  a1->BrbL2caOpenChannel.Callback = a4;
  a1->BrbL2caOpenChannel.ConfigOut.LinkTO = v7;
  a1->BrbL2caRegisterServer.BtAddress = *((_QWORD *)a6 + 2);
  a1->BrbGetDeviceInterfaceString.DeviceInterfaceStringCbLength = *((_DWORD *)a5 + 1);
  a1->BrbL2caRegisterServer.IndicationFlags = *((_DWORD *)a5 + 1);
  *((_WORD *)&a1->BrbAclEnterActiveMode + 88) = *((_WORD *)a5 + 4);
  *((_WORD *)&a1->BrbAclEnterActiveMode + 86) = *((_WORD *)a5 + 5);
  *((_DWORD *)&a1->BrbAclEnterActiveMode + 45) = *((_DWORD *)a5 + 3);
  *((_WORD *)&a1->BrbAclEnterActiveMode + 69) = *((_WORD *)a6 + 21);
  a1->BrbL2caOpenChannel.ConfigOut.Mtu.Min = *((_WORD *)a6 + 21);
  a1->BrbL2caAclTransfer.TransferFlags = *((_DWORD *)a6 + 9);
  a1->BrbL2caPing.PingRequestData[11] = *((_BYTE *)a6 + 40);
  *(_DWORD *)((char *)&a1->BrbAclEnterActiveMode + 133) = *((_DWORD *)a6 + 9);
  a1->BrbL2caPing.PingRequestData[16] = *((_BYTE *)a6 + 40);
  a1->BrbScoGetChannelInfo.ChannelFlags = *((_DWORD *)a6 + 12);
  a1->BrbL2caPing.PingRequestData[35] = *((_BYTE *)a6 + 52);
  *(_DWORD *)((char *)&a1->BrbAclEnterActiveMode + 157) = *((_DWORD *)a6 + 12);
  a1->BrbL2caPing.PingRequestData[40] = *((_BYTE *)a6 + 52);
  a1->BrbScoOpenChannel.CallbackFlags = *v9;
  a1->BrbScoGetChannelInfo.RetransmissionEffort = *v9;
  *((_WORD *)&a1->BrbAclEnterActiveMode + 81) = *v10;
  *((_WORD *)&a1->BrbAclEnterActiveMode + 82) = *v10;
  a1->BrbL2caPing.PingResponseData[0] = *((_BYTE *)a6 + 56);
  a1->BrbL2caPing.PingResponseData[1] = *((_BYTE *)a6 + 56);
  a1->BrbL2caPing.PingResponseData[2] = *((_BYTE *)a6 + 57);
  a1->BrbL2caPing.PingResponseData[3] = *((_BYTE *)a6 + 57);
  a1->BrbL2caPing.PingResponseData[42] = *((_BYTE *)a6 + 58);
  a1->BrbL2caPing.PingResponseData[4] = *v11;
  a1->BrbL2caPing.PingResponseData[5] = *v11;
  *((_QWORD *)&a1->BrbAclEnterActiveMode + 24) = BthScoIndicationCallback;
  *((_DWORD *)&a1->BrbAclEnterActiveMode + 47) = 1;
  *((_QWORD *)&a1->BrbAclEnterActiveMode + 25) = v6;
  *((_BYTE *)&a1->BrbAclEnterActiveMode + 232) = 0;
}

```

## disassembly

```asm
0x14000d3dc  mov     [rsp+arg_18], r9
0x14000d3e1  push    rbx
0x14000d3e2  push    rbp
0x14000d3e3  push    rsi
0x14000d3e4  push    rdi
0x14000d3e5  push    r12
0x14000d3e7  push    r13
0x14000d3e9  push    r14
0x14000d3eb  push    r15
0x14000d3ed  sub     rsp, 78h
0x14000d3f1  mov     r13, r8
0x14000d3f4  movzx   r12d, dx
0x14000d3f8  mov     rdi, rcx
0x14000d3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d402  lea     rax, WPP_GLOBAL_Control
0x14000d409  cmp     rcx, rax
0x14000d40c  jz      short loc_14000D41F
0x14000d40e  mov     eax, [rcx+2Ch]
0x14000d411  test    al, 10h
0x14000d413  jz      short loc_14000D41F
0x14000d415  cmp     byte ptr [rcx+29h], 4
0x14000d419  jb      short loc_14000D41F
0x14000d41b  mov     dl, 1
0x14000d41d  jmp     short loc_14000D421
0x14000d41f  xor     dl, dl
0x14000d421  mov     rbx, [rsp+0B8h+arg_28]
0x14000d429  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d430  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d437  mov     rbp, [rsp+0B8h+arg_20]
0x14000d43f  setnz   r8b
0x14000d443  test    dl, dl
0x14000d445  jnz     short loc_14000D45A
0x14000d447  test    r8b, r8b
0x14000d44a  jnz     short loc_14000D45A
0x14000d44c  lea     rsi, [rbx+2Ch]
0x14000d450  lea     r14, [rbx+36h]
0x14000d454  lea     r15, [rbx+3Bh]
0x14000d458  jmp     short loc_14000D496
0x14000d45a  lea     r15, [rbx+3Bh]
0x14000d45e  movzx   eax, byte ptr [r15]
0x14000d462  lea     r14, [rbx+36h]
0x14000d466  movzx   r9d, word ptr [r14]
0x14000d46a  lea     rsi, [rbx+2Ch]
0x14000d46e  mov     [rsp+0B8h+var_58], eax
0x14000d472  mov     eax, [rsi]
0x14000d474  mov     [rsp+0B8h+var_60], r9d
0x14000d479  mov     r9, [rcx+40h]
0x14000d47d  mov     rcx, [rcx+18h]
0x14000d481  mov     [rsp+0B8h+var_68], eax
0x14000d485  mov     eax, [rbp+4]
0x14000d488  mov     [rsp+0B8h+var_70], eax
0x14000d48c  mov     [rsp+0B8h+var_78], r12d
0x14000d491  call    WPP_RECORDER_AND_TRACE_SF_ddddd
0x14000d496  mov     rax, cs:WdfFunctions_01015
0x14000d49d  mov     rdx, r13
0x14000d4a0  mov     rcx, cs:WdfDriverGlobals
0x14000d4a7  mov     rax, [rax+0F8h]
0x14000d4ae  call    _guard_dispatch_icall
0x14000d4b3  mov     [rdi+0D8h], rax
0x14000d4ba  mov     rax, [rsp+0B8h+arg_18]
0x14000d4c2  mov     [rdi+0E0h], rax
0x14000d4c9  mov     [rdi+0AEh], r12w
0x14000d4d1  mov     rax, [rbx+10h]
0x14000d4d5  mov     [rdi+70h], rax
0x14000d4d9  mov     eax, [rbp+4]
0x14000d4dc  mov     [rdi+78h], eax
0x14000d4df  mov     eax, [rbp+4]
0x14000d4e2  mov     [rdi+7Ch], eax
0x14000d4e5  movzx   eax, word ptr [rbp+8]
0x14000d4e9  mov     [rdi+0B0h], ax
0x14000d4f0  movzx   eax, word ptr [rbp+0Ah]
0x14000d4f4  mov     [rdi+0ACh], ax
0x14000d4fb  mov     eax, [rbp+0Ch]
0x14000d4fe  mov     [rdi+0B4h], eax
0x14000d504  movzx   eax, word ptr [rbx+2Ah]
0x14000d508  mov     [rdi+8Ah], ax
0x14000d50f  movzx   eax, word ptr [rbx+2Ah]
0x14000d513  mov     [rdi+8Ch], ax
0x14000d51a  mov     eax, [rbx+24h]
0x14000d51d  mov     [rdi+80h], eax
0x14000d523  mov     al, [rbx+28h]
0x14000d526  mov     [rdi+84h], al
0x14000d52c  mov     eax, [rbx+24h]
0x14000d52f  mov     [rdi+85h], eax
0x14000d535  mov     al, [rbx+28h]
0x14000d538  mov     [rdi+89h], al
0x14000d53e  mov     eax, [rbx+30h]
0x14000d541  mov     [rdi+98h], eax
0x14000d547  mov     al, [rbx+34h]
0x14000d54a  mov     [rdi+9Ch], al
0x14000d550  mov     eax, [rbx+30h]
0x14000d553  mov     [rdi+9Dh], eax
0x14000d559  mov     al, [rbx+34h]
0x14000d55c  mov     [rdi+0A1h], al
0x14000d562  mov     eax, [rsi]
0x14000d564  mov     [rdi+90h], eax
0x14000d56a  mov     eax, [rsi]
0x14000d56c  mov     [rdi+94h], eax
0x14000d572  movzx   eax, word ptr [r14]
0x14000d576  mov     [rdi+0A2h], ax
0x14000d57d  movzx   eax, word ptr [r14]
0x14000d581  mov     [rdi+0A4h], ax
0x14000d588  mov     al, [rbx+38h]
0x14000d58b  mov     [rdi+0A6h], al
0x14000d591  mov     al, [rbx+38h]
0x14000d594  mov     [rdi+0A7h], al
0x14000d59a  mov     al, [rbx+39h]
0x14000d59d  mov     [rdi+0A8h], al
0x14000d5a3  mov     al, [rbx+39h]
0x14000d5a6  mov     [rdi+0A9h], al
0x14000d5ac  mov     al, [rbx+3Ah]
0x14000d5af  mov     [rdi+0D0h], al
0x14000d5b5  mov     al, [r15]
0x14000d5b8  mov     [rdi+0AAh], al
0x14000d5be  mov     al, [r15]
0x14000d5c1  mov     [rdi+0ABh], al
0x14000d5c7  lea     rax, BthScoIndicationCallback
0x14000d5ce  mov     [rdi+0C0h], rax
0x14000d5d5  mov     dword ptr [rdi+0BCh], 1
0x14000d5df  mov     [rdi+0C8h], r13
0x14000d5e6  mov     byte ptr [rdi+0E8h], 0
0x14000d5ed  add     rsp, 78h
0x14000d5f1  pop     r15
0x14000d5f3  pop     r14
0x14000d5f5  pop     r13
0x14000d5f7  pop     r12
0x14000d5f9  pop     rdi
0x14000d5fa  pop     rsi
0x14000d5fb  pop     rbp
0x14000d5fc  pop     rbx
0x14000d5fd  retn
```

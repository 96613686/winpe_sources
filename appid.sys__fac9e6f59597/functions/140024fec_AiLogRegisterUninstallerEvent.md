# AiLogRegisterUninstallerEvent

- ea: `0x140024fec`
- end: `0x14002518b`
- name: `AiLogRegisterUninstallerEvent`
- size: `415`
- prototype: `char __fastcall(REGHANDLE RegHandle, __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140020db4`

## callees

- `0x140002070`
- `0x140006a20`
- `0x140024fec`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140025124`
- `ntoskrnl!EtwWrite` at `0x140025124`
- `ntoskrnl!EtwEventEnabled` at `0x14002502d`
- `ntoskrnl!EtwEventEnabled` at `0x14002502d`

## pseudocode

```c
char __fastcall AiLogRegisterUninstallerEvent(
        REGHANDLE RegHandle,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        char a7)
{
  NTSTATUS v10; // eax
  int v11; // ecx
  unsigned __int16 v12; // ax
  int v13; // edx
  int v14; // r8d
  __int16 v16; // [rsp+30h] [rbp-81h] BYREF
  __int16 v17; // [rsp+34h] [rbp-7Dh] BYREF
  __int16 v18; // [rsp+38h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-71h] BYREF
  __int64 v20; // [rsp+50h] [rbp-61h]
  int v21; // [rsp+58h] [rbp-59h]
  int v22; // [rsp+5Ch] [rbp-55h]
  __int16 *v23; // [rsp+60h] [rbp-51h]
  __int64 v24; // [rsp+68h] [rbp-49h]
  __int64 v25; // [rsp+70h] [rbp-41h]
  int v26; // [rsp+78h] [rbp-39h]
  int v27; // [rsp+7Ch] [rbp-35h]
  __int16 *v28; // [rsp+80h] [rbp-31h]
  __int64 v29; // [rsp+88h] [rbp-29h]
  __int64 v30; // [rsp+90h] [rbp-21h]
  int v31; // [rsp+98h] [rbp-19h]
  int v32; // [rsp+9Ch] [rbp-15h]
  __int64 v33; // [rsp+A0h] [rbp-11h]
  __int64 v34; // [rsp+A8h] [rbp-9h]
  __int64 v35; // [rsp+B0h] [rbp-1h]
  __int64 v36; // [rsp+B8h] [rbp+7h]
  char *v37; // [rsp+C0h] [rbp+Fh]
  __int64 v38; // [rsp+C8h] [rbp+17h]

  v16 = 0;
  v17 = 0;
  v18 = 0;
  LOBYTE(v10) = EtwEventEnabled(RegHandle, &AppIdRegisterUninstallerEvent);
  if ( (_BYTE)v10 )
  {
    v11 = *a3;
    v16 = *a3 >> 1;
    UserData.Ptr = (ULONGLONG)&v16;
    v20 = *((_QWORD *)a3 + 1);
    v21 = v11;
    v12 = *a4;
    v26 = *a4;
    v17 = v12 >> 1;
    v23 = &v17;
    v13 = *a5;
    v25 = *((_QWORD *)a4 + 1);
    v18 = (unsigned __int16)v13 >> 1;
    v28 = &v18;
    v30 = *((_QWORD *)a5 + 1);
    v33 = a6 + 16;
    v35 = a6 + 32;
    v31 = v13;
    v37 = &a7;
    *(_QWORD *)&UserData.Size = 2;
    v22 = 0;
    v24 = 2;
    v27 = 0;
    v29 = 2;
    v32 = 0;
    v34 = 16;
    v36 = 16;
    v38 = 4;
    v10 = EtwWrite(RegHandle, &AppIdRegisterUninstallerEvent, 0, 9u, &UserData);
    if ( v10 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      LOBYTE(v10) = WPP_SF_ZDD(WPP_GLOBAL_Control->AttachedDevice, 21, v14, (_DWORD)a3, a7, v10);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140024fec  mov     [rsp-8+arg_8], rbx
0x140024ff1  push    rbp
0x140024ff2  push    rsi
0x140024ff3  push    rdi
0x140024ff4  lea     rbp, [rsp-2Fh]
0x140024ff9  sub     rsp, 0E0h
0x140025000  mov     rax, cs:__security_cookie
0x140025007  xor     rax, rsp
0x14002500a  mov     [rbp+3Fh+var_20], rax
0x14002500e  xor     eax, eax
0x140025010  lea     rdx, AppIdRegisterUninstallerEvent; EventDescriptor
0x140025017  mov     [rsp+0F0h+var_C0], ax
0x14002501c  mov     rsi, r9
0x14002501f  mov     [rbp+3Fh+var_BC], ax
0x140025023  mov     rbx, r8
0x140025026  mov     [rbp+3Fh+var_B8], ax
0x14002502a  mov     rdi, rcx
0x14002502d  call    cs:__imp_EtwEventEnabled
0x140025034  nop     dword ptr [rax+rax+00h]
0x140025039  test    al, al
0x14002503b  jz      loc_14002516B
0x140025041  movzx   ecx, word ptr [rbx]
0x140025044  mov     r9d, 9; UserDataCount
0x14002504a  mov     r8, [rbp+3Fh+arg_28]
0x14002504e  movzx   eax, cx
0x140025051  shr     ax, 1
0x140025054  mov     [rsp+0F0h+var_C0], ax
0x140025059  lea     rax, [rsp+0F0h+var_C0]
0x14002505e  mov     [rbp+3Fh+var_B0.Ptr], rax
0x140025062  mov     rax, [rbx+8]
0x140025066  mov     [rbp+3Fh+var_A0], rax
0x14002506a  mov     [rbp+3Fh+var_98], ecx
0x14002506d  movzx   ecx, word ptr [rsi]
0x140025070  movzx   eax, cx
0x140025073  mov     [rbp+3Fh+var_78], ecx
0x140025076  mov     rcx, [rbp+3Fh+arg_20]
0x14002507a  shr     ax, 1
0x14002507d  mov     [rbp+3Fh+var_BC], ax
0x140025081  lea     rax, [rbp+3Fh+var_BC]
0x140025085  mov     [rbp+3Fh+var_90], rax
0x140025089  movzx   edx, word ptr [rcx]
0x14002508c  mov     rax, [rsi+8]
0x140025090  mov     [rbp+3Fh+var_80], rax
0x140025094  movzx   eax, dx
0x140025097  shr     ax, 1
0x14002509a  mov     [rbp+3Fh+var_B8], ax
0x14002509e  lea     rax, [rbp+3Fh+var_B8]
0x1400250a2  mov     [rbp+3Fh+var_70], rax
0x1400250a6  mov     rax, [rcx+8]
0x1400250aa  mov     rcx, rdi; RegHandle
0x1400250ad  mov     [rbp+3Fh+var_60], rax
0x1400250b1  lea     rax, [r8+10h]
0x1400250b5  mov     [rbp+3Fh+var_50], rax
0x1400250b9  lea     rax, [r8+20h]
0x1400250bd  mov     [rbp+3Fh+var_40], rax
0x1400250c1  xor     r8d, r8d; ActivityId
0x1400250c4  lea     rax, [rbp+3Fh+arg_30]
0x1400250c8  mov     [rbp+3Fh+var_58], edx
0x1400250cb  mov     [rbp+3Fh+var_30], rax
0x1400250cf  lea     rdx, AppIdRegisterUninstallerEvent; EventDescriptor
0x1400250d6  lea     rax, [rbp+3Fh+var_B0]
0x1400250da  mov     qword ptr [rbp+3Fh+var_B0.Size], 2
0x1400250e2  mov     [rsp+0F0h+UserData], rax; UserData
0x1400250e7  mov     [rbp+3Fh+var_94], 0
0x1400250ee  mov     [rbp+3Fh+var_88], 2
0x1400250f6  mov     [rbp+3Fh+var_74], 0
0x1400250fd  mov     [rbp+3Fh+var_68], 2
0x140025105  mov     [rbp+3Fh+var_54], 0
0x14002510c  mov     [rbp+3Fh+var_48], 10h
0x140025114  mov     [rbp+3Fh+var_38], 10h
0x14002511c  mov     [rbp+3Fh+var_28], 4
0x140025124  call    cs:__imp_EtwWrite
0x14002512b  nop     dword ptr [rax+rax+00h]
0x140025130  test    eax, eax
0x140025132  jns     short loc_14002516B
0x140025134  mov     rcx, cs:WPP_GLOBAL_Control
0x14002513b  lea     rdx, WPP_GLOBAL_Control
0x140025142  cmp     rcx, rdx
0x140025145  jz      short loc_14002516B
0x140025147  mov     edx, [rcx+2Ch]
0x14002514a  test    dl, 4
0x14002514d  jz      short loc_14002516B
0x14002514f  mov     rcx, [rcx+18h]
0x140025153  mov     edx, 15h
0x140025158  mov     [rsp+0F0h+var_C8], eax
0x14002515c  mov     r9, rbx
0x14002515f  mov     eax, [rbp+3Fh+arg_30]
0x140025162  mov     dword ptr [rsp+0F0h+UserData], eax
0x140025166  call    WPP_SF_ZDD
0x14002516b  mov     rcx, [rbp+3Fh+var_20]
0x14002516f  xor     rcx, rsp; StackCookie
0x140025172  call    __security_check_cookie
0x140025177  mov     rbx, [rsp+0F0h+arg_8]
0x14002517f  add     rsp, 0E0h
0x140025186  pop     rdi
0x140025187  pop     rsi
0x140025188  pop     rbp
0x140025189  retn
```

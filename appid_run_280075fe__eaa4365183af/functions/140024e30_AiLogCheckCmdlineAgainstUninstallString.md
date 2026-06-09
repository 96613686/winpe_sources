# AiLogCheckCmdlineAgainstUninstallString

- ea: `0x140024e30`
- end: `0x140024f81`
- name: `AiLogCheckCmdlineAgainstUninstallString`
- size: `337`
- prototype: `__int64 __usercall@<rax>(REGHANDLE RegHandle@<rcx>, char, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140022d58`

## callees

- `0x140002070`
- `0x140006a20`
- `0x140024e30`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140024f1c`
- `ntoskrnl!EtwWrite` at `0x140024f1c`
- `ntoskrnl!EtwEventEnabled` at `0x140024e73`
- `ntoskrnl!EtwEventEnabled` at `0x140024e73`

## pseudocode

```c
char __fastcall AiLogCheckCmdlineAgainstUninstallString(
        REGHANDLE RegHandle,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int8 a5,
        char a6)
{
  NTSTATUS v9; // eax
  unsigned __int16 v10; // ax
  int v11; // ecx
  int v12; // r8d
  __int16 v14; // [rsp+30h] [rbp-49h] BYREF
  __int16 v15; // [rsp+34h] [rbp-45h] BYREF
  int v16; // [rsp+38h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h]
  int v19; // [rsp+58h] [rbp-21h]
  int v20; // [rsp+5Ch] [rbp-1Dh]
  __int16 *v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h]
  __int64 v23; // [rsp+70h] [rbp-9h]
  int v24; // [rsp+78h] [rbp-1h]
  int v25; // [rsp+7Ch] [rbp+3h]
  int *v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+88h] [rbp+Fh]
  char *v28; // [rsp+90h] [rbp+17h]
  __int64 v29; // [rsp+98h] [rbp+1Fh]

  v14 = 0;
  v15 = 0;
  v16 = a5;
  LOBYTE(v9) = EtwEventEnabled(RegHandle, &AppIdCheckCmdlineAgainstUninstallStringEvent);
  if ( (_BYTE)v9 )
  {
    v10 = *a3;
    v19 = *a3;
    v11 = *a4;
    v14 = v10 >> 1;
    UserData.Ptr = (ULONGLONG)&v14;
    v18 = *((_QWORD *)a3 + 1);
    v15 = (unsigned __int16)v11 >> 1;
    v21 = &v15;
    v23 = *((_QWORD *)a4 + 1);
    v26 = &v16;
    v28 = &a6;
    v24 = v11;
    *(_QWORD *)&UserData.Size = 2;
    v20 = 0;
    v22 = 2;
    v25 = 0;
    v27 = 4;
    v29 = 4;
    v9 = EtwWrite(RegHandle, &AppIdCheckCmdlineAgainstUninstallStringEvent, 0, 6u, &UserData);
    if ( v9 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      LOBYTE(v9) = WPP_SF_ZDD(WPP_GLOBAL_Control->AttachedDevice, 22, v12, (_DWORD)a3, a6, v9);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140024e30  mov     [rsp-8+arg_8], rbx
0x140024e35  push    rbp
0x140024e36  push    rsi
0x140024e37  push    rdi
0x140024e38  lea     rbp, [rsp-37h]
0x140024e3d  sub     rsp, 0B0h
0x140024e44  mov     rax, cs:__security_cookie
0x140024e4b  xor     rax, rsp
0x140024e4e  mov     [rbp+47h+var_20], rax
0x140024e52  xor     eax, eax
0x140024e54  lea     rdx, AppIdCheckCmdlineAgainstUninstallStringEvent; EventDescriptor
0x140024e5b  mov     [rbp+47h+var_90], ax
0x140024e5f  mov     rsi, r9
0x140024e62  mov     [rbp+47h+var_8C], ax
0x140024e66  mov     rbx, r8
0x140024e69  movzx   eax, [rbp+47h+arg_20]
0x140024e6d  mov     rdi, rcx
0x140024e70  mov     [rbp+47h+var_88], eax
0x140024e73  call    cs:__imp_EtwEventEnabled
0x140024e7a  nop     dword ptr [rax+rax+00h]
0x140024e7f  test    al, al
0x140024e81  jz      loc_140024F61
0x140024e87  movzx   ecx, word ptr [rbx]
0x140024e8a  lea     rdx, AppIdCheckCmdlineAgainstUninstallStringEvent; EventDescriptor
0x140024e91  movzx   eax, cx
0x140024e94  mov     [rbp+47h+var_68], ecx
0x140024e97  movzx   ecx, word ptr [rsi]
0x140024e9a  xor     r8d, r8d; ActivityId
0x140024e9d  shr     ax, 1
0x140024ea0  mov     [rbp+47h+var_90], ax
0x140024ea4  lea     rax, [rbp+47h+var_90]
0x140024ea8  mov     [rbp+47h+var_80.Ptr], rax
0x140024eac  mov     rax, [rbx+8]
0x140024eb0  mov     [rbp+47h+var_70], rax
0x140024eb4  movzx   eax, cx
0x140024eb7  shr     ax, 1
0x140024eba  mov     [rbp+47h+var_8C], ax
0x140024ebe  lea     rax, [rbp+47h+var_8C]
0x140024ec2  mov     [rbp+47h+var_60], rax
0x140024ec6  mov     rax, [rsi+8]
0x140024eca  mov     esi, 4
0x140024ecf  mov     [rbp+47h+var_50], rax
0x140024ed3  lea     rax, [rbp+47h+var_88]
0x140024ed7  mov     [rbp+47h+var_40], rax
0x140024edb  lea     rax, [rbp+47h+arg_28]
0x140024edf  mov     [rbp+47h+var_30], rax
0x140024ee3  lea     rax, [rbp+47h+var_80]
0x140024ee7  mov     [rbp+47h+var_48], ecx
0x140024eea  lea     r9d, [rsi+2]; UserDataCount
0x140024eee  mov     rcx, rdi; RegHandle
0x140024ef1  mov     [rsp+0C0h+UserData], rax; UserData
0x140024ef6  mov     qword ptr [rbp+47h+var_80.Size], 2
0x140024efe  mov     [rbp+47h+var_64], 0
0x140024f05  mov     [rbp+47h+var_58], 2
0x140024f0d  mov     [rbp+47h+var_44], 0
0x140024f14  mov     [rbp+47h+var_38], rsi
0x140024f18  mov     [rbp+47h+var_28], rsi
0x140024f1c  call    cs:__imp_EtwWrite
0x140024f23  nop     dword ptr [rax+rax+00h]
0x140024f28  test    eax, eax
0x140024f2a  jns     short loc_140024F61
0x140024f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f33  lea     rdx, WPP_GLOBAL_Control
0x140024f3a  cmp     rcx, rdx
0x140024f3d  jz      short loc_140024F61
0x140024f3f  mov     edx, [rcx+2Ch]
0x140024f42  test    sil, dl
0x140024f45  jz      short loc_140024F61
0x140024f47  mov     rcx, [rcx+18h]
0x140024f4b  lea     edx, [rsi+12h]
0x140024f4e  mov     [rsp+0C0h+var_98], eax
0x140024f52  mov     r9, rbx
0x140024f55  mov     eax, [rbp+47h+arg_28]
0x140024f58  mov     dword ptr [rsp+0C0h+UserData], eax
0x140024f5c  call    WPP_SF_ZDD
0x140024f61  mov     rcx, [rbp+47h+var_20]
0x140024f65  xor     rcx, rsp; StackCookie
0x140024f68  call    __security_check_cookie
0x140024f6d  mov     rbx, [rsp+0C0h+arg_8]
0x140024f75  add     rsp, 0B0h
0x140024f7c  pop     rdi
0x140024f7d  pop     rsi
0x140024f7e  pop     rbp
0x140024f7f  retn
```

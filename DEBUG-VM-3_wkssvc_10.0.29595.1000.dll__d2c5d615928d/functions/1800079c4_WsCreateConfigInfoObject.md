# WsCreateConfigInfoObject

- ea: `0x1800079c4`
- end: `0x180007b25`
- name: `WsCreateConfigInfoObject`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006c3c`

## callees

- `0x180007604`
- `0x1800079c4`
- `0x180007f60`

## import_xrefs

- `ntdll!NtClose` at `0x180007aff`
- `ntdll!NtClose` at `0x180007aff`
- `ntdll!NtOpenProcessToken` at `0x180007ac2`
- `ntdll!NtOpenProcessToken` at `0x180007ac2`
- `ntdll!RtlNewSecurityObject` at `0x180007af3`
- `ntdll!RtlNewSecurityObject` at `0x180007af3`

## pseudocode

```c
__int64 WsCreateConfigInfoObject()
{
  void *v0; // r8
  int SecurityDescriptor; // ebx
  __int16 v3; // [rsp+30h] [rbp-29h] BYREF
  char v4; // [rsp+32h] [rbp-27h]
  int v5; // [rsp+34h] [rbp-25h]
  __int64 v6; // [rsp+38h] [rbp-21h]
  __int16 v7; // [rsp+40h] [rbp-19h]
  char v8; // [rsp+42h] [rbp-17h]
  int v9; // [rsp+44h] [rbp-15h]
  __int64 v10; // [rsp+48h] [rbp-11h]
  __int16 v11; // [rsp+50h] [rbp-9h]
  char v12; // [rsp+52h] [rbp-7h]
  int v13; // [rsp+54h] [rbp-5h]
  __int64 v14; // [rsp+58h] [rbp-1h]
  __int16 v15; // [rsp+60h] [rbp+7h]
  char v16; // [rsp+62h] [rbp+9h]
  int v17; // [rsp+64h] [rbp+Bh]
  __int64 v18; // [rsp+68h] [rbp+Fh]
  __int16 v19; // [rsp+70h] [rbp+17h]
  char v20; // [rsp+72h] [rbp+19h]
  int v21; // [rsp+74h] [rbp+1Bh]
  __int64 v22; // [rsp+78h] [rbp+1Fh]
  __int16 v23; // [rsp+80h] [rbp+27h]
  char v24; // [rsp+82h] [rbp+29h]
  int v25; // [rsp+84h] [rbp+2Bh]
  __int64 v26; // [rsp+88h] [rbp+2Fh]
  __int16 v27; // [rsp+90h] [rbp+37h]
  char v28; // [rsp+92h] [rbp+39h]
  int v29; // [rsp+94h] [rbp+3Bh]
  __int64 v30; // [rsp+98h] [rbp+3Fh]
  __int16 v31; // [rsp+A0h] [rbp+47h]
  char v32; // [rsp+A2h] [rbp+49h]
  int v33; // [rsp+A4h] [rbp+4Bh]
  __int64 v34; // [rsp+A8h] [rbp+4Fh]
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+C0h] [rbp+67h] BYREF
  void *TokenHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  v3 = 0;
  v4 = 0;
  v7 = 0;
  v8 = 0;
  v5 = 7;
  v6 = WsLmsvcsGlobalData + 16;
  v13 = 7;
  v10 = WsLmsvcsGlobalData + 80;
  v14 = WsLmsvcsGlobalData + 112;
  v18 = WsLmsvcsGlobalData + 120;
  v22 = WsLmsvcsGlobalData + 128;
  v26 = WsLmsvcsGlobalData + 88;
  v30 = WsLmsvcsGlobalData + 8;
  v0 = *(void **)(WsLmsvcsGlobalData + 48);
  v17 = 7;
  v21 = 7;
  v34 = WsLmsvcsGlobalData + 72;
  v29 = 1;
  v33 = 1;
  v9 = 0x10000000;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 3;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  CreatorDescriptor = 0;
  TokenHandle = 0;
  SecurityDescriptor = NetpCreateSecurityDescriptor((__int64)&v3, 8u, v0, v0, (struct _ACL **)&CreatorDescriptor);
  if ( SecurityDescriptor >= 0 )
  {
    SecurityDescriptor = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlNewSecurityObject(
                             0,
                             CreatorDescriptor,
                             &ConfigurationInfoSd,
                             0,
                             TokenHandle,
                             &WsConfigInfoMapping);
      NtClose(TokenHandle);
    }
    NetpMemoryFree(CreatorDescriptor);
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x1800079c4  mov     [rsp-8+arg_10], rbx
0x1800079c9  mov     [rsp-8+arg_18], rdi
0x1800079ce  push    rbp
0x1800079cf  lea     rbp, [rsp-57h]
0x1800079d4  sub     rsp, 0B0h
0x1800079db  mov     r8, cs:WsLmsvcsGlobalData
0x1800079e2  xor     edi, edi
0x1800079e4  mov     [rbp+57h+var_80], di
0x1800079e8  mov     [rbp+57h+var_7E], dil
0x1800079ec  mov     [rbp+57h+var_70], di
0x1800079f0  lea     ecx, [rdi+7]
0x1800079f3  mov     [rbp+57h+var_6E], dil
0x1800079f7  lea     rax, [r8+10h]
0x1800079fb  mov     [rbp+57h+var_7C], ecx
0x1800079fe  mov     [rbp+57h+var_78], rax
0x180007a02  lea     edx, [rdi+8]
0x180007a05  lea     rax, [r8+50h]
0x180007a09  mov     [rbp+57h+var_5C], ecx
0x180007a0c  mov     [rbp+57h+var_68], rax
0x180007a10  lea     rax, [r8+70h]
0x180007a14  mov     [rbp+57h+var_58], rax
0x180007a18  lea     rax, [r8+78h]
0x180007a1c  mov     [rbp+57h+var_48], rax
0x180007a20  lea     rax, [r8+80h]
0x180007a27  mov     [rbp+57h+var_38], rax
0x180007a2b  lea     rax, [r8+58h]
0x180007a2f  mov     [rbp+57h+var_28], rax
0x180007a33  lea     rax, [r8+8]
0x180007a37  mov     [rbp+57h+var_18], rax
0x180007a3b  lea     rax, [r8+48h]
0x180007a3f  mov     r8, [r8+30h]
0x180007a43  mov     [rbp+57h+var_4C], ecx
0x180007a46  mov     r9, r8
0x180007a49  mov     [rbp+57h+var_3C], ecx
0x180007a4c  lea     ecx, [rdi+1]
0x180007a4f  mov     [rbp+57h+var_8], rax
0x180007a53  lea     rax, [rbp+57h+CreatorDescriptor]
0x180007a57  mov     [rbp+57h+var_1C], ecx
0x180007a5a  mov     [rbp+57h+var_C], ecx
0x180007a5d  lea     rcx, [rbp+57h+var_80]
0x180007a61  mov     [rsp+0B0h+Token], rax
0x180007a66  mov     [rbp+57h+var_6C], 10000000h
0x180007a6d  mov     [rbp+57h+var_60], di
0x180007a71  mov     [rbp+57h+var_5E], dil
0x180007a75  mov     [rbp+57h+var_50], di
0x180007a79  mov     [rbp+57h+var_4E], dil
0x180007a7d  mov     [rbp+57h+var_40], di
0x180007a81  mov     [rbp+57h+var_3E], dil
0x180007a85  mov     [rbp+57h+var_30], di
0x180007a89  mov     [rbp+57h+var_2E], dil
0x180007a8d  mov     [rbp+57h+var_2C], 3
0x180007a94  mov     [rbp+57h+var_20], di
0x180007a98  mov     [rbp+57h+var_1E], dil
0x180007a9c  mov     [rbp+57h+var_10], di
0x180007aa0  mov     [rbp+57h+var_E], dil
0x180007aa4  mov     [rbp+57h+CreatorDescriptor], rdi
0x180007aa8  mov     [rbp+57h+TokenHandle], rdi
0x180007aac  call    NetpCreateSecurityDescriptor
0x180007ab1  mov     ebx, eax
0x180007ab3  test    eax, eax
0x180007ab5  js      short loc_180007B0E
0x180007ab7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180007abb  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180007abf  lea     edx, [rdi+8]; DesiredAccess
0x180007ac2  call    cs:__imp_NtOpenProcessToken
0x180007ac8  mov     ebx, eax
0x180007aca  test    eax, eax
0x180007acc  js      short loc_180007B05
0x180007ace  mov     rdx, [rbp+57h+CreatorDescriptor]; CreatorDescriptor
0x180007ad2  lea     rax, WsConfigInfoMapping
0x180007ad9  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x180007ade  lea     r8, ConfigurationInfoSd; NewDescriptor
0x180007ae5  mov     rax, [rbp+57h+TokenHandle]
0x180007ae9  xor     r9d, r9d; IsDirectoryObject
0x180007aec  xor     ecx, ecx; ParentDescriptor
0x180007aee  mov     [rsp+0B0h+Token], rax; Token
0x180007af3  call    cs:__imp_RtlNewSecurityObject
0x180007af9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180007afd  mov     ebx, eax
0x180007aff  call    cs:__imp_NtClose
0x180007b05  mov     rcx, [rbp+57h+CreatorDescriptor]
0x180007b09  call    NetpMemoryFree
0x180007b0e  lea     r11, [rsp+0B0h+var_s0]
0x180007b16  mov     eax, ebx
0x180007b18  mov     rbx, [r11+20h]
0x180007b1c  mov     rdi, [r11+28h]
0x180007b20  mov     rsp, r11
0x180007b23  pop     rbp
0x180007b24  retn
```

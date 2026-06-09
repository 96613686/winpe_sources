# BamUserSettingsCheckOrigin

- ea: `0x140015878`
- end: `0x140015a60`
- name: `BamUserSettingsCheckOrigin`
- size: `488`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, bool *, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140015608`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x140015878`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140015a2a`
- `ntoskrnl!ZwClose` at `0x140015a2a`
- `ntoskrnl!ZwCreateFile` at `0x140015922`
- `ntoskrnl!ZwCreateFile` at `0x140015922`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14001594f`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14001594f`

## pseudocode

```c
__int64 __fastcall BamUserSettingsCheckOrigin(struct _UNICODE_STRING *a1, bool *a2, _BYTE *a3)
{
  bool v6; // r14
  char v7; // di
  NTSTATUS v8; // ebx
  char v9; // di
  bool v11; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+61h] [rbp-9Fh] BYREF
  NTSTATUS v13; // [rsp+64h] [rbp-9Ch] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 FsInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  char v18[32]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v19; // [rsp+E0h] [rbp-20h]
  __int64 v20; // [rsp+E8h] [rbp-18h]
  wchar_t *Buffer; // [rsp+F0h] [rbp-10h]
  _DWORD v22[2]; // [rsp+F8h] [rbp-8h] BYREF
  NTSTATUS *v23; // [rsp+100h] [rbp+0h]
  __int64 v24; // [rsp+108h] [rbp+8h]
  bool *v25; // [rsp+110h] [rbp+10h]
  __int64 v26; // [rsp+118h] [rbp+18h]
  char *v27; // [rsp+120h] [rbp+20h]
  __int64 v28; // [rsp+128h] [rbp+28h]

  ObjectAttributes.ObjectName = a1;
  FsInformation = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v6 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v7 = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x20u, 0, 0);
  if ( v8 >= 0 )
  {
    v8 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
    if ( (v8 & 0xC0000000) != 0xC0000000 )
    {
      v9 = BYTE4(FsInformation);
      v8 = 0;
      *a2 = (FsInformation & 0x1000000000LL) != 0;
      v7 = v9 & 1;
      *a3 = v7;
      v6 = *a2;
    }
  }
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v20 = 2;
    v19 = v22;
    Buffer = a1->Buffer;
    v22[0] = a1->Length;
    v23 = &v13;
    v25 = &v11;
    v27 = &v12;
    v22[1] = 0;
    v13 = v8;
    v24 = 4;
    v11 = v6;
    v26 = 1;
    v12 = v7;
    v28 = 1;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, byte_140005855, 0, 0, 7, v18);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140015878  mov     [rsp-8+arg_18], rbx
0x14001587d  push    rbp
0x14001587e  push    rsi
0x14001587f  push    rdi
0x140015880  push    r12
0x140015882  push    r13
0x140015884  push    r14
0x140015886  push    r15
0x140015888  lea     rbp, [rsp-40h]
0x14001588d  sub     rsp, 140h
0x140015894  mov     rax, cs:__security_cookie
0x14001589b  xor     rax, rsp
0x14001589e  mov     [rbp+70h+var_40], rax
0x1400158a2  xor     r13d, r13d
0x1400158a5  mov     [rbp+70h+ObjectAttributes.ObjectName], rcx
0x1400158a9  mov     [rsp+170h+EaLength], r13d; EaLength
0x1400158ae  lea     r9, [rsp+170h+IoStatusBlock]; IoStatusBlock
0x1400158b3  mov     [rsp+170h+EaBuffer], r13; EaBuffer
0x1400158b8  xorps   xmm0, xmm0
0x1400158bb  mov     [rsp+170h+CreateOptions], 20h ; ' '; CreateOptions
0x1400158c3  mov     r12, r8
0x1400158c6  mov     [rsp+170h+CreateDisposition], 1; CreateDisposition
0x1400158ce  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x1400158d2  mov     [rsp+170h+ShareAccess], 7; ShareAccess
0x1400158da  mov     rsi, rdx
0x1400158dd  mov     r15, rcx
0x1400158e0  mov     [rsp+170h+FileAttributes], r13d; FileAttributes
0x1400158e5  mov     edx, 100080h; DesiredAccess
0x1400158ea  mov     [rsp+170h+AllocationSize], r13; AllocationSize
0x1400158ef  lea     rcx, [rsp+170h+FileHandle]; FileHandle
0x1400158f4  mov     [rsp+170h+FsInformation], r13
0x1400158f9  movups  xmmword ptr [rsp+170h+IoStatusBlock], xmm0
0x1400158fe  mov     qword ptr [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x140015906  mov     r14b, r13b
0x140015909  mov     qword ptr [rbp+70h+ObjectAttributes.Attributes], 240h
0x140015911  mov     dil, r13b
0x140015914  mov     [rsp+170h+FileHandle], r13
0x140015919  mov     [rbp+70h+ObjectAttributes.RootDirectory], r13
0x14001591d  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015922  call    cs:__imp_ZwCreateFile
0x140015929  nop     dword ptr [rax+rax+00h]
0x14001592e  mov     ebx, eax
0x140015930  test    eax, eax
0x140015932  js      short loc_140015983
0x140015934  mov     rcx, [rsp+170h+FileHandle]; FileHandle
0x140015939  lea     r9d, [r13+8]; Length
0x14001593d  lea     r8, [rsp+170h+FsInformation]; FsInformation
0x140015942  mov     dword ptr [rsp+170h+AllocationSize], 4; FsInformationClass
0x14001594a  lea     rdx, [rsp+170h+IoStatusBlock]; IoStatusBlock
0x14001594f  call    cs:__imp_ZwQueryVolumeInformationFile
0x140015956  nop     dword ptr [rax+rax+00h]
0x14001595b  mov     ecx, 0C0000000h
0x140015960  mov     ebx, eax
0x140015962  and     eax, ecx
0x140015964  cmp     eax, ecx
0x140015966  jz      short loc_140015983
0x140015968  mov     edi, dword ptr [rsp+170h+FsInformation+4]
0x14001596c  mov     ebx, r13d
0x14001596f  mov     eax, edi
0x140015971  shr     eax, 4
0x140015974  and     al, 1
0x140015976  mov     [rsi], al
0x140015978  and     dil, 1
0x14001597c  mov     [r12], dil
0x140015980  mov     r14b, [rsi]
0x140015983  mov     eax, cs:dword_140007010
0x140015989  cmp     eax, 5
0x14001598c  jbe     loc_140015A20
0x140015992  lea     rax, [rbp+70h+var_78]
0x140015996  mov     [rbp+70h+var_88], 2
0x14001599e  mov     [rbp+70h+var_90], rax
0x1400159a2  lea     rdx, byte_140005855
0x1400159a9  mov     rax, [r15+8]
0x1400159ad  lea     rcx, dword_140007010
0x1400159b4  mov     [rbp+70h+var_80], rax
0x1400159b8  xor     r9d, r9d
0x1400159bb  movzx   eax, word ptr [r15]
0x1400159bf  xor     r8d, r8d
0x1400159c2  mov     [rbp+70h+var_78], eax
0x1400159c5  lea     rax, [rsp+170h+var_10C]
0x1400159ca  mov     [rbp+70h+var_70], rax
0x1400159ce  lea     rax, [rsp+170h+var_110]
0x1400159d3  mov     [rbp+70h+var_60], rax
0x1400159d7  lea     rax, [rsp+170h+var_10F]
0x1400159dc  mov     [rbp+70h+var_50], rax
0x1400159e0  lea     rax, [rbp+70h+var_B0]
0x1400159e4  mov     qword ptr [rsp+170h+FileAttributes], rax
0x1400159e9  mov     dword ptr [rsp+170h+AllocationSize], 7
0x1400159f1  mov     [rbp+70h+var_74], r13d
0x1400159f5  mov     [rsp+170h+var_10C], ebx
0x1400159f9  mov     [rbp+70h+var_68], 4
0x140015a01  mov     [rsp+170h+var_110], r14b
0x140015a06  mov     [rbp+70h+var_58], 1
0x140015a0e  mov     [rsp+170h+var_10F], dil
0x140015a13  mov     [rbp+70h+var_48], 1
0x140015a1b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140015a20  mov     rcx, [rsp+170h+FileHandle]; Handle
0x140015a25  test    rcx, rcx
0x140015a28  jz      short loc_140015A36
0x140015a2a  call    cs:__imp_ZwClose
0x140015a31  nop     dword ptr [rax+rax+00h]
0x140015a36  mov     eax, ebx
0x140015a38  mov     rcx, [rbp+70h+var_40]
0x140015a3c  xor     rcx, rsp; StackCookie
0x140015a3f  call    __security_check_cookie
0x140015a44  mov     rbx, [rsp+170h+arg_18]
0x140015a4c  add     rsp, 140h
0x140015a53  pop     r15
0x140015a55  pop     r14
0x140015a57  pop     r13
0x140015a59  pop     r12
0x140015a5b  pop     rdi
0x140015a5c  pop     rsi
0x140015a5d  pop     rbp
0x140015a5e  retn
```

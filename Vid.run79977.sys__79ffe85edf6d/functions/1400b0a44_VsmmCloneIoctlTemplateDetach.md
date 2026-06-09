# VsmmCloneIoctlTemplateDetach

- ea: `0x1400b0a44`
- end: `0x1400b0c76`
- name: `VsmmCloneIoctlTemplateDetach`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14003782c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140007ac8`
- `0x14000a010`
- `0x140021c60`
- `0x1400347a4`
- `0x140034b64`
- `0x1400386a0`
- `0x1400769d8`
- `0x1400b0a44`
- `0x1400b1608`
- `0x1400fd510`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400b0aeb`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400b0aeb`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400b0b41`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400b0b41`

## string_xrefs

- `0x1400b0b0a`: `VsmmCloneIoctlTemplateDetach`
- `0x1400b0b89`: `VsmmCloneIoctlTemplateDetach`
- `0x1400b0bd5`: `VsmmCloneIoctlTemplateDetach`

## pseudocode

```c
__int64 __fastcall VsmmCloneIoctlTemplateDetach(__int64 a1, __int64 a2, _OWORD *a3)
{
  NTSTATUS ProcessNotifyRoutine; // ebx
  __int64 v7; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r14
  _DWORD *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rbx
  int v14; // [rsp+30h] [rbp-69h] BYREF
  NTSTATUS v15; // [rsp+34h] [rbp-65h] BYREF
  char v16[32]; // [rsp+40h] [rbp-59h] BYREF
  char v17[16]; // [rsp+60h] [rbp-39h] BYREF
  char v18[16]; // [rsp+70h] [rbp-29h] BYREF
  int *v19; // [rsp+80h] [rbp-19h]
  __int64 v20; // [rsp+88h] [rbp-11h]
  NTSTATUS *v21; // [rsp+90h] [rbp-9h]
  __int64 v22; // [rsp+98h] [rbp-1h]
  __int64 v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]

  if ( (int)VidSidServiceCheck() >= 0 )
  {
    v7 = VidPartitionTableLookupAndReference(a1, a2, 0);
    v8 = (_QWORD *)v7;
    if ( !v7 )
    {
      ProcessNotifyRoutine = -1070137335;
      goto LABEL_15;
    }
    v9 = v7 + 3736;
    VidObjectLockAcquireExclusive(v7 + 3736);
    v10 = (_DWORD *)v8[1300];
    if ( !v10 || *v10 != 1 )
    {
      ProcessNotifyRoutine = -1073741811;
      VidTraceErrorInternal0("VsmmCloneIoctlTemplateDetach", "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c", 481);
LABEL_14:
      VidObjectLockRelease(v9);
      VidDereferencePartition(v8);
      if ( ProcessNotifyRoutine >= 0 )
        return (unsigned int)ProcessNotifyRoutine;
      goto LABEL_15;
    }
    v11 = a1 + 680;
    VidObjectLockAcquireExclusive(v11);
    if ( !*(_BYTE *)(v11 + 64) )
    {
      ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(VsmmClonepTableProcessNotifyRoutine, 0);
      if ( ProcessNotifyRoutine < 0 )
      {
        VidTraceErrorInternal0("VsmmCloneIoctlTemplateDetach", "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c", 495);
LABEL_12:
        VidObjectLockRelease(v11);
        goto LABEL_14;
      }
      *(_BYTE *)(v11 + 64) = 1;
    }
    *a3 = *(_OWORD *)(v8[1300] + 4LL);
    *(_DWORD *)v8[1300] = 2;
    v12 = v8[1300];
    *(_QWORD *)(v12 + 24) = PsGetCurrentProcessId();
    VsmmClonepTableInsertByOwningProcessId(v11, v8[1300]);
    ProcessNotifyRoutine = 0;
    v8[1300] = 0;
    goto LABEL_12;
  }
  ProcessNotifyRoutine = -1073741727;
LABEL_15:
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v17, "VsmmCloneIoctlTemplateDetach");
    tlgCreate1Sz_char(v18, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    v14 = 538;
    v19 = &v14;
    v20 = 4;
    v21 = &v15;
    v15 = ProcessNotifyRoutine;
    v22 = 4;
    v23 = a2;
    v24 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004EE2C, 0, 0, 7, v16);
  }
  return (unsigned int)ProcessNotifyRoutine;
}

```

## disassembly

```asm
0x1400b0a44  push    rbp
0x1400b0a46  push    rbx
0x1400b0a47  push    rsi
0x1400b0a48  push    rdi
0x1400b0a49  push    r12
0x1400b0a4b  push    r14
0x1400b0a4d  push    r15
0x1400b0a4f  lea     rbp, [rsp-27h]
0x1400b0a54  sub     rsp, 0C0h
0x1400b0a5b  mov     rax, cs:__security_cookie
0x1400b0a62  xor     rax, rsp
0x1400b0a65  mov     [rbp+57h+var_40], rax
0x1400b0a69  mov     r12, r8
0x1400b0a6c  mov     r15, rdx
0x1400b0a6f  mov     rsi, rcx
0x1400b0a72  call    VidSidServiceCheck
0x1400b0a77  test    eax, eax
0x1400b0a79  jns     short loc_1400B0A85
0x1400b0a7b  mov     ebx, 0C0000061h
0x1400b0a80  jmp     loc_1400B0BAD
0x1400b0a85  xor     r8d, r8d
0x1400b0a88  mov     rdx, r15
0x1400b0a8b  mov     rcx, rsi
0x1400b0a8e  call    VidPartitionTableLookupAndReference
0x1400b0a93  mov     rdi, rax
0x1400b0a96  test    rax, rax
0x1400b0a99  jnz     short loc_1400B0AA5
0x1400b0a9b  mov     ebx, 0C0370009h
0x1400b0aa0  jmp     loc_1400B0BAD
0x1400b0aa5  lea     r14, [rax+0E98h]
0x1400b0aac  mov     rcx, r14
0x1400b0aaf  call    VidObjectLockAcquireExclusive
0x1400b0ab4  mov     rax, [rdi+28A0h]
0x1400b0abb  test    rax, rax
0x1400b0abe  jz      loc_1400B0B77
0x1400b0ac4  cmp     dword ptr [rax], 1
0x1400b0ac7  jnz     loc_1400B0B77
0x1400b0acd  add     rsi, 2A8h
0x1400b0ad4  mov     rcx, rsi
0x1400b0ad7  call    VidObjectLockAcquireExclusive
0x1400b0adc  cmp     byte ptr [rsi+40h], 0
0x1400b0ae0  jnz     short loc_1400B0B1C
0x1400b0ae2  xor     edx, edx; Remove
0x1400b0ae4  lea     rcx, VsmmClonepTableProcessNotifyRoutine; NotifyRoutine
0x1400b0aeb  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x1400b0af2  nop     dword ptr [rax+rax+00h]
0x1400b0af7  mov     ebx, eax
0x1400b0af9  test    eax, eax
0x1400b0afb  jns     short loc_1400B0B18
0x1400b0afd  mov     r8d, 1EFh
0x1400b0b03  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0b0a  lea     rcx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400b0b11  call    VidTraceErrorInternal0
0x1400b0b16  jmp     short loc_1400B0B6D
0x1400b0b18  mov     byte ptr [rsi+40h], 1
0x1400b0b1c  mov     rax, [rdi+28A0h]
0x1400b0b23  movups  xmm0, xmmword ptr [rax+4]
0x1400b0b27  movdqu  xmmword ptr [r12], xmm0
0x1400b0b2d  mov     rax, [rdi+28A0h]
0x1400b0b34  mov     dword ptr [rax], 2
0x1400b0b3a  mov     rbx, [rdi+28A0h]
0x1400b0b41  call    cs:__imp_PsGetCurrentProcessId
0x1400b0b48  nop     dword ptr [rax+rax+00h]
0x1400b0b4d  mov     [rbx+18h], rax
0x1400b0b51  mov     rcx, rsi
0x1400b0b54  mov     rdx, [rdi+28A0h]
0x1400b0b5b  call    VsmmClonepTableInsertByOwningProcessId
0x1400b0b60  xor     ebx, ebx
0x1400b0b62  mov     qword ptr [rdi+28A0h], 0
0x1400b0b6d  mov     rcx, rsi
0x1400b0b70  call    VidObjectLockRelease
0x1400b0b75  jmp     short loc_1400B0B95
0x1400b0b77  mov     ebx, 0C000000Dh
0x1400b0b7c  mov     r8d, 1E1h
0x1400b0b82  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0b89  lea     rcx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400b0b90  call    VidTraceErrorInternal0
0x1400b0b95  mov     rcx, r14
0x1400b0b98  call    VidObjectLockRelease
0x1400b0b9d  mov     rcx, rdi; P
0x1400b0ba0  call    VidDereferencePartition
0x1400b0ba5  test    ebx, ebx
0x1400b0ba7  jns     loc_1400B0C55
0x1400b0bad  mov     eax, cs:dword_140065110
0x1400b0bb3  cmp     eax, 2
0x1400b0bb6  jbe     loc_1400B0C55
0x1400b0bbc  mov     edx, 100h
0x1400b0bc1  lea     rcx, dword_140065110
0x1400b0bc8  call    _tlgKeywordOn
0x1400b0bcd  test    al, al
0x1400b0bcf  jz      loc_1400B0C55
0x1400b0bd5  lea     rdx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400b0bdc  lea     rcx, [rbp+57h+var_90]
0x1400b0be0  call    _tlgCreate1Sz_char
0x1400b0be5  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0bec  lea     rcx, [rbp+57h+var_80]
0x1400b0bf0  call    _tlgCreate1Sz_char
0x1400b0bf5  lea     rax, [rbp+57h+var_C0]
0x1400b0bf9  mov     [rbp+57h+var_C0], 21Ah
0x1400b0c00  mov     [rbp+57h+var_70], rax
0x1400b0c04  lea     rdx, unk_14004EE2C
0x1400b0c0b  lea     rax, [rbp+57h+var_BC]
0x1400b0c0f  mov     [rbp+57h+var_68], 4
0x1400b0c17  mov     [rbp+57h+var_60], rax
0x1400b0c1b  lea     rcx, dword_140065110
0x1400b0c22  lea     rax, [rbp+57h+var_B0]
0x1400b0c26  mov     [rbp+57h+var_BC], ebx
0x1400b0c29  mov     [rsp+0F0h+var_C8], rax
0x1400b0c2e  xor     r9d, r9d
0x1400b0c31  xor     r8d, r8d
0x1400b0c34  mov     [rsp+0F0h+var_D0], 7
0x1400b0c3c  mov     [rbp+57h+var_58], 4
0x1400b0c44  mov     [rbp+57h+var_50], r15
0x1400b0c48  mov     [rbp+57h+var_48], 10h
0x1400b0c50  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b0c55  mov     eax, ebx
0x1400b0c57  mov     rcx, [rbp+57h+var_40]
0x1400b0c5b  xor     rcx, rsp; StackCookie
0x1400b0c5e  call    __security_check_cookie
0x1400b0c63  add     rsp, 0C0h
0x1400b0c6a  pop     r15
0x1400b0c6c  pop     r14
0x1400b0c6e  pop     r12
0x1400b0c70  pop     rdi
0x1400b0c71  pop     rsi
0x1400b0c72  pop     rbx
0x1400b0c73  pop     rbp
0x1400b0c74  retn
```

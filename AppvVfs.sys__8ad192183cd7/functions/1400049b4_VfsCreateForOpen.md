# VfsCreateForOpen

- ea: `0x1400049b4`
- end: `0x140004d13`
- name: `VfsCreateForOpen`
- size: `863`
- prototype: `int __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140003c00`

## callees

- `0x140002b4c`
- `0x14000437c`
- `0x1400049b4`
- `0x14000e438`
- `0x14000eb14`

## import_xrefs

- `ntoskrnl!IoReplaceFileObjectName` at `0x140004cd8`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140004cd8`

## pseudocode

```c
int __fastcall VfsCreateForOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _DWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int v7; // ebp
  int v8; // edx
  bool v9; // si
  int v10; // eax
  int result; // eax
  int v12; // edx
  _QWORD *v13; // r8
  void *v14; // rcx
  int v15; // edx
  struct _FLT_INSTANCE *v16; // rsi
  __int64 v17; // [rsp+C0h] [rbp+8h] BYREF

  Iopb = CallbackData->Iopb;
  LOBYTE(v17) = 0;
  v7 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  *a3 = 0;
  while ( 1 )
  {
    v8 = *(_DWORD *)(a2 + 76);
    if ( (v8 & 0x200) != 0 || (v8 & 0x40) == 0 && (v8 & 0x80u) == 0 )
      return -1073741772;
    if ( (v8 & 4) != 0 )
      break;
    v9 = 0;
    if ( (v8 & 0x800) == 0 )
    {
      v10 = *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16);
      if ( (v8 & 0x100) != 0 )
      {
        if ( (v8 & 0x40) != 0 && (v10 & 0xD0156) == 0 )
          goto LABEL_42;
      }
      else if ( (v8 & 0x80u) != 0 && (v10 & 0x10000) == 0 && *(_QWORD *)(a2 + 24) == *(_QWORD *)(a2 + 48) )
      {
        goto LABEL_39;
      }
    }
    if ( (*(_DWORD *)(a2 + 76) & 0x1080) == 0x1000 )
    {
      result = VfsCreateContextNormalize(a2);
      if ( result < 0 )
        return result;
      result = VfsCowCopyFile(
                 a2 + 56,
                 (__int64)CallbackData,
                 *(struct _FLT_INSTANCE **)(a2 + 24),
                 (struct _UNICODE_STRING *)(a2 + 32),
                 *(PFLT_INSTANCE *)(a2 + 48),
                 a2 + 56,
                 *(_QWORD *)(a2 + 8),
                 *(PVOID *)a2,
                 (*(_DWORD *)(a2 + 76) & 0x10) == 0,
                 BYTE1(*(_DWORD *)(a2 + 76)) & 1);
      if ( result < 0 )
        return result;
      *(_DWORD *)(a2 + 76) |= 0x90u;
      if ( (*(_DWORD *)(a2 + 76) & 0x900) == 0 )
        v9 = (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x10000) == 0
          && *(_QWORD *)(a2 + 24) == *(_QWORD *)(a2 + 48);
    }
    if ( v9 )
    {
LABEL_39:
      result = IoReplaceFileObjectName(CallbackData->Iopb->TargetFileObject, *(PWSTR *)(a2 + 64), *(_WORD *)(a2 + 56));
      if ( result < 0 )
        return result;
      *a3 = 2;
      return 0;
    }
    v12 = *(_DWORD *)(a2 + 76);
    if ( (v12 & 0x80u) != 0 )
    {
      v15 = *(_DWORD *)(a2 + 76) & 0x800;
      if ( v15 )
        v16 = *(struct _FLT_INSTANCE **)(a2 + 24);
      else
        v16 = 0;
      result = VfsCreateShadow(
                 CallbackData,
                 1,
                 v16,
                 (struct _FLT_INSTANCE *)((a2 + 32) & -(__int64)(v15 != 0)),
                 0,
                 *(PFLT_INSTANCE *)(a2 + 48),
                 a2 + 56,
                 0,
                 (*(_DWORD *)(a2 + 76) & 0x40) != 0,
                 0,
                 (*(_DWORD *)(a2 + 76) & 0x100) != 0,
                 0,
                 *(_QWORD *)a2,
                 *(_QWORD *)(a2 + 8),
                 *(_QWORD *)(a2 + 16),
                 &v17);
      if ( result >= 0 )
      {
LABEL_38:
        CallbackData->IoStatus.Information = 1;
        CallbackData->IoStatus.Status = 0;
        *a3 = 3;
        return 0;
      }
      return result;
    }
    if ( (v12 & 4) == 0 && (v7 & 0xD0156) != 0 )
    {
      v13 = *(_QWORD **)(a2 + 16);
      if ( *(_DWORD *)(a2 + 72) )
        v14 = (void *)((v12 & 0x100) != 0 ? v13[11] : v13[10]);
      else
        v14 = (void *)v13[9];
      result = VfsAccessCheck(
                 v14,
                 (__int64)CallbackData,
                 *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16),
                 0);
      if ( result < 0 )
        return result;
    }
    result = VfsCreateShadow(
               CallbackData,
               1,
               0,
               0,
               *(PFLT_INSTANCE *)(a2 + 48),
               *(PFLT_INSTANCE *)(a2 + 24),
               a2 + 32,
               1,
               1,
               0,
               BYTE1(*(_DWORD *)(a2 + 76)) & 1,
               (*(_DWORD *)(a2 + 76) & 4) == 0,
               *(_QWORD *)a2,
               *(_QWORD *)(a2 + 8),
               *(_QWORD *)(a2 + 16),
               &v17);
    if ( result < 0 )
      return result;
    if ( !(_BYTE)v17 )
      goto LABEL_38;
    *(_DWORD *)(a2 + 76) |= 0x90u;
  }
  if ( (v8 & 0x40) != 0 )
  {
LABEL_42:
    *a3 = 1;
    return 0;
  }
  return -1073741772;
}

```

## disassembly

```asm
0x1400049b4  push    rbx
0x1400049b6  push    rbp
0x1400049b7  push    rsi
0x1400049b8  push    rdi
0x1400049b9  push    r12
0x1400049bb  push    r14
0x1400049bd  sub     rsp, 88h
0x1400049c4  mov     rax, [rcx+10h]
0x1400049c8  mov     r14, r8
0x1400049cb  mov     rbx, rdx
0x1400049ce  mov     byte ptr [rsp+0B8h+arg_0], 0
0x1400049d6  mov     rdi, rcx
0x1400049d9  mov     r12d, 1
0x1400049df  mov     r9, [rax+18h]
0x1400049e3  mov     ebp, [r9+10h]
0x1400049e7  mov     dword ptr [r8], 0
0x1400049ee  mov     edx, [rbx+4Ch]
0x1400049f1  bt      edx, 9
0x1400049f5  jb      loc_140004CFD
0x1400049fb  mov     r8d, edx
0x1400049fe  and     r8d, 40h
0x140004a02  jnz     short loc_140004A0C
0x140004a04  test    dl, dl
0x140004a06  jns     loc_140004CFD
0x140004a0c  test    dl, 4
0x140004a0f  jnz     loc_140004CF1
0x140004a15  xor     sil, sil
0x140004a18  bt      edx, 0Bh
0x140004a1c  jb      short loc_140004A59
0x140004a1e  mov     rax, [rdi+10h]
0x140004a22  mov     rcx, [rax+18h]
0x140004a26  mov     eax, [rcx+10h]
0x140004a29  bt      edx, 8
0x140004a2d  jnb     short loc_140004A41
0x140004a2f  test    r8d, r8d
0x140004a32  jz      short loc_140004A59
0x140004a34  test    eax, 0D0156h
0x140004a39  jz      loc_140004CF6
0x140004a3f  jmp     short loc_140004A59
0x140004a41  test    dl, dl
0x140004a43  jns     short loc_140004A59
0x140004a45  bt      eax, 10h
0x140004a49  jb      short loc_140004A59
0x140004a4b  mov     rax, [rbx+30h]
0x140004a4f  cmp     [rbx+18h], rax
0x140004a53  jz      loc_140004CC7
0x140004a59  and     edx, 1080h
0x140004a5f  cmp     edx, 1000h
0x140004a65  jnz     loc_140004B03
0x140004a6b  mov     rcx, rbx
0x140004a6e  call    VfsCreateContextNormalize
0x140004a73  test    eax, eax
0x140004a75  js      loc_140004D02
0x140004a7b  mov     edx, [rbx+4Ch]
0x140004a7e  lea     rcx, [rbx+38h]
0x140004a82  mov     r8, [rbx+18h]
0x140004a86  lea     r9, [rbx+20h]
0x140004a8a  mov     eax, edx
0x140004a8c  shr     edx, 4
0x140004a8f  shr     eax, 8
0x140004a92  not     dl
0x140004a94  and     al, r12b
0x140004a97  and     dl, r12b
0x140004a9a  mov     [rsp+0B8h+var_70], al
0x140004a9e  mov     rax, [rbx]
0x140004aa1  mov     [rsp+0B8h+var_78], dl
0x140004aa5  mov     rdx, rdi
0x140004aa8  mov     qword ptr [rsp+0B8h+var_80], rax
0x140004aad  mov     rax, [rbx+8]
0x140004ab1  mov     [rsp+0B8h+var_88], rax
0x140004ab6  mov     rax, [rbx+30h]
0x140004aba  mov     [rsp+0B8h+TargetInstance], rcx
0x140004abf  mov     [rsp+0B8h+var_98], rax
0x140004ac4  call    VfsCowCopyFile
0x140004ac9  test    eax, eax
0x140004acb  js      loc_140004D02
0x140004ad1  or      dword ptr [rbx+4Ch], 90h
0x140004ad8  test    dword ptr [rbx+4Ch], 900h
0x140004adf  jnz     short loc_140004B03
0x140004ae1  mov     rax, [rdi+10h]
0x140004ae5  mov     rcx, [rax+18h]
0x140004ae9  test    dword ptr [rcx+10h], 10000h
0x140004af0  jz      short loc_140004AF7
0x140004af2  xor     sil, sil
0x140004af5  jmp     short loc_140004B03
0x140004af7  mov     rax, [rbx+30h]
0x140004afb  cmp     [rbx+18h], rax
0x140004aff  setz    sil
0x140004b03  test    sil, sil
0x140004b06  jnz     loc_140004CC7
0x140004b0c  mov     edx, [rbx+4Ch]
0x140004b0f  test    dl, dl
0x140004b11  js      loc_140004C08
0x140004b17  test    dl, 4
0x140004b1a  jnz     short loc_140004B65
0x140004b1c  test    ebp, 0D0156h
0x140004b22  jz      short loc_140004B65
0x140004b24  cmp     dword ptr [rbx+48h], 0
0x140004b28  mov     rax, [rdi+10h]
0x140004b2c  mov     r8, [rbx+10h]
0x140004b30  mov     rcx, [rax+18h]
0x140004b34  mov     eax, [rcx+10h]
0x140004b37  jnz     short loc_140004B3F
0x140004b39  mov     rcx, [r8+48h]
0x140004b3d  jmp     short loc_140004B4F
0x140004b3f  bt      edx, 8
0x140004b43  jb      short loc_140004B4B
0x140004b45  mov     rcx, [r8+50h]
0x140004b49  jmp     short loc_140004B4F
0x140004b4b  mov     rcx, [r8+58h]; SecurityDescriptor
0x140004b4f  xor     r9d, r9d
0x140004b52  mov     r8d, eax
0x140004b55  mov     rdx, rdi
0x140004b58  call    VfsAccessCheck
0x140004b5d  test    eax, eax
0x140004b5f  js      loc_140004D02
0x140004b65  mov     r8d, [rbx+4Ch]
0x140004b69  lea     rax, [rsp+0B8h+arg_0]
0x140004b71  mov     [rsp+0B8h+var_40], rax; __int64
0x140004b76  lea     rcx, [rbx+20h]
0x140004b7a  mov     rax, [rbx+10h]
0x140004b7e  mov     edx, r8d
0x140004b81  mov     [rsp+0B8h+var_48], rax; __int64
0x140004b86  xor     r9d, r9d
0x140004b89  mov     rax, [rbx+8]
0x140004b8d  mov     [rsp+0B8h+var_50], rax; __int64
0x140004b92  mov     rax, [rbx]
0x140004b95  mov     [rsp+0B8h+var_58], rax; __int64
0x140004b9a  mov     rax, [rbx+18h]
0x140004b9e  shr     edx, 2
0x140004ba1  not     dl
0x140004ba3  shr     r8d, 8
0x140004ba7  and     dl, r12b
0x140004baa  and     r8b, r12b
0x140004bad  mov     [rsp+0B8h+var_60], dl; char
0x140004bb1  mov     edx, r12d
0x140004bb4  mov     [rsp+0B8h+var_68], r8b; char
0x140004bb9  xor     r8d, r8d
0x140004bbc  mov     [rsp+0B8h+var_70], 0; char
0x140004bc1  mov     [rsp+0B8h+var_78], r12b; char
0x140004bc6  mov     [rsp+0B8h+var_80], r12b; char
0x140004bcb  mov     [rsp+0B8h+var_88], rcx; __int64
0x140004bd0  mov     rcx, rdi; CallbackData
0x140004bd3  mov     [rsp+0B8h+TargetInstance], rax; TargetInstance
0x140004bd8  mov     rax, [rbx+30h]
0x140004bdc  mov     [rsp+0B8h+var_98], rax; PFLT_INSTANCE
0x140004be1  call    VfsCreateShadow
0x140004be6  test    eax, eax
0x140004be8  js      loc_140004D02
0x140004bee  cmp     byte ptr [rsp+0B8h+arg_0], 0
0x140004bf6  jz      loc_140004CB3
0x140004bfc  or      dword ptr [rbx+4Ch], 90h
0x140004c03  jmp     loc_1400049EE
0x140004c08  mov     r8d, edx
0x140004c0b  lea     rcx, [rbx+20h]
0x140004c0f  mov     r9d, edx
0x140004c12  and     r8d, 100h
0x140004c19  and     edx, 800h
0x140004c1f  and     r9d, 40h
0x140004c23  mov     eax, edx
0x140004c25  neg     eax
0x140004c27  sbb     r11, r11
0x140004c2a  and     r11, rcx
0x140004c2d  test    edx, edx
0x140004c2f  jz      short loc_140004C37
0x140004c31  mov     rsi, [rbx+18h]
0x140004c35  jmp     short loc_140004C39
0x140004c37  xor     esi, esi
0x140004c39  test    r8d, r8d
0x140004c3c  lea     rax, [rsp+0B8h+arg_0]
0x140004c44  mov     [rsp+0B8h+var_40], rax; __int64
0x140004c49  lea     r10, [rbx+38h]
0x140004c4d  mov     rax, [rbx+10h]
0x140004c51  setnz   cl
0x140004c54  mov     [rsp+0B8h+var_48], rax; __int64
0x140004c59  test    r9d, r9d
0x140004c5c  mov     rax, [rbx+8]
0x140004c60  mov     r9, r11
0x140004c63  mov     [rsp+0B8h+var_50], rax; __int64
0x140004c68  setnz   dl
0x140004c6b  mov     rax, [rbx]
0x140004c6e  mov     r8, rsi
0x140004c71  mov     [rsp+0B8h+var_58], rax; __int64
0x140004c76  mov     rax, [rbx+30h]
0x140004c7a  mov     [rsp+0B8h+var_60], 0; char
0x140004c7f  mov     [rsp+0B8h+var_68], cl; char
0x140004c83  mov     rcx, rdi; CallbackData
0x140004c86  mov     [rsp+0B8h+var_70], 0; char
0x140004c8b  mov     [rsp+0B8h+var_78], dl; char
0x140004c8f  mov     edx, r12d
0x140004c92  mov     [rsp+0B8h+var_80], 0; char
0x140004c97  mov     [rsp+0B8h+var_88], r10; __int64
0x140004c9c  mov     [rsp+0B8h+TargetInstance], rax; TargetInstance
0x140004ca1  mov     [rsp+0B8h+var_98], 0; PFLT_INSTANCE
0x140004caa  call    VfsCreateShadow
0x140004caf  test    eax, eax
0x140004cb1  js      short loc_140004D02
0x140004cb3  mov     [rdi+20h], r12
0x140004cb7  mov     dword ptr [rdi+18h], 0
0x140004cbe  mov     dword ptr [r14], 3
0x140004cc5  jmp     short loc_140004CF9
0x140004cc7  mov     rcx, [rdi+10h]
0x140004ccb  movzx   r8d, word ptr [rbx+38h]; FileNameLength
0x140004cd0  mov     rdx, [rbx+40h]; NewFileName
0x140004cd4  mov     rcx, [rcx+8]; FileObject
0x140004cd8  call    cs:__imp_IoReplaceFileObjectName
0x140004cdf  nop     dword ptr [rax+rax+00h]
0x140004ce4  test    eax, eax
0x140004ce6  js      short loc_140004D02
0x140004ce8  mov     dword ptr [r14], 2
0x140004cef  jmp     short loc_140004CF9
0x140004cf1  test    r8d, r8d
0x140004cf4  jz      short loc_140004CFD
0x140004cf6  mov     [r14], r12d
0x140004cf9  xor     eax, eax
0x140004cfb  jmp     short loc_140004D02
0x140004cfd  mov     eax, 0C0000034h
0x140004d02  add     rsp, 88h
0x140004d09  pop     r14
0x140004d0b  pop     r12
0x140004d0d  pop     rdi
0x140004d0e  pop     rsi
0x140004d0f  pop     rbp
0x140004d10  pop     rbx
0x140004d11  retn
```

# WimReadOverlayConfig

- ea: `0x14003c5c8`
- end: `0x14003caaa`
- name: `WimReadOverlayConfig`
- size: `1250`
- prototype: `__int64 __fastcall(__int64, char, HANDLE *, PFILE_OBJECT *, _QWORD *, ULONG *)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1400227a0`
- `0x14002ad78`
- `0x14002b7cc`
- `0x14002badc`
- `0x14002d424`

## callees

- `0x14000d3b8`
- `0x14000fb90`
- `0x140010010`
- `0x140010078`
- `0x140011560`
- `0x14002b078`
- `0x14002ba10`
- `0x14002c2c0`
- `0x14003c5c8`
- `0x14003cab0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ca15`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c6e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c6e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ca5f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003ca5f`
- `FLTMGR!FltReadFile` at `0x14003c962`
- `FLTMGR!FltReadFile` at `0x14003c962`
- `FLTMGR!FltQueryInformationFile` at `0x14003c825`
- `FLTMGR!FltQueryInformationFile` at `0x14003c825`
- `FLTMGR!FltClose` at `0x14003ca74`
- `FLTMGR!FltClose` at `0x14003ca74`

## string_xrefs

- `0x14003c622`: `WimOverlay.dat`
- `0x14003c74b`: `WimOverlay.dat`
- `0x14003c66a`: `WimOverlay.new`

## pseudocode

```c
__int64 __fastcall WimReadOverlayConfig(__int64 a1, char a2, HANDLE *a3, PFILE_OBJECT *a4, _QWORD *a5, ULONG *a6)
{
  int v10; // eax
  int EmptyOverlayConfig; // ebx
  int v12; // eax
  char *PoolWithTag; // rax
  void *v14; // rdi
  __int64 v15; // r9
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  ULONG v18; // edi
  _DWORD *v19; // rsi
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  ULONG *v23; // rax
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-29h] BYREF
  ULONG BytesRead; // [rsp+58h] [rbp-21h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-19h] BYREF
  ULONG *v28; // [rsp+68h] [rbp-11h]
  __int128 FileInformation; // [rsp+70h] [rbp-9h] BYREF
  __int64 v30; // [rsp+80h] [rbp+7h]

  v30 = 0;
  BytesRead = 0;
  FileHandle = 0;
  FileObject = 0;
  v28 = a6;
  FileInformation = 0;
  v10 = WimOpenOverlayConfig(a1, L"WimOverlay.dat", 0, &FileHandle, &FileObject);
  EmptyOverlayConfig = v10;
  if ( v10 >= 0 )
    goto LABEL_29;
  if ( v10 != -1073741772 && v10 != -1073741766 )
  {
LABEL_24:
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      goto LABEL_65;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Sld(WPP_GLOBAL_Control->AttachedDevice);
LABEL_27:
    if ( EmptyOverlayConfig < 0 )
      goto LABEL_65;
    goto LABEL_61;
  }
  v12 = WimOpenOverlayConfig(a1, L"WimOverlay.new", 0, &FileHandle, &FileObject);
  EmptyOverlayConfig = v12;
  if ( a2 && (v12 == -1073741772 || v12 == -1073741766) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, a1 + 64);
    EmptyOverlayConfig = WimAllocateEmptyOverlayConfig(a5, a6);
    goto LABEL_27;
  }
  if ( v12 < 0 )
  {
    if ( v12 == -1073741772 )
    {
      EmptyOverlayConfig = -1073741809;
      goto LABEL_65;
    }
    goto LABEL_24;
  }
  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x30u, 0x66637077u);
  v14 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v15 = 3221225626LL;
    EmptyOverlayConfig = -1073741670;
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 29;
    goto LABEL_16;
  }
  *PoolWithTag = 1;
  *((_QWORD *)PoolWithTag + 1) = 0;
  *((_DWORD *)PoolWithTag + 4) = 28;
  *(_OWORD *)(PoolWithTag + 20) = *(_OWORD *)L"WimOverlay.dat";
  *((_OWORD *)PoolWithTag + 2) = *(_OWORD *)L"rlay.dat";
  EmptyOverlayConfig = WimRenameOnSystemThread(*(_QWORD *)(a1 + 120), FileObject, PoolWithTag);
  ExFreePoolWithTag(v14, 0);
  if ( (int)(EmptyOverlayConfig + 0x80000000) >= 0 && EmptyOverlayConfig != -1073741662 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 30;
LABEL_33:
    v15 = (unsigned int)EmptyOverlayConfig;
    goto LABEL_16;
  }
LABEL_29:
  EmptyOverlayConfig = FltQueryInformationFile(
                         *(PFLT_INSTANCE *)(a1 + 120),
                         FileObject,
                         &FileInformation,
                         0x18u,
                         FileStandardInformation,
                         0);
  if ( EmptyOverlayConfig < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 32;
    goto LABEL_33;
  }
  v18 = DWORD2(FileInformation);
  if ( *((__int64 *)&FileInformation + 1) > 0x200000 )
  {
    v15 = 3221226180LL;
    EmptyOverlayConfig = -1073741116;
    v16 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_65;
    v17 = 33;
    goto LABEL_16;
  }
  if ( DWORD2(FileInformation) >= 0x18 )
  {
    v19 = ExAllocatePoolWithTag(PagedPool, DWORD2(FileInformation), 0x66637077u);
    if ( !v19 )
    {
      v15 = 3221225626LL;
      EmptyOverlayConfig = -1073741670;
      v16 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_65;
      v17 = 35;
LABEL_16:
      WPP_SF_d(v16->AttachedDevice, v17, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v15);
      goto LABEL_65;
    }
    EmptyOverlayConfig = FltReadFile(*(PFLT_INSTANCE *)(a1 + 120), FileObject, 0, v18, v19, 0, &BytesRead, 0, 0);
    if ( EmptyOverlayConfig >= 0 )
    {
      if ( BytesRead == v18 )
      {
        EmptyOverlayConfig = WimpValidateOverlayConfig(v19, v18);
        if ( EmptyOverlayConfig >= 0 )
        {
          v23 = v28;
          *a5 = v19;
          *v23 = v18;
LABEL_61:
          if ( a3 )
          {
            *a3 = FileHandle;
            FileHandle = 0;
          }
          if ( a4 )
          {
            *a4 = FileObject;
            FileObject = 0;
          }
          goto LABEL_65;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, a1 + 64);
LABEL_59:
        ExFreePoolWithTag(v19, 0);
        goto LABEL_65;
      }
      v22 = 3221226180LL;
      EmptyOverlayConfig = -1073741116;
      v20 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_59;
      v21 = 37;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_59;
      v21 = 36;
      v22 = (unsigned int)EmptyOverlayConfig;
    }
    WPP_SF_d(v20->AttachedDevice, v21, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v22);
    goto LABEL_59;
  }
  EmptyOverlayConfig = -1073741116;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
      DWORD2(FileInformation),
      -1073741116);
LABEL_65:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)EmptyOverlayConfig;
}

```

## disassembly

```asm
0x14003c5c8  mov     [rsp-8+arg_8], rbx
0x14003c5cd  push    rbp
0x14003c5ce  push    rsi
0x14003c5cf  push    rdi
0x14003c5d0  push    r12
0x14003c5d2  push    r13
0x14003c5d4  push    r14
0x14003c5d6  push    r15
0x14003c5d8  lea     rbp, [rsp-17h]
0x14003c5dd  sub     rsp, 90h
0x14003c5e4  mov     rax, cs:__security_cookie
0x14003c5eb  xor     rax, rsp
0x14003c5ee  mov     [rbp+47h+var_38], rax
0x14003c5f2  mov     rsi, [rbp+47h+arg_28]
0x14003c5f6  xor     eax, eax
0x14003c5f8  mov     r13, [rbp+47h+arg_20]
0x14003c5fc  mov     r15, r9
0x14003c5ff  mov     [rbp+47h+var_40], rax
0x14003c603  lea     r9, [rbp+47h+FileHandle]
0x14003c607  mov     [rbp+47h+var_68], eax
0x14003c60a  mov     r12, r8
0x14003c60d  mov     [rbp+47h+FileHandle], rax
0x14003c611  xorps   xmm0, xmm0
0x14003c614  mov     [rbp+47h+FileObject], rax
0x14003c618  xor     r8d, r8d
0x14003c61b  lea     rax, [rbp+47h+FileObject]
0x14003c61f  movzx   edi, dl
0x14003c622  lea     rdx, aWimoverlayDat; "WimOverlay.dat"
0x14003c629  mov     qword ptr [rsp+0C0h+FileInformationClass], rax
0x14003c62e  mov     r14, rcx
0x14003c631  mov     [rbp+47h+var_58], rsi
0x14003c635  movups  [rbp+47h+FileInformation], xmm0
0x14003c639  call    WimOpenOverlayConfig
0x14003c63e  mov     ebx, eax
0x14003c640  test    eax, eax
0x14003c642  jns     loc_14003C802
0x14003c648  cmp     eax, 0C0000034h
0x14003c64d  jz      short loc_14003C65A
0x14003c64f  cmp     eax, 0C000003Ah
0x14003c654  jnz     loc_14003C7CC
0x14003c65a  lea     rax, [rbp+47h+FileObject]
0x14003c65e  xor     r8d, r8d
0x14003c661  lea     r9, [rbp+47h+FileHandle]
0x14003c665  mov     qword ptr [rsp+0C0h+FileInformationClass], rax
0x14003c66a  lea     rdx, aWimoverlayNew; "WimOverlay.new"
0x14003c671  mov     rcx, r14
0x14003c674  call    WimOpenOverlayConfig
0x14003c679  mov     ebx, eax
0x14003c67b  test    dil, dil
0x14003c67e  jz      short loc_14003C6CD
0x14003c680  cmp     eax, 0C0000034h
0x14003c685  jz      short loc_14003C68E
0x14003c687  cmp     eax, 0C000003Ah
0x14003c68c  jnz     short loc_14003C6CD
0x14003c68e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c695  mov     eax, [rcx+2Ch]
0x14003c698  test    al, 8
0x14003c69a  jz      short loc_14003C6BB
0x14003c69c  cmp     byte ptr [rcx+29h], 4
0x14003c6a0  jb      short loc_14003C6BB
0x14003c6a2  mov     rcx, [rcx+18h]
0x14003c6a6  lea     r9, [r14+40h]
0x14003c6aa  mov     edx, 1Ch
0x14003c6af  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c6b6  call    WPP_SF_Z
0x14003c6bb  mov     rdx, rsi
0x14003c6be  mov     rcx, r13
0x14003c6c1  call    WimAllocateEmptyOverlayConfig
0x14003c6c6  mov     ebx, eax
0x14003c6c8  jmp     loc_14003C7F5
0x14003c6cd  test    eax, eax
0x14003c6cf  js      loc_14003C7BD
0x14003c6d5  mov     edx, 30h ; '0'; NumberOfBytes
0x14003c6da  mov     r8d, 66637077h; Tag
0x14003c6e0  lea     ecx, [rdx-2Fh]; PoolType
0x14003c6e3  call    cs:__imp_ExAllocatePoolWithTag
0x14003c6ea  nop     dword ptr [rax+rax+00h]
0x14003c6ef  mov     rdi, rax
0x14003c6f2  test    rax, rax
0x14003c6f5  jnz     short loc_14003C736
0x14003c6f7  mov     r9d, 0C000009Ah
0x14003c6fd  mov     ebx, r9d
0x14003c700  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c707  test    dword ptr [rcx+2Ch], 400h
0x14003c70e  jz      loc_14003CA56
0x14003c714  cmp     byte ptr [rcx+29h], 2
0x14003c718  jb      loc_14003CA56
0x14003c71e  lea     edx, [rax+1Dh]
0x14003c721  mov     rcx, [rcx+18h]
0x14003c725  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c72c  call    WPP_SF_d
0x14003c731  jmp     loc_14003CA56
0x14003c736  mov     byte ptr [rax], 1
0x14003c739  mov     r8, rdi
0x14003c73c  mov     qword ptr [rax+8], 0
0x14003c744  mov     dword ptr [rax+10h], 1Ch
0x14003c74b  movups  xmm0, xmmword ptr cs:aWimoverlayDat; "WimOverlay.dat"
0x14003c752  movups  xmmword ptr [rax+14h], xmm0
0x14003c756  movups  xmm1, xmmword ptr cs:aWimoverlayDat+0Ch; "rlay.dat"
0x14003c75d  movups  xmmword ptr [rax+20h], xmm1
0x14003c761  mov     rdx, [rbp+47h+FileObject]
0x14003c765  mov     rcx, [r14+78h]
0x14003c769  call    WimRenameOnSystemThread
0x14003c76e  xor     edx, edx; Tag
0x14003c770  mov     rcx, rdi; P
0x14003c773  mov     ebx, eax
0x14003c775  call    cs:__imp_ExFreePoolWithTag
0x14003c77c  nop     dword ptr [rax+rax+00h]
0x14003c781  mov     ecx, 80000000h
0x14003c786  lea     eax, [rbx+rcx]
0x14003c789  test    ecx, eax
0x14003c78b  jnz     short loc_14003C802
0x14003c78d  cmp     ebx, 0C00000A2h
0x14003c793  jz      short loc_14003C802
0x14003c795  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c79c  test    dword ptr [rcx+2Ch], 400h
0x14003c7a3  jz      loc_14003CA56
0x14003c7a9  cmp     byte ptr [rcx+29h], 2
0x14003c7ad  jb      loc_14003CA56
0x14003c7b3  mov     edx, 1Eh
0x14003c7b8  jmp     loc_14003C858
0x14003c7bd  cmp     eax, 0C0000034h
0x14003c7c2  jnz     short loc_14003C7CC
0x14003c7c4  lea     ebx, [rax-25h]
0x14003c7c7  jmp     loc_14003CA56
0x14003c7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c7d3  mov     eax, [rcx+2Ch]
0x14003c7d6  test    al, 8
0x14003c7d8  jz      loc_14003CA56
0x14003c7de  cmp     byte ptr [rcx+29h], 2
0x14003c7e2  jb      short loc_14003C7F5
0x14003c7e4  mov     rcx, [rcx+18h]
0x14003c7e8  mov     dword ptr [rsp+0C0h+LengthReturned], ebx
0x14003c7ec  mov     [rsp+0C0h+FileInformationClass], edi
0x14003c7f0  call    WPP_SF_Sld
0x14003c7f5  test    ebx, ebx
0x14003c7f7  jns     loc_14003CA2D
0x14003c7fd  jmp     loc_14003CA56
0x14003c802  mov     rdx, [rbp+47h+FileObject]; FileObject
0x14003c806  lea     r8, [rbp+47h+FileInformation]; FileInformation
0x14003c80a  mov     rcx, [r14+78h]; Instance
0x14003c80e  mov     r9d, 18h; Length
0x14003c814  mov     [rsp+0C0h+LengthReturned], 0; LengthReturned
0x14003c81d  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x14003c825  call    cs:__imp_FltQueryInformationFile
0x14003c82c  nop     dword ptr [rax+rax+00h]
0x14003c831  mov     ebx, eax
0x14003c833  test    eax, eax
0x14003c835  jns     short loc_14003C860
0x14003c837  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c83e  mov     eax, [rcx+2Ch]
0x14003c841  test    al, 8
0x14003c843  jz      loc_14003CA56
0x14003c849  cmp     byte ptr [rcx+29h], 2
0x14003c84d  jb      loc_14003CA56
0x14003c853  mov     edx, 20h ; ' '
0x14003c858  mov     r9d, ebx
0x14003c85b  jmp     loc_14003C721
0x14003c860  mov     rdi, qword ptr [rbp+47h+FileInformation+8]
0x14003c864  cmp     rdi, 200000h
0x14003c86b  jle     short loc_14003C89C
0x14003c86d  mov     r9d, 0C00002C4h
0x14003c873  mov     ebx, r9d
0x14003c876  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c87d  mov     eax, [rcx+2Ch]
0x14003c880  test    al, 8
0x14003c882  jz      loc_14003CA56
0x14003c888  cmp     byte ptr [rcx+29h], 2
0x14003c88c  jb      loc_14003CA56
0x14003c892  mov     edx, 21h ; '!'
0x14003c897  jmp     loc_14003C721
0x14003c89c  cmp     edi, 18h
0x14003c89f  jnb     short loc_14003C8E8
0x14003c8a1  mov     r9d, 0C00002C4h
0x14003c8a7  mov     ebx, r9d
0x14003c8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8b1  mov     eax, [rcx+2Ch]
0x14003c8b4  test    al, 8
0x14003c8b6  jz      loc_14003CA56
0x14003c8bc  cmp     byte ptr [rcx+29h], 2
0x14003c8c0  jb      loc_14003CA56
0x14003c8c6  mov     rcx, [rcx+18h]
0x14003c8ca  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c8d1  mov     [rsp+0C0h+FileInformationClass], r9d
0x14003c8d6  mov     edx, 22h ; '"'
0x14003c8db  mov     r9d, edi
0x14003c8de  call    WPP_SF_dd
0x14003c8e3  jmp     loc_14003CA56
0x14003c8e8  mov     edx, edi; NumberOfBytes
0x14003c8ea  mov     ecx, 1; PoolType
0x14003c8ef  mov     r8d, 66637077h; Tag
0x14003c8f5  call    cs:__imp_ExAllocatePoolWithTag
0x14003c8fc  nop     dword ptr [rax+rax+00h]
0x14003c901  xor     ecx, ecx
0x14003c903  mov     rsi, rax
0x14003c906  test    rax, rax
0x14003c909  jnz     short loc_14003C938
0x14003c90b  mov     r9d, 0C000009Ah
0x14003c911  mov     ebx, r9d
0x14003c914  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c91b  mov     eax, [rcx+2Ch]
0x14003c91e  test    al, 8
0x14003c920  jz      loc_14003CA56
0x14003c926  cmp     byte ptr [rcx+29h], 2
0x14003c92a  jb      loc_14003CA56
0x14003c930  lea     edx, [rsi+23h]
0x14003c933  jmp     loc_14003C721
0x14003c938  mov     rdx, [rbp+47h+FileObject]; FileObject
0x14003c93c  lea     rax, [rbp+47h+var_68]
0x14003c940  mov     [rsp+0C0h+CallbackContext], rcx; CallbackContext
0x14003c945  mov     r9d, edi; Length
0x14003c948  mov     [rsp+0C0h+CallbackRoutine], rcx; CallbackRoutine
0x14003c94d  xor     r8d, r8d; ByteOffset
0x14003c950  mov     [rsp+0C0h+BytesRead], rax; BytesRead
0x14003c955  mov     dword ptr [rsp+0C0h+LengthReturned], ecx; Flags
0x14003c959  mov     rcx, [r14+78h]; InitiatingInstance
0x14003c95d  mov     qword ptr [rsp+0C0h+FileInformationClass], rsi; Buffer
0x14003c962  call    cs:__imp_FltReadFile
0x14003c969  nop     dword ptr [rax+rax+00h]
0x14003c96e  mov     ebx, eax
0x14003c970  test    eax, eax
0x14003c972  jns     short loc_14003C99A
0x14003c974  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c97b  mov     eax, [rcx+2Ch]
0x14003c97e  test    al, 8
0x14003c980  jz      loc_14003CA10
0x14003c986  cmp     byte ptr [rcx+29h], 2
0x14003c98a  jb      loc_14003CA10
0x14003c990  mov     edx, 24h ; '$'
0x14003c995  mov     r9d, ebx
0x14003c998  jmp     short loc_14003C9C1
0x14003c99a  cmp     [rbp+47h+var_68], edi
0x14003c99d  jz      short loc_14003C9D3
0x14003c99f  mov     r9d, 0C00002C4h
0x14003c9a5  mov     ebx, r9d
0x14003c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c9af  mov     eax, [rcx+2Ch]
0x14003c9b2  test    al, 8
0x14003c9b4  jz      short loc_14003CA10
0x14003c9b6  cmp     byte ptr [rcx+29h], 2
0x14003c9ba  jb      short loc_14003CA10
0x14003c9bc  mov     edx, 25h ; '%'
0x14003c9c1  mov     rcx, [rcx+18h]
0x14003c9c5  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003c9cc  call    WPP_SF_d
0x14003c9d1  jmp     short loc_14003CA10
0x14003c9d3  mov     edx, edi
0x14003c9d5  mov     rcx, rsi
0x14003c9d8  call    WimpValidateOverlayConfig
0x14003c9dd  mov     ebx, eax
0x14003c9df  test    eax, eax
0x14003c9e1  jns     short loc_14003CA23
0x14003c9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c9ea  mov     eax, [rcx+2Ch]
0x14003c9ed  test    al, 8
0x14003c9ef  jz      short loc_14003CA10
0x14003c9f1  cmp     byte ptr [rcx+29h], 2
0x14003c9f5  jb      short loc_14003CA10
0x14003c9f7  mov     rcx, [rcx+18h]
0x14003c9fb  lea     r9, [r14+40h]
0x14003c9ff  mov     edx, 26h ; '&'
0x14003ca04  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14003ca0b  call    WPP_SF_Z
0x14003ca10  xor     edx, edx; Tag
0x14003ca12  mov     rcx, rsi; P
0x14003ca15  call    cs:__imp_ExFreePoolWithTag
0x14003ca1c  nop     dword ptr [rax+rax+00h]
0x14003ca21  jmp     short loc_14003CA56
0x14003ca23  mov     rax, [rbp+47h+var_58]
0x14003ca27  mov     [r13+0], rsi
0x14003ca2b  mov     [rax], edi
0x14003ca2d  test    r12, r12
0x14003ca30  jz      short loc_14003CA42
0x14003ca32  mov     rax, [rbp+47h+FileHandle]
0x14003ca36  mov     [r12], rax
0x14003ca3a  mov     [rbp+47h+FileHandle], 0
0x14003ca42  test    r15, r15
0x14003ca45  jz      short loc_14003CA56
0x14003ca47  mov     rax, [rbp+47h+FileObject]
0x14003ca4b  mov     [r15], rax
0x14003ca4e  mov     [rbp+47h+FileObject], 0
0x14003ca56  mov     rcx, [rbp+47h+FileObject]; Object
0x14003ca5a  test    rcx, rcx
0x14003ca5d  jz      short loc_14003CA6B
0x14003ca5f  call    cs:__imp_ObfDereferenceObject
0x14003ca66  nop     dword ptr [rax+rax+00h]
0x14003ca6b  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14003ca6f  test    rcx, rcx
0x14003ca72  jz      short loc_14003CA80
0x14003ca74  call    cs:__imp_FltClose
0x14003ca7b  nop     dword ptr [rax+rax+00h]
0x14003ca80  mov     eax, ebx
0x14003ca82  mov     rcx, [rbp+47h+var_38]
0x14003ca86  xor     rcx, rsp; StackCookie
0x14003ca89  call    __security_check_cookie
0x14003ca8e  mov     rbx, [rsp+0C0h+arg_8]
0x14003ca96  add     rsp, 90h
0x14003ca9d  pop     r15
0x14003ca9f  pop     r14
0x14003caa1  pop     r13
  ... truncated ...
```

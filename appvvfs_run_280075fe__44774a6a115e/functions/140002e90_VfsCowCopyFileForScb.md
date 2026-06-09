# VfsCowCopyFileForScb

- ea: `0x140002e90`
- end: `0x1400031b6`
- name: `VfsCowCopyFileForScb`
- size: `806`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140002b4c`
- `0x14000aefc`
- `0x14000c6fc`

## callees

- `0x1400022b4`
- `0x140002e90`
- `0x14000f630`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003196`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003196`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000318a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000318a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002eef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140002eef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002ede`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002ede`
- `FLTMGR!FltObjectReference` at `0x14000303f`
- `FLTMGR!FltObjectReference` at `0x14000303f`
- `FLTMGR!FltObjectDereference` at `0x140003117`
- `FLTMGR!FltObjectDereference` at `0x140003117`
- `FLTMGR!FltCreateFileEx2` at `0x140003102`
- `FLTMGR!FltCreateFileEx2` at `0x140003102`

## string_xrefs

- `0x140002fb3`: `VfsCowCopyFileForScb() - Failed to copy file: %wZ\n Status: 0x%08X`
- `0x140003058`: `VfsCowCopyFileForScb() - Failed to reference instance: %p\n Status: 0x%08X`

## pseudocode

```c
__int64 VfsCowCopyFileForScb(__int64 a1, __int64 a2, struct _FLT_INSTANCE *a3, ...)
{
  int v6; // edi
  _BYTE *v7; // r14
  struct _ERESOURCE *v8; // rbx
  __int64 v9; // rdx
  struct _UNICODE_STRING *v10; // rbx
  void *v11; // r15
  PVOID v12; // r14
  __int64 *i; // rbx
  NTSTATUS v14; // eax
  NTSTATUS v15; // edi
  ACCESS_MASK DesiredAccess[2]; // [rsp+20h] [rbp-D8h]
  int AllocationSize; // [rsp+38h] [rbp-C0h]
  ULONG FileAttributes; // [rsp+40h] [rbp-B8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-68h] BYREF
  PFILE_OBJECT FileObject; // [rsp+118h] [rbp+20h] BYREF
  va_list FileObjecta; // [rsp+118h] [rbp+20h]
  struct _UNICODE_STRING *v24; // [rsp+120h] [rbp+28h]
  PVOID FltObject; // [rsp+128h] [rbp+30h]
  __int64 v26; // [rsp+130h] [rbp+38h]
  __int64 v27; // [rsp+138h] [rbp+40h]
  __int64 v28; // [rsp+140h] [rbp+48h]
  __int64 v29; // [rsp+148h] [rbp+50h]
  void *FileHandle; // [rsp+150h] [rbp+58h] BYREF
  va_list FileHandlea; // [rsp+150h] [rbp+58h]
  va_list va2; // [rsp+158h] [rbp+60h] BYREF

  va_start(va2, a3);
  va_start(FileHandlea, a3);
  va_start(FileObjecta, a3);
  FileObject = va_arg(FileHandlea, PFILE_OBJECT);
  v24 = va_arg(FileHandlea, struct _UNICODE_STRING *);
  FltObject = va_arg(FileHandlea, PVOID);
  v26 = va_arg(FileHandlea, _QWORD);
  v27 = va_arg(FileHandlea, _QWORD);
  v28 = va_arg(FileHandlea, _QWORD);
  v29 = va_arg(FileHandlea, _QWORD);
  va_copy(va2, FileHandlea);
  FileHandle = va_arg(va2, void *);
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  v7 = FileHandle;
  if ( FileHandle )
    *(_BYTE *)FileHandle = 0;
  v8 = (struct _ERESOURCE *)(*(_QWORD *)(a1 + 120) + 56LL);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v8, 1u);
  if ( (*(_DWORD *)(a1 + 272) & 1) == 0 )
  {
    if ( a2 )
    {
      v6 = VfsCheckShareAccess(a2, a1, 1, 0);
      if ( v6 < 0 )
        goto LABEL_22;
    }
    v10 = (struct _UNICODE_STRING *)v27;
    v11 = (void *)v26;
    v12 = FltObject;
    v6 = VfsCopyFile(
           a3,
           v9,
           v24,
           (struct _FLT_INSTANCE *)FltObject,
           (void *)v26,
           (struct _UNICODE_STRING *)v27,
           (*(_DWORD *)(a1 + 272) & 2) != 0,
           AllocationSize,
           FileAttributes,
           v28,
           v29);
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741771 )
    {
      DesiredAccess[0] = v6;
      LogWrite(
        1,
        0,
        L"VfsCowCopyFileForScb() - Failed to copy file: %wZ\n Status: 0x%08X",
        v24,
        *(_QWORD *)DesiredAccess);
      goto LABEL_22;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v11;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v10;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    for ( i = *(__int64 **)(a1 + 256); ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)(a1 + 256) )
      {
        _InterlockedOr((volatile signed __int32 *)(a1 + 272), 1u);
        v6 = 0;
        goto LABEL_22;
      }
      FileObject = 0;
      FileHandle = 0;
      IoStatusBlock = 0;
      if ( (*((_DWORD *)i - 1) & 4) != 0 )
      {
        v14 = FltObjectReference(v12);
        v15 = v14;
        if ( v14 < 0 )
        {
          DesiredAccess[0] = v14;
          LogWrite(
            1,
            0,
            L"VfsCowCopyFileForScb() - Failed to reference instance: %p\n Status: 0x%08X",
            v12,
            *(_QWORD *)DesiredAccess);
LABEL_16:
          *((_DWORD *)i + 6) = v15;
          continue;
        }
        v15 = FltCreateFileEx2(
                VfsData,
                (PFLT_INSTANCE)v12,
                (PHANDLE)FileHandlea,
                (PFILE_OBJECT *)FileObjecta,
                *((_DWORD *)i + 24),
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0,
                *((_DWORD *)i + 25),
                1u,
                i[13] & 0xFFFFFF,
                0,
                0,
                (*((_DWORD *)i - 1) & 0x10 | 2) << 7,
                0);
        if ( v15 < 0 )
        {
          FltObjectDereference(v12);
          goto LABEL_16;
        }
        i[9] = (__int64)FileHandle;
        i[8] = (__int64)FileObject;
        i[7] = (__int64)v12;
        *(_QWORD *)(i[11] + 40) = FileObject->SectionObjectPointer;
        *(_QWORD *)(i[11] + 48) = FileObject->PrivateCacheMap;
        *((_DWORD *)i - 1) &= ~4u;
      }
    }
  }
  if ( v7 )
    *v7 = 1;
LABEL_22:
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 120) + 56LL));
  KeLeaveCriticalRegion();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140002e90  mov     r11, rsp
0x140002e93  mov     [r11+20h], r9
0x140002e97  push    rbx
0x140002e98  push    rsi
0x140002e99  push    rdi
0x140002e9a  push    r12
0x140002e9c  push    r14
0x140002e9e  push    r15
0x140002ea0  sub     rsp, 0C8h
0x140002ea7  mov     r12, r8
0x140002eaa  mov     r15, rdx
0x140002ead  mov     rsi, rcx
0x140002eb0  xor     edi, edi
0x140002eb2  xor     eax, eax
0x140002eb4  xorps   xmm0, xmm0
0x140002eb7  movups  xmmword ptr [r11-68h], xmm0
0x140002ebc  movups  xmmword ptr [r11-58h], xmm0
0x140002ec1  movups  xmmword ptr [r11-4Ch], xmm0
0x140002ec6  mov     r14, [rsp+0F8h+FileHandle]
0x140002ece  test    r14, r14
0x140002ed1  jz      short loc_140002ED6
0x140002ed3  mov     [r14], al
0x140002ed6  mov     rax, [rcx+78h]
0x140002eda  lea     rbx, [rax+38h]
0x140002ede  call    cs:__imp_KeEnterCriticalRegion
0x140002ee5  nop     dword ptr [rax+rax+00h]
0x140002eea  mov     dl, 1; Wait
0x140002eec  mov     rcx, rbx; Resource
0x140002eef  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140002ef6  nop     dword ptr [rax+rax+00h]
0x140002efb  nop
0x140002efc  mov     eax, [rsi+110h]
0x140002f02  test    al, 1
0x140002f04  jz      short loc_140002F18
0x140002f06  test    r14, r14
0x140002f09  jz      loc_140003182
0x140002f0f  mov     byte ptr [r14], 1
0x140002f13  jmp     loc_140003182
0x140002f18  test    r15, r15
0x140002f1b  jz      short loc_140002F38
0x140002f1d  xor     r9d, r9d
0x140002f20  mov     r8b, 1
0x140002f23  mov     rdx, rsi
0x140002f26  mov     rcx, r15
0x140002f29  call    VfsCheckShareAccess
0x140002f2e  mov     edi, eax
0x140002f30  test    eax, eax
0x140002f32  js      loc_140003182
0x140002f38  mov     ecx, [rsi+110h]
0x140002f3e  shr     ecx, 1
0x140002f40  and     cl, 1
0x140002f43  mov     al, byte ptr [rsp+0F8h+arg_48]
0x140002f4a  mov     byte ptr [rsp+0F8h+CreateDisposition], al; char
0x140002f4e  mov     al, byte ptr [rsp+0F8h+arg_40]
0x140002f55  mov     byte ptr [rsp+0F8h+ShareAccess], al; char
0x140002f59  mov     byte ptr [rsp+0F8h+IoStatusBlock], cl; char
0x140002f5d  mov     rbx, [rsp+0F8h+arg_38]
0x140002f65  mov     [rsp+0F8h+ObjectAttributes], rbx; __int64
0x140002f6a  mov     r15, [rsp+0F8h+arg_30]
0x140002f72  mov     qword ptr [rsp+0F8h+DesiredAccess], r15; __int64
0x140002f77  mov     r14, [rsp+0F8h+FltObject]
0x140002f7f  mov     r9, r14
0x140002f82  mov     r8, [rsp+0F8h+arg_20]
0x140002f8a  mov     rcx, r12; Instance
0x140002f8d  call    VfsCopyFile
0x140002f92  mov     edi, eax
0x140002f94  mov     edx, 80000000h
0x140002f99  add     eax, edx
0x140002f9b  test    edx, eax
0x140002f9d  jnz     short loc_140002FC9
0x140002f9f  cmp     edi, 0C0000035h
0x140002fa5  jz      short loc_140002FC9
0x140002fa7  mov     [rsp+0F8h+DesiredAccess], edi
0x140002fab  mov     r9, [rsp+0F8h+arg_20]
0x140002fb3  lea     r8, aVfscowcopyfile; "VfsCowCopyFileForScb() - Failed to copy"...
0x140002fba  xor     edx, edx
0x140002fbc  lea     ecx, [rdx+1]
0x140002fbf  call    LogWrite
0x140002fc4  jmp     loc_140003182
0x140002fc9  mov     [rsp+0F8h+var_68.Length], 30h ; '0'
0x140002fd4  mov     [rsp+0F8h+var_68.RootDirectory], r15
0x140002fdc  mov     [rsp+0F8h+var_68.Attributes], 240h
0x140002fe7  mov     [rsp+0F8h+var_68.ObjectName], rbx
0x140002fef  xorps   xmm0, xmm0
0x140002ff2  movdqu  xmmword ptr [rsp+0F8h+var_68.SecurityDescriptor], xmm0
0x140002ffb  lea     r15, [rsi+100h]
0x140003002  mov     rbx, [r15]
0x140003005  cmp     rbx, r15
0x140003008  jz      loc_140003178
0x14000300e  mov     [rsp+0F8h+FileObject], 0
0x14000301a  mov     [rsp+0F8h+FileHandle], 0
0x140003026  xorps   xmm0, xmm0
0x140003029  movups  xmmword ptr [rsp+0F8h+var_78], xmm0
0x140003031  mov     eax, [rbx-4]
0x140003034  test    al, 4
0x140003036  jz      loc_140003170
0x14000303c  mov     rcx, r14; FltObject
0x14000303f  call    cs:__imp_FltObjectReference
0x140003046  nop     dword ptr [rax+rax+00h]
0x14000304b  mov     edi, eax
0x14000304d  test    eax, eax
0x14000304f  jns     short loc_140003071
0x140003051  mov     [rsp+0F8h+DesiredAccess], eax
0x140003055  mov     r9, r14
0x140003058  lea     r8, aVfscowcopyfile_1; "VfsCowCopyFileForScb() - Failed to refe"...
0x14000305f  xor     edx, edx
0x140003061  lea     ecx, [rdx+1]
0x140003064  call    LogWrite
0x140003069  mov     [rbx+18h], edi
0x14000306c  jmp     loc_140003170
0x140003071  mov     ecx, [rbx-4]
0x140003074  and     ecx, 10h
0x140003077  or      ecx, 2
0x14000307a  shl     ecx, 7
0x14000307d  mov     eax, [rbx+68h]
0x140003080  and     eax, 0FFFFFFh
0x140003085  mov     [rsp+0F8h+DriverContext], 0; DriverContext
0x14000308e  mov     [rsp+0F8h+Flags], ecx; Flags
0x140003092  mov     [rsp+0F8h+EaLength], 0; EaLength
0x14000309a  mov     [rsp+0F8h+EaBuffer], 0; EaBuffer
0x1400030a3  mov     [rsp+0F8h+CreateOptions], eax; CreateOptions
0x1400030a7  mov     [rsp+0F8h+CreateDisposition], 1; CreateDisposition
0x1400030af  mov     eax, [rbx+64h]
0x1400030b2  mov     [rsp+0F8h+ShareAccess], eax; ShareAccess
0x1400030b6  mov     [rsp+0F8h+FileAttributes], 0; FileAttributes
0x1400030be  mov     [rsp+0F8h+AllocationSize], 0; AllocationSize
0x1400030c7  lea     rax, [rsp+0F8h+var_78]
0x1400030cf  mov     [rsp+0F8h+IoStatusBlock], rax; IoStatusBlock
0x1400030d4  lea     rax, [rsp+0F8h+var_68]
0x1400030dc  mov     [rsp+0F8h+ObjectAttributes], rax; ObjectAttributes
0x1400030e1  mov     eax, [rbx+60h]
0x1400030e4  mov     [rsp+0F8h+DesiredAccess], eax; DesiredAccess
0x1400030e8  lea     r9, [rsp+0F8h+FileObject]; FileObject
0x1400030f0  lea     r8, [rsp+0F8h+FileHandle]; FileHandle
0x1400030f8  mov     rdx, r14; Instance
0x1400030fb  mov     rcx, cs:VfsData; Filter
0x140003102  call    cs:__imp_FltCreateFileEx2
0x140003109  nop     dword ptr [rax+rax+00h]
0x14000310e  mov     edi, eax
0x140003110  test    eax, eax
0x140003112  jns     short loc_140003128
0x140003114  mov     rcx, r14; FltObject
0x140003117  call    cs:__imp_FltObjectDereference
0x14000311e  nop     dword ptr [rax+rax+00h]
0x140003123  jmp     loc_140003069
0x140003128  mov     rax, [rsp+0F8h+FileHandle]
0x140003130  mov     [rbx+48h], rax
0x140003134  mov     rax, [rsp+0F8h+FileObject]
0x14000313c  mov     [rbx+40h], rax
0x140003140  mov     [rbx+38h], r14
0x140003144  mov     rdx, [rbx+58h]
0x140003148  mov     rax, [rsp+0F8h+FileObject]
0x140003150  mov     rcx, [rax+28h]
0x140003154  mov     [rdx+28h], rcx
0x140003158  mov     rdx, [rbx+58h]
0x14000315c  mov     rax, [rsp+0F8h+FileObject]
0x140003164  mov     rcx, [rax+30h]
0x140003168  mov     [rdx+30h], rcx
0x14000316c  and     dword ptr [rbx-4], 0FFFFFFFBh
0x140003170  mov     rbx, [rbx]
0x140003173  jmp     loc_140003005
0x140003178  lock or dword ptr [rsi+110h], 1
0x140003180  xor     edi, edi
0x140003182  mov     rcx, [rsi+78h]
0x140003186  add     rcx, 38h ; '8'; Resource
0x14000318a  call    cs:__imp_ExReleaseResourceLite
0x140003191  nop     dword ptr [rax+rax+00h]
0x140003196  call    cs:__imp_KeLeaveCriticalRegion
0x14000319d  nop     dword ptr [rax+rax+00h]
0x1400031a2  mov     eax, edi
0x1400031a4  add     rsp, 0C8h
0x1400031ab  pop     r15
0x1400031ad  pop     r14
0x1400031af  pop     r12
0x1400031b1  pop     rdi
0x1400031b2  pop     rsi
0x1400031b3  pop     rbx
0x1400031b4  retn
0x14001471e  push    rbp
0x140014720  sub     rsp, 80h
0x140014727  mov     rbp, rdx
0x14001472a  add     rsp, 80h
0x140014731  pop     rbp
0x140014732  retn
```

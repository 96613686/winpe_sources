# VfsCreateParentDirectories

- ea: `0x14000fd38`
- end: `0x14001064d`
- name: `VfsCreateParentDirectories`
- size: `2325`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140002b4c`
- `0x1400046bc`
- `0x140005b48`
- `0x14000aefc`
- `0x14000be3c`
- `0x14000ca28`

## callees

- `0x1400022b4`
- `0x14000fd38`
- `0x14001187c`
- `0x140012acc`
- `0x14001322c`
- `0x140013294`
- `0x140013384`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140010188`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001051e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140010188`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001051e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000fe47`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000fe47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001057a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400105d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010619`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001565a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015698`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001057a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400105d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010619`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001565a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015698`
- `ntoskrnl!ExAllocatePool2` at `0x140010123`
- `ntoskrnl!ExAllocatePool2` at `0x14001048a`
- `ntoskrnl!ExAllocatePool2` at `0x140010123`
- `ntoskrnl!ExAllocatePool2` at `0x14001048a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001016c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400104d8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001016c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400104d8`
- `FLTMGR!FltCreateFile` at `0x14001004e`
- `FLTMGR!FltCreateFile` at `0x1400102de`
- `FLTMGR!FltCreateFile` at `0x14001004e`
- `FLTMGR!FltCreateFile` at `0x1400102de`
- `FLTMGR!FltClose` at `0x1400102f6`
- `FLTMGR!FltClose` at `0x140010317`
- `FLTMGR!FltClose` at `0x1400105fa`
- `FLTMGR!FltClose` at `0x14001567d`
- `FLTMGR!FltClose` at `0x1400102f6`
- `FLTMGR!FltClose` at `0x140010317`
- `FLTMGR!FltClose` at `0x1400105fa`
- `FLTMGR!FltClose` at `0x14001567d`

## string_xrefs

- `0x14000fe5a`: `VfsCreateParentDirectories() - Failed to create parent directories for store entry '%wZ' because the volume name did not match the COW mapping.`
- `0x14000ff15`: `VfsCreateParentDirectories() - Failed to create parent directories for store entry '%wZ' because it is not a child of the COW mapping.`
- `0x14001033c`: `VfsCreateParentDirectories() - Failed to create parent directory '%wZ'.\n Status: 0x%08X`
- `0x14001038e`: `VfsCreateParentDirectories() - Failed to determine the remaining path of new COW directory '%wZ' after component #%d.\n Status: 0x%08X`
- `0x1400105a5`: `VfsCreateParentDirectories() - Failed to copy to parent directory '%wZ' from package.\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateParentDirectories(
        struct _FLT_INSTANCE *a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int16 *a4,
        unsigned __int16 a5)
{
  bool v7; // si
  unsigned __int16 v8; // bx
  wchar_t *v9; // r8
  unsigned __int16 v10; // dx
  __int64 result; // rax
  unsigned __int16 v12; // ax
  __int16 v13; // cx
  int v14; // r8d
  int v15; // r9d
  char v16; // r12
  unsigned __int16 v17; // di
  NTSTATUS v18; // eax
  unsigned __int16 v19; // bx
  UNICODE_STRING *v20; // rax
  unsigned int v21; // edi
  int v22; // r12d
  bool v23; // cc
  char v24; // al
  NTSTATUS v25; // eax
  int RemainingPath; // eax
  int v27; // edi
  unsigned int v28; // esi
  unsigned __int16 Length; // ax
  int v30; // edi
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-198h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+28h] [rbp-190h]
  ULONG FileAttributes; // [rsp+38h] [rbp-180h]
  ULONG ShareAccess; // [rsp+40h] [rbp-178h]
  char v35; // [rsp+70h] [rbp-148h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-144h] BYREF
  unsigned __int16 v37; // [rsp+78h] [rbp-140h]
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-138h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-128h] BYREF
  char v40; // [rsp+98h] [rbp-120h]
  __int16 v41; // [rsp+9Ch] [rbp-11Ch]
  int v42; // [rsp+A0h] [rbp-118h]
  __int64 v43[3]; // [rsp+A8h] [rbp-110h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-F8h] BYREF
  UNICODE_STRING v45; // [rsp+D0h] [rbp-E8h] BYREF
  unsigned int v46; // [rsp+E0h] [rbp-D8h]
  UNICODE_STRING String2; // [rsp+E8h] [rbp-D0h] BYREF
  __m128i v48; // [rsp+100h] [rbp-B8h] BYREF
  UNICODE_STRING SourceString; // [rsp+110h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES v50; // [rsp+120h] [rbp-98h] BYREF
  int v51; // [rsp+150h] [rbp-68h]
  struct _IO_STATUS_BLOCK v52; // [rsp+158h] [rbp-60h] BYREF
  UNICODE_STRING Source; // [rsp+168h] [rbp-50h] BYREF
  UNICODE_STRING v54; // [rsp+180h] [rbp-38h] BYREF
  char v57; // [rsp+1E0h] [rbp+28h]

  String2 = 0;
  v7 = 0;
  v35 = 0;
  FileHandle = 0;
  memset(&v50, 0, sizeof(v50));
  v52 = 0;
  *(_OWORD *)v43 = 0;
  DestinationString = 0;
  v48 = 0;
  Destination = 0;
  LOBYTE(v36) = 0;
  if ( a5 < 4u )
    return 3221225485LL;
  if ( (unsigned __int16)*a4 <= a5 )
    return 3221225485LL;
  v8 = a5 >> 1;
  v9 = (wchar_t *)*((_QWORD *)a4 + 1);
  if ( v9[a5 >> 1] != 92 )
    return 3221225485LL;
  v10 = ((unsigned __int16)*a4 >> 1) - 1;
  if ( v10 == v8 )
    return 0;
  v12 = ((unsigned __int16)*a4 >> 1) - 2;
  if ( v9[v10] != 92 )
    v12 = ((unsigned __int16)*a4 >> 1) - 1;
  v37 = v12;
  String2.Buffer = v9;
  String2.Length = a5;
  String2.MaximumLength = a5;
  if ( RtlCompareUnicodeString((PCUNICODE_STRING)(a3 + 24), &String2, 1u) )
  {
    LogWrite(
      1,
      0,
      L"VfsCreateParentDirectories() - Failed to create parent directories for store entry '%wZ' because the volume name d"
       "id not match the COW mapping.",
      a4);
    return 3221225490LL;
  }
  *(_DWORD *)(&v45.MaximumLength + 1) = 0;
  v13 = *a4;
  if ( a5 < (unsigned __int16)*a4 )
  {
    v45.Buffer = (wchar_t *)(*((_QWORD *)a4 + 1) + a5);
    v45.Length = v13 - a5;
    v45.MaximumLength = v13 - a5;
  }
  else
  {
    v45.Buffer = 0;
    *(_DWORD *)&v45.Length = 0;
  }
  SourceString = v45;
  result = IsProcessElevated(&v36);
  if ( (int)result >= 0 )
  {
    if ( !(_BYTE)v36 || (LOBYTE(v15) = 1, (*(_DWORD *)(a3 + 4) & 2) == 0) )
      LOBYTE(v15) = 0;
    IoStatusBlock = (PIO_STATUS_BLOCK)&v35;
    LOBYTE(v14) = 1;
    if ( !(unsigned __int8)MappingPrefixFileName((int)a3 + 40, (unsigned int)&SourceString, v14, v15) )
    {
      LogWrite(
        1,
        0,
        L"VfsCreateParentDirectories() - Failed to create parent directories for store entry '%wZ' because it is not a chi"
         "ld of the COW mapping.",
        a4);
      return 3221225530LL;
    }
    v16 = 0;
    v57 = 0;
    LOWORD(v36) = *(_WORD *)(*(_QWORD *)(a3 + 56) + 16LL) + GetNumberComponents(&String2);
    v17 = v37;
    if ( v37 <= v8 )
      goto LABEL_26;
    while ( 1 )
    {
      if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2LL * v17) == 92 )
      {
        if ( v7 )
        {
          v7 = 0;
        }
        else
        {
          v43[1] = *((_QWORD *)a4 + 1);
          LOWORD(v43[0]) = 2 * v17;
          WORD1(v43[0]) = 2 * v17;
          v50.Length = 48;
          v50.RootDirectory = 0;
          v50.Attributes = 576;
          v50.ObjectName = (PUNICODE_STRING)v43;
          *(_OWORD *)&v50.SecurityDescriptor = 0;
          v18 = FltCreateFile(VfsData, a2, &FileHandle, 0x100000u, &v50, &v52, 0, 0x80u, 7u, 1u, 0x21u, 0, 0, 0x900u);
          if ( v18 >= 0 )
          {
            FltClose(FileHandle);
            FileHandle = 0;
            v16 = 1;
LABEL_26:
            if ( v16 )
              v8 = LOWORD(v43[0]) >> 1;
            v19 = v8 + 1;
            DestinationString.Buffer = 0;
            DestinationString.Length = 0;
            DestinationString.MaximumLength = 0;
            if ( v35 )
            {
LABEL_34:
              v41 = v19;
              v22 = (unsigned __int16)v36;
              while ( v19 <= v37 )
              {
                if ( *(_WORD *)(*((_QWORD *)a4 + 1) + 2LL * v19) == 92 )
                {
                  v43[1] = *((_QWORD *)a4 + 1);
                  LOWORD(v43[0]) = 2 * v19;
                  WORD1(v43[0]) = 2 * v19;
                  if ( v57 )
                    goto LABEL_46;
                  if ( v35 || (v23 = (unsigned __int16)GetNumberComponents(v43) <= (unsigned __int16)v22, v24 = 1, v23) )
                    v24 = 0;
                  v57 = v24;
                  v40 = v24;
                  if ( v24 )
                  {
LABEL_46:
                    RemainingPath = GetRemainingPath(v43, (unsigned __int16)v22, &v48);
                    if ( RemainingPath >= 0 )
                    {
                      v36 = 0;
                      v42 = 0;
                      v45 = DestinationString;
                      v54 = (UNICODE_STRING)v48;
                      v27 = DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] == 92;
                      v42 = v27;
                      if ( *(_WORD *)_mm_srli_si128(v48, 8).m128i_i16[0] == 92 )
                        v42 = ++v27;
                      if ( v27 == 2 )
                      {
                        v45.Length = DestinationString.Length - 2;
                        v27 = 1;
                        v42 = 1;
                      }
                      if ( v27 )
                        v28 = v45.Length + v48.m128i_u16[0];
                      else
                        v28 = v48.m128i_u16[0] + v45.Length + 2;
                      v36 = v28;
                      if ( v28 <= 0xFFFE )
                      {
                        Destination.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v28, 1951614550);
                        if ( Destination.Buffer )
                        {
                          Destination.Length = 0;
                          Destination.MaximumLength = v28;
                          Length = v45.Length;
                          if ( v45.Length )
                          {
                            RtlCopyUnicodeString(&Destination, &v45);
                            Length = v45.Length;
                          }
                          if ( !v27 )
                          {
                            Destination.Buffer[(unsigned __int64)Length >> 1] = 92;
                            Destination.Length += 2;
                          }
                          RtlAppendUnicodeStringToString(&Destination, &v54);
                          v30 = VfsCopyFile(a1, 0, (__int64)v43, 1, FileAttributes, ShareAccess, 1, 0);
                          if ( Destination.Buffer )
                          {
                            ExFreePoolWithTag(Destination.Buffer, 0);
                            Destination.Buffer = 0;
                          }
                          Destination.Buffer = 0;
                          *(_DWORD *)&Destination.Length = 0;
                          if ( v30 < 0 )
                          {
                            LODWORD(ObjectAttributes) = v30;
                            LogWrite(
                              1,
                              0,
                              L"VfsCreateParentDirectories() - Failed to copy to parent directory '%wZ' from package.\n"
                               " Status: 0x%08X",
                              v43,
                              ObjectAttributes);
                          }
                        }
                      }
                    }
                    else
                    {
                      LODWORD(IoStatusBlock) = RemainingPath;
                      LODWORD(ObjectAttributes) = v22;
                      LogWrite(
                        1,
                        0,
                        L"VfsCreateParentDirectories() - Failed to determine the remaining path of new COW directory '%wZ'"
                         " after component #%d.\n"
                         " Status: 0x%08X",
                        v43,
                        ObjectAttributes,
                        IoStatusBlock);
                    }
                  }
                  else
                  {
                    v50.Length = 48;
                    v50.RootDirectory = 0;
                    v50.Attributes = 576;
                    v50.ObjectName = (PUNICODE_STRING)v43;
                    *(_OWORD *)&v50.SecurityDescriptor = 0;
                    v25 = FltCreateFile(
                            VfsData,
                            a2,
                            &FileHandle,
                            0x100000u,
                            &v50,
                            &v52,
                            0,
                            0x80u,
                            7u,
                            2u,
                            0x21u,
                            0,
                            0,
                            0x900u);
                    if ( v25 < 0 )
                    {
                      LODWORD(ObjectAttributes) = v25;
                      LogWrite(
                        1,
                        0,
                        L"VfsCreateParentDirectories() - Failed to create parent directory '%wZ'.\n Status: 0x%08X",
                        v43,
                        ObjectAttributes);
                    }
                    else
                    {
                      FltClose(FileHandle);
                      FileHandle = 0;
                    }
                  }
                }
                v41 = ++v19;
              }
            }
            else
            {
              v20 = *(UNICODE_STRING **)(a3 + 40);
              v46 = 0;
              v51 = 0;
              SourceString = *(UNICODE_STRING *)(a3 + 8);
              Source = *v20;
              v21 = (unsigned __int16)_mm_cvtsi128_si32((__m128i)SourceString)
                  + (unsigned __int16)_mm_cvtsi128_si32((__m128i)Source);
              v46 = v21;
              if ( v21 <= 0xFFFE )
              {
                DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v21, 1951614550);
                if ( DestinationString.Buffer )
                {
                  DestinationString.Length = 0;
                  DestinationString.MaximumLength = v21;
                  if ( SourceString.Length )
                    RtlCopyUnicodeString(&DestinationString, &SourceString);
                  RtlAppendUnicodeStringToString(&DestinationString, &Source);
                  goto LABEL_34;
                }
              }
            }
            if ( Destination.Buffer )
            {
              ExFreePoolWithTag(Destination.Buffer, 0);
              Destination.Buffer = 0;
            }
            if ( FileHandle )
              FltClose(FileHandle);
            if ( DestinationString.Buffer )
              ExFreePoolWithTag(DestinationString.Buffer, 0);
            return 0;
          }
          v7 = v18 == -1073741766;
        }
      }
      if ( --v17 <= v8 )
        goto LABEL_26;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000fd38  mov     rax, rsp
0x14000fd3b  mov     [rax+18h], rbx
0x14000fd3f  mov     [rax+20h], rsi
0x14000fd43  mov     [rax+10h], rdx
0x14000fd47  mov     [rax+8], rcx
0x14000fd4b  push    rdi
0x14000fd4c  push    r12
0x14000fd4e  push    r13
0x14000fd50  push    r14
0x14000fd52  push    r15
0x14000fd54  sub     rsp, 190h
0x14000fd5b  mov     r14, r9
0x14000fd5e  mov     r15, r8
0x14000fd61  xorps   xmm0, xmm0
0x14000fd64  movups  xmmword ptr [rax-0D0h], xmm0
0x14000fd6b  xor     esi, esi
0x14000fd6d  mov     [rsp+1B8h+var_148], sil
0x14000fd72  mov     [rax-128h], rsi
0x14000fd79  movups  xmmword ptr [rax-98h], xmm0
0x14000fd80  movups  xmmword ptr [rax-88h], xmm0
0x14000fd87  movups  xmmword ptr [rax-78h], xmm0
0x14000fd8b  movups  xmmword ptr [rax-60h], xmm0
0x14000fd8f  xorps   xmm1, xmm1
0x14000fd92  movups  xmmword ptr [rax-110h], xmm1
0x14000fd99  movups  xmmword ptr [rax-0F8h], xmm0
0x14000fda0  movups  xmmword ptr [rax-0B8h], xmm1
0x14000fda7  movups  xmmword ptr [rax-138h], xmm0
0x14000fdae  mov     byte ptr [rsp+1B8h+var_144], sil
0x14000fdb3  movzx   edi, [rsp+1B8h+arg_20]
0x14000fdbb  cmp     edi, 4
0x14000fdbe  jb      loc_14001062A
0x14000fdc4  movzx   edx, word ptr [r9]
0x14000fdc8  cmp     dx, di
0x14000fdcb  jbe     loc_14001062A
0x14000fdd1  movzx   ebx, di
0x14000fdd4  shr     bx, 1
0x14000fdd7  mov     r8, [r9+8]
0x14000fddb  movzx   eax, bx
0x14000fdde  lea     r9d, [rsi+5Ch]
0x14000fde2  cmp     [r8+rax*2], r9w
0x14000fde7  jnz     loc_14001062A
0x14000fded  shr     dx, 1
0x14000fdf0  lea     r12d, [rsi+1]
0x14000fdf4  sub     dx, r12w
0x14000fdf8  cmp     dx, bx
0x14000fdfb  jnz     short loc_14000FE04
0x14000fdfd  xor     eax, eax
0x14000fdff  jmp     loc_14001062F
0x14000fe04  movzx   eax, dx
0x14000fe07  movzx   ecx, word ptr [r8+rax*2]
0x14000fe0c  movzx   eax, dx
0x14000fe0f  sub     ax, r12w
0x14000fe13  cmp     cx, r9w
0x14000fe17  cmovnz  ax, dx
0x14000fe1b  mov     [rsp+1B8h+var_140], ax
0x14000fe20  mov     [rsp+1B8h+String2.Buffer], r8
0x14000fe28  mov     [rsp+1B8h+String2.Length], di
0x14000fe30  mov     [rsp+1B8h+String2.MaximumLength], di
0x14000fe38  lea     rcx, [r15+18h]; String1
0x14000fe3c  mov     r8b, r12b; CaseInSensitive
0x14000fe3f  lea     rdx, [rsp+1B8h+String2]; String2
0x14000fe47  call    cs:__imp_RtlCompareUnicodeString
0x14000fe4e  nop     dword ptr [rax+rax+00h]
0x14000fe53  test    eax, eax
0x14000fe55  jz      short loc_14000FE75
0x14000fe57  mov     r9, r14
0x14000fe5a  lea     r8, aVfscreateparen_0; "VfsCreateParentDirectories() - Failed t"...
0x14000fe61  xor     edx, edx
0x14000fe63  mov     ecx, r12d
0x14000fe66  call    LogWrite
0x14000fe6b  mov     eax, 0C0000012h
0x14000fe70  jmp     loc_14001062F
0x14000fe75  mov     dword ptr [rsp+1B8h+var_E8+4], esi
0x14000fe7c  movzx   ecx, word ptr [r14]
0x14000fe80  cmp     di, cx
0x14000fe83  jb      short loc_14000FE96
0x14000fe85  mov     [rsp+1B8h+var_E8.Buffer], rsi
0x14000fe8d  mov     dword ptr [rsp+1B8h+var_E8.Length], esi
0x14000fe94  jmp     short loc_14000FEB8
0x14000fe96  mov     rax, rdi
0x14000fe99  add     rax, [r14+8]
0x14000fe9d  mov     [rsp+1B8h+var_E8.Buffer], rax
0x14000fea5  sub     cx, di
0x14000fea8  mov     [rsp+1B8h+var_E8.Length], cx
0x14000feb0  mov     [rsp+1B8h+var_E8.MaximumLength], cx
0x14000feb8  movaps  xmm0, xmmword ptr [rsp+1B8h+var_E8.Length]
0x14000fec0  movdqa  xmmword ptr [rsp+1B8h+SourceString.Length], xmm0
0x14000fec9  lea     rcx, [rsp+1B8h+var_144]
0x14000fece  call    IsProcessElevated
0x14000fed3  test    eax, eax
0x14000fed5  js      loc_14001062F
0x14000fedb  cmp     byte ptr [rsp+1B8h+var_144], sil
0x14000fee0  jz      short loc_14000FEED
0x14000fee2  mov     eax, [r15+4]
0x14000fee6  test    al, 2
0x14000fee8  mov     r9b, r12b
0x14000feeb  jnz     short loc_14000FEF0
0x14000feed  mov     r9b, sil
0x14000fef0  lea     rax, [rsp+1B8h+var_148]
0x14000fef5  mov     [rsp+1B8h+IoStatusBlock], rax
0x14000fefa  mov     r8b, r12b
0x14000fefd  lea     rdx, [rsp+1B8h+SourceString]
0x14000ff05  lea     rcx, [r15+28h]
0x14000ff09  call    MappingPrefixFileName
0x14000ff0e  test    al, al
0x14000ff10  jnz     short loc_14000FF30
0x14000ff12  mov     r9, r14
0x14000ff15  lea     r8, aVfscreateparen_1; "VfsCreateParentDirectories() - Failed t"...
0x14000ff1c  xor     edx, edx
0x14000ff1e  mov     ecx, r12d
0x14000ff21  call    LogWrite
0x14000ff26  mov     eax, 0C000003Ah
0x14000ff2b  jmp     loc_14001062F
0x14000ff30  mov     r12b, sil
0x14000ff33  xor     ecx, ecx
0x14000ff35  mov     byte ptr [rsp+1B8h+arg_20], cl
0x14000ff3c  lea     rcx, [rsp+1B8h+String2]
0x14000ff44  call    GetNumberComponents
0x14000ff49  mov     rcx, [r15+38h]
0x14000ff4d  add     ax, [rcx+10h]
0x14000ff51  mov     word ptr [rsp+1B8h+var_144], ax
0x14000ff56  movzx   edi, [rsp+1B8h+var_140]
0x14000ff5b  cmp     di, bx
0x14000ff5e  jbe     loc_14001008B
0x14000ff64  mov     edx, 5Ch ; '\'
0x14000ff69  mov     rcx, [r14+8]
0x14000ff6d  movzx   eax, di
0x14000ff70  cmp     [rcx+rax*2], dx
0x14000ff74  jnz     loc_140010078
0x14000ff7a  xor     edx, edx
0x14000ff7c  test    sil, sil
0x14000ff7f  jz      short loc_14000FF89
0x14000ff81  mov     sil, dl
0x14000ff84  jmp     loc_140010073
0x14000ff89  mov     [rsp+1B8h+var_108], rcx
0x14000ff91  movzx   eax, di
0x14000ff94  add     ax, ax
0x14000ff97  mov     word ptr [rsp+1B8h+var_110], ax
0x14000ff9f  mov     word ptr [rsp+1B8h+var_110+2], ax
0x14000ffa7  mov     [rsp+1B8h+var_98.Length], 30h ; '0'
0x14000ffb2  mov     [rsp+1B8h+var_98.RootDirectory], rdx
0x14000ffba  mov     [rsp+1B8h+var_98.Attributes], 240h
0x14000ffc5  lea     rax, [rsp+1B8h+var_110]
0x14000ffcd  mov     [rsp+1B8h+var_98.ObjectName], rax
0x14000ffd5  xorps   xmm0, xmm0
0x14000ffd8  movdqu  xmmword ptr [rsp+1B8h+var_98.SecurityDescriptor], xmm0
0x14000ffe1  mov     [rsp+1B8h+Flags], 900h; Flags
0x14000ffe9  mov     [rsp+1B8h+EaLength], edx; EaLength
0x14000ffed  mov     [rsp+1B8h+EaBuffer], rdx; EaBuffer
0x14000fff2  mov     [rsp+1B8h+CreateOptions], 21h ; '!'; CreateOptions
0x14000fffa  mov     [rsp+1B8h+CreateDisposition], 1; CreateDisposition
0x140010002  mov     [rsp+1B8h+ShareAccess], 7; int
0x14001000a  mov     [rsp+1B8h+FileAttributes], 80h; int
0x140010012  mov     [rsp+1B8h+AllocationSize], rdx; AllocationSize
0x140010017  lea     rax, [rsp+1B8h+var_60]
0x14001001f  mov     [rsp+1B8h+IoStatusBlock], rax; IoStatusBlock
0x140010024  lea     rax, [rsp+1B8h+var_98]
0x14001002c  mov     [rsp+1B8h+ObjectAttributes], rax; ObjectAttributes
0x140010031  mov     r9d, 100000h; DesiredAccess
0x140010037  lea     r8, [rsp+1B8h+FileHandle]; FileHandle
0x14001003f  mov     rdx, [rsp+1B8h+Instance]; Instance
0x140010047  mov     rcx, cs:VfsData; Filter
0x14001004e  call    cs:__imp_FltCreateFile
0x140010055  nop     dword ptr [rax+rax+00h]
0x14001005a  test    eax, eax
0x14001005c  jns     loc_14001030F
0x140010062  movzx   esi, sil
0x140010066  cmp     eax, 0C000003Ah
0x14001006b  mov     eax, 1
0x140010070  cmovz   esi, eax
0x140010073  mov     edx, 5Ch ; '\'
0x140010078  mov     eax, 0FFFFh
0x14001007d  add     di, ax
0x140010080  cmp     di, bx
0x140010083  ja      loc_14000FF69
0x140010089  xor     esi, esi
0x14001008b  mov     eax, 1
0x140010090  test    r12b, r12b
0x140010093  jz      short loc_1400100A0
0x140010095  movzx   ebx, word ptr [rsp+1B8h+var_110]
0x14001009d  shr     bx, 1
0x1400100a0  add     bx, ax
0x1400100a3  mov     [rsp+1B8h+DestinationString.Buffer], rsi
0x1400100ab  mov     [rsp+1B8h+DestinationString.Length], si
0x1400100b3  mov     eax, esi
0x1400100b5  mov     [rsp+1B8h+DestinationString.MaximumLength], ax
0x1400100bd  cmp     [rsp+1B8h+var_148], sil
0x1400100c2  jnz     loc_140010194
0x1400100c8  mov     rax, [r15+28h]
0x1400100cc  mov     [rsp+1B8h+var_D8], esi
0x1400100d3  mov     [rsp+1B8h+var_68], esi
0x1400100da  movups  xmm1, xmmword ptr [r15+8]
0x1400100df  movups  xmmword ptr [rsp+1B8h+SourceString.Length], xmm1
0x1400100e7  movups  xmm0, xmmword ptr [rax]
0x1400100ea  movups  xmmword ptr [rsp+1B8h+Source.Length], xmm0
0x1400100f2  movd    eax, xmm0
0x1400100f6  movzx   edi, ax
0x1400100f9  movd    eax, xmm1
0x1400100fd  movzx   eax, ax
0x140010100  add     edi, eax
0x140010102  mov     [rsp+1B8h+var_D8], edi
0x140010109  cmp     edi, 0FFFEh
0x14001010f  ja      loc_1400105CA
0x140010115  movzx   edx, di
0x140010118  mov     ecx, 100h
0x14001011d  mov     r8d, 74534656h
0x140010123  call    cs:__imp_ExAllocatePool2
0x14001012a  nop     dword ptr [rax+rax+00h]
0x14001012f  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x140010137  test    rax, rax
0x14001013a  jz      loc_1400105CA
0x140010140  mov     eax, esi
0x140010142  mov     [rsp+1B8h+DestinationString.Length], ax
0x14001014a  mov     [rsp+1B8h+DestinationString.MaximumLength], di
0x140010152  cmp     [rsp+1B8h+SourceString.Length], si
0x14001015a  jz      short loc_140010178
0x14001015c  lea     rdx, [rsp+1B8h+SourceString]; SourceString
0x140010164  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x14001016c  call    cs:__imp_RtlCopyUnicodeString
0x140010173  nop     dword ptr [rax+rax+00h]
0x140010178  lea     rdx, [rsp+1B8h+Source]; Source
0x140010180  lea     rcx, [rsp+1B8h+DestinationString]; Destination
0x140010188  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001018f  nop     dword ptr [rax+rax+00h]
0x140010194  mov     [rsp+1B8h+var_11C], bx
0x14001019c  movzx   r12d, word ptr [rsp+1B8h+var_144]
0x1400101a2  mov     r13, [rsp+1B8h+arg_0]
0x1400101aa  mov     r15d, 1
0x1400101b0  cmp     bx, [rsp+1B8h+var_140]
0x1400101b5  ja      loc_1400105CA
0x1400101bb  mov     rcx, [r14+8]
0x1400101bf  movzx   eax, bx
0x1400101c2  mov     edx, 5Ch ; '\'
0x1400101c7  cmp     [rcx+rax*2], dx
0x1400101cb  jnz     loc_1400105B9
0x1400101d1  mov     [rsp+1B8h+var_108], rcx
0x1400101d9  movzx   eax, bx
0x1400101dc  add     ax, ax
0x1400101df  mov     word ptr [rsp+1B8h+var_110], ax
0x1400101e7  mov     word ptr [rsp+1B8h+var_110+2], ax
0x1400101ef  mov     al, byte ptr [rsp+1B8h+arg_20]
0x1400101f6  test    al, al
0x1400101f8  jnz     loc_140010360
0x1400101fe  cmp     [rsp+1B8h+var_148], sil
0x140010203  jnz     short loc_14001021B
0x140010205  lea     rcx, [rsp+1B8h+var_110]
0x14001020d  call    GetNumberComponents
0x140010212  cmp     ax, r12w
0x140010216  mov     al, r15b
0x140010219  ja      short loc_14001021E
0x14001021b  mov     al, sil
0x14001021e  mov     byte ptr [rsp+1B8h+arg_20], al
0x140010225  mov     [rsp+1B8h+var_120], al
0x14001022c  test    al, al
0x14001022e  jnz     loc_140010360
0x140010234  mov     [rsp+1B8h+var_98.Length], 30h ; '0'
0x14001023f  mov     [rsp+1B8h+var_98.RootDirectory], rsi
0x140010247  mov     [rsp+1B8h+var_98.Attributes], 240h
0x140010252  lea     rax, [rsp+1B8h+var_110]
0x14001025a  mov     [rsp+1B8h+var_98.ObjectName], rax
0x140010262  xorps   xmm0, xmm0
0x140010265  movdqu  xmmword ptr [rsp+1B8h+var_98.SecurityDescriptor], xmm0
0x14001026e  mov     [rsp+1B8h+Flags], 900h; Flags
0x140010276  mov     [rsp+1B8h+EaLength], esi; EaLength
0x14001027a  mov     [rsp+1B8h+EaBuffer], rsi; EaBuffer
0x14001027f  mov     [rsp+1B8h+CreateOptions], 21h ; '!'; CreateOptions
0x140010287  mov     r15d, 2
0x14001028d  mov     [rsp+1B8h+CreateDisposition], r15d; CreateDisposition
0x140010292  mov     [rsp+1B8h+ShareAccess], 7; ShareAccess
0x14001029a  mov     [rsp+1B8h+FileAttributes], 80h; FileAttributes
0x1400102a2  mov     [rsp+1B8h+AllocationSize], rsi; AllocationSize
0x1400102a7  lea     rax, [rsp+1B8h+var_60]
0x1400102af  mov     [rsp+1B8h+IoStatusBlock], rax; IoStatusBlock
0x1400102b4  lea     rax, [rsp+1B8h+var_98]
0x1400102bc  mov     [rsp+1B8h+ObjectAttributes], rax; ObjectAttributes
0x1400102c1  mov     r9d, 100000h; DesiredAccess
0x1400102c7  lea     r8, [rsp+1B8h+FileHandle]; FileHandle
0x1400102cf  mov     rdx, [rsp+1B8h+Instance]; Instance
0x1400102d7  mov     rcx, cs:VfsData; Filter
0x1400102de  call    cs:__imp_FltCreateFile
0x1400102e5  nop     dword ptr [rax+rax+00h]
0x1400102ea  test    eax, eax
0x1400102ec  js      short loc_140010338
0x1400102ee  mov     rcx, [rsp+1B8h+FileHandle]; FileHandle
0x1400102f6  call    cs:__imp_FltClose
0x1400102fd  nop     dword ptr [rax+rax+00h]
0x140010302  mov     [rsp+1B8h+FileHandle], rsi
0x14001030a  jmp     loc_1400105B3
0x14001030f  mov     rcx, [rsp+1B8h+FileHandle]; FileHandle
0x140010317  call    cs:__imp_FltClose
0x14001031e  nop     dword ptr [rax+rax+00h]
0x140010323  xor     esi, esi
0x140010325  mov     [rsp+1B8h+FileHandle], rsi
0x14001032d  lea     eax, [rsi+1]
0x140010330  mov     r12b, al
0x140010333  jmp     loc_140010090
0x140010338  mov     dword ptr [rsp+1B8h+ObjectAttributes], eax
0x14001033c  lea     r8, aVfscreateparen; "VfsCreateParentDirectories() - Failed t"...
0x140010343  mov     r15d, 1
0x140010349  xor     edx, edx
  ... truncated ...
```

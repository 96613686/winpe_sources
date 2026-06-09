# AslPathWildcardFindNext

- ea: `0x18001d030`
- end: `0x18001da09`
- name: `AslPathWildcardFindNext`
- size: `2521`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001cac8`
- `0x1801b73d0`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18001a2f4`
- `0x18001d030`
- `0x18001dbd8`
- `0x18001e0d8`
- `0x1802174f0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001d637`
- `ntdll!RtlFreeUnicodeString` at `0x18001d637`
- `ntdll!RtlFreeHeap` at `0x18001d613`
- `ntdll!RtlFreeHeap` at `0x18001d613`
- `ntdll!RtlAllocateHeap` at `0x18001d0cf`
- `ntdll!RtlAllocateHeap` at `0x18001d0cf`
- `ntdll!ZwQueryDirectoryFile` at `0x18001d38f`
- `ntdll!ZwQueryDirectoryFile` at `0x18001d38f`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d6f8`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d754`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d800`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d8a1`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d6f8`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d754`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d800`
- `ntdll!RtlpEnsureBufferSize` at `0x18001d8a1`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001d925`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001d925`
- `ntdll!RtlInitUnicodeString` at `0x18001d34c`
- `ntdll!RtlInitUnicodeString` at `0x18001d34c`
- `KERNEL32!HeapReAlloc` at `0x18001d2db`
- `KERNEL32!HeapReAlloc` at `0x18001d526`
- `KERNEL32!HeapReAlloc` at `0x18001d2db`
- `KERNEL32!HeapReAlloc` at `0x18001d526`
- `KERNEL32!HeapAlloc` at `0x18001d2bb`
- `KERNEL32!HeapAlloc` at `0x18001d506`
- `KERNEL32!HeapAlloc` at `0x18001d2bb`
- `KERNEL32!HeapAlloc` at `0x18001d506`

## string_xrefs

- `0x18001d307`: `AslpPathWildcardPeekNode`
- `0x18001d9c8`: `AslpPathWildcardPeekNode`
- `0x18001d31d`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18001d9d9`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18001d32e`: `AslpPathWildcardPopNode`
- `0x18001d9a1`: `RtlStringCbCopyNW failed [%x]`
- `0x18001d67c`: `AslpPathWildcardPushNode failed [%x]`
- `0x18001d14f`: `AslPathWildcardFindNext`
- `0x18001d3b8`: `AslPathWildcardFindNext`
- `0x18001d3d9`: `AslPathWildcardFindNext`
- `0x18001d5d8`: `AslPathWildcardFindNext`
- `0x18001d68d`: `AslPathWildcardFindNext`
- `0x18001d9ee`: `AslPathWildcardFindNext`
- `0x18001d3a7`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x18001d3cd`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x18001d599`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x18001d5cb`: `Failed to compute the path length [%x]`
- `0x18001d931`: `RtlNtPathNameToDosPathName failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(_WORD *a1, __int64 a2, __int64 a3)
{
  _WORD *v4; // r12
  char *FileInformation; // r13
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  unsigned __int64 v11; // rcx
  unsigned __int16 *v12; // rbx
  int v13; // ebx
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  __int64 v17; // r10
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // kr40_8
  unsigned __int64 v23; // rsi
  unsigned __int128 v24; // rax
  unsigned __int64 v25; // kr50_8
  void *v26; // r8
  void *v27; // rcx
  void *v28; // rax
  LPVOID v29; // rbx
  NTSTATUS v30; // eax
  __int64 v31; // rax
  PWSTR Buffer; // rsi
  bool v33; // zf
  int matched; // eax
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // rcx
  __int64 v37; // rsi
  unsigned __int128 v38; // rax
  unsigned __int64 v39; // kr60_8
  unsigned __int64 v40; // kr70_8
  unsigned __int64 v41; // rsi
  unsigned __int128 v42; // rax
  unsigned __int64 v43; // kr80_8
  size_t v44; // r14
  void *v45; // r8
  void *v46; // rcx
  void *v47; // rax
  LPVOID v48; // rbx
  _OWORD *v49; // rax
  NTSTATUS v50; // eax
  unsigned __int16 v51; // ax
  PUCHAR StaticBuffer; // rcx
  const char *v53; // r9
  __int64 v54; // r8
  SIZE_T Size; // rdx
  WCHAR *p_ReservedForAllocatedSize; // rcx
  SIZE_T v57; // r8
  USHORT Length; // r9
  SIZE_T v59; // r8
  USHORT v60; // cx
  unsigned __int64 v61; // r8
  USHORT v62; // ax
  USHORT v63; // r9
  USHORT v64; // dx
  unsigned __int64 v65; // r8
  unsigned __int64 v66; // rdx
  __int64 v67; // rdx
  PWSTR v68; // rcx
  unsigned __int64 v69; // rax
  _WORD *v70; // rcx
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-A9h]
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  __int128 v74; // [rsp+80h] [rbp-49h] BYREF
  __int128 v75; // [rsp+90h] [rbp-39h]
  struct _IO_STATUS_BLOCK v76; // [rsp+A0h] [rbp-29h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+B0h] [rbp-19h] BYREF

  v4 = a1;
  if ( a3 == -1 )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v76 = 0;
  DestinationString = 0;
  v74 = 0;
  v75 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v7 = -1073741801;
    goto LABEL_76;
  }
  v8 = *(_QWORD *)(a3 + 32);
  if ( !v8 )
  {
LABEL_74:
    v7 = -2147483642;
    goto LABEL_75;
  }
  while ( 1 )
  {
    v10 = *(_QWORD *)(a3 + 24);
    v9 = v10 * (v8 - 1);
    *(_QWORD *)&UnicodeString.Length = 0;
    if ( !is_mul_ok(v10, v8 - 1)
      || (v11 = *(_QWORD *)(a3 + 56), v12 = (unsigned __int16 *)(v11 + v9), v11 + v9 < v11)
      || !v12 )
    {
      AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
      AslLogCallPrintf(1, "AslPathWildcardFindNext", 2498, "AslpPathWildcardPeekNode failed [%x]", -1073741595);
      v7 = -1073741595;
      goto LABEL_75;
    }
    if ( *((_QWORD *)v12 + 3) )
      break;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2503, "Node on the stack with invalid handle.");
LABEL_39:
    v31 = *(_QWORD *)(a3 + 32);
    if ( v31 )
    {
      v14 = v31 - 1;
      *(_QWORD *)&UnicodeString.Length = 0;
      v15 = *(_QWORD *)(a3 + 24) * (v31 - 1);
      if ( is_mul_ok(*(_QWORD *)(a3 + 24), v14) )
      {
        v16 = *(_QWORD *)(a3 + 56);
        if ( v16 + v15 >= v16 )
        {
          if ( v16 + v15 )
          {
            AslpPathWildcardFreeMatchNode();
            v17 = *(_QWORD *)(a3 + 32);
            v18 = v17 - 1;
            if ( v17 )
            {
              *(_QWORD *)&UnicodeString.Length = 0;
              v19 = *(_QWORD *)(a3 + 24) * v18;
              if ( is_mul_ok(*(_QWORD *)(a3 + 24), v18) )
              {
                v20 = *(_QWORD *)(a3 + 56);
                if ( v20 + v19 >= v20 )
                {
                  memset_0((void *)(v20 + v19), 0, *(_QWORD *)(a3 + 24));
                  if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                  {
                    v21 = *(_QWORD *)(a3 + 40);
                    if ( *(_QWORD *)(a3 + 24) * v21 >= 0x400 && *(_QWORD *)(a3 + 32) < v21 >> 2 )
                    {
                      v22 = *(_QWORD *)(a3 + 24);
                      *(_QWORD *)&UnicodeString.Length = 0;
                      if ( is_mul_ok(v21, v22) )
                      {
                        v23 = v21 >> 1;
                        v25 = *(_QWORD *)(a3 + 24);
                        v24 = v23 * (unsigned __int128)v25;
                        *(_QWORD *)&UnicodeString.Length = 0;
                        if ( is_mul_ok(v23, v25) )
                        {
                          v26 = *(void **)(a3 + 56);
                          v27 = *(void **)(a3 + 16);
                          if ( v26 )
                          {
                            v29 = HeapReAlloc(v27, DWORD2(v24), v26, v24);
                          }
                          else
                          {
                            v28 = HeapAlloc(v27, DWORD2(v24), v24);
                            v29 = v28;
                            if ( v28 )
                              memset_0(v28, 0, v23 * v25);
                          }
                          if ( v29 )
                          {
                            *(_QWORD *)(a3 + 56) = v29;
                            *(_QWORD *)(a3 + 40) = v23;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_73;
          }
        }
      }
      v13 = -1073741595;
      AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
    }
    else
    {
      v13 = -2147483622;
    }
    AslLogCallPrintf(1, "AslpPathWildcardPopNode", 2106, "AslpPathWildcardPeekNode failed [%x]", v13);
LABEL_73:
    v8 = *(_QWORD *)(a3 + 32);
    if ( !v8 )
      goto LABEL_74;
  }
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v12 + 2));
  v30 = ZwQueryDirectoryFile(
          *((HANDLE *)v12 + 3),
          0,
          0,
          0,
          &v76,
          FileInformation,
          0x268u,
          FileBothDirectoryInformation,
          1u,
          &DestinationString,
          0);
  if ( v30 < 0 )
  {
    if ( v30 != -2147483642 && v30 != -1073741809 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindNext", 2527, "NtQueryDirectoryFile failed to query next file [%x]", v30);
      AslLogCallPrintf(
        2,
        "AslPathWildcardFindNext",
        2528,
        "FilePath: '%ws'  Pattern: '%ws'",
        *((_QWORD *)v12 + 1),
        DestinationString.Buffer);
    }
    goto LABEL_39;
  }
  Buffer = (PWSTR)(FileInformation + 94);
  if ( *((_DWORD *)FileInformation + 15) == 4 )
  {
    if ( *Buffer == 46 )
    {
      v33 = *((_WORD *)FileInformation + 48) == 46;
LABEL_46:
      if ( v33 )
        goto LABEL_73;
    }
  }
  else if ( *((_DWORD *)FileInformation + 15) == 2 )
  {
    Buffer = (PWSTR)(FileInformation + 94);
    v33 = *((_WORD *)FileInformation + 47) == 46;
    goto LABEL_46;
  }
  matched = AslpPathWildcardAllocMatchNode(
              (unsigned int)&v74,
              (_DWORD)v12,
              *((_QWORD *)v12 + 2),
              (*((_DWORD *)FileInformation + 14) >> 4) & 1,
              (__int64)Buffer,
              *((_WORD *)FileInformation + 30));
  if ( matched != -1073741197 )
  {
    if ( matched != -1073741565 && matched != -1073741638 )
    {
      if ( matched < 0 )
      {
        LODWORD(IoStatusBlock) = matched;
        AslLogCallPrintf(
          1,
          "AslPathWildcardFindNext",
          2585,
          "AslpPathWildcardAllocMatchNode failed [%x]",
          IoStatusBlock);
      }
      else
      {
        v35 = *(_QWORD *)(a3 + 32);
        if ( v35 >= *(_QWORD *)(a3 + 40) )
        {
          v36 = v35 + 1;
          if ( v35 + 1 <= *(_QWORD *)(a3 + 40) )
          {
            v7 = -2147024809;
            goto LABEL_68;
          }
          v37 = *(_QWORD *)(a3 + 48) - 1LL;
          if ( v37 + v36 < v36 )
            goto LABEL_67;
          v39 = *(_QWORD *)(a3 + 40);
          v40 = *(_QWORD *)(a3 + 24);
          v38 = v39 * (unsigned __int128)v40;
          *(_QWORD *)&UnicodeString.Length = 0;
          if ( !is_mul_ok(v39, v40)
            || (*(_QWORD *)&v38 = *(_QWORD *)(a3 + 24),
                v41 = (v37 + v36) & ~v37,
                *(_QWORD *)&UnicodeString.Length = *((_QWORD *)&v38 + 1),
                v43 = v38,
                v42 = v41 * (unsigned __int128)(unsigned __int64)v38,
                v44 = v42,
                !is_mul_ok(v41, v43)) )
          {
LABEL_67:
            v7 = -2147483637;
LABEL_68:
            v50 = v7;
LABEL_83:
            v53 = "AslpPathWildcardPushNode failed [%x]";
            v54 = 2577;
LABEL_84:
            LODWORD(IoStatusBlock) = v50;
            AslLogCallPrintf(1, "AslPathWildcardFindNext", v54, v53, IoStatusBlock);
            goto LABEL_75;
          }
          v45 = *(void **)(a3 + 56);
          v46 = *(void **)(a3 + 16);
          if ( v45 )
          {
            v48 = HeapReAlloc(v46, DWORD2(v42), v45, v42);
          }
          else
          {
            v47 = HeapAlloc(v46, DWORD2(v42), v42);
            v48 = v47;
            if ( v47 )
              memset_0(v47, 0, v44);
          }
          if ( !v48 )
          {
            v7 = -2147024882;
            goto LABEL_68;
          }
          *(_QWORD *)(a3 + 56) = v48;
          *(_QWORD *)(a3 + 40) = v41;
        }
        *(_QWORD *)&UnicodeString.Length = 0;
        if ( !is_mul_ok(*(_QWORD *)(a3 + 24), v35)
          || (v49 = (_OWORD *)(*(_QWORD *)(a3 + 56) + *(_QWORD *)(a3 + 24) * v35),
              (unsigned __int64)v49 < *(_QWORD *)(a3 + 56)) )
        {
          v50 = -2147483637;
          v7 = -2147483637;
          goto LABEL_83;
        }
        *v49 = v74;
        v49[1] = v75;
        ++*(_QWORD *)(a3 + 32);
      }
    }
    goto LABEL_73;
  }
  v51 = *((_WORD *)FileInformation + 30) + *v12;
  if ( v51 < *v12 || (unsigned __int16)(v51 + 2) < v51 )
  {
    LODWORD(IoStatusBlock) = -1073741675;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2629, "Failed to compute the path length [%x]", IoStatusBlock);
    goto LABEL_73;
  }
  Size = 2;
  Path.ByteBuffer.StaticSize = 2;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  v57 = (unsigned __int16)(v51 + 2) + 2LL;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Size = 2;
  LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
  Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
  *(_DWORD *)&Path.String.Length = 0x20000;
  if ( v57 > 0xFFFE )
  {
    v7 = -1073741562;
LABEL_90:
    LODWORD(IoStatusBlock) = v7;
    AslLogCallPrintf(
      1,
      "AslPathWildcardFindNext",
      2638,
      "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]",
      IoStatusBlock);
    goto LABEL_75;
  }
  if ( v57 > 2 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v57) < 0 )
    {
      v7 = -1073741801;
      goto LABEL_90;
    }
    Size = Path.ByteBuffer.Size;
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  Length = 0;
  Path.String.MaximumLength = Size;
  Path.String.Length = 0;
  v59 = *v12 + 2LL;
  if ( v59 > 0xFFFE )
  {
    v7 = -1073741562;
LABEL_97:
    LODWORD(IoStatusBlock) = v7;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2648, "RtlAssignUnicodeStringBuffer failed [%x]", IoStatusBlock);
    goto LABEL_75;
  }
  if ( v59 > Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v59) < 0 )
    {
      v7 = -1073741801;
      goto LABEL_97;
    }
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v12 + 1), *v12);
  Path.String.MaximumLength = *v12 + Path.String.Length + 2;
  Path.String.Length += *v12;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  if ( *(_WORD *)(*((_QWORD *)v12 + 1) + 2 * ((unsigned __int64)*v12 >> 1) - 2) != 92 )
  {
    v60 = Path.String.Length;
    v61 = (unsigned int)Path.String.Length + 2 + 2LL;
    if ( v61 > 0xFFFE )
    {
      v7 = -1073741562;
LABEL_105:
      LODWORD(IoStatusBlock) = v7;
      AslLogCallPrintf(1, "AslPathWildcardFindNext", 2655, "RtlAppendUnicodeStringBuffer failed [%x]", IoStatusBlock);
      goto LABEL_75;
    }
    if ( v61 > Path.ByteBuffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v61) < 0 )
      {
        v7 = -1073741801;
        goto LABEL_105;
      }
      v60 = Path.String.Length;
    }
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v60 >> 1)] = SubBlock[0];
    v62 = Path.String.Length + 4;
    Path.String.Length += 2;
    Path.String.MaximumLength = v62;
    Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  }
  v63 = Path.String.Length;
  DestinationString.Buffer = Buffer;
  DestinationString.Length = *((_WORD *)FileInformation + 30);
  v64 = DestinationString.Length;
  DestinationString.MaximumLength = *((_WORD *)FileInformation + 30);
  v65 = Path.String.Length + (unsigned int)DestinationString.Length + 2LL;
  if ( v65 > 0xFFFE )
  {
    v7 = -1073741562;
LABEL_113:
    LODWORD(IoStatusBlock) = v7;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2670, "RtlAppendUnicodeStringBuffer failed [%x]", IoStatusBlock);
    goto LABEL_75;
  }
  if ( v65 > Path.ByteBuffer.Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v65) < 0 )
    {
      v7 = -1073741801;
      goto LABEL_113;
    }
    Buffer = DestinationString.Buffer;
    v64 = DestinationString.Length;
    v63 = Path.String.Length;
  }
  Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
  memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v63 >> 1)], Buffer, v64);
  v66 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
  Path.String.Length = v66;
  Path.String.MaximumLength = v66 + 2;
  Path.String.Buffer[v66 >> 1] = 0;
  if ( *(_DWORD *)a3 )
  {
    v50 = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
    v7 = v50;
    if ( v50 < 0 )
    {
      v53 = "RtlNtPathNameToDosPathName failed [%x]";
      v54 = 2681;
      goto LABEL_84;
    }
  }
  v67 = 260;
  v68 = Path.String.Buffer;
  v69 = (unsigned __int64)Path.String.Length >> 1;
  do
  {
    if ( !v69 )
      break;
    if ( !*v68 )
      break;
    *v4++ = *v68++;
    --v69;
    --v67;
  }
  while ( v67 );
  v70 = v4 - 1;
  v7 = v67 == 0 ? 0x80000005 : 0;
  if ( v67 )
    v70 = v4;
  *v70 = 0;
  if ( v67 )
  {
    v7 = 0;
  }
  else
  {
    LODWORD(IoStatusBlock) = -2147483643;
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2692, "RtlStringCbCopyNW failed [%x]", IoStatusBlock);
  }
LABEL_75:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, FileInformation);
LABEL_76:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer && Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
  {
    *(_QWORD *)&UnicodeString.Length = 0;
    UnicodeString.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    RtlFreeUnicodeString(&UnicodeString);
    StaticBuffer = Path.ByteBuffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return v7;
}

```

## disassembly

```asm
0x18001d030  mov     [rsp-8+arg_8], rbx
0x18001d035  push    rbp
0x18001d036  push    rsi
0x18001d037  push    rdi
0x18001d038  push    r12
0x18001d03a  push    r13
0x18001d03c  push    r14
0x18001d03e  push    r15
0x18001d040  lea     rbp, [rsp-27h]
0x18001d045  sub     rsp, 0F0h
0x18001d04c  mov     rax, cs:__security_cookie
0x18001d053  xor     rax, rsp
0x18001d056  mov     [rbp+57h+Path.ByteBuffer.ReservedForIMalloc], rax
0x18001d05a  mov     rdi, r8
0x18001d05d  mov     r12, rcx
0x18001d060  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001d064  jnz     short loc_18001D070
0x18001d066  mov     eax, 80000006h
0x18001d06b  jmp     loc_18001D64C
0x18001d070  xor     r15d, r15d
0x18001d073  test    rcx, rcx
0x18001d076  jnz     short loc_18001D082
0x18001d078  mov     eax, 0C00000EFh
0x18001d07d  jmp     loc_18001D64C
0x18001d082  test    rdi, rdi
0x18001d085  jnz     short loc_18001D091
0x18001d087  mov     eax, 0C00000F1h
0x18001d08c  jmp     loc_18001D64C
0x18001d091  xorps   xmm1, xmm1
0x18001d094  xorps   xmm0, xmm0
0x18001d097  xor     eax, eax
0x18001d099  mov     r8d, 268h; Size
0x18001d09f  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18001d0a3  mov     [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x18001d0a7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18001d0ab  lea     edx, [rax+8]; Flags
0x18001d0ae  movups  [rbp+57h+var_A0], xmm0
0x18001d0b2  movups  [rbp+57h+var_90], xmm0
0x18001d0b6  movups  xmmword ptr [rbp+57h+Path.String.Length], xmm1
0x18001d0ba  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer], xmm1
0x18001d0be  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size], xmm1
0x18001d0c2  mov     rcx, gs:60h
0x18001d0cb  mov     rcx, [rcx+30h]; HeapHandle
0x18001d0cf  call    cs:__imp_RtlAllocateHeap
0x18001d0d5  mov     r13, rax
0x18001d0d8  test    rax, rax
0x18001d0db  jnz     short loc_18001D0E7
0x18001d0dd  mov     ebx, 0C0000017h
0x18001d0e2  jmp     loc_18001D619
0x18001d0e7  mov     rcx, [rdi+20h]
0x18001d0eb  cmp     rcx, 1
0x18001d0ef  jb      loc_18001D5FC
0x18001d0f5  mov     esi, 4
0x18001d0fa  mov     r14d, 2
0x18001d100  lea     rax, [rcx-1]
0x18001d104  cmp     rax, rcx
0x18001d107  jnb     loc_18001D9BB
0x18001d10d  mul     qword ptr [rdi+18h]
0x18001d111  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d115  test    rdx, rdx
0x18001d118  jnz     loc_18001D9BB
0x18001d11e  mov     rcx, [rdi+38h]
0x18001d122  lea     rbx, [rcx+rax]
0x18001d126  cmp     rbx, rcx
0x18001d129  jb      loc_18001D9BB
0x18001d12f  test    rbx, rbx
0x18001d132  jz      loc_18001D9BB
0x18001d138  cmp     [rbx+18h], r15
0x18001d13c  jnz     loc_18001D344
0x18001d142  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x18001d149  mov     r8d, 9C7h
0x18001d14f  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18001d156  lea     ecx, [r14-1]
0x18001d15a  call    AslLogCallPrintf
0x18001d15f  jmp     loc_18001D3F7
0x18001d164  mov     ebx, 8000001Ah
0x18001d169  jmp     loc_18001D31D
0x18001d16e  lea     rcx, [rax-1]
0x18001d172  cmp     rcx, rax
0x18001d175  jnb     loc_18001D2FA
0x18001d17b  mov     rax, rcx
0x18001d17e  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d182  mul     qword ptr [rdi+18h]
0x18001d186  test    rdx, rdx
0x18001d189  jnz     loc_18001D2FA
0x18001d18f  mov     rdx, [rdi+38h]
0x18001d193  lea     rcx, [rdx+rax]
0x18001d197  cmp     rcx, rdx
0x18001d19a  jb      loc_18001D2FA
0x18001d1a0  test    rcx, rcx
0x18001d1a3  jz      loc_18001D2FA
0x18001d1a9  call    AslpPathWildcardFreeMatchNode
0x18001d1ae  mov     r10, [rdi+20h]
0x18001d1b2  mov     r9, r10
0x18001d1b5  lea     rcx, [r10-1]
0x18001d1b9  cmp     rcx, r10
0x18001d1bc  jnb     loc_18001D5EE
0x18001d1c2  mov     rax, rcx
0x18001d1c5  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d1c9  mul     qword ptr [rdi+18h]
0x18001d1cd  test    rdx, rdx
0x18001d1d0  jnz     loc_18001D5EE
0x18001d1d6  mov     r8, [rdi+38h]
0x18001d1da  lea     rsi, [r8+rax]
0x18001d1de  cmp     rsi, r8
0x18001d1e1  jb      loc_18001D5E9
0x18001d1e7  not     rcx
0x18001d1ea  lea     rbx, [rcx+r10]
0x18001d1ee  test    rbx, rbx
0x18001d1f1  jz      short loc_18001D236
0x18001d1f3  mov     rax, [rdi+18h]
0x18001d1f7  mul     rbx
0x18001d1fa  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d1fe  mov     rbx, rax
0x18001d201  test    rdx, rdx
0x18001d204  jnz     loc_18001D5E9
0x18001d20a  mov     rax, r10
0x18001d20d  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d211  mul     qword ptr [rdi+18h]
0x18001d215  test    rdx, rdx
0x18001d218  jnz     loc_18001D5E9
0x18001d21e  lea     rdx, [r8+rax]; Src
0x18001d222  cmp     rdx, r8
0x18001d225  jb      loc_18001D5E9
0x18001d22b  mov     r8, rbx; Size
0x18001d22e  mov     rcx, rsi; void *
0x18001d231  call    memmove_0
0x18001d236  mov     r8, [rdi+18h]; Size
0x18001d23a  lea     rcx, [rsi+rbx]; void *
0x18001d23e  xor     edx, edx; Val
0x18001d240  call    memset_0
0x18001d245  dec     qword ptr [rdi+20h]
0x18001d249  cmp     qword ptr [rdi+20h], 10h
0x18001d24e  jbe     loc_18001D5E9
0x18001d254  mov     rsi, [rdi+28h]
0x18001d258  mov     rax, rsi
0x18001d25b  imul    rax, [rdi+18h]
0x18001d260  cmp     rax, 400h
0x18001d266  jb      loc_18001D5E9
0x18001d26c  mov     rax, rsi
0x18001d26f  shr     rax, 2
0x18001d273  cmp     [rdi+20h], rax
0x18001d277  jnb     loc_18001D5E9
0x18001d27d  mov     rax, [rdi+18h]
0x18001d281  mul     rsi
0x18001d284  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d288  test    rdx, rdx
0x18001d28b  jnz     loc_18001D5E9
0x18001d291  mov     rax, [rdi+18h]
0x18001d295  shr     rsi, 1
0x18001d298  mul     rsi
0x18001d29b  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x18001d29f  mov     r14, rax
0x18001d2a2  test    rdx, rdx
0x18001d2a5  jnz     loc_18001D5E9
0x18001d2ab  mov     r8, [rdi+38h]; lpMem
0x18001d2af  mov     rcx, [rdi+10h]; hHeap
0x18001d2b3  test    r8, r8
0x18001d2b6  jnz     short loc_18001D2D8
0x18001d2b8  mov     r8, rax; dwBytes
0x18001d2bb  call    cs:__imp_HeapAlloc
0x18001d2c1  mov     rbx, rax
0x18001d2c4  test    rax, rax
0x18001d2c7  jz      short loc_18001D2E4
0x18001d2c9  mov     r8, r14; Size
0x18001d2cc  xor     edx, edx; Val
0x18001d2ce  mov     rcx, rax; void *
0x18001d2d1  call    memset_0
0x18001d2d6  jmp     short loc_18001D2E4
0x18001d2d8  mov     r9, r14; dwBytes
0x18001d2db  call    cs:__imp_HeapReAlloc
0x18001d2e1  mov     rbx, rax
0x18001d2e4  test    rbx, rbx
0x18001d2e7  jz      loc_18001D5E9
0x18001d2ed  mov     [rdi+38h], rbx
0x18001d2f1  mov     [rdi+28h], rsi
0x18001d2f5  jmp     loc_18001D5E9
0x18001d2fa  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x18001d301  mov     r8d, 81Fh
0x18001d307  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x18001d30e  mov     ecx, 1
0x18001d313  mov     ebx, 0C00000E5h
0x18001d318  call    AslLogCallPrintf
0x18001d31d  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x18001d324  mov     dword ptr [rsp+120h+IoStatusBlock], ebx
0x18001d328  mov     r8d, 83Ah
0x18001d32e  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x18001d335  mov     ecx, 1
0x18001d33a  call    AslLogCallPrintf
0x18001d33f  jmp     loc_18001D5EE
0x18001d344  mov     rdx, [rbx+10h]; SourceString
0x18001d348  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001d34c  call    cs:__imp_RtlInitUnicodeString
0x18001d352  mov     rcx, [rbx+18h]; FileHandle
0x18001d356  lea     rax, [rbp+57h+DestinationString]
0x18001d35a  mov     [rsp+120h+RestartScan], r15b; RestartScan
0x18001d35f  xor     r9d, r9d; ApcContext
0x18001d362  mov     [rsp+120h+FileName], rax; FileName
0x18001d367  xor     r8d, r8d; ApcRoutine
0x18001d36a  mov     [rsp+120h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18001d36f  lea     rax, [rbp+57h+var_80]
0x18001d373  mov     [rsp+120h+FileInformationClass], 3; FileInformationClass
0x18001d37b  xor     edx, edx; Event
0x18001d37d  mov     [rsp+120h+Length], 268h; Length
0x18001d385  mov     [rsp+120h+FileInformation], r13; FileInformation
0x18001d38a  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x18001d38f  call    cs:__imp_ZwQueryDirectoryFile
0x18001d395  test    eax, eax
0x18001d397  jns     short loc_18001D40A
0x18001d399  cmp     eax, 80000006h
0x18001d39e  jz      short loc_18001D3F7
0x18001d3a0  cmp     eax, 0C000000Fh
0x18001d3a5  jz      short loc_18001D3F7
0x18001d3a7  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x18001d3ae  mov     dword ptr [rsp+120h+IoStatusBlock], eax
0x18001d3b2  mov     r8d, 9DFh
0x18001d3b8  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18001d3bf  mov     ecx, 1
0x18001d3c4  call    AslLogCallPrintf
0x18001d3c9  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18001d3cd  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x18001d3d4  mov     [rsp+120h+FileInformation], rax
0x18001d3d9  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18001d3e0  mov     rax, [rbx+8]
0x18001d3e4  mov     r8d, 9E0h
0x18001d3ea  mov     ecx, r14d
0x18001d3ed  mov     [rsp+120h+IoStatusBlock], rax
0x18001d3f2  call    AslLogCallPrintf
0x18001d3f7  mov     rax, [rdi+20h]
0x18001d3fb  cmp     rax, 1
0x18001d3ff  jb      loc_18001D164
0x18001d405  jmp     loc_18001D16E
0x18001d40a  cmp     [r13+3Ch], esi
0x18001d40e  lea     rsi, [r13+5Eh]
0x18001d412  jnz     short loc_18001D422
0x18001d414  cmp     word ptr [rsi], 2Eh ; '.'
0x18001d418  jnz     short loc_18001D436
0x18001d41a  cmp     word ptr [r13+60h], 2Eh ; '.'
0x18001d420  jmp     short loc_18001D430
0x18001d422  cmp     [r13+3Ch], r14d
0x18001d426  jnz     short loc_18001D436
0x18001d428  lea     rsi, [r13+5Eh]
0x18001d42c  cmp     word ptr [rsi], 2Eh ; '.'
0x18001d430  jz      loc_18001D5E9
0x18001d436  mov     r9d, [r13+38h]
0x18001d43a  lea     rcx, [rbp+57h+var_A0]
0x18001d43e  movzx   eax, word ptr [r13+3Ch]
0x18001d443  mov     rdx, rbx
0x18001d446  mov     r8, [rbx+10h]
0x18001d44a  shr     r9d, 4
0x18001d44e  mov     word ptr [rsp+120h+FileInformation], ax
0x18001d453  and     r9d, 1
0x18001d457  mov     [rsp+120h+IoStatusBlock], rsi
0x18001d45c  call    AslpPathWildcardAllocMatchNode
0x18001d461  cmp     eax, 0C0000273h
0x18001d466  jz      loc_18001D5A8
0x18001d46c  cmp     eax, 0C0000103h
0x18001d471  jz      loc_18001D5E9
0x18001d477  cmp     eax, 0C00000BAh
0x18001d47c  jz      loc_18001D5E9
0x18001d482  test    eax, eax
0x18001d484  js      loc_18001D595
0x18001d48a  mov     r15, [rdi+20h]
0x18001d48e  cmp     r15, [rdi+28h]
0x18001d492  jb      loc_18001D543
0x18001d498  lea     rcx, [r15+1]
0x18001d49c  cmp     rcx, [rdi+28h]
0x18001d4a0  ja      short loc_18001D4AC
0x18001d4a2  mov     ebx, 80070057h
0x18001d4a7  jmp     loc_18001D586
0x18001d4ac  mov     rsi, [rdi+30h]
0x18001d4b0  dec     rsi
0x18001d4b3  lea     r8, [rsi+rcx]
0x18001d4b7  cmp     r8, rcx
0x18001d4ba  jb      loc_18001D581
0x18001d4c0  mov     rax, [rdi+18h]
0x18001d4c4  mul     qword ptr [rdi+28h]
0x18001d4c8  mov     qword ptr [rbp+57h+UnicodeString.Length], 0
0x18001d4d0  test    rdx, rdx
0x18001d4d3  jnz     loc_18001D581
0x18001d4d9  mov     rax, [rdi+18h]
0x18001d4dd  not     rsi
0x18001d4e0  and     rsi, r8
0x18001d4e3  mov     qword ptr [rbp+57h+UnicodeString.Length], rdx
0x18001d4e7  mul     rsi
0x18001d4ea  mov     r14, rax
0x18001d4ed  test    rdx, rdx
0x18001d4f0  jnz     loc_18001D581
0x18001d4f6  mov     r8, [rdi+38h]; lpMem
0x18001d4fa  mov     rcx, [rdi+10h]; hHeap
0x18001d4fe  test    r8, r8
0x18001d501  jnz     short loc_18001D523
0x18001d503  mov     r8, rax; dwBytes
0x18001d506  call    cs:__imp_HeapAlloc
0x18001d50c  mov     rbx, rax
0x18001d50f  test    rax, rax
0x18001d512  jz      short loc_18001D52F
0x18001d514  mov     r8, r14; Size
0x18001d517  xor     edx, edx; Val
0x18001d519  mov     rcx, rax; void *
  ... truncated ...
```

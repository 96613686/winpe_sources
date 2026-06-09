# AslPathWildcardFindNext

- ea: `0x180054cc0`
- end: `0x1800557db`
- name: `AslPathWildcardFindNext`
- size: `2843`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800811a0`
- `0x1800e81a0`

## callees

- `0x180012920`
- `0x180019c84`
- `0x1800212b0`
- `0x18003769c`
- `0x180054cc0`
- `0x1800557e4`
- `0x180056262`
- `0x18007a9cf`
- `0x1800839d0`
- `0x1800847d4`
- `0x1800f1f10`

## import_xrefs

- `ntdll!ZwQueryDirectoryFile` at `0x180055081`
- `ntdll!ZwQueryDirectoryFile` at `0x180055081`
- `ntdll!RtlReAllocateHeap` at `0x180054fcf`
- `ntdll!RtlReAllocateHeap` at `0x180055326`
- `ntdll!RtlReAllocateHeap` at `0x180054fcf`
- `ntdll!RtlReAllocateHeap` at `0x180055326`
- `ntdll!RtlInitUnicodeString` at `0x18005503d`
- `ntdll!RtlInitUnicodeString` at `0x18005503d`
- `ntdll!RtlpEnsureBufferSize` at `0x1800554aa`
- `ntdll!RtlpEnsureBufferSize` at `0x180055502`
- `ntdll!RtlpEnsureBufferSize` at `0x1800555aa`
- `ntdll!RtlpEnsureBufferSize` at `0x180055649`
- `ntdll!RtlpEnsureBufferSize` at `0x1800554aa`
- `ntdll!RtlpEnsureBufferSize` at `0x180055502`
- `ntdll!RtlpEnsureBufferSize` at `0x1800555aa`
- `ntdll!RtlpEnsureBufferSize` at `0x180055649`
- `ntdll!RtlFreeUnicodeString` at `0x18005579e`
- `ntdll!RtlFreeUnicodeString` at `0x18005579e`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800556cb`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800556cb`
- `ntdll!RtlAllocateHeap` at `0x180054d69`
- `ntdll!RtlAllocateHeap` at `0x180054faf`
- `ntdll!RtlAllocateHeap` at `0x180055306`
- `ntdll!RtlAllocateHeap` at `0x180054d69`
- `ntdll!RtlAllocateHeap` at `0x180054faf`
- `ntdll!RtlAllocateHeap` at `0x180055306`

## string_xrefs

- `0x18005501b`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18005573d`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180055001`: `AslpPathWildcardPeekNode`
- `0x18005572c`: `AslpPathWildcardPeekNode`
- `0x180054df5`: `AslPathWildcardFindNext`
- `0x1800550ae`: `AslPathWildcardFindNext`
- `0x1800550cf`: `AslPathWildcardFindNext`
- `0x1800553c7`: `AslPathWildcardFindNext`
- `0x18005541e`: `AslPathWildcardFindNext`
- `0x180055753`: `AslPathWildcardFindNext`
- `0x180055028`: `AslpPathWildcardPopNode`
- `0x180055441`: `AslpPathWildcardPushNode failed [%x]`
- `0x18005570b`: `RtlStringCbCopyNW failed [%x]`
- `0x18005509d`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x1800550c3`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x1800553ba`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x180055409`: `Failed to compute the path length [%x]`
- `0x1800556db`: `RtlNtPathNameToDosPathName failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileInformation; // r13
  unsigned int v6; // ebx
  __int64 v7; // rax
  ULONGLONG v8; // rcx
  unsigned __int16 *v9; // rbx
  __int64 v10; // rax
  int v11; // ebx
  ULONGLONG v12; // rcx
  ULONGLONG v13; // rdx
  __int64 v14; // r10
  ULONGLONG v15; // rcx
  __int64 v16; // r9
  char *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r9
  ULONGLONG v20; // rbx
  ULONGLONG v21; // r10
  ULONGLONG v22; // rcx
  const void *v23; // rdx
  ULONGLONG v24; // rsi
  ULONGLONG v25; // rdx
  ULONGLONG v26; // rsi
  void *v27; // r8
  size_t v28; // r14
  void *v29; // rcx
  PVOID v30; // rax
  PVOID Heap; // rbx
  NTSTATUS v32; // eax
  __int64 v33; // rax
  ULONGLONG v34; // rcx
  ULONGLONG v35; // rdx
  __int64 v36; // r10
  ULONGLONG v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rbx
  __int64 v40; // r9
  ULONGLONG v41; // r10
  ULONGLONG v42; // rcx
  PWSTR Buffer; // rsi
  bool v44; // zf
  int matched; // eax
  ULONGLONG v46; // r15
  __int64 v47; // r14
  ULONGLONG v48; // rdx
  ULONGLONG v49; // rcx
  __int64 v50; // r9
  ULONGLONG v51; // r14
  void *v52; // r8
  size_t v53; // rsi
  void *v54; // rcx
  PVOID v55; // rax
  PVOID v56; // rbx
  ULONGLONG v57; // rcx
  _OWORD *v58; // rdx
  int v59; // eax
  SIZE_T v60; // rdx
  WCHAR *p_ReservedForAllocatedSize; // rcx
  SIZE_T v62; // r8
  const char *v63; // r9
  int v64; // r8d
  USHORT Length; // r9
  SIZE_T v66; // r8
  USHORT v67; // cx
  unsigned __int64 v68; // r8
  USHORT v69; // ax
  USHORT v70; // r9
  USHORT v71; // dx
  unsigned __int64 v72; // r8
  unsigned __int64 v73; // rdx
  NTSTATUS v74; // eax
  int v75; // eax
  PUCHAR StaticBuffer; // rcx
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-E0h]
  ULONGLONG Size; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v79; // [rsp+68h] [rbp-98h] BYREF
  ULONGLONG pullResult; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v83; // [rsp+98h] [rbp-68h] BYREF
  __int128 v84; // [rsp+A8h] [rbp-58h]
  struct _IO_STATUS_BLOCK v85; // [rsp+B8h] [rbp-48h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+C8h] [rbp-38h] BYREF

  *(_QWORD *)&UnicodeString.Length = a1;
  if ( a3 == -1 )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v79 = 0;
  v85 = 0;
  DestinationString = 0;
  v83 = 0;
  v84 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v6 = -1073741801;
    goto LABEL_131;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v7 = *(_QWORD *)(a3 + 32);
            if ( !v7 )
            {
              v6 = -2147483642;
              goto LABEL_130;
            }
            v8 = *(_QWORD *)(a3 + 24);
            pullResult = 0;
            if ( ULongLongMult(v8, v7 - 1, &pullResult) < 0
              || (v9 = (unsigned __int16 *)(*(_QWORD *)(a3 + 56) + pullResult),
                  (unsigned __int64)v9 < *(_QWORD *)(a3 + 56))
              || !v9 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"AslpPathWildcardPeekNode",
                2079,
                (unsigned int)"RtlArrayGet failed to get the next node");
              v63 = "AslpPathWildcardPeekNode failed [%x]";
              v64 = 2498;
              v6 = -1073741595;
              goto LABEL_128;
            }
            if ( *((_QWORD *)v9 + 3) )
              break;
            AslLogCallPrintf(
              1,
              (unsigned int)"AslPathWildcardFindNext",
              2503,
              (unsigned int)"Node on the stack with invalid handle.");
            v10 = *(_QWORD *)(a3 + 32);
            if ( !v10 )
              goto LABEL_15;
            v12 = *(_QWORD *)(a3 + 24);
            pullResult = 0;
            if ( ULongLongMult(v12, v10 - 1, &pullResult) < 0 )
              goto LABEL_39;
            v13 = *(_QWORD *)(a3 + 56) + pullResult;
            if ( v13 < *(_QWORD *)(a3 + 56) || !v13 )
              goto LABEL_39;
            AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + pullResult);
            v14 = *(_QWORD *)(a3 + 32);
            if ( v14 )
            {
              v15 = *(_QWORD *)(a3 + 24);
              pullResult = 0;
              if ( ULongLongMult(v15, v14 - 1, &pullResult) >= 0 )
              {
                v17 = (char *)(*(_QWORD *)(a3 + 56) + pullResult);
                if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
                {
                  v18 = *(_QWORD *)(a3 + 32);
                  v19 = ~v16;
                  v44 = v19 + v18 == 0;
                  v20 = v19 + v18;
                  Size = v20;
                  if ( v44 )
                    goto LABEL_28;
                  if ( ULongLongMult(v20, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                  {
                    v22 = *(_QWORD *)(a3 + 24);
                    pullResult = 0;
                    if ( ULongLongMult(v22, v21, &pullResult) >= 0 )
                    {
                      v23 = (const void *)(*(_QWORD *)(a3 + 56) + pullResult);
                      if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                      {
                        v20 = Size;
LABEL_27:
                        memmove_0(v17, v23, v20);
                        goto LABEL_28;
                      }
                    }
                  }
                }
              }
            }
          }
          RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v9 + 2));
          v32 = ZwQueryDirectoryFile(
                  *((HANDLE *)v9 + 3),
                  0,
                  0,
                  0,
                  &v85,
                  FileInformation,
                  0x268u,
                  FileBothDirectoryInformation,
                  1u,
                  &DestinationString,
                  0);
          if ( v32 >= 0 )
            break;
          if ( v32 != -2147483642 && v32 != -1073741809 )
          {
            LODWORD(IoStatusBlock) = v32;
            AslLogCallPrintf(
              1,
              (unsigned int)"AslPathWildcardFindNext",
              2527,
              (unsigned int)"NtQueryDirectoryFile failed to query next file [%x]",
              IoStatusBlock);
            AslLogCallPrintf(
              2,
              (unsigned int)"AslPathWildcardFindNext",
              2528,
              (unsigned int)"FilePath: '%ws'  Pattern: '%ws'",
              *((_QWORD *)v9 + 1),
              DestinationString.Buffer);
          }
          v33 = *(_QWORD *)(a3 + 32);
          if ( !v33 )
          {
LABEL_15:
            v11 = -2147483622;
            goto LABEL_40;
          }
          v34 = *(_QWORD *)(a3 + 24);
          Size = 0;
          if ( ULongLongMult(v34, v33 - 1, &Size) >= 0
            && (v35 = *(_QWORD *)(a3 + 56) + Size, v35 >= *(_QWORD *)(a3 + 56))
            && v35 )
          {
            AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + Size);
            v36 = *(_QWORD *)(a3 + 32);
            if ( v36 )
            {
              v37 = *(_QWORD *)(a3 + 24);
              Size = 0;
              if ( ULongLongMult(v37, v36 - 1, &Size) >= 0 )
              {
                v17 = (char *)(*(_QWORD *)(a3 + 56) + Size);
                if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
                {
                  v39 = *(_QWORD *)(a3 + 32);
                  v40 = ~v38;
                  v44 = v40 + v39 == 0;
                  v20 = v40 + v39;
                  pullResult = v20;
                  if ( v44 )
                  {
LABEL_28:
                    memset_0(&v17[v20], 0, *(_QWORD *)(a3 + 24));
                    if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                    {
                      v24 = *(_QWORD *)(a3 + 40);
                      v25 = *(_QWORD *)(a3 + 24);
                      if ( v25 * v24 >= 0x400 && *(_QWORD *)(a3 + 32) < v24 >> 2 )
                      {
                        Size = 0;
                        if ( ULongLongMult(v24, v25, &pullResult) >= 0 )
                        {
                          v26 = v24 >> 1;
                          if ( ULongLongMult(v26, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                          {
                            v27 = *(void **)(a3 + 56);
                            v28 = Size;
                            v29 = *(void **)(a3 + 16);
                            if ( v27 )
                            {
                              Heap = RtlReAllocateHeap(v29, 0, v27, Size);
                            }
                            else
                            {
                              v30 = RtlAllocateHeap(v29, 0, Size);
                              Heap = v30;
                              if ( v30 )
                                memset_0(v30, 0, v28);
                            }
                            if ( Heap )
                            {
                              *(_QWORD *)(a3 + 56) = Heap;
                              *(_QWORD *)(a3 + 40) = v26;
                            }
                          }
                        }
                      }
                    }
                  }
                  else if ( ULongLongMult(v20, *(_QWORD *)(a3 + 24), &pullResult) >= 0 )
                  {
                    v42 = *(_QWORD *)(a3 + 24);
                    Size = 0;
                    if ( ULongLongMult(v42, v41, &Size) >= 0 )
                    {
                      v23 = (const void *)(*(_QWORD *)(a3 + 56) + Size);
                      if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                      {
                        v20 = pullResult;
                        goto LABEL_27;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
LABEL_39:
            v11 = -1073741595;
            AslLogCallPrintf(
              1,
              (unsigned int)"AslpPathWildcardPeekNode",
              2079,
              (unsigned int)"RtlArrayGet failed to get the next node");
LABEL_40:
            LODWORD(IoStatusBlock) = v11;
            AslLogCallPrintf(
              1,
              (unsigned int)"AslpPathWildcardPopNode",
              2106,
              (unsigned int)"AslpPathWildcardPeekNode failed [%x]",
              IoStatusBlock);
          }
        }
        Buffer = (PWSTR)(FileInformation + 94);
        if ( *((_DWORD *)FileInformation + 15) == 4 )
        {
          if ( *Buffer != 46 )
            break;
          v44 = *((_WORD *)FileInformation + 48) == 46;
        }
        else
        {
          if ( *((_DWORD *)FileInformation + 15) != 2 )
            break;
          Buffer = (PWSTR)(FileInformation + 94);
          v44 = *((_WORD *)FileInformation + 47) == 46;
        }
      }
      while ( v44 );
      matched = AslpPathWildcardAllocMatchNode(
                  (unsigned int)&v83,
                  (_DWORD)v9,
                  *((_QWORD *)v9 + 2),
                  (*((_DWORD *)FileInformation + 14) >> 4) & 1,
                  (__int64)Buffer,
                  *((_WORD *)FileInformation + 30));
      if ( matched == -1073741197 )
        break;
      if ( matched != -1073741565 && matched != -1073741638 )
      {
        if ( matched < 0 )
        {
          LODWORD(IoStatusBlock) = matched;
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindNext",
            2585,
            (unsigned int)"AslpPathWildcardAllocMatchNode failed [%x]",
            IoStatusBlock);
        }
        else
        {
          v46 = *(_QWORD *)(a3 + 32);
          if ( v46 >= *(_QWORD *)(a3 + 40) )
          {
            if ( v46 + 1 <= *(_QWORD *)(a3 + 40) )
            {
              v6 = -1073741811;
              goto LABEL_84;
            }
            v47 = *(_QWORD *)(a3 + 48) - 1LL;
            if ( *(_QWORD *)(a3 + 48) + v46 < v46 + 1
              || (v48 = *(_QWORD *)(a3 + 24),
                  v49 = *(_QWORD *)(a3 + 40),
                  Size = 0,
                  ULongLongMult(v49, v48, &pullResult) < 0)
              || (v51 = v50 & ~v47, ULongLongMult(v51, *(_QWORD *)(a3 + 24), &Size) < 0) )
            {
              v6 = -1073741675;
LABEL_84:
              v59 = v6;
LABEL_90:
              LODWORD(IoStatusBlock) = v59;
              AslLogCallPrintf(
                1,
                (unsigned int)"AslPathWildcardFindNext",
                2577,
                (unsigned int)"AslpPathWildcardPushNode failed [%x]",
                IoStatusBlock);
              goto LABEL_130;
            }
            v52 = *(void **)(a3 + 56);
            v53 = Size;
            v54 = *(void **)(a3 + 16);
            if ( v52 )
            {
              v56 = RtlReAllocateHeap(v54, 0, v52, Size);
            }
            else
            {
              v55 = RtlAllocateHeap(v54, 0, Size);
              v56 = v55;
              if ( v55 )
                memset_0(v55, 0, v53);
            }
            if ( !v56 )
            {
              v6 = -1073741801;
              goto LABEL_84;
            }
            *(_QWORD *)(a3 + 40) = v51;
            *(_QWORD *)(a3 + 56) = v56;
          }
          v57 = *(_QWORD *)(a3 + 24);
          Size = 0;
          if ( ULongLongMult(v57, v46, &Size) < 0
            || (v58 = (_OWORD *)(*(_QWORD *)(a3 + 56) + Size), (unsigned __int64)v58 < *(_QWORD *)(a3 + 56)) )
          {
            v59 = -1073741675;
            v6 = -1073741675;
            goto LABEL_90;
          }
          *v58 = v83;
          v58[1] = v84;
          ++*(_QWORD *)(a3 + 32);
        }
      }
    }
    if ( (int)RtlUShortAdd(*v9, *((unsigned __int16 *)FileInformation + 30), &v79) >= 0
      && (int)RtlUShortAdd(v79, 2, &v79) >= 0 )
    {
      break;
    }
    LODWORD(IoStatusBlock) = -1073741675;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathWildcardFindNext",
      2629,
      (unsigned int)"Failed to compute the path length [%x]",
      IoStatusBlock);
  }
  v60 = 2;
  Path.ByteBuffer.StaticSize = 2;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  v62 = v79 + 2LL;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Size = 2;
  LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
  Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
  *(_DWORD *)&Path.String.Length = 0x20000;
  if ( v62 > 0xFFFE )
  {
    v6 = -1073741562;
    goto LABEL_96;
  }
  if ( v62 > 2 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v62) < 0 )
    {
      v6 = -1073741801;
LABEL_96:
      v63 = "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]";
      v64 = 2638;
LABEL_128:
      LODWORD(IoStatusBlock) = v6;
      AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindNext", v64, (_DWORD)v63, IoStatusBlock);
      goto LABEL_130;
    }
    v60 = Path.ByteBuffer.Size;
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  Length = 0;
  Path.String.MaximumLength = v60;
  Path.String.Length = 0;
  v66 = *v9 + 2LL;
  if ( v66 > 0xFFFE )
  {
    v6 = -1073741562;
LABEL_103:
    v63 = "RtlAssignUnicodeStringBuffer failed [%x]";
    v64 = 2648;
    goto LABEL_128;
  }
  if ( v66 > v60 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v66) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_103;
    }
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v9 + 1), *v9);
  Path.String.MaximumLength = *v9 + Path.String.Length + 2;
  Path.String.Length += *v9;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  if ( *(_WORD *)(*((_QWORD *)v9 + 1) + 2 * ((unsigned __int64)*v9 >> 1) - 2) != 92 )
  {
    v67 = Path.String.Length;
    v68 = (unsigned int)Path.String.Length + 2 + 2LL;
    if ( v68 > 0xFFFE )
    {
      v6 = -1073741562;
LABEL_111:
      v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
      v64 = 2655;
      goto LABEL_128;
    }
    if ( v68 > Path.ByteBuffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v68) < 0 )
      {
        v6 = -1073741801;
        goto LABEL_111;
      }
      v67 = Path.String.Length;
    }
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v67 >> 1)] = SubBlock[0];
    v69 = Path.String.Length + 4;
    Path.String.Length += 2;
    Path.String.MaximumLength = v69;
    Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  }
  v70 = Path.String.Length;
  DestinationString.Buffer = Buffer;
  DestinationString.Length = *((_WORD *)FileInformation + 30);
  v71 = DestinationString.Length;
  DestinationString.MaximumLength = *((_WORD *)FileInformation + 30);
  v72 = Path.String.Length + (unsigned int)DestinationString.Length + 2LL;
  if ( v72 > 0xFFFE )
  {
    v6 = -1073741562;
LABEL_119:
    v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
    v64 = 2670;
    goto LABEL_128;
  }
  if ( v72 > Path.ByteBuffer.Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v72) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_119;
    }
    Buffer = DestinationString.Buffer;
    v71 = DestinationString.Length;
    v70 = Path.String.Length;
  }
  Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
  memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v70 >> 1)], Buffer, v71);
  v73 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
  Path.String.Length = v73;
  Path.String.MaximumLength = v73 + 2;
  Path.String.Buffer[v73 >> 1] = 0;
  if ( *(_DWORD *)a3 && (v74 = RtlNtPathNameToDosPathName(0, &Path, 0, 0), v6 = v74, v74 < 0) )
  {
    LODWORD(IoStatusBlock) = v74;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathWildcardFindNext",
      2681,
      (unsigned int)"RtlNtPathNameToDosPathName failed [%x]",
      IoStatusBlock);
  }
  else
  {
    v75 = RtlStringCbCopyNW(*(_QWORD *)&UnicodeString.Length, 520, Path.String.Buffer, Path.String.Length);
    v6 = v75;
    if ( v75 >= 0 )
    {
      v6 = 0;
    }
    else
    {
      LODWORD(IoStatusBlock) = v75;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindNext",
        2692,
        (unsigned int)"RtlStringCbCopyNW failed [%x]",
        IoStatusBlock);
    }
  }
LABEL_130:
  AslFree(NtCurrentPeb()->ProcessHeap, FileInformation);
LABEL_131:
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
  return v6;
}

```

## disassembly

```asm
0x180054cc0  mov     [rsp-8+arg_8], rbx
0x180054cc5  mov     [rsp-8+arg_18], rsi
0x180054cca  push    rbp
0x180054ccb  push    rdi
0x180054ccc  push    r13
0x180054cce  push    r14
0x180054cd0  push    r15
0x180054cd2  lea     rbp, [rsp-10h]
0x180054cd7  sub     rsp, 110h
0x180054cde  mov     rax, cs:__security_cookie
0x180054ce5  xor     rax, rsp
0x180054ce8  mov     [rbp+30h+Path.ByteBuffer.ReservedForIMalloc], rax
0x180054cec  mov     qword ptr [rbp+30h+UnicodeString.Length], rcx
0x180054cf0  mov     rdi, r8
0x180054cf3  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180054cf7  jnz     short loc_180054D03
0x180054cf9  mov     eax, 80000006h
0x180054cfe  jmp     loc_1800557B3
0x180054d03  xor     r15d, r15d
0x180054d06  test    rcx, rcx
0x180054d09  jnz     short loc_180054D15
0x180054d0b  mov     eax, 0C00000EFh
0x180054d10  jmp     loc_1800557B3
0x180054d15  test    rdi, rdi
0x180054d18  jnz     short loc_180054D24
0x180054d1a  mov     eax, 0C00000F1h
0x180054d1f  jmp     loc_1800557B3
0x180054d24  xorps   xmm1, xmm1
0x180054d27  mov     [rsp+130h+var_C8], r15w
0x180054d2d  xorps   xmm0, xmm0
0x180054d30  xor     eax, eax
0x180054d32  movups  xmmword ptr [rbp+30h+var_78], xmm0
0x180054d36  mov     [rbp+30h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x180054d3a  mov     r8d, 268h; Size
0x180054d40  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x180054d45  lea     edx, [rax+8]; Flags
0x180054d48  movups  [rbp+30h+var_98], xmm0
0x180054d4c  movups  [rbp+30h+var_88], xmm0
0x180054d50  movups  xmmword ptr [rbp+30h+Path.String.Length], xmm1
0x180054d54  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Buffer], xmm1
0x180054d58  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Size], xmm1
0x180054d5c  mov     rcx, gs:60h
0x180054d65  mov     rcx, [rcx+30h]; HeapHandle
0x180054d69  call    cs:__imp_RtlAllocateHeap
0x180054d6f  mov     r13, rax
0x180054d72  test    rax, rax
0x180054d75  jnz     short loc_180054D81
0x180054d77  mov     ebx, 0C0000017h
0x180054d7c  jmp     loc_180055780
0x180054d81  mov     r14d, 2
0x180054d87  mov     esi, 4
0x180054d8c  mov     rax, [rdi+20h]
0x180054d90  cmp     rax, 1
0x180054d94  jb      loc_180055766
0x180054d9a  lea     rdx, [rax-1]; ullMultiplier
0x180054d9e  cmp     rdx, rax
0x180054da1  jnb     loc_18005571F
0x180054da7  mov     rcx, [rdi+18h]; ullMultiplicand
0x180054dab  lea     r8, [rsp+130h+pullResult]; pullResult
0x180054db0  mov     [rsp+130h+pullResult], r15
0x180054db5  call    ULongLongMult
0x180054dba  test    eax, eax
0x180054dbc  js      loc_18005571F
0x180054dc2  mov     rbx, [rsp+130h+pullResult]
0x180054dc7  add     rbx, [rdi+38h]
0x180054dcb  cmp     rbx, [rdi+38h]
0x180054dcf  jb      loc_18005571F
0x180054dd5  test    rbx, rbx
0x180054dd8  jz      loc_18005571F
0x180054dde  cmp     [rbx+18h], r15
0x180054de2  jnz     loc_180055034
0x180054de8  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x180054def  mov     r8d, 9C7h
0x180054df5  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180054dfc  mov     ecx, 1
0x180054e01  call    AslLogCallPrintf
0x180054e06  mov     rax, [rdi+20h]
0x180054e0a  cmp     rax, 1
0x180054e0e  jnb     short loc_180054E1A
0x180054e10  mov     ebx, 8000001Ah
0x180054e15  jmp     loc_180055017
0x180054e1a  lea     rdx, [rax-1]; ullMultiplier
0x180054e1e  cmp     rdx, rax
0x180054e21  jnb     loc_180054FF4
0x180054e27  mov     rcx, [rdi+18h]; ullMultiplicand
0x180054e2b  lea     r8, [rsp+130h+pullResult]; pullResult
0x180054e30  mov     [rsp+130h+pullResult], r15
0x180054e35  call    ULongLongMult
0x180054e3a  test    eax, eax
0x180054e3c  js      loc_180054FF4
0x180054e42  mov     rdx, [rsp+130h+pullResult]
0x180054e47  add     rdx, [rdi+38h]
0x180054e4b  cmp     rdx, [rdi+38h]
0x180054e4f  jb      loc_180054FF4
0x180054e55  test    rdx, rdx
0x180054e58  jz      loc_180054FF4
0x180054e5e  mov     rcx, rdx
0x180054e61  call    AslpPathWildcardFreeMatchNode
0x180054e66  mov     r10, [rdi+20h]
0x180054e6a  lea     r9, [r10-1]
0x180054e6e  cmp     r9, r10
0x180054e71  jnb     loc_180054D8C
0x180054e77  mov     rcx, [rdi+18h]; ullMultiplicand
0x180054e7b  lea     r8, [rsp+130h+pullResult]; pullResult
0x180054e80  mov     rdx, r9; ullMultiplier
0x180054e83  mov     [rsp+130h+pullResult], r15
0x180054e88  call    ULongLongMult
0x180054e8d  test    eax, eax
0x180054e8f  js      loc_180054D8C
0x180054e95  mov     rsi, [rsp+130h+pullResult]
0x180054e9a  add     rsi, [rdi+38h]
0x180054e9e  cmp     rsi, [rdi+38h]
0x180054ea2  jb      loc_180054D87
0x180054ea8  mov     rbx, [rdi+20h]
0x180054eac  not     r9
0x180054eaf  add     rbx, r9
0x180054eb2  mov     [rsp+130h+Size], rbx
0x180054eb7  jz      short loc_180054F13
0x180054eb9  mov     rdx, [rdi+18h]; ullMultiplier
0x180054ebd  lea     r8, [rsp+130h+Size]; pullResult
0x180054ec2  mov     rcx, rbx; ullMultiplicand
0x180054ec5  call    ULongLongMult
0x180054eca  test    eax, eax
0x180054ecc  js      loc_180054D87
0x180054ed2  mov     rcx, [rdi+18h]; ullMultiplicand
0x180054ed6  lea     r8, [rsp+130h+pullResult]; pullResult
0x180054edb  mov     rdx, r10; ullMultiplier
0x180054ede  mov     [rsp+130h+pullResult], r15
0x180054ee3  call    ULongLongMult
0x180054ee8  test    eax, eax
0x180054eea  js      loc_180054D87
0x180054ef0  mov     rdx, [rsp+130h+pullResult]
0x180054ef5  add     rdx, [rdi+38h]; Src
0x180054ef9  cmp     rdx, [rdi+38h]
0x180054efd  jb      loc_180054D87
0x180054f03  mov     rbx, [rsp+130h+Size]
0x180054f08  mov     r8, rbx; Size
0x180054f0b  mov     rcx, rsi; void *
0x180054f0e  call    memmove_0
0x180054f13  mov     r8, [rdi+18h]; Size
0x180054f17  lea     rcx, [rsi+rbx]; void *
0x180054f1b  xor     edx, edx; Val
0x180054f1d  call    memset_0
0x180054f22  dec     qword ptr [rdi+20h]
0x180054f26  mov     esi, 4
0x180054f2b  cmp     qword ptr [rdi+20h], 10h
0x180054f30  jbe     loc_180054D8C
0x180054f36  mov     rsi, [rdi+28h]
0x180054f3a  mov     rdx, [rdi+18h]; ullMultiplier
0x180054f3e  mov     rax, rsi
0x180054f41  imul    rax, rdx
0x180054f45  cmp     rax, 400h
0x180054f4b  jb      loc_180054D87
0x180054f51  mov     rax, rsi
0x180054f54  shr     rax, 2
0x180054f58  cmp     [rdi+20h], rax
0x180054f5c  jnb     loc_180054D87
0x180054f62  lea     r8, [rsp+130h+pullResult]; pullResult
0x180054f67  mov     [rsp+130h+Size], r15
0x180054f6c  mov     rcx, rsi; ullMultiplicand
0x180054f6f  call    ULongLongMult
0x180054f74  test    eax, eax
0x180054f76  js      loc_180054D87
0x180054f7c  mov     rdx, [rdi+18h]; ullMultiplier
0x180054f80  lea     r8, [rsp+130h+Size]; pullResult
0x180054f85  shr     rsi, 1
0x180054f88  mov     rcx, rsi; ullMultiplicand
0x180054f8b  call    ULongLongMult
0x180054f90  test    eax, eax
0x180054f92  js      loc_180054D87
0x180054f98  mov     r8, [rdi+38h]; Ptr
0x180054f9c  xor     edx, edx; Flags
0x180054f9e  mov     r14, [rsp+130h+Size]
0x180054fa3  mov     rcx, [rdi+10h]; Heap
0x180054fa7  test    r8, r8
0x180054faa  jnz     short loc_180054FCC
0x180054fac  mov     r8, r14; Size
0x180054faf  call    cs:__imp_RtlAllocateHeap
0x180054fb5  mov     rbx, rax
0x180054fb8  test    rax, rax
0x180054fbb  jz      short loc_180054FD8
0x180054fbd  mov     r8, r14; Size
0x180054fc0  xor     edx, edx; Val
0x180054fc2  mov     rcx, rax; void *
0x180054fc5  call    memset_0
0x180054fca  jmp     short loc_180054FD8
0x180054fcc  mov     r9, r14; Size
0x180054fcf  call    cs:__imp_RtlReAllocateHeap
0x180054fd5  mov     rbx, rax
0x180054fd8  mov     r14d, 2
0x180054fde  test    rbx, rbx
0x180054fe1  jz      loc_180054D87
0x180054fe7  mov     [rdi+38h], rbx
0x180054feb  mov     [rdi+28h], rsi
0x180054fef  jmp     loc_180054D87
0x180054ff4  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x180054ffb  mov     r8d, 81Fh
0x180055001  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180055008  mov     ecx, 1
0x18005500d  mov     ebx, 0C00000E5h
0x180055012  call    AslLogCallPrintf
0x180055017  mov     dword ptr [rsp+130h+IoStatusBlock], ebx
0x18005501b  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180055022  mov     r8d, 83Ah
0x180055028  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x18005502f  jmp     loc_1800553CE
0x180055034  mov     rdx, [rbx+10h]; SourceString
0x180055038  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18005503d  call    cs:__imp_RtlInitUnicodeString
0x180055043  mov     rcx, [rbx+18h]; FileHandle
0x180055047  lea     rax, [rsp+130h+DestinationString]
0x18005504c  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x180055051  xor     r9d, r9d; ApcContext
0x180055054  mov     [rsp+130h+FileName], rax; FileName
0x180055059  xor     r8d, r8d; ApcRoutine
0x18005505c  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180055061  lea     rax, [rbp+30h+var_78]
0x180055065  mov     [rsp+130h+FileInformationClass], 3; FileInformationClass
0x18005506d  xor     edx, edx; Event
0x18005506f  mov     [rsp+130h+Length], 268h; Length
0x180055077  mov     [rsp+130h+FileInformation], r13; FileInformation
0x18005507c  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x180055081  call    cs:__imp_ZwQueryDirectoryFile
0x180055087  test    eax, eax
0x180055089  jns     loc_1800551F2
0x18005508f  cmp     eax, 80000006h
0x180055094  jz      short loc_1800550ED
0x180055096  cmp     eax, 0C000000Fh
0x18005509b  jz      short loc_1800550ED
0x18005509d  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x1800550a4  mov     dword ptr [rsp+130h+IoStatusBlock], eax
0x1800550a8  mov     r8d, 9DFh
0x1800550ae  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800550b5  mov     ecx, 1
0x1800550ba  call    AslLogCallPrintf
0x1800550bf  mov     rax, [rbp+30h+DestinationString.Buffer]
0x1800550c3  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x1800550ca  mov     [rsp+130h+FileInformation], rax
0x1800550cf  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1800550d6  mov     rax, [rbx+8]
0x1800550da  mov     r8d, 9E0h
0x1800550e0  mov     ecx, r14d
0x1800550e3  mov     [rsp+130h+IoStatusBlock], rax
0x1800550e8  call    AslLogCallPrintf
0x1800550ed  mov     rax, [rdi+20h]
0x1800550f1  cmp     rax, 1
0x1800550f5  jb      loc_180054E10
0x1800550fb  lea     rdx, [rax-1]; ullMultiplier
0x1800550ff  cmp     rdx, rax
0x180055102  jnb     loc_180054FF4
0x180055108  mov     rcx, [rdi+18h]; ullMultiplicand
0x18005510c  lea     r8, [rsp+130h+Size]; pullResult
0x180055111  mov     [rsp+130h+Size], r15
0x180055116  call    ULongLongMult
0x18005511b  test    eax, eax
0x18005511d  js      loc_180054FF4
0x180055123  mov     rdx, [rsp+130h+Size]
0x180055128  add     rdx, [rdi+38h]
0x18005512c  cmp     rdx, [rdi+38h]
0x180055130  jb      loc_180054FF4
0x180055136  test    rdx, rdx
0x180055139  jz      loc_180054FF4
0x18005513f  mov     rcx, rdx
0x180055142  call    AslpPathWildcardFreeMatchNode
0x180055147  mov     r10, [rdi+20h]
0x18005514b  lea     r9, [r10-1]
0x18005514f  cmp     r9, r10
0x180055152  jnb     loc_180054D8C
0x180055158  mov     rcx, [rdi+18h]; ullMultiplicand
0x18005515c  lea     r8, [rsp+130h+Size]; pullResult
0x180055161  mov     rdx, r9; ullMultiplier
0x180055164  mov     [rsp+130h+Size], r15
0x180055169  call    ULongLongMult
0x18005516e  test    eax, eax
0x180055170  js      loc_180054D8C
0x180055176  mov     rsi, [rsp+130h+Size]
0x18005517b  add     rsi, [rdi+38h]
0x18005517f  cmp     rsi, [rdi+38h]
0x180055183  jb      loc_180054D87
0x180055189  mov     rbx, [rdi+20h]
0x18005518d  not     r9
0x180055190  add     rbx, r9
0x180055193  mov     [rsp+130h+pullResult], rbx
0x180055198  jz      loc_180054F13
0x18005519e  mov     rdx, [rdi+18h]; ullMultiplier
0x1800551a2  lea     r8, [rsp+130h+pullResult]; pullResult
0x1800551a7  mov     rcx, rbx; ullMultiplicand
0x1800551aa  call    ULongLongMult
0x1800551af  test    eax, eax
0x1800551b1  js      loc_180054D87
0x1800551b7  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800551bb  lea     r8, [rsp+130h+Size]; pullResult
0x1800551c0  mov     rdx, r10; ullMultiplier
0x1800551c3  mov     [rsp+130h+Size], r15
0x1800551c8  call    ULongLongMult
0x1800551cd  test    eax, eax
0x1800551cf  js      loc_180054D87
0x1800551d5  mov     rdx, [rsp+130h+Size]
0x1800551da  add     rdx, [rdi+38h]
0x1800551de  cmp     rdx, [rdi+38h]
  ... truncated ...
```

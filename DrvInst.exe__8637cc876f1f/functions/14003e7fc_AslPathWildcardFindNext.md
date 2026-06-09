# AslPathWildcardFindNext

- ea: `0x14003e7fc`
- end: `0x14003f317`
- name: `AslPathWildcardFindNext`
- size: `2843`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140031f20`
- `0x14003e294`

## callees

- `0x1400344cc`
- `0x14003bf18`
- `0x14003c368`
- `0x14003e7fc`
- `0x14003f624`
- `0x14003f9a4`
- `0x14003fd14`
- `0x14003fd84`
- `0x140045ede`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003eb79`
- `ntdll!RtlInitUnicodeString` at `0x14003eb79`
- `ntdll!RtlFreeUnicodeString` at `0x14003f2da`
- `ntdll!RtlFreeUnicodeString` at `0x14003f2da`
- `ntdll!RtlReAllocateHeap` at `0x14003eb0b`
- `ntdll!RtlReAllocateHeap` at `0x14003ee62`
- `ntdll!RtlReAllocateHeap` at `0x14003eb0b`
- `ntdll!RtlReAllocateHeap` at `0x14003ee62`
- `ntdll!RtlAllocateHeap` at `0x14003e8a5`
- `ntdll!RtlAllocateHeap` at `0x14003eaeb`
- `ntdll!RtlAllocateHeap` at `0x14003ee42`
- `ntdll!RtlAllocateHeap` at `0x14003e8a5`
- `ntdll!RtlAllocateHeap` at `0x14003eaeb`
- `ntdll!RtlAllocateHeap` at `0x14003ee42`
- `ntdll!ZwQueryDirectoryFile` at `0x14003ebbd`
- `ntdll!ZwQueryDirectoryFile` at `0x14003ebbd`
- `ntdll!RtlpEnsureBufferSize` at `0x14003efe6`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f03e`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f0e6`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f185`
- `ntdll!RtlpEnsureBufferSize` at `0x14003efe6`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f03e`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f0e6`
- `ntdll!RtlpEnsureBufferSize` at `0x14003f185`
- `ntdll!RtlNtPathNameToDosPathName` at `0x14003f207`
- `ntdll!RtlNtPathNameToDosPathName` at `0x14003f207`

## string_xrefs

- `0x14003eb57`: `AslpPathWildcardPeekNode failed [%x]`
- `0x14003f279`: `AslpPathWildcardPeekNode failed [%x]`
- `0x14003eb3d`: `AslpPathWildcardPeekNode`
- `0x14003f268`: `AslpPathWildcardPeekNode`
- `0x14003eb64`: `AslpPathWildcardPopNode`
- `0x14003f247`: `RtlStringCbCopyNW failed [%x]`
- `0x14003e931`: `AslPathWildcardFindNext`
- `0x14003ebea`: `AslPathWildcardFindNext`
- `0x14003ec0b`: `AslPathWildcardFindNext`
- `0x14003ef03`: `AslPathWildcardFindNext`
- `0x14003ef5a`: `AslPathWildcardFindNext`
- `0x14003f28f`: `AslPathWildcardFindNext`
- `0x14003ef7d`: `AslpPathWildcardPushNode failed [%x]`
- `0x14003ebd9`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x14003eef6`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x14003ebff`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x14003ef45`: `Failed to compute the path length [%x]`
- `0x14003f217`: `RtlNtPathNameToDosPathName failed [%x]`

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
  __int64 v64; // r8
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
              AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
              v63 = "AslpPathWildcardPeekNode failed [%x]";
              v64 = 2498;
              v6 = -1073741595;
              goto LABEL_128;
            }
            if ( *((_QWORD *)v9 + 3) )
              break;
            AslLogCallPrintf(1, "AslPathWildcardFindNext", 2503, "Node on the stack with invalid handle.");
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
            AslLogCallPrintf(
              1,
              "AslPathWildcardFindNext",
              2527,
              "NtQueryDirectoryFile failed to query next file [%x]",
              v32);
            AslLogCallPrintf(
              2,
              "AslPathWildcardFindNext",
              2528,
              "FilePath: '%ws'  Pattern: '%ws'",
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
            AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
LABEL_40:
            LODWORD(IoStatusBlock) = v11;
            AslLogCallPrintf(1, "AslpPathWildcardPopNode", 2106, "AslpPathWildcardPeekNode failed [%x]", IoStatusBlock);
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
            "AslPathWildcardFindNext",
            2585,
            "AslpPathWildcardAllocMatchNode failed [%x]",
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
                "AslPathWildcardFindNext",
                2577,
                "AslpPathWildcardPushNode failed [%x]",
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
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2629, "Failed to compute the path length [%x]", -1073741675);
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
      AslLogCallPrintf(1, "AslPathWildcardFindNext", v64, v63, IoStatusBlock);
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
    *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v67 >> 1)] = asc_140049D20[0];
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
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2681, "RtlNtPathNameToDosPathName failed [%x]", IoStatusBlock);
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
      AslLogCallPrintf(1, "AslPathWildcardFindNext", 2692, "RtlStringCbCopyNW failed [%x]", IoStatusBlock);
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
0x14003e7fc  mov     [rsp-8+arg_8], rbx
0x14003e801  mov     [rsp-8+arg_18], rsi
0x14003e806  push    rbp
0x14003e807  push    rdi
0x14003e808  push    r13
0x14003e80a  push    r14
0x14003e80c  push    r15
0x14003e80e  lea     rbp, [rsp-10h]
0x14003e813  sub     rsp, 110h
0x14003e81a  mov     rax, cs:__security_cookie
0x14003e821  xor     rax, rsp
0x14003e824  mov     [rbp+30h+Path.ByteBuffer.ReservedForIMalloc], rax
0x14003e828  mov     qword ptr [rbp+30h+UnicodeString.Length], rcx
0x14003e82c  mov     rdi, r8
0x14003e82f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14003e833  jnz     short loc_14003E83F
0x14003e835  mov     eax, 80000006h
0x14003e83a  jmp     loc_14003F2EF
0x14003e83f  xor     r15d, r15d
0x14003e842  test    rcx, rcx
0x14003e845  jnz     short loc_14003E851
0x14003e847  mov     eax, 0C00000EFh
0x14003e84c  jmp     loc_14003F2EF
0x14003e851  test    rdi, rdi
0x14003e854  jnz     short loc_14003E860
0x14003e856  mov     eax, 0C00000F1h
0x14003e85b  jmp     loc_14003F2EF
0x14003e860  xorps   xmm1, xmm1
0x14003e863  mov     [rsp+130h+var_C8], r15w
0x14003e869  xorps   xmm0, xmm0
0x14003e86c  xor     eax, eax
0x14003e86e  movups  xmmword ptr [rbp+30h+var_78], xmm0
0x14003e872  mov     [rbp+30h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x14003e876  mov     r8d, 268h; Size
0x14003e87c  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x14003e881  lea     edx, [rax+8]; Flags
0x14003e884  movups  [rbp+30h+var_98], xmm0
0x14003e888  movups  [rbp+30h+var_88], xmm0
0x14003e88c  movups  xmmword ptr [rbp+30h+Path.String.Length], xmm1
0x14003e890  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Buffer], xmm1
0x14003e894  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Size], xmm1
0x14003e898  mov     rcx, gs:60h
0x14003e8a1  mov     rcx, [rcx+30h]; HeapHandle
0x14003e8a5  call    cs:__imp_RtlAllocateHeap
0x14003e8ab  mov     r13, rax
0x14003e8ae  test    rax, rax
0x14003e8b1  jnz     short loc_14003E8BD
0x14003e8b3  mov     ebx, 0C0000017h
0x14003e8b8  jmp     loc_14003F2BC
0x14003e8bd  mov     r14d, 2
0x14003e8c3  mov     esi, 4
0x14003e8c8  mov     rax, [rdi+20h]
0x14003e8cc  cmp     rax, 1
0x14003e8d0  jb      loc_14003F2A2
0x14003e8d6  lea     rdx, [rax-1]; ullMultiplier
0x14003e8da  cmp     rdx, rax
0x14003e8dd  jnb     loc_14003F25B
0x14003e8e3  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003e8e7  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003e8ec  mov     [rsp+130h+pullResult], r15
0x14003e8f1  call    ULongLongMult
0x14003e8f6  test    eax, eax
0x14003e8f8  js      loc_14003F25B
0x14003e8fe  mov     rbx, [rsp+130h+pullResult]
0x14003e903  add     rbx, [rdi+38h]
0x14003e907  cmp     rbx, [rdi+38h]
0x14003e90b  jb      loc_14003F25B
0x14003e911  test    rbx, rbx
0x14003e914  jz      loc_14003F25B
0x14003e91a  cmp     [rbx+18h], r15
0x14003e91e  jnz     loc_14003EB70
0x14003e924  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x14003e92b  mov     r8d, 9C7h
0x14003e931  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14003e938  mov     ecx, 1
0x14003e93d  call    AslLogCallPrintf
0x14003e942  mov     rax, [rdi+20h]
0x14003e946  cmp     rax, 1
0x14003e94a  jnb     short loc_14003E956
0x14003e94c  mov     ebx, 8000001Ah
0x14003e951  jmp     loc_14003EB53
0x14003e956  lea     rdx, [rax-1]; ullMultiplier
0x14003e95a  cmp     rdx, rax
0x14003e95d  jnb     loc_14003EB30
0x14003e963  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003e967  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003e96c  mov     [rsp+130h+pullResult], r15
0x14003e971  call    ULongLongMult
0x14003e976  test    eax, eax
0x14003e978  js      loc_14003EB30
0x14003e97e  mov     rdx, [rsp+130h+pullResult]
0x14003e983  add     rdx, [rdi+38h]
0x14003e987  cmp     rdx, [rdi+38h]
0x14003e98b  jb      loc_14003EB30
0x14003e991  test    rdx, rdx
0x14003e994  jz      loc_14003EB30
0x14003e99a  mov     rcx, rdx
0x14003e99d  call    AslpPathWildcardFreeMatchNode
0x14003e9a2  mov     r10, [rdi+20h]
0x14003e9a6  lea     r9, [r10-1]
0x14003e9aa  cmp     r9, r10
0x14003e9ad  jnb     loc_14003E8C8
0x14003e9b3  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003e9b7  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003e9bc  mov     rdx, r9; ullMultiplier
0x14003e9bf  mov     [rsp+130h+pullResult], r15
0x14003e9c4  call    ULongLongMult
0x14003e9c9  test    eax, eax
0x14003e9cb  js      loc_14003E8C8
0x14003e9d1  mov     rsi, [rsp+130h+pullResult]
0x14003e9d6  add     rsi, [rdi+38h]
0x14003e9da  cmp     rsi, [rdi+38h]
0x14003e9de  jb      loc_14003E8C3
0x14003e9e4  mov     rbx, [rdi+20h]
0x14003e9e8  not     r9
0x14003e9eb  add     rbx, r9
0x14003e9ee  mov     [rsp+130h+Size], rbx
0x14003e9f3  jz      short loc_14003EA4F
0x14003e9f5  mov     rdx, [rdi+18h]; ullMultiplier
0x14003e9f9  lea     r8, [rsp+130h+Size]; pullResult
0x14003e9fe  mov     rcx, rbx; ullMultiplicand
0x14003ea01  call    ULongLongMult
0x14003ea06  test    eax, eax
0x14003ea08  js      loc_14003E8C3
0x14003ea0e  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003ea12  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003ea17  mov     rdx, r10; ullMultiplier
0x14003ea1a  mov     [rsp+130h+pullResult], r15
0x14003ea1f  call    ULongLongMult
0x14003ea24  test    eax, eax
0x14003ea26  js      loc_14003E8C3
0x14003ea2c  mov     rdx, [rsp+130h+pullResult]
0x14003ea31  add     rdx, [rdi+38h]; Src
0x14003ea35  cmp     rdx, [rdi+38h]
0x14003ea39  jb      loc_14003E8C3
0x14003ea3f  mov     rbx, [rsp+130h+Size]
0x14003ea44  mov     r8, rbx; Size
0x14003ea47  mov     rcx, rsi; void *
0x14003ea4a  call    memmove_0
0x14003ea4f  mov     r8, [rdi+18h]; Size
0x14003ea53  lea     rcx, [rsi+rbx]; void *
0x14003ea57  xor     edx, edx; Val
0x14003ea59  call    memset_0
0x14003ea5e  dec     qword ptr [rdi+20h]
0x14003ea62  mov     esi, 4
0x14003ea67  cmp     qword ptr [rdi+20h], 10h
0x14003ea6c  jbe     loc_14003E8C8
0x14003ea72  mov     rsi, [rdi+28h]
0x14003ea76  mov     rdx, [rdi+18h]; ullMultiplier
0x14003ea7a  mov     rax, rsi
0x14003ea7d  imul    rax, rdx
0x14003ea81  cmp     rax, 400h
0x14003ea87  jb      loc_14003E8C3
0x14003ea8d  mov     rax, rsi
0x14003ea90  shr     rax, 2
0x14003ea94  cmp     [rdi+20h], rax
0x14003ea98  jnb     loc_14003E8C3
0x14003ea9e  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003eaa3  mov     [rsp+130h+Size], r15
0x14003eaa8  mov     rcx, rsi; ullMultiplicand
0x14003eaab  call    ULongLongMult
0x14003eab0  test    eax, eax
0x14003eab2  js      loc_14003E8C3
0x14003eab8  mov     rdx, [rdi+18h]; ullMultiplier
0x14003eabc  lea     r8, [rsp+130h+Size]; pullResult
0x14003eac1  shr     rsi, 1
0x14003eac4  mov     rcx, rsi; ullMultiplicand
0x14003eac7  call    ULongLongMult
0x14003eacc  test    eax, eax
0x14003eace  js      loc_14003E8C3
0x14003ead4  mov     r8, [rdi+38h]; Ptr
0x14003ead8  xor     edx, edx; Flags
0x14003eada  mov     r14, [rsp+130h+Size]
0x14003eadf  mov     rcx, [rdi+10h]; Heap
0x14003eae3  test    r8, r8
0x14003eae6  jnz     short loc_14003EB08
0x14003eae8  mov     r8, r14; Size
0x14003eaeb  call    cs:__imp_RtlAllocateHeap
0x14003eaf1  mov     rbx, rax
0x14003eaf4  test    rax, rax
0x14003eaf7  jz      short loc_14003EB14
0x14003eaf9  mov     r8, r14; Size
0x14003eafc  xor     edx, edx; Val
0x14003eafe  mov     rcx, rax; void *
0x14003eb01  call    memset_0
0x14003eb06  jmp     short loc_14003EB14
0x14003eb08  mov     r9, r14; Size
0x14003eb0b  call    cs:__imp_RtlReAllocateHeap
0x14003eb11  mov     rbx, rax
0x14003eb14  mov     r14d, 2
0x14003eb1a  test    rbx, rbx
0x14003eb1d  jz      loc_14003E8C3
0x14003eb23  mov     [rdi+38h], rbx
0x14003eb27  mov     [rdi+28h], rsi
0x14003eb2b  jmp     loc_14003E8C3
0x14003eb30  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x14003eb37  mov     r8d, 81Fh
0x14003eb3d  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x14003eb44  mov     ecx, 1
0x14003eb49  mov     ebx, 0C00000E5h
0x14003eb4e  call    AslLogCallPrintf
0x14003eb53  mov     dword ptr [rsp+130h+IoStatusBlock], ebx
0x14003eb57  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x14003eb5e  mov     r8d, 83Ah
0x14003eb64  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x14003eb6b  jmp     loc_14003EF0A
0x14003eb70  mov     rdx, [rbx+10h]; SourceString
0x14003eb74  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14003eb79  call    cs:__imp_RtlInitUnicodeString
0x14003eb7f  mov     rcx, [rbx+18h]; FileHandle
0x14003eb83  lea     rax, [rsp+130h+DestinationString]
0x14003eb88  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x14003eb8d  xor     r9d, r9d; ApcContext
0x14003eb90  mov     [rsp+130h+FileName], rax; FileName
0x14003eb95  xor     r8d, r8d; ApcRoutine
0x14003eb98  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14003eb9d  lea     rax, [rbp+30h+var_78]
0x14003eba1  mov     [rsp+130h+FileInformationClass], 3; FileInformationClass
0x14003eba9  xor     edx, edx; Event
0x14003ebab  mov     [rsp+130h+Length], 268h; Length
0x14003ebb3  mov     [rsp+130h+FileInformation], r13; FileInformation
0x14003ebb8  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14003ebbd  call    cs:__imp_ZwQueryDirectoryFile
0x14003ebc3  test    eax, eax
0x14003ebc5  jns     loc_14003ED2E
0x14003ebcb  cmp     eax, 80000006h
0x14003ebd0  jz      short loc_14003EC29
0x14003ebd2  cmp     eax, 0C000000Fh
0x14003ebd7  jz      short loc_14003EC29
0x14003ebd9  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x14003ebe0  mov     dword ptr [rsp+130h+IoStatusBlock], eax
0x14003ebe4  mov     r8d, 9DFh
0x14003ebea  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14003ebf1  mov     ecx, 1
0x14003ebf6  call    AslLogCallPrintf
0x14003ebfb  mov     rax, [rbp+30h+DestinationString.Buffer]
0x14003ebff  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x14003ec06  mov     [rsp+130h+FileInformation], rax
0x14003ec0b  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14003ec12  mov     rax, [rbx+8]
0x14003ec16  mov     r8d, 9E0h
0x14003ec1c  mov     ecx, r14d
0x14003ec1f  mov     [rsp+130h+IoStatusBlock], rax
0x14003ec24  call    AslLogCallPrintf
0x14003ec29  mov     rax, [rdi+20h]
0x14003ec2d  cmp     rax, 1
0x14003ec31  jb      loc_14003E94C
0x14003ec37  lea     rdx, [rax-1]; ullMultiplier
0x14003ec3b  cmp     rdx, rax
0x14003ec3e  jnb     loc_14003EB30
0x14003ec44  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003ec48  lea     r8, [rsp+130h+Size]; pullResult
0x14003ec4d  mov     [rsp+130h+Size], r15
0x14003ec52  call    ULongLongMult
0x14003ec57  test    eax, eax
0x14003ec59  js      loc_14003EB30
0x14003ec5f  mov     rdx, [rsp+130h+Size]
0x14003ec64  add     rdx, [rdi+38h]
0x14003ec68  cmp     rdx, [rdi+38h]
0x14003ec6c  jb      loc_14003EB30
0x14003ec72  test    rdx, rdx
0x14003ec75  jz      loc_14003EB30
0x14003ec7b  mov     rcx, rdx
0x14003ec7e  call    AslpPathWildcardFreeMatchNode
0x14003ec83  mov     r10, [rdi+20h]
0x14003ec87  lea     r9, [r10-1]
0x14003ec8b  cmp     r9, r10
0x14003ec8e  jnb     loc_14003E8C8
0x14003ec94  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003ec98  lea     r8, [rsp+130h+Size]; pullResult
0x14003ec9d  mov     rdx, r9; ullMultiplier
0x14003eca0  mov     [rsp+130h+Size], r15
0x14003eca5  call    ULongLongMult
0x14003ecaa  test    eax, eax
0x14003ecac  js      loc_14003E8C8
0x14003ecb2  mov     rsi, [rsp+130h+Size]
0x14003ecb7  add     rsi, [rdi+38h]
0x14003ecbb  cmp     rsi, [rdi+38h]
0x14003ecbf  jb      loc_14003E8C3
0x14003ecc5  mov     rbx, [rdi+20h]
0x14003ecc9  not     r9
0x14003eccc  add     rbx, r9
0x14003eccf  mov     [rsp+130h+pullResult], rbx
0x14003ecd4  jz      loc_14003EA4F
0x14003ecda  mov     rdx, [rdi+18h]; ullMultiplier
0x14003ecde  lea     r8, [rsp+130h+pullResult]; pullResult
0x14003ece3  mov     rcx, rbx; ullMultiplicand
0x14003ece6  call    ULongLongMult
0x14003eceb  test    eax, eax
0x14003eced  js      loc_14003E8C3
0x14003ecf3  mov     rcx, [rdi+18h]; ullMultiplicand
0x14003ecf7  lea     r8, [rsp+130h+Size]; pullResult
0x14003ecfc  mov     rdx, r10; ullMultiplier
0x14003ecff  mov     [rsp+130h+Size], r15
0x14003ed04  call    ULongLongMult
0x14003ed09  test    eax, eax
0x14003ed0b  js      loc_14003E8C3
0x14003ed11  mov     rdx, [rsp+130h+Size]
0x14003ed16  add     rdx, [rdi+38h]
0x14003ed1a  cmp     rdx, [rdi+38h]
  ... truncated ...
```

# AslPathWildcardFindNext

- ea: `0x180023ae0`
- end: `0x1800245c3`
- name: `AslPathWildcardFindNext`
- size: `2787`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180034bb0`
- `0x18004def0`

## callees

- `0x1800056fc`
- `0x18000f114`
- `0x180018f20`
- `0x180023ae0`
- `0x1800245cc`
- `0x180024a14`
- `0x180024a80`
- `0x18002ecb4`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!ZwQueryDirectoryFile` at `0x180023e96`
- `ntdll!ZwQueryDirectoryFile` at `0x180023e96`
- `ntdll!RtlReAllocateHeap` at `0x180023de4`
- `ntdll!RtlReAllocateHeap` at `0x18002410e`
- `ntdll!RtlReAllocateHeap` at `0x180023de4`
- `ntdll!RtlReAllocateHeap` at `0x18002410e`
- `ntdll!RtlInitUnicodeString` at `0x180023e52`
- `ntdll!RtlInitUnicodeString` at `0x180023e52`
- `ntdll!RtlpEnsureBufferSize` at `0x180024292`
- `ntdll!RtlpEnsureBufferSize` at `0x1800242ea`
- `ntdll!RtlpEnsureBufferSize` at `0x180024392`
- `ntdll!RtlpEnsureBufferSize` at `0x180024431`
- `ntdll!RtlpEnsureBufferSize` at `0x180024292`
- `ntdll!RtlpEnsureBufferSize` at `0x1800242ea`
- `ntdll!RtlpEnsureBufferSize` at `0x180024392`
- `ntdll!RtlpEnsureBufferSize` at `0x180024431`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800244b3`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800244b3`
- `ntdll!RtlFreeUnicodeString` at `0x180024586`
- `ntdll!RtlFreeUnicodeString` at `0x180024586`
- `ntdll!RtlAllocateHeap` at `0x180023b89`
- `ntdll!RtlAllocateHeap` at `0x180023dc4`
- `ntdll!RtlAllocateHeap` at `0x1800240ee`
- `ntdll!RtlAllocateHeap` at `0x180023b89`
- `ntdll!RtlAllocateHeap` at `0x180023dc4`
- `ntdll!RtlAllocateHeap` at `0x1800240ee`

## string_xrefs

- `0x180023e30`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180024525`: `AslpPathWildcardPeekNode failed [%x]`
- `0x180023e16`: `AslpPathWildcardPeekNode`
- `0x180024514`: `AslpPathWildcardPeekNode`
- `0x180023e3d`: `AslpPathWildcardPopNode`
- `0x180023c0a`: `AslPathWildcardFindNext`
- `0x180023ec3`: `AslPathWildcardFindNext`
- `0x180023ee4`: `AslPathWildcardFindNext`
- `0x1800241af`: `AslPathWildcardFindNext`
- `0x180024206`: `AslPathWildcardFindNext`
- `0x18002453b`: `AslPathWildcardFindNext`
- `0x180024229`: `AslpPathWildcardPushNode failed [%x]`
- `0x1800244f3`: `RtlStringCbCopyNW failed [%x]`
- `0x180023eb2`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x180023ed8`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x1800241a2`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x1800241f1`: `Failed to compute the path length [%x]`
- `0x1800244c3`: `RtlNtPathNameToDosPathName failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileInformation; // r13
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  unsigned __int64 v10; // rcx
  unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  int v13; // ebx
  ULONGLONG v14; // rcx
  ULONGLONG v15; // rdx
  __int64 v16; // r10
  ULONGLONG v17; // rcx
  __int64 v18; // r9
  char *v19; // rsi
  __int64 v20; // rbx
  __int64 v21; // r9
  ULONGLONG v22; // rbx
  ULONGLONG v23; // r10
  ULONGLONG v24; // rcx
  const void *v25; // rdx
  ULONGLONG v26; // rsi
  ULONGLONG v27; // rdx
  ULONGLONG v28; // rsi
  void *v29; // r8
  size_t v30; // r14
  void *v31; // rcx
  PVOID v32; // rax
  PVOID Heap; // rbx
  NTSTATUS v34; // eax
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  __int64 v39; // r10
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // r8
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
  unsigned __int16 v78; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG Size; // [rsp+68h] [rbp-98h] BYREF
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
  v78 = 0;
  v85 = 0;
  DestinationString = 0;
  v83 = 0;
  v84 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v6 = -1073741801;
    goto LABEL_126;
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
              goto LABEL_125;
            }
            v9 = *(_QWORD *)(a3 + 24);
            v8 = v9 * (v7 - 1);
            Size = 0;
            if ( !is_mul_ok(v9, v7 - 1)
              || (v10 = *(_QWORD *)(a3 + 56), v11 = (unsigned __int16 *)(v10 + v8), v10 + v8 < v10)
              || !v11 )
            {
              AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
              v63 = "AslpPathWildcardPeekNode failed [%x]";
              v64 = 2498;
              v6 = -1073741595;
              goto LABEL_123;
            }
            if ( *((_QWORD *)v11 + 3) )
              break;
            AslLogCallPrintf(1, "AslPathWildcardFindNext", 2503, "Node on the stack with invalid handle.");
            v12 = *(_QWORD *)(a3 + 32);
            if ( !v12 )
              goto LABEL_15;
            v14 = *(_QWORD *)(a3 + 24);
            pullResult = 0;
            if ( ULongLongMult(v14, v12 - 1, &pullResult) < 0 )
              goto LABEL_38;
            v15 = *(_QWORD *)(a3 + 56) + pullResult;
            if ( v15 < *(_QWORD *)(a3 + 56) || !v15 )
              goto LABEL_38;
            AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + pullResult);
            v16 = *(_QWORD *)(a3 + 32);
            if ( v16 )
            {
              v17 = *(_QWORD *)(a3 + 24);
              pullResult = 0;
              if ( ULongLongMult(v17, v16 - 1, &pullResult) >= 0 )
              {
                v19 = (char *)(*(_QWORD *)(a3 + 56) + pullResult);
                if ( (unsigned __int64)v19 >= *(_QWORD *)(a3 + 56) )
                {
                  v20 = *(_QWORD *)(a3 + 32);
                  v21 = ~v18;
                  v44 = v21 + v20 == 0;
                  v22 = v21 + v20;
                  Size = v22;
                  if ( v44 )
                    goto LABEL_27;
                  if ( ULongLongMult(v22, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                  {
                    v24 = *(_QWORD *)(a3 + 24);
                    pullResult = 0;
                    if ( ULongLongMult(v24, v23, &pullResult) >= 0 )
                    {
                      v25 = (const void *)(*(_QWORD *)(a3 + 56) + pullResult);
                      if ( (unsigned __int64)v25 >= *(_QWORD *)(a3 + 56) )
                      {
                        v22 = Size;
                        memmove_0(v19, v25, Size);
                        goto LABEL_27;
                      }
                    }
                  }
                }
              }
            }
          }
          RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v11 + 2));
          v34 = ZwQueryDirectoryFile(
                  *((HANDLE *)v11 + 3),
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
          if ( v34 >= 0 )
            break;
          if ( v34 != -1073741809 && v34 != -2147483642 )
          {
            AslLogCallPrintf(
              1,
              "AslPathWildcardFindNext",
              2527,
              "NtQueryDirectoryFile failed to query next file [%x]",
              v34);
            AslLogCallPrintf(
              2,
              "AslPathWildcardFindNext",
              2528,
              "FilePath: '%ws'  Pattern: '%ws'",
              *((_QWORD *)v11 + 1),
              DestinationString.Buffer);
          }
          v35 = *(_QWORD *)(a3 + 32);
          if ( !v35 )
          {
LABEL_15:
            v13 = -2147483622;
            goto LABEL_39;
          }
          v36 = v35 - 1;
          Size = 0;
          v37 = *(_QWORD *)(a3 + 24) * (v35 - 1);
          if ( is_mul_ok(*(_QWORD *)(a3 + 24), v36)
            && (v38 = *(_QWORD *)(a3 + 56) + v37, v38 >= *(_QWORD *)(a3 + 56))
            && v38 )
          {
            AslpPathWildcardFreeMatchNode(v38);
            v39 = *(_QWORD *)(a3 + 32);
            v40 = v39 - 1;
            if ( v39 )
            {
              Size = 0;
              v41 = *(_QWORD *)(a3 + 24) * v40;
              if ( is_mul_ok(*(_QWORD *)(a3 + 24), v40) )
              {
                v42 = *(_QWORD *)(a3 + 56);
                v19 = (char *)(v41 + v42);
                if ( v41 + v42 >= v42 )
                {
                  v22 = 0;
LABEL_27:
                  memset_0(&v19[v22], 0, *(_QWORD *)(a3 + 24));
                  if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                  {
                    v26 = *(_QWORD *)(a3 + 40);
                    v27 = *(_QWORD *)(a3 + 24);
                    if ( v27 * v26 >= 0x400 && *(_QWORD *)(a3 + 32) < v26 >> 2 )
                    {
                      Size = 0;
                      if ( ULongLongMult(v26, v27, &pullResult) >= 0 )
                      {
                        v28 = v26 >> 1;
                        if ( ULongLongMult(v28, *(_QWORD *)(a3 + 24), &Size) >= 0 )
                        {
                          v29 = *(void **)(a3 + 56);
                          v30 = Size;
                          v31 = *(void **)(a3 + 16);
                          if ( v29 )
                          {
                            Heap = RtlReAllocateHeap(v31, 0, v29, Size);
                          }
                          else
                          {
                            v32 = RtlAllocateHeap(v31, 0, Size);
                            Heap = v32;
                            if ( v32 )
                              memset_0(v32, 0, v30);
                          }
                          if ( Heap )
                          {
                            *(_QWORD *)(a3 + 56) = Heap;
                            *(_QWORD *)(a3 + 40) = v28;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
LABEL_38:
            v13 = -1073741595;
            AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
LABEL_39:
            LODWORD(IoStatusBlock) = v13;
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
                  (_DWORD)v11,
                  *((_QWORD *)v11 + 2),
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
              goto LABEL_79;
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
LABEL_79:
              v59 = v6;
LABEL_85:
              LODWORD(IoStatusBlock) = v59;
              AslLogCallPrintf(
                1,
                "AslPathWildcardFindNext",
                2577,
                "AslpPathWildcardPushNode failed [%x]",
                IoStatusBlock);
              goto LABEL_125;
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
              goto LABEL_79;
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
            goto LABEL_85;
          }
          *v58 = v83;
          v58[1] = v84;
          ++*(_QWORD *)(a3 + 32);
        }
      }
    }
    if ( (int)RtlUShortAdd(*v11, *((unsigned __int16 *)FileInformation + 30), &v78) >= 0
      && (int)RtlUShortAdd(v78, 2, &v78) >= 0 )
    {
      break;
    }
    AslLogCallPrintf(1, "AslPathWildcardFindNext", 2629, "Failed to compute the path length [%x]", -1073741675);
  }
  v60 = 2;
  Path.ByteBuffer.StaticSize = 2;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  v62 = v78 + 2LL;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Size = 2;
  LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
  Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
  *(_DWORD *)&Path.String.Length = 0x20000;
  if ( v62 > 0xFFFE )
  {
    v6 = -1073741562;
    goto LABEL_91;
  }
  if ( v62 > 2 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v62) < 0 )
    {
      v6 = -1073741801;
LABEL_91:
      v63 = "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]";
      v64 = 2638;
LABEL_123:
      LODWORD(IoStatusBlock) = v6;
      AslLogCallPrintf(1, "AslPathWildcardFindNext", v64, v63, IoStatusBlock);
      goto LABEL_125;
    }
    v60 = Path.ByteBuffer.Size;
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  Length = 0;
  Path.String.MaximumLength = v60;
  Path.String.Length = 0;
  v66 = *v11 + 2LL;
  if ( v66 > 0xFFFE )
  {
    v6 = -1073741562;
LABEL_98:
    v63 = "RtlAssignUnicodeStringBuffer failed [%x]";
    v64 = 2648;
    goto LABEL_123;
  }
  if ( v66 > v60 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v66) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_98;
    }
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v11 + 1), *v11);
  Path.String.MaximumLength = *v11 + Path.String.Length + 2;
  Path.String.Length += *v11;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  if ( *(_WORD *)(*((_QWORD *)v11 + 1) + 2 * ((unsigned __int64)*v11 >> 1) - 2) != 92 )
  {
    v67 = Path.String.Length;
    v68 = (unsigned int)Path.String.Length + 2 + 2LL;
    if ( v68 > 0xFFFE )
    {
      v6 = -1073741562;
LABEL_106:
      v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
      v64 = 2655;
      goto LABEL_123;
    }
    if ( v68 > Path.ByteBuffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v68) < 0 )
      {
        v6 = -1073741801;
        goto LABEL_106;
      }
      v67 = Path.String.Length;
    }
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v67 >> 1)] = pszSrc[0];
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
LABEL_114:
    v63 = "RtlAppendUnicodeStringBuffer failed [%x]";
    v64 = 2670;
    goto LABEL_123;
  }
  if ( v72 > Path.ByteBuffer.Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v72) < 0 )
    {
      v6 = -1073741801;
      goto LABEL_114;
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
LABEL_125:
  AslFree(NtCurrentPeb()->ProcessHeap, FileInformation);
LABEL_126:
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
0x180023ae0  mov     [rsp-8+arg_8], rbx
0x180023ae5  mov     [rsp-8+arg_18], rsi
0x180023aea  push    rbp
0x180023aeb  push    rdi
0x180023aec  push    r13
0x180023aee  push    r14
0x180023af0  push    r15
0x180023af2  lea     rbp, [rsp-10h]
0x180023af7  sub     rsp, 110h
0x180023afe  mov     rax, cs:__security_cookie
0x180023b05  xor     rax, rsp
0x180023b08  mov     [rbp+30h+Path.ByteBuffer.ReservedForIMalloc], rax
0x180023b0c  mov     qword ptr [rbp+30h+UnicodeString.Length], rcx
0x180023b10  mov     rdi, r8
0x180023b13  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180023b17  jnz     short loc_180023B23
0x180023b19  mov     eax, 80000006h
0x180023b1e  jmp     loc_18002459B
0x180023b23  xor     r15d, r15d
0x180023b26  test    rcx, rcx
0x180023b29  jnz     short loc_180023B35
0x180023b2b  mov     eax, 0C00000EFh
0x180023b30  jmp     loc_18002459B
0x180023b35  test    rdi, rdi
0x180023b38  jnz     short loc_180023B44
0x180023b3a  mov     eax, 0C00000F1h
0x180023b3f  jmp     loc_18002459B
0x180023b44  xorps   xmm1, xmm1
0x180023b47  mov     [rsp+130h+var_D0], r15w
0x180023b4d  xorps   xmm0, xmm0
0x180023b50  xor     eax, eax
0x180023b52  movups  xmmword ptr [rbp+30h+var_78], xmm0
0x180023b56  mov     [rbp+30h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x180023b5a  mov     r8d, 268h; Size
0x180023b60  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x180023b65  lea     edx, [rax+8]; Flags
0x180023b68  movups  [rbp+30h+var_98], xmm0
0x180023b6c  movups  [rbp+30h+var_88], xmm0
0x180023b70  movups  xmmword ptr [rbp+30h+Path.String.Length], xmm1
0x180023b74  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Buffer], xmm1
0x180023b78  movups  xmmword ptr [rbp+30h+Path.ByteBuffer.Size], xmm1
0x180023b7c  mov     rcx, gs:60h
0x180023b85  mov     rcx, [rcx+30h]; HeapHandle
0x180023b89  call    cs:__imp_RtlAllocateHeap
0x180023b8f  mov     r13, rax
0x180023b92  test    rax, rax
0x180023b95  jnz     short loc_180023BA1
0x180023b97  mov     ebx, 0C0000017h
0x180023b9c  jmp     loc_180024568
0x180023ba1  mov     r14d, 2
0x180023ba7  mov     esi, 4
0x180023bac  mov     rcx, [rdi+20h]
0x180023bb0  cmp     rcx, 1
0x180023bb4  jb      loc_18002454E
0x180023bba  lea     rax, [rcx-1]
0x180023bbe  cmp     rax, rcx
0x180023bc1  jnb     loc_180024507
0x180023bc7  mul     qword ptr [rdi+18h]
0x180023bcb  mov     [rsp+130h+Size], r15
0x180023bd0  test    rdx, rdx
0x180023bd3  jnz     loc_180024507
0x180023bd9  mov     rcx, [rdi+38h]
0x180023bdd  lea     rbx, [rcx+rax]
0x180023be1  cmp     rbx, rcx
0x180023be4  jb      loc_180024507
0x180023bea  test    rbx, rbx
0x180023bed  jz      loc_180024507
0x180023bf3  cmp     [rbx+18h], r15
0x180023bf7  jnz     loc_180023E49
0x180023bfd  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x180023c04  mov     r8d, 9C7h
0x180023c0a  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180023c11  mov     ecx, 1
0x180023c16  call    AslLogCallPrintf
0x180023c1b  mov     rax, [rdi+20h]
0x180023c1f  cmp     rax, 1
0x180023c23  jnb     short loc_180023C2F
0x180023c25  mov     ebx, 8000001Ah
0x180023c2a  jmp     loc_180023E2C
0x180023c2f  lea     rdx, [rax-1]; ullMultiplier
0x180023c33  cmp     rdx, rax
0x180023c36  jnb     loc_180023E09
0x180023c3c  mov     rcx, [rdi+18h]; ullMultiplicand
0x180023c40  lea     r8, [rsp+130h+pullResult]; pullResult
0x180023c45  mov     [rsp+130h+pullResult], r15
0x180023c4a  call    ULongLongMult
0x180023c4f  test    eax, eax
0x180023c51  js      loc_180023E09
0x180023c57  mov     rdx, [rsp+130h+pullResult]
0x180023c5c  add     rdx, [rdi+38h]
0x180023c60  cmp     rdx, [rdi+38h]
0x180023c64  jb      loc_180023E09
0x180023c6a  test    rdx, rdx
0x180023c6d  jz      loc_180023E09
0x180023c73  mov     rcx, rdx
0x180023c76  call    AslpPathWildcardFreeMatchNode
0x180023c7b  mov     r10, [rdi+20h]
0x180023c7f  lea     r9, [r10-1]
0x180023c83  cmp     r9, r10
0x180023c86  jnb     loc_180023BAC
0x180023c8c  mov     rcx, [rdi+18h]; ullMultiplicand
0x180023c90  lea     r8, [rsp+130h+pullResult]; pullResult
0x180023c95  mov     rdx, r9; ullMultiplier
0x180023c98  mov     [rsp+130h+pullResult], r15
0x180023c9d  call    ULongLongMult
0x180023ca2  test    eax, eax
0x180023ca4  js      loc_180023BAC
0x180023caa  mov     rsi, [rsp+130h+pullResult]
0x180023caf  add     rsi, [rdi+38h]
0x180023cb3  cmp     rsi, [rdi+38h]
0x180023cb7  jb      loc_180023BA7
0x180023cbd  mov     rbx, [rdi+20h]
0x180023cc1  not     r9
0x180023cc4  add     rbx, r9
0x180023cc7  mov     [rsp+130h+Size], rbx
0x180023ccc  jz      short loc_180023D28
0x180023cce  mov     rdx, [rdi+18h]; ullMultiplier
0x180023cd2  lea     r8, [rsp+130h+Size]; pullResult
0x180023cd7  mov     rcx, rbx; ullMultiplicand
0x180023cda  call    ULongLongMult
0x180023cdf  test    eax, eax
0x180023ce1  js      loc_180023BA7
0x180023ce7  mov     rcx, [rdi+18h]; ullMultiplicand
0x180023ceb  lea     r8, [rsp+130h+pullResult]; pullResult
0x180023cf0  mov     rdx, r10; ullMultiplier
0x180023cf3  mov     [rsp+130h+pullResult], r15
0x180023cf8  call    ULongLongMult
0x180023cfd  test    eax, eax
0x180023cff  js      loc_180023BA7
0x180023d05  mov     rdx, [rsp+130h+pullResult]
0x180023d0a  add     rdx, [rdi+38h]; Src
0x180023d0e  cmp     rdx, [rdi+38h]
0x180023d12  jb      loc_180023BA7
0x180023d18  mov     rbx, [rsp+130h+Size]
0x180023d1d  mov     r8, rbx; Size
0x180023d20  mov     rcx, rsi; void *
0x180023d23  call    memmove_0
0x180023d28  mov     r8, [rdi+18h]; Size
0x180023d2c  lea     rcx, [rsi+rbx]; void *
0x180023d30  xor     edx, edx; Val
0x180023d32  call    memset_0
0x180023d37  dec     qword ptr [rdi+20h]
0x180023d3b  mov     esi, 4
0x180023d40  cmp     qword ptr [rdi+20h], 10h
0x180023d45  jbe     loc_180023BAC
0x180023d4b  mov     rsi, [rdi+28h]
0x180023d4f  mov     rdx, [rdi+18h]; ullMultiplier
0x180023d53  mov     rax, rsi
0x180023d56  imul    rax, rdx
0x180023d5a  cmp     rax, 400h
0x180023d60  jb      loc_180023BA7
0x180023d66  mov     rax, rsi
0x180023d69  shr     rax, 2
0x180023d6d  cmp     [rdi+20h], rax
0x180023d71  jnb     loc_180023BA7
0x180023d77  lea     r8, [rsp+130h+pullResult]; pullResult
0x180023d7c  mov     [rsp+130h+Size], r15
0x180023d81  mov     rcx, rsi; ullMultiplicand
0x180023d84  call    ULongLongMult
0x180023d89  test    eax, eax
0x180023d8b  js      loc_180023BA7
0x180023d91  mov     rdx, [rdi+18h]; ullMultiplier
0x180023d95  lea     r8, [rsp+130h+Size]; pullResult
0x180023d9a  shr     rsi, 1
0x180023d9d  mov     rcx, rsi; ullMultiplicand
0x180023da0  call    ULongLongMult
0x180023da5  test    eax, eax
0x180023da7  js      loc_180023BA7
0x180023dad  mov     r8, [rdi+38h]; Ptr
0x180023db1  xor     edx, edx; Flags
0x180023db3  mov     r14, [rsp+130h+Size]
0x180023db8  mov     rcx, [rdi+10h]; Heap
0x180023dbc  test    r8, r8
0x180023dbf  jnz     short loc_180023DE1
0x180023dc1  mov     r8, r14; Size
0x180023dc4  call    cs:__imp_RtlAllocateHeap
0x180023dca  mov     rbx, rax
0x180023dcd  test    rax, rax
0x180023dd0  jz      short loc_180023DED
0x180023dd2  mov     r8, r14; Size
0x180023dd5  xor     edx, edx; Val
0x180023dd7  mov     rcx, rax; void *
0x180023dda  call    memset_0
0x180023ddf  jmp     short loc_180023DED
0x180023de1  mov     r9, r14; Size
0x180023de4  call    cs:__imp_RtlReAllocateHeap
0x180023dea  mov     rbx, rax
0x180023ded  mov     r14d, 2
0x180023df3  test    rbx, rbx
0x180023df6  jz      loc_180023BA7
0x180023dfc  mov     [rdi+38h], rbx
0x180023e00  mov     [rdi+28h], rsi
0x180023e04  jmp     loc_180023BA7
0x180023e09  lea     r9, aRtlarraygetFai_0; "RtlArrayGet failed to get the next node"
0x180023e10  mov     r8d, 81Fh
0x180023e16  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x180023e1d  mov     ecx, 1
0x180023e22  mov     ebx, 0C00000E5h
0x180023e27  call    AslLogCallPrintf
0x180023e2c  mov     dword ptr [rsp+130h+IoStatusBlock], ebx
0x180023e30  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x180023e37  mov     r8d, 83Ah
0x180023e3d  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x180023e44  jmp     loc_1800241B6
0x180023e49  mov     rdx, [rbx+10h]; SourceString
0x180023e4d  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180023e52  call    cs:__imp_RtlInitUnicodeString
0x180023e58  mov     rcx, [rbx+18h]; FileHandle
0x180023e5c  lea     rax, [rsp+130h+DestinationString]
0x180023e61  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x180023e66  xor     r9d, r9d; ApcContext
0x180023e69  mov     [rsp+130h+FileName], rax; FileName
0x180023e6e  xor     r8d, r8d; ApcRoutine
0x180023e71  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180023e76  lea     rax, [rbp+30h+var_78]
0x180023e7a  mov     [rsp+130h+FileInformationClass], 3; FileInformationClass
0x180023e82  xor     edx, edx; Event
0x180023e84  mov     [rsp+130h+Length], 268h; Length
0x180023e8c  mov     [rsp+130h+FileInformation], r13; FileInformation
0x180023e91  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x180023e96  call    cs:__imp_ZwQueryDirectoryFile
0x180023e9c  test    eax, eax
0x180023e9e  jns     loc_180023FDA
0x180023ea4  cmp     eax, 0C000000Fh
0x180023ea9  jz      short loc_180023F02
0x180023eab  cmp     eax, 80000006h
0x180023eb0  jz      short loc_180023F02
0x180023eb2  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x180023eb9  mov     dword ptr [rsp+130h+IoStatusBlock], eax
0x180023ebd  mov     r8d, 9DFh
0x180023ec3  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180023eca  mov     ecx, 1
0x180023ecf  call    AslLogCallPrintf
0x180023ed4  mov     rax, [rbp+30h+DestinationString.Buffer]
0x180023ed8  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x180023edf  mov     [rsp+130h+FileInformation], rax
0x180023ee4  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x180023eeb  mov     rax, [rbx+8]
0x180023eef  mov     r8d, 9E0h
0x180023ef5  mov     ecx, r14d
0x180023ef8  mov     [rsp+130h+IoStatusBlock], rax
0x180023efd  call    AslLogCallPrintf
0x180023f02  mov     rax, [rdi+20h]
0x180023f06  cmp     rax, 1
0x180023f0a  jb      loc_180023C25
0x180023f10  lea     rcx, [rax-1]
0x180023f14  cmp     rcx, rax
0x180023f17  jnb     loc_180023E09
0x180023f1d  mov     rax, rcx
0x180023f20  mov     [rsp+130h+Size], r15
0x180023f25  mul     qword ptr [rdi+18h]
0x180023f29  test    rdx, rdx
0x180023f2c  jnz     loc_180023E09
0x180023f32  add     rax, [rdi+38h]
0x180023f36  cmp     rax, [rdi+38h]
0x180023f3a  jb      loc_180023E09
0x180023f40  test    rax, rax
0x180023f43  jz      loc_180023E09
0x180023f49  mov     rcx, rax
0x180023f4c  call    AslpPathWildcardFreeMatchNode
0x180023f51  mov     r10, [rdi+20h]
0x180023f55  mov     r9, r10
0x180023f58  lea     rcx, [r10-1]
0x180023f5c  cmp     rcx, r10
0x180023f5f  jnb     loc_180023BAC
0x180023f65  mov     rax, rcx
0x180023f68  mov     [rsp+130h+Size], r15
0x180023f6d  mul     qword ptr [rdi+18h]
0x180023f71  test    rdx, rdx
0x180023f74  jnz     loc_180023BAC
0x180023f7a  mov     r8, [rdi+38h]
0x180023f7e  lea     rsi, [rax+r8]
0x180023f82  cmp     rsi, r8
0x180023f85  jb      loc_180023BA7
0x180023f8b  not     rcx
0x180023f8e  lea     rbx, [rcx+r10]
0x180023f92  test    rbx, rbx
0x180023f95  jz      loc_180023D28
0x180023f9b  mov     rax, [rdi+18h]
0x180023f9f  mul     rbx
0x180023fa2  mov     [rsp+130h+Size], r15
0x180023fa7  mov     rbx, rax
0x180023faa  test    rdx, rdx
0x180023fad  jnz     loc_180023BA7
0x180023fb3  mov     rax, r10
0x180023fb6  mov     [rsp+130h+Size], r15
0x180023fbb  mul     qword ptr [rdi+18h]
0x180023fbf  test    rdx, rdx
0x180023fc2  jnz     loc_180023BA7
0x180023fc8  lea     rdx, [rax+r8]
0x180023fcc  cmp     rdx, r8
0x180023fcf  jb      loc_180023BA7
0x180023fd5  jmp     loc_180023D1D
0x180023fda  cmp     [r13+3Ch], esi
0x180023fde  lea     rsi, [r13+5Eh]
0x180023fe2  jnz     short loc_180023FF2
0x180023fe4  cmp     word ptr [rsi], 2Eh ; '.'
0x180023fe8  jnz     short loc_180024006
0x180023fea  cmp     word ptr [r13+60h], 2Eh ; '.'
0x180023ff0  jmp     short loc_180024000
  ... truncated ...
```

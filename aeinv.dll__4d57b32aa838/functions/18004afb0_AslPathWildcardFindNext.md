# AslPathWildcardFindNext

- ea: `0x18004afb0`
- end: `0x18004ba94`
- name: `AslPathWildcardFindNext`
- size: `2788`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18006c020`
- `0x180121230`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x1800303b0`
- `0x18004afb0`
- `0x18004ba9c`
- `0x180059920`
- `0x18005a8bc`
- `0x18006f9ec`
- `0x18006fd6c`
- `0x1800701fc`
- `0x18012549c`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x18004b769`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b7c1`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b869`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b906`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b769`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b7c1`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b869`
- `ntdll!RtlpEnsureBufferSize` at `0x18004b906`
- `ntdll!RtlFreeUnicodeString` at `0x18004ba58`
- `ntdll!RtlFreeUnicodeString` at `0x18004ba58`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18004b986`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18004b986`
- `ntdll!ZwQueryDirectoryFile` at `0x18004b357`
- `ntdll!ZwQueryDirectoryFile` at `0x18004b357`
- `ntdll!RtlAllocateHeap` at `0x18004b054`
- `ntdll!RtlAllocateHeap` at `0x18004b054`
- `ntdll!RtlInitUnicodeString` at `0x18004b314`
- `ntdll!RtlInitUnicodeString` at `0x18004b314`
- `KERNEL32!HeapReAlloc` at `0x18004b2a7`
- `KERNEL32!HeapReAlloc` at `0x18004b5ec`
- `KERNEL32!HeapReAlloc` at `0x18004b2a7`
- `KERNEL32!HeapReAlloc` at `0x18004b5ec`
- `KERNEL32!HeapAlloc` at `0x18004b287`
- `KERNEL32!HeapAlloc` at `0x18004b5cc`
- `KERNEL32!HeapAlloc` at `0x18004b287`
- `KERNEL32!HeapAlloc` at `0x18004b5cc`

## string_xrefs

- `0x18004b2f3`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18004b9f7`: `AslpPathWildcardPeekNode failed [%x]`
- `0x18004b2d9`: `AslpPathWildcardPeekNode`
- `0x18004b9e6`: `AslpPathWildcardPeekNode`
- `0x18004b0dd`: `AslPathWildcardFindNext`
- `0x18004b384`: `AslPathWildcardFindNext`
- `0x18004b3a5`: `AslPathWildcardFindNext`
- `0x18004b68a`: `AslPathWildcardFindNext`
- `0x18004b6de`: `AslPathWildcardFindNext`
- `0x18004ba0d`: `AslPathWildcardFindNext`
- `0x18004b300`: `AslpPathWildcardPopNode`
- `0x18004b701`: `AslpPathWildcardPushNode failed [%x]`
- `0x18004b9c5`: `RtlStringCbCopyNW failed [%x]`
- `0x18004b373`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x18004b399`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x18004b67d`: `AslpPathWildcardAllocMatchNode failed [%x]`
- `0x18004b6c9`: `Failed to compute the path length [%x]`
- `0x18004b996`: `RtlNtPathNameToDosPathName failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileInformation; // r13
  NTSTATUS v7; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // r10
  unsigned __int64 v15; // rcx
  __int64 v16; // r9
  char *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r9
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r10
  unsigned __int64 v22; // rcx
  const void *v23; // rdx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rsi
  void *v27; // r8
  size_t v28; // r14
  void *v29; // rcx
  void *v30; // rax
  LPVOID v31; // rbx
  const char *v32; // r9
  int v33; // r8d
  const char *v34; // rdx
  NTSTATUS v35; // eax
  __int64 v36; // rax
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  __int64 v39; // r10
  unsigned __int64 v40; // rcx
  __int64 v41; // r9
  __int64 v42; // rbx
  __int64 v43; // r9
  unsigned __int64 v44; // r10
  unsigned __int64 v45; // rcx
  PWSTR Buffer; // rsi
  bool v47; // zf
  int matched; // eax
  unsigned __int64 v49; // r15
  __int64 v50; // r14
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rcx
  __int64 v53; // r9
  unsigned __int64 v54; // r14
  void *v55; // r8
  size_t v56; // rsi
  void *v57; // rcx
  void *v58; // rax
  LPVOID v59; // rbx
  unsigned __int64 v60; // rcx
  _OWORD *v61; // rdx
  const char *v62; // r9
  int v63; // r8d
  SIZE_T v64; // rdx
  WCHAR *p_ReservedForAllocatedSize; // rcx
  SIZE_T v66; // r8
  USHORT Length; // r9
  SIZE_T v68; // r8
  USHORT v69; // cx
  unsigned __int64 v70; // r8
  USHORT v71; // ax
  USHORT v72; // r9
  USHORT v73; // dx
  unsigned __int64 v74; // r8
  unsigned __int64 v75; // rdx
  PUCHAR StaticBuffer; // rcx
  unsigned __int16 v77; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int64 v78; // [rsp+68h] [rbp-71h] BYREF
  struct _UNICODE_STRING Size; // [rsp+70h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-59h] BYREF
  __int128 v81; // [rsp+90h] [rbp-49h] BYREF
  __int128 v82; // [rsp+A0h] [rbp-39h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-29h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+C0h] [rbp-19h] BYREF

  if ( a3 == -1 )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v77 = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  v81 = 0;
  v82 = 0;
  memset(&Path, 0, 56);
  FileInformation = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x268u);
  if ( !FileInformation )
  {
    v7 = -1073741801;
    goto LABEL_131;
  }
  while ( 1 )
  {
    v8 = *(_QWORD *)(a3 + 32);
    if ( !v8 )
      break;
    v9 = *(_QWORD *)(a3 + 24);
    v78 = 0;
    if ( (int)ULongLongMult(v9, v8 - 1, &v78) < 0
      || (v10 = (unsigned __int16 *)(*(_QWORD *)(a3 + 56) + v78), (unsigned __int64)v10 < *(_QWORD *)(a3 + 56))
      || !v10 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardPeekNode",
        2079,
        (unsigned int)"RtlArrayGet failed to get the next node");
      v62 = "AslpPathWildcardPeekNode failed [%x]";
      v63 = 2498;
      v7 = -1073741595;
      goto LABEL_128;
    }
    if ( *((_QWORD *)v10 + 3) )
    {
      RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v10 + 2));
      v35 = ZwQueryDirectoryFile(
              *((HANDLE *)v10 + 3),
              0,
              0,
              0,
              &IoStatusBlock,
              FileInformation,
              0x268u,
              FileBothDirectoryInformation,
              1u,
              &DestinationString,
              0);
      if ( v35 >= 0 )
      {
        Buffer = (PWSTR)(FileInformation + 94);
        if ( *((_DWORD *)FileInformation + 15) == 4 )
        {
          if ( *Buffer != 46 )
            goto LABEL_63;
          v47 = *((_WORD *)FileInformation + 48) == 46;
LABEL_62:
          if ( !v47 )
            goto LABEL_63;
        }
        else
        {
          if ( *((_DWORD *)FileInformation + 15) == 2 )
          {
            Buffer = (PWSTR)(FileInformation + 94);
            v47 = *((_WORD *)FileInformation + 47) == 46;
            goto LABEL_62;
          }
LABEL_63:
          matched = AslpPathWildcardAllocMatchNode(
                      (unsigned int)&v81,
                      (_DWORD)v10,
                      *((_QWORD *)v10 + 2),
                      (*((_DWORD *)FileInformation + 14) >> 4) & 1,
                      (__int64)Buffer,
                      *((_WORD *)FileInformation + 30));
          if ( matched == -1073741197 )
          {
            if ( (int)RtlUShortAdd(*v10, *((unsigned __int16 *)FileInformation + 30), &v77) >= 0
              && (int)RtlUShortAdd(v77, 2, &v77) >= 0 )
            {
              v64 = 2;
              Path.ByteBuffer.StaticSize = 2;
              Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
              p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
              v66 = v77 + 2LL;
              Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
              Path.ByteBuffer.Size = 2;
              LOWORD(Path.ByteBuffer.ReservedForAllocatedSize) = 0;
              Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
              *(_DWORD *)&Path.String.Length = 0x20000;
              if ( v66 > 0xFFFE )
              {
                v7 = -1073741562;
LABEL_96:
                v62 = "RtlEnsureUnicodeStringBufferSizeBytes failed [%x]";
                v63 = 2638;
                goto LABEL_128;
              }
              if ( v66 > 2 )
              {
                if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v66) < 0 )
                {
                  v7 = -1073741801;
                  goto LABEL_96;
                }
                v64 = Path.ByteBuffer.Size;
                p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
              }
              Path.String.Buffer = p_ReservedForAllocatedSize;
              Length = 0;
              Path.String.MaximumLength = v64;
              Path.String.Length = 0;
              v68 = *v10 + 2LL;
              if ( v68 > 0xFFFE )
              {
                v7 = -1073741562;
LABEL_103:
                v62 = "RtlAssignUnicodeStringBuffer failed [%x]";
                v63 = 2648;
                goto LABEL_128;
              }
              if ( v68 > v64 )
              {
                if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v68) < 0 )
                {
                  v7 = -1073741801;
                  goto LABEL_103;
                }
                p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
                Length = Path.String.Length;
              }
              Path.String.Buffer = p_ReservedForAllocatedSize;
              memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], *((const void **)v10 + 1), *v10);
              Path.String.MaximumLength = *v10 + Path.String.Length + 2;
              Path.String.Length += *v10;
              Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
              if ( *(_WORD *)(*((_QWORD *)v10 + 1) + 2 * ((unsigned __int64)*v10 >> 1) - 2) != 92 )
              {
                v69 = Path.String.Length;
                v70 = (unsigned int)Path.String.Length + 2 + 2LL;
                if ( v70 > 0xFFFE )
                {
                  v7 = -1073741562;
LABEL_111:
                  v62 = "RtlAppendUnicodeStringBuffer failed [%x]";
                  v63 = 2655;
                  goto LABEL_128;
                }
                if ( v70 > Path.ByteBuffer.Size )
                {
                  if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v70) < 0 )
                  {
                    v7 = -1073741801;
                    goto LABEL_111;
                  }
                  v69 = Path.String.Length;
                }
                Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
                *(_WORD *)&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v69 >> 1)] = SubBlock[0];
                v71 = Path.String.Length + 4;
                Path.String.Length += 2;
                Path.String.MaximumLength = v71;
                Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
              }
              v72 = Path.String.Length;
              DestinationString.Buffer = Buffer;
              DestinationString.Length = *((_WORD *)FileInformation + 30);
              v73 = DestinationString.Length;
              DestinationString.MaximumLength = *((_WORD *)FileInformation + 30);
              v74 = Path.String.Length + (unsigned int)DestinationString.Length + 2LL;
              if ( v74 > 0xFFFE )
              {
                v7 = -1073741562;
LABEL_119:
                v62 = "RtlAppendUnicodeStringBuffer failed [%x]";
                v63 = 2670;
                goto LABEL_128;
              }
              if ( v74 > Path.ByteBuffer.Size )
              {
                if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v74) < 0 )
                {
                  v7 = -1073741801;
                  goto LABEL_119;
                }
                Buffer = DestinationString.Buffer;
                v73 = DestinationString.Length;
                v72 = Path.String.Length;
              }
              Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
              memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v72 >> 1)], Buffer, v73);
              v75 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
              Path.String.Length = v75;
              Path.String.MaximumLength = v75 + 2;
              Path.String.Buffer[v75 >> 1] = 0;
              if ( *(_DWORD *)a3 && (v7 = RtlNtPathNameToDosPathName(0, &Path, 0, 0), v7 < 0) )
              {
                v62 = "RtlNtPathNameToDosPathName failed [%x]";
                v63 = 2681;
              }
              else
              {
                v7 = RtlStringCbCopyNW(a1, 520, Path.String.Buffer, Path.String.Length);
                if ( v7 >= 0 )
                {
                  v7 = 0;
                  goto LABEL_130;
                }
                v62 = "RtlStringCbCopyNW failed [%x]";
                v63 = 2692;
              }
              goto LABEL_128;
            }
            AslLogCallPrintf(
              1,
              (unsigned int)"AslPathWildcardFindNext",
              2629,
              (unsigned int)"Failed to compute the path length [%x]");
          }
          else if ( matched != -1073741565 && matched != -1073741638 )
          {
            if ( matched < 0 )
            {
              v32 = "AslpPathWildcardAllocMatchNode failed [%x]";
              v33 = 2585;
              v34 = "AslPathWildcardFindNext";
LABEL_85:
              AslLogCallPrintf(1, (_DWORD)v34, v33, (_DWORD)v32);
            }
            else
            {
              v49 = *(_QWORD *)(a3 + 32);
              if ( v49 >= *(_QWORD *)(a3 + 40) )
              {
                if ( v49 + 1 <= *(_QWORD *)(a3 + 40) )
                {
                  v7 = -2147024809;
                  goto LABEL_90;
                }
                v50 = *(_QWORD *)(a3 + 48) - 1LL;
                if ( *(_QWORD *)(a3 + 48) + v49 < v49 + 1
                  || (v51 = *(_QWORD *)(a3 + 24),
                      v52 = *(_QWORD *)(a3 + 40),
                      *(_QWORD *)&Size.Length = 0,
                      (int)ULongLongMult(v52, v51, &v78) < 0)
                  || (v54 = v53 & ~v50,
                      (int)ULongLongMult(v54, *(_QWORD *)(a3 + 24), (unsigned __int64 *)&Size.Length) < 0) )
                {
                  v7 = -2147483637;
                  goto LABEL_90;
                }
                v55 = *(void **)(a3 + 56);
                v56 = *(_QWORD *)&Size.Length;
                v57 = *(void **)(a3 + 16);
                if ( v55 )
                {
                  v59 = HeapReAlloc(v57, 0, v55, *(SIZE_T *)&Size.Length);
                }
                else
                {
                  v58 = HeapAlloc(v57, 0, *(SIZE_T *)&Size.Length);
                  v59 = v58;
                  if ( v58 )
                    memset_0(v58, 0, v56);
                }
                if ( !v59 )
                {
                  v7 = -2147024882;
                  goto LABEL_90;
                }
                *(_QWORD *)(a3 + 40) = v54;
                *(_QWORD *)(a3 + 56) = v59;
              }
              v60 = *(_QWORD *)(a3 + 24);
              *(_QWORD *)&Size.Length = 0;
              if ( (int)ULongLongMult(v60, v49, (unsigned __int64 *)&Size.Length) < 0
                || (v61 = (_OWORD *)(*(_QWORD *)(a3 + 56) + *(_QWORD *)&Size.Length),
                    (unsigned __int64)v61 < *(_QWORD *)(a3 + 56)) )
              {
                v7 = -2147483637;
LABEL_90:
                v62 = "AslpPathWildcardPushNode failed [%x]";
                v63 = 2577;
LABEL_128:
                AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindNext", v63, (_DWORD)v62);
                goto LABEL_130;
              }
              *v61 = v81;
              v61[1] = v82;
              ++*(_QWORD *)(a3 + 32);
            }
          }
        }
      }
      else
      {
        if ( v35 != -2147483642 && v35 != -1073741809 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindNext",
            2527,
            (unsigned int)"NtQueryDirectoryFile failed to query next file [%x]");
          AslLogCallPrintf(
            2,
            (unsigned int)"AslPathWildcardFindNext",
            2528,
            (unsigned int)"FilePath: '%ws'  Pattern: '%ws'");
        }
        v36 = *(_QWORD *)(a3 + 32);
        if ( !v36 )
          goto LABEL_40;
        v37 = *(_QWORD *)(a3 + 24);
        *(_QWORD *)&Size.Length = 0;
        if ( (int)ULongLongMult(v37, v36 - 1, (unsigned __int64 *)&Size.Length) < 0 )
          goto LABEL_39;
        v38 = *(_QWORD *)(a3 + 56) + *(_QWORD *)&Size.Length;
        if ( v38 < *(_QWORD *)(a3 + 56) || !v38 )
          goto LABEL_39;
        AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + *(_QWORD *)&Size.Length);
        v39 = *(_QWORD *)(a3 + 32);
        if ( v39 )
        {
          v40 = *(_QWORD *)(a3 + 24);
          *(_QWORD *)&Size.Length = 0;
          if ( (int)ULongLongMult(v40, v39 - 1, (unsigned __int64 *)&Size.Length) >= 0 )
          {
            v17 = (char *)(*(_QWORD *)(a3 + 56) + *(_QWORD *)&Size.Length);
            if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
            {
              v42 = *(_QWORD *)(a3 + 32);
              v43 = ~v41;
              v47 = v43 + v42 == 0;
              v20 = v43 + v42;
              v78 = v20;
              if ( v47 )
              {
LABEL_28:
                memset_0(&v17[v20], 0, *(_QWORD *)(a3 + 24));
                if ( --*(_QWORD *)(a3 + 32) > 0x10u )
                {
                  v24 = *(_QWORD *)(a3 + 40);
                  v25 = *(_QWORD *)(a3 + 24);
                  if ( v25 * v24 >= 0x400 && *(_QWORD *)(a3 + 32) < v24 >> 2 )
                  {
                    *(_QWORD *)&Size.Length = 0;
                    if ( (int)ULongLongMult(v24, v25, &v78) >= 0 )
                    {
                      v26 = v24 >> 1;
                      if ( (int)ULongLongMult(v26, *(_QWORD *)(a3 + 24), (unsigned __int64 *)&Size.Length) >= 0 )
                      {
                        v27 = *(void **)(a3 + 56);
                        v28 = *(_QWORD *)&Size.Length;
                        v29 = *(void **)(a3 + 16);
                        if ( v27 )
                        {
                          v31 = HeapReAlloc(v29, 0, v27, *(SIZE_T *)&Size.Length);
                        }
                        else
                        {
                          v30 = HeapAlloc(v29, 0, *(SIZE_T *)&Size.Length);
                          v31 = v30;
                          if ( v30 )
                            memset_0(v30, 0, v28);
                        }
                        if ( v31 )
                        {
                          *(_QWORD *)(a3 + 56) = v31;
                          *(_QWORD *)(a3 + 40) = v26;
                        }
                      }
                    }
                  }
                }
              }
              else if ( (int)ULongLongMult(v20, *(_QWORD *)(a3 + 24), &v78) >= 0 )
              {
                v45 = *(_QWORD *)(a3 + 24);
                *(_QWORD *)&Size.Length = 0;
                if ( (int)ULongLongMult(v45, v44, (unsigned __int64 *)&Size.Length) >= 0 )
                {
                  v23 = (const void *)(*(_QWORD *)(a3 + 56) + *(_QWORD *)&Size.Length);
                  if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                  {
                    v20 = v78;
                    goto LABEL_27;
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
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindNext",
        2503,
        (unsigned int)"Node on the stack with invalid handle.");
      v11 = *(_QWORD *)(a3 + 32);
      if ( !v11 )
        goto LABEL_40;
      v12 = *(_QWORD *)(a3 + 24);
      v78 = 0;
      if ( (int)ULongLongMult(v12, v11 - 1, &v78) < 0
        || (v13 = *(_QWORD *)(a3 + 56) + v78, v13 < *(_QWORD *)(a3 + 56))
        || !v13 )
      {
LABEL_39:
        AslLogCallPrintf(
          1,
          (unsigned int)"AslpPathWildcardPeekNode",
          2079,
          (unsigned int)"RtlArrayGet failed to get the next node");
LABEL_40:
        v32 = "AslpPathWildcardPeekNode failed [%x]";
        v33 = 2106;
        v34 = "AslpPathWildcardPopNode";
        goto LABEL_85;
      }
      AslpPathWildcardFreeMatchNode(*(_QWORD *)(a3 + 56) + v78);
      v14 = *(_QWORD *)(a3 + 32);
      if ( v14 )
      {
        v15 = *(_QWORD *)(a3 + 24);
        v78 = 0;
        if ( (int)ULongLongMult(v15, v14 - 1, &v78) >= 0 )
        {
          v17 = (char *)(*(_QWORD *)(a3 + 56) + v78);
          if ( (unsigned __int64)v17 >= *(_QWORD *)(a3 + 56) )
          {
            v18 = *(_QWORD *)(a3 + 32);
            v19 = ~v16;
            v47 = v19 + v18 == 0;
            v20 = v19 + v18;
            *(_QWORD *)&Size.Length = v20;
            if ( v47 )
              goto LABEL_28;
            if ( (int)ULongLongMult(v20, *(_QWORD *)(a3 + 24), (unsigned __int64 *)&Size.Length) >= 0 )
            {
              v22 = *(_QWORD *)(a3 + 24);
              v78 = 0;
              if ( (int)ULongLongMult(v22, v21, &v78) >= 0 )
              {
                v23 = (const void *)(*(_QWORD *)(a3 + 56) + v78);
                if ( (unsigned __int64)v23 >= *(_QWORD *)(a3 + 56) )
                {
                  v20 = *(_QWORD *)&Size.Length;
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
  }
  v7 = -2147483642;
LABEL_130:
  AslFree(NtCurrentPeb()->ProcessHeap, FileInformation);
LABEL_131:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer && Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
  {
    *(_QWORD *)&Size.Length = 0;
    Size.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    RtlFreeUnicodeString(&Size);
    StaticBuffer = Path.ByteBuffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004afb0  mov     [rsp-8+arg_8], rbx
0x18004afb5  push    rbp
0x18004afb6  push    rsi
0x18004afb7  push    rdi
0x18004afb8  push    r12
0x18004afba  push    r13
0x18004afbc  push    r14
0x18004afbe  push    r15
0x18004afc0  lea     rbp, [rsp-27h]
0x18004afc5  sub     rsp, 100h
0x18004afcc  mov     rax, cs:__security_cookie
0x18004afd3  xor     rax, rsp
0x18004afd6  mov     [rbp+57h+Path.ByteBuffer.ReservedForIMalloc], rax
0x18004afda  mov     rdi, r8
0x18004afdd  mov     r12, rcx
0x18004afe0  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18004afe4  jnz     short loc_18004AFF0
0x18004afe6  mov     eax, 80000006h
0x18004afeb  jmp     loc_18004BA6D
0x18004aff0  xor     r15d, r15d
0x18004aff3  test    r12, r12
0x18004aff6  jnz     short loc_18004B002
0x18004aff8  mov     eax, 0C00000EFh
0x18004affd  jmp     loc_18004BA6D
0x18004b002  test    rdi, rdi
0x18004b005  jnz     short loc_18004B011
0x18004b007  mov     eax, 0C00000F1h
0x18004b00c  jmp     loc_18004BA6D
0x18004b011  xorps   xmm1, xmm1
0x18004b014  mov     [rbp+57h+var_D0], r15w
0x18004b019  xorps   xmm0, xmm0
0x18004b01c  xor     eax, eax
0x18004b01e  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18004b022  mov     [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x18004b026  mov     r8d, 268h; Size
0x18004b02c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18004b030  lea     edx, [rax+8]; Flags
0x18004b033  movups  [rbp+57h+var_A0], xmm0
0x18004b037  movups  [rbp+57h+var_90], xmm0
0x18004b03b  movups  xmmword ptr [rbp+57h+Path.String.Length], xmm1
0x18004b03f  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer], xmm1
0x18004b043  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size], xmm1
0x18004b047  mov     rcx, gs:60h
0x18004b050  mov     rcx, [rcx+30h]; HeapHandle
0x18004b054  call    cs:__imp_RtlAllocateHeap
0x18004b05a  mov     r13, rax
0x18004b05d  test    rax, rax
0x18004b060  jnz     short loc_18004B06C
0x18004b062  mov     ebx, 0C0000017h
0x18004b067  jmp     loc_18004BA3A
0x18004b06c  mov     r14d, 2
0x18004b072  mov     esi, 4
0x18004b077  mov     rax, [rdi+20h]
0x18004b07b  cmp     rax, 1
0x18004b07f  jb      loc_18004BA20
0x18004b085  lea     rdx, [rax-1]; unsigned __int64
0x18004b089  cmp     rdx, rax
0x18004b08c  jnb     loc_18004B9D9
0x18004b092  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b096  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b09a  mov     [rbp+57h+var_C8], r15
0x18004b09e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b0a3  test    eax, eax
0x18004b0a5  js      loc_18004B9D9
0x18004b0ab  mov     rbx, [rbp+57h+var_C8]
0x18004b0af  add     rbx, [rdi+38h]
0x18004b0b3  cmp     rbx, [rdi+38h]
0x18004b0b7  jb      loc_18004B9D9
0x18004b0bd  test    rbx, rbx
0x18004b0c0  jz      loc_18004B9D9
0x18004b0c6  cmp     [rbx+18h], r15
0x18004b0ca  jnz     loc_18004B30C
0x18004b0d0  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x18004b0d7  mov     r8d, 9C7h
0x18004b0dd  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18004b0e4  mov     ecx, 1
0x18004b0e9  call    AslLogCallPrintf
0x18004b0ee  mov     rax, [rdi+20h]
0x18004b0f2  cmp     rax, 1
0x18004b0f6  jnb     short loc_18004B102
0x18004b0f8  mov     ebx, 8000001Ah
0x18004b0fd  jmp     loc_18004B2EF
0x18004b102  lea     rdx, [rax-1]; unsigned __int64
0x18004b106  cmp     rdx, rax
0x18004b109  jnb     loc_18004B2CC
0x18004b10f  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b113  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b117  mov     [rbp+57h+var_C8], r15
0x18004b11b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b120  test    eax, eax
0x18004b122  js      loc_18004B2CC
0x18004b128  mov     rdx, [rbp+57h+var_C8]
0x18004b12c  add     rdx, [rdi+38h]
0x18004b130  cmp     rdx, [rdi+38h]
0x18004b134  jb      loc_18004B2CC
0x18004b13a  test    rdx, rdx
0x18004b13d  jz      loc_18004B2CC
0x18004b143  mov     rcx, rdx
0x18004b146  call    AslpPathWildcardFreeMatchNode
0x18004b14b  mov     r10, [rdi+20h]
0x18004b14f  lea     r9, [r10-1]
0x18004b153  cmp     r9, r10
0x18004b156  jnb     loc_18004B077
0x18004b15c  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b160  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b164  mov     rdx, r9; unsigned __int64
0x18004b167  mov     [rbp+57h+var_C8], r15
0x18004b16b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b170  test    eax, eax
0x18004b172  js      loc_18004B077
0x18004b178  mov     rsi, [rbp+57h+var_C8]
0x18004b17c  add     rsi, [rdi+38h]
0x18004b180  cmp     rsi, [rdi+38h]
0x18004b184  jb      loc_18004B072
0x18004b18a  mov     rbx, [rdi+20h]
0x18004b18e  not     r9
0x18004b191  add     rbx, r9
0x18004b194  mov     [rbp+57h+Size], rbx
0x18004b198  jz      short loc_18004B1EF
0x18004b19a  mov     rdx, [rdi+18h]; unsigned __int64
0x18004b19e  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x18004b1a2  mov     rcx, rbx; unsigned __int64
0x18004b1a5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b1aa  test    eax, eax
0x18004b1ac  js      loc_18004B072
0x18004b1b2  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b1b6  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b1ba  mov     rdx, r10; unsigned __int64
0x18004b1bd  mov     [rbp+57h+var_C8], r15
0x18004b1c1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b1c6  test    eax, eax
0x18004b1c8  js      loc_18004B072
0x18004b1ce  mov     rdx, [rbp+57h+var_C8]
0x18004b1d2  add     rdx, [rdi+38h]; Src
0x18004b1d6  cmp     rdx, [rdi+38h]
0x18004b1da  jb      loc_18004B072
0x18004b1e0  mov     rbx, [rbp+57h+Size]
0x18004b1e4  mov     r8, rbx; Size
0x18004b1e7  mov     rcx, rsi; void *
0x18004b1ea  call    memmove_0
0x18004b1ef  mov     r8, [rdi+18h]; Size
0x18004b1f3  lea     rcx, [rsi+rbx]; void *
0x18004b1f7  xor     edx, edx; Val
0x18004b1f9  call    memset_0
0x18004b1fe  dec     qword ptr [rdi+20h]
0x18004b202  mov     esi, 4
0x18004b207  cmp     qword ptr [rdi+20h], 10h
0x18004b20c  jbe     loc_18004B077
0x18004b212  mov     rsi, [rdi+28h]
0x18004b216  mov     rdx, [rdi+18h]; unsigned __int64
0x18004b21a  mov     rax, rsi
0x18004b21d  imul    rax, rdx
0x18004b221  cmp     rax, 400h
0x18004b227  jb      loc_18004B072
0x18004b22d  mov     rax, rsi
0x18004b230  shr     rax, 2
0x18004b234  cmp     [rdi+20h], rax
0x18004b238  jnb     loc_18004B072
0x18004b23e  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b242  mov     [rbp+57h+Size], r15
0x18004b246  mov     rcx, rsi; unsigned __int64
0x18004b249  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b24e  test    eax, eax
0x18004b250  js      loc_18004B072
0x18004b256  mov     rdx, [rdi+18h]; unsigned __int64
0x18004b25a  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x18004b25e  shr     rsi, 1
0x18004b261  mov     rcx, rsi; unsigned __int64
0x18004b264  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b269  test    eax, eax
0x18004b26b  js      loc_18004B072
0x18004b271  mov     r8, [rdi+38h]; lpMem
0x18004b275  xor     edx, edx; dwFlags
0x18004b277  mov     r14, [rbp+57h+Size]
0x18004b27b  mov     rcx, [rdi+10h]; hHeap
0x18004b27f  test    r8, r8
0x18004b282  jnz     short loc_18004B2A4
0x18004b284  mov     r8, r14; dwBytes
0x18004b287  call    cs:__imp_HeapAlloc
0x18004b28d  mov     rbx, rax
0x18004b290  test    rax, rax
0x18004b293  jz      short loc_18004B2B0
0x18004b295  mov     r8, r14; Size
0x18004b298  xor     edx, edx; Val
0x18004b29a  mov     rcx, rax; void *
0x18004b29d  call    memset_0
0x18004b2a2  jmp     short loc_18004B2B0
0x18004b2a4  mov     r9, r14; dwBytes
0x18004b2a7  call    cs:__imp_HeapReAlloc
0x18004b2ad  mov     rbx, rax
0x18004b2b0  mov     r14d, 2
0x18004b2b6  test    rbx, rbx
0x18004b2b9  jz      loc_18004B072
0x18004b2bf  mov     [rdi+38h], rbx
0x18004b2c3  mov     [rdi+28h], rsi
0x18004b2c7  jmp     loc_18004B072
0x18004b2cc  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x18004b2d3  mov     r8d, 81Fh
0x18004b2d9  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x18004b2e0  mov     ecx, 1
0x18004b2e5  mov     ebx, 0C00000E5h
0x18004b2ea  call    AslLogCallPrintf
0x18004b2ef  mov     dword ptr [rsp+130h+IoStatusBlock], ebx
0x18004b2f3  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x18004b2fa  mov     r8d, 83Ah
0x18004b300  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x18004b307  jmp     loc_18004B691
0x18004b30c  mov     rdx, [rbx+10h]; SourceString
0x18004b310  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004b314  call    cs:__imp_RtlInitUnicodeString
0x18004b31a  mov     rcx, [rbx+18h]; FileHandle
0x18004b31e  lea     rax, [rbp+57h+DestinationString]
0x18004b322  mov     [rsp+130h+RestartScan], r15b; RestartScan
0x18004b327  xor     r9d, r9d; ApcContext
0x18004b32a  mov     [rsp+130h+FileName], rax; FileName
0x18004b32f  xor     r8d, r8d; ApcRoutine
0x18004b332  mov     [rsp+130h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18004b337  lea     rax, [rbp+57h+var_80]
0x18004b33b  mov     [rsp+130h+FileInformationClass], 3; FileInformationClass
0x18004b343  xor     edx, edx; Event
0x18004b345  mov     [rsp+130h+Length], 268h; Length
0x18004b34d  mov     [rsp+130h+FileInformation], r13; FileInformation
0x18004b352  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x18004b357  call    cs:__imp_ZwQueryDirectoryFile
0x18004b35d  test    eax, eax
0x18004b35f  jns     loc_18004B4BC
0x18004b365  cmp     eax, 80000006h
0x18004b36a  jz      short loc_18004B3C3
0x18004b36c  cmp     eax, 0C000000Fh
0x18004b371  jz      short loc_18004B3C3
0x18004b373  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x18004b37a  mov     dword ptr [rsp+130h+IoStatusBlock], eax
0x18004b37e  mov     r8d, 9DFh
0x18004b384  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18004b38b  mov     ecx, 1
0x18004b390  call    AslLogCallPrintf
0x18004b395  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18004b399  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x18004b3a0  mov     [rsp+130h+FileInformation], rax
0x18004b3a5  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x18004b3ac  mov     rax, [rbx+8]
0x18004b3b0  mov     r8d, 9E0h
0x18004b3b6  mov     ecx, r14d
0x18004b3b9  mov     [rsp+130h+IoStatusBlock], rax
0x18004b3be  call    AslLogCallPrintf
0x18004b3c3  mov     rax, [rdi+20h]
0x18004b3c7  cmp     rax, 1
0x18004b3cb  jb      loc_18004B0F8
0x18004b3d1  lea     rdx, [rax-1]; unsigned __int64
0x18004b3d5  cmp     rdx, rax
0x18004b3d8  jnb     loc_18004B2CC
0x18004b3de  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b3e2  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x18004b3e6  mov     [rbp+57h+Size], r15
0x18004b3ea  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b3ef  test    eax, eax
0x18004b3f1  js      loc_18004B2CC
0x18004b3f7  mov     rdx, [rbp+57h+Size]
0x18004b3fb  add     rdx, [rdi+38h]
0x18004b3ff  cmp     rdx, [rdi+38h]
0x18004b403  jb      loc_18004B2CC
0x18004b409  test    rdx, rdx
0x18004b40c  jz      loc_18004B2CC
0x18004b412  mov     rcx, rdx
0x18004b415  call    AslpPathWildcardFreeMatchNode
0x18004b41a  mov     r10, [rdi+20h]
0x18004b41e  lea     r9, [r10-1]
0x18004b422  cmp     r9, r10
0x18004b425  jnb     loc_18004B077
0x18004b42b  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b42f  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x18004b433  mov     rdx, r9; unsigned __int64
0x18004b436  mov     [rbp+57h+Size], r15
0x18004b43a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b43f  test    eax, eax
0x18004b441  js      loc_18004B077
0x18004b447  mov     rsi, [rbp+57h+Size]
0x18004b44b  add     rsi, [rdi+38h]
0x18004b44f  cmp     rsi, [rdi+38h]
0x18004b453  jb      loc_18004B072
0x18004b459  mov     rbx, [rdi+20h]
0x18004b45d  not     r9
0x18004b460  add     rbx, r9
0x18004b463  mov     [rbp+57h+var_C8], rbx
0x18004b467  jz      loc_18004B1EF
0x18004b46d  mov     rdx, [rdi+18h]; unsigned __int64
0x18004b471  lea     r8, [rbp+57h+var_C8]; unsigned __int64 *
0x18004b475  mov     rcx, rbx; unsigned __int64
0x18004b478  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b47d  test    eax, eax
0x18004b47f  js      loc_18004B072
0x18004b485  mov     rcx, [rdi+18h]; unsigned __int64
0x18004b489  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x18004b48d  mov     rdx, r10; unsigned __int64
0x18004b490  mov     [rbp+57h+Size], r15
0x18004b494  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004b499  test    eax, eax
0x18004b49b  js      loc_18004B072
0x18004b4a1  mov     rdx, [rbp+57h+Size]
0x18004b4a5  add     rdx, [rdi+38h]
  ... truncated ...
```

# WcRemoveFilesInDirectoryInternal

- ea: `0x18000d8f4`
- end: `0x18000dc98`
- name: `WcRemoveFilesInDirectoryInternal`
- size: `932`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18000d80c`
- `0x18000d8f4`

## callees

- `0x180002140`
- `0x180002c48`
- `0x18000d8f4`
- `0x18000dca0`
- `0x18000e014`
- `0x18000e320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db13`
- `ntdll!RtlAllocateHeap` at `0x18000d961`
- `ntdll!RtlAllocateHeap` at `0x18000d961`
- `ntdll!RtlFreeHeap` at `0x18000dc59`
- `ntdll!RtlFreeHeap` at `0x18000dc59`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000dbe8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000dc25`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000dbe8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000dc25`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000dbce`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000dbce`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000da93`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000da93`

## pseudocode

```c
__int64 __fastcall WcRemoveFilesInDirectoryInternal(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  WCHAR *Heap; // r14
  signed int v8; // ebx
  unsigned __int64 v9; // rsi
  _WORD *v10; // rdi
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  unsigned __int64 v13; // rdx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  int v16; // ebx
  HANDLE i; // rax
  __int64 v18; // r9
  void *v19; // r15
  __int64 v20; // rcx
  WCHAR *cFileName; // r8
  unsigned __int64 v22; // rdx
  _WORD *v23; // rax
  _WORD *v24; // rcx
  signed int LastError; // eax
  int v26; // eax
  __int64 v27; // r9
  int v28; // eax
  unsigned __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v31; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v31 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v30 = 0;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10000u);
  if ( !Heap )
    return (unsigned int)-2147024882;
  v8 = WciEnsureLongPath(Heap, v6, a1, &v31, &v30);
  if ( v8 >= 0 )
  {
    v9 = v30;
    v10 = v31;
    if ( v30 )
    {
      if ( v30 > 0x7FFFFFFF )
      {
        v8 = -2147024809;
        *v31 = 0;
        goto LABEL_52;
      }
      v11 = 2147483646;
      v12 = L"*.*";
      v13 = v30;
      v14 = v31;
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v11;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      v8 = v13 == 0 ? 0x8007007A : 0;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( !v13 )
        goto LABEL_52;
      v16 = 0;
      for ( i = FindFirstFileExW(Heap, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
            ;
            i = FindFirstFileExW(Heap, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u) )
      {
        v19 = i;
        if ( i != (HANDLE)-1LL )
          break;
        if ( GetLastError() != 5 || v16 )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_48:
          if ( v19 != (void *)-1LL && !FindClose(v19) )
            __int2c();
          goto LABEL_52;
        }
        *v10 = 0;
        v8 = WcpTakeOwnership(Heap);
        if ( v8 < 0 )
          goto LABEL_48;
        v16 = 1;
        *v10 = 42;
      }
      while ( 1 )
      {
        if ( v9 )
        {
          if ( v9 > 0x7FFFFFFF )
          {
            *v10 = 0;
            v8 = -2147024809;
            goto LABEL_48;
          }
          v20 = 2147483646;
          cFileName = FindFileData.cFileName;
          v22 = v9;
          v23 = v10;
          do
          {
            if ( !v20 )
              break;
            v18 = *cFileName;
            if ( !(_WORD)v18 )
              break;
            *v23 = v18;
            ++cFileName;
            ++v23;
            --v20;
            --v22;
          }
          while ( v22 );
          v24 = v23 - 1;
          if ( v22 )
            v24 = v23;
          v8 = v22 == 0 ? 0x8007007A : 0;
          *v24 = 0;
        }
        else
        {
          v8 = -2147024809;
        }
        if ( v8 < 0 )
          goto LABEL_48;
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          goto LABEL_43;
        if ( *(_DWORD *)FindFileData.cFileName != 46
          && (*(_DWORD *)FindFileData.cFileName != 3014702 || FindFileData.cFileName[2]) )
        {
          break;
        }
LABEL_45:
        if ( !FindNextFileW(v19, &FindFileData) )
        {
          FindClose(v19);
          *(v10 - 1) = 0;
          v8 = WcpRemoveFile((__int64)Heap, a2, a3, v27, 0);
          goto LABEL_52;
        }
      }
      if ( (FindFileData.dwFileAttributes & 0x400) == 0
        || FindFileData.dwReserved0 == -2147483624
        || FindFileData.dwReserved0 == -1879044072
        || FindFileData.dwReserved0 == -1610612697
        || FindFileData.dwReserved0 == -1610608601 )
      {
        v26 = WcRemoveFilesInDirectoryInternal(Heap, a2, a3, 1);
      }
      else
      {
LABEL_43:
        v26 = WcpRemoveFile((__int64)Heap, a2, a3, v18, 0);
      }
      v8 = v26;
      if ( v26 < 0 )
        goto LABEL_48;
      goto LABEL_45;
    }
    v8 = -2147024809;
  }
LABEL_52:
  LOBYTE(v28) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( !v28 )
    __int2c();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d8f4  mov     [rsp-8+arg_18], rbx
0x18000d8f9  push    rbp
0x18000d8fa  push    rsi
0x18000d8fb  push    rdi
0x18000d8fc  push    r12
0x18000d8fe  push    r13
0x18000d900  push    r14
0x18000d902  push    r15
0x18000d904  lea     rbp, [rsp-1A0h]
0x18000d90c  sub     rsp, 2A0h
0x18000d913  mov     rax, cs:__security_cookie
0x18000d91a  xor     rax, rsp
0x18000d91d  mov     [rbp+1D0h+var_40], rax
0x18000d924  mov     r13, r8
0x18000d927  mov     r12, rdx
0x18000d92a  mov     rbx, rcx
0x18000d92d  xor     r15d, r15d
0x18000d930  xor     edx, edx; Val
0x18000d932  mov     [rsp+2D0h+var_298], r15
0x18000d937  mov     r8d, 250h; Size
0x18000d93d  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x18000d942  call    memset_0
0x18000d947  mov     rcx, gs:60h
0x18000d950  xor     edx, edx; Flags
0x18000d952  mov     r8d, 10000h; Size
0x18000d958  mov     [rsp+2D0h+var_2A0], r15
0x18000d95d  mov     rcx, [rcx+30h]; HeapHandle
0x18000d961  call    cs:__imp_RtlAllocateHeap
0x18000d968  nop     dword ptr [rax+rax+00h]
0x18000d96d  mov     r14, rax
0x18000d970  test    rax, rax
0x18000d973  jnz     short loc_18000D97F
0x18000d975  mov     ebx, 8007000Eh
0x18000d97a  jmp     loc_18000DC6B
0x18000d97f  lea     rax, [rsp+2D0h+var_2A0]
0x18000d984  mov     r8, rbx
0x18000d987  lea     r9, [rsp+2D0h+var_298]
0x18000d98c  mov     [rsp+2D0h+lpSearchFilter], rax
0x18000d991  mov     rcx, r14
0x18000d994  call    WciEnsureLongPath
0x18000d999  mov     ebx, eax
0x18000d99b  test    eax, eax
0x18000d99d  js      loc_18000DC47
0x18000d9a3  mov     rsi, [rsp+2D0h+var_2A0]
0x18000d9a8  mov     rdi, [rsp+2D0h+var_298]
0x18000d9ad  test    rsi, rsi
0x18000d9b0  jz      loc_18000DC39
0x18000d9b6  cmp     rsi, 7FFFFFFFh
0x18000d9bd  jbe     short loc_18000D9C9
0x18000d9bf  mov     ebx, 80070057h
0x18000d9c4  jmp     loc_18000DC43
0x18000d9c9  mov     eax, 7FFFFFFEh
0x18000d9ce  lea     rcx, asc_18003FC48; "*.*"
0x18000d9d5  mov     rdx, rsi
0x18000d9d8  mov     r8, rdi
0x18000d9db  test    rax, rax
0x18000d9de  jz      short loc_18000D9FF
0x18000d9e0  movzx   r9d, word ptr [rcx]
0x18000d9e4  test    r9w, r9w
0x18000d9e8  jz      short loc_18000D9FF
0x18000d9ea  mov     [r8], r9w
0x18000d9ee  add     rcx, 2
0x18000d9f2  add     r8, 2
0x18000d9f6  dec     rax
0x18000d9f9  sub     rdx, 1
0x18000d9fd  jnz     short loc_18000D9DB
0x18000d9ff  mov     rax, rdx
0x18000da02  lea     rcx, [r8-2]
0x18000da06  neg     rax
0x18000da09  sbb     ebx, ebx
0x18000da0b  not     ebx
0x18000da0d  and     ebx, 8007007Ah
0x18000da13  test    rdx, rdx
0x18000da16  cmovnz  rcx, r8
0x18000da1a  mov     [rcx], r15w
0x18000da1e  jz      loc_18000DC47
0x18000da24  mov     [rsp+2D0h+dwAdditionalFlags], 2
0x18000da2c  mov     ebx, r15d
0x18000da2f  mov     [rsp+2D0h+lpSearchFilter], r15
0x18000da34  mov     edx, 1
0x18000da39  jmp     short loc_18000DA88
0x18000da3b  call    cs:__imp_GetLastError
0x18000da42  nop     dword ptr [rax+rax+00h]
0x18000da47  cmp     eax, 5
0x18000da4a  jnz     loc_18000DB13
0x18000da50  xor     eax, eax
0x18000da52  test    ebx, ebx
0x18000da54  jnz     loc_18000DB13
0x18000da5a  mov     rcx, r14; pObjectName
0x18000da5d  mov     [rdi], ax
0x18000da60  call    WcpTakeOwnership
0x18000da65  xor     ecx, ecx
0x18000da67  mov     ebx, eax
0x18000da69  test    eax, eax
0x18000da6b  js      loc_18000DC1C
0x18000da71  lea     ebx, [rcx+1]
0x18000da74  mov     [rsp+2D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x18000da7c  mov     edx, ebx; fInfoLevelId
0x18000da7e  mov     word ptr [rdi], 2Ah ; '*'
0x18000da83  mov     [rsp+2D0h+lpSearchFilter], rcx; lpSearchFilter
0x18000da88  xor     r9d, r9d; fSearchOp
0x18000da8b  lea     r8, [rsp+2D0h+FindFileData]; lpFindFileData
0x18000da90  mov     rcx, r14; lpFileName
0x18000da93  call    cs:__imp_FindFirstFileExW
0x18000da9a  nop     dword ptr [rax+rax+00h]
0x18000da9f  mov     r15, rax
0x18000daa2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000daa6  jz      short loc_18000DA3B
0x18000daa8  xor     r10d, r10d
0x18000daab  test    rsi, rsi
0x18000daae  jz      loc_18000DB37
0x18000dab4  cmp     rsi, 7FFFFFFFh
0x18000dabb  ja      loc_18000DC13
0x18000dac1  mov     ecx, 7FFFFFFEh
0x18000dac6  lea     r8, [rsp+2D0h+var_264]
0x18000dacb  mov     rdx, rsi
0x18000dace  mov     rax, rdi
0x18000dad1  test    rcx, rcx
0x18000dad4  jz      short loc_18000DAF5
0x18000dad6  movzx   r9d, word ptr [r8]
0x18000dada  test    r9w, r9w
0x18000dade  jz      short loc_18000DAF5
0x18000dae0  mov     [rax], r9w
0x18000dae4  add     r8, 2
0x18000dae8  add     rax, 2
0x18000daec  dec     rcx
0x18000daef  sub     rdx, 1
0x18000daf3  jnz     short loc_18000DAD1
0x18000daf5  test    rdx, rdx
0x18000daf8  lea     rcx, [rax-2]
0x18000dafc  cmovnz  rcx, rax
0x18000db00  neg     rdx
0x18000db03  sbb     ebx, ebx
0x18000db05  not     ebx
0x18000db07  and     ebx, 8007007Ah
0x18000db0d  mov     [rcx], r10w
0x18000db11  jmp     short loc_18000DB45
0x18000db13  call    cs:__imp_GetLastError
0x18000db1a  nop     dword ptr [rax+rax+00h]
0x18000db1f  mov     ebx, eax
0x18000db21  test    eax, eax
0x18000db23  jle     loc_18000DC1C
0x18000db29  movzx   ebx, ax
0x18000db2c  or      ebx, 80070000h
0x18000db32  jmp     loc_18000DC1C
0x18000db37  mov     ebx, 80070057h
0x18000db3c  test    rsi, rsi
0x18000db3f  jnz     loc_18000DC13
0x18000db45  test    ebx, ebx
0x18000db47  js      loc_18000DC1C
0x18000db4d  test    byte ptr [rsp+2D0h+FindFileData], 10h
0x18000db52  jz      short loc_18000DBAD
0x18000db54  cmp     [rsp+2D0h+var_264], 2Eh ; '.'
0x18000db59  jz      short loc_18000DBC6
0x18000db5b  cmp     [rsp+2D0h+var_264], 2E002Eh
0x18000db63  jnz     short loc_18000DB6D
0x18000db65  cmp     [rsp+2D0h+var_260], r10w
0x18000db6b  jz      short loc_18000DBC6
0x18000db6d  test    [rsp+2D0h+FindFileData], 400h
0x18000db75  jz      short loc_18000DB97
0x18000db77  mov     eax, [rsp+2D0h+var_26C]
0x18000db7b  cmp     eax, 80000018h
0x18000db80  jz      short loc_18000DB97
0x18000db82  cmp     eax, 90001018h
0x18000db87  jz      short loc_18000DB97
0x18000db89  cmp     eax, 0A0000027h
0x18000db8e  jz      short loc_18000DB97
0x18000db90  cmp     eax, 0A0001027h
0x18000db95  jnz     short loc_18000DBAD
0x18000db97  mov     r9d, 1
0x18000db9d  mov     r8, r13
0x18000dba0  mov     rdx, r12
0x18000dba3  mov     rcx, r14
0x18000dba6  call    WcRemoveFilesInDirectoryInternal
0x18000dbab  jmp     short loc_18000DBC0
0x18000dbad  mov     r8, r13
0x18000dbb0  mov     byte ptr [rsp+2D0h+lpSearchFilter], r10b
0x18000dbb5  mov     rdx, r12
0x18000dbb8  mov     rcx, r14
0x18000dbbb  call    WcpRemoveFile
0x18000dbc0  mov     ebx, eax
0x18000dbc2  test    eax, eax
0x18000dbc4  js      short loc_18000DC1C
0x18000dbc6  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x18000dbcb  mov     rcx, r15; hFindFile
0x18000dbce  call    cs:__imp_FindNextFileW
0x18000dbd5  nop     dword ptr [rax+rax+00h]
0x18000dbda  xor     r10d, r10d
0x18000dbdd  test    eax, eax
0x18000dbdf  jnz     loc_18000DAAB
0x18000dbe5  mov     rcx, r15; hFindFile
0x18000dbe8  call    cs:__imp_FindClose
0x18000dbef  nop     dword ptr [rax+rax+00h]
0x18000dbf4  xor     r15d, r15d
0x18000dbf7  mov     r8, r13
0x18000dbfa  mov     rdx, r12
0x18000dbfd  mov     [rdi-2], r15w
0x18000dc02  mov     rcx, r14
0x18000dc05  mov     byte ptr [rsp+2D0h+lpSearchFilter], r15b
0x18000dc0a  call    WcpRemoveFile
0x18000dc0f  mov     ebx, eax
0x18000dc11  jmp     short loc_18000DC47
0x18000dc13  mov     [rdi], r10w
0x18000dc17  mov     ebx, 80070057h
0x18000dc1c  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000dc20  jz      short loc_18000DC47
0x18000dc22  mov     rcx, r15; hFindFile
0x18000dc25  call    cs:__imp_FindClose
0x18000dc2c  nop     dword ptr [rax+rax+00h]
0x18000dc31  test    eax, eax
0x18000dc33  jnz     short loc_18000DC47
0x18000dc35  int     2Ch; Windows NT - assertion failure
0x18000dc37  jmp     short loc_18000DC47
0x18000dc39  mov     ebx, 80070057h
0x18000dc3e  test    rsi, rsi
0x18000dc41  jz      short loc_18000DC47
0x18000dc43  mov     [rdi], r15w
0x18000dc47  mov     rcx, gs:60h
0x18000dc50  mov     r8, r14; P
0x18000dc53  xor     edx, edx; Flags
0x18000dc55  mov     rcx, [rcx+30h]; HeapHandle
0x18000dc59  call    cs:__imp_RtlFreeHeap
0x18000dc60  nop     dword ptr [rax+rax+00h]
0x18000dc65  test    eax, eax
0x18000dc67  jnz     short loc_18000DC6B
0x18000dc69  int     2Ch; Windows NT - assertion failure
0x18000dc6b  mov     eax, ebx
0x18000dc6d  mov     rcx, [rbp+1D0h+var_40]
0x18000dc74  xor     rcx, rsp; StackCookie
0x18000dc77  call    __security_check_cookie
0x18000dc7c  mov     rbx, [rsp+2D0h+arg_18]
0x18000dc84  add     rsp, 2A0h
0x18000dc8b  pop     r15
0x18000dc8d  pop     r14
0x18000dc8f  pop     r13
0x18000dc91  pop     r12
0x18000dc93  pop     rdi
0x18000dc94  pop     rsi
0x18000dc95  pop     rbp
0x18000dc96  retn
```

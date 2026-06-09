# BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(ushort const *,ushort const *,void *)

- ea: `0x180022f88`
- end: `0x18002310a`
- name: `?CopyConfigFileTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBG0PEAX@Z`
- size: `386`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180023208`
- `0x1800253fc`

## callees

- `0x180001fb0`
- `0x180022f88`
- `0x1800235dc`
- `0x180024de8`
- `0x180033bc4`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230b2`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CopyFileTransactedW` at `0x1800230a8`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CopyFileTransactedW` at `0x1800230a8`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::CopyConfigFileTransacted(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        void *a3)
{
  signed int PathCanonicalizationProof; // ebx
  int DirectoryTreeTransacted; // eax
  signed int LastError; // eax
  _QWORD v9[4]; // [rsp+40h] [rbp-69h] BYREF
  LPCWSTR lpNewFileName; // [rsp+60h] [rbp-49h]
  int v11; // [rsp+68h] [rbp-41h]
  __int16 v12; // [rsp+6Ch] [rbp-3Dh]
  int v13; // [rsp+70h] [rbp-39h]
  _QWORD v14[4]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int16 *v15; // [rsp+98h] [rbp-11h]
  int v16; // [rsp+A0h] [rbp-9h]
  __int16 v17; // [rsp+A4h] [rbp-5h]
  int v18; // [rsp+A8h] [rbp-1h]
  _QWORD v19[4]; // [rsp+B0h] [rbp+7h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+D0h] [rbp+27h]
  int v21; // [rsp+D8h] [rbp+2Fh]
  __int16 v22; // [rsp+DCh] [rbp+33h]
  int v23; // [rsp+E0h] [rbp+37h]

  v19[0] = 0;
  lpExistingFileName = (LPCWSTR)v19;
  lpNewFileName = (LPCWSTR)v9;
  v22 = 256;
  v21 = 32;
  v15 = (unsigned __int16 *)v14;
  v23 = 0;
  v9[0] = 0;
  v11 = 32;
  v12 = 256;
  v13 = 0;
  v14[0] = 0;
  v16 = 32;
  v17 = 256;
  v18 = 0;
  if ( !a1 || !a2 || a3 == (void *)-1LL )
  {
    PathCanonicalizationProof = 87;
    goto LABEL_14;
  }
  PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v19);
  if ( PathCanonicalizationProof >= 0 )
  {
    PathCanonicalizationProof = MakePathCanonicalizationProof(a2, (struct STRU *)v9);
    if ( PathCanonicalizationProof >= 0 )
    {
      PathCanonicalizationProof = BACKUP_FILE_SYSTEM_HELPER::GetParentPath(lpNewFileName, (struct STRU *)v14);
      if ( PathCanonicalizationProof >= 0 )
      {
        DirectoryTreeTransacted = BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(v15, a3);
        PathCanonicalizationProof = DirectoryTreeTransacted;
        if ( DirectoryTreeTransacted < 0 )
        {
          if ( DirectoryTreeTransacted != -2147024713 )
            goto LABEL_14;
          PathCanonicalizationProof = 0;
        }
        if ( !CopyFileTransactedW(lpExistingFileName, lpNewFileName, 0, 0, 0, 0, a3) )
        {
          LastError = GetLastError();
          PathCanonicalizationProof = LastError;
          if ( LastError > 0 )
            PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
LABEL_14:
  BUFFER::~BUFFER((BUFFER *)v14);
  BUFFER::~BUFFER((BUFFER *)v9);
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180022f88  mov     [rsp-8+arg_18], rbx
0x180022f8d  push    rbp
0x180022f8e  push    rsi
0x180022f8f  push    rdi
0x180022f90  lea     rbp, [rsp-47h]
0x180022f95  sub     rsp, 0F0h
0x180022f9c  mov     rax, cs:__security_cookie
0x180022fa3  xor     rax, rsp
0x180022fa6  mov     [rbp+57h+var_18], rax
0x180022faa  mov     [rbp+57h+var_50], 0
0x180022fb2  lea     rax, [rbp+57h+var_50]
0x180022fb6  mov     [rbp+57h+lpExistingFileName], rax
0x180022fba  lea     rax, [rbp+57h+var_C0]
0x180022fbe  mov     [rbp+57h+lpNewFileName], rax
0x180022fc2  mov     rsi, rdx
0x180022fc5  mov     [rbp+57h+var_24], 100h
0x180022fcb  mov     edx, 20h ; ' '
0x180022fd0  mov     [rbp+57h+var_28], edx
0x180022fd3  lea     rax, [rbp+57h+var_88]
0x180022fd7  mov     [rbp+57h+var_68], rax
0x180022fdb  mov     rdi, r8
0x180022fde  mov     [rbp+57h+var_20], 0
0x180022fe5  mov     [rbp+57h+var_C0], 0
0x180022fed  mov     [rbp+57h+var_98], edx
0x180022ff0  mov     [rbp+57h+var_94], 100h
0x180022ff6  mov     [rbp+57h+var_90], 0
0x180022ffd  mov     [rbp+57h+var_88], 0
0x180023005  mov     [rbp+57h+var_60], edx
0x180023008  mov     [rbp+57h+var_5C], 100h
0x18002300e  mov     [rbp+57h+var_58], 0
0x180023015  test    rcx, rcx
0x180023018  jz      loc_1800230C9
0x18002301e  test    rsi, rsi
0x180023021  jz      loc_1800230C9
0x180023027  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002302b  jz      loc_1800230C9
0x180023031  lea     rdx, [rbp+57h+var_50]; this
0x180023035  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002303a  mov     ebx, eax
0x18002303c  test    eax, eax
0x18002303e  js      loc_1800230CE
0x180023044  lea     rdx, [rbp+57h+var_C0]; this
0x180023048  mov     rcx, rsi; unsigned __int16 *
0x18002304b  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180023050  mov     ebx, eax
0x180023052  test    eax, eax
0x180023054  js      short loc_1800230CE
0x180023056  mov     rcx, [rbp+57h+lpNewFileName]; unsigned __int16 *
0x18002305a  lea     rdx, [rbp+57h+var_88]; this
0x18002305e  call    ?GetParentPath@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::GetParentPath(ushort const *,STRU *)
0x180023063  mov     ebx, eax
0x180023065  test    eax, eax
0x180023067  js      short loc_1800230CE
0x180023069  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18002306d  mov     rdx, rdi; void *
0x180023070  call    ?CreateDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z; BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(ushort const *,void *)
0x180023075  mov     ebx, eax
0x180023077  test    eax, eax
0x180023079  jns     short loc_180023084
0x18002307b  cmp     eax, 800700B7h
0x180023080  jnz     short loc_1800230CE
0x180023082  xor     ebx, ebx
0x180023084  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180023088  xor     r9d, r9d; lpData
0x18002308b  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x18002308f  xor     r8d, r8d; lpProgressRoutine
0x180023092  mov     [rsp+100h+hTransaction], rdi; hTransaction
0x180023097  mov     [rsp+100h+dwCopyFlags], 0; dwCopyFlags
0x18002309f  mov     [rsp+100h+pbCancel], 0; pbCancel
0x1800230a8  call    cs:__imp_CopyFileTransactedW
0x1800230ae  test    eax, eax
0x1800230b0  jnz     short loc_1800230CE
0x1800230b2  call    cs:__imp_GetLastError
0x1800230b8  mov     ebx, eax
0x1800230ba  test    eax, eax
0x1800230bc  jle     short loc_1800230CE
0x1800230be  movzx   ebx, ax
0x1800230c1  or      ebx, 80070000h
0x1800230c7  jmp     short loc_1800230CE
0x1800230c9  mov     ebx, 57h ; 'W'
0x1800230ce  lea     rcx, [rbp+57h+var_88]; this
0x1800230d2  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800230d7  lea     rcx, [rbp+57h+var_C0]; this
0x1800230db  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800230e0  lea     rcx, [rbp+57h+var_50]; this
0x1800230e4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800230e9  mov     eax, ebx
0x1800230eb  mov     rcx, [rbp+57h+var_18]
0x1800230ef  xor     rcx, rsp; StackCookie
0x1800230f2  call    __security_check_cookie
0x1800230f7  mov     rbx, [rsp+100h+arg_18]
0x1800230ff  add     rsp, 0F0h
0x180023106  pop     rdi
0x180023107  pop     rsi
0x180023108  pop     rbp
0x180023109  retn
```

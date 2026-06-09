# BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(ushort const *,void *)

- ea: `0x1800235dc`
- end: `0x180023730`
- name: `?CreateDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z`
- size: `340`
- prototype: `static int(const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180022f88`
- `0x1800235dc`

## callees

- `0x180001fb0`
- `0x1800235dc`
- `0x180024de8`
- `0x180033bc4`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236e0`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023654`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1800236d6`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x180023654`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x1800236d6`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(const unsigned __int16 *a1, void *a2)
{
  signed int PathCanonicalizationProof; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  _QWORD v7[4]; // [rsp+20h] [rbp-29h] BYREF
  unsigned __int16 *v8; // [rsp+40h] [rbp-9h]
  int v9; // [rsp+48h] [rbp-1h]
  __int16 v10; // [rsp+4Ch] [rbp+3h]
  int v11; // [rsp+50h] [rbp+7h]
  _QWORD v12[4]; // [rsp+58h] [rbp+Fh] BYREF
  LPCWSTR lpNewDirectory; // [rsp+78h] [rbp+2Fh]
  int v14; // [rsp+80h] [rbp+37h]
  __int16 v15; // [rsp+84h] [rbp+3Bh]
  int v16; // [rsp+88h] [rbp+3Fh]

  PathCanonicalizationProof = 0;
  v14 = 32;
  v12[0] = 0;
  lpNewDirectory = (LPCWSTR)v12;
  v15 = 256;
  v16 = 0;
  if ( a1 )
  {
    if ( a2 != (void *)-1LL )
    {
      PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v12);
      if ( PathCanonicalizationProof >= 0 )
      {
        if ( CreateDirectoryTransactedW(0, lpNewDirectory, 0, a2) )
        {
          PathCanonicalizationProof = 0;
        }
        else
        {
          LastError = GetLastError();
          PathCanonicalizationProof = LastError;
          if ( LastError == 3 )
          {
            v8 = (unsigned __int16 *)v7;
            v7[0] = 0;
            v9 = 32;
            v10 = 256;
            v11 = 0;
            PathCanonicalizationProof = BACKUP_FILE_SYSTEM_HELPER::GetParentPath(lpNewDirectory, (struct STRU *)v7);
            if ( PathCanonicalizationProof >= 0 )
            {
              PathCanonicalizationProof = BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(v8, a2);
              if ( PathCanonicalizationProof >= 0 && !CreateDirectoryTransactedW(0, lpNewDirectory, 0, a2) )
              {
                v5 = GetLastError();
                PathCanonicalizationProof = v5;
                if ( v5 > 0 )
                  PathCanonicalizationProof = (unsigned __int16)v5 | 0x80070000;
              }
            }
            BUFFER::~BUFFER((BUFFER *)v7);
          }
          else if ( LastError > 0 )
          {
            PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  BUFFER::~BUFFER((BUFFER *)v12);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x1800235dc  mov     [rsp-8+arg_10], rbx
0x1800235e1  mov     [rsp-8+arg_18], rdi
0x1800235e6  push    rbp
0x1800235e7  lea     rbp, [rsp-57h]
0x1800235ec  sub     rsp, 0A0h
0x1800235f3  mov     rax, cs:__security_cookie
0x1800235fa  xor     rax, rsp
0x1800235fd  mov     [rbp+57h+var_10], rax
0x180023601  xor     ebx, ebx
0x180023603  mov     [rbp+57h+var_20], 20h ; ' '
0x18002360a  mov     [rbp+57h+var_48], rbx
0x18002360e  lea     rax, [rbp+57h+var_48]
0x180023612  mov     [rbp+57h+lpNewDirectory], rax
0x180023616  mov     rdi, rdx
0x180023619  mov     [rbp+57h+var_1C], 100h
0x18002361f  mov     [rbp+57h+var_18], ebx
0x180023622  test    rcx, rcx
0x180023625  jz      loc_180023704
0x18002362b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18002362f  jz      loc_180023704
0x180023635  lea     rdx, [rbp+57h+var_48]; this
0x180023639  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002363e  mov     ebx, eax
0x180023640  test    eax, eax
0x180023642  js      loc_180023704
0x180023648  mov     rdx, [rbp+57h+lpNewDirectory]; lpNewDirectory
0x18002364c  mov     r9, rdi; hTransaction
0x18002364f  xor     r8d, r8d; lpSecurityAttributes
0x180023652  xor     ecx, ecx; lpTemplateDirectory
0x180023654  call    cs:__imp_CreateDirectoryTransactedW
0x18002365a  test    eax, eax
0x18002365c  jz      short loc_180023665
0x18002365e  xor     ebx, ebx
0x180023660  jmp     loc_180023704
0x180023665  call    cs:__imp_GetLastError
0x18002366b  mov     ebx, eax
0x18002366d  cmp     eax, 3
0x180023670  jnz     loc_1800236F7
0x180023676  mov     rcx, [rbp+57h+lpNewDirectory]; unsigned __int16 *
0x18002367a  lea     rax, [rbp+57h+var_80]
0x18002367e  lea     rdx, [rbp+57h+var_80]; this
0x180023682  mov     [rbp+57h+var_60], rax
0x180023686  mov     [rbp+57h+var_80], 0
0x18002368e  mov     [rbp+57h+var_58], 20h ; ' '
0x180023695  mov     [rbp+57h+var_54], 100h
0x18002369b  mov     [rbp+57h+var_50], 0
0x1800236a2  call    ?GetParentPath@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::GetParentPath(ushort const *,STRU *)
0x1800236a7  mov     ebx, eax
0x1800236a9  test    eax, eax
0x1800236ab  jns     short loc_1800236B8
0x1800236ad  lea     rcx, [rbp+57h+var_80]; this
0x1800236b1  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800236b6  jmp     short loc_180023704
0x1800236b8  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800236bc  mov     rdx, rdi; void *
0x1800236bf  call    ?CreateDirectoryTreeTransacted@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAX@Z; BACKUP_FILE_SYSTEM_HELPER::CreateDirectoryTreeTransacted(ushort const *,void *)
0x1800236c4  mov     ebx, eax
0x1800236c6  test    eax, eax
0x1800236c8  js      short loc_1800236AD
0x1800236ca  mov     rdx, [rbp+57h+lpNewDirectory]; lpNewDirectory
0x1800236ce  mov     r9, rdi; hTransaction
0x1800236d1  xor     r8d, r8d; lpSecurityAttributes
0x1800236d4  xor     ecx, ecx; lpTemplateDirectory
0x1800236d6  call    cs:__imp_CreateDirectoryTransactedW
0x1800236dc  test    eax, eax
0x1800236de  jnz     short loc_1800236AD
0x1800236e0  call    cs:__imp_GetLastError
0x1800236e6  mov     ebx, eax
0x1800236e8  test    eax, eax
0x1800236ea  jle     short loc_1800236AD
0x1800236ec  movzx   ebx, ax
0x1800236ef  or      ebx, 80070000h
0x1800236f5  jmp     short loc_1800236AD
0x1800236f7  test    eax, eax
0x1800236f9  jle     short loc_180023704
0x1800236fb  movzx   ebx, ax
0x1800236fe  or      ebx, 80070000h
0x180023704  lea     rcx, [rbp+57h+var_48]; this
0x180023708  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002370d  mov     eax, ebx
0x18002370f  mov     rcx, [rbp+57h+var_10]
0x180023713  xor     rcx, rsp; StackCookie
0x180023716  call    __security_check_cookie
0x18002371b  lea     r11, [rsp+0A0h+var_s0]
0x180023723  mov     rbx, [r11+20h]
0x180023727  mov     rdi, [r11+28h]
0x18002372b  mov     rsp, r11
0x18002372e  pop     rbp
0x18002372f  retn
```

# BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(ushort const *,BACKUP_FILE_SYSTEM_HELPER::ConfigFilePathListingMode,MULTISZ *,MULTISZ *)

- ea: `0x180024a98`
- end: `0x180024de0`
- name: `?GetConfigFilePathsListing@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGW4ConfigFilePathListingMode@1@PEAVMULTISZ@@2@Z`
- size: `840`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180023208`
- `0x1800253fc`

## callees

- `0x180001ed0`
- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x1800243c8`
- `0x180024854`
- `0x180024a98`
- `0x180032c08`
- `0x180034d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d5c`

## pseudocode

```c
__int64 __fastcall BACKUP_FILE_SYSTEM_HELPER::GetConfigFilePathsListing(
        const unsigned __int8 *a1,
        int a2,
        __int64 a3,
        __int64 a4)
{
  int BackupableFilenames; // ebx
  unsigned int v9; // r15d
  unsigned __int16 *v10; // rcx
  __int64 i; // rcx
  const unsigned __int16 *v12; // rdi
  __int64 v13; // rax
  signed int LastError; // eax
  _QWORD v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h]
  __int16 v19; // [rsp+4Ch] [rbp-B4h]
  int v20; // [rsp+50h] [rbp-B0h]
  _QWORD v21[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  __int16 v24; // [rsp+84h] [rbp-7Ch]
  int v25; // [rsp+88h] [rbp-78h]
  _QWORD v26[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *Src; // [rsp+B0h] [rbp-50h]
  int v28; // [rsp+B8h] [rbp-48h]
  __int16 v29; // [rsp+BCh] [rbp-44h]
  int v30; // [rsp+C0h] [rbp-40h]
  _QWORD v31[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+F0h] [rbp-10h]
  __int16 v34; // [rsp+F4h] [rbp-Ch]
  int v35; // [rsp+F8h] [rbp-8h]
  _BYTE v36[32]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v37; // [rsp+120h] [rbp+20h]

  if ( !a1 || !a3 || **(_WORD **)(a3 + 32) || !a4 || **(_WORD **)(a4 + 32) )
    return (unsigned int)-2147024809;
  BackupableFilenames = 0;
  v9 = 0;
LABEL_7:
  if ( v9 < 3 )
  {
    MULTISZ::MULTISZ((MULTISZ *)v36);
    v16[0] = 0;
    v18 = 32;
    v17 = (unsigned __int16 *)v16;
    v33 = 32;
    v32 = (unsigned __int16 *)v31;
    v19 = 256;
    v20 = 0;
    v31[0] = 0;
    v34 = 256;
    v35 = 0;
    BackupableFilenames = STRU::Copy((STRU *)v16, a1);
    if ( BackupableFilenames < 0
      || (BackupableFilenames = STRU::Append(
                                  (STRU *)v16,
                                  *((const unsigned __int16 **)&BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo
                                  + 3 * v9
                                  + 1)),
          BackupableFilenames < 0)
      || (BackupableFilenames = BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(
                                  *((LPCWSTR *)&BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo + 3 * v9),
                                  (struct STRU *)v31),
          BackupableFilenames < 0) )
    {
LABEL_33:
      BUFFER::~BUFFER((BUFFER *)v31);
      BUFFER::~BUFFER((BUFFER *)v16);
      BUFFER::~BUFFER((BUFFER *)v36);
      return (unsigned int)BackupableFilenames;
    }
    if ( a2 )
    {
      if ( a2 != 1 )
        goto LABEL_16;
      v10 = v32;
    }
    else
    {
      v10 = v17;
    }
    BackupableFilenames = BACKUP_FILE_SYSTEM_HELPER::GetBackupableFilenames(
                            v10,
                            *((int (**)(const unsigned __int16 *))&BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo
                            + 3 * v9
                            + 2),
                            (struct MULTISZ *)v36);
LABEL_16:
    for ( i = v37; ; i = (__int64)&v12[v13 + 1] )
    {
      v12 = (const unsigned __int16 *)(i & -(__int64)(*(_WORD *)i != 0));
      if ( !v12 )
      {
        BUFFER::~BUFFER((BUFFER *)v31);
        BUFFER::~BUFFER((BUFFER *)v16);
        BUFFER::~BUFFER((BUFFER *)v36);
        ++v9;
        goto LABEL_7;
      }
      v26[0] = 0;
      v28 = 32;
      Src = (unsigned __int16 *)v26;
      v30 = 0;
      v21[0] = 0;
      v23 = 32;
      v25 = 0;
      v22 = (unsigned __int16 *)v21;
      v29 = 256;
      v24 = 256;
      BackupableFilenames = STRU::Copy((STRU *)v26, (const unsigned __int8 *)v17);
      if ( BackupableFilenames < 0 )
        break;
      BackupableFilenames = STRU::Append((STRU *)v26, L"\\");
      if ( BackupableFilenames < 0 )
        break;
      BackupableFilenames = STRU::Append((STRU *)v26, v12);
      if ( BackupableFilenames < 0 )
        break;
      if ( !(unsigned int)MULTISZ::AuxAppend((MULTISZ *)a3, Src, (unsigned int)(2 * v30), 1) )
        goto LABEL_30;
      BackupableFilenames = STRU::Copy((STRU *)v21, (const unsigned __int8 *)v32);
      if ( BackupableFilenames < 0 )
        break;
      BackupableFilenames = STRU::Append((STRU *)v21, L"\\");
      if ( BackupableFilenames < 0 )
        break;
      BackupableFilenames = STRU::Append((STRU *)v21, v12);
      if ( BackupableFilenames < 0 )
        break;
      if ( !(unsigned int)MULTISZ::AuxAppend((MULTISZ *)a4, v22, (unsigned int)(2 * v25), 1) )
      {
LABEL_30:
        LastError = GetLastError();
        BackupableFilenames = LastError;
        if ( LastError > 0 )
          BackupableFilenames = (unsigned __int16)LastError | 0x80070000;
        break;
      }
      BUFFER::~BUFFER((BUFFER *)v21);
      BUFFER::~BUFFER((BUFFER *)v26);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
    }
    BUFFER::~BUFFER((BUFFER *)v21);
    BUFFER::~BUFFER((BUFFER *)v26);
    goto LABEL_33;
  }
  if ( *(_DWORD *)(a3 + 52) != *(_DWORD *)(a4 + 52) )
    return (unsigned int)-2147024883;
  return (unsigned int)BackupableFilenames;
}

```

## disassembly

```asm
0x180024a98  mov     [rsp-8+arg_8], rbx
0x180024a9d  push    rbp
0x180024a9e  push    rsi
0x180024a9f  push    rdi
0x180024aa0  push    r12
0x180024aa2  push    r13
0x180024aa4  push    r14
0x180024aa6  push    r15
0x180024aa8  lea     rbp, [rsp-40h]
0x180024aad  sub     rsp, 140h
0x180024ab4  mov     rax, cs:__security_cookie
0x180024abb  xor     rax, rsp
0x180024abe  mov     [rbp+70h+var_38], rax
0x180024ac2  xor     edi, edi
0x180024ac4  mov     r14, r9
0x180024ac7  mov     rsi, r8
0x180024aca  mov     r12d, edx
0x180024acd  mov     r13, rcx
0x180024ad0  test    rcx, rcx
0x180024ad3  jz      loc_180024DB2
0x180024ad9  test    r8, r8
0x180024adc  jz      loc_180024DB2
0x180024ae2  mov     rax, [r8+20h]
0x180024ae6  cmp     [rax], di
0x180024ae9  jnz     loc_180024DB2
0x180024aef  test    r9, r9
0x180024af2  jz      loc_180024DB2
0x180024af8  mov     rax, [r9+20h]
0x180024afc  cmp     [rax], di
0x180024aff  jnz     loc_180024DB2
0x180024b05  mov     ebx, edi
0x180024b07  mov     r15d, edi
0x180024b0a  cmp     r15d, 3
0x180024b0e  jnb     loc_180024DA2
0x180024b14  lea     rcx, [rbp+70h+var_70]; this
0x180024b18  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180024b1d  mov     ecx, 20h ; ' '
0x180024b22  mov     [rsp+170h+var_150], rdi
0x180024b27  lea     rax, [rsp+170h+var_150]
0x180024b2c  mov     [rsp+170h+var_128], ecx
0x180024b30  mov     [rsp+170h+var_130], rax
0x180024b35  mov     rdx, r13; unsigned __int16 *
0x180024b38  lea     rax, [rbp+70h+var_A8]
0x180024b3c  mov     [rbp+70h+var_80], ecx
0x180024b3f  lea     rcx, [rsp+170h+var_150]; this
0x180024b44  mov     [rbp+70h+var_88], rax
0x180024b48  mov     [rsp+170h+var_124], 100h
0x180024b4f  mov     [rsp+170h+var_120], edi
0x180024b53  mov     [rbp+70h+var_A8], rdi
0x180024b57  mov     [rbp+70h+var_7C], 100h
0x180024b5d  mov     [rbp+70h+var_78], edi
0x180024b60  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180024b65  mov     ebx, eax
0x180024b67  test    eax, eax
0x180024b69  js      loc_180024D84
0x180024b6f  mov     eax, r15d
0x180024b72  lea     rdx, ?s_rgBackupableDirectoryInfo@BACKUP_FILE_SYSTEM_HELPER@@0QBUBACKUPABLE_DIRECTORY_INFO@1@B; BACKUP_FILE_SYSTEM_HELPER::BACKUPABLE_DIRECTORY_INFO const near * const BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo
0x180024b79  lea     rcx, [rsp+170h+var_150]; this
0x180024b7e  lea     rdi, [rax+rax*2]
0x180024b82  mov     rdx, [rdx+rdi*8+8]; unsigned __int16 *
0x180024b87  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024b8c  mov     ebx, eax
0x180024b8e  test    eax, eax
0x180024b90  js      loc_180024D84
0x180024b96  lea     rax, ?s_rgBackupableDirectoryInfo@BACKUP_FILE_SYSTEM_HELPER@@0QBUBACKUPABLE_DIRECTORY_INFO@1@B; BACKUP_FILE_SYSTEM_HELPER::BACKUPABLE_DIRECTORY_INFO const near * const BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo
0x180024b9d  mov     rcx, [rax+rdi*8]; lpSrc
0x180024ba1  lea     rdx, [rbp+70h+var_A8]; this
0x180024ba5  call    ?ExpandEnvironmentStringsSTRU@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGPEAVSTRU@@@Z; BACKUP_FILE_SYSTEM_HELPER::ExpandEnvironmentStringsSTRU(ushort const *,STRU *)
0x180024baa  xor     edx, edx
0x180024bac  mov     ebx, eax
0x180024bae  test    eax, eax
0x180024bb0  js      loc_180024D84
0x180024bb6  test    r12d, r12d
0x180024bb9  jnz     short loc_180024BC2
0x180024bbb  mov     rcx, [rsp+170h+var_130]
0x180024bc0  jmp     short loc_180024BCC
0x180024bc2  cmp     r12d, 1
0x180024bc6  jnz     short loc_180024BE5
0x180024bc8  mov     rcx, [rbp+70h+var_88]; unsigned __int16 *
0x180024bcc  lea     rax, ?s_rgBackupableDirectoryInfo@BACKUP_FILE_SYSTEM_HELPER@@0QBUBACKUPABLE_DIRECTORY_INFO@1@B; BACKUP_FILE_SYSTEM_HELPER::BACKUPABLE_DIRECTORY_INFO const near * const BACKUP_FILE_SYSTEM_HELPER::s_rgBackupableDirectoryInfo
0x180024bd3  mov     rdx, [rax+rdi*8+10h]; int (*)(const unsigned __int16 *)
0x180024bd8  lea     r8, [rbp+70h+var_70]; struct MULTISZ *
0x180024bdc  call    ?GetBackupableFilenames@BACKUP_FILE_SYSTEM_HELPER@@CAJPEBGP6AH0@ZPEAVMULTISZ@@@Z; BACKUP_FILE_SYSTEM_HELPER::GetBackupableFilenames(ushort const *,int (*)(ushort const *),MULTISZ *)
0x180024be1  xor     edx, edx
0x180024be3  mov     ebx, eax
0x180024be5  mov     rcx, [rbp+70h+var_50]
0x180024be9  movzx   eax, word ptr [rcx]
0x180024bec  neg     ax
0x180024bef  sbb     rdi, rdi
0x180024bf2  and     rdi, rcx
0x180024bf5  test    rdi, rdi
0x180024bf8  jz      loc_180024D36
0x180024bfe  mov     ecx, 20h ; ' '
0x180024c03  mov     [rbp+70h+var_E0], rdx
0x180024c07  lea     rax, [rbp+70h+var_E0]
0x180024c0b  mov     [rbp+70h+var_B8], ecx
0x180024c0e  mov     [rbp+70h+Src], rax
0x180024c12  lea     rax, [rsp+170h+var_118]
0x180024c17  mov     [rbp+70h+var_B0], edx
0x180024c1a  mov     [rsp+170h+var_118], rdx
0x180024c1f  mov     [rbp+70h+var_F0], ecx
0x180024c22  lea     rcx, [rbp+70h+var_E0]; this
0x180024c26  mov     [rbp+70h+var_E8], edx
0x180024c29  mov     rdx, [rsp+170h+var_130]; unsigned __int16 *
0x180024c2e  mov     [rsp+170h+var_F8], rax
0x180024c33  mov     [rbp+70h+var_B4], 100h
0x180024c39  mov     [rbp+70h+var_EC], 100h
0x180024c3f  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180024c44  mov     ebx, eax
0x180024c46  test    eax, eax
0x180024c48  js      loc_180024D71
0x180024c4e  lea     rdx, asc_180039420; "\\"
0x180024c55  lea     rcx, [rbp+70h+var_E0]; this
0x180024c59  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024c5e  mov     ebx, eax
0x180024c60  test    eax, eax
0x180024c62  js      loc_180024D71
0x180024c68  mov     rdx, rdi; unsigned __int16 *
0x180024c6b  lea     rcx, [rbp+70h+var_E0]; this
0x180024c6f  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024c74  mov     ebx, eax
0x180024c76  test    eax, eax
0x180024c78  js      loc_180024D71
0x180024c7e  mov     r8d, [rbp+70h+var_B0]
0x180024c82  mov     r9d, 1; int
0x180024c88  mov     rdx, [rbp+70h+Src]; Src
0x180024c8c  add     r8d, r8d; Size
0x180024c8f  mov     rcx, rsi; this
0x180024c92  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x180024c97  test    eax, eax
0x180024c99  jz      loc_180024D5C
0x180024c9f  mov     rdx, [rbp+70h+var_88]; unsigned __int16 *
0x180024ca3  lea     rcx, [rsp+170h+var_118]; this
0x180024ca8  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180024cad  mov     ebx, eax
0x180024caf  test    eax, eax
0x180024cb1  js      loc_180024D71
0x180024cb7  lea     rdx, asc_180039420; "\\"
0x180024cbe  lea     rcx, [rsp+170h+var_118]; this
0x180024cc3  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024cc8  mov     ebx, eax
0x180024cca  test    eax, eax
0x180024ccc  js      loc_180024D71
0x180024cd2  mov     rdx, rdi; unsigned __int16 *
0x180024cd5  lea     rcx, [rsp+170h+var_118]; this
0x180024cda  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180024cdf  mov     ebx, eax
0x180024ce1  test    eax, eax
0x180024ce3  js      loc_180024D71
0x180024ce9  mov     r8d, [rbp+70h+var_E8]
0x180024ced  mov     r9d, 1; int
0x180024cf3  mov     rdx, [rsp+170h+var_F8]; Src
0x180024cf8  add     r8d, r8d; Size
0x180024cfb  mov     rcx, r14; this
0x180024cfe  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x180024d03  test    eax, eax
0x180024d05  jz      short loc_180024D5C
0x180024d07  lea     rcx, [rsp+170h+var_118]; this
0x180024d0c  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d11  lea     rcx, [rbp+70h+var_E0]; this
0x180024d15  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024d1e  xor     edx, edx
0x180024d20  inc     rax
0x180024d23  cmp     [rdi+rax*2], dx
0x180024d27  jnz     short loc_180024D20
0x180024d29  lea     rcx, [rdi+2]
0x180024d2d  lea     rcx, [rcx+rax*2]
0x180024d31  jmp     loc_180024BE9
0x180024d36  lea     rcx, [rbp+70h+var_A8]; this
0x180024d3a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d3f  lea     rcx, [rsp+170h+var_150]; this
0x180024d44  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d49  lea     rcx, [rbp+70h+var_70]; this
0x180024d4d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d52  inc     r15d
0x180024d55  xor     edi, edi
0x180024d57  jmp     loc_180024B0A
0x180024d5c  call    cs:__imp_GetLastError
0x180024d62  mov     ebx, eax
0x180024d64  test    eax, eax
0x180024d66  jle     short loc_180024D71
0x180024d68  movzx   ebx, ax
0x180024d6b  or      ebx, 80070000h
0x180024d71  lea     rcx, [rsp+170h+var_118]; this
0x180024d76  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d7b  lea     rcx, [rbp+70h+var_E0]; this
0x180024d7f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d84  lea     rcx, [rbp+70h+var_A8]; this
0x180024d88  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d8d  lea     rcx, [rsp+170h+var_150]; this
0x180024d92  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024d97  lea     rcx, [rbp+70h+var_70]; this
0x180024d9b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024da0  jmp     short loc_180024DB7
0x180024da2  mov     eax, [r14+34h]
0x180024da6  cmp     [rsi+34h], eax
0x180024da9  jz      short loc_180024DB7
0x180024dab  mov     ebx, 8007000Dh
0x180024db0  jmp     short loc_180024DB7
0x180024db2  mov     ebx, 80070057h
0x180024db7  mov     eax, ebx
0x180024db9  mov     rcx, [rbp+70h+var_38]
0x180024dbd  xor     rcx, rsp; StackCookie
0x180024dc0  call    __security_check_cookie
0x180024dc5  mov     rbx, [rsp+170h+arg_8]
0x180024dcd  add     rsp, 140h
0x180024dd4  pop     r15
0x180024dd6  pop     r14
0x180024dd8  pop     r13
0x180024dda  pop     r12
0x180024ddc  pop     rdi
0x180024ddd  pop     rsi
0x180024dde  pop     rbp
0x180024ddf  retn
```

# FvePersistentRequest::CreateSVIRequestFolder(ushort const *,_FVE_REQUEST_TYPE)

- ea: `0x18000b020`
- end: `0x18000b3c3`
- name: `?CreateSVIRequestFolder@FvePersistentRequest@@SAJPEBGW4_FVE_REQUEST_TYPE@@@Z`
- size: `931`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180029df0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000b020`
- `0x18000b3d0`
- `0x18000be60`
- `0x18000c890`
- `0x18000cce0`
- `0x18000d530`
- `0x18000f7e0`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b19a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b35d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b19a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000b35d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b0ef`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000b0ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FvePersistentRequest::CreateSVIRequestFolder(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned int FolderName; // eax
  unsigned int v5; // r9d
  signed int v6; // ebx
  PVOID *v7; // rcx
  unsigned int SystemVolumeInformationPath; // eax
  signed int v9; // eax
  signed int v11; // eax
  signed int LastError; // eax
  int v13; // eax
  bool v14; // [rsp+30h] [rbp-458h] BYREF
  WCHAR PathName[264]; // [rsp+40h] [rbp-448h] BYREF
  unsigned __int16 v16[264]; // [rsp+250h] [rbp-238h] BYREF

  memset_0(PathName, 0, 0x208u);
  memset_0(v16, 0, 0x208u);
  v14 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  FolderName = FvePersistentRequest::GetFolderName(a2, v16);
  v6 = FolderName;
  if ( FolderName )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, FolderName);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 < 0 )
      goto LABEL_12;
  }
  SystemVolumeInformationPath = MakeSystemVolumeInformationPath(a1, v16, PathName, v5);
  v6 = SystemVolumeInformationPath;
  if ( SystemVolumeInformationPath )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        SystemVolumeInformationPath);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 < 0 )
      goto LABEL_12;
  }
  if ( CreateDirectoryW(PathName, 0) )
  {
    v6 = IsTerminalFolderRedirection(PathName, &v14);
    if ( v6 >= 0 && !v14 )
    {
      if ( a2 == 1 )
      {
        v13 = GrantAccessToSpecifiedUsers(PathName, 1);
        v6 = v13;
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              (unsigned int)&WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
              (unsigned int)PathName,
              v13);
          if ( !RemoveDirectoryW(PathName) )
          {
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return (unsigned int)v6;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_12;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
              (unsigned int)LastError);
          }
        }
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_12:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
        WPP_SF_d(v7[2], 58, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v6);
      return (unsigned int)v6;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_DlS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, (__int64)PathName);
    if ( !RemoveDirectoryW(PathName) )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_11;
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)v11);
    }
LABEL_10:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_11:
    v6 = 0;
    goto LABEL_12;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 == 183 )
    goto LABEL_10;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)v6);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_12;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b020  mov     [rsp+arg_10], rbx
0x18000b025  push    rbp
0x18000b026  push    rsi
0x18000b027  push    rdi
0x18000b028  sub     rsp, 470h
0x18000b02f  mov     rax, cs:__security_cookie
0x18000b036  xor     rax, rsp
0x18000b039  mov     [rsp+488h+var_28], rax
0x18000b041  mov     edi, edx
0x18000b043  mov     rsi, rcx
0x18000b046  xor     edx, edx; Val
0x18000b048  lea     rcx, [rsp+488h+PathName]; void *
0x18000b04d  mov     r8d, 208h; Size
0x18000b053  call    memset_0
0x18000b058  xor     edx, edx; Val
0x18000b05a  lea     rcx, [rsp+488h+var_238]; void *
0x18000b062  mov     r8d, 208h; Size
0x18000b068  call    memset_0
0x18000b06d  mov     [rsp+488h+var_458], 1
0x18000b072  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b079  lea     rbp, WPP_GLOBAL_Control
0x18000b080  cmp     rcx, rbp
0x18000b083  jz      short loc_18000B0A0
0x18000b085  test    byte ptr [rcx+1Ch], 20h
0x18000b089  jz      short loc_18000B0A0
0x18000b08b  mov     rcx, [rcx+10h]
0x18000b08f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b096  mov     edx, 32h ; '2'
0x18000b09b  call    WPP_SF_
0x18000b0a0  lea     rdx, [rsp+488h+var_238]
0x18000b0a8  mov     ecx, edi
0x18000b0aa  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z; FvePersistentRequest::GetFolderName(_FVE_REQUEST_TYPE,ushort *,ulong)
0x18000b0af  mov     ebx, eax
0x18000b0b1  test    eax, eax
0x18000b0b3  jz      short loc_18000B0C9
0x18000b0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0bc  cmp     rcx, rbp
0x18000b0bf  jnz     loc_18000B292
0x18000b0c5  test    ebx, ebx
0x18000b0c7  js      short loc_18000B121
0x18000b0c9  lea     r8, [rsp+488h+PathName]; unsigned __int16 *
0x18000b0ce  mov     rcx, rsi; unsigned __int16 *
0x18000b0d1  lea     rdx, [rsp+488h+var_238]; unsigned __int16 *
0x18000b0d9  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z; MakeSystemVolumeInformationPath(ushort const *,ushort const *,ushort *,ulong)
0x18000b0de  mov     ebx, eax
0x18000b0e0  test    eax, eax
0x18000b0e2  jnz     loc_18000B2C0
0x18000b0e8  xor     edx, edx; lpSecurityAttributes
0x18000b0ea  lea     rcx, [rsp+488h+PathName]; lpPathName
0x18000b0ef  call    cs:__imp_CreateDirectoryW
0x18000b0f6  nop     dword ptr [rax+rax+00h]
0x18000b0fb  test    eax, eax
0x18000b0fd  jnz     short loc_18000B16C
0x18000b0ff  call    cs:__imp_GetLastError
0x18000b106  nop     dword ptr [rax+rax+00h]
0x18000b10b  mov     ebx, eax
0x18000b10d  cmp     eax, 0B7h
0x18000b112  jnz     loc_18000B204
0x18000b118  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b11f  xor     ebx, ebx
0x18000b121  cmp     rcx, rbp
0x18000b124  jnz     short loc_18000B14C
0x18000b126  mov     eax, ebx
0x18000b128  mov     rcx, [rsp+488h+var_28]
0x18000b130  xor     rcx, rsp; StackCookie
0x18000b133  call    __security_check_cookie
0x18000b138  mov     rbx, [rsp+488h+arg_10]
0x18000b140  add     rsp, 470h
0x18000b147  pop     rdi
0x18000b148  pop     rsi
0x18000b149  pop     rbp
0x18000b14a  retn
0x18000b14c  test    byte ptr [rcx+1Ch], 20h
0x18000b150  jz      short loc_18000B126
0x18000b152  mov     rcx, [rcx+10h]
0x18000b156  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b15d  mov     edx, 3Ah ; ':'
0x18000b162  mov     r9d, ebx
0x18000b165  call    WPP_SF_d
0x18000b16a  jmp     short loc_18000B126
0x18000b16c  lea     rdx, [rsp+488h+var_458]; bool *
0x18000b171  lea     rcx, [rsp+488h+PathName]; unsigned __int16 *
0x18000b176  call    ?IsTerminalFolderRedirection@@YAJPEAGPEA_N@Z; IsTerminalFolderRedirection(ushort *,bool *)
0x18000b17b  mov     ebx, eax
0x18000b17d  test    eax, eax
0x18000b17f  jns     loc_18000B2FE
0x18000b185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b18c  cmp     rcx, rbp
0x18000b18f  jnz     loc_18000B390
0x18000b195  lea     rcx, [rsp+488h+PathName]; lpPathName
0x18000b19a  call    cs:__imp_RemoveDirectoryW
0x18000b1a1  nop     dword ptr [rax+rax+00h]
0x18000b1a6  test    eax, eax
0x18000b1a8  jnz     loc_18000B118
0x18000b1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1b5  cmp     rcx, rbp
0x18000b1b8  jz      loc_18000B11F
0x18000b1be  test    byte ptr [rcx+1Ch], 2
0x18000b1c2  jz      loc_18000B11F
0x18000b1c8  call    cs:__imp_GetLastError
0x18000b1cf  nop     dword ptr [rax+rax+00h]
0x18000b1d4  test    eax, eax
0x18000b1d6  jle     short loc_18000B1E0
0x18000b1d8  movzx   eax, ax
0x18000b1db  or      eax, 80070000h
0x18000b1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1e7  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b1ee  mov     edx, 37h ; '7'
0x18000b1f3  mov     r9d, eax
0x18000b1f6  mov     rcx, [rcx+10h]
0x18000b1fa  call    WPP_SF_d
0x18000b1ff  jmp     loc_18000B118
0x18000b204  test    eax, eax
0x18000b206  jle     short loc_18000B211
0x18000b208  movzx   ebx, ax
0x18000b20b  or      ebx, 80070000h
0x18000b211  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b218  cmp     rcx, rbp
0x18000b21b  jz      loc_18000B126
0x18000b221  test    byte ptr [rcx+1Ch], 40h
0x18000b225  jz      loc_18000B121
0x18000b22b  mov     rcx, [rcx+10h]
0x18000b22f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b236  mov     edx, 35h ; '5'
0x18000b23b  mov     r9d, ebx
0x18000b23e  call    WPP_SF_d
0x18000b243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b24a  jmp     loc_18000B121
0x18000b24f  call    cs:__imp_GetLastError
0x18000b256  nop     dword ptr [rax+rax+00h]
0x18000b25b  test    eax, eax
0x18000b25d  jle     short loc_18000B267
0x18000b25f  movzx   eax, ax
0x18000b262  or      eax, 80070000h
0x18000b267  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b26e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b275  mov     edx, 39h ; '9'
0x18000b27a  mov     r9d, eax
0x18000b27d  mov     rcx, [rcx+10h]
0x18000b281  call    WPP_SF_d
0x18000b286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b28d  jmp     loc_18000B121
0x18000b292  test    byte ptr [rcx+1Ch], 40h
0x18000b296  jz      loc_18000B0C5
0x18000b29c  mov     rcx, [rcx+10h]
0x18000b2a0  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b2a7  mov     edx, 33h ; '3'
0x18000b2ac  mov     r9d, ebx
0x18000b2af  call    WPP_SF_d
0x18000b2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2bb  jmp     loc_18000B0C5
0x18000b2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2c7  cmp     rcx, rbp
0x18000b2ca  jz      short loc_18000B2F1
0x18000b2cc  test    byte ptr [rcx+1Ch], 40h
0x18000b2d0  jz      short loc_18000B2F1
0x18000b2d2  mov     rcx, [rcx+10h]
0x18000b2d6  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b2dd  mov     edx, 34h ; '4'
0x18000b2e2  mov     r9d, ebx
0x18000b2e5  call    WPP_SF_d
0x18000b2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2f1  test    ebx, ebx
0x18000b2f3  js      loc_18000B121
0x18000b2f9  jmp     loc_18000B0E8
0x18000b2fe  cmp     [rsp+488h+var_458], 0
0x18000b303  jnz     loc_18000B185
0x18000b309  cmp     edi, 1
0x18000b30c  jnz     loc_18000B286
0x18000b312  mov     edx, edi
0x18000b314  lea     rcx, [rsp+488h+PathName]
0x18000b319  call    ?GrantAccessToSpecifiedUsers@@YAJPEBGW4_TypeFolderAccessNeeded@@@Z; GrantAccessToSpecifiedUsers(ushort const *,_TypeFolderAccessNeeded)
0x18000b31e  mov     ebx, eax
0x18000b320  test    eax, eax
0x18000b322  jns     loc_18000B286
0x18000b328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b32f  cmp     rcx, rbp
0x18000b332  jz      short loc_18000B358
0x18000b334  test    byte ptr [rcx+1Ch], 2
0x18000b338  jz      short loc_18000B358
0x18000b33a  mov     rcx, [rcx+10h]
0x18000b33e  lea     r9, [rsp+488h+PathName]
0x18000b343  mov     edx, 38h ; '8'
0x18000b348  mov     dword ptr [rsp+488h+var_468], eax
0x18000b34c  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18000b353  call    WPP_SF_SD
0x18000b358  lea     rcx, [rsp+488h+PathName]; lpPathName
0x18000b35d  call    cs:__imp_RemoveDirectoryW
0x18000b364  nop     dword ptr [rax+rax+00h]
0x18000b369  test    eax, eax
0x18000b36b  jnz     loc_18000B286
0x18000b371  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b378  cmp     rcx, rbp
0x18000b37b  jz      loc_18000B126
0x18000b381  test    byte ptr [rcx+1Ch], 2
0x18000b385  jz      loc_18000B121
0x18000b38b  jmp     loc_18000B24F
0x18000b390  test    byte ptr [rcx+1Ch], 8
0x18000b394  jz      loc_18000B195
0x18000b39a  movzx   eax, [rsp+488h+var_458]
0x18000b39f  lea     r8, [rsp+488h+PathName]
0x18000b3a4  mov     rcx, [rcx+10h]; LoggerHandle
0x18000b3a8  mov     edx, 36h ; '6'
0x18000b3ad  mov     [rsp+488h+var_460], r8; __int64
0x18000b3b2  mov     r9d, ebx
0x18000b3b5  mov     dword ptr [rsp+488h+var_468], eax; char
0x18000b3b9  call    WPP_SF_DlS
0x18000b3be  jmp     loc_18000B195
```

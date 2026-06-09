# Common::Deployment::WalkTreeHardLinkCallbackWorker(void *,ushort const *,_WIN32_FIND_DATAW const *)

- ea: `0x18004ae14`
- end: `0x18004afe6`
- name: `?WalkTreeHardLinkCallbackWorker@Deployment@Common@@YAJPEAXPEBGPEBU_WIN32_FIND_DATAW@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(Common::Deployment *this, const unsigned __int16 *, const unsigned __int16 *, const struct _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18004adb0`

## callees

- `0x180004920`
- `0x180010384`
- `0x180018248`
- `0x18001a324`
- `0x18001a604`
- `0x18004682c`
- `0x18004a9a4`
- `0x18004ae14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aeca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aeca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af61`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004aec0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004aec0`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18004af57`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18004af57`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18004af79`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18004af79`

## string_xrefs

- `0x18004ae55`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`
- `0x18004ae9b`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`
- `0x18004af87`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`
- `0x18004afa5`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::WalkTreeHardLinkCallbackWorker(
        Common::Deployment *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _WIN32_FIND_DATAW *a4)
{
  const unsigned __int16 *v6; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rcx
  int v11; // eax
  bool *v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  const unsigned __int16 *v15; // r8
  signed int LastError; // eax
  DWORD v17; // eax
  const char *v18; // r9
  int v19; // eax
  LPCWSTR lpExistingFileName[2]; // [rsp+20h] [rbp-30h] BYREF
  int v22; // [rsp+30h] [rbp-20h]
  LPCWSTR lpPathName[2]; // [rsp+38h] [rbp-18h] BYREF
  int v24; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int16 v26; // [rsp+70h] [rbp+20h] BYREF

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  *(_OWORD *)lpPathName = 0;
  v24 = 0;
  v8 = Common::PathHelpers::CombinePaths(v6, a2, (struct Common::StringBuffer *)lpPathName);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = *(const unsigned __int16 **)this;
    v22 = 0;
    *(_OWORD *)lpExistingFileName = 0;
    v11 = Common::PathHelpers::CombinePaths(v10, a2, (struct Common::StringBuffer *)lpExistingFileName);
    v9 = v11;
    if ( v11 < 0 )
    {
      v13 = 74;
LABEL_5:
      v14 = (unsigned int)v11;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
        (const char *)v14,
        (int)lpExistingFileName[0]);
LABEL_7:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
      goto LABEL_30;
    }
    if ( (*(_BYTE *)a3 & 0x10) != 0 )
    {
      if ( CreateDirectoryW(lpPathName[1], 0) )
        goto LABEL_33;
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (v9 & 0x80000000) == 0 )
          goto LABEL_7;
        v14 = v9;
        v13 = 82;
        goto LABEL_6;
      }
      if ( !*((_BYTE *)this + 16) )
      {
LABEL_33:
        v11 = Common::Deployment::CopyPermissions(lpExistingFileName[1], (LPWSTR)lpPathName[1], v15);
        v9 = v11;
        if ( v11 < 0 )
        {
          v13 = 86;
          goto LABEL_5;
        }
      }
    }
    else
    {
      if ( !*((_BYTE *)this + 16) )
        goto LABEL_34;
      LOBYTE(v26) = 0;
      v11 = Common::FileExists((Common *)lpPathName[1], &v26, v12);
      v9 = v11;
      if ( v11 < 0 )
      {
        v13 = 95;
        goto LABEL_5;
      }
      if ( !(_BYTE)v26 )
      {
LABEL_34:
        if ( !CreateHardLinkW(lpPathName[1], lpExistingFileName[1], 0) )
        {
          v17 = GetLastError();
          if ( v17 == 1142 )
          {
            if ( CopyFileW(lpExistingFileName[1], lpPathName[1], 0) )
              goto LABEL_29;
            v19 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6A,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
                    v18);
          }
          else
          {
            if ( !v17 )
              goto LABEL_29;
            v19 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x6E,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
                    (const char *)v17,
                    (unsigned int)lpExistingFileName[0]);
          }
          v9 = v19;
          goto LABEL_7;
        }
      }
    }
LABEL_29:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
    v9 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x47,
    (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
    (const char *)(unsigned int)v8,
    (int)lpExistingFileName[0]);
LABEL_30:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpPathName);
  return v9;
}

```

## disassembly

```asm
0x18004ae14  mov     [rsp-18h+arg_8], rbx
0x18004ae19  mov     [rsp-18h+arg_10], rsi
0x18004ae1e  push    rbp
0x18004ae1f  push    rdi
0x18004ae20  push    r14
0x18004ae22  mov     rbp, rsp
0x18004ae25  sub     rsp, 50h
0x18004ae29  mov     rsi, r8
0x18004ae2c  mov     rdi, rcx
0x18004ae2f  mov     rcx, [rcx+8]; Src
0x18004ae33  lea     r8, [rbp+lpPathName]; this
0x18004ae37  xor     eax, eax
0x18004ae39  xorps   xmm0, xmm0
0x18004ae3c  movups  xmmword ptr [rbp+lpPathName], xmm0
0x18004ae40  mov     [rbp+var_8], eax
0x18004ae43  mov     r14, rdx
0x18004ae46  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18004ae4b  mov     ebx, eax
0x18004ae4d  test    eax, eax
0x18004ae4f  jns     short loc_18004AE6E
0x18004ae51  mov     rcx, [rbp+18h]; this
0x18004ae55  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004ae5c  mov     r9d, eax; char *
0x18004ae5f  mov     edx, 47h ; 'G'; void *
0x18004ae64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ae69  jmp     loc_18004AFC6
0x18004ae6e  mov     rcx, [rdi]; Src
0x18004ae71  lea     r8, [rbp+lpExistingFileName]; this
0x18004ae75  xor     eax, eax
0x18004ae77  xorps   xmm0, xmm0
0x18004ae7a  mov     rdx, r14; unsigned __int16 *
0x18004ae7d  mov     [rbp+var_20], eax
0x18004ae80  movups  xmmword ptr [rbp+lpExistingFileName], xmm0
0x18004ae84  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18004ae89  mov     ebx, eax
0x18004ae8b  test    eax, eax
0x18004ae8d  jns     short loc_18004AEB5
0x18004ae8f  mov     edx, 4Ah ; 'J'; void *
0x18004ae94  mov     r9d, eax; char *
0x18004ae97  mov     rcx, [rbp+18h]; this
0x18004ae9b  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004aea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aea7  lea     rcx, [rbp+lpExistingFileName]; this
0x18004aeab  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004aeb0  jmp     loc_18004AFC6
0x18004aeb5  test    byte ptr [rsi], 10h
0x18004aeb8  jz      short loc_18004AF1F
0x18004aeba  mov     rcx, [rbp+lpPathName+8]; lpPathName
0x18004aebe  xor     edx, edx; lpSecurityAttributes
0x18004aec0  call    cs:__imp_CreateDirectoryW
0x18004aec6  test    eax, eax
0x18004aec8  jnz     short loc_18004AEFE
0x18004aeca  call    cs:__imp_GetLastError
0x18004aed0  mov     ebx, eax
0x18004aed2  cmp     eax, 0B7h
0x18004aed7  jz      short loc_18004AEF4
0x18004aed9  test    eax, eax
0x18004aedb  jle     short loc_18004AEE6
0x18004aedd  movzx   ebx, ax
0x18004aee0  or      ebx, 80070000h
0x18004aee6  test    ebx, ebx
0x18004aee8  jns     short loc_18004AEA7
0x18004aeea  mov     r9d, ebx
0x18004aeed  mov     edx, 52h ; 'R'
0x18004aef2  jmp     short loc_18004AE97
0x18004aef4  cmp     byte ptr [rdi+10h], 0
0x18004aef8  jnz     loc_18004AFBB
0x18004aefe  mov     rdx, [rbp+lpPathName+8]; LPWSTR
0x18004af02  mov     rcx, [rbp+lpExistingFileName+8]; pObjectName
0x18004af06  call    ?CopyPermissions@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::CopyPermissions(ushort const *,ushort const *)
0x18004af0b  mov     ebx, eax
0x18004af0d  test    eax, eax
0x18004af0f  jns     loc_18004AFBB
0x18004af15  mov     edx, 56h ; 'V'
0x18004af1a  jmp     loc_18004AE94
0x18004af1f  cmp     byte ptr [rdi+10h], 0
0x18004af23  jz      short loc_18004AF4C
0x18004af25  mov     rcx, [rbp+lpPathName+8]; this
0x18004af29  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x18004af2d  mov     byte ptr [rbp+arg_0], 0
0x18004af31  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18004af36  mov     ebx, eax
0x18004af38  test    eax, eax
0x18004af3a  jns     short loc_18004AF46
0x18004af3c  mov     edx, 5Fh ; '_'
0x18004af41  jmp     loc_18004AE94
0x18004af46  cmp     byte ptr [rbp+arg_0], 0
0x18004af4a  jnz     short loc_18004AFBB
0x18004af4c  mov     rdx, [rbp+lpExistingFileName+8]; lpExistingFileName
0x18004af50  xor     r8d, r8d; lpSecurityAttributes
0x18004af53  mov     rcx, [rbp+lpPathName+8]; lpFileName
0x18004af57  call    cs:__imp_CreateHardLinkW
0x18004af5d  test    eax, eax
0x18004af5f  jnz     short loc_18004AFBB
0x18004af61  call    cs:__imp_GetLastError
0x18004af67  cmp     eax, 476h
0x18004af6c  jnz     short loc_18004AF9D
0x18004af6e  mov     rdx, [rbp+lpPathName+8]; lpNewFileName
0x18004af72  xor     r8d, r8d; bFailIfExists
0x18004af75  mov     rcx, [rbp+lpExistingFileName+8]; lpExistingFileName
0x18004af79  call    cs:__imp_CopyFileW
0x18004af7f  test    eax, eax
0x18004af81  jnz     short loc_18004AFBB
0x18004af83  mov     rcx, [rbp+18h]; this
0x18004af87  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004af8e  lea     edx, [rax+6Ah]; void *
0x18004af91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004af96  mov     ebx, eax
0x18004af98  jmp     loc_18004AEA7
0x18004af9d  test    eax, eax
0x18004af9f  jz      short loc_18004AFBB
0x18004afa1  mov     rcx, [rbp+18h]; this
0x18004afa5  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004afac  mov     r9d, eax; char *
0x18004afaf  mov     edx, 6Eh ; 'n'; void *
0x18004afb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004afb9  jmp     short loc_18004AF96
0x18004afbb  lea     rcx, [rbp+lpExistingFileName]; this
0x18004afbf  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004afc4  xor     ebx, ebx
0x18004afc6  lea     rcx, [rbp+lpPathName]; this
0x18004afca  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004afcf  lea     r11, [rsp+50h+var_s0]
0x18004afd4  mov     eax, ebx
0x18004afd6  mov     rbx, [r11+28h]
0x18004afda  mov     rsi, [r11+30h]
0x18004afde  mov     rsp, r11
0x18004afe1  pop     r14
0x18004afe3  pop     rdi
0x18004afe4  pop     rbp
0x18004afe5  retn
```

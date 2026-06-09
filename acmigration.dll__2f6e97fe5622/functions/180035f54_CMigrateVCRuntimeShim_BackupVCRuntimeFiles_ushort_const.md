# CMigrateVCRuntimeShim::BackupVCRuntimeFiles(ushort const *)

- ea: `0x180035f54`
- end: `0x180036326`
- name: `?BackupVCRuntimeFiles@CMigrateVCRuntimeShim@@QEAAKPEBG@Z`
- size: `978`
- prototype: `unsigned int __fastcall(CMigrateVCRuntimeShim *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180036330`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x180035f54`
- `0x180036384`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180036210`
- `KERNEL32!CreateDirectoryW` at `0x18003623b`
- `KERNEL32!CreateDirectoryW` at `0x180036210`
- `KERNEL32!CreateDirectoryW` at `0x18003623b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035fed`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180035fed`
- `KERNEL32!GetLastError` at `0x180035ff9`
- `KERNEL32!GetLastError` at `0x180036070`
- `KERNEL32!GetLastError` at `0x1800360ca`
- `KERNEL32!GetLastError` at `0x1800360f7`
- `KERNEL32!GetLastError` at `0x180036129`
- `KERNEL32!GetLastError` at `0x18003615b`
- `KERNEL32!GetLastError` at `0x18003618d`
- `KERNEL32!GetLastError` at `0x1800361bf`
- `KERNEL32!GetLastError` at `0x1800361f1`
- `KERNEL32!GetLastError` at `0x18003621a`
- `KERNEL32!GetLastError` at `0x180036245`
- `KERNEL32!GetLastError` at `0x180036278`
- `KERNEL32!GetLastError` at `0x1800362b8`
- `KERNEL32!GetLastError` at `0x180035ff9`
- `KERNEL32!GetLastError` at `0x180036070`
- `KERNEL32!GetLastError` at `0x1800360ca`
- `KERNEL32!GetLastError` at `0x1800360f7`
- `KERNEL32!GetLastError` at `0x180036129`
- `KERNEL32!GetLastError` at `0x18003615b`
- `KERNEL32!GetLastError` at `0x18003618d`
- `KERNEL32!GetLastError` at `0x1800361bf`
- `KERNEL32!GetLastError` at `0x1800361f1`
- `KERNEL32!GetLastError` at `0x18003621a`
- `KERNEL32!GetLastError` at `0x180036245`
- `KERNEL32!GetLastError` at `0x180036278`
- `KERNEL32!GetLastError` at `0x1800362b8`

## string_xrefs

- `0x1800360df`: `\System32`
- `0x180036173`: `\System32`
- `0x180036076`: `[MigrateVCRuntimeShim] Creating System32 backup string failed. [%d]`
- `0x1800360fd`: `[MigrateVCRuntimeShim] Concatenating System32 backup path failed. [%d]`
- `0x18003612f`: `[MigrateVCRuntimeShim] Concatenating Syswow64 backup path failed. [%d]`
- `0x180036161`: `[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]`
- `0x180036193`: `[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]`
- `0x1800361c5`: `[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]`
- `0x1800361f7`: `[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]`
- `0x180036220`: `[MigrateVCRuntimeShim] Creating System32 backup path failed. [%d]`
- `0x18003624b`: `[MigrateVCRuntimeShim] Creating Syswow64 backup path failed. [%d]`
- `0x18003628c`: `[MigrateVCRuntimeShim] No native (System32) files to copy.`
- `0x180036302`: `[MigrateVCRuntimeShim] copy native files failed. [%d]`
- `0x1800362cc`: `[MigrateVCRuntimeShim] No Wow (SysWow64) files to copy.`
- `0x180036314`: `[MigrateVCRuntimeShim] copy wow files failed. [%d]`

## pseudocode

```c
__int64 __fastcall CMigrateVCRuntimeShim::BackupVCRuntimeFiles(CMigrateVCRuntimeShim *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  DWORD v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  __int64 v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // r9
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  wchar_t *v14; // rax
  wchar_t *v15; // rcx
  CMigrateVCRuntimeShim *v16; // rcx
  CMigrateVCRuntimeShim *v17; // rcx
  wchar_t pszDest[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t PathName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR Dst[264]; // [rsp+450h] [rbp+350h] BYREF
  wchar_t v22[264]; // [rsp+660h] [rbp+560h] BYREF
  wchar_t v23[264]; // [rsp+870h] [rbp+770h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(pszDest, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(v22, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%", Dst, 0x104u) )
  {
    v7 = 2147483646;
    v8 = pszDest;
    v9 = 2147483646;
    v10 = a2;
    v11 = 260;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v8++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v12 = v8 - 1;
    if ( v11 )
      v12 = v8;
    *v12 = 0;
    if ( v11 )
    {
      v13 = 260;
      v14 = PathName;
      do
      {
        if ( !v7 )
          break;
        if ( !*a2 )
          break;
        *v14++ = *a2++;
        --v7;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( v13 )
      {
        if ( StringCchCatW(pszDest, 0x104u, L"\\System32") )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating System32 backup path failed. [%d]";
          v6 = 355;
        }
        else if ( StringCchCatW(PathName, 0x104u, L"\\SysWOW64") )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating Syswow64 backup path failed. [%d]";
          v6 = 361;
        }
        else if ( StringCchCatW(v22, 0x104u, Dst) )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]";
          v6 = 368;
        }
        else if ( StringCchCatW(v22, 0x104u, L"\\System32") )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]";
          v6 = 374;
        }
        else if ( StringCchCatW(v23, 0x104u, Dst) )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]";
          v6 = 380;
        }
        else if ( StringCchCatW(v23, 0x104u, L"\\SysWOW64") )
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]";
          v6 = 386;
        }
        else if ( CreateDirectoryW(pszDest, 0) )
        {
          if ( CreateDirectoryW(PathName, 0) )
          {
            if ( !CMigrateVCRuntimeShim::CopyVCRuntimeFiles(v16, v22, pszDest) )
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError != 2 )
              {
                v5 = "[MigrateVCRuntimeShim] copy native files failed. [%d]";
                v6 = 415;
                goto LABEL_3;
              }
              AslLogCallPrintf(
                3,
                "CMigrateVCRuntimeShim::BackupVCRuntimeFiles",
                411,
                "[MigrateVCRuntimeShim] No native (System32) files to copy.");
            }
            if ( !CMigrateVCRuntimeShim::CopyVCRuntimeFiles(v17, v23, PathName) )
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError != 2 )
              {
                v5 = "[MigrateVCRuntimeShim] copy wow files failed. [%d]";
                v6 = 430;
                goto LABEL_3;
              }
              AslLogCallPrintf(
                3,
                "CMigrateVCRuntimeShim::BackupVCRuntimeFiles",
                426,
                "[MigrateVCRuntimeShim] No Wow (SysWow64) files to copy.");
            }
            return 0;
          }
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Creating Syswow64 backup path failed. [%d]";
          v6 = 401;
        }
        else
        {
          LastError = GetLastError();
          v5 = "[MigrateVCRuntimeShim] Creating System32 backup path failed. [%d]";
          v6 = 394;
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = "[MigrateVCRuntimeShim] Creating Syswow64 backup string failed. [%d]";
        v6 = 348;
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = "[MigrateVCRuntimeShim] Creating System32 backup string failed. [%d]";
      v6 = 342;
    }
    v4 = LastError;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = "[MigrateVCRuntimeShim] Error expanding SystemRoot. [%d]";
    v6 = 334;
  }
LABEL_3:
  AslLogCallPrintf(1, "CMigrateVCRuntimeShim::BackupVCRuntimeFiles", v6, v5, LastError);
  return v4;
}

```

## disassembly

```asm
0x180035f54  push    rbp
0x180035f56  push    rbx
0x180035f57  push    rsi
0x180035f58  push    rdi
0x180035f59  push    r14
0x180035f5b  lea     rbp, [rsp-990h]
0x180035f63  sub     rsp, 0A90h
0x180035f6a  mov     rax, cs:__security_cookie
0x180035f71  xor     rax, rsp
0x180035f74  mov     [rbp+9B0h+var_30], rax
0x180035f7b  mov     rbx, rdx
0x180035f7e  lea     rcx, [rbp+9B0h+Dst]; void *
0x180035f85  mov     edi, 208h
0x180035f8a  xor     edx, edx; Val
0x180035f8c  mov     r8d, edi; Size
0x180035f8f  call    memset_0
0x180035f94  mov     r8d, edi; Size
0x180035f97  lea     rcx, [rsp+0AB0h+pszDest]; void *
0x180035f9c  xor     edx, edx; Val
0x180035f9e  call    memset_0
0x180035fa3  mov     r8d, edi; Size
0x180035fa6  lea     rcx, [rbp+9B0h+PathName]; void *
0x180035fad  xor     edx, edx; Val
0x180035faf  call    memset_0
0x180035fb4  mov     r8d, edi; Size
0x180035fb7  lea     rcx, [rbp+9B0h+var_450]; void *
0x180035fbe  xor     edx, edx; Val
0x180035fc0  call    memset_0
0x180035fc5  mov     r8d, edi; Size
0x180035fc8  lea     rcx, [rbp+9B0h+var_240]; void *
0x180035fcf  xor     edx, edx; Val
0x180035fd1  call    memset_0
0x180035fd6  mov     r14d, 104h
0x180035fdc  lea     rdx, [rbp+9B0h+Dst]; lpDst
0x180035fe3  mov     r8d, r14d; nSize
0x180035fe6  lea     rcx, aSystemroot_1; "%SystemRoot%"
0x180035fed  call    cs:__imp_ExpandEnvironmentStringsW
0x180035ff3  xor     esi, esi
0x180035ff5  test    eax, eax
0x180035ff7  jnz     short loc_180036024
0x180035ff9  call    cs:__imp_GetLastError
0x180035fff  mov     ebx, eax
0x180036001  lea     r9, aMigratevcrunti_10; "[MigrateVCRuntimeShim] Error expanding "...
0x180036008  lea     r8d, [r14+4Ah]
0x18003600c  lea     rdx, aCmigratevcrunt_0; "CMigrateVCRuntimeShim::BackupVCRuntimeF"...
0x180036013  lea     ecx, [rsi+1]
0x180036016  mov     [rsp+0AB0h+var_A90], eax
0x18003601a  call    AslLogCallPrintf
0x18003601f  jmp     loc_1800362E3
0x180036024  mov     r8d, 7FFFFFFEh
0x18003602a  lea     rax, [rsp+0AB0h+pszDest]
0x18003602f  mov     ecx, r8d
0x180036032  mov     r9, rbx
0x180036035  mov     rdx, r14
0x180036038  mov     edi, 1
0x18003603d  test    rcx, rcx
0x180036040  jz      short loc_180036060
0x180036042  movzx   r10d, word ptr [r9]
0x180036046  test    r10w, r10w
0x18003604a  jz      short loc_180036060
0x18003604c  mov     [rax], r10w
0x180036050  add     r9, 2
0x180036054  add     rax, 2
0x180036058  sub     rcx, rdi
0x18003605b  sub     rdx, rdi
0x18003605e  jnz     short loc_18003603D
0x180036060  test    rdx, rdx
0x180036063  lea     rcx, [rax-2]
0x180036067  cmovnz  rcx, rax
0x18003606b  mov     [rcx], si
0x18003606e  jnz     short loc_180036090
0x180036070  call    cs:__imp_GetLastError
0x180036076  lea     r9, aMigratevcrunti_6; "[MigrateVCRuntimeShim] Creating System3"...
0x18003607d  mov     r8d, 156h
0x180036083  mov     ebx, eax
0x180036085  lea     rdx, aCmigratevcrunt_0; "CMigrateVCRuntimeShim::BackupVCRuntimeF"...
0x18003608c  mov     ecx, edi
0x18003608e  jmp     short loc_180036016
0x180036090  mov     rdx, r14
0x180036093  lea     rax, [rbp+9B0h+PathName]
0x18003609a  test    r8, r8
0x18003609d  jz      short loc_1800360BA
0x18003609f  movzx   ecx, word ptr [rbx]
0x1800360a2  test    cx, cx
0x1800360a5  jz      short loc_1800360BA
0x1800360a7  mov     [rax], cx
0x1800360aa  add     rbx, 2
0x1800360ae  add     rax, 2
0x1800360b2  sub     r8, rdi
0x1800360b5  sub     rdx, rdi
0x1800360b8  jnz     short loc_18003609A
0x1800360ba  test    rdx, rdx
0x1800360bd  lea     rcx, [rax-2]
0x1800360c1  cmovnz  rcx, rax
0x1800360c5  mov     [rcx], si
0x1800360c8  jnz     short loc_1800360DF
0x1800360ca  call    cs:__imp_GetLastError
0x1800360d0  lea     r9, aMigratevcrunti_12; "[MigrateVCRuntimeShim] Creating Syswow6"...
0x1800360d7  mov     r8d, 15Ch
0x1800360dd  jmp     short loc_180036083
0x1800360df  lea     r8, aSystem32_1; "\\System32"
0x1800360e6  mov     rdx, r14; cchDest
0x1800360e9  lea     rcx, [rsp+0AB0h+pszDest]; pszDest
0x1800360ee  call    StringCchCatW
0x1800360f3  test    eax, eax
0x1800360f5  jz      short loc_18003610F
0x1800360f7  call    cs:__imp_GetLastError
0x1800360fd  lea     r9, aMigratevcrunti; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x180036104  mov     r8d, 163h
0x18003610a  jmp     loc_180036083
0x18003610f  lea     r8, aSyswow64; "\\SysWOW64"
0x180036116  mov     rdx, r14; cchDest
0x180036119  lea     rcx, [rbp+9B0h+PathName]; pszDest
0x180036120  call    StringCchCatW
0x180036125  test    eax, eax
0x180036127  jz      short loc_180036141
0x180036129  call    cs:__imp_GetLastError
0x18003612f  lea     r9, aMigratevcrunti_4; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x180036136  mov     r8d, 169h
0x18003613c  jmp     loc_180036083
0x180036141  lea     r8, [rbp+9B0h+Dst]; pszSrc
0x180036148  mov     rdx, r14; cchDest
0x18003614b  lea     rcx, [rbp+9B0h+var_450]; pszDest
0x180036152  call    StringCchCatW
0x180036157  test    eax, eax
0x180036159  jz      short loc_180036173
0x18003615b  call    cs:__imp_GetLastError
0x180036161  lea     r9, aMigratevcrunti_11; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x180036168  mov     r8d, 170h
0x18003616e  jmp     loc_180036083
0x180036173  lea     r8, aSystem32_1; "\\System32"
0x18003617a  mov     rdx, r14; cchDest
0x18003617d  lea     rcx, [rbp+9B0h+var_450]; pszDest
0x180036184  call    StringCchCatW
0x180036189  test    eax, eax
0x18003618b  jz      short loc_1800361A5
0x18003618d  call    cs:__imp_GetLastError
0x180036193  lea     r9, aMigratevcrunti_11; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x18003619a  mov     r8d, 176h
0x1800361a0  jmp     loc_180036083
0x1800361a5  lea     r8, [rbp+9B0h+Dst]; pszSrc
0x1800361ac  mov     rdx, r14; cchDest
0x1800361af  lea     rcx, [rbp+9B0h+var_240]; pszDest
0x1800361b6  call    StringCchCatW
0x1800361bb  test    eax, eax
0x1800361bd  jz      short loc_1800361D7
0x1800361bf  call    cs:__imp_GetLastError
0x1800361c5  lea     r9, aMigratevcrunti_2; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x1800361cc  mov     r8d, 17Ch
0x1800361d2  jmp     loc_180036083
0x1800361d7  lea     r8, aSyswow64; "\\SysWOW64"
0x1800361de  mov     rdx, r14; cchDest
0x1800361e1  lea     rcx, [rbp+9B0h+var_240]; pszDest
0x1800361e8  call    StringCchCatW
0x1800361ed  test    eax, eax
0x1800361ef  jz      short loc_180036209
0x1800361f1  call    cs:__imp_GetLastError
0x1800361f7  lea     r9, aMigratevcrunti_2; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x1800361fe  mov     r8d, 182h
0x180036204  jmp     loc_180036083
0x180036209  xor     edx, edx; lpSecurityAttributes
0x18003620b  lea     rcx, [rsp+0AB0h+pszDest]; lpPathName
0x180036210  call    cs:__imp_CreateDirectoryW
0x180036216  test    eax, eax
0x180036218  jnz     short loc_180036232
0x18003621a  call    cs:__imp_GetLastError
0x180036220  lea     r9, aMigratevcrunti_1; "[MigrateVCRuntimeShim] Creating System3"...
0x180036227  mov     r8d, 18Ah
0x18003622d  jmp     loc_180036083
0x180036232  xor     edx, edx; lpSecurityAttributes
0x180036234  lea     rcx, [rbp+9B0h+PathName]; lpPathName
0x18003623b  call    cs:__imp_CreateDirectoryW
0x180036241  test    eax, eax
0x180036243  jnz     short loc_18003625D
0x180036245  call    cs:__imp_GetLastError
0x18003624b  lea     r9, aMigratevcrunti_8; "[MigrateVCRuntimeShim] Creating Syswow6"...
0x180036252  mov     r8d, 191h
0x180036258  jmp     loc_180036083
0x18003625d  lea     r8, [rsp+0AB0h+pszDest]; unsigned __int16 *
0x180036262  lea     rdx, [rbp+9B0h+var_450]; unsigned __int16 *
0x180036269  call    ?CopyVCRuntimeFiles@CMigrateVCRuntimeShim@@AEAAHPEBG0@Z; CMigrateVCRuntimeShim::CopyVCRuntimeFiles(ushort const *,ushort const *)
0x18003626e  mov     r14d, 3
0x180036274  test    eax, eax
0x180036276  jnz     short loc_1800362A1
0x180036278  call    cs:__imp_GetLastError
0x18003627e  lea     rdx, aCmigratevcrunt_0; "CMigrateVCRuntimeShim::BackupVCRuntimeF"...
0x180036285  mov     ebx, eax
0x180036287  cmp     eax, 2
0x18003628a  jnz     short loc_180036302
0x18003628c  lea     r9, aMigratevcrunti_15; "[MigrateVCRuntimeShim] No native (Syste"...
0x180036293  mov     r8d, 19Bh
0x180036299  mov     ecx, r14d
0x18003629c  call    AslLogCallPrintf
0x1800362a1  lea     r8, [rbp+9B0h+PathName]; unsigned __int16 *
0x1800362a8  lea     rdx, [rbp+9B0h+var_240]; unsigned __int16 *
0x1800362af  call    ?CopyVCRuntimeFiles@CMigrateVCRuntimeShim@@AEAAHPEBG0@Z; CMigrateVCRuntimeShim::CopyVCRuntimeFiles(ushort const *,ushort const *)
0x1800362b4  test    eax, eax
0x1800362b6  jnz     short loc_1800362E1
0x1800362b8  call    cs:__imp_GetLastError
0x1800362be  lea     rdx, aCmigratevcrunt_0; "CMigrateVCRuntimeShim::BackupVCRuntimeF"...
0x1800362c5  mov     ebx, eax
0x1800362c7  cmp     eax, 2
0x1800362ca  jnz     short loc_180036314
0x1800362cc  lea     r9, aMigratevcrunti_9; "[MigrateVCRuntimeShim] No Wow (SysWow64"...
0x1800362d3  mov     r8d, 1AAh
0x1800362d9  mov     ecx, r14d
0x1800362dc  call    AslLogCallPrintf
0x1800362e1  mov     ebx, esi
0x1800362e3  mov     eax, ebx
0x1800362e5  mov     rcx, [rbp+9B0h+var_30]
0x1800362ec  xor     rcx, rsp; StackCookie
0x1800362ef  call    __security_check_cookie
0x1800362f4  add     rsp, 0A90h
0x1800362fb  pop     r14
0x1800362fd  pop     rdi
0x1800362fe  pop     rsi
0x1800362ff  pop     rbx
0x180036300  pop     rbp
0x180036301  retn
0x180036302  lea     r9, aMigratevcrunti_16; "[MigrateVCRuntimeShim] copy native file"...
0x180036309  mov     r8d, 19Fh
0x18003630f  jmp     loc_18003608C
0x180036314  lea     r9, aMigratevcrunti_7; "[MigrateVCRuntimeShim] copy wow files f"...
0x18003631b  mov     r8d, 1AEh
0x180036321  jmp     loc_18003608C
```

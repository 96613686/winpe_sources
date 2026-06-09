# SetupDUUpdateFiles(ushort const * * const,uint,ushort const *,ushort const *,SetupDUMergeType)

- ea: `0x140055684`
- end: `0x140055b43`
- name: `?SetupDUUpdateFiles@@YAJQEAPEBGIPEBG1W4SetupDUMergeType@@@Z`
- size: `1215`
- prototype: `signed int __fastcall(_QWORD *, unsigned int, __int64, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x140015e10`

## callees

- `0x140021f6c`
- `0x140022960`
- `0x140023c8c`
- `0x140024510`
- `0x14002571c`
- `0x140026684`
- `0x140027028`
- `0x1400552c8`
- `0x140055684`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140055af9`
- `KERNEL32!HeapFree` at `0x140055af9`
- `KERNEL32!GetProcessHeap` at `0x140055ae5`
- `KERNEL32!GetProcessHeap` at `0x140055ae5`
- `KERNEL32!GetLastError` at `0x140055779`
- `KERNEL32!GetLastError` at `0x140055799`
- `KERNEL32!GetLastError` at `0x1400558e3`
- `KERNEL32!GetLastError` at `0x140055997`
- `KERNEL32!GetLastError` at `0x140055a14`
- `KERNEL32!GetLastError` at `0x140055a91`
- `KERNEL32!GetLastError` at `0x140055779`
- `KERNEL32!GetLastError` at `0x140055799`
- `KERNEL32!GetLastError` at `0x1400558e3`
- `KERNEL32!GetLastError` at `0x140055997`
- `KERNEL32!GetLastError` at `0x140055a14`
- `KERNEL32!GetLastError` at `0x140055a91`
- `msvcrt!wcsrchr` at `0x140055943`
- `msvcrt!wcsrchr` at `0x140055943`

## string_xrefs

- `0x140055729`: `SetupDUUpdateFiles: Source directory [%s] does not exist.`
- `0x140055719`: `SetupDUUpdateFiles: Target directory [%s] does not exist.`
- `0x140055761`: `SetupDUUpdateFiles: Could not determine whether target directory [%s] is empty.`
- `0x1400557c5`: `SetupDUUpdateFiles: Target directory [%s] should be empty in the presence of reference directory [%s].`
- `0x140055a59`: `Source directory [%s] has older files; will not copy it`
- `0x140055a73`: `Source directory [%s] has newer files; will copy it`
- `0x140055ab8`: `Source directory [%s] does not have newer files; will skip it`
- `0x140055970`: `Creating directory [%s]`
- `0x1400559db`: `Copying [%s] -> [%s]`

## pseudocode

```c
signed int __fastcall SetupDUUpdateFiles(_QWORD *a1, unsigned int a2, __int64 a3, const wchar_t *a4, unsigned int a5)
{
  __int64 v8; // r13
  unsigned int v9; // r14d
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  signed int result; // eax
  signed int LastError; // eax
  bool v14; // sf
  signed int v15; // edi
  __int64 v16; // rdx
  const WCHAR *v17; // r10
  __int64 v18; // rax
  signed int v19; // eax
  _QWORD *i; // rbx
  wchar_t *v21; // r14
  signed int v22; // eax
  signed int v23; // eax
  __int64 v24; // r9
  signed int v25; // eax
  LPVOID *j; // rax
  LPVOID *v27; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD v29[3]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h] BYREF
  const wchar_t *v31; // [rsp+60h] [rbp-29h]
  const wchar_t *v32; // [rsp+68h] [rbp-21h]
  __int64 v33; // [rsp+70h] [rbp-19h]
  int v34; // [rsp+78h] [rbp-11h]
  LPVOID lpMem[2]; // [rsp+88h] [rbp-1h]
  char v36; // [rsp+98h] [rbp+Fh]
  __int64 v37; // [rsp+E8h] [rbp+5Fh]
  int v39; // [rsp+F8h] [rbp+6Fh]

  v8 = 0;
  if ( !a1 )
    return -2147024809;
  if ( !a2 )
    return -2147024809;
  if ( !a4 )
    return -2147024809;
  v9 = a5;
  if ( a5 > 1 )
    return -2147024809;
  v10 = 0;
  v11 = a1;
  do
  {
    if ( !(unsigned int)DirectoryExists(*v11) )
    {
      LibLog(&g_SetupDULog, 0x2000000, L"SetupDUUpdateFiles: Source directory [%s] does not exist.", a1[v10]);
      return -2147024893;
    }
    ++v10;
    ++v11;
  }
  while ( v10 < a2 );
  if ( !(unsigned int)DirectoryExists(a4) )
  {
    LibLog(&g_SetupDULog, 0x2000000, L"SetupDUUpdateFiles: Target directory [%s] does not exist.", a4);
    return -2147024893;
  }
  if ( !(unsigned int)IsEmptyDirectory(a4) )
  {
    LibLog(
      &g_SetupDULog,
      0x2000000,
      L"SetupDUUpdateFiles: Could not determine whether target directory [%s] is empty.",
      a4);
    LastError = GetLastError();
    v14 = LastError < 0;
    if ( LastError > 0 )
      v14 = 1;
    if ( !v14 )
      return -2147467259;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v15 = 0;
  g_WdsLibLog = (__int64)&lambda_a358e63619279849b6d2d2bf87dd1830_::_lambda_invoker_cdecl_;
  g_WdsNativeLibLog = (__int64)&lambda_a358e63619279849b6d2d2bf87dd1830_::_lambda_invoker_cdecl_;
  v16 = -1;
  do
    ++v16;
  while ( a4[v16] );
  v37 = v16;
  v39 = 0;
  while ( (unsigned int)v8 < a2 )
  {
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    *(_OWORD *)lpMem = 0;
    v36 = 0;
    v17 = 0;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v17 = (const WCHAR *)a1[v8];
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        v30 = v18;
        v31 = a4;
      }
    }
    else
    {
      v17 = a4;
      v30 = v16;
      v31 = (const wchar_t *)a1[v8];
    }
    v32 = a4;
    LODWORD(v33) = v9;
    v36 = 1;
    v29[0] = 1;
    v29[1] = &v30;
    v29[2] = EnumerateDirCallback;
    if ( (unsigned int)EnumeratePathEx(
                         v17,
                         (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))EnumeratePathDirCallback,
                         (__int64 (__fastcall *)(DWORD *, __int64))EnumeratePathFileCallback,
                         (__int64)v29,
                         0) )
    {
      v15 = 0;
    }
    else
    {
      v19 = GetLastError();
      v15 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v15 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v15 = -2147024865;
      }
      if ( v15 < 0 )
        goto LABEL_71;
    }
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        for ( i = lpMem[0]; i; i = (_QWORD *)i[2] )
        {
          if ( v15 >= 0 )
          {
            v21 = wcsrchr((const wchar_t *)i[1], 0x5Cu);
            if ( !v21 )
              goto LABEL_53;
            *v21 = 0;
            if ( !(unsigned int)DirectoryExists(i[1]) )
            {
              LibLog(&g_SetupDULog, 0x4000000, L"Creating directory [%s]", i[1]);
              if ( (unsigned int)CreatePath(i[1]) )
              {
                v15 = 0;
              }
              else
              {
                v22 = GetLastError();
                v15 = v22;
                if ( v22 )
                {
                  if ( v22 > 0 )
                    v15 = (unsigned __int16)v22 | 0x80070000;
                }
                else
                {
                  v15 = -2147024865;
                }
              }
            }
            *v21 = 92;
            if ( v15 >= 0 )
            {
LABEL_53:
              v39 = 1;
              LibLog(&g_SetupDULog, 0x4000000, L"Copying [%s] -> [%s]", *i, i[1]);
              if ( (unsigned int)CopyFileWithAttributesEx2(*i, i[1], 0, 0, 0) )
              {
                v15 = 0;
              }
              else
              {
                v23 = GetLastError();
                v15 = v23;
                if ( v23 )
                {
                  if ( v23 > 0 )
                    v15 = (unsigned __int16)v23 | 0x80070000;
                }
                else
                {
                  v15 = -2147024865;
                }
              }
            }
          }
        }
        v9 = a5;
      }
    }
    else
    {
      v24 = a1[v8];
      if ( HIDWORD(v33) )
      {
        LibLog(&g_SetupDULog, 0x4000000, L"Source directory [%s] has older files; will not copy it", v24);
      }
      else if ( v34 )
      {
        v39 = 1;
        LibLog(&g_SetupDULog, 0x4000000, L"Source directory [%s] has newer files; will copy it", v24);
        if ( (unsigned int)CopyDirectory(a1[v8], a4) )
        {
          v15 = 0;
        }
        else
        {
          v25 = GetLastError();
          v15 = v25;
          if ( v25 )
          {
            if ( v25 > 0 )
              v15 = (unsigned __int16)v25 | 0x80070000;
          }
          else
          {
            v15 = -2147024865;
          }
        }
      }
      else
      {
        LibLog(&g_SetupDULog, 0x4000000, L"Source directory [%s] does not have newer files; will skip it", v24);
      }
    }
LABEL_71:
    for ( j = (LPVOID *)lpMem[0]; j; j = (LPVOID *)lpMem[0] )
    {
      v27 = j;
      lpMem[0] = j[2];
      FileCopyInfo::~FileCopyInfo((FileCopyInfo *)j);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v27);
    }
    v8 = (unsigned int)(v8 + 1);
    v16 = v37;
    if ( v15 < 0 )
      break;
  }
  g_WdsLibLog = 0;
  g_WdsNativeLibLog = 0;
  if ( v15 >= 0 && !v39 )
    return 1;
  return v15;
}

```

## disassembly

```asm
0x140055684  mov     rax, rsp
0x140055687  mov     [rax+18h], r8
0x14005568b  mov     [rax+10h], edx
0x14005568e  push    rbp
0x14005568f  push    rsi
0x140055690  push    rdi
0x140055691  push    r12
0x140055693  push    r13
0x140055695  push    r14
0x140055697  push    r15
0x140055699  lea     rbp, [rax-57h]
0x14005569d  sub     rsp, 0A0h
0x1400556a4  mov     [rbp+4Fh+var_A0], 0FFFFFFFFFFFFFFFEh
0x1400556ac  mov     [rax+20h], rbx
0x1400556b0  mov     rsi, r9
0x1400556b3  mov     r12d, edx
0x1400556b6  mov     r15, rcx
0x1400556b9  xor     r13d, r13d
0x1400556bc  test    rcx, rcx
0x1400556bf  jz      loc_1400557DD
0x1400556c5  test    edx, edx
0x1400556c7  jz      loc_1400557DD
0x1400556cd  test    r9, r9
0x1400556d0  jz      loc_1400557DD
0x1400556d6  lea     eax, [r13+1]
0x1400556da  mov     r14d, [rbp+4Fh+arg_20]
0x1400556de  cmp     r14d, eax
0x1400556e1  ja      loc_1400557DD
0x1400556e7  mov     ebx, r13d
0x1400556ea  test    edx, edx
0x1400556ec  jz      short loc_140055708
0x1400556ee  mov     rdi, rcx
0x1400556f1  mov     rcx, [rdi]
0x1400556f4  call    DirectoryExists
0x1400556f9  test    eax, eax
0x1400556fb  jz      short loc_140055722
0x1400556fd  inc     ebx
0x1400556ff  add     rdi, 8
0x140055703  cmp     ebx, r12d
0x140055706  jb      short loc_1400556F1
0x140055708  mov     rcx, rsi
0x14005570b  call    DirectoryExists
0x140055710  xor     ebx, ebx
0x140055712  test    eax, eax
0x140055714  jnz     short loc_14005574B
0x140055716  mov     r9, rsi
0x140055719  lea     r8, aSetupduupdatef; "SetupDUUpdateFiles: Target directory [%"...
0x140055720  jmp     short loc_140055730
0x140055722  mov     r9d, ebx
0x140055725  mov     r9, [r15+r9*8]
0x140055729  lea     r8, aSetupduupdatef_1; "SetupDUUpdateFiles: Source directory [%"...
0x140055730  mov     edx, 2000000h
0x140055735  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x14005573c  call    LibLog
0x140055741  mov     eax, 80070003h
0x140055746  jmp     loc_1400557E2
0x14005574b  mov     [rbp+4Fh+arg_10], ebx
0x14005574e  lea     rdx, [rbp+4Fh+arg_10]
0x140055752  mov     rcx, rsi; pszSrc
0x140055755  call    IsEmptyDirectory
0x14005575a  test    eax, eax
0x14005575c  jnz     short loc_1400557B8
0x14005575e  mov     r9, rsi
0x140055761  lea     r8, aSetupduupdatef_0; "SetupDUUpdateFiles: Could not determine"...
0x140055768  mov     edx, 2000000h
0x14005576d  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x140055774  call    LibLog
0x140055779  call    cs:__imp_GetLastError
0x140055780  nop     dword ptr [rax+rax+00h]
0x140055785  mov     r12d, 80070000h
0x14005578b  test    eax, eax
0x14005578d  jle     short loc_140055797
0x14005578f  movzx   eax, ax
0x140055792  or      eax, r12d
0x140055795  test    eax, eax
0x140055797  jns     short loc_1400557B1
0x140055799  call    cs:__imp_GetLastError
0x1400557a0  nop     dword ptr [rax+rax+00h]
0x1400557a5  test    eax, eax
0x1400557a7  jle     short loc_1400557E2
0x1400557a9  movzx   eax, ax
0x1400557ac  or      eax, r12d
0x1400557af  jmp     short loc_1400557E2
0x1400557b1  mov     eax, 80004005h
0x1400557b6  jmp     short loc_1400557E2
0x1400557b8  cmp     [rbp+4Fh+arg_10], ebx
0x1400557bb  jz      short loc_1400557FE
0x1400557bd  mov     [rsp+20h], rbx
0x1400557c2  mov     r9, rsi
0x1400557c5  lea     r8, aSetupduupdatef_2; "SetupDUUpdateFiles: Target directory [%"...
0x1400557cc  mov     edx, 2000000h
0x1400557d1  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x1400557d8  call    LibLog
0x1400557dd  mov     eax, 80070057h
0x1400557e2  mov     rbx, [rsp+0D0h+arg_18]
0x1400557ea  add     rsp, 0A0h
0x1400557f1  pop     r15
0x1400557f3  pop     r14
0x1400557f5  pop     r13
0x1400557f7  pop     r12
0x1400557f9  pop     rdi
0x1400557fa  pop     rsi
0x1400557fb  pop     rbp
0x1400557fc  retn
0x1400557fe  mov     edi, ebx
0x140055800  lea     rax, _lambda_a358e63619279849b6d2d2bf87dd1830____lambda_invoker_cdecl_
0x140055807  mov     cs:g_WdsLibLog, rax
0x14005580e  mov     cs:g_WdsNativeLibLog, rax
0x140055815  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140055819  inc     rdx
0x14005581c  cmp     [rsi+rdx*2], bx
0x140055820  jnz     short loc_140055819
0x140055822  mov     [rbp+4Fh+arg_0], rdx
0x140055826  mov     [rbp+4Fh+arg_10], ebx
0x140055829  mov     r12d, 80070000h
0x14005582f  mov     r8d, 1
0x140055835  cmp     r13d, [rbp+4Fh+arg_8]
0x140055839  jnb     loc_140055B23
0x14005583f  mov     [rbp+4Fh+var_80], rbx
0x140055843  mov     [rbp+4Fh+var_78], rbx
0x140055847  mov     [rbp+4Fh+var_70], rbx
0x14005584b  mov     [rbp+4Fh+var_68], 0
0x140055853  mov     [rbp+4Fh+var_60], ebx
0x140055856  xorps   xmm0, xmm0
0x140055859  movdqa  xmmword ptr [rbp+4Fh+lpMem], xmm0
0x14005585e  mov     [rbp+4Fh+var_40], bl
0x140055861  mov     r10, rbx
0x140055864  test    r14d, r14d
0x140055867  jz      short loc_14005588B
0x140055869  cmp     r14d, 1
0x14005586d  jnz     short loc_14005589A
0x14005586f  mov     r10, [r15+r13*8]
0x140055873  or      rax, 0FFFFFFFFFFFFFFFFh
0x140055877  inc     rax
0x14005587a  cmp     [r10+rax*2], bx
0x14005587f  jnz     short loc_140055877
0x140055881  mov     [rbp+4Fh+var_80], rax
0x140055885  mov     [rbp+4Fh+var_78], rsi
0x140055889  jmp     short loc_14005589A
0x14005588b  mov     r10, rsi
0x14005588e  mov     [rbp+4Fh+var_80], rdx
0x140055892  mov     rcx, [r15+r13*8]
0x140055896  mov     [rbp+4Fh+var_78], rcx
0x14005589a  mov     [rbp+4Fh+var_70], rsi
0x14005589e  mov     dword ptr [rbp+4Fh+var_68], r14d
0x1400558a2  mov     [rbp+4Fh+var_40], r8b
0x1400558a6  mov     [rbp+4Fh+var_98], 1
0x1400558ae  lea     rax, [rbp+4Fh+var_80]
0x1400558b2  mov     [rbp+4Fh+var_90], rax
0x1400558b6  lea     rax, EnumerateDirCallback
0x1400558bd  mov     [rbp+4Fh+var_88], rax
0x1400558c1  mov     [rsp+20h], ebx; int
0x1400558c5  lea     r9, [rbp+4Fh+var_98]
0x1400558c9  lea     r8, EnumeratePathFileCallback
0x1400558d0  lea     rdx, EnumeratePathDirCallback
0x1400558d7  mov     rcx, r10; lpFileName
0x1400558da  call    EnumeratePathEx
0x1400558df  test    eax, eax
0x1400558e1  jnz     short loc_14005590E
0x1400558e3  call    cs:__imp_GetLastError
0x1400558ea  nop     dword ptr [rax+rax+00h]
0x1400558ef  mov     edi, eax
0x1400558f1  test    eax, eax
0x1400558f3  jnz     short loc_1400558FC
0x1400558f5  mov     edi, 8007001Fh
0x1400558fa  jmp     short loc_140055904
0x1400558fc  jle     short loc_140055904
0x1400558fe  movzx   edi, ax
0x140055901  or      edi, r12d
0x140055904  test    edi, edi
0x140055906  js      loc_140055AC7
0x14005590c  jmp     short loc_140055910
0x14005590e  mov     edi, ebx
0x140055910  test    r14d, r14d
0x140055913  jz      loc_140055A44
0x140055919  cmp     r14d, 1
0x14005591d  jnz     loc_140055AC7
0x140055923  mov     rbx, [rbp+4Fh+lpMem]
0x140055927  xor     ecx, ecx
0x140055929  test    rbx, rbx
0x14005592c  jz      loc_140055AC1
0x140055932  test    edi, edi
0x140055934  js      loc_140055A3B
0x14005593a  mov     edx, 5Ch ; '\'; Ch
0x14005593f  mov     rcx, [rbx+8]; Str
0x140055943  call    cs:__imp_wcsrchr
0x14005594a  nop     dword ptr [rax+rax+00h]
0x14005594f  mov     r14, rax
0x140055952  xor     eax, eax
0x140055954  test    r14, r14
0x140055957  jz      short loc_1400559C8
0x140055959  mov     [r14], ax
0x14005595d  mov     rcx, [rbx+8]
0x140055961  call    DirectoryExists
0x140055966  xor     ecx, ecx
0x140055968  test    eax, eax
0x14005596a  jnz     short loc_1400559BE
0x14005596c  mov     r9, [rbx+8]
0x140055970  lea     r8, aCreatingDirect; "Creating directory [%s]"
0x140055977  mov     edx, 4000000h
0x14005597c  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x140055983  call    LibLog
0x140055988  mov     rcx, [rbx+8]
0x14005598c  call    CreatePath
0x140055991  xor     ecx, ecx
0x140055993  test    eax, eax
0x140055995  jnz     short loc_1400559BC
0x140055997  call    cs:__imp_GetLastError
0x14005599e  nop     dword ptr [rax+rax+00h]
0x1400559a3  mov     edi, eax
0x1400559a5  xor     ecx, ecx
0x1400559a7  test    eax, eax
0x1400559a9  jnz     short loc_1400559B2
0x1400559ab  mov     edi, 8007001Fh
0x1400559b0  jmp     short loc_1400559BE
0x1400559b2  jle     short loc_1400559BE
0x1400559b4  movzx   edi, ax
0x1400559b7  or      edi, r12d
0x1400559ba  jmp     short loc_1400559BE
0x1400559bc  mov     edi, ecx
0x1400559be  mov     word ptr [r14], 5Ch ; '\'
0x1400559c4  test    edi, edi
0x1400559c6  js      short loc_140055A3B
0x1400559c8  mov     [rbp+4Fh+arg_10], 1
0x1400559cf  mov     rax, [rbx+8]
0x1400559d3  mov     [rsp+20h], rax
0x1400559d8  mov     r9, [rbx]
0x1400559db  lea     r8, aCopyingSS_0; "Copying [%s] -> [%s]"
0x1400559e2  mov     edx, 4000000h
0x1400559e7  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x1400559ee  call    LibLog
0x1400559f3  mov     qword ptr [rsp+20h], 0
0x1400559fc  xor     r9d, r9d
0x1400559ff  xor     r8d, r8d
0x140055a02  mov     rdx, [rbx+8]
0x140055a06  mov     rcx, [rbx]
0x140055a09  call    CopyFileWithAttributesEx2
0x140055a0e  xor     ecx, ecx
0x140055a10  test    eax, eax
0x140055a12  jnz     short loc_140055A39
0x140055a14  call    cs:__imp_GetLastError
0x140055a1b  nop     dword ptr [rax+rax+00h]
0x140055a20  mov     edi, eax
0x140055a22  xor     ecx, ecx
0x140055a24  test    eax, eax
0x140055a26  jnz     short loc_140055A2F
0x140055a28  mov     edi, 8007001Fh
0x140055a2d  jmp     short loc_140055A3B
0x140055a2f  jle     short loc_140055A3B
0x140055a31  movzx   edi, ax
0x140055a34  or      edi, r12d
0x140055a37  jmp     short loc_140055A3B
0x140055a39  mov     edi, ecx
0x140055a3b  mov     rbx, [rbx+10h]
0x140055a3f  jmp     loc_140055929
0x140055a44  mov     r9, [r15+r13*8]
0x140055a48  mov     edx, 4000000h
0x140055a4d  lea     rcx, ?g_SetupDULog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_SetupDULog
0x140055a54  cmp     dword ptr [rbp+4Fh+var_68+4], ebx
0x140055a57  jbe     short loc_140055A67
0x140055a59  lea     r8, aSourceDirector_0; "Source directory [%s] has older files; "...
0x140055a60  call    LibLog
0x140055a65  jmp     short loc_140055AC7
0x140055a67  cmp     [rbp+4Fh+var_60], ebx
0x140055a6a  jbe     short loc_140055AB8
0x140055a6c  mov     [rbp+4Fh+arg_10], 1
0x140055a73  lea     r8, aSourceDirector_1; "Source directory [%s] has newer files; "...
0x140055a7a  call    LibLog
0x140055a7f  mov     rdx, rsi
0x140055a82  mov     rcx, [r15+r13*8]
0x140055a86  call    CopyDirectory
0x140055a8b  xor     ebx, ebx
0x140055a8d  test    eax, eax
0x140055a8f  jnz     short loc_140055AB4
0x140055a91  call    cs:__imp_GetLastError
0x140055a98  nop     dword ptr [rax+rax+00h]
0x140055a9d  mov     edi, eax
0x140055a9f  test    eax, eax
0x140055aa1  jnz     short loc_140055AAA
0x140055aa3  mov     edi, 8007001Fh
0x140055aa8  jmp     short loc_140055AC7
0x140055aaa  jle     short loc_140055AC7
0x140055aac  movzx   edi, ax
0x140055aaf  or      edi, r12d
0x140055ab2  jmp     short loc_140055AC7
0x140055ab4  mov     edi, ebx
0x140055ab6  jmp     short loc_140055AC7
0x140055ab8  lea     r8, aSourceDirector; "Source directory [%s] does not have new"...
0x140055abf  jmp     short loc_140055A60
0x140055ac1  mov     r14d, [rbp+4Fh+arg_20]
0x140055ac5  xor     ebx, ebx
0x140055ac7  mov     rax, [rbp+4Fh+lpMem]
0x140055acb  jmp     short loc_140055B0B
0x140055acd  mov     rbx, rax
0x140055ad0  mov     rax, [rax+10h]
0x140055ad4  mov     [rbp+4Fh+lpMem], rax
0x140055ad8  test    rbx, rbx
0x140055adb  jz      short loc_140055B09
0x140055add  mov     rcx, rbx; this
0x140055ae0  call    ??1FileCopyInfo@@QEAA@XZ; FileCopyInfo::~FileCopyInfo(void)
  ... truncated ...
```

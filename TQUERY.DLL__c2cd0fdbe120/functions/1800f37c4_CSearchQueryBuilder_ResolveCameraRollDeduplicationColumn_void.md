# CSearchQueryBuilder::ResolveCameraRollDeduplicationColumn(void)

- ea: `0x1800f37c4`
- end: `0x1800f3db8`
- name: `?ResolveCameraRollDeduplicationColumn@CSearchQueryBuilder@@AEAAXXZ`
- size: `1524`
- prototype: `void __fastcall(CSearchQueryBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18020f59c`

## callees

- `0x18008efd8`
- `0x18008f4a4`
- `0x18008facc`
- `0x18008fb4c`
- `0x1800f37c4`
- `0x1800f3dc0`
- `0x1800f3e90`
- `0x180177de8`
- `0x180188d90`
- `0x18019b924`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800f3927`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800f3927`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f38b0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f38db`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f3adc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f3b07`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f38b0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f38db`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f3adc`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f3b07`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f39e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3a58`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f39e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f3a58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3bf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f3bf5`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1800f3be1`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1800f3be1`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f3824`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f3858`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f3824`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800f3858`

## string_xrefs

- `0x1800f38d4`: `path:`
- `0x1800f3b00`: `path:`
- `0x1800f3d81`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x1800f3da0`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSearchQueryBuilder::ResolveCameraRollDeduplicationColumn(CSearchQueryBuilder *this)
{
  CSearchQueryBuilder *v1; // rbx
  bool v2; // r12
  bool v3; // r15
  char v4; // r13
  unsigned int v5; // edi
  wchar_t *v6; // rax
  __int64 v7; // rbx
  wchar_t *v8; // rax
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t v11; // r8
  unsigned int v12; // r9d
  __int64 v13; // rsi
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  wchar_t *v20; // rax
  __int64 v21; // rbx
  wchar_t *v22; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PWSTR ppszCanonicalName; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  CSearchQueryBuilder *v30; // [rsp+60h] [rbp-A0h]
  _DWORD v31[2]; // [rsp+68h] [rbp-98h] BYREF
  void ***v32; // [rsp+70h] [rbp-90h]
  void **v33; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *Str; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  unsigned int v36; // [rsp+94h] [rbp-6Ch]
  wchar_t v37[1028]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F8h] [rbp+7F8h]

  v1 = this;
  v30 = this;
  ppszPath = 0;
  v28 = -1;
  v29 = -1;
  if ( SHGetKnownFolderPath(&FOLDERID_CameraRoll, 0x4000u, 0, &ppszPath) < 0 )
    goto LABEL_51;
  v2 = 0;
  v3 = 0;
  ppszCanonicalName = 0;
  v25 = -1;
  v26 = -1;
  if ( SHGetKnownFolderPath(&FOLDERID_SkyDriveCameraRoll, 0x4000u, 0, &ppszCanonicalName) < 0 )
    goto LABEL_48;
  v33 = &CLMString::`vftable';
  Str = v37;
  v35 = 1025;
  CLMString::AssignInConstructor((CLMString *)&v33, *((const wchar_t **)v1 + 812), 0xFFFFFFFF);
  v33 = &TLMString<1024,1024,1048576>::`vftable';
  v4 = 0;
  v5 = -1;
  v6 = wcsstr(Str, L"file:");
  if ( v6 )
  {
    v7 = v6 - Str;
    if ( (_DWORD)v7 != -1 )
      v5 = v7 + 5;
  }
  else
  {
    LODWORD(v7) = -1;
  }
  v8 = wcsstr(Str, L"path:");
  if ( v8 )
  {
    v9 = v8 - Str;
    if ( (_DWORD)v9 != -1 && ((_DWORD)v7 == -1 || (int)v9 < (int)v7) )
    {
      v4 = 1;
LABEL_97:
      v5 = v9 + 5;
    }
  }
  while ( (!v2 || !v3) && v5 != -1 )
  {
    if ( v5 >= v36 || (v10 = wcschr(&Str[v5], 0x27u)) == 0 || (v13 = v10 - Str, (_DWORD)v13 == -1) )
    {
      v5 = -1;
    }
    else
    {
      v14 = (unsigned int)v13 - v5 - 1;
      v15 = v14;
      if ( v14 + v5 < v5 )
        goto LABEL_94;
      if ( v14 + v5 > v36 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          bIgnoreCase);
      v31[0] = v5;
      v31[1] = v13 - v5 - 1;
      v32 = &v33;
      CLMSubStr::ReplaceAll((CLMSubStr *)v31, v14, v11, v12);
      if ( !v2 )
      {
        v16 = v28;
        if ( v4 )
        {
          if ( v28 != -1 )
            goto LABEL_24;
          if ( ppszPath )
          {
            v16 = -1;
            do
              ++v16;
            while ( ppszPath[v16] );
            goto LABEL_64;
          }
        }
        else
        {
          if ( v28 == -1 )
          {
            if ( ppszPath )
            {
              v16 = -1;
              do
                ++v16;
              while ( ppszPath[v16] );
              v28 = v16;
            }
            else
            {
              v16 = 0;
              v28 = 0;
            }
          }
          if ( v15 < v16 )
          {
            LODWORD(v16) = v13 - v5 - 1;
LABEL_24:
            v2 = CompareStringOrdinal(&Str[v5], v16, ppszPath, v16, 1) == 2;
            goto LABEL_25;
          }
          if ( v16 != -1 )
            goto LABEL_24;
          if ( ppszPath )
          {
            v16 = -1;
            do
              ++v16;
            while ( ppszPath[v16] );
LABEL_64:
            v28 = v16;
            goto LABEL_24;
          }
        }
        v28 = 0;
        LODWORD(v16) = 0;
        goto LABEL_24;
      }
LABEL_25:
      if ( !v3 )
      {
        if ( v4 )
        {
          LODWORD(v15) = v25;
          if ( v25 == -1 )
          {
            if ( ppszCanonicalName )
            {
              v15 = -1;
              do
                ++v15;
              while ( ppszCanonicalName[v15] );
              v25 = v15;
            }
            else
            {
              LODWORD(v15) = 0;
              v25 = 0;
            }
          }
        }
        else
        {
          v17 = v25;
          if ( v25 == -1 )
          {
            if ( ppszCanonicalName )
            {
              v17 = -1;
              do
                ++v17;
              while ( ppszCanonicalName[v17] );
              v25 = v17;
            }
            else
            {
              v17 = 0;
              v25 = 0;
            }
          }
          if ( v15 >= v17 )
          {
            if ( v17 == -1 )
            {
              if ( ppszCanonicalName )
              {
                v17 = -1;
                do
                  ++v17;
                while ( ppszCanonicalName[v17] );
                v25 = v17;
              }
              else
              {
                LODWORD(v17) = 0;
                v25 = 0;
              }
            }
            LODWORD(v15) = v17;
          }
        }
        v3 = CompareStringOrdinal(&Str[v5], v15, ppszCanonicalName, v15, 1) == 2;
      }
      if ( !v2 || !v3 )
      {
        v18 = (unsigned int)(v13 + 1);
        v19 = v36 - ((_DWORD)v13 + 1) + v18;
        if ( v19 < v18 )
LABEL_94:
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        if ( v19 > v36 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x40C,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            bIgnoreCase);
        ((void (__fastcall *)(void ***, wchar_t *, _QWORD))v33[4])(&v33, &Str[v18], 0);
        v4 = 0;
        v5 = -1;
        v20 = wcsstr(Str, L"file:");
        if ( v20 )
        {
          v21 = v20 - Str;
          if ( (_DWORD)v21 != -1 )
            v5 = v21 + 5;
        }
        else
        {
          LODWORD(v21) = -1;
        }
        v22 = wcsstr(Str, L"path:");
        if ( v22 )
        {
          v9 = v22 - Str;
          if ( (_DWORD)v9 != -1 && ((_DWORD)v21 == -1 || (int)v9 < (int)v21) )
          {
            v4 = 1;
            goto LABEL_97;
          }
        }
      }
    }
  }
  v33 = &TLMString<1024,1024,1048576>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v33, v37);
  v1 = v30;
LABEL_48:
  if ( ppszCanonicalName )
    CoTaskMemFree(ppszCanonicalName);
  if ( v2 && v3 )
  {
    ppszCanonicalName = 0;
    v25 = -1;
    v26 = -1;
    if ( PSGetNameFromPropertyKey(&PKEY_CameraRollDeduplicationId, &ppszCanonicalName) >= 0 )
    {
      v33 = &CLMString::`vftable';
      Str = v37;
      v35 = 1025;
      v36 = MultiByteToWideCharSZ(", ", 2, v37, 3);
      v33 = &TLMString<1024,1024,1048576>::`vftable';
      CLMString::operator=((char *)v1 + 12728, Str);
      v33 = &TLMString<1024,1024,1048576>::`vftable';
      CLMString::DeleteBuf((CLMString *)&v33, v37);
      CLMString::Append((CSearchQueryBuilder *)((char *)v1 + 12728), ppszCanonicalName, 0xFFFFFFFF);
    }
    if ( ppszCanonicalName )
      CoTaskMemFree(ppszCanonicalName);
  }
LABEL_51:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
}

```

## disassembly

```asm
0x1800f37c4  push    rbp
0x1800f37c6  push    rbx
0x1800f37c7  push    rsi
0x1800f37c8  push    rdi
0x1800f37c9  push    r12
0x1800f37cb  push    r13
0x1800f37cd  push    r14
0x1800f37cf  push    r15
0x1800f37d1  lea     rbp, [rsp-7B8h]
0x1800f37d9  sub     rsp, 8B8h
0x1800f37e0  mov     rax, cs:__security_cookie
0x1800f37e7  xor     rax, rsp
0x1800f37ea  mov     [rbp+7F0h+var_50], rax
0x1800f37f1  mov     rbx, rcx
0x1800f37f4  mov     [rsp+8F0h+var_890], rcx
0x1800f37f9  xor     esi, esi
0x1800f37fb  mov     [rsp+8F0h+ppszPath], rsi
0x1800f3800  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800f3804  mov     [rsp+8F0h+var_8A0], r14
0x1800f3809  mov     [rsp+8F0h+var_898], r14
0x1800f380e  lea     r9, [rsp+8F0h+ppszPath]; ppszPath
0x1800f3813  xor     r8d, r8d; hToken
0x1800f3816  mov     edi, 4000h
0x1800f381b  mov     edx, edi; dwFlags
0x1800f381d  lea     rcx, FOLDERID_CameraRoll; rfid
0x1800f3824  call    cs:__imp_SHGetKnownFolderPath
0x1800f382a  test    eax, eax
0x1800f382c  js      loc_1800F3B83
0x1800f3832  mov     r12b, sil
0x1800f3835  mov     r15b, sil
0x1800f3838  mov     [rsp+8F0h+ppszCanonicalName], rsi
0x1800f383d  mov     [rsp+8F0h+var_8B8], r14
0x1800f3842  mov     [rsp+8F0h+var_8B0], r14
0x1800f3847  lea     r9, [rsp+8F0h+ppszCanonicalName]; ppszPath
0x1800f384c  xor     r8d, r8d; hToken
0x1800f384f  mov     edx, edi; dwFlags
0x1800f3851  lea     rcx, FOLDERID_SkyDriveCameraRoll; rfid
0x1800f3858  call    cs:__imp_SHGetKnownFolderPath
0x1800f385e  lea     r13, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800f3865  lea     rdi, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800f386c  test    eax, eax
0x1800f386e  js      loc_1800F3B6E
0x1800f3874  mov     [rbp+7F0h+var_870], r13
0x1800f3878  lea     rax, [rbp+7F0h+var_858]
0x1800f387c  mov     [rbp+7F0h+Str], rax
0x1800f3880  mov     [rbp+7F0h+var_860], 401h
0x1800f3887  or      r8d, 0FFFFFFFFh; unsigned int
0x1800f388b  mov     rdx, [rbx+1960h]; wchar_t *
0x1800f3892  lea     rcx, [rbp+7F0h+var_870]; this
0x1800f3896  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x1800f389b  mov     [rbp+7F0h+var_870], rdi
0x1800f389f  mov     r13b, sil
0x1800f38a2  mov     edi, r14d
0x1800f38a5  lea     rdx, aFile_5; "file:"
0x1800f38ac  mov     rcx, [rbp+7F0h+Str]; Str
0x1800f38b0  call    cs:__imp_wcsstr
0x1800f38b6  mov     rbx, rax
0x1800f38b9  mov     rcx, [rbp+7F0h+Str]; Str
0x1800f38bd  test    rax, rax
0x1800f38c0  jz      loc_1800F3D42
0x1800f38c6  sub     rbx, rcx
0x1800f38c9  sar     rbx, 1
0x1800f38cc  cmp     ebx, r14d
0x1800f38cf  jz      short loc_1800F38D4
0x1800f38d1  lea     edi, [rbx+5]
0x1800f38d4  lea     rdx, aPath_1; "path:"
0x1800f38db  call    cs:__imp_wcsstr
0x1800f38e1  xor     ecx, ecx
0x1800f38e3  lea     r9d, [rcx+1]
0x1800f38e7  test    rax, rax
0x1800f38ea  jz      short loc_1800F38FC
0x1800f38ec  sub     rax, [rbp+7F0h+Str]
0x1800f38f0  sar     rax, 1
0x1800f38f3  cmp     eax, r14d
0x1800f38f6  jnz     loc_1800F3D4A
0x1800f38fc  test    r12b, r12b
0x1800f38ff  jnz     loc_1800F3B3E
0x1800f3905  cmp     edi, r14d
0x1800f3908  jz      loc_1800F3B47
0x1800f390e  cmp     edi, [rbp+7F0h+var_85C]
0x1800f3911  jnb     loc_1800F3D6C
0x1800f3917  mov     r14d, edi
0x1800f391a  mov     edx, 27h ; '''; Ch
0x1800f391f  mov     rax, [rbp+7F0h+Str]
0x1800f3923  lea     rcx, [rax+r14*2]; Str
0x1800f3927  call    cs:__imp_wcschr
0x1800f392d  mov     rsi, rax
0x1800f3930  xor     ecx, ecx
0x1800f3932  test    rax, rax
0x1800f3935  jz      loc_1800F3D68
0x1800f393b  sub     rsi, [rbp+7F0h+Str]
0x1800f393f  sar     rsi, 1
0x1800f3942  cmp     esi, 0FFFFFFFFh
0x1800f3945  jz      loc_1800F3D68
0x1800f394b  mov     edx, esi
0x1800f394d  sub     edx, edi
0x1800f394f  dec     edx; wchar_t
0x1800f3951  mov     ebx, edx
0x1800f3953  lea     rcx, [rdx+r14]
0x1800f3957  cmp     rcx, r14
0x1800f395a  jb      loc_1800F3DB2
0x1800f3960  mov     eax, [rbp+7F0h+var_85C]
0x1800f3963  cmp     rcx, rax
0x1800f3966  ja      loc_1800F3D93
0x1800f396c  mov     [rsp+8F0h+var_888], edi
0x1800f3970  mov     [rsp+8F0h+var_884], edx
0x1800f3974  lea     rax, [rbp+7F0h+var_870]
0x1800f3978  mov     [rsp+8F0h+var_880], rax
0x1800f397d  lea     rcx, [rsp+8F0h+var_888]; this
0x1800f3982  call    ?ReplaceAll@CLMSubStr@@QEAAX_W0I@Z; CLMSubStr::ReplaceAll(wchar_t,wchar_t,uint)
0x1800f3987  xor     ecx, ecx
0x1800f3989  test    r12b, r12b
0x1800f398c  jnz     loc_1800F3BB6
0x1800f3992  mov     r8, [rsp+8F0h+ppszPath]; lpString2
0x1800f3997  mov     rdx, [rsp+8F0h+var_8A0]
0x1800f399c  test    r13b, r13b
0x1800f399f  jnz     loc_1800F3CE1
0x1800f39a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f39a9  cmp     rdx, rax
0x1800f39ac  jnz     short loc_1800F39C9
0x1800f39ae  test    r8, r8
0x1800f39b1  jz      loc_1800F3C0A
0x1800f39b7  mov     rdx, rax
0x1800f39ba  inc     rdx
0x1800f39bd  cmp     [r8+rdx*2], cx
0x1800f39c2  jnz     short loc_1800F39BA
0x1800f39c4  mov     [rsp+8F0h+var_8A0], rdx
0x1800f39c9  cmp     rbx, rdx
0x1800f39cc  jnb     loc_1800F3CFD
0x1800f39d2  mov     rdx, rbx; cchCount1
0x1800f39d5  mov     rax, [rbp+7F0h+Str]
0x1800f39d9  lea     rcx, [rax+r14*2]; lpString1
0x1800f39dd  mov     [rsp+8F0h+bIgnoreCase], 1; bIgnoreCase
0x1800f39e5  mov     r9d, edx; cchCount2
0x1800f39e8  call    cs:__imp_CompareStringOrdinal
0x1800f39ee  movzx   r12d, r12b
0x1800f39f2  cmp     eax, 2
0x1800f39f5  mov     r9d, 1
0x1800f39fb  cmovz   r12d, r9d
0x1800f39ff  xor     ecx, ecx
0x1800f3a01  test    r15b, r15b
0x1800f3a04  jnz     short loc_1800F3A70
0x1800f3a06  mov     r8, [rsp+8F0h+ppszCanonicalName]; lpString2
0x1800f3a0b  test    r13b, r13b
0x1800f3a0e  jnz     loc_1800F3D0D
0x1800f3a14  mov     rax, [rsp+8F0h+var_8B8]
0x1800f3a19  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f3a1d  cmp     rax, rdx
0x1800f3a20  jnz     short loc_1800F3A3D
0x1800f3a22  test    r8, r8
0x1800f3a25  jz      loc_1800F3BFD
0x1800f3a2b  mov     rax, rdx
0x1800f3a2e  inc     rax
0x1800f3a31  cmp     [r8+rax*2], cx
0x1800f3a36  jnz     short loc_1800F3A2E
0x1800f3a38  mov     [rsp+8F0h+var_8B8], rax
0x1800f3a3d  cmp     rbx, rax
0x1800f3a40  jnb     loc_1800F3D2E
0x1800f3a46  mov     rax, [rbp+7F0h+Str]
0x1800f3a4a  lea     rcx, [rax+r14*2]; lpString1
0x1800f3a4e  mov     [rsp+8F0h+bIgnoreCase], r9d; unsigned int
0x1800f3a53  mov     r9d, ebx; cchCount2
0x1800f3a56  mov     edx, ebx; cchCount1
0x1800f3a58  call    cs:__imp_CompareStringOrdinal
0x1800f3a5e  movzx   r15d, r15b
0x1800f3a62  cmp     eax, 2
0x1800f3a65  mov     eax, 1
0x1800f3a6a  cmovz   r15d, eax
0x1800f3a6e  xor     ecx, ecx
0x1800f3a70  test    r12b, r12b
0x1800f3a73  jz      short loc_1800F3A85
0x1800f3a75  test    r15b, r15b
0x1800f3a78  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800f3a7f  jnz     loc_1800F38FC
0x1800f3a85  lea     ecx, [rsi+1]
0x1800f3a88  mov     r9d, [rbp+7F0h+var_85C]
0x1800f3a8c  sub     r9d, ecx
0x1800f3a8f  mov     edx, ecx
0x1800f3a91  add     rcx, r9
0x1800f3a94  cmp     rcx, rdx
0x1800f3a97  jb      loc_1800F3DB2
0x1800f3a9d  mov     eax, [rbp+7F0h+var_85C]
0x1800f3aa0  cmp     rcx, rax
0x1800f3aa3  ja      loc_1800F3D74
0x1800f3aa9  mov     rax, [rbp+7F0h+Str]
0x1800f3aad  lea     rdx, [rax+rdx*2]
0x1800f3ab1  mov     rax, [rbp+7F0h+var_870]
0x1800f3ab5  xor     r8d, r8d
0x1800f3ab8  lea     rcx, [rbp+7F0h+var_870]
0x1800f3abc  mov     rax, [rax+20h]
0x1800f3ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3ac5  xor     esi, esi
0x1800f3ac7  mov     r13b, sil
0x1800f3aca  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800f3ace  mov     edi, r14d
0x1800f3ad1  lea     rdx, aFile_5; "file:"
0x1800f3ad8  mov     rcx, [rbp+7F0h+Str]; Str
0x1800f3adc  call    cs:__imp_wcsstr
0x1800f3ae2  mov     rbx, rax
0x1800f3ae5  mov     rcx, [rbp+7F0h+Str]; Str
0x1800f3ae9  test    rax, rax
0x1800f3aec  jz      loc_1800F3D60
0x1800f3af2  sub     rbx, rcx
0x1800f3af5  sar     rbx, 1
0x1800f3af8  cmp     ebx, r14d
0x1800f3afb  jz      short loc_1800F3B00
0x1800f3afd  lea     edi, [rbx+5]
0x1800f3b00  lea     rdx, aPath_1; "path:"
0x1800f3b07  call    cs:__imp_wcsstr
0x1800f3b0d  xor     ecx, ecx
0x1800f3b0f  test    rax, rax
0x1800f3b12  jz      loc_1800F38FC
0x1800f3b18  sub     rax, [rbp+7F0h+Str]
0x1800f3b1c  sar     rax, 1
0x1800f3b1f  cmp     eax, r14d
0x1800f3b22  jz      loc_1800F38FC
0x1800f3b28  cmp     ebx, r14d
0x1800f3b2b  jz      loc_1802BEA07
0x1800f3b31  cmp     eax, ebx
0x1800f3b33  jge     loc_1800F38FC
0x1800f3b39  jmp     loc_1802BEA07
0x1800f3b3e  test    r15b, r15b
0x1800f3b41  jz      loc_1800F3905
0x1800f3b47  lea     rdi, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800f3b4e  mov     [rbp+7F0h+var_870], rdi
0x1800f3b52  lea     rdx, [rbp+7F0h+var_858]; wchar_t *
0x1800f3b56  lea     rcx, [rbp+7F0h+var_870]; this
0x1800f3b5a  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800f3b5f  nop
0x1800f3b60  mov     rbx, [rsp+8F0h+var_890]
0x1800f3b65  xor     esi, esi
0x1800f3b67  lea     r13, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800f3b6e  mov     rcx, [rsp+8F0h+ppszCanonicalName]; pv
0x1800f3b73  test    rcx, rcx
0x1800f3b76  jz      short loc_1800F3B7E
0x1800f3b78  call    cs:__imp_CoTaskMemFree
0x1800f3b7e  test    r12b, r12b
0x1800f3b81  jnz     short loc_1800F3BC1
0x1800f3b83  mov     rcx, [rsp+8F0h+ppszPath]; pv
0x1800f3b88  test    rcx, rcx
0x1800f3b8b  jz      short loc_1800F3B93
0x1800f3b8d  call    cs:__imp_CoTaskMemFree
0x1800f3b93  mov     rcx, [rbp+7F0h+var_50]
0x1800f3b9a  xor     rcx, rsp; StackCookie
0x1800f3b9d  call    __security_check_cookie
0x1800f3ba2  add     rsp, 8B8h
0x1800f3ba9  pop     r15
0x1800f3bab  pop     r14
0x1800f3bad  pop     r13
0x1800f3baf  pop     r12
0x1800f3bb1  pop     rdi
0x1800f3bb2  pop     rsi
0x1800f3bb3  pop     rbx
0x1800f3bb4  pop     rbp
0x1800f3bb5  retn
0x1800f3bb6  mov     r9d, 1
0x1800f3bbc  jmp     loc_1800F3A01
0x1800f3bc1  test    r15b, r15b
0x1800f3bc4  jz      short loc_1800F3B83
0x1800f3bc6  mov     [rsp+8F0h+ppszCanonicalName], rsi
0x1800f3bcb  mov     [rsp+8F0h+var_8B8], r14
0x1800f3bd0  mov     [rsp+8F0h+var_8B0], r14
0x1800f3bd5  lea     rdx, [rsp+8F0h+ppszCanonicalName]; ppszCanonicalName
0x1800f3bda  lea     rcx, PKEY_CameraRollDeduplicationId; propkey
0x1800f3be1  call    cs:__imp_PSGetNameFromPropertyKey
0x1800f3be7  test    eax, eax
0x1800f3be9  jns     short loc_1800F3C17
0x1800f3beb  mov     rcx, [rsp+8F0h+ppszCanonicalName]; pv
0x1800f3bf0  test    rcx, rcx
0x1800f3bf3  jz      short loc_1800F3B83
0x1800f3bf5  call    cs:__imp_CoTaskMemFree
0x1800f3bfb  jmp     short loc_1800F3B83
0x1800f3bfd  mov     rax, rcx
0x1800f3c00  mov     [rsp+8F0h+var_8B8], rcx
0x1800f3c05  jmp     loc_1800F3A3D
0x1800f3c0a  mov     rdx, rcx
0x1800f3c0d  mov     [rsp+8F0h+var_8A0], rcx
0x1800f3c12  jmp     loc_1800F39C9
0x1800f3c17  mov     [rbp+7F0h+var_870], r13
0x1800f3c1b  lea     rax, [rbp+7F0h+var_858]
0x1800f3c1f  mov     [rbp+7F0h+Str], rax
0x1800f3c23  mov     [rbp+7F0h+var_860], 401h
0x1800f3c2a  mov     r9d, 3; int
0x1800f3c30  lea     r8, [rbp+7F0h+var_858]; wchar_t *
0x1800f3c34  lea     edx, [r9-1]; cbMultiByte
0x1800f3c38  lea     rcx, MultiByteStr; ", "
0x1800f3c3f  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x1800f3c44  mov     [rbp+7F0h+var_85C], eax
0x1800f3c47  mov     [rbp+7F0h+var_870], rdi
0x1800f3c4b  mov     rdx, [rbp+7F0h+Str]
0x1800f3c4f  lea     rcx, [rbx+31B8h]
0x1800f3c56  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800f3c5b  nop
0x1800f3c5c  mov     [rbp+7F0h+var_870], rdi
0x1800f3c60  lea     rdx, [rbp+7F0h+var_858]; wchar_t *
0x1800f3c64  lea     rcx, [rbp+7F0h+var_870]; this
0x1800f3c68  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800f3c6d  nop
0x1800f3c6e  or      r8d, 0FFFFFFFFh; unsigned int
0x1800f3c72  mov     rdx, [rsp+8F0h+ppszCanonicalName]; wchar_t *
  ... truncated ...
```

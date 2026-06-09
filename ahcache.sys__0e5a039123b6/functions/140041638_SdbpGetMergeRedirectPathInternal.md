# SdbpGetMergeRedirectPathInternal

- ea: `0x140041638`
- end: `0x140041d66`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1838`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140041d6c`
- `0x14004224c`

## callees

- `0x140001848`
- `0x140001dc4`
- `0x140004469`
- `0x14000448d`
- `0x1400044f9`
- `0x140004553`
- `0x1400079f0`
- `0x14003e364`
- `0x140040564`
- `0x140041638`
- `0x140041f48`
- `0x140041f78`
- `0x1400423d0`
- `0x14004506c`
- `0x140045d44`
- `0x140046440`
- `0x140046660`

## string_xrefs

- `0x140041862`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1400417ce`: `SdbpGetMergeRedirectPathInternal`
- `0x140041896`: `SdbpGetMergeRedirectPathInternal`
- `0x140041aa2`: `SdbpGetMergeRedirectPathInternal`
- `0x1400417a3`: `StagedDelete_`
- `0x140041c43`: `Failed to get manifested stub [%x]`
- `0x140041885`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x1400419e8`: `RtlStringCchCopyW failed to copy first string [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, const wchar_t *a4)
{
  void *v6; // r14
  wchar_t *v7; // rdi
  wchar_t *v9; // r12
  signed int String; // ebx
  const wchar_t *FileNamePart; // rax
  HANDLE v12; // rcx
  const wchar_t *v13; // r13
  const wchar_t *i; // rdi
  const wchar_t *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  void *v18; // rsi
  const WCHAR *v19; // r14
  int Key; // eax
  const char *v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  const WCHAR *v24; // rax
  size_t v25; // r15
  const char *v26; // r9
  __int64 v27; // r8
  size_t v28; // rsi
  wchar_t *Pool2_0; // rax
  wchar_t *v30; // rdi
  NTSTATUS v31; // eax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // rcx
  HANDLE v35; // r14
  unsigned int v36; // esi
  int UInt32; // eax
  const wchar_t *v38; // rsi
  const wchar_t *v39; // rax
  __int64 v40; // rcx
  unsigned __int64 v41; // r8
  int v42; // eax
  int FileTimestamp; // eax
  __int64 v44; // r8
  const char *v45; // r9
  unsigned __int64 v46; // rax
  int v47; // eax
  __int64 v48; // [rsp+20h] [rbp-89h]
  __int64 v49; // [rsp+20h] [rbp-89h]
  void *v50; // [rsp+30h] [rbp-79h] BYREF
  void *v51; // [rsp+38h] [rbp-71h]
  unsigned int v52; // [rsp+40h] [rbp-69h] BYREF
  int v53; // [rsp+44h] [rbp-65h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v55; // [rsp+50h] [rbp-59h] BYREF
  wchar_t *Str1; // [rsp+58h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-49h] BYREF
  void *v58; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v59; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int64 v60; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v61; // [rsp+80h] [rbp-29h] BYREF
  const wchar_t *v62; // [rsp+88h] [rbp-21h]
  unsigned __int64 v63; // [rsp+90h] [rbp-19h]
  _QWORD *v64; // [rsp+98h] [rbp-11h]
  _DWORD *v65; // [rsp+A0h] [rbp-9h]
  wchar_t Str2[12]; // [rsp+A8h] [rbp-1h] BYREF

  v65 = a2;
  v62 = a4;
  v53 = a3;
  v64 = a1;
  v6 = 0;
  v52 = 0;
  v7 = 0;
  Handle = 0;
  Str1 = 0;
  v55 = 0;
  v51 = 0;
  v58 = 0;
  v60 = 0;
  v61 = 0;
  v59 = 0;
  v50 = 0;
  pszSrc = 0;
  wcscpy(Str2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  v9 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  String = -1073741772;
  FileNamePart = AslPathGetFileNamePart(a4);
  v13 = FileNamePart;
  if ( FileNamePart != a4 )
  {
    for ( i = FileNamePart - 2; ; --i )
    {
      if ( i < a4 )
        goto LABEL_21;
      if ( (*i == 92 || *i == 47) && !wcsnicmp_0(i, Str2, 0xAu) )
        break;
    }
    if ( v13 )
    {
      v15 = v13;
      v16 = 0x7FFFFFFF;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v16;
      }
      while ( v16 );
      String = v16 == 0 ? 0xC000000D : 0;
      v63 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
      if ( v16 )
      {
        if ( v53 )
        {
          v17 = SdbpSafeAllocAndConcatW(&pszSrc, L"StagedDelete_", 13, v13, (0x7FFFFFFF - v16) & -(__int64)(v16 != 0));
          String = v17;
          if ( v17 < 0 )
          {
            LODWORD(v48) = v17;
            AslLogCallPrintf(
              1,
              "SdbpGetMergeRedirectPathInternal",
              1878,
              "Failed to alloc and cat file to prefix [%x]",
              v48);
LABEL_21:
            v7 = (wchar_t *)pszSrc;
            goto LABEL_22;
          }
          v19 = pszSrc;
        }
        else
        {
          v19 = v13;
        }
        Key = AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                0x80000100,
                1);
        String = Key;
        if ( Key < 0 )
        {
          if ( Key != -1073741772 )
          {
            v21 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
            v22 = 1895;
            goto LABEL_39;
          }
LABEL_41:
          v6 = v51;
LABEL_42:
          v18 = v50;
LABEL_43:
          v12 = Handle;
          if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            ZwClose_0(Handle);
          v7 = (wchar_t *)pszSrc;
          goto LABEL_23;
        }
        String = AslRegistryGetString(&Str1, Handle, v19);
        if ( String < 0 )
          goto LABEL_41;
        String = 0;
        if ( !wcsicmp_0(Str1, v13) )
        {
          String = -1073741772;
          goto LABEL_41;
        }
        if ( v53 && !wcsicmp_0(Str1, L"__NotRedirected__") && a2 )
        {
          *a2 = 1;
          goto LABEL_41;
        }
        if ( !v19 )
        {
          String = -1073741582;
LABEL_118:
          LODWORD(v48) = String;
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1929,
            "Failed to alloc and cat file to prefix [%x]",
            v48);
          goto LABEL_41;
        }
        v23 = 0x7FFFFFFF;
        v24 = v19;
        do
        {
          if ( !*v24 )
            break;
          ++v24;
          --v23;
        }
        while ( v23 );
        String = v23 == 0 ? 0xC000000D : 0;
        v25 = (0x7FFFFFFF - v23) & -(__int64)(v23 != 0);
        if ( !v23 )
        {
          v26 = "RtlStringCchLengthW failed [%x]";
          v27 = 1647;
LABEL_117:
          LODWORD(v48) = String;
          AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v27, v26, v48);
          goto LABEL_118;
        }
        if ( v25 >= 0xFFFFFFFFFFFFFFF7uLL )
        {
          v27 = 1657;
        }
        else
        {
          v28 = v25 + 10;
          if ( v25 + 10 >= v25 + 9 )
          {
            Pool2_0 = (wchar_t *)ExAllocatePool2_0(256, 2 * v28, 1953517633);
            v30 = Pool2_0;
            if ( !Pool2_0 )
            {
              String = -1073741801;
              goto LABEL_118;
            }
            v31 = RtlStringCchCopyNW(Pool2_0, v28, L"MergeVer_", 9u);
            String = v31;
            if ( v31 < 0 )
            {
              v32 = 1679;
              v33 = "RtlStringCchCopyW failed to copy first string [%x]";
LABEL_68:
              LODWORD(v48) = v31;
              AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v32, v33, v48);
              AslFree(v34, v30);
              goto LABEL_118;
            }
            v31 = RtlStringCchCatNW(v30, v28, v19, v25);
            String = v31;
            if ( v31 < 0 )
            {
              v32 = 1688;
              v33 = "RtlStringCchCatW failed to cat second string [%x]";
              goto LABEL_68;
            }
            v35 = Handle;
            v9 = v30;
            Key = AslRegistryGetUInt32(&v55, Handle, v30);
            String = Key;
            if ( Key == -1073741772 )
            {
              v36 = 0;
            }
            else
            {
              if ( Key < 0 )
              {
                v21 = "Failed to query reg value. [%x]";
                v22 = 1938;
                goto LABEL_39;
              }
              v36 = v55;
            }
            Key = AslRegistryGetUInt32(&v52, v35, L"MergeVer");
            String = Key;
            if ( Key < 0 )
            {
              v21 = "Failed to query reg value. [%x]";
              v22 = 1944;
LABEL_39:
              LODWORD(v48) = Key;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v22, v21, v48);
              goto LABEL_41;
            }
            if ( v52 < v36 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1953,
                "Merge target is too high of a version, this code might not handle it correctly.");
            UInt32 = AslRegistryGetUInt32(&v52, v35, L"MinMergeVer");
            String = UInt32;
            if ( UInt32 < 0 )
            {
              LODWORD(v48) = UInt32;
              AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1959, "Failed to query reg value. [%x]", v48);
              goto LABEL_41;
            }
            if ( v36 < v52 )
              AslLogCallPrintf(
                1,
                "SdbpGetMergeRedirectPathInternal",
                1968,
                "Merge target is too low of a version, it might not be possible to handle correctly.");
            v38 = v62;
            if ( v62 )
            {
              v39 = v62;
              v40 = 0x7FFFFFFF;
              do
              {
                if ( !*v39 )
                  break;
                ++v39;
                --v40;
              }
              while ( v40 );
              String = v40 == 0 ? 0xC000000D : 0;
              v41 = (0x7FFFFFFF - v40) & -(__int64)(v40 != 0);
              if ( v40 )
              {
                if ( v41 < v63 )
                {
                  String = -1073741675;
                  LODWORD(v48) = -1073741675;
                  AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1982, "RtlSizeTSub failed [%x]", v48);
                  goto LABEL_41;
                }
                v42 = SdbpSafeAllocAndConcatW(&v58, v62, v41 - v63, Str1, 0);
                String = v42;
                if ( v42 < 0 )
                {
                  AslLogCallPrintf(
                    1,
                    "SdbpGetMergeRedirectPathInternal",
                    1992,
                    "Failed to alloc and cat file to prefix [%x]",
                    v42);
                  v6 = v58;
                  goto LABEL_42;
                }
                v6 = v58;
                FileTimestamp = SdbpGetFileTimestamp(&v60, v58, 1);
                String = FileTimestamp;
                if ( FileTimestamp >= 0 )
                {
                  FileTimestamp = SdbpGetFileTimestamp(&v61, v38, 0);
                  String = FileTimestamp;
                  if ( FileTimestamp >= 0 )
                  {
                    FileTimestamp = SdbpGetManifestedMergeStubAlloc(&v50, v13);
                    String = FileTimestamp;
                    if ( FileTimestamp == -1073741772 )
                    {
                      v18 = v50;
                      v46 = 0;
                    }
                    else
                    {
                      if ( FileTimestamp < 0 )
                      {
                        v45 = "Failed to get manifested stub [%x]";
                        v44 = 2028;
                        goto LABEL_94;
                      }
                      v18 = v50;
                      v47 = SdbpGetFileTimestamp(&v59, v50, 0);
                      String = v47;
                      if ( v47 < 0 )
                      {
                        AslLogCallPrintf(
                          1,
                          "SdbpGetMergeRedirectPathInternal",
                          2038,
                          "Failed to check timestamp [%x]",
                          v47);
                        goto LABEL_43;
                      }
                      v46 = v59;
                    }
                    if ( v60 < v61 || v60 < v46 )
                    {
                      String = -1073741772;
                    }
                    else
                    {
                      *v64 = v6;
                      if ( v65 && v53 )
                        *v65 = 1;
                      v6 = 0;
                      String = 0;
                    }
                    goto LABEL_43;
                  }
                  v44 = 2014;
                }
                else
                {
                  if ( FileTimestamp == -1073741772 )
                    goto LABEL_42;
                  v44 = 2003;
                }
                v45 = "Failed to check timestamp [%x]";
LABEL_94:
                LODWORD(v49) = FileTimestamp;
                AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v44, v45, v49);
                goto LABEL_42;
              }
            }
            else
            {
              String = -1073741811;
            }
            LODWORD(v48) = String;
            AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1975, "RtlStringCchLengthW failed [%x]", v48);
            goto LABEL_41;
          }
          v27 = 1664;
        }
        v26 = "RtlSizeTAdd failed [%x]";
        String = -1073741675;
        goto LABEL_117;
      }
    }
    else
    {
      String = -1073741811;
    }
    AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", String);
    goto LABEL_21;
  }
LABEL_22:
  v18 = v50;
LABEL_23:
  if ( Str1 )
    AslFree((__int64)v12, Str1);
  if ( v6 )
    AslFree((__int64)v12, v6);
  if ( v18 )
    AslFree((__int64)v12, v18);
  if ( v9 )
    AslFree((__int64)v12, v9);
  if ( v7 )
    AslFree((__int64)v12, v7);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x140041638  mov     [rsp-8+arg_10], rbx
0x14004163d  push    rbp
0x14004163e  push    rsi
0x14004163f  push    rdi
0x140041640  push    r12
0x140041642  push    r13
0x140041644  push    r14
0x140041646  push    r15
0x140041648  lea     rbp, [rsp-27h]
0x14004164d  sub     rsp, 0D0h
0x140041654  mov     rax, cs:__security_cookie
0x14004165b  xor     rax, rsp
0x14004165e  mov     [rbp+57h+var_40], rax
0x140041662  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x140041669  mov     r15, rdx
0x14004166c  mov     [rbp+57h+var_60], rdx
0x140041670  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x140041678  xor     edx, edx
0x14004167a  mov     [rbp+57h+var_78], r9
0x14004167e  mov     eax, r8d
0x140041681  mov     [rbp+57h+var_BC], eax
0x140041684  mov     rsi, r9
0x140041687  mov     [rbp+57h+var_68], rcx
0x14004168b  mov     r14d, edx
0x14004168e  mov     [rbp+57h+var_C0], edx
0x140041691  mov     edi, edx
0x140041693  mov     [rbp+57h+Handle], rdx
0x140041697  mov     [rbp+57h+Str1], rdx
0x14004169b  mov     [rbp+57h+var_B0], edx
0x14004169e  mov     [rbp+57h+var_C8], rdx
0x1400416a2  mov     [rbp+57h+var_98], rdx
0x1400416a6  mov     [rbp+57h+var_88], rdx
0x1400416aa  mov     [rbp+57h+var_80], rdx
0x1400416ae  mov     [rbp+57h+var_90], rdx
0x1400416b2  mov     [rbp+57h+var_D0], rdx
0x1400416b6  mov     [rbp+57h+pszSrc], rdx
0x1400416ba  movups  xmmword ptr [rbp+57h+Str2], xmm0
0x1400416be  movsd   qword ptr [rbp+57h+Str2+0Eh], xmm1
0x1400416c3  test    rcx, rcx
0x1400416c6  jnz     short loc_1400416D2
0x1400416c8  mov     eax, 0C00000EFh
0x1400416cd  jmp     loc_14004182B
0x1400416d2  mov     [rcx], rdx
0x1400416d5  mov     r12, rdx
0x1400416d8  test    r15, r15
0x1400416db  jz      short loc_1400416E4
0x1400416dd  test    eax, eax
0x1400416df  jz      short loc_1400416E4
0x1400416e1  mov     [r15], edx
0x1400416e4  mov     rcx, rsi
0x1400416e7  mov     ebx, 0C0000034h
0x1400416ec  call    AslPathGetFileNamePart
0x1400416f1  mov     r13, rax
0x1400416f4  cmp     rax, rsi
0x1400416f7  jz      loc_1400417E3
0x1400416fd  lea     rdi, [rax-4]
0x140041701  cmp     rdi, rsi
0x140041704  jb      loc_1400417DF
0x14004170a  movzx   eax, word ptr [rdi]
0x14004170d  cmp     ax, 5Ch ; '\'
0x140041711  jz      short loc_140041719
0x140041713  cmp     ax, 2Fh ; '/'
0x140041717  jnz     short loc_140041732
0x140041719  mov     r8d, 0Ah; MaxCount
0x14004171f  lea     rdx, [rbp+57h+Str2]; Str2
0x140041723  mov     rcx, rdi; Str1
0x140041726  call    _wcsnicmp_0
0x14004172b  xor     r8d, r8d
0x14004172e  test    eax, eax
0x140041730  jz      short loc_140041738
0x140041732  sub     rdi, 2
0x140041736  jmp     short loc_140041701
0x140041738  test    r13, r13
0x14004173b  jz      loc_140041D4B
0x140041741  mov     esi, 7FFFFFFFh
0x140041746  mov     rax, r13
0x140041749  mov     edx, esi
0x14004174b  cmp     [rax], r8w
0x14004174f  jz      short loc_14004175B
0x140041751  add     rax, 2
0x140041755  sub     rdx, 1
0x140041759  jnz     short loc_14004174B
0x14004175b  mov     rax, rdx
0x14004175e  mov     edi, 0C000000Dh
0x140041763  neg     rax
0x140041766  mov     rcx, rsi
0x140041769  mov     rax, rdx
0x14004176c  sbb     ebx, ebx
0x14004176e  sub     rcx, rdx
0x140041771  not     ebx
0x140041773  and     ebx, edi
0x140041775  neg     rax
0x140041778  sbb     rax, rax
0x14004177b  and     rax, rcx
0x14004177e  mov     [rbp+57h+var_70], rax
0x140041782  test    rdx, rdx
0x140041785  jz      loc_140041D50
0x14004178b  cmp     [rbp+57h+var_BC], r8d
0x14004178f  jz      loc_140041859
0x140041795  mov     r9, r13
0x140041798  mov     [rsp+100h+var_E0], rax
0x14004179d  mov     r8d, 0Dh
0x1400417a3  lea     rdx, aStageddelete; "StagedDelete_"
0x1400417aa  lea     rcx, [rbp+57h+pszSrc]
0x1400417ae  call    SdbpSafeAllocAndConcatW
0x1400417b3  mov     ebx, eax
0x1400417b5  test    eax, eax
0x1400417b7  jns     loc_140041853
0x1400417bd  mov     dword ptr [rsp+100h+var_E0], eax
0x1400417c1  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x1400417c8  mov     r8d, 756h
0x1400417ce  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1400417d5  mov     ecx, 1
0x1400417da  call    AslLogCallPrintf
0x1400417df  mov     rdi, [rbp+57h+pszSrc]
0x1400417e3  mov     rsi, [rbp+57h+var_D0]
0x1400417e7  mov     rdx, [rbp+57h+Str1]
0x1400417eb  test    rdx, rdx
0x1400417ee  jz      short loc_1400417F5
0x1400417f0  call    AslFree
0x1400417f5  test    r14, r14
0x1400417f8  jz      short loc_140041802
0x1400417fa  mov     rdx, r14
0x1400417fd  call    AslFree
0x140041802  test    rsi, rsi
0x140041805  jz      short loc_14004180F
0x140041807  mov     rdx, rsi
0x14004180a  call    AslFree
0x14004180f  test    r12, r12
0x140041812  jz      short loc_14004181C
0x140041814  mov     rdx, r12
0x140041817  call    AslFree
0x14004181c  test    rdi, rdi
0x14004181f  jz      short loc_140041829
0x140041821  mov     rdx, rdi
0x140041824  call    AslFree
0x140041829  mov     eax, ebx
0x14004182b  mov     rcx, [rbp+57h+var_40]
0x14004182f  xor     rcx, rsp; StackCookie
0x140041832  call    __security_check_cookie
0x140041837  mov     rbx, [rsp+100h+arg_10]
0x14004183f  add     rsp, 0D0h
0x140041846  pop     r15
0x140041848  pop     r14
0x14004184a  pop     r13
0x14004184c  pop     r12
0x14004184e  pop     rdi
0x14004184f  pop     rsi
0x140041850  pop     rbp
0x140041851  retn
0x140041853  mov     r14, [rbp+57h+pszSrc]
0x140041857  jmp     short loc_14004185C
0x140041859  mov     r14, r13
0x14004185c  mov     r9d, 1
0x140041862  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x140041869  mov     r8d, 80000100h
0x14004186f  lea     rcx, [rbp+57h+Handle]
0x140041873  call    AslRegistryGetKey
0x140041878  mov     ebx, eax
0x14004187a  test    eax, eax
0x14004187c  jns     short loc_1400418CB
0x14004187e  cmp     eax, 0C0000034h
0x140041883  jz      short loc_1400418A7
0x140041885  lea     r9, aAslregistryget_4; "AslRegistryGetKey failed to open SdbUpd"...
0x14004188c  mov     r8d, 767h
0x140041892  mov     dword ptr [rsp+100h+var_E0], eax
0x140041896  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x14004189d  mov     ecx, 1
0x1400418a2  call    AslLogCallPrintf
0x1400418a7  mov     r14, [rbp+57h+var_C8]
0x1400418ab  mov     rsi, [rbp+57h+var_D0]
0x1400418af  mov     rcx, [rbp+57h+Handle]; Handle
0x1400418b3  lea     rax, [rcx-1]
0x1400418b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400418bb  ja      short loc_1400418C2
0x1400418bd  call    ZwClose_0
0x1400418c2  mov     rdi, [rbp+57h+pszSrc]
0x1400418c6  jmp     loc_1400417E7
0x1400418cb  mov     rdx, [rbp+57h+Handle]
0x1400418cf  lea     rcx, [rbp+57h+Str1]
0x1400418d3  mov     r8, r14
0x1400418d6  call    AslRegistryGetString
0x1400418db  mov     ebx, eax
0x1400418dd  test    eax, eax
0x1400418df  js      short loc_1400418A7
0x1400418e1  mov     rcx, [rbp+57h+Str1]; Str1
0x1400418e5  mov     rdx, r13; Str2
0x1400418e8  call    _wcsicmp_0
0x1400418ed  xor     ebx, ebx
0x1400418ef  test    eax, eax
0x1400418f1  jnz     short loc_1400418FA
0x1400418f3  mov     ebx, 0C0000034h
0x1400418f8  jmp     short loc_1400418A7
0x1400418fa  cmp     [rbp+57h+var_BC], ebx
0x1400418fd  jz      short loc_140041921
0x1400418ff  mov     rcx, [rbp+57h+Str1]; Str1
0x140041903  lea     rdx, aNotredirected; "__NotRedirected__"
0x14004190a  call    _wcsicmp_0
0x14004190f  test    eax, eax
0x140041911  jnz     short loc_140041921
0x140041913  test    r15, r15
0x140041916  jz      short loc_140041921
0x140041918  mov     dword ptr [r15], 1
0x14004191f  jmp     short loc_1400418A7
0x140041921  xor     r15d, r15d
0x140041924  test    r14, r14
0x140041927  jnz     short loc_140041933
0x140041929  mov     ebx, 0C00000F2h
0x14004192e  jmp     loc_140041D35
0x140041933  mov     rdx, rsi
0x140041936  mov     rax, r14
0x140041939  mov     r10d, 1
0x14004193f  cmp     [rax], r15w
0x140041943  jz      short loc_14004194E
0x140041945  add     rax, 2
0x140041949  sub     rdx, r10
0x14004194c  jnz     short loc_14004193F
0x14004194e  mov     rax, rdx
0x140041951  mov     rcx, rsi
0x140041954  neg     rax
0x140041957  mov     rax, rdx
0x14004195a  sbb     ebx, ebx
0x14004195c  sub     rcx, rdx
0x14004195f  not     ebx
0x140041961  and     ebx, edi
0x140041963  neg     rax
0x140041966  sbb     r15, r15
0x140041969  and     r15, rcx
0x14004196c  test    rdx, rdx
0x14004196f  jnz     short loc_140041983
0x140041971  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x140041978  mov     r8d, 66Fh
0x14004197e  jmp     loc_140041D22
0x140041983  lea     rax, [r15+9]
0x140041987  cmp     rax, 9
0x14004198b  jb      loc_140041D10
0x140041991  lea     rsi, [rax+1]
0x140041995  cmp     rsi, rax
0x140041998  jb      loc_140041D08
0x14004199e  lea     rdx, [rsi+rsi]
0x1400419a2  mov     ecx, 100h
0x1400419a7  mov     r8d, 74705041h
0x1400419ad  call    ExAllocatePool2_0
0x1400419b2  mov     rdi, rax
0x1400419b5  test    rax, rax
0x1400419b8  jnz     short loc_1400419C4
0x1400419ba  mov     ebx, 0C0000017h
0x1400419bf  jmp     loc_140041D35
0x1400419c4  mov     r9d, 9; cchToCopy
0x1400419ca  lea     r8, aMergever_0; "MergeVer_"
0x1400419d1  mov     rdx, rsi; cchDest
0x1400419d4  mov     rcx, rdi; pszDest
0x1400419d7  call    RtlStringCchCopyNW
0x1400419dc  mov     ebx, eax
0x1400419de  test    eax, eax
0x1400419e0  jns     short loc_1400419F1
0x1400419e2  mov     r8d, 68Fh
0x1400419e8  lea     r9, aRtlstringcchco_3; "RtlStringCchCopyW failed to copy first "...
0x1400419ef  jmp     short loc_140041A18
0x1400419f1  mov     r9, r15; cchToAppend
0x1400419f4  mov     r8, r14; pszSrc
0x1400419f7  mov     rdx, rsi; cchDest
0x1400419fa  mov     rcx, rdi; pszDest
0x1400419fd  call    RtlStringCchCatNW
0x140041a02  xor     r15d, r15d
0x140041a05  mov     ebx, eax
0x140041a07  test    eax, eax
0x140041a09  jns     short loc_140041A3A
0x140041a0b  mov     r8d, 698h
0x140041a11  lea     r9, aRtlstringcchca_0; "RtlStringCchCatW failed to cat second s"...
0x140041a18  lea     rdx, aSdbpsafealloca; "SdbpSafeAllocAndConcatW"
0x140041a1f  mov     dword ptr [rsp+100h+var_E0], eax
0x140041a23  mov     ecx, 1
0x140041a28  call    AslLogCallPrintf
0x140041a2d  mov     rdx, rdi
0x140041a30  call    AslFree
0x140041a35  jmp     loc_140041D35
0x140041a3a  mov     r14, [rbp+57h+Handle]
0x140041a3e  lea     rcx, [rbp+57h+var_B0]
0x140041a42  mov     rdx, r14
0x140041a45  mov     r8, rdi
0x140041a48  mov     r12, rdi
0x140041a4b  call    AslRegistryGetUInt32
0x140041a50  mov     ebx, eax
0x140041a52  cmp     eax, 0C0000034h
0x140041a57  jnz     short loc_140041A5E
0x140041a59  mov     esi, r15d
0x140041a5c  jmp     short loc_140041A77
0x140041a5e  test    eax, eax
0x140041a60  jns     short loc_140041A74
0x140041a62  lea     r9, aFailedToQueryR_0; "Failed to query reg value. [%x]"
0x140041a69  mov     r8d, 792h
0x140041a6f  jmp     loc_140041892
0x140041a74  mov     esi, [rbp+57h+var_B0]
0x140041a77  lea     r8, aMergever; "MergeVer"
0x140041a7e  mov     rdx, r14
0x140041a81  lea     rcx, [rbp+57h+var_C0]
0x140041a85  call    AslRegistryGetUInt32
0x140041a8a  mov     ebx, eax
0x140041a8c  test    eax, eax
  ... truncated ...
```

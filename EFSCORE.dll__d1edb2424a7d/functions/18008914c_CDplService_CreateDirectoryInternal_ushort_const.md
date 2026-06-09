# CDplService::CreateDirectoryInternal(ushort const *)

- ea: `0x18008914c`
- end: `0x1800895e0`
- name: `?CreateDirectoryInternal@CDplService@@SAJPEBG@Z`
- size: `1172`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18008914c`
- `0x1800b62c0`
- `0x1800b6470`
- `0x1800b8820`
- `0x1800b9ea4`

## callees

- `0x18000b884`
- `0x18000efb8`
- `0x1800124a8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800805c4`
- `0x18008914c`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008943e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008949d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008956c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008943e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008949d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008956c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089476`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089562`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089476`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089562`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180089421`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180089421`

## pseudocode

```c
__int64 __fastcall CDplService::CreateDirectoryInternal(const unsigned __int16 *a1)
{
  WCHAR *v2; // r14
  unsigned int DirectoryInternal; // ebx
  int v4; // r8d
  int v5; // ecx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r15
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  signed int v13; // eax
  int v14; // ecx
  WCHAR v15; // bp
  signed int v16; // eax
  char v18; // [rsp+20h] [rbp-58h]
  LPCWSTR lpFileName; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int64 v20; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp+18h] BYREF

  lpFileName = 0;
  v2 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a1 )
  {
    v18 = -40;
LABEL_3:
    DirectoryInternal = -2147024809;
    v4 = -2147024809;
LABEL_47:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v4, 37, v18);
    goto LABEL_48;
  }
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 218);
  DirectoryInternal = StringCchLengthW(a1, 0x7FFFFFFFu, &v20);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              DirectoryInternal,
              37,
              218) >= 0 )
  {
    v6 = v20;
    if ( a1[v20] )
    {
      DirectoryInternal = -2147418113;
      v18 = -37;
      v4 = -2147418113;
      goto LABEL_47;
    }
    if ( !v20 )
    {
      v18 = -33;
      goto LABEL_3;
    }
    fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 226);
    v7 = v6 + 1;
    if ( v6 + 1 < v6 )
    {
      v7 = -1;
      DirectoryInternal = -2147024362;
    }
    else
    {
      DirectoryInternal = 0;
    }
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                DirectoryInternal,
                37,
                226) >= 0 )
    {
      fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 227);
      DirectoryInternal = ULongLongMult(v7, 2u, &v21);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  DirectoryInternal,
                  37,
                  227) >= 0 )
      {
        fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 232);
        DirectoryInternal = DplibpMemAllocEx(v21, 0, 0, &lpFileName);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    DirectoryInternal,
                    37,
                    232) < 0 )
        {
          v2 = (WCHAR *)lpFileName;
          goto LABEL_48;
        }
        fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 236);
        v2 = (WCHAR *)lpFileName;
        DirectoryInternal = StringCchCopyW((unsigned __int16 *)lpFileName, v7, a1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    DirectoryInternal,
                    37,
                    236) >= 0 )
        {
          if ( !v6 )
            goto LABEL_20;
          do
          {
            if ( v2[v6 - 1] != 92 && v2[v6 - 1] != 47 )
              break;
            v2[--v6] = 0;
          }
          while ( v6 );
          if ( !v6 )
          {
LABEL_20:
            v18 = -9;
LABEL_21:
            DirectoryInternal = -2147024809;
            v4 = -2147024809;
            goto LABEL_47;
          }
          FileAttributesW = GetFileAttributesW(v2);
          if ( FileAttributesW == -1 )
          {
            LastError = GetLastError();
            DirectoryInternal = LastError;
            if ( LastError > 0 )
              DirectoryInternal = (unsigned __int16)LastError | 0x80070000;
            if ( DirectoryInternal + 2147024894 <= 1 )
            {
              if ( CreateDirectoryW(v2, 0) )
              {
                DirectoryInternal = 0;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 37, 36);
                goto LABEL_48;
              }
              v13 = GetLastError();
              DirectoryInternal = v13;
              if ( v13 > 0 )
                DirectoryInternal = (unsigned __int16)v13 | 0x80070000;
              if ( DirectoryInternal + 2147024894 <= 1 )
              {
                while ( v2[v6 - 1] != 92 && v2[v6 - 1] != 47 )
                {
                  if ( !--v6 )
                  {
                    v18 = 71;
                    goto LABEL_21;
                  }
                }
                v15 = v2[v6 - 1];
                v2[v6 - 1] = 0;
                fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 81);
                DirectoryInternal = CDplService::CreateDirectoryInternal(v2);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            DirectoryInternal,
                            37,
                            81) < 0 )
                  goto LABEL_48;
                v2[v6 - 1] = v15;
                if ( CreateDirectoryW(v2, 0) )
                  goto LABEL_48;
                v16 = GetLastError();
                DirectoryInternal = v16;
                if ( v16 > 0 )
                  DirectoryInternal = (unsigned __int16)v16 | 0x80070000;
                v18 = 92;
              }
              else
              {
                v18 = 53;
              }
            }
            else
            {
              v18 = 23;
            }
            v4 = DirectoryInternal;
            goto LABEL_47;
          }
          if ( (FileAttributesW & 0x10) == 0 )
          {
            v18 = 4;
            goto LABEL_21;
          }
        }
      }
    }
  }
LABEL_48:
  CDplService::MemFreeIf<unsigned short>(v2);
  return DirectoryInternal;
}

```

## disassembly

```asm
0x18008914c  mov     rax, rsp
0x18008914f  mov     [rax+20h], rbx
0x180089153  push    rbp
0x180089154  push    rsi
0x180089155  push    rdi
0x180089156  push    r12
0x180089158  push    r13
0x18008915a  push    r14
0x18008915c  push    r15
0x18008915e  sub     rsp, 40h
0x180089162  xor     r13d, r13d
0x180089165  mov     rbp, rcx
0x180089168  mov     [rax+8], r13
0x18008916c  mov     r14d, r13d
0x18008916f  mov     [rax+10h], r13
0x180089173  mov     [rax+18h], r13
0x180089177  test    rcx, rcx
0x18008917a  jnz     short loc_180089197
0x18008917c  mov     dword ptr [rax-58h], 29D8h
0x180089183  lea     r9d, [rcx+25h]
0x180089187  mov     ebx, 80070057h
0x18008918c  mov     r8d, 80070057h
0x180089192  jmp     loc_1800895AB
0x180089197  mov     edi, 25h ; '%'
0x18008919c  lea     r15, sourceString
0x1800891a3  mov     esi, 29DAh
0x1800891a8  lea     rdx, EFS_TRACE_START_EVENT
0x1800891af  mov     r9d, edi
0x1800891b2  mov     dword ptr [rsp+78h+var_58], esi
0x1800891b6  mov     r8, r15
0x1800891b9  call    fnEfsLogTrace1Strings
0x1800891be  lea     r8, [rsp+78h+arg_8]; unsigned __int64 *
0x1800891c6  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800891cb  mov     rcx, rbp; unsigned __int16 *
0x1800891ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800891d3  mov     rcx, cs:g_hPublisher
0x1800891da  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800891e1  mov     [rsp+78h+var_48], esi
0x1800891e5  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800891ec  mov     [rsp+78h+var_50], edi
0x1800891f0  mov     r9, r15
0x1800891f3  mov     dword ptr [rsp+78h+var_58], eax
0x1800891f7  mov     ebx, eax
0x1800891f9  call    fnEfsLogTrace1String1Dword
0x1800891fe  test    eax, eax
0x180089200  js      loc_1800895BE
0x180089206  mov     rsi, [rsp+78h+arg_8]
0x18008920e  cmp     [rbp+rsi*2+0], r13w
0x180089214  jnz     loc_180089595
0x18008921a  mov     r9d, edi
0x18008921d  test    rsi, rsi
0x180089220  jnz     short loc_18008922F
0x180089222  mov     dword ptr [rsp+78h+var_58], 29DFh
0x18008922a  jmp     loc_180089187
0x18008922f  mov     r12d, 29E2h
0x180089235  lea     rdx, EFS_TRACE_START_EVENT
0x18008923c  mov     r8, r15
0x18008923f  mov     dword ptr [rsp+78h+var_58], r12d
0x180089244  call    fnEfsLogTrace1Strings
0x180089249  lea     r15, [rsi+1]
0x18008924d  cmp     r15, rsi
0x180089250  jb      short loc_180089257
0x180089252  mov     ebx, r13d
0x180089255  jmp     short loc_180089260
0x180089257  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008925b  mov     ebx, 80070216h
0x180089260  mov     rcx, cs:g_hPublisher
0x180089267  lea     r9, sourceString
0x18008926e  mov     [rsp+78h+var_48], r12d
0x180089273  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008927a  mov     [rsp+78h+var_50], edi
0x18008927e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180089285  mov     dword ptr [rsp+78h+var_58], ebx
0x180089289  call    fnEfsLogTrace1String1Dword
0x18008928e  test    eax, eax
0x180089290  js      loc_1800895BE
0x180089296  mov     r12d, 29E3h
0x18008929c  lea     r8, sourceString
0x1800892a3  mov     r9d, edi
0x1800892a6  mov     dword ptr [rsp+78h+var_58], r12d
0x1800892ab  lea     rdx, EFS_TRACE_START_EVENT
0x1800892b2  call    fnEfsLogTrace1Strings
0x1800892b7  lea     r8, [rsp+78h+arg_10]; unsigned __int64 *
0x1800892bf  mov     edx, 2; unsigned __int64
0x1800892c4  mov     rcx, r15; unsigned __int64
0x1800892c7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800892cc  mov     rcx, cs:g_hPublisher
0x1800892d3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800892da  mov     [rsp+78h+var_48], r12d
0x1800892df  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800892e6  lea     r12, sourceString
0x1800892ed  mov     [rsp+78h+var_50], edi
0x1800892f1  mov     r9, r12
0x1800892f4  mov     dword ptr [rsp+78h+var_58], eax
0x1800892f8  mov     ebx, eax
0x1800892fa  call    fnEfsLogTrace1String1Dword
0x1800892ff  test    eax, eax
0x180089301  js      loc_1800895BE
0x180089307  mov     r14d, 29E8h
0x18008930d  lea     rdx, EFS_TRACE_START_EVENT
0x180089314  mov     r9d, edi
0x180089317  mov     dword ptr [rsp+78h+var_58], r14d
0x18008931c  mov     r8, r12
0x18008931f  call    fnEfsLogTrace1Strings
0x180089324  mov     rcx, [rsp+78h+arg_10]
0x18008932c  lea     r9, [rsp+78h+lpFileName]
0x180089334  xor     r8d, r8d
0x180089337  xor     edx, edx
0x180089339  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x18008933e  mov     rcx, cs:g_hPublisher
0x180089345  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008934c  mov     [rsp+78h+var_48], r14d
0x180089351  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180089358  mov     [rsp+78h+var_50], edi
0x18008935c  mov     r9, r12
0x18008935f  mov     dword ptr [rsp+78h+var_58], eax
0x180089363  mov     ebx, eax
0x180089365  call    fnEfsLogTrace1String1Dword
0x18008936a  test    eax, eax
0x18008936c  js      loc_18008958B
0x180089372  lea     r12d, [r14+4]
0x180089376  mov     r9d, edi
0x180089379  lea     r8, sourceString
0x180089380  mov     dword ptr [rsp+78h+var_58], r12d
0x180089385  lea     rdx, EFS_TRACE_START_EVENT
0x18008938c  call    fnEfsLogTrace1Strings
0x180089391  mov     r14, [rsp+78h+lpFileName]
0x180089399  mov     r8, rbp; unsigned __int16 *
0x18008939c  mov     rcx, r14; unsigned __int16 *
0x18008939f  mov     rdx, r15; unsigned __int64
0x1800893a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800893a7  mov     rcx, cs:g_hPublisher
0x1800893ae  lea     r9, sourceString
0x1800893b5  mov     [rsp+78h+var_48], r12d
0x1800893ba  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800893c1  mov     [rsp+78h+var_50], edi
0x1800893c5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800893cc  mov     dword ptr [rsp+78h+var_58], eax
0x1800893d0  mov     ebx, eax
0x1800893d2  call    fnEfsLogTrace1String1Dword
0x1800893d7  test    eax, eax
0x1800893d9  js      loc_1800895BE
0x1800893df  test    rsi, rsi
0x1800893e2  jz      short loc_180089406
0x1800893e4  cmp     word ptr [r14+rsi*2-2], 5Ch ; '\'
0x1800893eb  jz      short loc_1800893F6
0x1800893ed  cmp     word ptr [r14+rsi*2-2], 2Fh ; '/'
0x1800893f4  jnz     short loc_180089401
0x1800893f6  sub     rsi, 1
0x1800893fa  mov     [r14+rsi*2], r13w
0x1800893ff  jnz     short loc_1800893E4
0x180089401  test    rsi, rsi
0x180089404  jnz     short loc_18008941E
0x180089406  mov     dword ptr [rsp+78h+var_58], 29F7h
0x18008940e  mov     ebx, 80070057h
0x180089413  mov     r8d, 80070057h
0x180089419  jmp     loc_1800895A8
0x18008941e  mov     rcx, r14; lpFileName
0x180089421  call    cs:__imp_GetFileAttributesW
0x180089427  cmp     eax, 0FFFFFFFFh
0x18008942a  jz      short loc_18008943E
0x18008942c  test    al, 10h
0x18008942e  jnz     loc_1800895BE
0x180089434  mov     dword ptr [rsp+78h+var_58], 2A04h
0x18008943c  jmp     short loc_18008940E
0x18008943e  call    cs:__imp_GetLastError
0x180089444  mov     ebx, eax
0x180089446  mov     r12d, 80070000h
0x18008944c  test    eax, eax
0x18008944e  jle     short loc_180089456
0x180089450  movzx   ebx, ax
0x180089453  or      ebx, r12d
0x180089456  lea     eax, [rbx+7FF8FFFEh]
0x18008945c  cmp     eax, 1
0x18008945f  jbe     short loc_180089471
0x180089461  mov     dword ptr [rsp+78h+var_58], 2A17h
0x180089469  mov     r8d, ebx
0x18008946c  jmp     loc_1800895A8
0x180089471  xor     edx, edx; lpSecurityAttributes
0x180089473  mov     rcx, r14; lpPathName
0x180089476  call    cs:__imp_CreateDirectoryW
0x18008947c  test    eax, eax
0x18008947e  jz      short loc_18008949D
0x180089480  mov     ebx, r13d
0x180089483  mov     dword ptr [rsp+78h+var_58], 2A24h
0x18008948b  mov     r9d, edi
0x18008948e  lea     rdx, EFS_TRACE_STATUS
0x180089495  xor     r8d, r8d
0x180089498  jmp     loc_1800895B2
0x18008949d  call    cs:__imp_GetLastError
0x1800894a3  mov     ebx, eax
0x1800894a5  test    eax, eax
0x1800894a7  jle     short loc_1800894AF
0x1800894a9  movzx   ebx, ax
0x1800894ac  or      ebx, r12d
0x1800894af  lea     eax, [rbx+7FF8FFFEh]
0x1800894b5  cmp     eax, 1
0x1800894b8  jbe     short loc_1800894C4
0x1800894ba  mov     dword ptr [rsp+78h+var_58], 2A35h
0x1800894c2  jmp     short loc_180089469
0x1800894c4  test    rsi, rsi
0x1800894c7  jz      short loc_1800894E1
0x1800894c9  cmp     word ptr [r14+rsi*2-2], 5Ch ; '\'
0x1800894d0  jz      short loc_1800894EE
0x1800894d2  cmp     word ptr [r14+rsi*2-2], 2Fh ; '/'
0x1800894d9  jz      short loc_1800894EE
0x1800894db  sub     rsi, 1
0x1800894df  jnz     short loc_1800894C9
0x1800894e1  mov     dword ptr [rsp+78h+var_58], 2A47h
0x1800894e9  jmp     loc_18008940E
0x1800894ee  movzx   ebp, word ptr [r14+rsi*2-2]
0x1800894f4  lea     r8, sourceString
0x1800894fb  mov     r15d, 2A51h
0x180089501  mov     [r14+rsi*2-2], r13w
0x180089507  mov     r9d, edi
0x18008950a  mov     dword ptr [rsp+78h+var_58], r15d
0x18008950f  lea     rdx, EFS_TRACE_START_EVENT
0x180089516  call    fnEfsLogTrace1Strings
0x18008951b  mov     rcx, r14; unsigned __int16 *
0x18008951e  call    ?CreateDirectoryInternal@CDplService@@SAJPEBG@Z; CDplService::CreateDirectoryInternal(ushort const *)
0x180089523  mov     rcx, cs:g_hPublisher
0x18008952a  lea     r9, sourceString
0x180089531  mov     [rsp+78h+var_48], r15d
0x180089536  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008953d  mov     [rsp+78h+var_50], edi
0x180089541  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180089548  mov     dword ptr [rsp+78h+var_58], eax
0x18008954c  mov     ebx, eax
0x18008954e  call    fnEfsLogTrace1String1Dword
0x180089553  test    eax, eax
0x180089555  js      short loc_1800895BE
0x180089557  xor     edx, edx; lpSecurityAttributes
0x180089559  mov     [r14+rsi*2-2], bp
0x18008955f  mov     rcx, r14; lpPathName
0x180089562  call    cs:__imp_CreateDirectoryW
0x180089568  test    eax, eax
0x18008956a  jnz     short loc_1800895BE
0x18008956c  call    cs:__imp_GetLastError
0x180089572  mov     ebx, eax
0x180089574  test    eax, eax
0x180089576  jle     short loc_18008957E
0x180089578  movzx   ebx, ax
0x18008957b  or      ebx, r12d
0x18008957e  mov     dword ptr [rsp+78h+var_58], 2A5Ch
0x180089586  jmp     loc_180089469
0x18008958b  mov     r14, [rsp+78h+lpFileName]
0x180089593  jmp     short loc_1800895BE
0x180089595  mov     ebx, 8000FFFFh
0x18008959a  mov     dword ptr [rsp+78h+var_58], 29DBh
0x1800895a2  mov     r8d, 8000FFFFh
0x1800895a8  mov     r9d, edi
0x1800895ab  lea     rdx, EFS_TRACE_ERROR
0x1800895b2  mov     rcx, cs:g_hPublisher
0x1800895b9  call    fnEfsLogTrace1
0x1800895be  mov     rcx, r14
0x1800895c1  call    ??$MemFreeIf@G@CDplService@@SAPEAGPEAG@Z; CDplService::MemFreeIf<ushort>(ushort *)
0x1800895c6  mov     eax, ebx
0x1800895c8  mov     rbx, [rsp+78h+arg_18]
0x1800895d0  add     rsp, 40h
0x1800895d4  pop     r15
0x1800895d6  pop     r14
0x1800895d8  pop     r13
0x1800895da  pop     r12
0x1800895dc  pop     rdi
0x1800895dd  pop     rsi
0x1800895de  pop     rbp
0x1800895df  retn
```

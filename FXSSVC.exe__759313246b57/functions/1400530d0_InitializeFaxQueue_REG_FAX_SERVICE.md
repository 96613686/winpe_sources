# InitializeFaxQueue(_REG_FAX_SERVICE *)

- ea: `0x1400530d0`
- end: `0x14005340c`
- name: `?InitializeFaxQueue@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `828`
- prototype: `_BOOL8 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004ae64`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x1400530d0`
- `0x1400698ec`
- `0x14006998c`
- `0x14006a574`
- `0x140072490`
- `0x1400728bc`
- `0x1400795e0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140053175`
- `KERNEL32!GetLastError` at `0x14005321c`
- `KERNEL32!GetLastError` at `0x140053175`
- `KERNEL32!GetLastError` at `0x14005321c`
- `KERNEL32!SetLastError` at `0x1400533d9`
- `KERNEL32!SetLastError` at `0x1400533d9`

## pseudocode

```c
_BOOL8 __fastcall InitializeFaxQueue(struct _REG_FAX_SERVICE *a1)
{
  unsigned __int16 *v1; // rcx
  wchar_t *v2; // rax
  wchar_t *v3; // rbx
  DWORD LastError; // eax
  CFaxConfiguration *v6; // rcx
  DWORD v7; // eax
  DWORD v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  int v12; // eax
  DWORD valid; // eax
  unsigned __int16 v14[264]; // [rsp+30h] [rbp-248h] BYREF

  memset_0(v14, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
  }
  v1 = (unsigned __int16 *)*((_QWORD *)g_pFaxConfig + 12);
  if ( v1 )
  {
    v2 = (wchar_t *)ExpandEnvironmentString(v1);
    v3 = v2;
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, LastError);
      }
      return 0;
    }
    if ( !(unsigned int)PathRepresentsFullPath(v2) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, v3);
      }
      pMemFree(v3);
      return 0;
    }
    pMemFree(*((LPVOID *)g_pFaxConfig + 12));
    v6 = g_pFaxConfig;
    *((_QWORD *)g_pFaxConfig + 12) = v3;
LABEL_48:
    valid = IsValidFaxFolder(*((unsigned __int16 **)v6 + 12));
    v8 = valid;
    if ( valid )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
          *((_QWORD *)g_pFaxConfig + 12),
          valid);
      }
      goto LABEL_53;
    }
    return v8 == 0;
  }
  if ( (unsigned int)GetSpecialPath(35, v14, 0x104u) )
  {
    v9 = -1;
    do
      ++v9;
    while ( v14[v9] );
    v10 = (unsigned int)(v9 + 34);
    if ( (unsigned int)v10 >= 0x104 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
      }
      v8 = 111;
      goto LABEL_53;
    }
    v11 = (unsigned __int16 *)pMemAlloc(2 * v10);
    *((_QWORD *)g_pFaxConfig + 12) = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
          (unsigned int)v10);
      }
      v8 = 8;
      goto LABEL_53;
    }
    v12 = StringCchPrintfW(v11, (unsigned int)v10, L"%s\\%s", v14, L"Microsoft\\Windows NT\\MSFax\\Queue");
    v8 = v12;
    if ( v12 >= 0 )
    {
      v6 = g_pFaxConfig;
      goto LABEL_48;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids,
        (unsigned int)v12);
    }
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v8;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, v7);
    }
  }
  if ( v8 )
  {
LABEL_53:
    pMemFree(*((LPVOID *)g_pFaxConfig + 12));
    *((_QWORD *)g_pFaxConfig + 12) = 0;
    SetLastError(v8);
  }
  return v8 == 0;
}

```

## disassembly

```asm
0x1400530d0  push    rbx
0x1400530d2  push    rsi
0x1400530d3  push    rdi
0x1400530d4  push    r14
0x1400530d6  push    r15
0x1400530d8  sub     rsp, 250h
0x1400530df  mov     rax, cs:__security_cookie
0x1400530e6  xor     rax, rsp
0x1400530e9  mov     [rsp+278h+var_38], rax
0x1400530f1  xor     edx, edx; Val
0x1400530f3  lea     rcx, [rsp+278h+var_248]; void *
0x1400530f8  mov     r8d, 208h; Size
0x1400530fe  call    memset_0
0x140053103  mov     rcx, cs:WPP_GLOBAL_Control
0x14005310a  lea     r14, WPP_GLOBAL_Control
0x140053111  lea     r15, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x140053118  cmp     rcx, r14
0x14005311b  jz      short loc_14005313A
0x14005311d  test    byte ptr [rcx+1Ch], 4
0x140053121  jz      short loc_14005313A
0x140053123  cmp     byte ptr [rcx+19h], 5
0x140053127  jb      short loc_14005313A
0x140053129  mov     rcx, [rcx+10h]
0x14005312d  mov     edx, 0Dh
0x140053132  mov     r8, r15
0x140053135  call    WPP_SF_
0x14005313a  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140053141  xor     esi, esi
0x140053143  mov     rcx, [rax+60h]; unsigned __int16 *
0x140053147  test    rcx, rcx
0x14005314a  jz      loc_140053201
0x140053150  call    ExpandEnvironmentString
0x140053155  mov     rbx, rax
0x140053158  test    rax, rax
0x14005315b  jnz     short loc_1400531A1
0x14005315d  mov     rax, cs:WPP_GLOBAL_Control
0x140053164  cmp     rax, r14
0x140053167  jz      short loc_14005319A
0x140053169  test    byte ptr [rax+1Ch], 4
0x14005316d  jz      short loc_14005319A
0x14005316f  cmp     byte ptr [rax+19h], 2
0x140053173  jb      short loc_14005319A
0x140053175  call    cs:__imp_GetLastError
0x14005317c  nop     dword ptr [rax+rax+00h]
0x140053181  mov     rcx, cs:WPP_GLOBAL_Control
0x140053188  lea     edx, [rsi+0Eh]
0x14005318b  mov     r9d, eax
0x14005318e  mov     r8, r15
0x140053191  mov     rcx, [rcx+10h]
0x140053195  call    WPP_SF_d
0x14005319a  xor     eax, eax
0x14005319c  jmp     loc_1400533EC
0x1400531a1  mov     rcx, rbx; String1
0x1400531a4  call    PathRepresentsFullPath
0x1400531a9  test    eax, eax
0x1400531ab  jnz     short loc_1400531E1
0x1400531ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400531b4  cmp     rcx, r14
0x1400531b7  jz      short loc_1400531D7
0x1400531b9  test    byte ptr [rcx+1Ch], 4
0x1400531bd  jz      short loc_1400531D7
0x1400531bf  cmp     byte ptr [rcx+19h], 2
0x1400531c3  jb      short loc_1400531D7
0x1400531c5  mov     rcx, [rcx+10h]
0x1400531c9  lea     edx, [rax+0Fh]
0x1400531cc  mov     r9, rbx
0x1400531cf  mov     r8, r15
0x1400531d2  call    WPP_SF_S
0x1400531d7  mov     rcx, rbx; lpMem
0x1400531da  call    pMemFree
0x1400531df  jmp     short loc_14005319A
0x1400531e1  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400531e8  mov     rcx, [rcx+60h]; lpMem
0x1400531ec  call    pMemFree
0x1400531f1  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400531f8  mov     [rcx+60h], rbx
0x1400531fc  jmp     loc_140053375
0x140053201  mov     edi, 104h
0x140053206  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x14005320b  mov     r8d, edi; unsigned __int64
0x14005320e  mov     ecx, 23h ; '#'; csidl
0x140053213  call    GetSpecialPath
0x140053218  test    eax, eax
0x14005321a  jnz     short loc_140053267
0x14005321c  call    cs:__imp_GetLastError
0x140053223  nop     dword ptr [rax+rax+00h]
0x140053228  mov     ebx, eax
0x14005322a  mov     rcx, cs:WPP_GLOBAL_Control
0x140053231  cmp     rcx, r14
0x140053234  jz      loc_140053368
0x14005323a  test    byte ptr [rcx+1Ch], 4
0x14005323e  jz      loc_140053368
0x140053244  cmp     byte ptr [rcx+19h], 2
0x140053248  jb      loc_140053368
0x14005324e  mov     rcx, [rcx+10h]
0x140053252  mov     edx, 10h
0x140053257  mov     r9d, eax
0x14005325a  mov     r8, r15
0x14005325d  call    WPP_SF_d
0x140053262  jmp     loc_140053368
0x140053267  lea     rcx, [rsp+278h+var_248]
0x14005326c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140053270  inc     rax
0x140053273  cmp     [rcx+rax*2], si
0x140053277  jnz     short loc_140053270
0x140053279  lea     ebx, [rax+22h]
0x14005327c  cmp     ebx, edi
0x14005327e  jb      short loc_1400532B3
0x140053280  mov     rcx, cs:WPP_GLOBAL_Control
0x140053287  cmp     rcx, r14
0x14005328a  jz      short loc_1400532A9
0x14005328c  test    byte ptr [rcx+1Ch], 4
0x140053290  jz      short loc_1400532A9
0x140053292  cmp     byte ptr [rcx+19h], 2
0x140053296  jb      short loc_1400532A9
0x140053298  mov     rcx, [rcx+10h]
0x14005329c  mov     edx, 11h
0x1400532a1  mov     r8, r15
0x1400532a4  call    WPP_SF_
0x1400532a9  mov     ebx, 6Fh ; 'o'
0x1400532ae  jmp     loc_1400533BC
0x1400532b3  lea     rcx, [rbx+rbx]; dwBytes
0x1400532b7  mov     edi, ebx
0x1400532b9  call    pMemAlloc
0x1400532be  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400532c5  mov     [rcx+60h], rax
0x1400532c9  test    rax, rax
0x1400532cc  jnz     short loc_140053302
0x1400532ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532d5  cmp     rcx, r14
0x1400532d8  jz      short loc_1400532F8
0x1400532da  test    byte ptr [rcx+1Ch], 4
0x1400532de  jz      short loc_1400532F8
0x1400532e0  cmp     byte ptr [rcx+19h], 2
0x1400532e4  jb      short loc_1400532F8
0x1400532e6  mov     rcx, [rcx+10h]
0x1400532ea  lea     edx, [rax+12h]
0x1400532ed  mov     r9d, ebx
0x1400532f0  mov     r8, r15
0x1400532f3  call    WPP_SF_d
0x1400532f8  mov     ebx, 8
0x1400532fd  jmp     loc_1400533BC
0x140053302  lea     rcx, aMicrosoftWindo_0; "Microsoft\\Windows NT\\MSFax\\Queue"
0x140053309  mov     rdx, rdi; unsigned __int64
0x14005330c  mov     [rsp+278h+var_258], rcx
0x140053311  lea     r9, [rsp+278h+var_248]
0x140053316  mov     rcx, rax; unsigned __int16 *
0x140053319  lea     r8, aSS_0; "%s\\%s"
0x140053320  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140053325  mov     ebx, eax
0x140053327  test    eax, eax
0x140053329  jns     short loc_14005336E
0x14005332b  mov     rcx, cs:WPP_GLOBAL_Control
0x140053332  cmp     rcx, r14
0x140053335  jz      short loc_140053357
0x140053337  test    byte ptr [rcx+1Ch], 4
0x14005333b  jz      short loc_140053357
0x14005333d  cmp     byte ptr [rcx+19h], 2
0x140053341  jb      short loc_140053357
0x140053343  mov     rcx, [rcx+10h]
0x140053347  mov     edx, 13h
0x14005334c  mov     r9d, eax
0x14005334f  mov     r8, r15
0x140053352  call    WPP_SF_d
0x140053357  mov     eax, ebx
0x140053359  and     eax, 1FFF0000h
0x14005335e  cmp     eax, 70000h
0x140053363  jnz     short loc_140053368
0x140053365  movzx   ebx, bx
0x140053368  test    ebx, ebx
0x14005336a  jz      short loc_1400533E5
0x14005336c  jmp     short loc_1400533BC
0x14005336e  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140053375  mov     rcx, [rcx+60h]; unsigned __int16 *
0x140053379  call    IsValidFaxFolder
0x14005337e  mov     ebx, eax
0x140053380  test    eax, eax
0x140053382  jz      short loc_1400533E5
0x140053384  mov     rcx, cs:WPP_GLOBAL_Control
0x14005338b  cmp     rcx, r14
0x14005338e  jz      short loc_1400533BC
0x140053390  test    byte ptr [rcx+1Ch], 4
0x140053394  jz      short loc_1400533BC
0x140053396  cmp     byte ptr [rcx+19h], 2
0x14005339a  jb      short loc_1400533BC
0x14005339c  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400533a3  mov     edx, 14h
0x1400533a8  mov     rcx, [rcx+10h]
0x1400533ac  mov     r8, r15
0x1400533af  mov     dword ptr [rsp+278h+var_258], eax
0x1400533b3  mov     r9, [r9+60h]
0x1400533b7  call    WPP_SF_Sd
0x1400533bc  mov     rcx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400533c3  mov     rcx, [rcx+60h]; lpMem
0x1400533c7  call    pMemFree
0x1400533cc  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400533d3  mov     ecx, ebx; dwErrCode
0x1400533d5  mov     [rax+60h], rsi
0x1400533d9  call    cs:__imp_SetLastError
0x1400533e0  nop     dword ptr [rax+rax+00h]
0x1400533e5  test    ebx, ebx
0x1400533e7  mov     eax, esi
0x1400533e9  setz    al
0x1400533ec  mov     rcx, [rsp+278h+var_38]
0x1400533f4  xor     rcx, rsp; StackCookie
0x1400533f7  call    __security_check_cookie
0x1400533fc  add     rsp, 250h
0x140053403  pop     r15
0x140053405  pop     r14
0x140053407  pop     rdi
0x140053408  pop     rsi
0x140053409  pop     rbx
0x14005340a  retn
```

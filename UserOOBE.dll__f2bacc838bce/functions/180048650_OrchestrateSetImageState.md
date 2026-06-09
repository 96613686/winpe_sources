# OrchestrateSetImageState

- ea: `0x180048650`
- end: `0x1800488d8`
- name: `OrchestrateSetImageState`
- size: `648`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800488e0`

## callees

- `0x180048430`
- `0x180048650`
- `0x1800491f4`
- `0x18004929c`
- `0x180049484`
- `0x18004a000`
- `0x18004ab30`
- `0x18004ace8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800487a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004888e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800488ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800487a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004888e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800488ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800487af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004889c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800488bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800487af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004889c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800488bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048857`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004883d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004883d`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180048820`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180048820`

## pseudocode

```c
__int64 __fastcall OrchestrateSetImageState(__int64 a1, const wchar_t *a2, const WCHAR *a3)
{
  signed int v4; // ebx
  wchar_t *Expand; // r14
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax
  signed int v9; // eax
  bool v10; // sf
  signed int v11; // eax
  __int64 v12; // rcx
  wchar_t *v13; // rdi
  signed int v14; // eax
  bool v15; // sf
  signed int v16; // eax
  int PersistedFileLocation; // eax
  HANDLE ProcessHeap; // rax
  _WORD *v19; // rsi
  signed int v20; // eax
  bool v21; // sf
  signed int v22; // eax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  STRSAFE_PCNZWCH pszSrc; // [rsp+68h] [rbp+10h] BYREF

  pszSrc = a2;
  if ( a3 && *a3 )
  {
    v4 = 0;
    Expand = (wchar_t *)AllocateExpand(L"%windir%");
    if ( !Expand )
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
        v7 = 1;
      if ( !v7 )
        return (unsigned int)-2147467259;
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 < 0 )
        return (unsigned int)v4;
    }
    if ( !(unsigned int)RegSetString(
                          -2147483646,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
                          L"ImageState",
                          a3)
      || !(unsigned int)RegSetString(
                          -2147483646,
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\ImageServicingData",
                          L"ImageState",
                          a3) )
    {
      v9 = GetLastError();
      v10 = v9 < 0;
      if ( v9 > 0 )
        v10 = 1;
      if ( !v10 )
        goto LABEL_50;
      v11 = GetLastError();
      v4 = v11;
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
    }
    if ( v4 < 0 )
      goto LABEL_51;
    v13 = (wchar_t *)BuildPath(Expand, L"Setup\\State");
    if ( v13 )
      goto LABEL_25;
    v14 = GetLastError();
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( v15 )
    {
      v16 = GetLastError();
      v4 = v16;
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_51;
LABEL_25:
      pszSrc = 0;
      PersistedFileLocation = OrchestrateGetPersistedFileLocation(v12, &pszSrc);
      v4 = PersistedFileLocation;
      if ( PersistedFileLocation < 0 )
      {
        if ( PersistedFileLocation != -2147023728 )
          goto LABEL_48;
        v4 = 1;
      }
      else
      {
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
        }
        v13 = (wchar_t *)pszSrc;
      }
      v19 = (_WORD *)BuildPath(v13, L"State.ini");
      if ( v19 && ((unsigned int)DirectoryExists(v13) || (unsigned int)CreatePath(v13)) )
      {
        if ( *v19 )
        {
          if ( WritePrivateProfileStringW(L"State", L"ImageState", a3, v19) && (unsigned int)FlushFile(v19) )
          {
LABEL_47:
            v23 = GetProcessHeap();
            HeapFree(v23, 0, v19);
LABEL_48:
            if ( v13 )
            {
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v13);
            }
            goto LABEL_51;
          }
        }
        else
        {
          SetLastError(0x57u);
        }
      }
      v20 = GetLastError();
      v21 = v20 < 0;
      if ( v20 > 0 )
        v21 = 1;
      if ( v21 )
      {
        v22 = GetLastError();
        v4 = v22;
        if ( v22 > 0 )
          v4 = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      if ( !v19 )
        goto LABEL_48;
      goto LABEL_47;
    }
LABEL_50:
    v4 = -2147467259;
LABEL_51:
    if ( Expand )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, Expand);
    }
    return (unsigned int)v4;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180048650  mov     [rsp+pszSrc], rdx
0x180048655  push    rbx
0x180048656  push    rbp
0x180048657  push    rsi
0x180048658  push    rdi
0x180048659  push    r14
0x18004865b  push    r15
0x18004865d  sub     rsp, 28h
0x180048661  mov     rbp, r8
0x180048664  test    r8, r8
0x180048667  jz      loc_1800488C6
0x18004866d  xor     eax, eax
0x18004866f  cmp     ax, [r8]
0x180048673  jz      loc_1800488C6
0x180048679  lea     rcx, aWindir; "%windir%"
0x180048680  xor     ebx, ebx
0x180048682  call    AllocateExpand
0x180048687  mov     r14, rax
0x18004868a  mov     r15d, 80070000h
0x180048690  test    rax, rax
0x180048693  jnz     short loc_1800486C7
0x180048695  call    cs:__imp_GetLastError
0x18004869b  test    eax, eax
0x18004869d  jle     short loc_1800486A7
0x18004869f  movzx   eax, ax
0x1800486a2  or      eax, r15d
0x1800486a5  test    eax, eax
0x1800486a7  jns     loc_1800487BC
0x1800486ad  call    cs:__imp_GetLastError
0x1800486b3  mov     ebx, eax
0x1800486b5  test    eax, eax
0x1800486b7  jle     short loc_1800486BF
0x1800486b9  movzx   ebx, ax
0x1800486bc  or      ebx, r15d
0x1800486bf  test    ebx, ebx
0x1800486c1  js      loc_1800488C2
0x1800486c7  mov     rdi, 0FFFFFFFF80000002h
0x1800486ce  lea     r8, KeyName; "ImageState"
0x1800486d5  mov     rcx, rdi
0x1800486d8  lea     rdx, aSoftwareMicros_21; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800486df  mov     r9, rbp
0x1800486e2  call    RegSetString
0x1800486e7  test    eax, eax
0x1800486e9  jz      short loc_180048708
0x1800486eb  mov     r9, rbp
0x1800486ee  lea     r8, KeyName; "ImageState"
0x1800486f5  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800486fc  mov     rcx, rdi
0x1800486ff  call    RegSetString
0x180048704  test    eax, eax
0x180048706  jnz     short loc_180048732
0x180048708  call    cs:__imp_GetLastError
0x18004870e  test    eax, eax
0x180048710  jle     short loc_18004871A
0x180048712  movzx   eax, ax
0x180048715  or      eax, r15d
0x180048718  test    eax, eax
0x18004871a  jns     loc_1800488A4
0x180048720  call    cs:__imp_GetLastError
0x180048726  mov     ebx, eax
0x180048728  test    eax, eax
0x18004872a  jle     short loc_180048732
0x18004872c  movzx   ebx, ax
0x18004872f  or      ebx, r15d
0x180048732  test    ebx, ebx
0x180048734  js      loc_1800488A9
0x18004873a  lea     rdx, aSetupState; "Setup\\State"
0x180048741  mov     rcx, r14; pszSrc
0x180048744  call    BuildPath
0x180048749  mov     rdi, rax
0x18004874c  test    rax, rax
0x18004874f  jnz     short loc_180048783
0x180048751  call    cs:__imp_GetLastError
0x180048757  test    eax, eax
0x180048759  jle     short loc_180048763
0x18004875b  movzx   eax, ax
0x18004875e  or      eax, r15d
0x180048761  test    eax, eax
0x180048763  jns     loc_1800488A4
0x180048769  call    cs:__imp_GetLastError
0x18004876f  mov     ebx, eax
0x180048771  test    eax, eax
0x180048773  jle     short loc_18004877B
0x180048775  movzx   ebx, ax
0x180048778  or      ebx, r15d
0x18004877b  test    ebx, ebx
0x18004877d  js      loc_1800488A9
0x180048783  lea     rdx, [rsp+58h+pszSrc]
0x180048788  mov     [rsp+58h+pszSrc], 0
0x180048791  call    OrchestrateGetPersistedFileLocation
0x180048796  mov     ebx, eax
0x180048798  test    eax, eax
0x18004879a  js      short loc_1800487C6
0x18004879c  test    rdi, rdi
0x18004879f  jz      short loc_1800487B5
0x1800487a1  call    cs:__imp_GetProcessHeap
0x1800487a7  mov     r8, rdi; lpMem
0x1800487aa  xor     edx, edx; dwFlags
0x1800487ac  mov     rcx, rax; hHeap
0x1800487af  call    cs:__imp_HeapFree
0x1800487b5  mov     rdi, [rsp+58h+pszSrc]
0x1800487ba  jmp     short loc_1800487D6
0x1800487bc  mov     ebx, 80004005h
0x1800487c1  jmp     loc_1800488C2
0x1800487c6  cmp     eax, 80070490h
0x1800487cb  jnz     loc_180048889
0x1800487d1  mov     ebx, 1
0x1800487d6  lea     rdx, aStateIni; "State.ini"
0x1800487dd  mov     rcx, rdi; pszSrc
0x1800487e0  call    BuildPath
0x1800487e5  mov     rsi, rax
0x1800487e8  test    rax, rax
0x1800487eb  jz      short loc_180048843
0x1800487ed  mov     rcx, rdi
0x1800487f0  call    DirectoryExists
0x1800487f5  test    eax, eax
0x1800487f7  jnz     short loc_180048805
0x1800487f9  mov     rcx, rdi
0x1800487fc  call    CreatePath
0x180048801  test    eax, eax
0x180048803  jz      short loc_180048843
0x180048805  xor     eax, eax
0x180048807  cmp     ax, [rsi]
0x18004880a  jz      short loc_180048838
0x18004880c  mov     r9, rsi; lpFileName
0x18004880f  lea     rdx, KeyName; "ImageState"
0x180048816  mov     r8, rbp; lpString
0x180048819  lea     rcx, AppName; "State"
0x180048820  call    cs:__imp_WritePrivateProfileStringW
0x180048826  test    eax, eax
0x180048828  jz      short loc_180048843
0x18004882a  mov     rcx, rsi
0x18004882d  call    FlushFile
0x180048832  test    eax, eax
0x180048834  jz      short loc_180048843
0x180048836  jmp     short loc_180048875
0x180048838  mov     ecx, 57h ; 'W'; dwErrCode
0x18004883d  call    cs:__imp_SetLastError
0x180048843  call    cs:__imp_GetLastError
0x180048849  test    eax, eax
0x18004884b  jle     short loc_180048855
0x18004884d  movzx   eax, ax
0x180048850  or      eax, r15d
0x180048853  test    eax, eax
0x180048855  jns     short loc_18004886B
0x180048857  call    cs:__imp_GetLastError
0x18004885d  mov     ebx, eax
0x18004885f  test    eax, eax
0x180048861  jle     short loc_180048870
0x180048863  movzx   ebx, ax
0x180048866  or      ebx, r15d
0x180048869  jmp     short loc_180048870
0x18004886b  mov     ebx, 80004005h
0x180048870  test    rsi, rsi
0x180048873  jz      short loc_180048889
0x180048875  call    cs:__imp_GetProcessHeap
0x18004887b  mov     r8, rsi; lpMem
0x18004887e  xor     edx, edx; dwFlags
0x180048880  mov     rcx, rax; hHeap
0x180048883  call    cs:__imp_HeapFree
0x180048889  test    rdi, rdi
0x18004888c  jz      short loc_1800488A9
0x18004888e  call    cs:__imp_GetProcessHeap
0x180048894  mov     r8, rdi; lpMem
0x180048897  xor     edx, edx; dwFlags
0x180048899  mov     rcx, rax; hHeap
0x18004889c  call    cs:__imp_HeapFree
0x1800488a2  jmp     short loc_1800488A9
0x1800488a4  mov     ebx, 80004005h
0x1800488a9  test    r14, r14
0x1800488ac  jz      short loc_1800488C2
0x1800488ae  call    cs:__imp_GetProcessHeap
0x1800488b4  mov     r8, r14; lpMem
0x1800488b7  xor     edx, edx; dwFlags
0x1800488b9  mov     rcx, rax; hHeap
0x1800488bc  call    cs:__imp_HeapFree
0x1800488c2  mov     eax, ebx
0x1800488c4  jmp     short loc_1800488CB
0x1800488c6  mov     eax, 80070057h
0x1800488cb  add     rsp, 28h
0x1800488cf  pop     r15
0x1800488d1  pop     r14
0x1800488d3  pop     rdi
0x1800488d4  pop     rsi
0x1800488d5  pop     rbp
0x1800488d6  pop     rbx
0x1800488d7  retn
```

# CModelDownloadComponent::EnumerateLocaleSubFolders(ushort const *)

- ea: `0x14000ea08`
- end: `0x14000eb86`
- name: `?EnumerateLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG@Z`
- size: `382`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000cd18`
- `0x14000e8d8`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000985c`
- `0x14000af50`
- `0x14000ea08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000eaff`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000eaff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000eb25`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000eb25`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000eb0d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000eb0d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ea80`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ea80`

## string_xrefs

- `0x14000eb32`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2357)`
- `0x14000eb3d`: `CModelDownloadComponent::EnumerateLocaleSubFolders`
- `0x14000ea94`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2365)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::EnumerateLocaleSubFolders(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2)
{
  HANDLE FirstFileW; // rdi
  unsigned int v5; // ebx
  const wchar_t *v6; // rax
  int i; // edx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-488h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-238h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 || !*a2 )
  {
    v5 = -2147024809;
    v6 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2357)";
    goto LABEL_16;
  }
  swprintf_s<261>(FileName, L"%s\\%s", a2, L"*");
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v5 = -2147024891;
    v6 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2365)";
LABEL_16:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::EnumerateLocaleSubFolders",
      v6,
      v5);
    return v5;
  }
  v5 = 0;
  *((_DWORD *)this + 6145) = 0;
  for ( i = 0; i < 32; i = *((_DWORD *)this + 6145) )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0
      && (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
    {
      *((_DWORD *)this + 6145) = i + 1;
      _o_wcscpy_s((char *)this + 522 * i + 7874, 261, FindFileData.cFileName);
    }
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      break;
  }
  FindClose(FirstFileW);
  return v5;
}

```

## disassembly

```asm
0x14000ea08  mov     [rsp+arg_10], rbx
0x14000ea0d  push    rbp
0x14000ea0e  push    rsi
0x14000ea0f  push    rdi
0x14000ea10  sub     rsp, 4A0h
0x14000ea17  mov     rax, cs:__security_cookie
0x14000ea1e  xor     rax, rsp
0x14000ea21  mov     [rsp+4B8h+var_28], rax
0x14000ea29  mov     rbx, rdx
0x14000ea2c  mov     rsi, rcx
0x14000ea2f  xor     edx, edx; Val
0x14000ea31  lea     rcx, [rsp+4B8h+FindFileData]; void *
0x14000ea36  mov     r8d, 250h; Size
0x14000ea3c  call    memset_0
0x14000ea41  xor     ebp, ebp
0x14000ea43  test    rbx, rbx
0x14000ea46  jz      loc_14000EB2D
0x14000ea4c  cmp     [rbx], bp
0x14000ea4f  jz      loc_14000EB2D
0x14000ea55  lea     r9, asc_140028618; "*"
0x14000ea5c  mov     r8, rbx
0x14000ea5f  lea     rdx, aSS; "%s\\%s"
0x14000ea66  lea     rcx, [rsp+4B8h+FileName]
0x14000ea6e  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000ea73  lea     rdx, [rsp+4B8h+FindFileData]; lpFindFileData
0x14000ea78  lea     rcx, [rsp+4B8h+FileName]; lpFileName
0x14000ea80  call    cs:__imp_FindFirstFileW
0x14000ea86  mov     rdi, rax
0x14000ea89  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ea8d  jnz     short loc_14000EAA0
0x14000ea8f  mov     ebx, 80070005h
0x14000ea94  lea     rax, aOnecoreuapEndu_2; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ea9b  jmp     loc_14000EB39
0x14000eaa0  mov     ebx, ebp
0x14000eaa2  mov     [rsi+6004h], ebp
0x14000eaa8  mov     edx, ebp
0x14000eaaa  test    byte ptr [rsp+4B8h+FindFileData.dwFileAttributes], 10h
0x14000eaaf  jbe     short loc_14000EB05
0x14000eab1  cmp     [rsp+4B8h+FindFileData.cFileName], 2Eh ; '.'
0x14000eab7  movzx   eax, [rsp+4B8h+FindFileData.cFileName+2]
0x14000eabc  jnz     short loc_14000EAD8
0x14000eabe  test    ax, ax
0x14000eac1  jz      short loc_14000EB05
0x14000eac3  cmp     [rsp+4B8h+FindFileData.cFileName], 2Eh ; '.'
0x14000eac9  jnz     short loc_14000EAD8
0x14000eacb  cmp     ax, 2Eh ; '.'
0x14000eacf  jnz     short loc_14000EAD8
0x14000ead1  cmp     [rsp+4B8h+FindFileData.cFileName+4], bp
0x14000ead6  jz      short loc_14000EB05
0x14000ead8  movsxd  rax, edx
0x14000eadb  lea     r8, [rsp+4B8h+FindFileData.cFileName]
0x14000eae0  imul    rcx, rax, 20Ah
0x14000eae7  lea     eax, [rdx+1]
0x14000eaea  mov     edx, 105h
0x14000eaef  add     rcx, 1EC2h
0x14000eaf6  mov     [rsi+6004h], eax
0x14000eafc  add     rcx, rsi
0x14000eaff  call    cs:__imp__o_wcscpy_s
0x14000eb05  lea     rdx, [rsp+4B8h+FindFileData]; lpFindFileData
0x14000eb0a  mov     rcx, rdi; hFindFile
0x14000eb0d  call    cs:__imp_FindNextFileW
0x14000eb13  test    eax, eax
0x14000eb15  jz      short loc_14000EB22
0x14000eb17  mov     edx, [rsi+6004h]
0x14000eb1d  cmp     edx, 20h ; ' '
0x14000eb20  jl      short loc_14000EAAA
0x14000eb22  mov     rcx, rdi; hFindFile
0x14000eb25  call    cs:__imp_FindClose
0x14000eb2b  jmp     short loc_14000EB61
0x14000eb2d  mov     ebx, 80070057h
0x14000eb32  lea     rax, aOnecoreuapEndu_37; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000eb39  mov     [rsp+4B8h+var_490], ebx
0x14000eb3d  lea     r9, aCmodeldownload_20; "CModelDownloadComponent::EnumerateLocal"...
0x14000eb44  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000eb4b  mov     [rsp+4B8h+var_498], rax
0x14000eb50  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000eb57  mov     ecx, 2; int
0x14000eb5c  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000eb61  mov     eax, ebx
0x14000eb63  mov     rcx, [rsp+4B8h+var_28]
0x14000eb6b  xor     rcx, rsp; StackCookie
0x14000eb6e  call    __security_check_cookie
0x14000eb73  mov     rbx, [rsp+4B8h+arg_10]
0x14000eb7b  add     rsp, 4A0h
0x14000eb82  pop     rdi
0x14000eb83  pop     rsi
0x14000eb84  pop     rbp
0x14000eb85  retn
```

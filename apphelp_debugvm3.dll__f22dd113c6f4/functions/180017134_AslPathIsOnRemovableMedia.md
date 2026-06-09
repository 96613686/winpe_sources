# AslPathIsOnRemovableMedia

- ea: `0x180017134`
- end: `0x18001732c`
- name: `AslPathIsOnRemovableMedia`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180016dc0`

## callees

- `0x18000f114`
- `0x180017134`
- `0x180039a66`
- `0x180039a8a`
- `0x1800591b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017282`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017282`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800172b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800172b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001729a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001729a`

## string_xrefs

- `0x180017270`: `ntdll.dll`
- `0x1800172d0`: `%ws not a full path we can operate on [%x]`
- `0x1800172e1`: `AslPathIsOnRemovableMedia`
- `0x180017319`: `AslPathIsOnRemovableMedia`
- `0x180017308`: `RtlStringCchCopyW failed for c:\ [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsOnRemovableMedia(int *a1, wchar_t *a2)
{
  size_t v3; // r14
  int v4; // ebp
  unsigned __int64 v5; // rax
  __int64 v6; // r8
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  wchar_t *v9; // r9
  wchar_t *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rbx
  UINT DriveTypeW_0; // ecx
  HMODULE Library; // rax
  HMODULE v16; // rsi
  __int64 (*ProcAddress)(void); // rax
  __int64 v18; // r8
  __int64 v19; // [rsp+28h] [rbp-50h]
  wchar_t String1[8]; // [rsp+30h] [rbp-48h] BYREF

  v3 = -1;
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 < 8 )
  {
    v11 = 0;
    v18 = 263;
LABEL_27:
    LODWORD(v19) = 0;
    AslLogCallPrintf(1, "AslPathIsOnRemovableMedia", v18, "%ws not a full path we can operate on [%x]", a2, v19);
    goto LABEL_16;
  }
  if ( a2[1] != 58 )
  {
    v11 = 0;
    if ( a2[1] == 92 )
      goto LABEL_16;
    v18 = 274;
    goto LABEL_27;
  }
  v6 = 5;
  v7 = L"c:\\";
  v8 = 2147483646;
  v9 = String1;
  do
  {
    if ( !v8 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v8;
    --v6;
  }
  while ( v6 );
  v10 = v9 - 1;
  v11 = v6 == 0 ? 0x80000005 : 0;
  if ( v6 )
    v10 = v9;
  *v10 = 0;
  if ( v6 )
  {
    v12 = (__int64)::String1;
    String1[0] = *a2;
    if ( !::String1 )
    {
      v12 = 2147352624;
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v16 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v12 = ProcAddress();
        FreeLibrary(v16);
      }
      ::String1 = (wchar_t *)v12;
    }
    do
      ++v3;
    while ( String1[v3] );
    if ( wcsnicmp_0(String1, (const wchar_t *)v12, v3) )
    {
      DriveTypeW_0 = GetDriveTypeW_0(String1);
      if ( ((DriveTypeW_0 - 2) & 0xFFFFFFFC) == 0 && DriveTypeW_0 != 3 )
        v4 = 1;
    }
    v11 = 0;
  }
  else
  {
    AslLogCallPrintf(1, "AslPathIsOnRemovableMedia", 291, "RtlStringCchCopyW failed for c:\\ [%x]", -2147483643);
  }
LABEL_16:
  *a1 = v4;
  return v11;
}

```

## disassembly

```asm
0x180017134  mov     [rsp+arg_10], rbx
0x180017139  mov     [rsp+arg_18], rbp
0x18001713e  push    rsi
0x18001713f  push    rdi
0x180017140  push    r12
0x180017142  push    r14
0x180017144  push    r15
0x180017146  sub     rsp, 50h
0x18001714a  mov     rax, cs:__security_cookie
0x180017151  xor     rax, rsp
0x180017154  mov     [rsp+78h+var_38], rax
0x180017159  xor     r12d, r12d
0x18001715c  mov     r15, rcx
0x18001715f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017163  mov     ebp, r12d
0x180017166  mov     rax, r14
0x180017169  inc     rax
0x18001716c  cmp     [rdx+rax*2], r12w
0x180017171  jnz     short loc_180017169
0x180017173  cmp     rax, 8
0x180017177  jb      loc_1800172C2
0x18001717d  cmp     word ptr [rdx+2], 3Ah ; ':'
0x180017182  jnz     loc_1800172F2
0x180017188  mov     r8d, 5
0x18001718e  lea     rcx, aC; "c:\\"
0x180017195  mov     eax, 7FFFFFFEh
0x18001719a  lea     r9, [rsp+78h+String1]
0x18001719f  lea     edi, [r8-4]
0x1800171a3  test    rax, rax
0x1800171a6  jz      short loc_1800171C6
0x1800171a8  movzx   r10d, word ptr [rcx]
0x1800171ac  test    r10w, r10w
0x1800171b0  jz      short loc_1800171C6
0x1800171b2  mov     [r9], r10w
0x1800171b6  add     rcx, 2
0x1800171ba  add     r9, 2
0x1800171be  sub     rax, rdi
0x1800171c1  sub     r8, rdi
0x1800171c4  jnz     short loc_1800171A3
0x1800171c6  mov     rax, r8
0x1800171c9  lea     rcx, [r9-2]
0x1800171cd  neg     rax
0x1800171d0  sbb     ebx, ebx
0x1800171d2  not     ebx
0x1800171d4  and     ebx, 80000005h
0x1800171da  test    r8, r8
0x1800171dd  cmovnz  rcx, r9
0x1800171e1  mov     [rcx], r12w
0x1800171e5  jz      loc_180017308
0x1800171eb  mov     rbx, cs:String1
0x1800171f2  movzx   eax, word ptr [rdx]
0x1800171f5  mov     [rsp+78h+String1], ax
0x1800171fa  test    rbx, rbx
0x1800171fd  jz      short loc_18001726E
0x1800171ff  lea     rax, [rsp+78h+String1]
0x180017204  inc     r14
0x180017207  cmp     [rax+r14*2], r12w
0x18001720c  jnz     short loc_180017204
0x18001720e  mov     r8, r14; MaxCount
0x180017211  lea     rcx, [rsp+78h+String1]; String1
0x180017216  mov     rdx, rbx; String2
0x180017219  call    _wcsnicmp_0
0x18001721e  test    eax, eax
0x180017220  jnz     short loc_180017250
0x180017222  mov     ebx, r12d
0x180017225  mov     [r15], ebp
0x180017228  mov     eax, ebx
0x18001722a  mov     rcx, [rsp+78h+var_38]
0x18001722f  xor     rcx, rsp; StackCookie
0x180017232  call    __security_check_cookie
0x180017237  lea     r11, [rsp+78h+var_28]
0x18001723c  mov     rbx, [r11+40h]
0x180017240  mov     rbp, [r11+48h]
0x180017244  mov     rsp, r11
0x180017247  pop     r15
0x180017249  pop     r14
0x18001724b  pop     r12
0x18001724d  pop     rdi
0x18001724e  pop     rsi
0x18001724f  retn
0x180017250  lea     rcx, [rsp+78h+String1]; lpRootPathName
0x180017255  call    GetDriveTypeW_0
0x18001725a  mov     ecx, eax
0x18001725c  add     eax, 0FFFFFFFEh
0x18001725f  test    eax, 0FFFFFFFCh
0x180017264  jnz     short loc_180017222
0x180017266  cmp     ecx, 3
0x180017269  cmovnz  ebp, edi
0x18001726c  jmp     short loc_180017222
0x18001726e  xor     edx, edx; hFile
0x180017270  lea     rcx, LibFileName; "ntdll.dll"
0x180017277  mov     r8d, 800h; dwFlags
0x18001727d  mov     ebx, 7FFE0030h
0x180017282  call    cs:__imp_LoadLibraryExW
0x180017288  mov     rsi, rax
0x18001728b  test    rax, rax
0x18001728e  jz      short loc_1800172B6
0x180017290  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180017297  mov     rcx, rax; hModule
0x18001729a  call    cs:__imp_GetProcAddress
0x1800172a0  test    rax, rax
0x1800172a3  jz      short loc_1800172AD
0x1800172a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172aa  mov     rbx, rax
0x1800172ad  mov     rcx, rsi; hLibModule
0x1800172b0  call    cs:__imp_FreeLibrary
0x1800172b6  mov     cs:String1, rbx
0x1800172bd  jmp     loc_1800171FF
0x1800172c2  mov     ebx, r12d
0x1800172c5  mov     r8d, 107h
0x1800172cb  mov     dword ptr [rsp+78h+var_50], r12d
0x1800172d0  lea     r9, aWsNotAFullPath; "%ws not a full path we can operate on ["...
0x1800172d7  mov     [rsp+78h+var_58], rdx
0x1800172dc  mov     ecx, 1
0x1800172e1  lea     rdx, aAslpathisonrem; "AslPathIsOnRemovableMedia"
0x1800172e8  call    AslLogCallPrintf
0x1800172ed  jmp     loc_180017225
0x1800172f2  cmp     word ptr [rdx+2], 5Ch ; '\'
0x1800172f7  mov     ebx, r12d
0x1800172fa  jz      loc_180017225
0x180017300  mov     r8d, 112h
0x180017306  jmp     short loc_1800172CB
0x180017308  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed for c:\\ [%x]"
0x18001730f  mov     dword ptr [rsp+78h+var_58], ebx
0x180017313  mov     r8d, 123h
0x180017319  lea     rdx, aAslpathisonrem; "AslPathIsOnRemovableMedia"
0x180017320  mov     ecx, edi
0x180017322  call    AslLogCallPrintf
0x180017327  jmp     loc_180017225
```

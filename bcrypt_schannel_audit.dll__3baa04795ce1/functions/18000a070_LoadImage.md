# _LoadImage

- ea: `0x18000a070`
- end: `0x18000a21c`
- name: `_LoadImage`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007d60`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000a070`
- `0x18000a3e8`
- `0x18001a9c8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000a0f1`
- `ntdll!RtlCompareUnicodeString` at `0x18000a0f1`
- `ntdll!RtlInitUnicodeString` at `0x18000a0b8`
- `ntdll!RtlInitUnicodeString` at `0x18000a0b8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a113`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1e0`

## string_xrefs

- `0x18000a190`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000a1f1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000a094`: `bcrypt.dll`

## pseudocode

```c
__int64 __fastcall LoadImage(__int64 a1, HMODULE *a2)
{
  PCWSTR *v3; // rdx
  int v4; // r14d
  int ImagePath; // eax
  int v6; // edx
  const WCHAR *v7; // rsi
  unsigned int v8; // ebx
  HMODULE Library; // rdx
  int v10; // r8d
  UNICODE_STRING String2; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpLibFileName; // [rsp+80h] [rbp+20h] BYREF

  *(_QWORD *)&String2.Length = 1441812;
  v3 = *(PCWSTR **)(a1 + 40);
  String2.Buffer = L"bcrypt.dll";
  v4 = a1;
  lpLibFileName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *v3);
  ImagePath = GetImagePath(&DestinationString, &lpLibFileName);
  v7 = lpLibFileName;
  v8 = ImagePath;
  if ( ImagePath < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        (unsigned int)"sResult",
        ImagePath,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        171);
  }
  else
  {
    *a2 = 0;
    if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
      *a2 = (HMODULE)g_hInstance;
    if ( *a2 )
      goto LABEL_9;
    Library = LoadLibraryExW(v7, 0, 0);
    *a2 = Library;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)Library, v10, v4, (__int64)v7, (char)Library);
    if ( *a2 )
    {
LABEL_9:
      v8 = 0;
    }
    else
    {
      v8 = -1073741515;
      if ( GetLastError() != 126 )
        v8 = -1073741701;
      DebugTraceError(v8, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
    }
  }
  if ( v7 )
    MSCryptFree(v7);
  return v8;
}

```

## disassembly

```asm
0x18000a070  mov     [rsp-18h+arg_8], rbx
0x18000a075  mov     [rsp-18h+arg_10], rsi
0x18000a07a  push    rbp
0x18000a07b  push    rdi
0x18000a07c  push    r14
0x18000a07e  mov     rbp, rsp
0x18000a081  sub     rsp, 60h
0x18000a085  mov     rdi, rdx
0x18000a088  mov     qword ptr [rbp+String2.Length], 160014h
0x18000a090  mov     rdx, [rcx+28h]
0x18000a094  lea     rax, aBcryptDll_0; "bcrypt.dll"
0x18000a09b  xorps   xmm0, xmm0
0x18000a09e  mov     [rbp+String2.Buffer], rax
0x18000a0a2  mov     r14, rcx
0x18000a0a5  mov     [rbp+lpLibFileName], 0
0x18000a0ad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a0b1  mov     rdx, [rdx]; SourceString
0x18000a0b4  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a0b8  call    cs:__imp_RtlInitUnicodeString
0x18000a0bf  nop     dword ptr [rax+rax+00h]
0x18000a0c4  lea     rdx, [rbp+lpLibFileName]
0x18000a0c8  lea     rcx, [rbp+DestinationString]
0x18000a0cc  call    _GetImagePath
0x18000a0d1  mov     rsi, [rbp+lpLibFileName]
0x18000a0d5  mov     ebx, eax
0x18000a0d7  test    eax, eax
0x18000a0d9  js      loc_18000A173
0x18000a0df  mov     r8b, 1; CaseInsensitive
0x18000a0e2  mov     qword ptr [rdi], 0
0x18000a0e9  lea     rdx, [rbp+String2]; String2
0x18000a0ed  lea     rcx, [rbp+DestinationString]; String1
0x18000a0f1  call    cs:__imp_RtlCompareUnicodeString
0x18000a0f8  nop     dword ptr [rax+rax+00h]
0x18000a0fd  test    eax, eax
0x18000a0ff  jz      loc_18000A1B6
0x18000a105  cmp     qword ptr [rdi], 0
0x18000a109  jnz     short loc_18000A14C
0x18000a10b  xor     r8d, r8d; dwFlags
0x18000a10e  xor     edx, edx; hFile
0x18000a110  mov     rcx, rsi; lpLibFileName
0x18000a113  call    cs:__imp_LoadLibraryExW
0x18000a11a  nop     dword ptr [rax+rax+00h]
0x18000a11f  mov     rdx, rax
0x18000a122  mov     [rdi], rax
0x18000a125  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a12c  lea     rax, WPP_GLOBAL_Control
0x18000a133  cmp     rcx, rax
0x18000a136  jz      short loc_18000A142
0x18000a138  test    byte ptr [rcx+1Ch], 20h
0x18000a13c  jnz     loc_18000A1C5
0x18000a142  cmp     qword ptr [rdi], 0
0x18000a146  jz      loc_18000A1E0
0x18000a14c  xor     ebx, ebx
0x18000a14e  test    rsi, rsi
0x18000a151  jz      short loc_18000A15B
0x18000a153  mov     rcx, rsi
0x18000a156  call    MSCryptFree
0x18000a15b  lea     r11, [rsp+60h+var_s0]
0x18000a160  mov     eax, ebx
0x18000a162  mov     rbx, [r11+28h]
0x18000a166  mov     rsi, [r11+30h]
0x18000a16a  mov     rsp, r11
0x18000a16d  pop     r14
0x18000a16f  pop     rdi
0x18000a170  pop     rbp
0x18000a171  retn
0x18000a173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a17a  lea     rax, WPP_GLOBAL_Control
0x18000a181  cmp     rcx, rax
0x18000a184  jz      short loc_18000A14E
0x18000a186  test    byte ptr [rcx+1Ch], 1
0x18000a18a  jz      short loc_18000A14E
0x18000a18c  mov     rcx, [rcx+10h]
0x18000a190  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a197  mov     [rsp+60h+var_30], 4ABh
0x18000a19f  lea     r9, aSresult; "sResult"
0x18000a1a6  mov     [rsp+60h+var_38], r8
0x18000a1ab  mov     dword ptr [rsp+60h+var_40], ebx
0x18000a1af  call    WPP_SF_sDsd
0x18000a1b4  jmp     short loc_18000A14E
0x18000a1b6  mov     rax, cs:g_hInstance
0x18000a1bd  mov     [rdi], rax
0x18000a1c0  jmp     loc_18000A105
0x18000a1c5  mov     rcx, [rcx+10h]
0x18000a1c9  mov     r9, r14
0x18000a1cc  mov     [rsp+60h+var_38], rdx
0x18000a1d1  mov     [rsp+60h+var_40], rsi
0x18000a1d6  call    WPP_SF_qSq
0x18000a1db  jmp     loc_18000A142
0x18000a1e0  call    cs:__imp_GetLastError
0x18000a1e7  nop     dword ptr [rax+rax+00h]
0x18000a1ec  mov     ecx, 0C000007Bh
0x18000a1f1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a1f8  cmp     eax, 7Eh ; '~'
0x18000a1fb  lea     rdx, aSresult; "sResult"
0x18000a202  mov     ebx, 0C0000135h
0x18000a207  mov     r9d, 4C8h
0x18000a20d  cmovnz  ebx, ecx
0x18000a210  mov     ecx, ebx
0x18000a212  call    DebugTraceError
0x18000a217  jmp     loc_18000A14E
```

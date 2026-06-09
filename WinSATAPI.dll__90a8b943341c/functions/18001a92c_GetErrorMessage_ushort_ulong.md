# GetErrorMessage<ushort>(ulong)

- ea: `0x18001a92c`
- end: `0x18001aa6f`
- name: `??$GetErrorMessage@G@@YAPEAGK@Z`
- size: `323`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001b068`

## callees

- `0x18000a0b0`
- `0x18000f0e8`
- `0x180011fc0`
- `0x18001a92c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001a986`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001a986`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aa49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aa49`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a9dc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a9dc`

## string_xrefs

- `0x18001a961`: `netmsg.dll`
- `0x18001a977`: `Wininet.dll`
- `0x18001a9fb`: `base\winsat\api-dll\logging.cpp`

## pseudocode

```c
WCHAR *__fastcall GetErrorMessage<unsigned short>(DWORD dwMessageId)
{
  HMODULE v2; // rbx
  const CHAR *v3; // rcx
  WCHAR *lpBuffer; // rsi
  signed int v5; // eax
  WCHAR *i; // r14
  HMODULE Library; // [rsp+78h] [rbp+10h]

  v2 = 0;
  Library = 0;
  if ( dwMessageId - 2100 > 0x383 )
  {
    if ( dwMessageId - 12000 > 0xC0 )
      goto LABEL_18;
    v3 = "Wininet.dll";
  }
  else
  {
    v3 = "netmsg.dll";
  }
  Library = LoadLibraryExA(v3, 0, 2u);
  v2 = Library;
LABEL_18:
  try
  {
    lpBuffer = (WCHAR *)operator new[](0x400u);
    v5 = FormatMessageW(v2 != 0 ? 6144 : 4096, v2, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
    if ( v5 )
    {
      for ( i = &lpBuffer[v5 - 1]; i >= lpBuffer && (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*i); --i )
        *i = 0;
    }
    else
    {
      Log_Text_F("base\\winsat\\api-dll\\logging.cpp", 196, "INFO: cannot find message for Win32 error %u", dwMessageId);
      *lpBuffer = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\api-dll\\logging.cpp", 206, "INFO: cannot allocate memory for error string");
    v2 = Library;
    lpBuffer = (WCHAR *)&String2;
  }
  if ( v2 )
    FreeLibrary(v2);
  return lpBuffer;
}

```

## disassembly

```asm
0x18001a92c  mov     rax, rsp
0x18001a92f  push    rdi
0x18001a930  push    r14
0x18001a932  push    r15
0x18001a934  sub     rsp, 50h
0x18001a938  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001a940  mov     [rax+8], rbx
0x18001a944  mov     [rax+20h], rsi
0x18001a948  mov     r14d, ecx
0x18001a94b  xor     edi, edi
0x18001a94d  mov     ebx, edi
0x18001a94f  mov     [rsp+68h+arg_8], rbx
0x18001a954  lea     eax, [rcx-834h]
0x18001a95a  cmp     eax, 383h
0x18001a95f  ja      short loc_18001A96A
0x18001a961  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18001a968  jmp     short loc_18001A97E
0x18001a96a  lea     eax, [rcx-2EE0h]
0x18001a970  cmp     eax, 0C0h
0x18001a975  ja      short loc_18001A99A
0x18001a977  lea     rcx, aWininetDll; "Wininet.dll"
0x18001a97e  mov     r8d, 2; dwFlags
0x18001a984  xor     edx, edx; hFile
0x18001a986  call    cs:__imp_LoadLibraryExA
0x18001a98d  nop     dword ptr [rax+rax+00h]
0x18001a992  mov     [rsp+68h+arg_8], rax
0x18001a997  mov     rbx, rax
0x18001a99a  mov     rax, rbx
0x18001a99d  neg     rax
0x18001a9a0  sbb     r15d, r15d
0x18001a9a3  and     r15d, 800h
0x18001a9aa  mov     ecx, 400h; unsigned __int64
0x18001a9af  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a9b4  mov     rsi, rax
0x18001a9b7  mov     [rsp+68h+Arguments], rdi; Arguments
0x18001a9bc  mov     [rsp+68h+nSize], 200h; nSize
0x18001a9c4  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18001a9c9  mov     r9d, 400h; dwLanguageId
0x18001a9cf  mov     r8d, r14d; dwMessageId
0x18001a9d2  mov     rdx, rbx; lpSource
0x18001a9d5  lea     ecx, [r15+1000h]; dwFlags
0x18001a9dc  call    cs:__imp_FormatMessageW
0x18001a9e3  nop     dword ptr [rax+rax+00h]
0x18001a9e8  test    eax, eax
0x18001a9ea  jnz     short loc_18001AA0C
0x18001a9ec  mov     r9d, r14d
0x18001a9ef  lea     r8, aInfoCannotFind; "INFO: cannot find message for Win32 err"...
0x18001a9f6  mov     edx, 0C4h
0x18001a9fb  lea     rcx, aBaseWinsatApiD_0; "base\\winsat\\api-dll\\logging.cpp"
0x18001aa02  call    Log_Text_F
0x18001aa07  mov     [rsi], di
0x18001aa0a  jmp     short loc_18001AA32
0x18001aa0c  movsxd  r14, eax
0x18001aa0f  dec     r14
0x18001aa12  lea     r14, [rsi+r14*2]
0x18001aa16  jmp     short loc_18001AA2D
0x18001aa18  movzx   ecx, word ptr [r14]
0x18001aa1c  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001aa21  test    al, al
0x18001aa23  jz      short loc_18001AA32
0x18001aa25  mov     [r14], di
0x18001aa29  sub     r14, 2
0x18001aa2d  cmp     r14, rsi
0x18001aa30  jnb     short loc_18001AA18
0x18001aa32  jmp     short loc_18001AA41
0x18001aa34  mov     rbx, [rsp+68h+arg_8]
0x18001aa39  mov     rsi, [rsp+68h+arg_10]
0x18001aa41  test    rbx, rbx
0x18001aa44  jz      short loc_18001AA55
0x18001aa46  mov     rcx, rbx; hLibModule
0x18001aa49  call    cs:__imp_FreeLibrary
0x18001aa50  nop     dword ptr [rax+rax+00h]
0x18001aa55  mov     rax, rsi
0x18001aa58  lea     r11, [rsp+68h+var_18]
0x18001aa5d  mov     rbx, [r11+20h]
0x18001aa61  mov     rsi, [r11+38h]
0x18001aa65  mov     rsp, r11
0x18001aa68  pop     r15
0x18001aa6a  pop     r14
0x18001aa6c  pop     rdi
0x18001aa6d  retn
```

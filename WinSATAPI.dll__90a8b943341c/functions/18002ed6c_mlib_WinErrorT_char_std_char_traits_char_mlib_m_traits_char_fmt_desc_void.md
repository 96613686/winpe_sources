# mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)

- ea: `0x18002ed6c`
- end: `0x18002ee8a`
- name: `?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ`
- size: `286`
- prototype: `__int64 __fastcall(LPSTR lpBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020fa0`
- `0x180021d84`

## callees

- `0x18001b318`
- `0x18002ed6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ed97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ede7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ed97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ede7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ee66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ee66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18002ee29`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18002ee29`

## string_xrefs

- `0x18002edc2`: `netmsg.dll`
- `0x18002edd8`: `Wininet.dll`

## pseudocode

```c
__int64 __fastcall mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(_QWORD *lpBuffer)
{
  HMODULE v2; // rbp
  const CHAR *v3; // rcx
  HMODULE Library; // rax
  DWORD *v5; // rsi
  int v6; // ecx
  const CHAR *v7; // rcx
  DWORD v8; // eax
  __int64 v9; // rcx
  CHAR *i; // rdi

  v2 = 0;
  v3 = (const CHAR *)lpBuffer[33];
  if ( v3 )
  {
    Library = LoadLibraryExA(v3, 0, 2u);
    v5 = (DWORD *)(lpBuffer + 32);
  }
  else
  {
    v5 = (DWORD *)(lpBuffer + 32);
    v6 = *((_DWORD *)lpBuffer + 64);
    if ( (unsigned int)(v6 - 2100) > 0x383 )
    {
      if ( (unsigned int)(v6 - 12000) > 0xC0 )
        goto LABEL_9;
      v7 = "Wininet.dll";
    }
    else
    {
      v7 = "netmsg.dll";
    }
    Library = LoadLibraryExA(v7, 0, 2u);
  }
  v2 = Library;
LABEL_9:
  v8 = FormatMessageA(v2 != 0 ? 6144 : 4096, v2, *v5, 0x400u, (LPSTR)lpBuffer, 0x100u, 0);
  if ( v8 )
  {
    for ( i = (char *)lpBuffer + (int)v8 - 1; i >= (CHAR *)lpBuffer; --i )
    {
      LOBYTE(v9) = *i;
      if ( !(unsigned __int8)mlib::m_traits<char>::isSpace(v9) )
        break;
      *i = 0;
    }
  }
  else
  {
    *(_BYTE *)lpBuffer = 0;
  }
  if ( v2 )
    FreeLibrary(v2);
  return *v5;
}

```

## disassembly

```asm
0x18002ed6c  mov     [rsp+arg_0], rbx
0x18002ed71  mov     [rsp+arg_8], rbp
0x18002ed76  mov     [rsp+arg_10], rsi
0x18002ed7b  push    rdi
0x18002ed7c  sub     rsp, 40h
0x18002ed80  mov     rbx, rcx
0x18002ed83  xor     ebp, ebp
0x18002ed85  mov     rcx, [rcx+108h]; lpLibFileName
0x18002ed8c  test    rcx, rcx
0x18002ed8f  jz      short loc_18002EDAC
0x18002ed91  xor     edx, edx; hFile
0x18002ed93  lea     r8d, [rbp+2]; dwFlags
0x18002ed97  call    cs:__imp_LoadLibraryExA
0x18002ed9e  nop     dword ptr [rax+rax+00h]
0x18002eda3  lea     rsi, [rbx+100h]
0x18002edaa  jmp     short loc_18002EDF3
0x18002edac  lea     rsi, [rbx+100h]
0x18002edb3  mov     ecx, [rsi]
0x18002edb5  lea     eax, [rcx-834h]
0x18002edbb  cmp     eax, 383h
0x18002edc0  ja      short loc_18002EDCB
0x18002edc2  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18002edc9  jmp     short loc_18002EDDF
0x18002edcb  lea     eax, [rcx-2EE0h]
0x18002edd1  cmp     eax, 0C0h
0x18002edd6  ja      short loc_18002EDF6
0x18002edd8  lea     rcx, aWininetDll; "Wininet.dll"
0x18002eddf  mov     r8d, 2; dwFlags
0x18002ede5  xor     edx, edx; hFile
0x18002ede7  call    cs:__imp_LoadLibraryExA
0x18002edee  nop     dword ptr [rax+rax+00h]
0x18002edf3  mov     rbp, rax
0x18002edf6  mov     r8d, [rsi]; dwMessageId
0x18002edf9  mov     rax, rbp
0x18002edfc  neg     rax
0x18002edff  mov     r9d, 400h; dwLanguageId
0x18002ee05  mov     rdx, rbp; lpSource
0x18002ee08  sbb     ecx, ecx
0x18002ee0a  and     [rsp+48h+var_18], 0
0x18002ee10  and     ecx, 800h
0x18002ee16  mov     [rsp+48h+nSize], 100h; nSize
0x18002ee1e  add     ecx, 1000h; dwFlags
0x18002ee24  mov     [rsp+48h+lpBuffer], rbx; lpBuffer
0x18002ee29  call    cs:__imp_FormatMessageA
0x18002ee30  nop     dword ptr [rax+rax+00h]
0x18002ee35  test    eax, eax
0x18002ee37  jnz     short loc_18002EE3D
0x18002ee39  mov     [rbx], al
0x18002ee3b  jmp     short loc_18002EE5E
0x18002ee3d  movsxd  rdi, eax
0x18002ee40  dec     rdi
0x18002ee43  add     rdi, rbx
0x18002ee46  jmp     short loc_18002EE59
0x18002ee48  mov     cl, [rdi]
0x18002ee4a  call    ?isSpace@?$m_traits@D@mlib@@SA_ND@Z; mlib::m_traits<char>::isSpace(char)
0x18002ee4f  test    al, al
0x18002ee51  jz      short loc_18002EE5E
0x18002ee53  mov     byte ptr [rdi], 0
0x18002ee56  dec     rdi
0x18002ee59  cmp     rdi, rbx
0x18002ee5c  jnb     short loc_18002EE48
0x18002ee5e  test    rbp, rbp
0x18002ee61  jz      short loc_18002EE72
0x18002ee63  mov     rcx, rbp; hLibModule
0x18002ee66  call    cs:__imp_FreeLibrary
0x18002ee6d  nop     dword ptr [rax+rax+00h]
0x18002ee72  mov     eax, [rsi]
0x18002ee74  mov     rsi, [rsp+48h+arg_10]
0x18002ee79  mov     rbx, [rsp+48h+arg_0]
0x18002ee7e  mov     rbp, [rsp+48h+arg_8]
0x18002ee83  add     rsp, 40h
0x18002ee87  pop     rdi
0x18002ee88  retn
```

# DeleteCacheEntry

- ea: `0x140074084`
- end: `0x140074228`
- name: `DeleteCacheEntry`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400513e4`
- `0x140083acc`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140074084`
- `0x1400745e4`
- `0x140074f18`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400741fc`
- `ADVAPI32!RegCloseKey` at `0x1400741fc`
- `KERNEL32!GetLastError` at `0x1400740fc`
- `KERNEL32!GetLastError` at `0x1400741bb`
- `KERNEL32!GetLastError` at `0x1400740fc`
- `KERNEL32!GetLastError` at `0x1400741bb`

## string_xrefs

- `0x1400740de`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall DeleteCacheEntry(unsigned int a1)
{
  HKEY v2; // rdi
  DWORD v3; // ebx
  int v4; // eax
  DWORD LastError; // eax
  unsigned __int16 v7[12]; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Devices Cache", 0, 0x2001Fu);
  if ( v2 )
  {
    v4 = StringCchPrintfW(v7, 0xAu, L"%08lx", a1);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v3 = 0;
      if ( !(unsigned int)DeleteRegistryKey(v2, v7) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, LastError);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids,
          (unsigned int)v4);
      }
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        v3 = (unsigned __int16)v3;
    }
    RegCloseKey(v2);
  }
  else
  {
    v3 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140074084  mov     [rsp+arg_8], rbx
0x140074089  mov     [rsp+arg_10], rbp
0x14007408e  push    rdi
0x14007408f  sub     rsp, 40h
0x140074093  mov     rax, cs:__security_cookie
0x14007409a  xor     rax, rsp
0x14007409d  mov     [rsp+48h+var_10], rax
0x1400740a2  mov     ebx, ecx
0x1400740a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740ab  lea     rbp, WPP_GLOBAL_Control
0x1400740b2  cmp     rcx, rbp
0x1400740b5  jz      short loc_1400740D8
0x1400740b7  test    byte ptr [rcx+1Ch], 2
0x1400740bb  jz      short loc_1400740D8
0x1400740bd  cmp     byte ptr [rcx+19h], 5
0x1400740c1  jb      short loc_1400740D8
0x1400740c3  mov     rcx, [rcx+10h]
0x1400740c7  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400740ce  mov     edx, 1Bh
0x1400740d3  call    WPP_SF_
0x1400740d8  mov     r9d, 2001Fh
0x1400740de  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x1400740e5  xor     r8d, r8d
0x1400740e8  mov     rcx, 0FFFFFFFF80000002h
0x1400740ef  call    OpenRegistryKey
0x1400740f4  mov     rdi, rax
0x1400740f7  test    rax, rax
0x1400740fa  jnz     short loc_140074146
0x1400740fc  call    cs:__imp_GetLastError
0x140074103  nop     dword ptr [rax+rax+00h]
0x140074108  mov     ebx, eax
0x14007410a  mov     rcx, cs:WPP_GLOBAL_Control
0x140074111  cmp     rcx, rbp
0x140074114  jz      loc_140074208
0x14007411a  test    byte ptr [rcx+1Ch], 2
0x14007411e  jz      loc_140074208
0x140074124  cmp     byte ptr [rcx+19h], 2
0x140074128  jb      loc_140074208
0x14007412e  mov     rcx, [rcx+10h]
0x140074132  lea     edx, [rdi+1Ch]
0x140074135  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14007413c  call    WPP_SF_
0x140074141  jmp     loc_140074208
0x140074146  mov     r9d, ebx
0x140074149  lea     r8, a08lx; "%08lx"
0x140074150  mov     edx, 0Ah; unsigned __int64
0x140074155  lea     rcx, [rsp+48h+var_28]; unsigned __int16 *
0x14007415a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007415f  mov     ebx, eax
0x140074161  test    eax, eax
0x140074163  jns     short loc_1400741A8
0x140074165  mov     rcx, cs:WPP_GLOBAL_Control
0x14007416c  cmp     rcx, rbp
0x14007416f  jz      short loc_140074195
0x140074171  test    byte ptr [rcx+1Ch], 2
0x140074175  jz      short loc_140074195
0x140074177  cmp     byte ptr [rcx+19h], 2
0x14007417b  jb      short loc_140074195
0x14007417d  mov     rcx, [rcx+10h]
0x140074181  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x140074188  mov     edx, 1Dh
0x14007418d  mov     r9d, eax
0x140074190  call    WPP_SF_d
0x140074195  mov     eax, ebx
0x140074197  and     eax, 1FFF0000h
0x14007419c  cmp     eax, 70000h
0x1400741a1  jnz     short loc_1400741F9
0x1400741a3  movzx   ebx, bx
0x1400741a6  jmp     short loc_1400741F9
0x1400741a8  lea     rdx, [rsp+48h+var_28]
0x1400741ad  mov     rcx, rdi
0x1400741b0  xor     ebx, ebx
0x1400741b2  call    DeleteRegistryKey
0x1400741b7  test    eax, eax
0x1400741b9  jnz     short loc_1400741F9
0x1400741bb  call    cs:__imp_GetLastError
0x1400741c2  nop     dword ptr [rax+rax+00h]
0x1400741c7  mov     ebx, eax
0x1400741c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400741d0  cmp     rcx, rbp
0x1400741d3  jz      short loc_1400741F9
0x1400741d5  test    byte ptr [rcx+1Ch], 2
0x1400741d9  jz      short loc_1400741F9
0x1400741db  cmp     byte ptr [rcx+19h], 2
0x1400741df  jb      short loc_1400741F9
0x1400741e1  mov     rcx, [rcx+10h]
0x1400741e5  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x1400741ec  mov     edx, 1Eh
0x1400741f1  mov     r9d, eax
0x1400741f4  call    WPP_SF_d
0x1400741f9  mov     rcx, rdi; hKey
0x1400741fc  call    cs:__imp_RegCloseKey
0x140074203  nop     dword ptr [rax+rax+00h]
0x140074208  mov     eax, ebx
0x14007420a  mov     rcx, [rsp+48h+var_10]
0x14007420f  xor     rcx, rsp; StackCookie
0x140074212  call    __security_check_cookie
0x140074217  mov     rbx, [rsp+48h+arg_8]
0x14007421c  mov     rbp, [rsp+48h+arg_10]
0x140074221  add     rsp, 40h
0x140074225  pop     rdi
0x140074226  retn
```

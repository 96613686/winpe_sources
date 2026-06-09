# HinstLoadWWLibDarwin(wchar_t const *)

- ea: `0x140004244`
- end: `0x140004474`
- name: `?HinstLoadWWLibDarwin@@YAPEAUHINSTANCE__@@PEB_W@Z`
- size: `560`
- prototype: `HINSTANCE __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400011a0`

## callees

- `0x140001000`
- `0x140001020`
- `0x140001e08`
- `0x140004244`
- `0x140004474`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140004288`
- `KERNEL32!GetSystemDirectoryW` at `0x140004288`
- `KERNEL32!GetProcAddress` at `0x140004339`
- `KERNEL32!GetProcAddress` at `0x14000434c`
- `KERNEL32!GetProcAddress` at `0x140004339`
- `KERNEL32!GetProcAddress` at `0x14000434c`
- `KERNEL32!FreeLibrary` at `0x14000442f`
- `KERNEL32!FreeLibrary` at `0x140004443`
- `KERNEL32!FreeLibrary` at `0x14000442f`
- `KERNEL32!FreeLibrary` at `0x140004443`
- `KERNEL32!LoadLibraryExW` at `0x14000431d`
- `KERNEL32!LoadLibraryExW` at `0x14000431d`
- `api-ms-win-crt-string-l1-1-0!wcsncat_s` at `0x1400042ed`
- `api-ms-win-crt-string-l1-1-0!wcsncat_s` at `0x1400042ed`

## string_xrefs

- `0x1400043af`: `wwlib.dll`
- `0x1400043fe`: `wwlib.dll`
- `0x1400042d9`: `msi.dll`
- `0x140004316`: `msi.dll`
- `0x14000432f`: `MsiGetProductCodeW`
- `0x140004342`: `MsiProvideQualifiedComponentExW`

## pseudocode

```c
HINSTANCE __fastcall HinstLoadWWLibDarwin(const wchar_t *a1)
{
  UINT SystemDirectoryW; // eax
  const wchar_t *v2; // rdx
  unsigned int v3; // r9d
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rbx
  FARPROC v6; // rsi
  int v7; // eax
  const wchar_t *v8; // rdx
  unsigned int v9; // r9d
  HINSTANCE v10; // rbx
  _DWORD v12[4]; // [rsp+50h] [rbp-498h] BYREF
  _BYTE v13[80]; // [rsp+60h] [rbp-488h] BYREF
  wchar_t Buffer[264]; // [rsp+B0h] [rbp-438h] BYREF
  _WORD v15[264]; // [rsp+2C0h] [rbp-228h] BYREF

  v12[0] = 0;
  v15[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( SystemDirectoryW - 1 <= 0x103 )
  {
    if ( Buffer[SystemDirectoryW] != 92 )
    {
      Buffer[SystemDirectoryW] = 92;
      if ( 2 * (unsigned __int64)(SystemDirectoryW + 1) >= 0x20C )
        _report_rangecheckfailure();
      Buffer[SystemDirectoryW + 1] = 0;
    }
    wcsncat_s(Buffer, 0x106u, L"msi.dll", 0xFFFFFFFFFFFFFFFFuLL);
    Library = Mso::SafeLoadLibrary((Mso *)Buffer, v2, (void *)8, v3);
    if ( Library || (Library = LoadLibraryExW(L"msi.dll", 0, 0x1000u)) != 0 )
    {
      ProcAddress = GetProcAddress(Library, "MsiGetProductCodeW");
      v6 = GetProcAddress(Library, "MsiProvideQualifiedComponentExW");
      if ( v6 && ProcAddress )
      {
        if ( (v7 = ((__int64 (__fastcall *)(const wchar_t *, _BYTE *))ProcAddress)(
                     L"{DC5CCACD-A7AC-4FD3-9F70-9454B5DE5161}",
                     v13)) == 0
          && (v12[0] = 260,
              (v7 = ((__int64 (__fastcall *)(const wchar_t *, const WCHAR *, _QWORD, _BYTE *, _DWORD, _DWORD, _WORD *, _DWORD *))v6)(
                      L"{5812C571-53F0-4467-BEFA-0A4F47A9437C}",
                      L"wwlib.dll",
                      0,
                      v13,
                      0,
                      0,
                      v15,
                      v12)) == 0)
          || v7 == 1602
          || (v12[0] = 260,
              !((unsigned int (__fastcall *)(const wchar_t *, const WCHAR *, _QWORD, _QWORD, _DWORD, _DWORD, _WORD *, _DWORD *))v6)(
                 L"{5812C571-53F0-4467-BEFA-0A4F47A9437C}",
                 L"wwlib.dll",
                 0,
                 0,
                 0,
                 0,
                 v15,
                 v12)) )
        {
          v10 = Mso::SafeLoadLibrary((Mso *)v15, v8, 0, v9);
          FreeLibrary(Library);
          return v10;
        }
      }
      FreeLibrary(Library);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004244  mov     [rsp+arg_0], rbx
0x140004249  mov     [rsp+arg_8], rbp
0x14000424e  mov     [rsp+arg_10], rsi
0x140004253  push    rdi
0x140004254  sub     rsp, 4E0h
0x14000425b  mov     rax, cs:__security_cookie
0x140004262  xor     rax, rsp
0x140004265  mov     [rsp+4E8h+var_18], rax
0x14000426d  xor     ebp, ebp
0x14000426f  mov     [rsp+4E8h+var_498], ebp
0x140004273  mov     [rsp+4E8h+var_228], bp
0x14000427b  mov     edx, 105h; uSize
0x140004280  lea     rcx, [rsp+4E8h+Buffer]; lpBuffer
0x140004288  call    cs:__imp_GetSystemDirectoryW
0x14000428e  lea     ecx, [rax-1]
0x140004291  cmp     ecx, 103h
0x140004297  ja      loc_140004449
0x14000429d  mov     ecx, eax
0x14000429f  cmp     [rsp+rcx*2+4E8h+Buffer], 5Ch ; '\'
0x1400042a8  jz      short loc_1400042D2
0x1400042aa  mov     edx, 5Ch ; '\'
0x1400042af  mov     [rsp+rcx*2+4E8h+Buffer], dx
0x1400042b7  lea     ecx, [rax+1]
0x1400042ba  add     rcx, rcx
0x1400042bd  cmp     rcx, 20Ch
0x1400042c4  jnb     loc_14000443A
0x1400042ca  mov     [rsp+rcx+4E8h+Buffer], bp
0x1400042d2  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400042d9  lea     r8, aMsiDll; "msi.dll"
0x1400042e0  mov     edx, 106h; SizeInWords
0x1400042e5  lea     rcx, [rsp+4E8h+Buffer]; Destination
0x1400042ed  call    cs:__imp_wcsncat_s
0x1400042f3  mov     r8d, 8; void *
0x1400042f9  lea     rcx, [rsp+4E8h+Buffer]; this
0x140004301  call    ?SafeLoadLibrary@Mso@@YAPEAUHINSTANCE__@@PEB_WPEAXK@Z; Mso::SafeLoadLibrary(wchar_t const *,void *,ulong)
0x140004306  mov     rdi, rax
0x140004309  test    rax, rax
0x14000430c  jnz     short loc_14000432F
0x14000430e  xor     edx, edx; hFile
0x140004310  mov     r8d, 1000h; dwFlags
0x140004316  lea     rcx, aMsiDll; "msi.dll"
0x14000431d  call    cs:__imp_LoadLibraryExW
0x140004323  mov     rdi, rax
0x140004326  test    rax, rax
0x140004329  jz      loc_140004449
0x14000432f  lea     rdx, aMsigetproductc; "MsiGetProductCodeW"
0x140004336  mov     rcx, rdi; hModule
0x140004339  call    cs:__imp_GetProcAddress
0x14000433f  mov     rbx, rax
0x140004342  lea     rdx, aMsiprovidequal; "MsiProvideQualifiedComponentExW"
0x140004349  mov     rcx, rdi; hModule
0x14000434c  call    cs:__imp_GetProcAddress
0x140004352  mov     rsi, rax
0x140004355  test    rax, rax
0x140004358  jz      loc_140004440
0x14000435e  test    rbx, rbx
0x140004361  jz      loc_140004440
0x140004367  lea     rdx, [rsp+4E8h+var_488]
0x14000436c  lea     rcx, aDc5ccacdA7ac4f; "{DC5CCACD-A7AC-4FD3-9F70-9454B5DE5161}"
0x140004373  mov     rax, rbx
0x140004376  call    cs:__guard_dispatch_icall_fptr
0x14000437c  test    eax, eax
0x14000437e  jnz     short loc_1400043CA
0x140004380  mov     [rsp+4E8h+var_498], 104h
0x140004388  lea     rax, [rsp+4E8h+var_498]
0x14000438d  mov     [rsp+4E8h+var_4B0], rax
0x140004392  lea     rax, [rsp+4E8h+var_228]
0x14000439a  mov     [rsp+4E8h+var_4B8], rax
0x14000439f  mov     [rsp+4E8h+var_4C0], ebp
0x1400043a3  mov     [rsp+4E8h+var_4C8], ebp
0x1400043a7  lea     r9, [rsp+4E8h+var_488]
0x1400043ac  xor     r8d, r8d
0x1400043af  lea     rdx, LibFileName; "wwlib.dll"
0x1400043b6  lea     rcx, a5812c57153f044; "{5812C571-53F0-4467-BEFA-0A4F47A9437C}"
0x1400043bd  mov     rax, rsi
0x1400043c0  call    cs:__guard_dispatch_icall_fptr
0x1400043c6  test    eax, eax
0x1400043c8  jz      short loc_140004419
0x1400043ca  cmp     eax, 642h
0x1400043cf  jz      short loc_140004419
0x1400043d1  mov     [rsp+4E8h+var_498], 104h
0x1400043d9  lea     rax, [rsp+4E8h+var_498]
0x1400043de  mov     [rsp+4E8h+var_4B0], rax
0x1400043e3  lea     rax, [rsp+4E8h+var_228]
0x1400043eb  mov     [rsp+4E8h+var_4B8], rax
0x1400043f0  mov     [rsp+4E8h+var_4C0], ebp
0x1400043f4  mov     [rsp+4E8h+var_4C8], ebp
0x1400043f8  xor     r9d, r9d
0x1400043fb  xor     r8d, r8d
0x1400043fe  lea     rdx, LibFileName; "wwlib.dll"
0x140004405  lea     rcx, a5812c57153f044; "{5812C571-53F0-4467-BEFA-0A4F47A9437C}"
0x14000440c  mov     rax, rsi
0x14000440f  call    cs:__guard_dispatch_icall_fptr
0x140004415  test    eax, eax
0x140004417  jnz     short loc_140004440
0x140004419  xor     r8d, r8d; void *
0x14000441c  lea     rcx, [rsp+4E8h+var_228]; this
0x140004424  call    ?SafeLoadLibrary@Mso@@YAPEAUHINSTANCE__@@PEB_WPEAXK@Z; Mso::SafeLoadLibrary(wchar_t const *,void *,ulong)
0x140004429  mov     rbx, rax
0x14000442c  mov     rcx, rdi; hLibModule
0x14000442f  call    cs:__imp_FreeLibrary
0x140004435  mov     rax, rbx
0x140004438  jmp     short loc_14000444B
0x14000443a  call    __report_rangecheckfailure
0x140004440  mov     rcx, rdi; hLibModule
0x140004443  call    cs:__imp_FreeLibrary
0x140004449  xor     eax, eax
0x14000444b  mov     rcx, [rsp+4E8h+var_18]
0x140004453  xor     rcx, rsp; StackCookie
0x140004456  call    __security_check_cookie
0x14000445b  lea     r11, [rsp+4E8h+var_8]
0x140004463  mov     rbx, [r11+10h]
0x140004467  mov     rbp, [r11+18h]
0x14000446b  mov     rsi, [r11+20h]
0x14000446f  mov     rsp, r11
0x140004472  pop     rdi
0x140004473  retn
```

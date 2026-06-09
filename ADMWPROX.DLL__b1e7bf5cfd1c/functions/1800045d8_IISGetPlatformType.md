# IISGetPlatformType

- ea: `0x1800045d8`
- end: `0x1800046c9`
- name: `IISGetPlatformType`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002400`

## callees

- `0x1800045d8`
- `0x1800083de`
- `0x180008410`
- `0x180009010`

## import_xrefs

- `KERNEL32!GetVersionExA` at `0x180004629`
- `KERNEL32!GetVersionExA` at `0x180004629`
- `KERNEL32!LoadLibraryA` at `0x180004656`
- `KERNEL32!LoadLibraryA` at `0x180004656`
- `KERNEL32!GetProcAddress` at `0x18000466e`
- `KERNEL32!GetProcAddress` at `0x18000466e`
- `KERNEL32!FreeLibrary` at `0x180004696`
- `KERNEL32!FreeLibrary` at `0x180004696`

## string_xrefs

- `0x180004642`: `ntdll.dll`

## pseudocode

```c
__int64 IISGetPlatformType()
{
  __int64 result; // rax
  unsigned int v1; // ebx
  HMODULE LibraryA; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  _DWORD v5[4]; // [rsp+20h] [rbp-C8h] BYREF
  struct _OSVERSIONINFOA VersionInformation; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x90u);
  result = (unsigned int)g_PlatformType;
  if ( !g_PlatformType )
  {
    VersionInformation.dwOSVersionInfoSize = 148;
    if ( !GetVersionExA(&VersionInformation) || VersionInformation.dwPlatformId == 2 )
    {
      v5[0] = 0;
      v1 = 1;
      LibraryA = LoadLibraryA("ntdll.dll");
      v3 = LibraryA;
      if ( LibraryA )
      {
        ProcAddress = GetProcAddress(LibraryA, "RtlGetNtProductType");
        if ( ProcAddress
          && ((unsigned __int8 (__fastcall *)(_DWORD *))ProcAddress)(v5)
          && (unsigned int)(v5[0] - 2) <= 1 )
        {
          v1 = 2;
        }
        FreeLibrary(v3);
      }
    }
    else
    {
      v1 = 0;
    }
    g_PlatformType = v1;
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800045d8  mov     [rsp+arg_0], rbx
0x1800045dd  mov     [rsp+arg_8], rsi
0x1800045e2  push    rdi
0x1800045e3  sub     rsp, 0E0h
0x1800045ea  mov     rax, cs:__security_cookie
0x1800045f1  xor     rax, rsp
0x1800045f4  mov     [rsp+0E8h+var_18], rax
0x1800045fc  xor     edx, edx; Val
0x1800045fe  lea     rcx, [rsp+0E8h+VersionInformation.dwMajorVersion]; void *
0x180004603  mov     r8d, 90h; Size
0x180004609  call    memset_0
0x18000460e  mov     eax, cs:g_PlatformType
0x180004614  test    eax, eax
0x180004616  jnz     loc_1800046A4
0x18000461c  lea     rcx, [rsp+0E8h+VersionInformation]; lpVersionInformation
0x180004621  mov     [rsp+0E8h+VersionInformation.dwOSVersionInfoSize], 94h
0x180004629  call    cs:__imp_GetVersionExA
0x18000462f  mov     esi, 2
0x180004634  test    eax, eax
0x180004636  jz      short loc_180004642
0x180004638  cmp     [rsp+0E8h+VersionInformation.dwPlatformId], esi
0x18000463c  jz      short loc_180004642
0x18000463e  xor     ebx, ebx
0x180004640  jmp     short loc_18000469C
0x180004642  lea     rcx, LibFileName; "ntdll.dll"
0x180004649  mov     [rsp+0E8h+var_C8], 0
0x180004651  mov     ebx, 1
0x180004656  call    cs:__imp_LoadLibraryA
0x18000465c  mov     rdi, rax
0x18000465f  test    rax, rax
0x180004662  jz      short loc_18000469C
0x180004664  lea     rdx, ProcName; "RtlGetNtProductType"
0x18000466b  mov     rcx, rax; hModule
0x18000466e  call    cs:__imp_GetProcAddress
0x180004674  test    rax, rax
0x180004677  jz      short loc_180004693
0x180004679  lea     rcx, [rsp+0E8h+var_C8]
0x18000467e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004683  test    al, al
0x180004685  jz      short loc_180004693
0x180004687  mov     ecx, [rsp+0E8h+var_C8]
0x18000468b  add     ecx, 0FFFFFFFEh
0x18000468e  cmp     ecx, ebx
0x180004690  cmovbe  ebx, esi
0x180004693  mov     rcx, rdi; hLibModule
0x180004696  call    cs:__imp_FreeLibrary
0x18000469c  mov     cs:g_PlatformType, ebx
0x1800046a2  mov     eax, ebx
0x1800046a4  mov     rcx, [rsp+0E8h+var_18]
0x1800046ac  xor     rcx, rsp; StackCookie
0x1800046af  call    __security_check_cookie
0x1800046b4  lea     r11, [rsp+0E8h+var_8]
0x1800046bc  mov     rbx, [r11+10h]
0x1800046c0  mov     rsi, [r11+18h]
0x1800046c4  mov     rsp, r11
0x1800046c7  pop     rdi
0x1800046c8  retn
```

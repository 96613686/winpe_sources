# GetDateWindow(ulong,tagDATEINFO *,ulong)

- ea: `0x18002cdbc`
- end: `0x18002cf4f`
- name: `?GetDateWindow@@YAJKPEAUtagDATEINFO@@K@Z`
- size: `403`
- prototype: `__int64 __fastcall(unsigned int, struct tagDATEINFO *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bddc`

## callees

- `0x180005790`
- `0x18002cdbc`
- `0x18004d900`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18002ced4`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18002ced4`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18002cf1b`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18002cf1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ce0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ce0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ce1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ce1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002cefb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002cefb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002ceb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002ceb4`

## string_xrefs

- `0x18002ce03`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall GetDateWindow(unsigned int a1, struct tagDATEINFO *a2, int a3)
{
  unsigned int v3; // edi
  bool v4; // zf
  HMODULE ModuleHandleW; // rax
  __int16 v9; // si
  unsigned int v10; // eax
  DWORD Type; // [rsp+40h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-30h] BYREF
  CHAR ValueName[16]; // [rsp+60h] [rbp-20h] BYREF

  v3 = 0;
  hKey = 0;
  v4 = dword_1800C291C == 0;
  *((_WORD *)a2 + 1168) = 2029;
  if ( !v4 )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    _InterlockedExchange64(
      (volatile __int64 *)&qword_1800C3600,
      (__int64)GetProcAddress(ModuleHandleW, "GetCalendarInfoW"));
    dword_1800C291C = 0;
  }
  v9 = 1;
  if ( (unsigned int)IsThai(a1) )
    v9 = *((_WORD *)a2 + 1171);
  if ( qword_1800C3600 )
  {
    Type = 0;
    if ( (int)qword_1800C3600(a1, (unsigned int)v9, a3 & 0x5FFFFFCF | 0x20000030u, 0, 0, &Type) > 0 )
    {
      LOWORD(v10) = Type;
      if ( Type < 0x2710 )
        goto LABEL_12;
    }
  }
  if ( !RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\International\\Calendars\\TwoDigitYearMax", 0, 1u, &hKey) )
  {
    cbData = 10;
    Type = 0;
    _o__itoa_s((unsigned int)v9, ValueName, 12, 10);
    v3 = RegQueryValueExA(hKey, ValueName, 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    if ( !v3 && Type == 1 )
    {
      v10 = atol((const char *)Data);
      if ( v10 < 0x2710 )
LABEL_12:
        *((_WORD *)a2 + 1168) = v10;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002cdbc  push    rbp
0x18002cdbe  push    rbx
0x18002cdbf  push    rsi
0x18002cdc0  push    rdi
0x18002cdc1  push    r13
0x18002cdc3  push    r14
0x18002cdc5  push    r15
0x18002cdc7  mov     rbp, rsp
0x18002cdca  sub     rsp, 80h
0x18002cdd1  mov     rax, cs:__security_cookie
0x18002cdd8  xor     rax, rsp
0x18002cddb  mov     [rbp+var_10], rax
0x18002cddf  xor     edi, edi
0x18002cde1  mov     [rbp+hKey], 0
0x18002cde9  cmp     cs:dword_1800C291C, edi
0x18002cdef  mov     r14d, r8d
0x18002cdf2  mov     rbx, rdx
0x18002cdf5  mov     word ptr [rdx+920h], 7EDh
0x18002cdfe  mov     r15d, ecx
0x18002ce01  jz      short loc_18002CE2D
0x18002ce03  lea     rcx, ModuleName; "kernel32.dll"
0x18002ce0a  call    cs:__imp_GetModuleHandleW
0x18002ce10  mov     rcx, rax; hModule
0x18002ce13  lea     rdx, ProcName; "GetCalendarInfoW"
0x18002ce1a  call    cs:__imp_GetProcAddress
0x18002ce20  xchg    rax, cs:qword_1800C3600
0x18002ce27  mov     cs:dword_1800C291C, edi
0x18002ce2d  mov     r13d, 1
0x18002ce33  mov     ecx, r15d
0x18002ce36  movzx   esi, r13w
0x18002ce3a  call    IsThai
0x18002ce3f  test    eax, eax
0x18002ce41  jz      short loc_18002CE4A
0x18002ce43  movzx   esi, word ptr [rbx+926h]
0x18002ce4a  mov     rax, cs:qword_1800C3600
0x18002ce51  test    rax, rax
0x18002ce54  jz      short loc_18002CE97
0x18002ce56  lea     rcx, [rbp+Type]
0x18002ce5a  movsx   edx, si
0x18002ce5d  mov     [rsp+80h+lpcbData], rcx
0x18002ce62  and     r14d, 5FFFFFCFh
0x18002ce69  or      r14d, 20000030h
0x18002ce70  mov     [rbp+Type], edi
0x18002ce73  mov     r8d, r14d
0x18002ce76  mov     dword ptr [rsp+80h+phkResult], edi
0x18002ce7a  xor     r9d, r9d
0x18002ce7d  mov     ecx, r15d
0x18002ce80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce85  test    eax, eax
0x18002ce87  jle     short loc_18002CE97
0x18002ce89  mov     eax, [rbp+Type]
0x18002ce8c  cmp     eax, 2710h
0x18002ce91  jb      loc_18002CF28
0x18002ce97  lea     rax, [rbp+hKey]
0x18002ce9b  mov     r9d, r13d; samDesired
0x18002ce9e  xor     r8d, r8d; ulOptions
0x18002cea1  mov     [rsp+80h+phkResult], rax; phkResult
0x18002cea6  lea     rdx, aControlPanelIn; "Control Panel\\International\\Calendars"...
0x18002cead  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ceb4  call    cs:__imp_RegOpenKeyExA
0x18002ceba  test    eax, eax
0x18002cebc  jnz     short loc_18002CF2F
0x18002cebe  lea     r9d, [rax+0Ah]
0x18002cec2  movsx   ecx, si
0x18002cec5  lea     r8d, [rax+0Ch]
0x18002cec9  mov     [rbp+cbData], r9d
0x18002cecd  lea     rdx, [rbp+ValueName]
0x18002ced1  mov     [rbp+Type], edi
0x18002ced4  call    cs:__imp__o__itoa_s
0x18002ceda  mov     rcx, [rbp+hKey]; hKey
0x18002cede  lea     rax, [rbp+cbData]
0x18002cee2  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18002cee7  lea     r9, [rbp+Type]; lpType
0x18002ceeb  lea     rax, [rbp+Data]
0x18002ceef  xor     r8d, r8d; lpReserved
0x18002cef2  lea     rdx, [rbp+ValueName]; lpValueName
0x18002cef6  mov     [rsp+80h+phkResult], rax; lpData
0x18002cefb  call    cs:__imp_RegQueryValueExA
0x18002cf01  mov     rcx, [rbp+hKey]; hKey
0x18002cf05  mov     edi, eax
0x18002cf07  call    cs:__imp_RegCloseKey
0x18002cf0d  test    edi, edi
0x18002cf0f  jnz     short loc_18002CF2F
0x18002cf11  cmp     [rbp+Type], r13d
0x18002cf15  jnz     short loc_18002CF2F
0x18002cf17  lea     rcx, [rbp+Data]; String
0x18002cf1b  call    cs:__imp_atol
0x18002cf21  cmp     eax, 2710h
0x18002cf26  jnb     short loc_18002CF2F
0x18002cf28  mov     [rbx+920h], ax
0x18002cf2f  mov     eax, edi
0x18002cf31  mov     rcx, [rbp+var_10]
0x18002cf35  xor     rcx, rsp; StackCookie
0x18002cf38  call    __security_check_cookie
0x18002cf3d  add     rsp, 80h
0x18002cf44  pop     r15
0x18002cf46  pop     r14
0x18002cf48  pop     r13
0x18002cf4a  pop     rdi
0x18002cf4b  pop     rsi
0x18002cf4c  pop     rbx
0x18002cf4d  pop     rbp
0x18002cf4e  retn
```

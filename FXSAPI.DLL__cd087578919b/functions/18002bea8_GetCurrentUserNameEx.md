# GetCurrentUserNameEx

- ea: `0x18002bea8`
- end: `0x18002c05c`
- name: `GetCurrentUserNameEx`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002a650`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002bea8`
- `0x18002c7bc`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18002bf23`
- `KERNEL32!LoadLibraryW` at `0x18002bf23`
- `KERNEL32!FreeLibrary` at `0x18002bfdf`
- `KERNEL32!FreeLibrary` at `0x18002bfdf`
- `KERNEL32!GetProcAddress` at `0x18002bf45`
- `KERNEL32!GetProcAddress` at `0x18002bf45`
- `KERNEL32!GetLastError` at `0x18002bf86`
- `KERNEL32!GetLastError` at `0x18002bfb1`
- `KERNEL32!GetLastError` at `0x18002c005`
- `KERNEL32!GetLastError` at `0x18002bf86`
- `KERNEL32!GetLastError` at `0x18002bfb1`
- `KERNEL32!GetLastError` at `0x18002c005`

## string_xrefs

- `0x18002bf14`: `Secur32.dll`

## pseudocode

```c
unsigned __int16 *GetCurrentUserNameEx()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  __int64 v4; // rdx
  DWORD v5; // eax
  int v7[4]; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v8; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v9[526]; // [rsp+32h] [rbp-226h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  v8 = 0;
  memset_0(v9, 0, 0x206u);
  v7[0] = 260;
  LibraryW = LoadLibraryW(L"Secur32.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetUserNameExW");
    if ( ProcAddress )
    {
      if ( ((unsigned __int8 (__fastcall *)(__int64, unsigned __int16 *, int *))ProcAddress)(3, &v8, v7)
        || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      LastError = GetLastError();
      v4 = 60;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      LastError = GetLastError();
      v4 = 61;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids, LastError);
LABEL_17:
    FreeLibrary(v1);
    return StringDup(&v8);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids, v5);
  }
  return StringDup(&v8);
}

```

## disassembly

```asm
0x18002bea8  mov     [rsp+arg_0], rbx
0x18002bead  push    rsi
0x18002beae  sub     rsp, 250h
0x18002beb5  mov     rax, cs:__security_cookie
0x18002bebc  xor     rax, rsp
0x18002bebf  mov     [rsp+258h+var_18], rax
0x18002bec7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bece  lea     rsi, WPP_GLOBAL_Control
0x18002bed5  cmp     rcx, rsi
0x18002bed8  jz      short loc_18002BEFB
0x18002beda  test    byte ptr [rcx+1Ch], 2
0x18002bede  jz      short loc_18002BEFB
0x18002bee0  cmp     byte ptr [rcx+19h], 5
0x18002bee4  jb      short loc_18002BEFB
0x18002bee6  mov     rcx, [rcx+10h]
0x18002beea  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002bef1  mov     edx, 3Bh ; ';'
0x18002bef6  call    WPP_SF_
0x18002befb  xor     eax, eax
0x18002befd  lea     rcx, [rsp+258h+var_226]; void *
0x18002bf02  xor     edx, edx; Val
0x18002bf04  mov     [rsp+258h+var_228], ax
0x18002bf09  mov     r8d, 206h; Size
0x18002bf0f  call    memset_0
0x18002bf14  lea     rcx, aSecur32Dll; "Secur32.dll"
0x18002bf1b  mov     [rsp+258h+var_238], 104h
0x18002bf23  call    cs:__imp_LoadLibraryW
0x18002bf2a  nop     dword ptr [rax+rax+00h]
0x18002bf2f  mov     rbx, rax
0x18002bf32  test    rax, rax
0x18002bf35  jz      loc_18002BFED
0x18002bf3b  lea     rdx, aGetusernameexw; "GetUserNameExW"
0x18002bf42  mov     rcx, rax; hModule
0x18002bf45  call    cs:__imp_GetProcAddress
0x18002bf4c  nop     dword ptr [rax+rax+00h]
0x18002bf51  test    rax, rax
0x18002bf54  jz      short loc_18002BF99
0x18002bf56  lea     r8, [rsp+258h+var_238]
0x18002bf5b  mov     ecx, 3
0x18002bf60  lea     rdx, [rsp+258h+var_228]
0x18002bf65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf6a  test    al, al
0x18002bf6c  jnz     short loc_18002BFDC
0x18002bf6e  mov     rax, cs:WPP_GLOBAL_Control
0x18002bf75  cmp     rax, rsi
0x18002bf78  jz      short loc_18002BFDC
0x18002bf7a  test    byte ptr [rax+1Ch], 2
0x18002bf7e  jz      short loc_18002BFDC
0x18002bf80  cmp     byte ptr [rax+19h], 2
0x18002bf84  jb      short loc_18002BFDC
0x18002bf86  call    cs:__imp_GetLastError
0x18002bf8d  nop     dword ptr [rax+rax+00h]
0x18002bf92  mov     edx, 3Ch ; '<'
0x18002bf97  jmp     short loc_18002BFC2
0x18002bf99  mov     rax, cs:WPP_GLOBAL_Control
0x18002bfa0  cmp     rax, rsi
0x18002bfa3  jz      short loc_18002BFDC
0x18002bfa5  test    byte ptr [rax+1Ch], 2
0x18002bfa9  jz      short loc_18002BFDC
0x18002bfab  cmp     byte ptr [rax+19h], 2
0x18002bfaf  jb      short loc_18002BFDC
0x18002bfb1  call    cs:__imp_GetLastError
0x18002bfb8  nop     dword ptr [rax+rax+00h]
0x18002bfbd  mov     edx, 3Dh ; '='
0x18002bfc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfc9  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002bfd0  mov     r9d, eax
0x18002bfd3  mov     rcx, [rcx+10h]
0x18002bfd7  call    WPP_SF_d
0x18002bfdc  mov     rcx, rbx; hLibModule
0x18002bfdf  call    cs:__imp_FreeLibrary
0x18002bfe6  nop     dword ptr [rax+rax+00h]
0x18002bfeb  jmp     short loc_18002C030
0x18002bfed  mov     rax, cs:WPP_GLOBAL_Control
0x18002bff4  cmp     rax, rsi
0x18002bff7  jz      short loc_18002C030
0x18002bff9  test    byte ptr [rax+1Ch], 2
0x18002bffd  jz      short loc_18002C030
0x18002bfff  cmp     byte ptr [rax+19h], 2
0x18002c003  jb      short loc_18002C030
0x18002c005  call    cs:__imp_GetLastError
0x18002c00c  nop     dword ptr [rax+rax+00h]
0x18002c011  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c018  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c01f  mov     edx, 3Eh ; '>'
0x18002c024  mov     r9d, eax
0x18002c027  mov     rcx, [rcx+10h]
0x18002c02b  call    WPP_SF_d
0x18002c030  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18002c035  call    StringDup
0x18002c03a  mov     rcx, [rsp+258h+var_18]
0x18002c042  xor     rcx, rsp; StackCookie
0x18002c045  call    __security_check_cookie
0x18002c04a  mov     rbx, [rsp+258h+arg_0]
0x18002c052  add     rsp, 250h
0x18002c059  pop     rsi
0x18002c05a  retn
```

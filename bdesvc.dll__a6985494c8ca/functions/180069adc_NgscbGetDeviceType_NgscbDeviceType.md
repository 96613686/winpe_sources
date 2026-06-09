# NgscbGetDeviceType(NgscbDeviceType *)

- ea: `0x180069adc`
- end: `0x180069bef`
- name: `?NgscbGetDeviceType@@YAJPEAW4NgscbDeviceType@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(enum NgscbDeviceType *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180032f60`

## callees

- `0x180009f60`
- `0x18002e628`
- `0x180069adc`
- `0x180069ed0`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069b0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069b0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180069bd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180069bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069b6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069b6a`

## string_xrefs

- `0x180069aff`: `powrprof.dll`

## pseudocode

```c
__int64 __fastcall NgscbGetDeviceType(enum NgscbDeviceType *a1)
{
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  int v6; // eax
  int v7; // ecx

  KnownLastErrorHR = 0;
  if ( !(unsigned __int8)NgscbpGetDeviceType_TEST_Override() )
  {
    Library = LoadLibraryExW(L"powrprof.dll", 0, 0x800u);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PowerDeterminePlatformRoleEx");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
        v7 = -1;
        if ( v6 == 8 )
          v7 = 1;
        *(_DWORD *)a1 = v7;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            KnownLastErrorHR);
      }
      FreeLibrary(v4);
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          KnownLastErrorHR);
    }
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x180069adc  mov     [rsp+arg_0], rbx
0x180069ae1  mov     [rsp+arg_8], rsi
0x180069ae6  push    rdi
0x180069ae7  sub     rsp, 20h
0x180069aeb  mov     rsi, rcx
0x180069aee  xor     ebx, ebx
0x180069af0  call    NgscbpGetDeviceType_TEST_Override
0x180069af5  test    al, al
0x180069af7  jnz     loc_180069BDC
0x180069afd  xor     edx, edx; hFile
0x180069aff  lea     rcx, aPowrprofDll; "powrprof.dll"
0x180069b06  mov     r8d, 800h; dwFlags
0x180069b0c  call    cs:__imp_LoadLibraryExW
0x180069b13  nop     dword ptr [rax+rax+00h]
0x180069b18  mov     rdi, rax
0x180069b1b  test    rax, rax
0x180069b1e  jnz     short loc_180069B60
0x180069b20  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180069b25  mov     ebx, eax
0x180069b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180069b2e  lea     rax, WPP_GLOBAL_Control
0x180069b35  cmp     rcx, rax
0x180069b38  jz      loc_180069BDC
0x180069b3e  test    byte ptr [rcx+1Ch], 40h
0x180069b42  jz      loc_180069BDC
0x180069b48  mov     rcx, [rcx+10h]
0x180069b4c  lea     edx, [rdi+15h]
0x180069b4f  mov     r9d, ebx
0x180069b52  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180069b59  call    WPP_SF_d
0x180069b5e  jmp     short loc_180069BDC
0x180069b60  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRoleEx"
0x180069b67  mov     rcx, rdi; hModule
0x180069b6a  call    cs:__imp_GetProcAddress
0x180069b71  nop     dword ptr [rax+rax+00h]
0x180069b76  test    rax, rax
0x180069b79  jnz     short loc_180069BB5
0x180069b7b  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180069b80  mov     ebx, eax
0x180069b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180069b89  lea     rax, WPP_GLOBAL_Control
0x180069b90  cmp     rcx, rax
0x180069b93  jz      short loc_180069BCD
0x180069b95  test    byte ptr [rcx+1Ch], 40h
0x180069b99  jz      short loc_180069BCD
0x180069b9b  mov     rcx, [rcx+10h]
0x180069b9f  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180069ba6  mov     edx, 16h
0x180069bab  mov     r9d, ebx
0x180069bae  call    WPP_SF_d
0x180069bb3  jmp     short loc_180069BCD
0x180069bb5  mov     ecx, 2
0x180069bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bbf  or      ecx, 0FFFFFFFFh
0x180069bc2  cmp     eax, 8
0x180069bc5  lea     edx, [rcx+2]
0x180069bc8  cmovz   ecx, edx
0x180069bcb  mov     [rsi], ecx
0x180069bcd  mov     rcx, rdi; hLibModule
0x180069bd0  call    cs:__imp_FreeLibrary
0x180069bd7  nop     dword ptr [rax+rax+00h]
0x180069bdc  mov     rsi, [rsp+28h+arg_8]
0x180069be1  mov     eax, ebx
0x180069be3  mov     rbx, [rsp+28h+arg_0]
0x180069be8  add     rsp, 20h
0x180069bec  pop     rdi
0x180069bed  retn
```

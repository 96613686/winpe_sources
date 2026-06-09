# WbemPauseService(void)

- ea: `0x18001273c`
- end: `0x18001286b`
- name: `?WbemPauseService@@YAJXZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008840`
- `0x18000dcdc`
- `0x180012210`

## callees

- `0x180004c30`
- `0x18000b5dc`
- `0x18000c024`
- `0x18001273c`
- `0x180012c34`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800127ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800127ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001283b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001283b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001278b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001278b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012795`

## string_xrefs

- `0x1800127b0`: `\wbem\wbemcore.dll`

## pseudocode

```c
signed int WbemPauseService(void)
{
  signed int result; // eax
  HMODULE Library; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rax
  int v4; // ebx
  unsigned int v5; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  dword_180032CC8 = 7;
  _PROG_RESOURCES::RevokeLogin((_PROG_RESOURCES *)&g_ProgRes);
  CMonitorEvents::Unregister((CMonitorEvents *)&dword_180032A88, 0);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    StringCchCatW(Buffer, 0x104u, L"\\wbem\\wbemcore.dll");
    Library = LoadLibraryExW(Buffer, 0, 0);
    v2 = Library;
    if ( !Library )
      return -2147217398;
    ProcAddress = GetProcAddress(Library, "Shutdown");
    if ( ProcAddress )
    {
      v4 = 0;
      v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress)(0, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2716f4bd31e130f967505b342dce5479_Traceguids, v5);
      }
    }
    else
    {
      v4 = -2147217398;
    }
    FreeLibrary(v2);
    return v4;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001273c  mov     [rsp+arg_0], rbx
0x180012741  push    rdi
0x180012742  sub     rsp, 240h
0x180012749  mov     rax, cs:__security_cookie
0x180012750  xor     rax, rsp
0x180012753  mov     [rsp+248h+var_18], rax
0x18001275b  lea     rcx, ?g_ProgRes@@3U_PROG_RESOURCES@@A; this
0x180012762  mov     cs:dword_180032CC8, 7
0x18001276c  call    ?RevokeLogin@_PROG_RESOURCES@@QEAAHXZ; _PROG_RESOURCES::RevokeLogin(void)
0x180012771  xor     edx, edx; int
0x180012773  lea     rcx, dword_180032A88; this
0x18001277a  call    ?Unregister@CMonitorEvents@@QEAAKH@Z; CMonitorEvents::Unregister(int)
0x18001277f  mov     ebx, 104h
0x180012784  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180012789  mov     edx, ebx; uSize
0x18001278b  call    cs:__imp_GetSystemDirectoryW
0x180012791  test    eax, eax
0x180012793  jnz     short loc_1800127B0
0x180012795  call    cs:__imp_GetLastError
0x18001279b  test    eax, eax
0x18001279d  jle     loc_18001284A
0x1800127a3  movzx   eax, ax
0x1800127a6  or      eax, 80070000h
0x1800127ab  jmp     loc_18001284A
0x1800127b0  lea     r8, aWbemWbemcoreDl; "\\wbem\\wbemcore.dll"
0x1800127b7  mov     rdx, rbx; unsigned __int64
0x1800127ba  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x1800127bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800127c4  xor     r8d, r8d; dwFlags
0x1800127c7  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x1800127cc  xor     edx, edx; hFile
0x1800127ce  call    cs:__imp_LoadLibraryExW
0x1800127d4  mov     rdi, rax
0x1800127d7  test    rax, rax
0x1800127da  jz      short loc_180012843
0x1800127dc  lea     rdx, aShutdown; "Shutdown"
0x1800127e3  mov     rcx, rax; hModule
0x1800127e6  call    cs:__imp_GetProcAddress
0x1800127ec  test    rax, rax
0x1800127ef  jz      short loc_180012833
0x1800127f1  xor     ebx, ebx
0x1800127f3  xor     edx, edx
0x1800127f5  xor     ecx, ecx
0x1800127f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012803  lea     rdx, WPP_GLOBAL_Control
0x18001280a  cmp     rcx, rdx
0x18001280d  jz      short loc_180012838
0x18001280f  test    byte ptr [rcx+1Ch], 1
0x180012813  jz      short loc_180012838
0x180012815  cmp     byte ptr [rcx+19h], 5
0x180012819  jb      short loc_180012838
0x18001281b  mov     rcx, [rcx+10h]
0x18001281f  lea     edx, [rbx+16h]
0x180012822  mov     r9d, eax
0x180012825  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x18001282c  call    WPP_SF_d
0x180012831  jmp     short loc_180012838
0x180012833  mov     ebx, 8004100Ah
0x180012838  mov     rcx, rdi; hLibModule
0x18001283b  call    cs:__imp_FreeLibrary
0x180012841  jmp     short loc_180012848
0x180012843  mov     ebx, 8004100Ah
0x180012848  mov     eax, ebx
0x18001284a  mov     rcx, [rsp+248h+var_18]
0x180012852  xor     rcx, rsp; StackCookie
0x180012855  call    __security_check_cookie
0x18001285a  mov     rbx, [rsp+248h+arg_0]
0x180012862  add     rsp, 240h
0x180012869  pop     rdi
0x18001286a  retn
```

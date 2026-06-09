# WbemContinueService(void)

- ea: `0x180012604`
- end: `0x180012733`
- name: `?WbemContinueService@@YAJXZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008840`
- `0x18000dcdc`
- `0x180011b40`

## callees

- `0x180004c30`
- `0x180009ba4`
- `0x180012604`
- `0x180012c34`
- `0x180016aec`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012672`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001268a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001268a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800126dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800126dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001262f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001262f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012639`

## string_xrefs

- `0x180012654`: `\wbem\wbemcore.dll`

## pseudocode

```c
signed int WbemContinueService(void)
{
  signed int result; // eax
  HMODULE Library; // rax
  _PROG_RESOURCES *v2; // rcx
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  int v5; // ebx
  unsigned int v6; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    StringCchCatW(Buffer, 0x104u, L"\\wbem\\wbemcore.dll");
    Library = LoadLibraryExW(Buffer, 0, 0);
    v3 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "Reinitialize");
      if ( ProcAddress )
      {
        v5 = 0;
        v6 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2716f4bd31e130f967505b342dce5479_Traceguids, v6);
        }
      }
      else
      {
        v5 = -2147217398;
      }
      FreeLibrary(v3);
    }
    else
    {
      v5 = -2147217398;
    }
    if ( (unsigned int)_PROG_RESOURCES::RegisterLogin(v2) )
    {
      CMonitorEvents::Register((CMonitorEvents *)&dword_180032A88);
      result = v5;
      dword_180032CC8 = 4;
    }
    else
    {
      return -2147217398;
    }
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
0x180012604  mov     [rsp+arg_0], rbx
0x180012609  push    rdi
0x18001260a  sub     rsp, 240h
0x180012611  mov     rax, cs:__security_cookie
0x180012618  xor     rax, rsp
0x18001261b  mov     [rsp+248h+var_18], rax
0x180012623  mov     ebx, 104h
0x180012628  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18001262d  mov     edx, ebx; uSize
0x18001262f  call    cs:__imp_GetSystemDirectoryW
0x180012635  test    eax, eax
0x180012637  jnz     short loc_180012654
0x180012639  call    cs:__imp_GetLastError
0x18001263f  test    eax, eax
0x180012641  jle     loc_180012712
0x180012647  movzx   eax, ax
0x18001264a  or      eax, 80070000h
0x18001264f  jmp     loc_180012712
0x180012654  lea     r8, aWbemWbemcoreDl; "\\wbem\\wbemcore.dll"
0x18001265b  mov     rdx, rbx; unsigned __int64
0x18001265e  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x180012663  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012668  xor     r8d, r8d; dwFlags
0x18001266b  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180012670  xor     edx, edx; hFile
0x180012672  call    cs:__imp_LoadLibraryExW
0x180012678  mov     rdi, rax
0x18001267b  test    rax, rax
0x18001267e  jz      short loc_1800126E5
0x180012680  lea     rdx, ProcName; "Reinitialize"
0x180012687  mov     rcx, rax; hModule
0x18001268a  call    cs:__imp_GetProcAddress
0x180012690  test    rax, rax
0x180012693  jz      short loc_1800126D5
0x180012695  xor     ebx, ebx
0x180012697  xor     ecx, ecx
0x180012699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001269e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126a5  lea     rdx, WPP_GLOBAL_Control
0x1800126ac  cmp     rcx, rdx
0x1800126af  jz      short loc_1800126DA
0x1800126b1  test    byte ptr [rcx+1Ch], 1
0x1800126b5  jz      short loc_1800126DA
0x1800126b7  cmp     byte ptr [rcx+19h], 5
0x1800126bb  jb      short loc_1800126DA
0x1800126bd  mov     rcx, [rcx+10h]
0x1800126c1  lea     edx, [rbx+17h]
0x1800126c4  mov     r9d, eax
0x1800126c7  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x1800126ce  call    WPP_SF_d
0x1800126d3  jmp     short loc_1800126DA
0x1800126d5  mov     ebx, 8004100Ah
0x1800126da  mov     rcx, rdi; hLibModule
0x1800126dd  call    cs:__imp_FreeLibrary
0x1800126e3  jmp     short loc_1800126EA
0x1800126e5  mov     ebx, 8004100Ah
0x1800126ea  call    ?RegisterLogin@_PROG_RESOURCES@@QEAAHXZ; _PROG_RESOURCES::RegisterLogin(void)
0x1800126ef  test    eax, eax
0x1800126f1  jnz     short loc_1800126FA
0x1800126f3  mov     eax, 8004100Ah
0x1800126f8  jmp     short loc_180012712
0x1800126fa  lea     rcx, dword_180032A88; this
0x180012701  call    ?Register@CMonitorEvents@@QEAAKXZ; CMonitorEvents::Register(void)
0x180012706  mov     eax, ebx
0x180012708  mov     cs:dword_180032CC8, 4
0x180012712  mov     rcx, [rsp+248h+var_18]
0x18001271a  xor     rcx, rsp; StackCookie
0x18001271d  call    __security_check_cookie
0x180012722  mov     rbx, [rsp+248h+arg_0]
0x18001272a  add     rsp, 240h
0x180012731  pop     rdi
0x180012732  retn
```

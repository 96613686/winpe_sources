# CNTService::ParseStandardArgs(int,ushort * * const)

- ea: `0x140005790`
- end: `0x1400058df`
- name: `?ParseStandardArgs@CNTService@@QEAAHHQEAPEAG@Z`
- size: `335`
- prototype: `__int64 __fastcall(CNTService *__hidden this, int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x140003218`

## callees

- `0x1400055d0`
- `0x140005790`
- `0x14000ae60`
- `0x14000c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005808`
- `KERNEL32!GetLastError` at `0x14000589c`
- `KERNEL32!GetLastError` at `0x140005808`
- `KERNEL32!GetLastError` at `0x14000589c`
- `KERNEL32!GetModuleFileNameW` at `0x14000587f`
- `KERNEL32!GetModuleFileNameW` at `0x14000587f`
- `msvcrt!wprintf` at `0x14000584d`
- `msvcrt!wprintf` at `0x140005894`
- `msvcrt!wprintf` at `0x1400058af`
- `msvcrt!wprintf` at `0x14000584d`
- `msvcrt!wprintf` at `0x140005894`
- `msvcrt!wprintf` at `0x1400058af`
- `msvcrt!_wcsicmp` at `0x1400057c9`
- `msvcrt!_wcsicmp` at `0x140005825`
- `msvcrt!_wcsicmp` at `0x1400057c9`
- `msvcrt!_wcsicmp` at `0x140005825`

## string_xrefs

- `0x1400057e3`: `%ls is already installed\n`
- `0x1400057ff`: `%ls installed\n`
- `0x14000580e`: `l%s failed to install. Error %d\n`
- `0x140005843`: `%ls is not installed\n`
- `0x14000588d`: `%ls removed. (You must delete the file (%s) yourself.)\n`
- `0x1400058a2`: `Could not remove %ls. Error %d\n`

## pseudocode

```c
__int64 __fastcall CNTService::ParseStandardArgs(CNTService *this, int a2, unsigned __int16 **const a3)
{
  char *v5; // rdi
  DWORD LastError; // eax
  char *v7; // rdi
  DWORD v8; // eax
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( a2 > 1 )
  {
    if ( !_wcsicmp(a3[1], L"-i") )
    {
      v5 = (char *)this + 8;
      if ( (unsigned int)CNTService::IsInstalled(this) )
      {
        wprintf(L"%ls is already installed\n", v5);
      }
      else if ( (*(unsigned int (__fastcall **)(CNTService *))(*(_QWORD *)this + 8LL))(this) )
      {
        wprintf(L"%ls installed\n", v5);
      }
      else
      {
        LastError = GetLastError();
        wprintf(L"l%s failed to install. Error %d\n", v5, LastError);
      }
      return 1;
    }
    if ( !_wcsicmp(a3[1], L"-u") )
    {
      v7 = (char *)this + 8;
      if ( (unsigned int)CNTService::IsInstalled(this) )
      {
        if ( (*(unsigned int (__fastcall **)(CNTService *))(*(_QWORD *)this + 16LL))(this) )
        {
          Filename[260] = 0;
          GetModuleFileNameW(0, Filename, 0x105u);
          wprintf(L"%ls removed. (You must delete the file (%s) yourself.)\n", (char *)this + 8, Filename);
        }
        else
        {
          v8 = GetLastError();
          wprintf(L"Could not remove %ls. Error %d\n", v7, v8);
        }
      }
      else
      {
        wprintf(L"%ls is not installed\n", v7);
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005790  mov     [rsp+arg_8], rbx
0x140005795  push    rdi
0x140005796  sub     rsp, 240h
0x14000579d  mov     rax, cs:__security_cookie
0x1400057a4  xor     rax, rsp
0x1400057a7  mov     [rsp+248h+var_18], rax
0x1400057af  mov     rdi, r8
0x1400057b2  mov     rbx, rcx
0x1400057b5  cmp     edx, 1
0x1400057b8  jle     loc_1400058BC
0x1400057be  mov     rcx, [r8+8]; String1
0x1400057c2  lea     rdx, aI; "-i"
0x1400057c9  call    cs:__imp__wcsicmp
0x1400057cf  test    eax, eax
0x1400057d1  jnz     short loc_14000581A
0x1400057d3  mov     rcx, rbx; this
0x1400057d6  lea     rdi, [rbx+8]
0x1400057da  call    ?IsInstalled@CNTService@@QEAAHXZ; CNTService::IsInstalled(void)
0x1400057df  test    eax, eax
0x1400057e1  jz      short loc_1400057EC
0x1400057e3  lea     rcx, aLsIsAlreadyIns; "%ls is already installed\n"
0x1400057ea  jmp     short loc_14000584A
0x1400057ec  mov     rax, [rbx]
0x1400057ef  mov     rcx, rbx
0x1400057f2  mov     rax, [rax+8]
0x1400057f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057fb  test    eax, eax
0x1400057fd  jz      short loc_140005808
0x1400057ff  lea     rcx, aLsInstalled; "%ls installed\n"
0x140005806  jmp     short loc_14000584A
0x140005808  call    cs:__imp_GetLastError
0x14000580e  lea     rcx, aLSFailedToInst; "l%s failed to install. Error %d\n"
0x140005815  jmp     loc_1400058A9
0x14000581a  mov     rcx, [rdi+8]; String1
0x14000581e  lea     rdx, aU; "-u"
0x140005825  call    cs:__imp__wcsicmp
0x14000582b  test    eax, eax
0x14000582d  jnz     loc_1400058BC
0x140005833  mov     rcx, rbx; this
0x140005836  lea     rdi, [rbx+8]
0x14000583a  call    ?IsInstalled@CNTService@@QEAAHXZ; CNTService::IsInstalled(void)
0x14000583f  test    eax, eax
0x140005841  jnz     short loc_140005855
0x140005843  lea     rcx, aLsIsNotInstall; "%ls is not installed\n"
0x14000584a  mov     rdx, rdi
0x14000584d  call    cs:__imp_wprintf
0x140005853  jmp     short loc_1400058B5
0x140005855  mov     rax, [rbx]
0x140005858  mov     rcx, rbx
0x14000585b  mov     rax, [rax+10h]
0x14000585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005864  test    eax, eax
0x140005866  jz      short loc_14000589C
0x140005868  xor     eax, eax
0x14000586a  lea     rdx, [rsp+248h+Filename]; lpFilename
0x14000586f  mov     r8d, 105h; nSize
0x140005875  mov     [rsp+248h+var_20], ax
0x14000587d  xor     ecx, ecx; hModule
0x14000587f  call    cs:__imp_GetModuleFileNameW
0x140005885  lea     r8, [rsp+248h+Filename]
0x14000588a  mov     rdx, rdi
0x14000588d  lea     rcx, aLsRemovedYouMu; "%ls removed. (You must delete the file "...
0x140005894  call    cs:__imp_wprintf
0x14000589a  jmp     short loc_1400058B5
0x14000589c  call    cs:__imp_GetLastError
0x1400058a2  lea     rcx, aCouldNotRemove; "Could not remove %ls. Error %d\n"
0x1400058a9  mov     r8d, eax
0x1400058ac  mov     rdx, rdi
0x1400058af  call    cs:__imp_wprintf
0x1400058b5  mov     eax, 1
0x1400058ba  jmp     short loc_1400058BE
0x1400058bc  xor     eax, eax
0x1400058be  mov     rcx, [rsp+248h+var_18]
0x1400058c6  xor     rcx, rsp; StackCookie
0x1400058c9  call    __security_check_cookie
0x1400058ce  mov     rbx, [rsp+248h+arg_8]
0x1400058d6  add     rsp, 240h
0x1400058dd  pop     rdi
0x1400058de  retn
```

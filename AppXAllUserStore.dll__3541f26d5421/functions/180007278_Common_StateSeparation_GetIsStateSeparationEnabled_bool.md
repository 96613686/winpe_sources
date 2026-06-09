# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x180007278`
- end: `0x18000734e`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `214`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `23`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006d40`
- `0x180007638`
- `0x18000f53c`
- `0x180010eac`
- `0x1800110cc`
- `0x180011c44`
- `0x180011dd0`
- `0x1800124c0`
- `0x180012dcc`
- `0x180013a60`
- `0x180014240`
- `0x180014694`
- `0x180015430`
- `0x18002b79c`
- `0x18002bbf0`
- `0x1800302a0`
- `0x1800316b8`
- `0x18003a274`
- `0x18003adb0`
- `0x18003dd38`
- `0x180046c78`
- `0x1800493a4`
- `0x18004b024`

## callees

- `0x180007278`
- `0x18001ed14`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800072cf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800072cf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007323`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007323`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800072ae`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800072c6`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800072ae`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800072c6`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007294`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007294`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180007305`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180007305`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800072ed`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800072ed`

## string_xrefs

- `0x1800072e0`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetIsStateSeparationEnabled(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  __int64 (*ProcAddress)(void); // rax
  char v6; // al
  char v7; // al

  RtlAcquireSRWLockShared(&qword_180064DD0);
  if ( byte_180064DD9 )
  {
    *a1 = byte_180064DD8;
    RtlReleaseSRWLockShared(&qword_180064DD0);
  }
  else
  {
    RtlReleaseSRWLockShared(&qword_180064DD0);
    RtlAcquireSRWLockExclusive(&qword_180064DD0);
    if ( byte_180064DD9 )
    {
      *a1 = byte_180064DD8;
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v4 = Library;
      if ( Library && (ProcAddress = GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0 )
      {
        v7 = ProcAddress();
        byte_180064DD9 = 1;
        v6 = v7 != 0;
        byte_180064DD8 = v6;
      }
      else
      {
        v6 = byte_180064DD8;
      }
      *a1 = v6;
      Common::AutoHandleCloseModule<HINSTANCE__ *>(v4);
    }
    RtlReleaseSRWLockExclusive(&qword_180064DD0);
  }
  return 0;
}

```

## disassembly

```asm
0x180007278  mov     [rsp+arg_0], rbx
0x18000727d  mov     [rsp+arg_8], rsi
0x180007282  push    rdi
0x180007283  sub     rsp, 20h
0x180007287  mov     rdi, rcx
0x18000728a  lea     rsi, qword_180064DD0
0x180007291  mov     rcx, rsi
0x180007294  call    cs:__imp_RtlAcquireSRWLockShared
0x18000729a  cmp     cs:byte_180064DD9, 0
0x1800072a1  mov     rcx, rsi
0x1800072a4  jz      short loc_1800072C6
0x1800072a6  mov     al, cs:byte_180064DD8
0x1800072ac  mov     [rdi], al
0x1800072ae  call    cs:__imp_RtlReleaseSRWLockShared
0x1800072b4  mov     rbx, [rsp+28h+arg_0]
0x1800072b9  xor     eax, eax
0x1800072bb  mov     rsi, [rsp+28h+arg_8]
0x1800072c0  add     rsp, 20h
0x1800072c4  pop     rdi
0x1800072c5  retn
0x1800072c6  call    cs:__imp_RtlReleaseSRWLockShared
0x1800072cc  mov     rcx, rsi
0x1800072cf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800072d5  cmp     cs:byte_180064DD9, 0
0x1800072dc  jnz     short loc_18000732B
0x1800072de  xor     edx, edx; hFile
0x1800072e0  lea     rcx, LibFileName; "ntdll.dll"
0x1800072e7  mov     r8d, 800h; dwFlags
0x1800072ed  call    cs:__imp_LoadLibraryExW
0x1800072f3  mov     rbx, rax
0x1800072f6  test    rax, rax
0x1800072f9  jz      short loc_180007310
0x1800072fb  lea     rdx, ProcName; "RtlIsStateSeparationEnabled"
0x180007302  mov     rcx, rax; hModule
0x180007305  call    cs:__imp_GetProcAddress
0x18000730b  test    rax, rax
0x18000730e  jnz     short loc_180007335
0x180007310  mov     al, cs:byte_180064DD8
0x180007316  mov     rcx, rbx
0x180007319  mov     [rdi], al
0x18000731b  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x180007320  mov     rcx, rsi
0x180007323  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007329  jmp     short loc_1800072B4
0x18000732b  mov     al, cs:byte_180064DD8
0x180007331  mov     [rdi], al
0x180007333  jmp     short loc_180007320
0x180007335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733a  test    al, al
0x18000733c  mov     cs:byte_180064DD9, 1
0x180007343  setnz   al
0x180007346  mov     cs:byte_180064DD8, al
0x18000734c  jmp     short loc_180007316
```

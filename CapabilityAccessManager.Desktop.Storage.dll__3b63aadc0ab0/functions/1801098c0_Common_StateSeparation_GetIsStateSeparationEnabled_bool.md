# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x1801098c0`
- end: `0x1801099a9`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `233`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801099b0`
- `0x180109fac`

## callees

- `0x180003b80`
- `0x1801098c0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180109937`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180109937`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109987`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109987`
- `ntdll!RtlReleaseSRWLockShared` at `0x1801098f6`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109901`
- `ntdll!RtlReleaseSRWLockShared` at `0x1801098f6`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109901`
- `ntdll!RtlAcquireSRWLockShared` at `0x1801098dc`
- `ntdll!RtlAcquireSRWLockShared` at `0x1801098dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109991`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109991`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18010990a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18010990a`

## string_xrefs

- `0x180109930`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetIsStateSeparationEnabled(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  char v5; // al

  RtlAcquireSRWLockShared(&qword_180140600);
  if ( byte_180140608 )
  {
    *a1 = byte_1801405F8;
    RtlReleaseSRWLockShared(&qword_180140600);
  }
  else
  {
    RtlReleaseSRWLockShared(&qword_180140600);
    RtlAcquireSRWLockExclusive(&qword_180140600);
    if ( byte_180140608 )
    {
      *a1 = byte_1801405F8;
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v3 = Library;
      if ( Library
        && (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                       Library,
                                                                       "RtlIsStateSeparationEnabled")) != 0 )
      {
        v5 = RtlIsStateSeparationEnabled() != 0;
        byte_1801405F8 = v5;
        byte_180140608 = 1;
      }
      else
      {
        v5 = byte_1801405F8;
      }
      *a1 = v5;
      if ( v3 )
        FreeLibrary(v3);
    }
    RtlReleaseSRWLockExclusive(&qword_180140600);
  }
  return 0;
}

```

## disassembly

```asm
0x1801098c0  mov     [rsp+arg_0], rbx
0x1801098c5  mov     [rsp+arg_18], rsi
0x1801098ca  push    rdi
0x1801098cb  sub     rsp, 20h
0x1801098cf  mov     rdi, rcx
0x1801098d2  lea     rsi, qword_180140600
0x1801098d9  mov     rcx, rsi
0x1801098dc  call    cs:__imp_RtlAcquireSRWLockShared
0x1801098e2  mov     rcx, rsi
0x1801098e5  cmp     cs:byte_180140608, 0
0x1801098ec  jz      short loc_180109901
0x1801098ee  mov     al, cs:byte_1801405F8
0x1801098f4  mov     [rdi], al
0x1801098f6  call    cs:__imp_RtlReleaseSRWLockShared
0x1801098fc  jmp     loc_180109997
0x180109901  call    cs:__imp_RtlReleaseSRWLockShared
0x180109907  mov     rcx, rsi
0x18010990a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180109910  mov     [rsp+28h+arg_8], rsi
0x180109915  cmp     cs:byte_180140608, 0
0x18010991c  jz      short loc_180109928
0x18010991e  mov     al, cs:byte_1801405F8
0x180109924  mov     [rdi], al
0x180109926  jmp     short loc_18010998E
0x180109928  xor     edx, edx; hFile
0x18010992a  mov     r8d, 800h; dwFlags
0x180109930  lea     rcx, ModuleName; "ntdll.dll"
0x180109937  call    cs:__imp_LoadLibraryExW
0x18010993d  mov     rbx, rax
0x180109940  mov     [rsp+28h+arg_10], rax
0x180109945  test    rax, rax
0x180109948  jz      short loc_180109977
0x18010994a  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x180109951  mov     rcx, rax; hModule
0x180109954  call    GetProcAddress_0
0x180109959  test    rax, rax
0x18010995c  jz      short loc_180109977
0x18010995e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109963  test    al, al
0x180109965  setnz   al
0x180109968  mov     cs:byte_1801405F8, al
0x18010996e  mov     cs:byte_180140608, 1
0x180109975  jmp     short loc_18010997D
0x180109977  mov     al, cs:byte_1801405F8
0x18010997d  mov     [rdi], al
0x18010997f  test    rbx, rbx
0x180109982  jz      short loc_18010998E
0x180109984  mov     rcx, rbx; hLibModule
0x180109987  call    cs:__imp_FreeLibrary
0x18010998d  nop
0x18010998e  mov     rcx, rsi
0x180109991  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180109997  xor     eax, eax
0x180109999  mov     rbx, [rsp+28h+arg_0]
0x18010999e  mov     rsi, [rsp+28h+arg_18]
0x1801099a3  add     rsp, 20h
0x1801099a7  pop     rdi
0x1801099a8  retn
```

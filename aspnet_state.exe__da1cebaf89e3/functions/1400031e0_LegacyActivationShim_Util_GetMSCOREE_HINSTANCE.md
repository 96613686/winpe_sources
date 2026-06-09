# LegacyActivationShim::Util::GetMSCOREE(HINSTANCE__ * *)

- ea: `0x1400031e0`
- end: `0x14000325d`
- name: `?GetMSCOREE@Util@LegacyActivationShim@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *__hidden this, HINSTANCE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002bd8`
- `0x140002f14`

## callees

- `0x1400031e0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400031fc`
- `KERNEL32!LoadLibraryW` at `0x1400031fc`
- `KERNEL32!FreeLibrary` at `0x140003245`
- `KERNEL32!FreeLibrary` at `0x140003245`
- `KERNEL32!GetLastError` at `0x14000320a`
- `KERNEL32!GetLastError` at `0x14000320a`

## string_xrefs

- `0x1400031f5`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::GetMSCOREE(LegacyActivationShim::Util *this, HINSTANCE *a2)
{
  HINSTANCE v2; // rax
  HMODULE LibraryW; // rax
  signed int LastError; // ecx
  __int64 result; // rax

  v2 = LegacyActivationShim::Util::g_hModMscoree;
  if ( LegacyActivationShim::Util::g_hModMscoree )
    goto LABEL_9;
  LibraryW = LoadLibraryW(L"mscoree.dll");
  if ( LibraryW )
  {
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&LegacyActivationShim::Util::g_hModMscoree,
           (signed __int64)LibraryW,
           0) )
    {
      FreeLibrary(LibraryW);
      v2 = LegacyActivationShim::Util::g_hModMscoree;
    }
    else
    {
      v2 = LegacyActivationShim::Util::g_hModMscoree;
      LegacyActivationShim::Util::g_hModMscoreeHolder = LegacyActivationShim::Util::g_hModMscoree;
      byte_14000A0C8 = 1;
    }
LABEL_9:
    *(_QWORD *)this = v2;
    return 0;
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x1400031e0  push    rbx
0x1400031e2  sub     rsp, 20h
0x1400031e6  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x1400031ed  mov     rbx, rcx
0x1400031f0  test    rax, rax
0x1400031f3  jnz     short loc_140003252
0x1400031f5  lea     rcx, LibFileName; "mscoree.dll"
0x1400031fc  call    cs:__imp_LoadLibraryW
0x140003202  mov     rcx, rax; hLibModule
0x140003205  test    rax, rax
0x140003208  jnz     short loc_140003221
0x14000320a  call    cs:__imp_GetLastError
0x140003210  mov     ecx, eax
0x140003212  movzx   eax, ax
0x140003215  or      eax, 80070000h
0x14000321a  test    ecx, ecx
0x14000321c  cmovle  eax, ecx
0x14000321f  jmp     short loc_140003257
0x140003221  xor     eax, eax
0x140003223  lock cmpxchg cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x14000322c  jnz     short loc_140003245
0x14000322e  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x140003235  mov     cs:?g_hModMscoreeHolder@Util@LegacyActivationShim@@3VZeroInitGlobalHMODULEHolder@12@A, rax; LegacyActivationShim::Util::ZeroInitGlobalHMODULEHolder LegacyActivationShim::Util::g_hModMscoreeHolder
0x14000323c  mov     cs:byte_14000A0C8, 1
0x140003243  jmp     short loc_140003252
0x140003245  call    cs:__imp_FreeLibrary
0x14000324b  mov     rax, cs:?g_hModMscoree@Util@LegacyActivationShim@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * LegacyActivationShim::Util::g_hModMscoree
0x140003252  mov     [rbx], rax
0x140003255  xor     eax, eax
0x140003257  add     rsp, 20h
0x14000325b  pop     rbx
0x14000325c  retn
```

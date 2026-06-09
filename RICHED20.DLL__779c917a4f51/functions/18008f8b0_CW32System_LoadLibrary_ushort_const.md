# CW32System::LoadLibrary(ushort const *)

- ea: `0x18008f8b0`
- end: `0x18008f91d`
- name: `?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z`
- size: `109`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18005c854`
- `0x1800905e8`
- `0x1800907ac`

## callees

- `0x18008cc4c`
- `0x18008dbbc`
- `0x18008f8b0`
- `0x180091140`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x18008f8ee`
- `KERNEL32!LoadLibraryA` at `0x18008f8ee`
- `KERNEL32!LoadLibraryW` at `0x18008f8d4`
- `KERNEL32!LoadLibraryW` at `0x18008f8d4`

## pseudocode

```c
HINSTANCE __fastcall CW32System::LoadLibrary(const unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  HMODULE LibraryA; // rbx
  LPCSTR lpLibFileName[68]; // [rsp+20h] [rbp-238h] BYREF

  if ( CW32System::_dwPlatformId != 1 )
    return LoadLibraryW(a1);
  CStrIn::CStrIn((CStrIn *)lpLibFileName, a1, a3);
  LibraryA = LoadLibraryA(lpLibFileName[0]);
  CConvertStr::Free((CConvertStr *)lpLibFileName);
  return LibraryA;
}

```

## disassembly

```asm
0x18008f8b0  push    rbx
0x18008f8b2  sub     rsp, 250h
0x18008f8b9  mov     rax, cs:__security_cookie
0x18008f8c0  xor     rax, rsp
0x18008f8c3  mov     [rsp+258h+var_18], rax
0x18008f8cb  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18008f8d2  jz      short loc_18008F8DC
0x18008f8d4  call    cs:__imp_LoadLibraryW
0x18008f8da  jmp     short loc_18008F904
0x18008f8dc  mov     rdx, rcx; unsigned __int16 *
0x18008f8df  lea     rcx, [rsp+258h+lpLibFileName]; this
0x18008f8e4  call    ??0CStrIn@@QEAA@PEBGI@Z; CStrIn::CStrIn(ushort const *,uint)
0x18008f8e9  mov     rcx, [rsp+258h+lpLibFileName]; lpLibFileName
0x18008f8ee  call    cs:__imp_LoadLibraryA
0x18008f8f4  lea     rcx, [rsp+258h+lpLibFileName]; this
0x18008f8f9  mov     rbx, rax
0x18008f8fc  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18008f901  mov     rax, rbx
0x18008f904  mov     rcx, [rsp+258h+var_18]
0x18008f90c  xor     rcx, rsp; StackCookie
0x18008f90f  call    __security_check_cookie
0x18008f914  add     rsp, 250h
0x18008f91b  pop     rbx
0x18008f91c  retn
```

# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x180018bcc`
- end: `0x180018c74`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `168`
- prototype: `char __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180019fb8`

## callees

- `0x180018bcc`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180018c43`
- `KERNEL32!GetProcAddress` at `0x180018c43`
- `KERNEL32!GetModuleHandleW` at `0x180018c33`
- `KERNEL32!GetModuleHandleW` at `0x180018c33`

## string_xrefs

- `0x180018c2c`: `ntdll.dll`
- `0x180018c3c`: `RtlAreLongPathsEnabled`

## pseudocode

```c
char __fastcall AreOptionsValidAndOptInLongPathAwareProcess(enum PATHCCH_OPTIONS *a1)
{
  __int64 v2; // rdx
  unsigned __int32 v3; // r9d
  __int64 (*ProcAddress)(void); // rax
  HMODULE ModuleHandleW; // rax
  int v7; // ecx
  enum PATHCCH_OPTIONS v8; // ecx
  char v9; // al

  v2 = *a1 & 6;
  if ( (*a1 & 1) != 0 )
  {
    if ( (_DWORD)v2 && ((v2 - 1) & (unsigned int)v2) != 0 )
      return 0;
  }
  else if ( (_DWORD)v2 )
  {
    return 0;
  }
  v3 = *a1 & 0x11;
  if ( v3 && ((v3 - 1LL) & v3) != 0 )
    return 0;
  if ( (*a1 & 1) != 0 && !(_DWORD)v2 )
  {
    ProcAddress = (__int64 (*)(void))`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled;
    if ( `RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled
      || (ModuleHandleW = GetModuleHandleW(L"ntdll.dll"),
          ProcAddress = GetProcAddress(ModuleHandleW, "RtlAreLongPathsEnabled"),
          (`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled = (__int64)ProcAddress) != 0) )
    {
      v9 = ProcAddress();
      v7 = *a1;
      if ( v9 )
      {
        v8 = v7 | 2;
        goto LABEL_15;
      }
    }
    else
    {
      v7 = *a1;
    }
    v8 = v7 | 4;
LABEL_15:
    *a1 = v8;
  }
  return 1;
}

```

## disassembly

```asm
0x180018bcc  push    rbx
0x180018bce  sub     rsp, 20h
0x180018bd2  mov     r9d, [rcx]
0x180018bd5  mov     rbx, rcx
0x180018bd8  mov     edx, r9d
0x180018bdb  mov     r8d, r9d
0x180018bde  and     edx, 6
0x180018be1  and     r8d, 1
0x180018be5  jz      short loc_180018BF8
0x180018be7  test    edx, edx
0x180018be9  jz      short loc_180018C01
0x180018beb  mov     ecx, edx
0x180018bed  lea     rax, [rdx-1]
0x180018bf1  test    rcx, rax
0x180018bf4  jnz     short loc_180018C13
0x180018bf6  jmp     short loc_180018C01
0x180018bf8  test    edx, edx
0x180018bfa  jz      short loc_180018C01
0x180018bfc  test    r8d, r8d
0x180018bff  jz      short loc_180018C13
0x180018c01  and     r9d, 11h
0x180018c05  jz      short loc_180018C17
0x180018c07  mov     ecx, r9d
0x180018c0a  lea     rax, [r9-1]
0x180018c0e  test    rcx, rax
0x180018c11  jz      short loc_180018C17
0x180018c13  xor     al, al
0x180018c15  jmp     short loc_180018C5E
0x180018c17  test    r8d, r8d
0x180018c1a  jz      short loc_180018C5C
0x180018c1c  test    edx, edx
0x180018c1e  jnz     short loc_180018C5C
0x180018c20  mov     rax, cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180018c27  test    rax, rax
0x180018c2a  jnz     short loc_180018C64
0x180018c2c  lea     rcx, ModuleName; "ntdll.dll"
0x180018c33  call    cs:__imp_GetModuleHandleW
0x180018c39  mov     rcx, rax; hModule
0x180018c3c  lea     rdx, aRtlarelongpath; "RtlAreLongPathsEnabled"
0x180018c43  call    cs:__imp_GetProcAddress
0x180018c49  mov     cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA, rax; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180018c50  test    rax, rax
0x180018c53  jnz     short loc_180018C64
0x180018c55  mov     ecx, [rbx]
0x180018c57  or      ecx, 4
0x180018c5a  mov     [rbx], ecx
0x180018c5c  mov     al, 1
0x180018c5e  add     rsp, 20h
0x180018c62  pop     rbx
0x180018c63  retn
0x180018c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c69  mov     ecx, [rbx]
0x180018c6b  test    al, al
0x180018c6d  jz      short loc_180018C57
0x180018c6f  or      ecx, 2
0x180018c72  jmp     short loc_180018C5A
```

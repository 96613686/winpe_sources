# SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)

- ea: `0x180026d68`
- end: `0x180026e48`
- name: `?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z`
- size: `224`
- prototype: `_BOOL8 __fastcall(signed int, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800276e8`
- `0x180027a90`
- `0x1800281cc`
- `0x180028a08`
- `0x180028d7c`
- `0x18002a3c4`

## callees

- `0x180026d68`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180026dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180026dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026db8`

## string_xrefs

- `0x180026da7`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall SErrorConverterT<CEmptyType>::C_NtStatus2HR(signed int a1, _DWORD *a2)
{
  signed int v3; // ebx
  __int64 (__fastcall *v4)(_QWORD); // rdx
  signed int LastError; // eax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v9; // eax
  HMODULE phModule; // [rsp+40h] [rbp+18h] BYREF

  phModule = 0;
  v3 = a1;
  if ( !a1 )
  {
    *a2 = 0;
    return v3 >= 0;
  }
  v4 = (__int64 (__fastcall *)(_QWORD))_InterlockedCompareExchange64(
                                         &`SErrorConverterT<CEmptyType>::C_NtStatus2HR'::`2'::pfnRtlNtStatusToDosError,
                                         0,
                                         0);
  if ( v4 )
  {
LABEL_12:
    v9 = v4((unsigned int)v3);
    if ( v9 == 317 )
    {
      v3 |= 0x10000000u;
    }
    else if ( v9 > 0 )
    {
      v3 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v3 = v9;
    }
    *a2 = v3;
    if ( v3 >= 0 )
    {
      v3 = -2147467259;
      *a2 = -2147467259;
    }
    return v3 >= 0;
  }
  if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule) )
  {
    ProcAddress = GetProcAddress(phModule, "RtlNtStatusToDosError");
    v4 = (__int64 (__fastcall *)(_QWORD))ProcAddress;
    if ( ProcAddress )
    {
      _InterlockedCompareExchange64(
        &`SErrorConverterT<CEmptyType>::C_NtStatus2HR'::`2'::pfnRtlNtStatusToDosError,
        (signed __int64)ProcAddress,
        0);
      goto LABEL_12;
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = -2147467259;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x180026d68  mov     [rsp+arg_0], rbx
0x180026d6d  push    rdi
0x180026d6e  sub     rsp, 20h
0x180026d72  mov     [rsp+28h+phModule], 0
0x180026d7b  mov     rdi, rdx
0x180026d7e  mov     ebx, ecx
0x180026d80  test    ecx, ecx
0x180026d82  jnz     short loc_180026D8B
0x180026d84  mov     [rdx], ecx
0x180026d86  jmp     loc_180026E36
0x180026d8b  xor     ecx, ecx
0x180026d8d  xor     eax, eax
0x180026d8f  lock cmpxchg cs:?pfnRtlNtStatusToDosError@?1??C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z@4P6AKJ@ZEA, rcx; ulong (*`SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)'::`2'::pfnRtlNtStatusToDosError)(long)
0x180026d98  mov     rdx, rax
0x180026d9b  jnz     short loc_180026E01
0x180026d9d  lea     r8, [rsp+28h+phModule]; phModule
0x180026da2  mov     ecx, 1; dwFlags
0x180026da7  lea     rdx, LibFileName; "ntdll.dll"
0x180026dae  call    cs:__imp_GetModuleHandleExW
0x180026db4  test    eax, eax
0x180026db6  jnz     short loc_180026DDC
0x180026db8  call    cs:__imp_GetLastError
0x180026dbe  mov     ebx, eax
0x180026dc0  test    eax, eax
0x180026dc2  jnz     short loc_180026DCB
0x180026dc4  mov     ebx, 80004005h
0x180026dc9  jmp     short loc_180026DD6
0x180026dcb  jle     short loc_180026DD6
0x180026dcd  movzx   ebx, ax
0x180026dd0  or      ebx, 80070000h
0x180026dd6  mov     [rdi], ebx
0x180026dd8  xor     eax, eax
0x180026dda  jmp     short loc_180026E3D
0x180026ddc  mov     rcx, [rsp+28h+phModule]; hModule
0x180026de1  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosError"
0x180026de8  call    cs:__imp_GetProcAddress
0x180026dee  mov     rdx, rax
0x180026df1  test    rax, rax
0x180026df4  jz      short loc_180026DB8
0x180026df6  xor     eax, eax
0x180026df8  lock cmpxchg cs:?pfnRtlNtStatusToDosError@?1??C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z@4P6AKJ@ZEA, rdx; ulong (*`SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)'::`2'::pfnRtlNtStatusToDosError)(long)
0x180026e01  mov     ecx, ebx
0x180026e03  mov     rax, rdx
0x180026e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e0b  cmp     eax, 13Dh
0x180026e10  jnz     short loc_180026E18
0x180026e12  bts     ebx, 1Ch
0x180026e16  jmp     short loc_180026E29
0x180026e18  test    eax, eax
0x180026e1a  jg      short loc_180026E20
0x180026e1c  mov     ebx, eax
0x180026e1e  jmp     short loc_180026E29
0x180026e20  movzx   ebx, ax
0x180026e23  or      ebx, 80070000h
0x180026e29  mov     [rdi], ebx
0x180026e2b  test    ebx, ebx
0x180026e2d  js      short loc_180026E36
0x180026e2f  mov     ebx, 80004005h
0x180026e34  mov     [rdi], ebx
0x180026e36  not     ebx
0x180026e38  shr     ebx, 1Fh
0x180026e3b  mov     eax, ebx
0x180026e3d  mov     rbx, [rsp+28h+arg_0]
0x180026e42  add     rsp, 20h
0x180026e46  pop     rdi
0x180026e47  retn
```

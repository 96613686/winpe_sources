# try_get_function(`anonymous namespace'::function_id,char const * const,A0x391cf84c::module_id const * const,A0x391cf84c::module_id const * const)

- ea: `0x411ca5`
- end: `0x411d28`
- name: `?try_get_function@@YAPAXW4function_id@?A0x391cf84c@@QBDQBW4module_id@2@2@Z`
- size: `131`
- prototype: `FARPROC __cdecl(int, const CHAR *lpProcName, _DWORD *, _DWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x411baa`
- `0x411bc4`
- `0x411d28`
- `0x411d68`
- `0x411da7`
- `0x411de6`
- `0x411e25`
- `0x411e67`

## callees

- `0x40e40c`
- `0x411bde`
- `0x411ca5`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x411cf1`
- `KERNEL32!GetProcAddress` at `0x411cf1`

## pseudocode

```c
FARPROC __cdecl try_get_function(int a1, const CHAR *lpProcName, _DWORD *a3, _DWORD *a4)
{
  int *v4; // ebx
  int v5; // edx
  HMODULE first_available_module; // eax
  FARPROC ProcAddress; // eax
  FARPROC v9; // esi

  v4 = &dword_418408[a1];
  v5 = __ROR4__(*v4 ^ __security_cookie, __security_cookie & 0x1F);
  if ( v5 == -1 )
    return 0;
  if ( v5 )
    return (FARPROC)v5;
  first_available_module = try_get_first_available_module(a3, a4);
  if ( first_available_module
    && (ProcAddress = GetProcAddress(first_available_module, lpProcName), (v9 = ProcAddress) != 0) )
  {
    _InterlockedExchange(v4, unknown_libname_4(ProcAddress));
    return v9;
  }
  else
  {
    _InterlockedExchange(v4, __security_cookie ^ __ROR4__(-1, 32 - (__security_cookie & 0x1F)));
    return 0;
  }
}

```

## disassembly

```asm
0x411ca5  mov     edi, edi
0x411ca7  push    ebp
0x411ca8  mov     ebp, esp
0x411caa  mov     eax, [ebp+arg_0]
0x411cad  push    ebx
0x411cae  push    edi
0x411caf  lea     ebx, dword_418408[eax*4]
0x411cb6  mov     eax, [ebx]
0x411cb8  nop
0x411cb9  mov     edx, ___security_cookie
0x411cbf  or      edi, 0FFFFFFFFh
0x411cc2  mov     ecx, edx
0x411cc4  xor     edx, eax
0x411cc6  and     ecx, 1Fh
0x411cc9  ror     edx, cl
0x411ccb  cmp     edx, edi
0x411ccd  jnz     short loc_411CD3
0x411ccf  xor     eax, eax
0x411cd1  jmp     short loc_411D24
0x411cd3  test    edx, edx
0x411cd5  jz      short loc_411CDB
0x411cd7  mov     eax, edx
0x411cd9  jmp     short loc_411D24
0x411cdb  push    esi
0x411cdc  push    [ebp+arg_C]
0x411cdf  push    [ebp+arg_8]
0x411ce2  call    ?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z
0x411ce7  pop     ecx
0x411ce8  pop     ecx
0x411ce9  test    eax, eax
0x411ceb  jz      short loc_411D0A
0x411ced  push    [ebp+lpProcName]; lpProcName
0x411cf0  push    eax; hModule
0x411cf1  call    ds:GetProcAddress
0x411cf7  mov     esi, eax
0x411cf9  test    esi, esi
0x411cfb  jz      short loc_411D0A
0x411cfd  push    esi
0x411cfe  call    unknown_libname_4; Microsoft VisualC universal runtime
0x411d03  pop     ecx
0x411d04  xchg    eax, [ebx]
0x411d06  mov     eax, esi
0x411d08  jmp     short loc_411D23
0x411d0a  mov     eax, ___security_cookie
0x411d0f  push    20h ; ' '
0x411d11  and     eax, 1Fh
0x411d14  pop     ecx
0x411d15  sub     ecx, eax
0x411d17  ror     edi, cl
0x411d19  xor     edi, ___security_cookie
0x411d1f  xchg    edi, [ebx]
0x411d21  xor     eax, eax
0x411d23  pop     esi
0x411d24  pop     edi
0x411d25  pop     ebx
0x411d26  pop     ebp
0x411d27  retn
```

# try_get_function(`anonymous namespace'::function_id,char const * const,A0x391cf84c::module_id const * const,A0x391cf84c::module_id const * const)

- ea: `0x4112eb`
- end: `0x41136e`
- name: `?try_get_function@@YAPAXW4function_id@?A0x391cf84c@@QBDQBW4module_id@2@2@Z`
- size: `131`
- prototype: `FARPROC __cdecl(int, const CHAR *lpProcName, _DWORD *, _DWORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4111d6`
- `0x4111f0`
- `0x41120a`
- `0x41136e`
- `0x4113cd`
- `0x41140c`
- `0x41144b`
- `0x41148a`
- `0x4114cc`

## callees

- `0x40b23d`
- `0x411224`
- `0x4112eb`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x411337`
- `KERNEL32!GetProcAddress` at `0x411337`

## pseudocode

```c
FARPROC __cdecl try_get_function(int a1, const CHAR *lpProcName, _DWORD *a3, _DWORD *a4)
{
  int *v4; // ebx
  int v5; // edx
  HMODULE first_available_module; // eax
  FARPROC ProcAddress; // eax
  FARPROC v9; // esi

  v4 = &dword_427270[a1];
  v5 = __ROR4__(*v4 ^ __security_cookie, __security_cookie & 0x1F);
  if ( v5 == -1 )
    return 0;
  if ( v5 )
    return (FARPROC)v5;
  first_available_module = try_get_first_available_module(a3, a4);
  if ( first_available_module
    && (ProcAddress = GetProcAddress(first_available_module, lpProcName), (v9 = ProcAddress) != 0) )
  {
    _InterlockedExchange(v4, unknown_libname_3(ProcAddress));
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
0x4112eb  mov     edi, edi
0x4112ed  push    ebp
0x4112ee  mov     ebp, esp
0x4112f0  mov     eax, [ebp+arg_0]
0x4112f3  push    ebx
0x4112f4  push    edi
0x4112f5  lea     ebx, dword_427270[eax*4]
0x4112fc  mov     eax, [ebx]
0x4112fe  nop
0x4112ff  mov     edx, ___security_cookie
0x411305  or      edi, 0FFFFFFFFh
0x411308  mov     ecx, edx
0x41130a  xor     edx, eax
0x41130c  and     ecx, 1Fh
0x41130f  ror     edx, cl
0x411311  cmp     edx, edi
0x411313  jnz     short loc_411319
0x411315  xor     eax, eax
0x411317  jmp     short loc_41136A
0x411319  test    edx, edx
0x41131b  jz      short loc_411321
0x41131d  mov     eax, edx
0x41131f  jmp     short loc_41136A
0x411321  push    esi
0x411322  push    [ebp+arg_C]
0x411325  push    [ebp+arg_8]
0x411328  call    ?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z
0x41132d  pop     ecx
0x41132e  pop     ecx
0x41132f  test    eax, eax
0x411331  jz      short loc_411350
0x411333  push    [ebp+lpProcName]; lpProcName
0x411336  push    eax; hModule
0x411337  call    ds:GetProcAddress
0x41133d  mov     esi, eax
0x41133f  test    esi, esi
0x411341  jz      short loc_411350
0x411343  push    esi
0x411344  call    unknown_libname_3; Microsoft VisualC universal runtime
0x411349  pop     ecx
0x41134a  xchg    eax, [ebx]
0x41134c  mov     eax, esi
0x41134e  jmp     short loc_411369
0x411350  mov     eax, ___security_cookie
0x411355  push    20h ; ' '
0x411357  and     eax, 1Fh
0x41135a  pop     ecx
0x41135b  sub     ecx, eax
0x41135d  ror     edi, cl
0x41135f  xor     edi, ___security_cookie
0x411365  xchg    edi, [ebx]
0x411367  xor     eax, eax
0x411369  pop     esi
0x41136a  pop     edi
0x41136b  pop     ebx
0x41136c  pop     ebp
0x41136d  retn
```

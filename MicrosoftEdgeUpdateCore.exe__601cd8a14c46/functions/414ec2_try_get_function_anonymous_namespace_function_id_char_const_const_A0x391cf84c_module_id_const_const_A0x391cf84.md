# try_get_function(`anonymous namespace'::function_id,char const * const,A0x391cf84c::module_id const * const,A0x391cf84c::module_id const * const)

- ea: `0x414ec2`
- end: `0x414f45`
- name: `?try_get_function@@YAPAXW4function_id@?A0x391cf84c@@QBDQBW4module_id@2@2@Z`
- size: `131`
- prototype: `FARPROC __cdecl(int, const CHAR *lpProcName, _DWORD *, _DWORD *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x414dc7`
- `0x414de1`
- `0x414f45`
- `0x414f85`
- `0x414fc5`
- `0x415004`
- `0x415043`
- `0x415085`
- `0x41515e`

## callees

- `0x410668`
- `0x414dfb`
- `0x414ec2`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x414f0e`
- `KERNEL32!GetProcAddress` at `0x414f0e`

## pseudocode

```c
FARPROC __cdecl try_get_function(int a1, const CHAR *lpProcName, _DWORD *a3, _DWORD *a4)
{
  int *v4; // ebx
  int v5; // edx
  HMODULE first_available_module; // eax
  FARPROC ProcAddress; // eax
  FARPROC v9; // esi

  v4 = &dword_43E4F8[a1];
  v5 = __ROR4__(*v4 ^ __security_cookie, __security_cookie & 0x1F);
  if ( v5 == -1 )
    return 0;
  if ( v5 )
    return (FARPROC)v5;
  first_available_module = try_get_first_available_module(a3, a4);
  if ( first_available_module
    && (ProcAddress = GetProcAddress(first_available_module, lpProcName), (v9 = ProcAddress) != 0) )
  {
    _InterlockedExchange(v4, unknown_libname_6(ProcAddress));
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
0x414ec2  mov     edi, edi
0x414ec4  push    ebp
0x414ec5  mov     ebp, esp
0x414ec7  mov     eax, [ebp+arg_0]
0x414eca  push    ebx
0x414ecb  push    edi
0x414ecc  lea     ebx, dword_43E4F8[eax*4]
0x414ed3  mov     eax, [ebx]
0x414ed5  nop
0x414ed6  mov     edx, ___security_cookie
0x414edc  or      edi, 0FFFFFFFFh
0x414edf  mov     ecx, edx
0x414ee1  xor     edx, eax
0x414ee3  and     ecx, 1Fh
0x414ee6  ror     edx, cl
0x414ee8  cmp     edx, edi
0x414eea  jnz     short loc_414EF0
0x414eec  xor     eax, eax
0x414eee  jmp     short loc_414F41
0x414ef0  test    edx, edx
0x414ef2  jz      short loc_414EF8
0x414ef4  mov     eax, edx
0x414ef6  jmp     short loc_414F41
0x414ef8  push    esi
0x414ef9  push    [ebp+arg_C]
0x414efc  push    [ebp+arg_8]
0x414eff  call    ?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z
0x414f04  pop     ecx
0x414f05  pop     ecx
0x414f06  test    eax, eax
0x414f08  jz      short loc_414F27
0x414f0a  push    [ebp+lpProcName]; lpProcName
0x414f0d  push    eax; hModule
0x414f0e  call    ds:GetProcAddress
0x414f14  mov     esi, eax
0x414f16  test    esi, esi
0x414f18  jz      short loc_414F27
0x414f1a  push    esi
0x414f1b  call    unknown_libname_6; Microsoft VisualC universal runtime
0x414f20  pop     ecx
0x414f21  xchg    eax, [ebx]
0x414f23  mov     eax, esi
0x414f25  jmp     short loc_414F40
0x414f27  mov     eax, ___security_cookie
0x414f2c  push    20h ; ' '
0x414f2e  and     eax, 1Fh
0x414f31  pop     ecx
0x414f32  sub     ecx, eax
0x414f34  ror     edi, cl
0x414f36  xor     edi, ___security_cookie
0x414f3c  xchg    edi, [ebx]
0x414f3e  xor     eax, eax
0x414f40  pop     esi
0x414f41  pop     edi
0x414f42  pop     ebx
0x414f43  pop     ebp
0x414f44  retn
```

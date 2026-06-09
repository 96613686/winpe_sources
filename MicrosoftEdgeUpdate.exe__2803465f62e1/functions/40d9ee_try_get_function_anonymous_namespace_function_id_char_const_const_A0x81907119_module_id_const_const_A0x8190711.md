# try_get_function(`anonymous namespace'::function_id,char const * const,A0x81907119::module_id const * const,A0x81907119::module_id const * const)

- ea: `0x40d9ee`
- end: `0x40da38`
- name: `?try_get_function@@YAPAXW4function_id@?A0x81907119@@QBDQBW4module_id@2@2@Z`
- size: `74`
- prototype: `FARPROC __cdecl(int, const CHAR *lpProcName, _DWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x40da38`
- `0x40da73`
- `0x40daae`
- `0x40dae9`
- `0x40db27`

## callees

- `0x40d953`
- `0x40d9ee`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40da20`
- `KERNEL32!GetProcAddress` at `0x40da20`

## pseudocode

```c
FARPROC __cdecl try_get_function(int a1, const CHAR *lpProcName, _DWORD *a3, _DWORD *a4)
{
  int *v4; // edi
  FARPROC result; // eax
  HMODULE first_available_module; // eax

  v4 = &dword_417DA8[a1];
  result = (FARPROC)*v4;
  if ( *v4 != -1 )
  {
    if ( result )
      return result;
    first_available_module = try_get_first_available_module(a3, a4);
    if ( first_available_module )
    {
      result = GetProcAddress(first_available_module, lpProcName);
      if ( result )
      {
        _InterlockedExchange(v4, (__int32)result);
        return result;
      }
    }
    _InterlockedExchange(v4, -1);
  }
  return 0;
}

```

## disassembly

```asm
0x40d9ee  push    ebp
0x40d9ef  mov     ebp, esp
0x40d9f1  mov     eax, [ebp+arg_0]
0x40d9f4  push    esi
0x40d9f5  push    edi
0x40d9f6  lea     edi, dword_417DA8[eax*4]
0x40d9fd  mov     eax, [edi]
0x40d9ff  nop
0x40da00  or      esi, 0FFFFFFFFh
0x40da03  cmp     eax, esi
0x40da05  jz      short loc_40DA32
0x40da07  test    eax, eax
0x40da09  jnz     short loc_40DA34
0x40da0b  push    [ebp+arg_C]
0x40da0e  push    [ebp+arg_8]
0x40da11  call    ?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z
0x40da16  pop     ecx
0x40da17  pop     ecx
0x40da18  test    eax, eax
0x40da1a  jz      short loc_40DA30
0x40da1c  push    [ebp+lpProcName]; lpProcName
0x40da1f  push    eax; hModule
0x40da20  call    ds:GetProcAddress
0x40da26  test    eax, eax
0x40da28  jz      short loc_40DA30
0x40da2a  mov     ecx, eax
0x40da2c  xchg    ecx, [edi]
0x40da2e  jmp     short loc_40DA34
0x40da30  xchg    esi, [edi]
0x40da32  xor     eax, eax
0x40da34  pop     edi
0x40da35  pop     esi
0x40da36  pop     ebp
0x40da37  retn
```

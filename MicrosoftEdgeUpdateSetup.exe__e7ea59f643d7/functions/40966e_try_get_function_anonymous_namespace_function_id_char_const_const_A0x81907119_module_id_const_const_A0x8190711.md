# try_get_function(`anonymous namespace'::function_id,char const * const,A0x81907119::module_id const * const,A0x81907119::module_id const * const)

- ea: `0x40966e`
- end: `0x4096b8`
- name: `?try_get_function@@YAPAXW4function_id@?A0x81907119@@QBDQBW4module_id@2@2@Z`
- size: `74`
- prototype: `FARPROC __cdecl(int, const CHAR *lpProcName, _DWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x4096b8`
- `0x4096f3`
- `0x40972e`
- `0x409769`
- `0x4097a7`

## callees

- `0x4095d3`
- `0x40966e`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x4096a0`
- `KERNEL32!GetProcAddress` at `0x4096a0`

## pseudocode

```c
FARPROC __cdecl try_get_function(int a1, const CHAR *lpProcName, _DWORD *a3, _DWORD *a4)
{
  int *v4; // edi
  FARPROC result; // eax
  HMODULE first_available_module; // eax

  v4 = &dword_426D1C[a1];
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
0x40966e  push    ebp
0x40966f  mov     ebp, esp
0x409671  mov     eax, [ebp+arg_0]
0x409674  push    esi
0x409675  push    edi
0x409676  lea     edi, dword_426D1C[eax*4]
0x40967d  mov     eax, [edi]
0x40967f  nop
0x409680  or      esi, 0FFFFFFFFh
0x409683  cmp     eax, esi
0x409685  jz      short loc_4096B2
0x409687  test    eax, eax
0x409689  jnz     short loc_4096B4
0x40968b  push    [ebp+arg_C]
0x40968e  push    [ebp+arg_8]
0x409691  call    ?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z
0x409696  pop     ecx
0x409697  pop     ecx
0x409698  test    eax, eax
0x40969a  jz      short loc_4096B0
0x40969c  push    [ebp+lpProcName]; lpProcName
0x40969f  push    eax; hModule
0x4096a0  call    ds:GetProcAddress
0x4096a6  test    eax, eax
0x4096a8  jz      short loc_4096B0
0x4096aa  mov     ecx, eax
0x4096ac  xchg    ecx, [edi]
0x4096ae  jmp     short loc_4096B4
0x4096b0  xchg    esi, [edi]
0x4096b2  xor     eax, eax
0x4096b4  pop     edi
0x4096b5  pop     esi
0x4096b6  pop     ebp
0x4096b7  retn
```

# IsPageheapEnabled(void)

- ea: `0x180034864`
- end: `0x1800348be`
- name: `?IsPageheapEnabled@@YAHXZ`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003366c`

## callees

- `0x180034864`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034880`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034880`

## string_xrefs

- `0x180034879`: `verifier.dll`

## pseudocode

```c
__int64 IsPageheapEnabled(void)
{
  __int64 result; // rax

  if ( dword_180060018 )
    return (unsigned int)dword_180060014;
  if ( GetModuleHandleW(L"verifier.dll") )
  {
    result = 1;
  }
  else
  {
    result = (__int64)NtCurrentPeb();
    if ( result )
      result = (*(_DWORD *)(result + 188) >> 25) & 1;
  }
  dword_180060014 = result;
  dword_180060018 = 1;
  return result;
}

```

## disassembly

```asm
0x180034864  sub     rsp, 28h
0x180034868  cmp     cs:dword_180060018, 0
0x18003486f  jz      short loc_180034879
0x180034871  mov     eax, cs:dword_180060014
0x180034877  jmp     short loc_1800348B9
0x180034879  lea     rcx, aVerifierDll; "verifier.dll"
0x180034880  call    cs:__imp_GetModuleHandleW
0x180034886  mov     ecx, 1
0x18003488b  test    rax, rax
0x18003488e  jz      short loc_180034894
0x180034890  mov     eax, ecx
0x180034892  jmp     short loc_1800348AD
0x180034894  mov     rax, gs:60h
0x18003489d  test    rax, rax
0x1800348a0  jz      short loc_1800348AD
0x1800348a2  mov     eax, [rax+0BCh]
0x1800348a8  shr     eax, 19h
0x1800348ab  and     eax, ecx
0x1800348ad  mov     cs:dword_180060014, eax
0x1800348b3  mov     cs:dword_180060018, ecx
0x1800348b9  add     rsp, 28h
0x1800348bd  retn
```

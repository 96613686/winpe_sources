# HRESULTFromLastErrorError(void)

- ea: `0x4066c4`
- end: `0x4066f6`
- name: `?HRESULTFromLastErrorError@@YGJXZ`
- size: `50`
- prototype: `DWORD __stdcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x407d14`
- `0x407eab`
- `0x4083bc`

## callees

- `0x4066c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x4066c4`
- `KERNEL32!GetLastError` at `0x4066d0`
- `KERNEL32!GetLastError` at `0x4066df`
- `KERNEL32!GetLastError` at `0x4066c4`
- `KERNEL32!GetLastError` at `0x4066d0`
- `KERNEL32!GetLastError` at `0x4066df`

## pseudocode

```c
DWORD __stdcall HRESULTFromLastErrorError()
{
  DWORD result; // eax
  DWORD LastError; // eax

  if ( (GetLastError() & 0x80000000) == 0 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LOWORD(LastError) = 1;
    return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    result = GetLastError();
    if ( !result )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x4066c4  call    ds:__imp__GetLastError@0; GetLastError()
0x4066ca  test    eax, eax
0x4066cc  jz      short loc_4066DF
0x4066ce  jg      short loc_4066DF
0x4066d0  call    ds:__imp__GetLastError@0; GetLastError()
0x4066d6  xor     ecx, ecx
0x4066d8  inc     ecx
0x4066d9  test    eax, eax
0x4066db  cmovz   eax, ecx
0x4066de  retn
0x4066df  call    ds:__imp__GetLastError@0; GetLastError()
0x4066e5  xor     ecx, ecx
0x4066e7  inc     ecx
0x4066e8  test    eax, eax
0x4066ea  cmovz   eax, ecx
0x4066ed  movzx   eax, ax
0x4066f0  or      eax, 80070000h
0x4066f5  retn
```

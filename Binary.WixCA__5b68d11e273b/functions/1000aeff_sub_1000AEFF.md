# sub_1000AEFF

- ea: `0x1000aeff`
- end: `0x1000af36`
- name: `sub_1000AEFF`
- size: `55`
- prototype: `int __stdcall(LPVOID lpMem)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x100012eb`
- `0x10001416`
- `0x10001515`
- `0x1000196c`
- `0x1000530d`
- `0x1000582e`
- `0x100069b8`
- `0x100070ac`
- `0x10007d8c`
- `0x100083f0`
- `0x1000852f`
- `0x1000942a`
- `0x10009a3e`
- `0x1000a91f`
- `0x1000a952`
- `0x1000a991`
- `0x1000af5e`
- `0x1000b1df`
- `0x1000b616`
- `0x1000ba7f`
- `0x1000bbf8`
- `0x1000bdbd`
- `0x1000c0be`
- `0x1000c162`
- `0x1000c245`
- `0x1000c2da`
- `0x1000f6f2`
- `0x1000f9cc`
- `0x1000ffdb`

## callees

- `0x1000aeff`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000af1a`
- `KERNEL32!GetLastError` at `0x1000af1a`
- `KERNEL32!HeapFree` at `0x1000af10`
- `KERNEL32!HeapFree` at `0x1000af10`
- `KERNEL32!GetProcessHeap` at `0x1000af09`
- `KERNEL32!GetProcessHeap` at `0x1000af09`

## pseudocode

```c
unsigned int __stdcall sub_1000AEFF(LPVOID lpMem)
{
  signed int v1; // esi
  HANDLE ProcessHeap; // eax
  signed int LastError; // eax

  v1 = 0;
  ProcessHeap = GetProcessHeap();
  if ( !HeapFree(ProcessHeap, 0, lpMem) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1000aeff  push    ebp
0x1000af00  mov     ebp, esp
0x1000af02  push    esi
0x1000af03  push    [ebp+lpMem]; lpMem
0x1000af06  xor     esi, esi
0x1000af08  push    esi; dwFlags
0x1000af09  call    ds:GetProcessHeap
0x1000af0f  push    eax; hHeap
0x1000af10  call    ds:HeapFree
0x1000af16  test    eax, eax
0x1000af18  jnz     short loc_1000AF2F
0x1000af1a  call    ds:GetLastError
0x1000af20  mov     esi, eax
0x1000af22  test    esi, esi
0x1000af24  jle     short loc_1000AF2F
0x1000af26  movzx   esi, si
0x1000af29  or      esi, 80070000h
0x1000af2f  mov     eax, esi
0x1000af31  pop     esi
0x1000af32  pop     ebp
0x1000af33  retn    4
```

# mlib::RstringReg::writeIt(void)

- ea: `0x18002e460`
- end: `0x18002e4ba`
- name: `?writeIt@RstringReg@mlib@@MEAAHXZ`
- size: `90`
- prototype: `__int64 __fastcall(mlib::RstringReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e4a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e4a0`

## pseudocode

```c
_BOOL8 __fastcall mlib::RstringReg::writeIt(HKEY *this)
{
  LSTATUS v1; // ebx

  v1 = RegSetValueExW(this[1], *((LPCWSTR *)this[6] + 3), 0, 1u, *((const BYTE **)this[9] + 3), 2 * *(_DWORD *)this[9]);
  SetLastError(v1);
  return v1 != 0;
}

```

## disassembly

```asm
0x18002e460  push    rbx
0x18002e462  sub     rsp, 30h
0x18002e466  mov     rax, [rcx+48h]
0x18002e46a  mov     r9d, 1; dwType
0x18002e470  mov     edx, [rax]
0x18002e472  mov     r8, [rax+18h]
0x18002e476  add     edx, edx
0x18002e478  mov     rax, [rcx+30h]
0x18002e47c  mov     rcx, [rcx+8]; hKey
0x18002e480  mov     [rsp+38h+cbData], edx; cbData
0x18002e484  mov     [rsp+38h+lpData], r8; lpData
0x18002e489  xor     r8d, r8d; Reserved
0x18002e48c  mov     rdx, [rax+18h]; lpValueName
0x18002e490  call    cs:__imp_RegSetValueExW
0x18002e497  nop     dword ptr [rax+rax+00h]
0x18002e49c  mov     ecx, eax; dwErrCode
0x18002e49e  mov     ebx, eax
0x18002e4a0  call    cs:__imp_SetLastError
0x18002e4a7  nop     dword ptr [rax+rax+00h]
0x18002e4ac  xor     eax, eax
0x18002e4ae  test    ebx, ebx
0x18002e4b0  setnz   al
0x18002e4b3  add     rsp, 30h
0x18002e4b7  pop     rbx
0x18002e4b8  retn
```

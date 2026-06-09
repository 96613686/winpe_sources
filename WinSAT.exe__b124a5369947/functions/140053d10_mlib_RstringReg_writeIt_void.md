# mlib::RstringReg::writeIt(void)

- ea: `0x140053d10`
- end: `0x140053d5e`
- name: `?writeIt@RstringReg@mlib@@MEAAHXZ`
- size: `78`
- prototype: `__int64 __fastcall(mlib::RstringReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140053d41`
- `ADVAPI32!RegSetValueExW` at `0x140053d41`
- `KERNEL32!SetLastError` at `0x140053d4b`
- `KERNEL32!SetLastError` at `0x140053d4b`

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
0x140053d10  push    rbx
0x140053d12  sub     rsp, 30h
0x140053d16  mov     r8, [rcx+48h]
0x140053d1a  mov     r9d, 1; dwType
0x140053d20  mov     rdx, [rcx+30h]
0x140053d24  mov     rcx, [rcx+8]; hKey
0x140053d28  mov     eax, [r8]
0x140053d2b  mov     rdx, [rdx+18h]; lpValueName
0x140053d2f  add     eax, eax
0x140053d31  mov     [rsp+38h+cbData], eax; cbData
0x140053d35  mov     rax, [r8+18h]
0x140053d39  xor     r8d, r8d; Reserved
0x140053d3c  mov     [rsp+38h+lpData], rax; lpData
0x140053d41  call    cs:__imp_RegSetValueExW
0x140053d47  mov     ecx, eax; dwErrCode
0x140053d49  mov     ebx, eax
0x140053d4b  call    cs:__imp_SetLastError
0x140053d51  xor     eax, eax
0x140053d53  test    ebx, ebx
0x140053d55  setnz   al
0x140053d58  add     rsp, 30h
0x140053d5c  pop     rbx
0x140053d5d  retn
```

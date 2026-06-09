# mlib::DWORDReg::writeIt(void)

- ea: `0x18002e400`
- end: `0x18002e453`
- name: `?writeIt@DWORDReg@mlib@@MEAAHXZ`
- size: `83`
- prototype: `__int64 __fastcall(mlib::DWORDReg *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e439`

## pseudocode

```c
_BOOL8 __fastcall mlib::DWORDReg::writeIt(mlib::DWORDReg *this)
{
  LSTATUS v1; // ebx

  v1 = RegSetValueExW(
         *((HKEY *)this + 1),
         *(LPCWSTR *)(*((_QWORD *)this + 6) + 24LL),
         0,
         4u,
         (const BYTE *)this + 72,
         4u);
  SetLastError(v1);
  return v1 != 0;
}

```

## disassembly

```asm
0x18002e400  push    rbx
0x18002e402  sub     rsp, 30h
0x18002e406  mov     rax, [rcx+30h]
0x18002e40a  mov     r9d, 4; dwType
0x18002e410  mov     [rsp+38h+cbData], r9d; cbData
0x18002e415  xor     r8d, r8d; Reserved
0x18002e418  mov     rdx, [rax+18h]; lpValueName
0x18002e41c  lea     rax, [rcx+48h]
0x18002e420  mov     rcx, [rcx+8]; hKey
0x18002e424  mov     [rsp+38h+lpData], rax; lpData
0x18002e429  call    cs:__imp_RegSetValueExW
0x18002e430  nop     dword ptr [rax+rax+00h]
0x18002e435  mov     ecx, eax; dwErrCode
0x18002e437  mov     ebx, eax
0x18002e439  call    cs:__imp_SetLastError
0x18002e440  nop     dword ptr [rax+rax+00h]
0x18002e445  xor     eax, eax
0x18002e447  test    ebx, ebx
0x18002e449  setnz   al
0x18002e44c  add     rsp, 30h
0x18002e450  pop     rbx
0x18002e451  retn
```

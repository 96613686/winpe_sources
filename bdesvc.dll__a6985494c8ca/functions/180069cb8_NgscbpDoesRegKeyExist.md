# NgscbpDoesRegKeyExist

- ea: `0x180069cb8`
- end: `0x180069d4a`
- name: `NgscbpDoesRegKeyExist`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18006a348`
- `0x18006ad70`

## callees

- `0x180069cb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069cf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d23`

## pseudocode

```c
__int64 __fastcall NgscbpDoesRegKeyExist(__int64 a1, __int64 a2, _DWORD *a3)
{
  LSTATUS v4; // eax
  int v5; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      *a3 = 0;
      v5 = 0;
    }
  }
  else
  {
    *a3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180069cb8  mov     r11, rsp
0x180069cbb  mov     [r11+8], rbx
0x180069cbf  mov     [r11+10h], rdx
0x180069cc3  push    rdi
0x180069cc4  sub     rsp, 30h
0x180069cc8  mov     rdi, r8
0x180069ccb  mov     qword ptr [r11+10h], 0
0x180069cd3  lea     rax, [r11+10h]
0x180069cd7  xor     r8d, r8d; ulOptions
0x180069cda  mov     r9d, 20019h; samDesired
0x180069ce0  mov     [r11-18h], rax
0x180069ce4  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180069ceb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069cf2  call    cs:__imp_RegOpenKeyExW
0x180069cf9  nop     dword ptr [rax+rax+00h]
0x180069cfe  mov     ebx, eax
0x180069d00  test    eax, eax
0x180069d02  jnz     short loc_180069D0C
0x180069d04  mov     dword ptr [rdi], 1
0x180069d0a  jmp     short loc_180069D19
0x180069d0c  cmp     eax, 2
0x180069d0f  jnz     short loc_180069D19
0x180069d11  mov     dword ptr [rdi], 0
0x180069d17  xor     ebx, ebx
0x180069d19  mov     rcx, [rsp+38h+hKey]; hKey
0x180069d1e  test    rcx, rcx
0x180069d21  jz      short loc_180069D2F
0x180069d23  call    cs:__imp_RegCloseKey
0x180069d2a  nop     dword ptr [rax+rax+00h]
0x180069d2f  test    ebx, ebx
0x180069d31  jle     short loc_180069D3C
0x180069d33  movzx   ebx, bx
0x180069d36  or      ebx, 80070000h
0x180069d3c  mov     eax, ebx
0x180069d3e  mov     rbx, [rsp+38h+arg_0]
0x180069d43  add     rsp, 30h
0x180069d47  pop     rdi
0x180069d48  retn
```

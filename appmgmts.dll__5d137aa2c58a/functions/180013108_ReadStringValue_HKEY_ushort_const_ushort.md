# ReadStringValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180013108`
- end: `0x1800131cd`
- name: `?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `197`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpValueName, HLOCAL *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800061f8`

## callees

- `0x180013108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013146`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001319f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013146`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001319f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001316f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001316f`

## pseudocode

```c
LSTATUS __fastcall ReadStringValue(HKEY hKey, LPCWSTR lpValueName, HLOCAL *a3)
{
  LSTATUS result; // eax
  SIZE_T v7; // rax
  unsigned __int16 *lpData; // rax
  LSTATUS v9; // edi
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  cbData = 0;
  result = RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData);
  if ( !result )
  {
    v7 = 2 * ((unsigned __int64)cbData >> 1);
    if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
      v7 = -1;
    lpData = (unsigned __int16 *)LocalAlloc(0, v7);
    *a3 = lpData;
    if ( lpData )
    {
      v9 = RegQueryValueExW(hKey, lpValueName, 0, 0, (LPBYTE)lpData, &cbData);
      if ( v9 )
      {
        LocalFree(*a3);
        *a3 = 0;
      }
      return v9;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013108  mov     r11, rsp
0x18001310b  mov     [r11+8], rbx
0x18001310f  mov     [r11+10h], rsi
0x180013113  push    rdi
0x180013114  sub     rsp, 30h
0x180013118  lea     rax, [r11+18h]
0x18001311c  mov     qword ptr [r8], 0
0x180013123  mov     rbx, r8
0x180013126  mov     [r11-10h], rax
0x18001312a  xor     r9d, r9d; lpType
0x18001312d  mov     qword ptr [r11-18h], 0
0x180013135  xor     r8d, r8d; lpReserved
0x180013138  mov     [rsp+38h+cbData], 0
0x180013140  mov     rdi, rdx
0x180013143  mov     rsi, rcx
0x180013146  call    cs:__imp_RegQueryValueExW
0x18001314c  test    eax, eax
0x18001314e  jnz     short loc_1800131BD
0x180013150  mov     ecx, [rsp+38h+cbData]
0x180013154  mov     eax, 2
0x180013159  shr     rcx, 1
0x18001315c  mul     rcx
0x18001315f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013166  cmovb   rax, rcx
0x18001316a  xor     ecx, ecx; uFlags
0x18001316c  mov     rdx, rax; uBytes
0x18001316f  call    cs:__imp_LocalAlloc
0x180013175  mov     [rbx], rax
0x180013178  test    rax, rax
0x18001317b  jnz     short loc_180013184
0x18001317d  mov     eax, 0Eh
0x180013182  jmp     short loc_1800131BD
0x180013184  lea     rcx, [rsp+38h+cbData]
0x180013189  xor     r9d, r9d; lpType
0x18001318c  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x180013191  xor     r8d, r8d; lpReserved
0x180013194  mov     rcx, rsi; hKey
0x180013197  mov     [rsp+38h+lpData], rax; lpData
0x18001319c  mov     rdx, rdi; lpValueName
0x18001319f  call    cs:__imp_RegQueryValueExW
0x1800131a5  mov     edi, eax
0x1800131a7  test    eax, eax
0x1800131a9  jz      short loc_1800131BB
0x1800131ab  mov     rcx, [rbx]; hMem
0x1800131ae  call    cs:__imp_LocalFree
0x1800131b4  mov     qword ptr [rbx], 0
0x1800131bb  mov     eax, edi
0x1800131bd  mov     rbx, [rsp+38h+arg_0]
0x1800131c2  mov     rsi, [rsp+38h+arg_8]
0x1800131c7  add     rsp, 30h
0x1800131cb  pop     rdi
0x1800131cc  retn
```

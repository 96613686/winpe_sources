# GetHelperDllFullPath

- ea: `0x180002ca8`
- end: `0x180002d65`
- name: `GetHelperDllFullPath`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002da8`

## callees

- `0x180002ca8`
- `0x18024cd20`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180002d24`
- `msvcrt!swprintf_s` at `0x180002d24`
- `msvcrt!malloc` at `0x180002cf0`
- `msvcrt!malloc` at `0x180002cf0`
- `msvcrt!free` at `0x180002d38`
- `msvcrt!free` at `0x180002d38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002cd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002cd4`

## string_xrefs

- `0x180002d04`: `wmitomi.dll`

## pseudocode

```c
void *GetHelperDllFullPath()
{
  signed int SystemDirectoryW; // eax
  void *v1; // rbx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  Buffer[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return 0;
  if ( SystemDirectoryW > 260 )
    return 0;
  v1 = malloc(0x208u);
  if ( !v1 )
    return 0;
  if ( swprintf_s((wchar_t *const)v1, 0x104u, L"%s\\%s", Buffer, L"wmitomi.dll") == -1 )
  {
    free(v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180002ca8  push    rbx
0x180002caa  sub     rsp, 250h
0x180002cb1  mov     rax, cs:__security_cookie
0x180002cb8  xor     rax, rsp
0x180002cbb  mov     [rsp+258h+var_18], rax
0x180002cc3  xor     eax, eax
0x180002cc5  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180002cca  mov     edx, 104h; uSize
0x180002ccf  mov     [rsp+258h+Buffer], ax
0x180002cd4  call    cs:__imp_GetSystemDirectoryW
0x180002cdb  nop     dword ptr [rax+rax+00h]
0x180002ce0  test    eax, eax
0x180002ce2  jz      short loc_180002D44
0x180002ce4  cmp     eax, 104h
0x180002ce9  jg      short loc_180002D44
0x180002ceb  mov     ecx, 208h; Size
0x180002cf0  call    cs:__imp_malloc
0x180002cf7  nop     dword ptr [rax+rax+00h]
0x180002cfc  mov     rbx, rax
0x180002cff  test    rax, rax
0x180002d02  jz      short loc_180002D44
0x180002d04  lea     rax, aWmitomiDll; "wmitomi.dll"
0x180002d0b  mov     edx, 104h; BufferCount
0x180002d10  lea     r9, [rsp+258h+Buffer]
0x180002d15  mov     [rsp+258h+var_238], rax
0x180002d1a  lea     r8, aSS; "%s\\%s"
0x180002d21  mov     rcx, rbx; Buffer
0x180002d24  call    cs:__imp_swprintf_s
0x180002d2b  nop     dword ptr [rax+rax+00h]
0x180002d30  cmp     eax, 0FFFFFFFFh
0x180002d33  jnz     short loc_180002D60
0x180002d35  mov     rcx, rbx; Block
0x180002d38  call    cs:__imp_free
0x180002d3f  nop     dword ptr [rax+rax+00h]
0x180002d44  xor     eax, eax
0x180002d46  mov     rcx, [rsp+258h+var_18]
0x180002d4e  xor     rcx, rsp; StackCookie
0x180002d51  call    __security_check_cookie
0x180002d56  add     rsp, 250h
0x180002d5d  pop     rbx
0x180002d5e  retn
0x180002d60  mov     rax, rbx
0x180002d63  jmp     short loc_180002D46
```

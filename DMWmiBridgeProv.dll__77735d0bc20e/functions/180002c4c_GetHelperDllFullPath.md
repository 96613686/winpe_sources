# GetHelperDllFullPath

- ea: `0x180002c4c`
- end: `0x180002cf0`
- name: `GetHelperDllFullPath`
- size: `164`
- prototype: `void *()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d38`

## callees

- `0x180002c4c`
- `0x18024d160`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180002cbc`
- `msvcrt!swprintf_s` at `0x180002cbc`
- `msvcrt!malloc` at `0x180002c8e`
- `msvcrt!malloc` at `0x180002c8e`
- `msvcrt!free` at `0x180002cca`
- `msvcrt!free` at `0x180002cca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002c78`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180002c78`

## string_xrefs

- `0x180002c9c`: `wmitomi.dll`

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
0x180002c4c  push    rbx
0x180002c4e  sub     rsp, 250h
0x180002c55  mov     rax, cs:__security_cookie
0x180002c5c  xor     rax, rsp
0x180002c5f  mov     [rsp+258h+var_18], rax
0x180002c67  xor     eax, eax
0x180002c69  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180002c6e  mov     edx, 104h; uSize
0x180002c73  mov     [rsp+258h+Buffer], ax
0x180002c78  call    cs:__imp_GetSystemDirectoryW
0x180002c7e  test    eax, eax
0x180002c80  jz      short loc_180002CD0
0x180002c82  cmp     eax, 104h
0x180002c87  jg      short loc_180002CD0
0x180002c89  mov     ecx, 208h; Size
0x180002c8e  call    cs:__imp_malloc
0x180002c94  mov     rbx, rax
0x180002c97  test    rax, rax
0x180002c9a  jz      short loc_180002CD0
0x180002c9c  lea     rax, aWmitomiDll; "wmitomi.dll"
0x180002ca3  mov     edx, 104h; BufferCount
0x180002ca8  lea     r9, [rsp+258h+Buffer]
0x180002cad  mov     [rsp+258h+var_238], rax
0x180002cb2  lea     r8, aSS; "%s\\%s"
0x180002cb9  mov     rcx, rbx; Buffer
0x180002cbc  call    cs:__imp_swprintf_s
0x180002cc2  cmp     eax, 0FFFFFFFFh
0x180002cc5  jnz     short loc_180002CEB
0x180002cc7  mov     rcx, rbx; Block
0x180002cca  call    cs:__imp_free
0x180002cd0  xor     eax, eax
0x180002cd2  mov     rcx, [rsp+258h+var_18]
0x180002cda  xor     rcx, rsp; StackCookie
0x180002cdd  call    __security_check_cookie
0x180002ce2  add     rsp, 250h
0x180002ce9  pop     rbx
0x180002cea  retn
0x180002ceb  mov     rax, rbx
0x180002cee  jmp     short loc_180002CD2
```

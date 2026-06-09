# ImageDirectoryRvaAndSize

- ea: `0x180004e98`
- end: `0x180004ee7`
- name: `ImageDirectoryRvaAndSize`
- size: `79`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004db8`
- `0x180004e48`
- `0x18000677c`
- `0x180006858`

## callees

- `0x180004e98`
- `0x180005400`

## pseudocode

```c
__int64 __fastcall ImageDirectoryRvaAndSize(
        __int64 a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned __int64 a4,
        unsigned int a5)
{
  unsigned __int64 v6; // rcx

  if ( a2 >= *(_DWORD *)(a1 + 116) )
    return 0;
  v6 = a1 + 8 * (a2 + 15LL);
  if ( v6 < a4 || v6 >= v6 + 8 || v6 + 8 > a4 + a5 )
  {
    ThrowPeFmtException();
    JUMPOUT(0x180004EE6LL);
  }
  if ( a3 )
    *a3 = *(_DWORD *)(a1 + 8LL * a2 + 124);
  return *(unsigned int *)(a1 + 8LL * a2 + 120);
}

```

## disassembly

```asm
0x180004e98  sub     rsp, 28h
0x180004e9c  mov     rax, rcx
0x180004e9f  cmp     edx, [rcx+74h]
0x180004ea2  jnb     short loc_180004EDA
0x180004ea4  mov     edx, edx
0x180004ea6  lea     rcx, [rdx+0Fh]
0x180004eaa  lea     rcx, [rax+rcx*8]
0x180004eae  cmp     rcx, r9
0x180004eb1  jb      short loc_180004EE1
0x180004eb3  lea     r10, [rcx+8]
0x180004eb7  cmp     rcx, r10
0x180004eba  ja      short loc_180004EE1
0x180004ebc  mov     ecx, [rsp+28h+arg_20]
0x180004ec0  add     rcx, r9
0x180004ec3  cmp     r10, rcx
0x180004ec6  ja      short loc_180004EE1
0x180004ec8  test    r8, r8
0x180004ecb  jz      short loc_180004ED4
0x180004ecd  mov     ecx, [rax+rdx*8+7Ch]
0x180004ed1  mov     [r8], ecx
0x180004ed4  mov     eax, [rax+rdx*8+78h]
0x180004ed8  jmp     short loc_180004EDC
0x180004eda  xor     eax, eax
0x180004edc  add     rsp, 28h
0x180004ee0  retn
0x180004ee1  call    ThrowPeFmtException
```

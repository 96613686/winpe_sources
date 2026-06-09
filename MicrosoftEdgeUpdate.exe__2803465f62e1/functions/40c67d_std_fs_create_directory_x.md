# __std_fs_create_directory(x)

- ea: `0x40c67d`
- end: `0x40c6dc`
- name: `___std_fs_create_directory@4`
- size: `95`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x408ff9`
- `0x4090e0`

## callees

- `0x40c67d`
- `0x40c77d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c69d`
- `KERNEL32!GetLastError` at `0x40c69d`
- `KERNEL32!CreateDirectoryW` at `0x40c68a`
- `KERNEL32!CreateDirectoryW` at `0x40c68a`

## pseudocode

```c
int __stdcall __std_fs_create_directory(LPCWSTR lpPathName)
{
  _BYTE v2[16]; // [esp+4h] [ebp-28h] BYREF
  int v3; // [esp+24h] [ebp-8h]

  if ( CreateDirectoryW(lpPathName, 0) )
  {
    LOBYTE(v3) = 1;
  }
  else
  {
    if ( GetLastError() == 183 )
      __std_fs_get_stats(lpPathName, v2, 3, -1);
    LOBYTE(v3) = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x40c67d  push    ebp
0x40c67e  mov     ebp, esp
0x40c680  sub     esp, 28h
0x40c683  push    ebx
0x40c684  xor     ebx, ebx
0x40c686  push    ebx; lpSecurityAttributes
0x40c687  push    [ebp+lpPathName]; lpPathName
0x40c68a  call    ds:CreateDirectoryW
0x40c690  test    eax, eax
0x40c692  jz      short loc_40C69C
0x40c694  mov     byte ptr [ebp+var_8], 1
0x40c698  mov     edx, ebx
0x40c69a  jmp     short loc_40C6D4
0x40c69c  push    esi
0x40c69d  call    ds:GetLastError
0x40c6a3  mov     edx, eax
0x40c6a5  mov     esi, 0B7h
0x40c6aa  cmp     edx, esi
0x40c6ac  jnz     short loc_40C6D0
0x40c6ae  push    0FFFFFFFFh
0x40c6b0  push    3
0x40c6b2  lea     eax, [ebp+var_28]
0x40c6b5  push    eax
0x40c6b6  push    [ebp+lpPathName]
0x40c6b9  call    ___std_fs_get_stats@16
0x40c6be  mov     edx, eax
0x40c6c0  test    edx, edx
0x40c6c2  jnz     short loc_40C6D0
0x40c6c4  mov     eax, [ebp+var_18]
0x40c6c7  shr     eax, 4
0x40c6ca  test    al, 1
0x40c6cc  jnz     short loc_40C6D0
0x40c6ce  mov     edx, esi
0x40c6d0  mov     byte ptr [ebp+var_8], bl
0x40c6d3  pop     esi
0x40c6d4  mov     eax, [ebp+var_8]
0x40c6d7  pop     ebx
0x40c6d8  leave
0x40c6d9  retn    4
```

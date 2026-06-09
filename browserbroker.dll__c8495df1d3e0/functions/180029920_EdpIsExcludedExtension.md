# _EdpIsExcludedExtension

- ea: `0x180029920`
- end: `0x18002999d`
- name: `_EdpIsExcludedExtension`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027ad0`

## callees

- `0x180029920`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002992b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002992b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002996d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002996d`

## pseudocode

```c
char __fastcall EdpIsExcludedExtension(const WCHAR *a1)
{
  const WCHAR *ExtensionW; // rbp
  int v2; // ebx
  int v3; // edi
  __int64 v4; // rsi
  int v5; // eax

  ExtensionW = PathFindExtensionW(a1);
  if ( ExtensionW )
  {
    v2 = 0;
    v3 = 79;
    while ( v3 >= v2 )
    {
      v4 = (v3 + v2) / 2;
      v5 = CompareStringOrdinal(ExtensionW, -1, off_18002EB60[v4], -1, 1);
      switch ( v5 )
      {
        case 2:
          return 1;
        case 1:
          v3 = v4 - 1;
          break;
        case 3:
          v2 = v4 + 1;
          break;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029920  push    rbx
0x180029922  push    rbp
0x180029923  push    rsi
0x180029924  push    rdi
0x180029925  push    r15
0x180029927  sub     rsp, 30h
0x18002992b  call    cs:__imp_PathFindExtensionW
0x180029931  mov     rbp, rax
0x180029934  test    rax, rax
0x180029937  jz      short loc_180029990
0x180029939  xor     ebx, ebx
0x18002993b  lea     edi, [rbx+4Fh]
0x18002993e  lea     r15d, [rbx+2]
0x180029942  cmp     edi, ebx
0x180029944  jl      short loc_180029990
0x180029946  lea     eax, [rdi+rbx]
0x180029949  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180029951  cdq
0x180029952  or      r9d, 0FFFFFFFFh; cchCount2
0x180029956  idiv    r15d
0x180029959  mov     rcx, rbp; lpString1
0x18002995c  movsxd  rsi, eax
0x18002995f  or      edx, r9d; cchCount1
0x180029962  lea     rax, off_18002EB60; ".appx"
0x180029969  mov     r8, [rax+rsi*8]; lpString2
0x18002996d  call    cs:__imp_CompareStringOrdinal
0x180029973  cmp     eax, r15d
0x180029976  jz      short loc_18002998C
0x180029978  cmp     eax, 1
0x18002997b  jnz     short loc_180029982
0x18002997d  lea     edi, [rsi-1]
0x180029980  jmp     short loc_180029942
0x180029982  cmp     eax, 3
0x180029985  jnz     short loc_180029942
0x180029987  lea     ebx, [rsi+1]
0x18002998a  jmp     short loc_180029942
0x18002998c  mov     al, 1
0x18002998e  jmp     short loc_180029992
0x180029990  xor     al, al
0x180029992  add     rsp, 30h
0x180029996  pop     r15
0x180029998  pop     rdi
0x180029999  pop     rsi
0x18002999a  pop     rbp
0x18002999b  pop     rbx
0x18002999c  retn
```

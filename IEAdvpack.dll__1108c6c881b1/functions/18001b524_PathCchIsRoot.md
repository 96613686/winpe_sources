# PathCchIsRoot

- ea: `0x18001b524`
- end: `0x18001b62d`
- name: `PathCchIsRoot`
- size: `265`
- prototype: `BOOL __stdcall(PCWSTR pszPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180019fb8`
- `0x18001b784`

## callees

- `0x1800198d0`
- `0x18001a688`
- `0x18001a720`
- `0x18001ac8c`
- `0x18001b524`

## import_xrefs

- `msvcrt!iswalpha` at `0x18001b552`
- `msvcrt!iswalpha` at `0x18001b5d7`
- `msvcrt!iswalpha` at `0x18001b552`
- `msvcrt!iswalpha` at `0x18001b5d7`

## pseudocode

```c
BOOL __stdcall PathCchIsRoot(PCWSTR pszPath)
{
  WCHAR v2; // cx
  _WORD *v3; // rax
  int v4; // ecx

  if ( pszPath )
  {
    v2 = *pszPath;
    if ( v2 )
    {
      if ( iswalpha(v2) && StrIsEqualCaseInsensitive(pszPath + 1, L":\\", 3) || *pszPath == 92 && !pszPath[1] )
        return 1;
      if ( (unsigned int)PathIsUnc2((unsigned __int16 *)pszPath) )
      {
        v3 = 0;
        v4 = 0;
        while ( *v3 )
        {
          if ( *v3 == 92 && (++v4 > 1 || !v3[1]) )
            return 0;
          ++v3;
        }
        return 1;
      }
      if ( IsExtendedLengthDosDevicePath(pszPath)
        && iswalpha(pszPath[4])
        && StrIsEqualCaseInsensitive(pszPath + 5, L":\\", 3)
        || PathIsVolumeGUIDWorker(pszPath) && pszPath[48] == 92 && !pszPath[49] )
      {
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b524  mov     [rsp+arg_8], rbx
0x18001b529  mov     [rsp+arg_10], rsi
0x18001b52e  push    rdi
0x18001b52f  sub     rsp, 20h
0x18001b533  xor     esi, esi
0x18001b535  mov     rbx, rcx
0x18001b538  mov     [rsp+28h+arg_0], rsi
0x18001b53d  test    rcx, rcx
0x18001b540  jz      loc_18001B61B
0x18001b546  movzx   ecx, word ptr [rcx]; C
0x18001b549  test    cx, cx
0x18001b54c  jz      loc_18001B61B
0x18001b552  call    cs:__imp_iswalpha
0x18001b558  lea     rdi, [rbx+2]
0x18001b55c  test    eax, eax
0x18001b55e  jz      short loc_18001B57B
0x18001b560  lea     r8d, [rsi+3]; int
0x18001b564  mov     rcx, rdi; unsigned __int16 *
0x18001b567  lea     rdx, asc_18002114C; ":\\"
0x18001b56e  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18001b573  test    al, al
0x18001b575  jnz     loc_18001B614
0x18001b57b  cmp     word ptr [rbx], 5Ch ; '\'
0x18001b57f  jnz     short loc_18001B58A
0x18001b581  cmp     [rdi], si
0x18001b584  jz      loc_18001B614
0x18001b58a  lea     r8, IsBackslash
0x18001b591  mov     rcx, rbx; unsigned __int16 *
0x18001b594  lea     rdx, [rsp+28h+arg_0]
0x18001b599  call    PathIsUnc2
0x18001b59e  test    eax, eax
0x18001b5a0  jz      short loc_18001B5C7
0x18001b5a2  mov     rax, [rsp+28h+arg_0]
0x18001b5a7  mov     ecx, esi
0x18001b5a9  cmp     [rax], si
0x18001b5ac  jz      short loc_18001B614
0x18001b5ae  cmp     word ptr [rax], 5Ch ; '\'
0x18001b5b2  jnz     short loc_18001B5C1
0x18001b5b4  inc     ecx
0x18001b5b6  cmp     ecx, 1
0x18001b5b9  jg      short loc_18001B61B
0x18001b5bb  cmp     [rax+2], si
0x18001b5bf  jz      short loc_18001B61B
0x18001b5c1  add     rax, 2
0x18001b5c5  jmp     short loc_18001B5A9
0x18001b5c7  mov     rcx, rbx; unsigned __int16 *
0x18001b5ca  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18001b5cf  test    al, al
0x18001b5d1  jz      short loc_18001B5FB
0x18001b5d3  movzx   ecx, word ptr [rbx+8]; C
0x18001b5d7  call    cs:__imp_iswalpha
0x18001b5dd  test    eax, eax
0x18001b5df  jz      short loc_18001B5FB
0x18001b5e1  lea     rcx, [rbx+0Ah]; unsigned __int16 *
0x18001b5e5  mov     r8d, 3; int
0x18001b5eb  lea     rdx, asc_18002114C; ":\\"
0x18001b5f2  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18001b5f7  test    al, al
0x18001b5f9  jnz     short loc_18001B614
0x18001b5fb  mov     rcx, rbx; unsigned __int16 *
0x18001b5fe  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18001b603  test    al, al
0x18001b605  jz      short loc_18001B61B
0x18001b607  cmp     word ptr [rbx+60h], 5Ch ; '\'
0x18001b60c  jnz     short loc_18001B61B
0x18001b60e  cmp     [rbx+62h], si
0x18001b612  jnz     short loc_18001B61B
0x18001b614  mov     eax, 1
0x18001b619  jmp     short loc_18001B61D
0x18001b61b  xor     eax, eax
0x18001b61d  mov     rbx, [rsp+28h+arg_8]
0x18001b622  mov     rsi, [rsp+28h+arg_10]
0x18001b627  add     rsp, 20h
0x18001b62b  pop     rdi
0x18001b62c  retn
```

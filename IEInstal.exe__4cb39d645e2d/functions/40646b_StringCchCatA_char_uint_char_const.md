# StringCchCatA(char *,uint,char const *)

- ea: `0x40646b`
- end: `0x4064b8`
- name: `?StringCchCatA@@YGJPADIPBD@Z`
- size: `77`
- prototype: `int __stdcall(char *, signed int, const char *cchDest)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x40707d`
- `0x4072e3`
- `0x407fd4`

## callees

- `0x40646b`
- `0x406521`
- `0x406568`

## pseudocode

```c
int __stdcall StringCchCatA(char *a1, signed int a2, const char *cchDest)
{
  int result; // eax
  size_t *v4; // ecx
  size_t v5; // [esp+0h] [ebp-Ch]
  const char *v6; // [esp+0h] [ebp-Ch]
  size_t *v7; // [esp+4h] [ebp-8h]
  size_t v8; // [esp+4h] [ebp-8h]
  char psz[4]; // [esp+8h] [ebp-4h] BYREF

  if ( a2 <= 0 )
    return -2147024809;
  result = StringLengthWorkerA(psz, v5, v7);
  if ( result >= 0 )
    return StringCopyWorkerA(0, (size_t)cchDest, v4, v6, v8);
  return result;
}

```

## disassembly

```asm
0x40646b  mov     edi, edi
0x40646d  push    ebp
0x40646e  mov     ebp, esp
0x406470  push    ecx
0x406471  push    esi; cchToCopy
0x406472  mov     esi, [ebp+arg_4]
0x406475  push    edi; pszSrc
0x406476  test    esi, esi
0x406478  jz      short loc_4064AD
0x40647a  cmp     esi, 7FFFFFFFh
0x406480  ja      short loc_4064AD
0x406482  mov     edi, [ebp+arg_0]
0x406485  lea     eax, [ebp+psz]
0x406488  push    eax; psz
0x406489  mov     edx, esi
0x40648b  mov     ecx, edi
0x40648d  call    StringLengthWorkerA
0x406492  test    eax, eax
0x406494  js      short loc_4064B2
0x406496  mov     eax, dword ptr [ebp+psz]
0x406499  sub     esi, eax
0x40649b  push    ecx; pcchNewDestLength
0x40649c  push    [ebp+cchDest]; cchDest
0x40649f  mov     edx, esi
0x4064a1  push    0; pszDest
0x4064a3  lea     ecx, [eax+edi]
0x4064a6  call    StringCopyWorkerA
0x4064ab  jmp     short loc_4064B2
0x4064ad  mov     eax, 80070057h
0x4064b2  pop     edi
0x4064b3  pop     esi
0x4064b4  leave
0x4064b5  retn    0Ch
```

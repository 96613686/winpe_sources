# StringCchCopyA(char *,uint,char const *)

- ea: `0x406224`
- end: `0x406260`
- name: `?StringCchCopyA@@YGJPADIPBD@Z`
- size: `60`
- prototype: `int __stdcall(char *, unsigned int, size_t cchDest)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x4067aa`
- `0x406d91`
- `0x40707d`
- `0x4072e3`
- `0x407fd4`

## callees

- `0x406224`
- `0x406568`

## pseudocode

```c

```

## disassembly

```asm
0x406224  mov     edi, edi
0x406226  push    ebp; pszSrc
0x406227  mov     ebp, esp
0x406229  mov     eax, [ebp+arg_4]
0x40622c  test    eax, eax
0x40622e  jz      short loc_40624B
0x406230  cmp     eax, 7FFFFFFFh
0x406235  ja      short loc_40624B
0x406237  push    ecx; pcchNewDestLength
0x406238  push    [ebp+cchDest]; cchDest
0x40623b  mov     ecx, [ebp+arg_0]
0x40623e  mov     edx, eax
0x406240  push    0; pszDest
0x406242  call    StringCopyWorkerA
0x406247  mov     ecx, eax
0x406249  jmp     short loc_40625A
0x40624b  mov     ecx, 80070057h
0x406250  test    eax, eax
0x406252  jz      short loc_40625A
0x406254  mov     eax, [ebp+arg_0]
0x406257  mov     byte ptr [eax], 0
0x40625a  mov     eax, ecx
0x40625c  pop     ebp
0x40625d  retn    0Ch
```

# DeleteExtractedFiles(char *,sFNAME *)

- ea: `0x40723a`
- end: `0x4072dd`
- name: `?DeleteExtractedFiles@@YGJPADPAUsFNAME@@@Z`
- size: `163`
- prototype: `int __fastcall(char *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x405849`

## callees

- `0x40707d`
- `0x40723a`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x4072a7`
- `KERNEL32!SetFileAttributesA` at `0x4072a7`
- `KERNEL32!DeleteFileA` at `0x4072b8`
- `KERNEL32!DeleteFileA` at `0x4072b8`

## pseudocode

```c
int __fastcall DeleteExtractedFiles(char *a1, int a2)
{
  int v4; // edi
  unsigned int v6; // [esp+0h] [ebp-114h]
  char *v7; // [esp+4h] [ebp-110h]
  CHAR FileName[260]; // [esp+Ch] [ebp-108h] BYREF

  v4 = 0;
  while ( a2 )
  {
    if ( !*(_DWORD *)(a2 + 8) )
    {
      if ( *(_DWORD *)a2 )
      {
        memset(FileName, 0, sizeof(FileName));
        if ( !CatDirAndFileA(*(char **)a2, a1, (const char *)0x104, FileName, v6, v7)
          || !SetFileAttributesA(FileName, 0x80u)
          || !DeleteFileA(FileName) )
        {
          v4 = 1;
        }
      }
    }
    a2 = *(_DWORD *)(a2 + 4);
  }
  return v4;
}

```

## disassembly

```asm
0x40723a  mov     edi, edi
0x40723c  push    ebp
0x40723d  mov     ebp, esp
0x40723f  sub     esp, 108h
0x407245  mov     eax, ___security_cookie
0x40724a  xor     eax, ebp
0x40724c  mov     [ebp+var_4], eax
0x40724f  push    ebx
0x407250  push    esi
0x407251  push    edi
0x407252  mov     esi, edx
0x407254  mov     ebx, ecx
0x407256  xor     edi, edi
0x407258  jmp     short loc_4072C8
0x40725a  cmp     dword ptr [esi+8], 0
0x40725e  jnz     short loc_4072C5
0x407260  cmp     dword ptr [esi], 0
0x407263  jz      short loc_4072C5
0x407265  push    103h; Size
0x40726a  lea     eax, [ebp+var_107]
0x407270  mov     [ebp+FileName], 0
0x407277  push    0; Val
0x407279  push    eax; void *
0x40727a  call    _memset
0x40727f  mov     edx, [esi]
0x407281  lea     eax, [ebp+FileName]
0x407287  add     esp, 0Ch
0x40728a  mov     ecx, ebx
0x40728c  push    eax; char *
0x40728d  push    104h; char *
0x407292  call    ?CatDirAndFileA@@YGHPBD0KPAD@Z; CatDirAndFileA(char const *,char const *,ulong,char *)
0x407297  test    eax, eax
0x407299  jz      short loc_4072C2
0x40729b  push    80h; dwFileAttributes
0x4072a0  lea     eax, [ebp+FileName]
0x4072a6  push    eax; lpFileName
0x4072a7  call    ds:__imp__SetFileAttributesA@8; SetFileAttributesA(x,x)
0x4072ad  test    eax, eax
0x4072af  jz      short loc_4072C2
0x4072b1  lea     eax, [ebp+FileName]
0x4072b7  push    eax; lpFileName
0x4072b8  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x4072be  test    eax, eax
0x4072c0  jnz     short loc_4072C5
0x4072c2  xor     edi, edi
0x4072c4  inc     edi
0x4072c5  mov     esi, [esi+4]
0x4072c8  test    esi, esi
0x4072ca  jnz     short loc_40725A
0x4072cc  mov     ecx, [ebp+var_4]
0x4072cf  mov     eax, edi
0x4072d1  pop     edi
0x4072d2  pop     esi
0x4072d3  xor     ecx, ebp; StackCookie
0x4072d5  pop     ebx
0x4072d6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x4072db  leave
0x4072dc  retn
```

# BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)

- ea: `0x1800152f0`
- end: `0x180015376`
- name: `?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z`
- size: `134`
- prototype: `int(struct _objectinfo *, unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bb8`
- `0x18000474c`
- `0x18000d638`
- `0x1800151fc`
- `0x180015664`

## callees

- `0x1800152f0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180015319`
- `msvcrt!wcscat_s` at `0x180015343`
- `msvcrt!wcscat_s` at `0x18001535b`
- `msvcrt!wcscat_s` at `0x180015319`
- `msvcrt!wcscat_s` at `0x180015343`
- `msvcrt!wcscat_s` at `0x18001535b`

## pseudocode

```c
__int64 __fastcall BuildIISPathFromADsPath(struct _objectinfo *a1, unsigned __int16 *a2, rsize_t a3)
{
  unsigned int v3; // edi
  unsigned int i; // ebx

  v3 = *((_DWORD *)a1 + 136);
  wcscat_s(a2, a3, L"/LM/");
  if ( v3 )
  {
    for ( i = 0; i < v3; ++i )
    {
      wcscat_s(a2, a3, *(const wchar_t **)(*((_QWORD *)a1 + 69) + 16LL * i));
      if ( i < v3 - 1 )
        wcscat_s(a2, a3, L"/");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800152f0  push    rbx
0x1800152f2  push    rbp
0x1800152f3  push    rsi
0x1800152f4  push    rdi
0x1800152f5  push    r14
0x1800152f7  push    r15
0x1800152f9  sub     rsp, 28h
0x1800152fd  mov     edi, [rcx+220h]
0x180015303  mov     rsi, r8
0x180015306  mov     rbp, rdx
0x180015309  lea     r8, aLm; "/LM/"
0x180015310  mov     r15, rcx
0x180015313  mov     rdx, rsi; SizeInWords
0x180015316  mov     rcx, rbp; Destination
0x180015319  call    cs:__imp_wcscat_s
0x18001531f  test    edi, edi
0x180015321  jz      short loc_180015367
0x180015323  xor     ebx, ebx
0x180015325  test    edi, edi
0x180015327  jz      short loc_180015367
0x180015329  lea     r14d, [rdi-1]
0x18001532d  mov     r8, [r15+228h]
0x180015334  mov     rdx, rsi; SizeInWords
0x180015337  mov     eax, ebx
0x180015339  mov     rcx, rbp; Destination
0x18001533c  add     rax, rax
0x18001533f  mov     r8, [r8+rax*8]; Source
0x180015343  call    cs:__imp_wcscat_s
0x180015349  cmp     ebx, r14d
0x18001534c  jnb     short loc_180015361
0x18001534e  lea     r8, Source; "/"
0x180015355  mov     rdx, rsi; SizeInWords
0x180015358  mov     rcx, rbp; Destination
0x18001535b  call    cs:__imp_wcscat_s
0x180015361  inc     ebx
0x180015363  cmp     ebx, edi
0x180015365  jb      short loc_18001532D
0x180015367  xor     eax, eax
0x180015369  add     rsp, 28h
0x18001536d  pop     r15
0x18001536f  pop     r14
0x180015371  pop     rdi
0x180015372  pop     rsi
0x180015373  pop     rbp
0x180015374  pop     rbx
0x180015375  retn
```

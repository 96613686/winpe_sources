# SystemSettings::PenSettings::IsAppIdInTheList(ushort const * const *,uint,ushort const *)

- ea: `0x180054330`
- end: `0x18005438b`
- name: `?IsAppIdInTheList@PenSettings@SystemSettings@@YA_NPEBQEBGIPEBG@Z`
- size: `91`
- prototype: `bool(SystemSettings::PenSettings *__hidden this, const unsigned __int16 *const *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054048`

## callees

- `0x180054330`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005436b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005436b`

## pseudocode

```c
char __fastcall SystemSettings::PenSettings::IsAppIdInTheList(
        PCNZWCH *this,
        const unsigned __int16 *const *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  char v4; // di
  __int64 v6; // rbx
  unsigned int v7; // esi

  v4 = 0;
  v6 = 0;
  v7 = (unsigned int)a2;
  while ( (unsigned int)v6 < v7 )
  {
    if ( CompareStringW(0x7Fu, 1u, a3, -1, this[v6], -1) == 2 )
      return 1;
    v6 = (unsigned int)(v6 + 1);
  }
  return v4;
}

```

## disassembly

```asm
0x180054330  push    rbx
0x180054332  push    rbp
0x180054333  push    rsi
0x180054334  push    rdi
0x180054335  push    r14
0x180054337  sub     rsp, 30h
0x18005433b  xor     dil, dil
0x18005433e  mov     rbp, r8
0x180054341  xor     ebx, ebx
0x180054343  mov     esi, edx
0x180054345  mov     r14, rcx
0x180054348  cmp     ebx, esi
0x18005434a  jnb     short loc_18005437D
0x18005434c  mov     rax, [r14+rbx*8]
0x180054350  or      r9d, 0FFFFFFFFh; cchCount1
0x180054354  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005435c  mov     r8, rbp; lpString1
0x18005435f  mov     [rsp+58h+lpString2], rax; lpString2
0x180054364  lea     edx, [r9+2]; dwCmpFlags
0x180054368  lea     ecx, [rdx+7Eh]; Locale
0x18005436b  call    cs:__imp_CompareStringW
0x180054371  cmp     eax, 2
0x180054374  jz      short loc_18005437A
0x180054376  inc     ebx
0x180054378  jmp     short loc_180054348
0x18005437a  mov     dil, 1
0x18005437d  mov     al, dil
0x180054380  add     rsp, 30h
0x180054384  pop     r14
0x180054386  pop     rdi
0x180054387  pop     rsi
0x180054388  pop     rbp
0x180054389  pop     rbx
0x18005438a  retn
```

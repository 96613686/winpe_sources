# TsiCreateUserSid

- ea: `0x1800201a8`
- end: `0x18002024a`
- name: `TsiCreateUserSid`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001ff70`
- `0x18002005c`

## callees

- `0x18000be70`
- `0x180010094`
- `0x180010208`
- `0x1800201a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020234`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020234`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002022b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002022b`

## pseudocode

```c
__int64 __fastcall TsiCreateUserSid(_QWORD *a1, __int64 a2)
{
  _DWORD *v4; // rbx
  int v5; // edi
  unsigned __int16 *v6; // rax

  if ( !a2 || !*(_DWORD *)(a2 + 8) )
    return 0;
  if ( !a1 )
  {
    v4 = 0;
    v5 = -2147467261;
LABEL_10:
    operator delete(v4);
    return (unsigned int)v5;
  }
  v4 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = -2147024882;
  if ( !v4 )
    goto LABEL_10;
  v6 = (unsigned __int16 *)operator new[](*(unsigned int *)(a2 + 8), (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)v4 = v6;
  if ( !v6
    || (v4[2] = *(_DWORD *)(a2 + 8),
        v5 = StringCchCopyW(v6, (unsigned __int64)*(unsigned int *)(a2 + 8) >> 1, *(const unsigned __int16 **)a2),
        v5 < 0) )
  {
    operator delete[](*(void **)v4);
    goto LABEL_10;
  }
  *a1 = v4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800201a8  push    rbx
0x1800201aa  push    rsi
0x1800201ab  push    rdi
0x1800201ac  push    r14
0x1800201ae  sub     rsp, 28h
0x1800201b2  mov     rsi, rdx
0x1800201b5  mov     r14, rcx
0x1800201b8  test    rdx, rdx
0x1800201bb  jz      short loc_18002023C
0x1800201bd  cmp     dword ptr [rdx+8], 0
0x1800201c1  jz      short loc_18002023C
0x1800201c3  test    rcx, rcx
0x1800201c6  jnz     short loc_1800201D1
0x1800201c8  xor     ebx, ebx
0x1800201ca  mov     edi, 80004003h
0x1800201cf  jmp     short loc_180020231
0x1800201d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800201d8  mov     ecx, 10h; unsigned __int64
0x1800201dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800201e2  mov     rbx, rax
0x1800201e5  mov     edi, 8007000Eh
0x1800201ea  test    rax, rax
0x1800201ed  jz      short loc_180020231
0x1800201ef  mov     ecx, [rsi+8]; unsigned __int64
0x1800201f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800201f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800201fe  mov     [rbx], rax
0x180020201  mov     rcx, rax; unsigned __int16 *
0x180020204  test    rax, rax
0x180020207  jz      short loc_180020228
0x180020209  mov     eax, [rsi+8]
0x18002020c  mov     [rbx+8], eax
0x18002020f  mov     edx, [rsi+8]
0x180020212  mov     r8, [rsi]; unsigned __int16 *
0x180020215  shr     rdx, 1; unsigned __int64
0x180020218  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002021d  mov     edi, eax
0x18002021f  test    eax, eax
0x180020221  js      short loc_180020228
0x180020223  mov     [r14], rbx
0x180020226  jmp     short loc_18002023E
0x180020228  mov     rcx, [rbx]
0x18002022b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180020231  mov     rcx, rbx
0x180020234  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002023a  jmp     short loc_18002023E
0x18002023c  xor     edi, edi
0x18002023e  mov     eax, edi
0x180020240  add     rsp, 28h
0x180020244  pop     r14
0x180020246  pop     rdi
0x180020247  pop     rsi
0x180020248  pop     rbx
0x180020249  retn
```

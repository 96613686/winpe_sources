# FILTERS_CUSTOM_PROVIDER::AllFiltersPresent(MULTISZ,ABO_NODE *)

- ea: `0x180010440`
- end: `0x1800104fe`
- name: `?AllFiltersPresent@FILTERS_CUSTOM_PROVIDER@@AEAAHVMULTISZ@@PEAVABO_NODE@@@Z`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010f40`

## callees

- `0x180010440`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010493`
- `msvcrt!_wcsicmp` at `0x1800104b5`
- `msvcrt!_wcsicmp` at `0x180010493`
- `msvcrt!_wcsicmp` at `0x1800104b5`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800104ea`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x1800104ea`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180010460`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180010460`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010483`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800104a9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010483`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800104a9`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800104cb`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800104cb`

## string_xrefs

- `0x18001048c`: `COMPRESSION`

## pseudocode

```c
__int64 __fastcall FILTERS_CUSTOM_PROVIDER::AllFiltersPresent(__int64 a1, MULTISZ *a2, __int64 a3)
{
  unsigned int v3; // ebx
  const unsigned __int16 *v6; // rax
  __int64 v7; // rbp
  const wchar_t *Str; // rax
  const wchar_t *v9; // rax
  const wchar_t *v11; // rdi

  v3 = 0;
  if ( a3 )
  {
    v6 = MULTISZ::First(a2);
    v3 = 1;
    while ( 1 )
    {
      v11 = v6;
      if ( !v6 )
        break;
      v7 = 0;
      if ( !*(_DWORD *)(a3 + 40) )
      {
LABEL_7:
        v3 = 0;
        break;
      }
      while ( 1 )
      {
        Str = STRU::QueryStr((STRU *)(*(_QWORD *)(*(_QWORD *)(a3 + 32) + 8 * v7) + 56LL));
        if ( _wcsicmp(Str, L"COMPRESSION") )
        {
          v9 = STRU::QueryStr((STRU *)(*(_QWORD *)(*(_QWORD *)(a3 + 32) + 8 * v7) + 56LL));
          if ( !_wcsicmp(v9, v11) )
            break;
        }
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= *(_DWORD *)(a3 + 40) )
          goto LABEL_7;
      }
      v6 = MULTISZ::Next(a2, v11);
    }
  }
  MULTISZ::~MULTISZ(a2);
  return v3;
}

```

## disassembly

```asm
0x180010440  mov     [rsp+arg_0], rbx
0x180010445  push    rbp
0x180010446  push    rsi
0x180010447  push    rdi
0x180010448  push    r14
0x18001044a  push    r15
0x18001044c  sub     rsp, 20h
0x180010450  xor     ebx, ebx
0x180010452  mov     rsi, r8
0x180010455  mov     r14, rdx
0x180010458  test    r8, r8
0x18001045b  jz      short loc_1800104C8
0x18001045d  mov     rcx, rdx
0x180010460  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180010466  mov     ebx, 1
0x18001046b  jmp     loc_1800104F0
0x180010470  xor     ebp, ebp
0x180010472  cmp     [rsi+28h], ebp
0x180010475  jbe     short loc_1800104C6
0x180010477  mov     rax, [rsi+20h]
0x18001047b  mov     rcx, [rax+rbp*8]
0x18001047f  add     rcx, 38h ; '8'
0x180010483  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180010489  mov     rcx, rax; String1
0x18001048c  lea     rdx, aCompression; "COMPRESSION"
0x180010493  call    cs:__imp__wcsicmp
0x180010499  test    eax, eax
0x18001049b  jz      short loc_1800104BF
0x18001049d  mov     rax, [rsi+20h]
0x1800104a1  mov     rcx, [rax+rbp*8]
0x1800104a5  add     rcx, 38h ; '8'
0x1800104a9  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800104af  mov     rcx, rax; String1
0x1800104b2  mov     rdx, rdi; String2
0x1800104b5  call    cs:__imp__wcsicmp
0x1800104bb  test    eax, eax
0x1800104bd  jz      short loc_1800104E4
0x1800104bf  add     ebp, ebx
0x1800104c1  cmp     ebp, [rsi+28h]
0x1800104c4  jb      short loc_180010477
0x1800104c6  xor     ebx, ebx
0x1800104c8  mov     rcx, r14
0x1800104cb  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800104d1  mov     eax, ebx
0x1800104d3  mov     rbx, [rsp+48h+arg_0]
0x1800104d8  add     rsp, 20h
0x1800104dc  pop     r15
0x1800104de  pop     r14
0x1800104e0  pop     rdi
0x1800104e1  pop     rsi
0x1800104e2  pop     rbp
0x1800104e3  retn
0x1800104e4  mov     rdx, rdi
0x1800104e7  mov     rcx, r14
0x1800104ea  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x1800104f0  mov     rdi, rax
0x1800104f3  test    rax, rax
0x1800104f6  jnz     loc_180010470
0x1800104fc  jmp     short loc_1800104C8
```

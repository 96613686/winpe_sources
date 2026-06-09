# _DSAFromComCatCache(uchar const *,ulong,_DSA * *)

- ea: `0x18002a4b8`
- end: `0x18002a55d`
- name: `?_DSAFromComCatCache@@YAJPEBEKPEAPEAU_DSA@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, struct _DSA **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a6ac`

## callees

- `0x18000dc94`
- `0x18002a4b8`

## import_xrefs

- `iertutil!__imp_DSA_Create` at `0x18002a4f5`
- `iertutil!__imp_DSA_Create` at `0x18002a4f5`
- `iertutil!__imp_DSA_InsertItem` at `0x18002a53c`
- `iertutil!__imp_DSA_InsertItem` at `0x18002a53c`

## string_xrefs

- `0x18002a508`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\comcatex.cpp`

## pseudocode

```c
__int64 __fastcall _DSAFromComCatCache(const unsigned __int8 *a1, unsigned int a2, struct _DSA **a3)
{
  unsigned int v5; // edi
  struct _DSA *v6; // rax
  const char *v7; // r9
  unsigned int i; // ebp
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 >= 0x1C && *(_DWORD *)a1 == 28 && *((_DWORD *)a1 + 1) == 1 )
  {
    if ( *((_DWORD *)a1 + 6) )
    {
      if ( !*a3 )
      {
        v6 = DSA_Create(16, 4);
        *a3 = v6;
        if ( !v6 )
          wil::details::in1diag3::_FailFast_NullAlloc(
            retaddr,
            (void *)0x1D2,
            (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\comcatex.cpp",
            v7);
      }
      v5 = 0;
      for ( i = 0; i < *((_DWORD *)a1 + 6); ++i )
        DSA_InsertItem(*a3, 0x7FFFFFFF, &a1[16 * i + 28]);
    }
    else
    {
      return 1;
    }
  }
  else
  {
    return (unsigned int)-2147024883;
  }
  return v5;
}

```

## disassembly

```asm
0x18002a4b8  push    rbx
0x18002a4ba  push    rbp
0x18002a4bb  push    rsi
0x18002a4bc  push    rdi
0x18002a4bd  push    r14
0x18002a4bf  sub     rsp, 20h
0x18002a4c3  mov     rsi, r8
0x18002a4c6  mov     rbx, rcx
0x18002a4c9  cmp     edx, 1Ch
0x18002a4cc  jb      short loc_18002A54B
0x18002a4ce  cmp     dword ptr [rcx], 1Ch
0x18002a4d1  jnz     short loc_18002A54B
0x18002a4d3  cmp     dword ptr [rcx+4], 1
0x18002a4d7  jnz     short loc_18002A54B
0x18002a4d9  xor     r14d, r14d
0x18002a4dc  cmp     [rcx+18h], r14d
0x18002a4e0  jnz     short loc_18002A4E8
0x18002a4e2  lea     edi, [r14+1]
0x18002a4e6  jmp     short loc_18002A550
0x18002a4e8  cmp     [r8], r14
0x18002a4eb  jnz     short loc_18002A51A
0x18002a4ed  mov     edx, 4; cItemGrow
0x18002a4f2  lea     ecx, [rdx+0Ch]; cbItem
0x18002a4f5  call    cs:__imp_DSA_Create
0x18002a4fb  mov     [rsi], rax
0x18002a4fe  test    rax, rax
0x18002a501  jnz     short loc_18002A51A
0x18002a503  mov     rcx, [rsp+48h]; this
0x18002a508  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002a50f  mov     edx, 1D2h; void *
0x18002a514  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18002a51a  mov     edi, r14d
0x18002a51d  mov     ebp, r14d
0x18002a520  cmp     [rbx+18h], r14d
0x18002a524  jbe     short loc_18002A550
0x18002a526  lea     r14, [rbx+1Ch]
0x18002a52a  mov     rcx, [rsi]; hdsa
0x18002a52d  mov     edx, 7FFFFFFFh; i
0x18002a532  mov     r8d, ebp
0x18002a535  shl     r8, 4
0x18002a539  add     r8, r14; pitem
0x18002a53c  call    cs:__imp_DSA_InsertItem
0x18002a542  inc     ebp
0x18002a544  cmp     ebp, [rbx+18h]
0x18002a547  jb      short loc_18002A52A
0x18002a549  jmp     short loc_18002A550
0x18002a54b  mov     edi, 8007000Dh
0x18002a550  mov     eax, edi
0x18002a552  add     rsp, 20h
0x18002a556  pop     r14
0x18002a558  pop     rdi
0x18002a559  pop     rsi
0x18002a55a  pop     rbp
0x18002a55b  pop     rbx
0x18002a55c  retn
```

# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Tidy(void)

- ea: `0x1800214f4`
- end: `0x180021589`
- name: `?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ`
- size: `149`
- prototype: `void __fastcall(__int64)`
- caller_count: `30`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000afac`
- `0x18000b560`
- `0x18000ba74`
- `0x18000f3f8`
- `0x180010560`
- `0x18001082c`
- `0x180011d10`
- `0x1800126e0`
- `0x180012da4`
- `0x180012e30`
- `0x180012e68`
- `0x18001330c`
- `0x18001333c`
- `0x180013388`
- `0x1800137b4`
- `0x180013b68`
- `0x180013e1c`
- `0x1800140e0`
- `0x180014788`
- `0x180017a80`
- `0x180017e84`
- `0x18001bb94`
- `0x18001bdc8`
- `0x18001e518`
- `0x180021590`
- `0x180021f74`
- `0x180022024`
- `0x180023070`
- `0x180024198`
- `0x180024b28`

## callees

- `0x180003a34`
- `0x180006380`
- `0x1800214f4`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::_Tidy(__int64 a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rax
  char **v5; // rcx

  v1 = *(char ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char ***)(a1 + 8);
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1);
      v1 += 4;
    }
    v4 = *(char ***)a1;
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v5 = *(char ***)a1;
    }
    else
    {
      v5 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800214f4  mov     [rsp+arg_8], rbx
0x1800214f9  mov     [rsp+arg_10], rsi
0x1800214fe  push    rdi
0x1800214ff  sub     rsp, 20h
0x180021503  mov     rbx, [rcx]
0x180021506  mov     rdi, rcx
0x180021509  test    rbx, rbx
0x18002150c  jz      short loc_180021579
0x18002150e  mov     rsi, [rcx+8]
0x180021512  jmp     short loc_180021520
0x180021514  mov     rcx, rbx; void *
0x180021517  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002151c  add     rbx, 20h ; ' '
0x180021520  cmp     rbx, rsi
0x180021523  jnz     short loc_180021514
0x180021525  mov     rax, [rdi]
0x180021528  mov     rdx, [rdi+10h]
0x18002152c  sub     rdx, rax
0x18002152f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180021533  cmp     rdx, 1000h
0x18002153a  jb      short loc_18002155A
0x18002153c  mov     rcx, [rax-8]
0x180021540  sub     rax, rcx
0x180021543  sub     rax, 8
0x180021547  cmp     rax, 1Fh
0x18002154b  ja      short loc_180021553
0x18002154d  add     rdx, 27h ; '''
0x180021551  jmp     short loc_18002155D
0x180021553  mov     ecx, 5
0x180021558  int     29h; Win8: RtlFailFast(ecx)
0x18002155a  mov     rcx, rax; Block
0x18002155d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021562  mov     qword ptr [rdi], 0
0x180021569  mov     qword ptr [rdi+8], 0
0x180021571  mov     qword ptr [rdi+10h], 0
0x180021579  mov     rbx, [rsp+28h+arg_8]
0x18002157e  mov     rsi, [rsp+28h+arg_10]
0x180021583  add     rsp, 20h
0x180021587  pop     rdi
0x180021588  retn
```

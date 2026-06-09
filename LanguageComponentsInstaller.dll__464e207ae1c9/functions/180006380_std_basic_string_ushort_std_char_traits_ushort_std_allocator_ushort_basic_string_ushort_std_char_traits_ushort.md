# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180006380`
- end: `0x1800063e4`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `105`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005c60`
- `0x180006348`
- `0x1800067f4`
- `0x180007594`
- `0x18000a254`
- `0x18000afac`
- `0x18000b560`
- `0x18000ba74`
- `0x18000c32c`
- `0x18000d7e4`
- `0x18000d970`
- `0x18000daa0`
- `0x18000f0a8`
- `0x18000f3f8`
- `0x180010560`
- `0x18001060c`
- `0x180010768`
- `0x18001082c`
- `0x180011534`
- `0x1800119a0`
- `0x180011d10`
- `0x180012a48`
- `0x180012e30`
- `0x180012e68`
- `0x1800137b4`
- `0x180013e1c`
- `0x1800140e0`
- `0x180014508`
- `0x180014788`
- `0x18001568c`
- `0x180016ae0`
- `0x180017328`
- `0x1800178e0`
- `0x180017e84`
- `0x18001844c`
- `0x180019168`
- `0x18001b5b4`
- `0x18001b728`
- `0x18001baa0`
- `0x18001bb94`
- `0x18001bdc8`
- `0x18001d6c8`
- `0x18001e518`
- `0x18001f49c`
- `0x1800214f4`
- `0x180021590`
- `0x180021c50`
- `0x180021f74`
- `0x180022024`
- `0x180023f40`

## callees

- `0x180003a34`
- `0x180006380`

## pseudocode

```c
void __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
  }
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x180006380  push    rbx
0x180006382  sub     rsp, 20h
0x180006386  mov     rdx, [rcx+18h]
0x18000638a  mov     rbx, rcx
0x18000638d  cmp     rdx, 7
0x180006391  jbe     short loc_1800063CD
0x180006393  mov     rax, [rcx]
0x180006396  lea     rdx, ds:2[rdx*2]
0x18000639e  cmp     rdx, 1000h
0x1800063a5  jb      short loc_1800063C5
0x1800063a7  mov     rcx, [rax-8]
0x1800063ab  sub     rax, rcx
0x1800063ae  sub     rax, 8
0x1800063b2  cmp     rax, 1Fh
0x1800063b6  ja      short loc_1800063BE
0x1800063b8  add     rdx, 27h ; '''
0x1800063bc  jmp     short loc_1800063C8
0x1800063be  mov     ecx, 5
0x1800063c3  int     29h; Win8: RtlFailFast(ecx)
0x1800063c5  mov     rcx, rax; Block
0x1800063c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800063cd  xor     eax, eax
0x1800063cf  mov     qword ptr [rbx+18h], 7
0x1800063d7  mov     [rbx+10h], rax
0x1800063db  mov     [rbx], ax
0x1800063de  add     rsp, 20h
0x1800063e2  pop     rbx
0x1800063e3  retn
```

# ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x180003968`
- end: `0x1800039e5`
- name: `?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `125`
- prototype: `void __fastcall(void *, __int64, const void *, int)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d44`
- `0x180002e50`
- `0x180003338`
- `0x180003b94`
- `0x1800045b4`
- `0x18002ec58`

## callees

- `0x1800025f2`
- `0x180002678`
- `0x180003968`
- `0x180032ac8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003987`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800039c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180003987`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800039c4`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::CopyChars(void *a1, __int64 a2, const void *a3, int a4)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi

  v5 = 2LL * a4;
  if ( v5 )
  {
    if ( !a1 )
      goto LABEL_3;
    v6 = 2 * a2;
    if ( a3 && v6 >= v5 )
    {
      memcpy_0(a1, a3, 2LL * a4);
      return;
    }
    memset_0(a1, 0, 2 * a2);
    if ( a3 )
    {
      if ( v6 >= v5 )
        return;
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
LABEL_3:
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
  }
}

```

## disassembly

```asm
0x180003968  mov     [rsp+arg_0], rbx
0x18000396d  mov     [rsp+arg_8], rsi
0x180003972  push    rdi
0x180003973  sub     rsp, 20h
0x180003977  movsxd  rbx, r9d
0x18000397a  mov     rsi, r8
0x18000397d  add     rbx, rbx
0x180003980  jz      short loc_1800039D5
0x180003982  test    rcx, rcx
0x180003985  jnz     short loc_180003995
0x180003987  call    cs:__imp__o__errno
0x18000398d  mov     dword ptr [rax], 16h
0x180003993  jmp     short loc_1800039D0
0x180003995  lea     rdi, [rdx+rdx]
0x180003999  test    rsi, rsi
0x18000399c  jz      short loc_1800039B0
0x18000399e  cmp     rdi, rbx
0x1800039a1  jb      short loc_1800039B0
0x1800039a3  mov     r8, rbx; Size
0x1800039a6  mov     rdx, rsi; Src
0x1800039a9  call    memcpy_0
0x1800039ae  jmp     short loc_1800039D5
0x1800039b0  mov     r8, rdi; Size
0x1800039b3  xor     edx, edx; Val
0x1800039b5  call    memset_0
0x1800039ba  test    rsi, rsi
0x1800039bd  jz      short loc_180003987
0x1800039bf  cmp     rdi, rbx
0x1800039c2  jnb     short loc_1800039D5
0x1800039c4  call    cs:__imp__o__errno
0x1800039ca  mov     dword ptr [rax], 22h ; '"'
0x1800039d0  call    _invalid_parameter_noinfo
0x1800039d5  mov     rbx, [rsp+28h+arg_0]
0x1800039da  mov     rsi, [rsp+28h+arg_8]
0x1800039df  add     rsp, 20h
0x1800039e3  pop     rdi
0x1800039e4  retn
```

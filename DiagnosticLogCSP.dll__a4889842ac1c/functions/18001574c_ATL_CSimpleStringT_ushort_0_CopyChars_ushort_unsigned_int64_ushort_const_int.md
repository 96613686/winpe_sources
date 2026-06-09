# ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x18001574c`
- end: `0x1800157c9`
- name: `?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `125`
- prototype: `void __fastcall(void *, __int64, const void *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180015674`
- `0x18001639c`
- `0x180019260`
- `0x18001dc28`
- `0x18001dccc`
- `0x18001f65c`
- `0x1800223a4`
- `0x180030470`

## callees

- `0x180002582`
- `0x18000262c`
- `0x180002cf5`
- `0x18001574c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001576b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800157a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001576b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800157a8`

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
0x18001574c  mov     [rsp+arg_0], rbx
0x180015751  mov     [rsp+arg_8], rsi
0x180015756  push    rdi
0x180015757  sub     rsp, 20h
0x18001575b  movsxd  rbx, r9d
0x18001575e  mov     rsi, r8
0x180015761  add     rbx, rbx
0x180015764  jz      short loc_1800157B9
0x180015766  test    rcx, rcx
0x180015769  jnz     short loc_180015779
0x18001576b  call    cs:__imp__o__errno
0x180015771  mov     dword ptr [rax], 16h
0x180015777  jmp     short loc_1800157B4
0x180015779  lea     rdi, [rdx+rdx]
0x18001577d  test    rsi, rsi
0x180015780  jz      short loc_180015794
0x180015782  cmp     rdi, rbx
0x180015785  jb      short loc_180015794
0x180015787  mov     r8, rbx; Size
0x18001578a  mov     rdx, rsi; Src
0x18001578d  call    memcpy_0
0x180015792  jmp     short loc_1800157B9
0x180015794  mov     r8, rdi; Size
0x180015797  xor     edx, edx; Val
0x180015799  call    memset_0
0x18001579e  test    rsi, rsi
0x1800157a1  jz      short loc_18001576B
0x1800157a3  cmp     rdi, rbx
0x1800157a6  jnb     short loc_1800157B9
0x1800157a8  call    cs:__imp__o__errno
0x1800157ae  mov     dword ptr [rax], 22h ; '"'
0x1800157b4  call    _invalid_parameter_noinfo
0x1800157b9  mov     rbx, [rsp+28h+arg_0]
0x1800157be  mov     rsi, [rsp+28h+arg_8]
0x1800157c3  add     rsp, 20h
0x1800157c7  pop     rdi
0x1800157c8  retn
```

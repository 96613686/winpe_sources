# ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x1800046bc`
- end: `0x180004739`
- name: `?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `125`
- prototype: `void __fastcall(void *, __int64, const void *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800045d4`
- `0x180005304`
- `0x180007da8`
- `0x18000cf40`
- `0x18000cfe4`
- `0x18000ea38`
- `0x180011774`
- `0x180022e08`

## callees

- `0x180002382`
- `0x180002420`
- `0x1800027b1`
- `0x1800046bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800046db`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004718`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800046db`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004718`

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
0x1800046bc  mov     [rsp+arg_0], rbx
0x1800046c1  mov     [rsp+arg_8], rsi
0x1800046c6  push    rdi
0x1800046c7  sub     rsp, 20h
0x1800046cb  movsxd  rbx, r9d
0x1800046ce  mov     rsi, r8
0x1800046d1  add     rbx, rbx
0x1800046d4  jz      short loc_180004729
0x1800046d6  test    rcx, rcx
0x1800046d9  jnz     short loc_1800046E9
0x1800046db  call    cs:__imp__o__errno
0x1800046e1  mov     dword ptr [rax], 16h
0x1800046e7  jmp     short loc_180004724
0x1800046e9  lea     rdi, [rdx+rdx]
0x1800046ed  test    rsi, rsi
0x1800046f0  jz      short loc_180004704
0x1800046f2  cmp     rdi, rbx
0x1800046f5  jb      short loc_180004704
0x1800046f7  mov     r8, rbx; Size
0x1800046fa  mov     rdx, rsi; Src
0x1800046fd  call    memcpy_0
0x180004702  jmp     short loc_180004729
0x180004704  mov     r8, rdi; Size
0x180004707  xor     edx, edx; Val
0x180004709  call    memset_0
0x18000470e  test    rsi, rsi
0x180004711  jz      short loc_1800046DB
0x180004713  cmp     rdi, rbx
0x180004716  jnb     short loc_180004729
0x180004718  call    cs:__imp__o__errno
0x18000471e  mov     dword ptr [rax], 22h ; '"'
0x180004724  call    _invalid_parameter_noinfo
0x180004729  mov     rbx, [rsp+28h+arg_0]
0x18000472e  mov     rsi, [rsp+28h+arg_8]
0x180004733  add     rsp, 20h
0x180004737  pop     rdi
0x180004738  retn
```

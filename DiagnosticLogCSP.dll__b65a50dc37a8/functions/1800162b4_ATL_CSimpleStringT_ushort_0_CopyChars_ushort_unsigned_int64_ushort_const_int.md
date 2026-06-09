# ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)

- ea: `0x1800162b4`
- end: `0x18001633e`
- name: `?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z`
- size: `138`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800161d4`
- `0x180016f5c`
- `0x18001a030`
- `0x18001ebc0`
- `0x18001ec68`
- `0x180020678`
- `0x1800232f0`
- `0x180031910`

## callees

- `0x1800025b2`
- `0x18000265c`
- `0x180002d25`
- `0x1800162b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800162d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016316`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800162d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016316`

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
0x1800162b4  mov     [rsp+arg_0], rbx
0x1800162b9  mov     [rsp+arg_8], rsi
0x1800162be  push    rdi
0x1800162bf  sub     rsp, 20h
0x1800162c3  movsxd  rbx, r9d
0x1800162c6  mov     rsi, r8
0x1800162c9  add     rbx, rbx
0x1800162cc  jz      short loc_18001632D
0x1800162ce  test    rcx, rcx
0x1800162d1  jnz     short loc_1800162E7
0x1800162d3  call    cs:__imp__o__errno
0x1800162da  nop     dword ptr [rax+rax+00h]
0x1800162df  mov     dword ptr [rax], 16h
0x1800162e5  jmp     short loc_180016328
0x1800162e7  lea     rdi, [rdx+rdx]
0x1800162eb  test    rsi, rsi
0x1800162ee  jz      short loc_180016302
0x1800162f0  cmp     rdi, rbx
0x1800162f3  jb      short loc_180016302
0x1800162f5  mov     r8, rbx; Size
0x1800162f8  mov     rdx, rsi; Src
0x1800162fb  call    memcpy_0
0x180016300  jmp     short loc_18001632D
0x180016302  mov     r8, rdi; Size
0x180016305  xor     edx, edx; Val
0x180016307  call    memset_0
0x18001630c  test    rsi, rsi
0x18001630f  jz      short loc_1800162D3
0x180016311  cmp     rdi, rbx
0x180016314  jnb     short loc_18001632D
0x180016316  call    cs:__imp__o__errno
0x18001631d  nop     dword ptr [rax+rax+00h]
0x180016322  mov     dword ptr [rax], 22h ; '"'
0x180016328  call    _invalid_parameter_noinfo
0x18001632d  mov     rbx, [rsp+28h+arg_0]
0x180016332  mov     rsi, [rsp+28h+arg_8]
0x180016337  add     rsp, 20h
0x18001633b  pop     rdi
0x18001633c  retn
```

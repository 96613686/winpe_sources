# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)

- ea: `0x18006cf6c`
- end: `0x18006d047`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `219`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006f760`
- `0x18006f870`
- `0x18006f9f0`
- `0x18006faf0`
- `0x18006fca0`
- `0x18006fde0`
- `0x18006fea0`
- `0x18006ff60`

## callees

- `0x1800445e4`
- `0x18006cf6c`
- `0x18006d5bc`
- `0x180096078`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006cf91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006cf91`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(__int64 a1, _DWORD *a2)
{
  PROPVARIANT *Item; // rax
  __int64 v5; // rbx
  int v6; // edx
  unsigned int v7; // edx
  __int64 i; // r10
  __int64 v9; // rbx

  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
  v5 = (__int64)Item;
  if ( Item )
  {
    PropVariantClear(Item);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 60) == v6
      && (int)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::ExtendStorage(a1, (unsigned int)(2 * v6 + 4)) < 0 )
    {
      return 0;
    }
    else
    {
      v7 = *(_DWORD *)(a1 + 60);
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 40 * i) >= *a2 )
          break;
      }
      v9 = 5 * i;
      memmove_0(
        (void *)(*(_QWORD *)(a1 + 48) + 40LL * (unsigned int)(i + 1)),
        (const void *)(*(_QWORD *)(a1 + 48) + 40 * i),
        40LL * (v7 - (unsigned int)i));
      *(_OWORD *)(*(_QWORD *)(a1 + 48) + 8 * v9) = *(_OWORD *)a2;
      v5 = *(_QWORD *)(a1 + 48) + 8 * (v9 + 2);
      *(_OWORD *)v5 = 0;
      *(_QWORD *)(v5 + 16) = 0;
      ++*(_DWORD *)(a1 + 60);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18006cf6c  mov     [rsp+arg_0], rbx
0x18006cf71  mov     [rsp+arg_8], rsi
0x18006cf76  push    rdi
0x18006cf77  sub     rsp, 20h
0x18006cf7b  mov     rsi, rdx
0x18006cf7e  mov     rdi, rcx
0x18006cf81  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18006cf86  mov     rbx, rax
0x18006cf89  test    rax, rax
0x18006cf8c  jz      short loc_18006CFA2
0x18006cf8e  mov     rcx, rax; pvar
0x18006cf91  call    cs:__imp_PropVariantClear
0x18006cf98  nop     dword ptr [rax+rax+00h]
0x18006cf9d  jmp     loc_18006D033
0x18006cfa2  mov     edx, [rdi+38h]
0x18006cfa5  cmp     [rdi+3Ch], edx
0x18006cfa8  jnz     short loc_18006CFC1
0x18006cfaa  lea     edx, ds:4[rdx*2]
0x18006cfb1  mov     rcx, rdi
0x18006cfb4  call    ?ExtendStorage@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAJI@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::ExtendStorage(uint)
0x18006cfb9  test    eax, eax
0x18006cfbb  jns     short loc_18006CFC1
0x18006cfbd  xor     ebx, ebx
0x18006cfbf  jmp     short loc_18006D033
0x18006cfc1  mov     edx, [rdi+3Ch]
0x18006cfc4  xor     r10d, r10d
0x18006cfc7  test    edx, edx
0x18006cfc9  jz      short loc_18006CFE4
0x18006cfcb  mov     r8d, [rsi]
0x18006cfce  mov     r9, [rdi+30h]
0x18006cfd2  lea     rcx, [r10+r10*4]
0x18006cfd6  cmp     [r9+rcx*8], r8d
0x18006cfda  jnb     short loc_18006CFE4
0x18006cfdc  inc     r10d
0x18006cfdf  cmp     r10d, edx
0x18006cfe2  jb      short loc_18006CFD2
0x18006cfe4  mov     r9, [rdi+30h]
0x18006cfe8  lea     eax, [r10+1]
0x18006cfec  sub     edx, r10d
0x18006cfef  lea     rbx, [r10+r10*4]
0x18006cff3  lea     rax, [rax+rax*4]
0x18006cff7  lea     rcx, [r9+rax*8]; void *
0x18006cffb  lea     r8, [rdx+rdx*4]
0x18006cfff  shl     r8, 3; Size
0x18006d003  lea     rdx, [r9+rbx*8]; Src
0x18006d007  call    memmove_0
0x18006d00c  movups  xmm0, xmmword ptr [rsi]
0x18006d00f  mov     rax, [rdi+30h]
0x18006d013  movdqu  xmmword ptr [rax+rbx*8], xmm0
0x18006d018  mov     rax, [rdi+30h]
0x18006d01c  lea     rbx, [rbx+2]
0x18006d020  xorps   xmm0, xmm0
0x18006d023  lea     rbx, [rax+rbx*8]
0x18006d027  xor     eax, eax
0x18006d029  movups  xmmword ptr [rbx], xmm0
0x18006d02c  mov     [rbx+10h], rax
0x18006d030  inc     dword ptr [rdi+3Ch]
0x18006d033  mov     rsi, [rsp+28h+arg_8]
0x18006d038  mov     rax, rbx
0x18006d03b  mov     rbx, [rsp+28h+arg_0]
0x18006d040  add     rsp, 20h
0x18006d044  pop     rdi
0x18006d045  retn
```

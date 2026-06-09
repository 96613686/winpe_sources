# CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)

- ea: `0x1800781c8`
- end: `0x1800782b6`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `238`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007a2e0`
- `0x18007a3b0`
- `0x18007a440`
- `0x18007a4f0`
- `0x18007a5b0`
- `0x18007a6a0`
- `0x18007a710`
- `0x18007a780`

## callees

- `0x180010158`
- `0x1800781c8`
- `0x1800784ec`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180078293`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180078293`
- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180078266`
- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180078266`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800781ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800781ed`

## pseudocode

```c
PROPVARIANT *__fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(__int64 a1, _DWORD *a2)
{
  PROPVARIANT *Item; // rax
  PROPVARIANT *v5; // rbx
  int v6; // edx
  unsigned int v7; // edx
  __int64 i; // r10
  __int64 v9; // rbx

  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem();
  v5 = Item;
  if ( Item )
  {
    PropVariantClear(Item);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 60) == v6
      && (int)CMFAttributesImpl<IMFAttributes,CMFCSLock>::ExtendStorage(a1, (unsigned int)(2 * v6 + 4)) < 0 )
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
      memmove(
        (void *)(*(_QWORD *)(a1 + 48) + 40LL * (unsigned int)(i + 1)),
        (const void *)(*(_QWORD *)(a1 + 48) + 40 * i),
        40LL * (v7 - (unsigned int)i));
      *(_OWORD *)(*(_QWORD *)(a1 + 48) + 8 * v9) = *(_OWORD *)a2;
      v5 = (PROPVARIANT *)(*(_QWORD *)(a1 + 48) + 8 * (v9 + 2));
      memset(v5, 0, sizeof(PROPVARIANT));
      ++*(_DWORD *)(a1 + 60);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800781c8  mov     [rsp+arg_0], rbx
0x1800781cd  mov     [rsp+arg_8], rsi
0x1800781d2  push    rdi
0x1800781d3  sub     rsp, 20h
0x1800781d7  mov     rsi, rdx
0x1800781da  mov     rdi, rcx
0x1800781dd  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::_FindItem(_GUID const &)
0x1800781e2  mov     rbx, rax
0x1800781e5  test    rax, rax
0x1800781e8  jz      short loc_1800781FE
0x1800781ea  mov     rcx, rax; pvar
0x1800781ed  call    cs:__imp_PropVariantClear
0x1800781f4  nop     dword ptr [rax+rax+00h]
0x1800781f9  jmp     loc_1800782A2
0x1800781fe  mov     edx, [rdi+38h]
0x180078201  cmp     [rdi+3Ch], edx
0x180078204  jnz     short loc_180078220
0x180078206  lea     edx, ds:4[rdx*2]
0x18007820d  mov     rcx, rdi
0x180078210  call    ?ExtendStorage@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@IEAAJI@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::ExtendStorage(uint)
0x180078215  test    eax, eax
0x180078217  jns     short loc_180078220
0x180078219  xor     ebx, ebx
0x18007821b  jmp     loc_1800782A2
0x180078220  mov     edx, [rdi+3Ch]
0x180078223  xor     r10d, r10d
0x180078226  test    edx, edx
0x180078228  jz      short loc_180078243
0x18007822a  mov     r8d, [rsi]
0x18007822d  mov     r9, [rdi+30h]
0x180078231  lea     rcx, [r10+r10*4]
0x180078235  cmp     [r9+rcx*8], r8d
0x180078239  jnb     short loc_180078243
0x18007823b  inc     r10d
0x18007823e  cmp     r10d, edx
0x180078241  jb      short loc_180078231
0x180078243  mov     r9, [rdi+30h]
0x180078247  lea     eax, [r10+1]
0x18007824b  sub     edx, r10d
0x18007824e  lea     rbx, [r10+r10*4]
0x180078252  lea     rax, [rax+rax*4]
0x180078256  lea     rcx, [r9+rax*8]; void *
0x18007825a  lea     r8, [rdx+rdx*4]
0x18007825e  shl     r8, 3; Size
0x180078262  lea     rdx, [r9+rbx*8]; Src
0x180078266  call    cs:__imp_memmove
0x18007826d  nop     dword ptr [rax+rax+00h]
0x180078272  mov     rax, [rdi+30h]
0x180078276  xor     edx, edx; Val
0x180078278  movups  xmm0, xmmword ptr [rsi]
0x18007827b  movdqu  xmmword ptr [rax+rbx*8], xmm0
0x180078280  mov     rax, [rdi+30h]
0x180078284  lea     rbx, [rbx+2]
0x180078288  lea     r8d, [rdx+18h]; Size
0x18007828c  lea     rbx, [rax+rbx*8]
0x180078290  mov     rcx, rbx; void *
0x180078293  call    cs:__imp_memset
0x18007829a  nop     dword ptr [rax+rax+00h]
0x18007829f  inc     dword ptr [rdi+3Ch]
0x1800782a2  mov     rsi, [rsp+28h+arg_8]
0x1800782a7  mov     rax, rbx
0x1800782aa  mov     rbx, [rsp+28h+arg_0]
0x1800782af  add     rsp, 20h
0x1800782b3  pop     rdi
0x1800782b4  retn
```

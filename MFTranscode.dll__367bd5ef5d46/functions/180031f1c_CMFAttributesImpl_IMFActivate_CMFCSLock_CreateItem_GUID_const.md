# CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(_GUID const &)

- ea: `0x180031f1c`
- end: `0x180031ff0`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `212`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034680`
- `0x180034730`
- `0x1800347b0`
- `0x180034850`
- `0x180034ab0`
- `0x180034b90`
- `0x180034bf0`
- `0x180034c50`

## callees

- `0x1800088d0`
- `0x180031f1c`
- `0x18003254c`
- `0x1800594c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031f41`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180031f41`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(__int64 a1, _DWORD *a2)
{
  PROPVARIANT *Item; // rax
  __int64 v5; // rbx
  int v6; // edx
  unsigned int v7; // edx
  __int64 i; // r10
  __int64 v9; // rbx

  Item = (PROPVARIANT *)CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(a1, a2);
  v5 = (__int64)Item;
  if ( Item )
  {
    PropVariantClear(Item);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 60) == v6
      && (int)CMFAttributesImpl<IMFActivate,CMFCSLock>::ExtendStorage(a1, (unsigned int)(2 * v6 + 4)) < 0 )
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
0x180031f1c  mov     [rsp+arg_0], rbx
0x180031f21  mov     [rsp+arg_8], rsi
0x180031f26  push    rdi
0x180031f27  sub     rsp, 20h
0x180031f2b  mov     rsi, rdx
0x180031f2e  mov     rdi, rcx
0x180031f31  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x180031f36  mov     rbx, rax
0x180031f39  test    rax, rax
0x180031f3c  jz      short loc_180031F4C
0x180031f3e  mov     rcx, rax; pvar
0x180031f41  call    cs:__imp_PropVariantClear
0x180031f47  jmp     loc_180031FDD
0x180031f4c  mov     edx, [rdi+38h]
0x180031f4f  cmp     [rdi+3Ch], edx
0x180031f52  jnz     short loc_180031F6B
0x180031f54  lea     edx, ds:4[rdx*2]
0x180031f5b  mov     rcx, rdi
0x180031f5e  call    ?ExtendStorage@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAJI@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::ExtendStorage(uint)
0x180031f63  test    eax, eax
0x180031f65  jns     short loc_180031F6B
0x180031f67  xor     ebx, ebx
0x180031f69  jmp     short loc_180031FDD
0x180031f6b  mov     edx, [rdi+3Ch]
0x180031f6e  xor     r10d, r10d
0x180031f71  test    edx, edx
0x180031f73  jz      short loc_180031F8E
0x180031f75  mov     r8d, [rsi]
0x180031f78  mov     r9, [rdi+30h]
0x180031f7c  lea     rcx, [r10+r10*4]
0x180031f80  cmp     [r9+rcx*8], r8d
0x180031f84  jnb     short loc_180031F8E
0x180031f86  inc     r10d
0x180031f89  cmp     r10d, edx
0x180031f8c  jb      short loc_180031F7C
0x180031f8e  mov     r9, [rdi+30h]
0x180031f92  lea     eax, [r10+1]
0x180031f96  sub     edx, r10d
0x180031f99  lea     rbx, [r10+r10*4]
0x180031f9d  lea     rax, [rax+rax*4]
0x180031fa1  lea     rcx, [r9+rax*8]; void *
0x180031fa5  lea     r8, [rdx+rdx*4]
0x180031fa9  shl     r8, 3; Size
0x180031fad  lea     rdx, [r9+rbx*8]; Src
0x180031fb1  call    memmove_0
0x180031fb6  movups  xmm0, xmmword ptr [rsi]
0x180031fb9  mov     rax, [rdi+30h]
0x180031fbd  movdqu  xmmword ptr [rax+rbx*8], xmm0
0x180031fc2  mov     rax, [rdi+30h]
0x180031fc6  lea     rbx, [rbx+2]
0x180031fca  xorps   xmm0, xmm0
0x180031fcd  lea     rbx, [rax+rbx*8]
0x180031fd1  xor     eax, eax
0x180031fd3  movups  xmmword ptr [rbx], xmm0
0x180031fd6  mov     [rbx+10h], rax
0x180031fda  inc     dword ptr [rdi+3Ch]
0x180031fdd  mov     rsi, [rsp+28h+arg_8]
0x180031fe2  mov     rax, rbx
0x180031fe5  mov     rbx, [rsp+28h+arg_0]
0x180031fea  add     rsp, 20h
0x180031fee  pop     rdi
0x180031fef  retn
```

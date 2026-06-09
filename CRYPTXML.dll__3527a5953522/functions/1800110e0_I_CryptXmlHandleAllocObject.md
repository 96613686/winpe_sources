# I_CryptXmlHandleAllocObject

- ea: `0x1800110e0`
- end: `0x1800113c1`
- name: `I_CryptXmlHandleAllocObject`
- size: `737`
- prototype: `__int64 __fastcall(HANDLE hHeap)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001a40`
- `0x1800029b0`
- `0x180003650`

## callees

- `0x180004f60`
- `0x1800070d0`
- `0x1800110e0`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011150`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001134b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011150`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001134b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800111ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800111ed`

## string_xrefs

- `0x180011170`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x18001136f`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlHandleAllocObject(HANDLE hHeap, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // rax
  char *v8; // rax
  char *v9; // rbx
  unsigned int v10; // edi
  const char *v11; // r8
  char v12; // al
  const char *v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // r14
  char *v17; // r15
  int v18; // ecx
  const char *v19; // rax

  v5 = (unsigned int)(*(_DWORD *)(a3 + 8) + 1);
  *a4 = 0;
  v8 = (char *)HeapAlloc(
                 hHeap,
                 8u,
                 ((2LL * (unsigned int)(*(_DWORD *)(a3 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
               + ((2LL * (unsigned int)(*(_DWORD *)(a3 + 40) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
               + ((2 * v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL)
               + *(unsigned int *)(a3 + 52)
               + 240LL);
  v9 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 7) = 1;
    *(_DWORD *)v8 = 1145324612;
    *((_QWORD *)v8 + 6) = hHeap;
    *((_QWORD *)v8 + 14) = I_CRYPT_XML_HANDLE_FREE_OBJECT;
    *((_QWORD *)v8 + 8) = 12;
    *((_DWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 11) = 0;
    *((_QWORD *)v8 + 12) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    *((_QWORD *)v9 + 15) = CRYPT_XML_HANDLE_LOCK;
    *((_QWORD *)v9 + 16) = CRYPT_XML_HANDLE_UNLOCK;
    *((_QWORD *)v9 + 18) = *(_QWORD *)(a3 + 72);
    *((_QWORD *)v9 + 17) = v9 + 168;
    *((_DWORD *)v9 + 42) = 72;
    *((_QWORD *)v9 + 22) = v9;
    v15 = *((_QWORD *)v9 + 17);
    v16 = v15 + 72;
    if ( *(_DWORD *)(a3 + 8) )
    {
      *(_QWORD *)(v15 + 16) = v16;
      memcpy_0((void *)(v15 + 72), *(const void **)a3, 2LL * *(unsigned int *)(a3 + 8));
      v17 = (char *)(v16 + ((2LL * (unsigned int)(*(_DWORD *)(a3 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL));
    }
    else
    {
      v17 = (char *)(v15 + 72);
    }
    if ( *(_DWORD *)(a3 + 24) )
    {
      *(_QWORD *)(*((_QWORD *)v9 + 17) + 24LL) = v17;
      memcpy_0(v17, *(const void **)(a3 + 16), 2LL * *(unsigned int *)(a3 + 24));
      v17 += (2LL * (unsigned int)(*(_DWORD *)(a3 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    if ( *(_DWORD *)(a3 + 40) )
    {
      *(_QWORD *)(*((_QWORD *)v9 + 17) + 32LL) = v17;
      memcpy_0(v17, *(const void **)(a3 + 32), 2LL * *(unsigned int *)(a3 + 40));
      v17 += (2LL * (unsigned int)(*(_DWORD *)(a3 + 40) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    if ( *(_DWORD *)(a3 + 52) )
    {
      *(_DWORD *)(*((_QWORD *)v9 + 17) + 56LL) = *(_DWORD *)(a3 + 48);
      *(_QWORD *)(*((_QWORD *)v9 + 17) + 64LL) = v17;
      *(_DWORD *)(*((_QWORD *)v9 + 17) + 60LL) = *(_DWORD *)(a3 + 52);
      memcpy_0(v17, *(const void **)(a3 + 56), *(unsigned int *)(a3 + 52));
    }
    v18 = *(_DWORD *)(a3 + 64);
    if ( !v18
      || (*(_DWORD *)(*((_QWORD *)v9 + 17) + 40LL) = v18,
          (*(_QWORD *)(*((_QWORD *)v9 + 17) + 48LL) = HeapAlloc(hHeap, 8u, 8LL * *(unsigned int *)(a3 + 64))) != 0) )
    {
      *a4 = v9;
      _InterlockedIncrement((volatile signed __int32 *)v9 + 14);
      v10 = 0;
    }
    else
    {
      v10 = -2147024882;
      v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v19, 140);
    }
    I_CryptXmlRelease(v9);
  }
  else
  {
    v10 = -2147024882;
    v11 = "";
    while ( 1 )
    {
      v12 = *(v11 - 1);
      v13 = v11--;
      v14 = v12 == 92;
      if ( v12 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp" )
      {
        v14 = v12 == 92;
        break;
      }
    }
    if ( v14 )
      v11 = v13;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v11, 66);
  }
  return v10;
}

```

## disassembly

```asm
0x1800110e0  mov     [rsp+arg_10], rbx
0x1800110e5  mov     [rsp+arg_18], rbp
0x1800110ea  push    rsi
0x1800110eb  push    rdi
0x1800110ec  push    r12
0x1800110ee  sub     rsp, 20h
0x1800110f2  mov     eax, [r8+8]
0x1800110f6  mov     rdi, r8
0x1800110f9  inc     eax
0x1800110fb  xor     r12d, r12d
0x1800110fe  mov     rsi, r9
0x180011101  mov     [r9], r12
0x180011104  mov     rbp, rcx
0x180011107  lea     rdx, ds:7[rax*2]
0x18001110f  mov     eax, [r8+28h]
0x180011113  inc     eax
0x180011115  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180011119  lea     rax, ds:7[rax*2]
0x180011121  and     rax, 0FFFFFFFFFFFFFFF8h
0x180011125  add     rdx, rax
0x180011128  mov     eax, [r8+18h]
0x18001112c  mov     r8d, [r8+34h]
0x180011130  inc     eax
0x180011132  add     r8, 0F0h
0x180011139  lea     rax, ds:7[rax*2]
0x180011141  and     rax, 0FFFFFFFFFFFFFFF8h
0x180011145  add     rdx, rax
0x180011148  add     r8, rdx; dwBytes
0x18001114b  mov     edx, 8; dwFlags
0x180011150  call    cs:__imp_HeapAlloc
0x180011157  nop     dword ptr [rax+rax+00h]
0x18001115c  mov     rbx, rax
0x18001115f  test    rax, rax
0x180011162  jnz     short loc_1800111AA
0x180011164  mov     edi, 8007000Eh
0x180011169  lea     r8, aOnecoreDsSecur_9+30h; ""
0x180011170  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011177  movzx   eax, byte ptr [r8-1]
0x18001117c  mov     rdx, r8
0x18001117f  dec     r8
0x180011182  cmp     al, 5Ch ; '\'
0x180011184  jz      short loc_18001118D
0x180011186  cmp     r8, rcx
0x180011189  ja      short loc_180011177
0x18001118b  cmp     al, 5Ch ; '\'
0x18001118d  cmovz   r8, rdx
0x180011191  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011198  mov     edx, edi
0x18001119a  mov     r9d, 42h ; 'B'
0x1800111a0  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800111a5  jmp     loc_1800113AB
0x1800111aa  mov     qword ptr [rax+38h], 1
0x1800111b2  lea     rcx, [rbx+8]; lpCriticalSection
0x1800111b6  mov     dword ptr [rax], 44444444h
0x1800111bc  mov     [rax+30h], rbp
0x1800111c0  lea     rax, ?I_CRYPT_XML_HANDLE_FREE_OBJECT@@YAJPEAU_HXML_HANDLE@@@Z; I_CRYPT_XML_HANDLE_FREE_OBJECT(_HXML_HANDLE *)
0x1800111c7  mov     [rsp+38h+arg_0], r14
0x1800111cc  mov     [rbx+70h], rax
0x1800111d0  mov     [rsp+38h+arg_8], r15
0x1800111d5  mov     qword ptr [rbx+40h], 0Ch
0x1800111dd  mov     [rbx+48h], r12d
0x1800111e1  mov     [rbx+50h], r12
0x1800111e5  mov     [rbx+58h], r12
0x1800111e9  mov     [rbx+60h], r12
0x1800111ed  call    cs:__imp_InitializeCriticalSection
0x1800111f4  nop     dword ptr [rax+rax+00h]
0x1800111f9  lea     rax, _CRYPT_XML_HANDLE_LOCK
0x180011200  mov     [rbx+78h], rax
0x180011204  lea     rax, _CRYPT_XML_HANDLE_UNLOCK
0x18001120b  mov     [rbx+80h], rax
0x180011212  mov     rax, [rdi+48h]
0x180011216  mov     [rbx+90h], rax
0x18001121d  lea     rax, [rbx+0A8h]
0x180011224  mov     [rbx+88h], rax
0x18001122b  mov     dword ptr [rax], 48h ; 'H'
0x180011231  mov     [rax+8], rbx
0x180011235  mov     rax, [rbx+88h]
0x18001123c  lea     r14, [rax+48h]
0x180011240  cmp     [rdi+8], r12d
0x180011244  jbe     short loc_180011272
0x180011246  mov     [rax+10h], r14
0x18001124a  mov     rcx, r14; void *
0x18001124d  mov     r8d, [rdi+8]
0x180011251  mov     rdx, [rdi]; Src
0x180011254  add     r8, r8; Size
0x180011257  call    memcpy_0
0x18001125c  mov     eax, [rdi+8]
0x18001125f  inc     eax
0x180011261  lea     r15, ds:7[rax*2]
0x180011269  and     r15, 0FFFFFFFFFFFFFFF8h
0x18001126d  add     r15, r14
0x180011270  jmp     short loc_180011275
0x180011272  mov     r15, r14
0x180011275  mov     r14, [rsp+38h+arg_0]
0x18001127a  cmp     [rdi+18h], r12d
0x18001127e  jbe     short loc_1800112B2
0x180011280  mov     rax, [rbx+88h]
0x180011287  mov     rcx, r15; void *
0x18001128a  mov     [rax+18h], r15
0x18001128e  mov     r8d, [rdi+18h]
0x180011292  mov     rdx, [rdi+10h]; Src
0x180011296  add     r8, r8; Size
0x180011299  call    memcpy_0
0x18001129e  mov     eax, [rdi+18h]
0x1800112a1  inc     eax
0x1800112a3  lea     rax, ds:7[rax*2]
0x1800112ab  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800112af  add     r15, rax
0x1800112b2  cmp     [rdi+28h], r12d
0x1800112b6  jbe     short loc_1800112EA
0x1800112b8  mov     rax, [rbx+88h]
0x1800112bf  mov     rcx, r15; void *
0x1800112c2  mov     [rax+20h], r15
0x1800112c6  mov     r8d, [rdi+28h]
0x1800112ca  mov     rdx, [rdi+20h]; Src
0x1800112ce  add     r8, r8; Size
0x1800112d1  call    memcpy_0
0x1800112d6  mov     eax, [rdi+28h]
0x1800112d9  inc     eax
0x1800112db  lea     rax, ds:7[rax*2]
0x1800112e3  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800112e7  add     r15, rax
0x1800112ea  cmp     [rdi+34h], r12d
0x1800112ee  jbe     short loc_180011325
0x1800112f0  mov     rdx, [rbx+88h]
0x1800112f7  mov     rcx, r15; void *
0x1800112fa  mov     eax, [rdi+30h]
0x1800112fd  mov     [rdx+38h], eax
0x180011300  mov     rax, [rbx+88h]
0x180011307  mov     [rax+40h], r15
0x18001130b  mov     rdx, [rbx+88h]
0x180011312  mov     eax, [rdi+34h]
0x180011315  mov     [rdx+3Ch], eax
0x180011318  mov     r8d, [rdi+34h]; Size
0x18001131c  mov     rdx, [rdi+38h]; Src
0x180011320  call    memcpy_0
0x180011325  mov     ecx, [rdi+40h]
0x180011328  mov     r15, [rsp+38h+arg_8]
0x18001132d  test    ecx, ecx
0x18001132f  jz      short loc_180011399
0x180011331  mov     rax, [rbx+88h]
0x180011338  mov     edx, 8; dwFlags
0x18001133d  mov     [rax+28h], ecx
0x180011340  mov     rcx, rbp; hHeap
0x180011343  mov     r8d, [rdi+40h]
0x180011347  shl     r8, 3; dwBytes
0x18001134b  call    cs:__imp_HeapAlloc
0x180011352  nop     dword ptr [rax+rax+00h]
0x180011357  mov     rcx, [rbx+88h]
0x18001135e  mov     [rcx+30h], rax
0x180011362  mov     rax, [rbx+88h]
0x180011369  cmp     [rax+30h], r12
0x18001136d  jnz     short loc_180011399
0x18001136f  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011376  mov     edi, 8007000Eh
0x18001137b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011380  mov     r8, rax
0x180011383  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001138a  mov     edx, edi
0x18001138c  mov     r9d, 8Ch
0x180011392  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011397  jmp     short loc_1800113A3
0x180011399  mov     [rsi], rbx
0x18001139c  lock inc dword ptr [rbx+38h]
0x1800113a0  mov     edi, r12d
0x1800113a3  mov     rcx, rbx
0x1800113a6  call    I_CryptXmlRelease
0x1800113ab  mov     rbx, [rsp+38h+arg_10]
0x1800113b0  mov     eax, edi
0x1800113b2  mov     rbp, [rsp+38h+arg_18]
0x1800113b7  add     rsp, 20h
0x1800113bb  pop     r12
0x1800113bd  pop     rdi
0x1800113be  pop     rsi
0x1800113bf  retn
```

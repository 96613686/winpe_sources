# I_CryptXmlHandleAllocReference

- ea: `0x1800049c0`
- end: `0x180004f59`
- name: `I_CryptXmlHandleAllocReference`
- size: `1433`
- prototype: `__int64 __fastcall(HANDLE hHeap, int, int, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001010`
- `0x180003650`

## callees

- `0x1800049c0`
- `0x180004f60`
- `0x1800070d0`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004bc7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004bc7`

## string_xrefs

- `0x180004b02`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180004b42`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180004f0a`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlHandleAllocReference(HANDLE hHeap, int a2, int a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  unsigned int v9; // r9d
  unsigned int v12; // r10d
  unsigned int v13; // r11d
  unsigned int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // r12
  unsigned int v17; // r8d
  SIZE_T v18; // r10
  unsigned int i; // edx
  unsigned int v20; // eax
  const char *v21; // r8
  int v22; // r9d
  char *v23; // rax
  char *v24; // rbx
  const char *v25; // r8
  char v26; // dl
  const char *v27; // r9
  bool v28; // zf
  __int64 (__fastcall *v30)(); // rax
  __int64 (__fastcall *v31)(); // rcx
  _QWORD *v32; // rdx
  char *v33; // r14
  char *v34; // rbp
  __int64 v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // r14d
  __int64 v38; // r12
  __int64 v39; // r15
  __int64 v40; // rax
  char *v41; // r9
  _WORD *v42; // rax
  char v43; // al
  const char *v44; // rdx
  bool v45; // zf
  __int64 v46; // [rsp+98h] [rbp+30h]

  v9 = *(_DWORD *)(a4 + 8);
  *a6 = 0;
  if ( v9 > 0x100
    || (v12 = *(_DWORD *)(a4 + 24), v12 > 0x2000)
    || (v13 = *(_DWORD *)(a4 + 40), v13 > 0x2000)
    || (v14 = *(_DWORD *)(a4 + 56), v14 > 0x2000)
    || (v15 = *(unsigned int *)(a4 + 68), (unsigned int)v15 > 0x7FFFFFF8)
    || (v16 = *(unsigned int *)(a4 + 88), (unsigned int)v16 > 0x80)
    || (v17 = *(_DWORD *)(a4 + 92), v17 > 0x10) )
  {
    v21 = "";
    while ( 1 )
    {
      v43 = *(v21 - 1);
      v44 = v21--;
      v45 = v43 == 92;
      if ( v43 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
      {
        v45 = v43 == 92;
        break;
      }
    }
    if ( v45 )
      v21 = v44;
    v22 = 67;
LABEL_56:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v21, v22);
    return 2148081921LL;
  }
  else
  {
    v18 = 32LL * v17
        + ((v15 + 7) & 0xFFFFFFFFFFFFFFF8uLL)
        + ((2LL * (v9 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
        + ((2LL * (v12 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
        + ((2LL * (v13 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
        + ((2LL * (v14 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
        + v16
        + 400;
    for ( i = 0; i < v17; ++i )
    {
      v20 = *(_DWORD *)(a4 + 40LL * i + 104);
      if ( v20 > 0x2000 )
      {
        v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v22 = 88;
        goto LABEL_56;
      }
      v18 += ((2LL * (v20 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
           + ((*(unsigned int *)(a4 + 40LL * i + 116) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    v23 = (char *)HeapAlloc(hHeap, 8u, v18);
    v24 = v23;
    if ( v23 )
    {
      *((_DWORD *)v23 + 14) = 1;
      *(_DWORD *)v23 = 1145324611;
      *((_QWORD *)v23 + 6) = hHeap;
      *((_DWORD *)v23 + 15) = a3;
      *((_QWORD *)v23 + 14) = I_CRYPT_XML_HANDLE_FREE_REFERENCE;
      *((_QWORD *)v23 + 8) = 12;
      *((_DWORD *)v23 + 18) = 0;
      *((_QWORD *)v23 + 10) = 0;
      *((_QWORD *)v23 + 11) = 0;
      *((_QWORD *)v23 + 12) = 0;
      if ( a3 < 0 )
      {
        v30 = 0;
        v31 = 0;
      }
      else
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(v23 + 8));
        v30 = CRYPT_XML_HANDLE_UNLOCK;
        v31 = CRYPT_XML_HANDLE_LOCK;
      }
      *((_QWORD *)v24 + 15) = v31;
      *((_QWORD *)v24 + 16) = v30;
      *((_DWORD *)v24 + 17) |= 1u;
      *((_QWORD *)v24 + 10) = a5;
      *((_QWORD *)v24 + 36) = *(_QWORD *)(a4 + 736);
      if ( a2 )
        *((_DWORD *)v24 + 18) |= 0x80000000;
      *((_QWORD *)v24 + 17) = v24 + 296;
      *((_DWORD *)v24 + 74) = 104;
      *((_QWORD *)v24 + 38) = v24;
      *(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL) = *((_QWORD *)v24 + 17) + 104LL;
      v32 = (_QWORD *)*((_QWORD *)v24 + 17);
      v33 = (char *)(v32[12] + 32LL * *(unsigned int *)(a4 + 92));
      if ( *(_DWORD *)(a4 + 8) )
      {
        v32[2] = v33;
        memcpy_0(v33, *(const void **)a4, 2LL * *(unsigned int *)(a4 + 8));
        v32 = (_QWORD *)*((_QWORD *)v24 + 17);
        v34 = &v33[(2LL * (unsigned int)(*(_DWORD *)(a4 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL];
      }
      else
      {
        v34 = (char *)(v32[12] + 32LL * *(unsigned int *)(a4 + 92));
      }
      if ( *(_QWORD *)(a4 + 16) )
      {
        v32[3] = v34;
        memcpy_0(v34, *(const void **)(a4 + 16), 2LL * *(unsigned int *)(a4 + 24));
        v32 = (_QWORD *)*((_QWORD *)v24 + 17);
        v34 += (2LL * (unsigned int)(*(_DWORD *)(a4 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      if ( *(_QWORD *)(a4 + 32) )
      {
        v32[4] = v34;
        memcpy_0(v34, *(const void **)(a4 + 32), 2LL * *(unsigned int *)(a4 + 40));
        v34 += (2LL * (unsigned int)(*(_DWORD *)(a4 + 40) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      *(_DWORD *)(*((_QWORD *)v24 + 17) + 40LL) = 32;
      if ( *(_QWORD *)(a4 + 48) )
      {
        *(_QWORD *)(*((_QWORD *)v24 + 17) + 48LL) = v34;
        memcpy_0(v34, *(const void **)(a4 + 48), 2LL * *(unsigned int *)(a4 + 56));
        v34 += (2LL * (unsigned int)(*(_DWORD *)(a4 + 56) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      *(_DWORD *)(*((_QWORD *)v24 + 17) + 60LL) = *(_DWORD *)(a4 + 68);
      v35 = *((_QWORD *)v24 + 17);
      if ( *(_DWORD *)(v35 + 60) )
      {
        *(_QWORD *)(v35 + 64) = v34;
        *(_DWORD *)(*((_QWORD *)v24 + 17) + 56LL) = *(_DWORD *)(a4 + 64);
        memcpy_0(v34, *(const void **)(a4 + 72), *(unsigned int *)(a4 + 68));
        v34 += (*(unsigned int *)(a4 + 68) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      *(_DWORD *)(*((_QWORD *)v24 + 17) + 72LL) = *(_DWORD *)(a4 + 88);
      v36 = *((_QWORD *)v24 + 17);
      if ( *(_DWORD *)(v36 + 72) )
      {
        *(_QWORD *)(v36 + 80) = v34;
        memcpy_0(v34, *(const void **)(a4 + 80), *(unsigned int *)(a4 + 88));
        v36 = *((_QWORD *)v24 + 17);
        v34 += (*(unsigned int *)(v36 + 72) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      }
      v37 = 0;
      for ( *(_DWORD *)(v36 + 88) = *(_DWORD *)(a4 + 92); v37 < *(_DWORD *)(a4 + 92); ++v37 )
      {
        v38 = 32LL * v37;
        *(_DWORD *)(v38 + *(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL)) = 32;
        v39 = a4 + 40LL * v37;
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL) + v38 + 8) = v34;
        memcpy_0(v34, *(const void **)(v39 + 96), 2LL * *(unsigned int *)(v39 + 104));
        v40 = (unsigned int)(*(_DWORD *)(v39 + 104) + 1);
        v41 = &v34[(2 * v40 + 7) & 0xFFFFFFFFFFFFFFF8uLL];
        v46 = (__int64)v41;
        if ( *(_DWORD *)(v39 + 116) )
        {
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL) + v38 + 24) = v41;
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL) + v38 + 20) = *(_DWORD *)(v39 + 116);
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 17) + 96LL) + v38 + 16) = *(_DWORD *)(v39 + 112);
          memcpy_0(v41, *(const void **)(a4 + 40LL * v37 + 120), *(unsigned int *)(v39 + 116));
          v34 = (char *)(v46 + ((*(unsigned int *)(v39 + 116) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL));
        }
        else
        {
          v34 += (2 * v40 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        }
      }
      v42 = *(_WORD **)(a4 + 16);
      if ( v42 && (!*(_DWORD *)(a4 + 24) || *v42 == 35) )
        *((_DWORD *)v24 + 18) |= 1u;
      *a6 = v24;
      _InterlockedIncrement((volatile signed __int32 *)v24 + 14);
      I_CryptXmlRelease(v24);
      return 0;
    }
    else
    {
      v25 = "";
      while ( 1 )
      {
        v26 = *(v25 - 1);
        v27 = v25--;
        v28 = v26 == 92;
        if ( v26 == 92 )
          break;
        if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v28 = v26 == 92;
          break;
        }
      }
      if ( v28 )
        v25 = v27;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v25, 100);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x1800049c0  push    rbx
0x1800049c2  push    rbp
0x1800049c3  push    rsi
0x1800049c4  push    rdi
0x1800049c5  push    r12
0x1800049c7  push    r13
0x1800049c9  push    r14
0x1800049cb  push    r15
0x1800049cd  sub     rsp, 28h
0x1800049d1  mov     rsi, [rsp+68h+arg_28]
0x1800049d9  xor     r13d, r13d
0x1800049dc  mov     rdi, r9
0x1800049df  mov     r14d, r8d
0x1800049e2  mov     r9d, [r9+8]
0x1800049e6  mov     r15d, edx
0x1800049e9  mov     rbp, rcx
0x1800049ec  mov     [rsi], r13
0x1800049ef  cmp     r9d, 100h
0x1800049f6  ja      loc_180004F03
0x1800049fc  mov     r10d, [rdi+18h]
0x180004a00  cmp     r10d, 2000h
0x180004a07  ja      loc_180004F03
0x180004a0d  mov     r11d, [rdi+28h]
0x180004a11  cmp     r11d, 2000h
0x180004a18  ja      loc_180004F03
0x180004a1e  mov     eax, [rdi+38h]
0x180004a21  cmp     eax, 2000h
0x180004a26  ja      loc_180004F03
0x180004a2c  mov     ebx, [rdi+44h]
0x180004a2f  cmp     ebx, 7FFFFFF8h
0x180004a35  ja      loc_180004F03
0x180004a3b  mov     r12d, [rdi+58h]
0x180004a3f  cmp     r12d, 80h
0x180004a46  ja      loc_180004F03
0x180004a4c  mov     r8d, [rdi+5Ch]
0x180004a50  cmp     r8d, 10h
0x180004a54  ja      loc_180004F03
0x180004a5a  inc     eax
0x180004a5c  lea     rdx, ds:7[rax*2]
0x180004a64  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180004a68  lea     eax, [r11+1]
0x180004a6c  lea     rcx, ds:7[rax*2]
0x180004a74  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004a78  lea     eax, [r10+1]
0x180004a7c  add     rdx, rcx
0x180004a7f  lea     r10, [r12+190h]
0x180004a87  lea     rcx, ds:7[rax*2]
0x180004a8f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004a93  lea     eax, [r9+1]
0x180004a97  add     rdx, rcx
0x180004a9a  lea     rcx, ds:7[rax*2]
0x180004aa2  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004aa6  lea     rax, [rbx+7]
0x180004aaa  add     rdx, rcx
0x180004aad  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004ab1  add     rdx, rax
0x180004ab4  mov     eax, r8d
0x180004ab7  shl     rax, 5
0x180004abb  add     rdx, rax
0x180004abe  add     r10, rdx
0x180004ac1  mov     edx, r13d
0x180004ac4  cmp     edx, r8d
0x180004ac7  jnb     short loc_180004B1C
0x180004ac9  mov     eax, edx
0x180004acb  lea     rcx, [rax+rax*4]
0x180004acf  mov     eax, [rdi+rcx*8+68h]
0x180004ad3  lea     r9, [rdi+rcx*8]
0x180004ad7  cmp     eax, 2000h
0x180004adc  ja      short loc_180004B02
0x180004ade  inc     eax
0x180004ae0  lea     rcx, ds:7[rax*2]
0x180004ae8  mov     eax, [r9+74h]
0x180004aec  add     rax, 7
0x180004af0  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180004af4  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004af8  add     r10, rax
0x180004afb  add     r10, rcx
0x180004afe  inc     edx
0x180004b00  jmp     short loc_180004AC4
0x180004b02  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004b09  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004b0e  mov     r8, rax
0x180004b11  mov     r9d, 58h ; 'X'
0x180004b17  jmp     loc_180004F31
0x180004b1c  mov     r8, r10; dwBytes
0x180004b1f  mov     edx, 8; dwFlags
0x180004b24  mov     rcx, rbp; hHeap
0x180004b27  call    cs:__imp_HeapAlloc
0x180004b2e  nop     dword ptr [rax+rax+00h]
0x180004b33  mov     rbx, rax
0x180004b36  test    rax, rax
0x180004b39  jnz     short loc_180004B86
0x180004b3b  lea     r8, aOnecoreDsSecur_14+33h; ""
0x180004b42  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004b49  movzx   edx, byte ptr [r8-1]
0x180004b4e  mov     r9, r8
0x180004b51  dec     r8
0x180004b54  cmp     dl, 5Ch ; '\'
0x180004b57  jz      short loc_180004B61
0x180004b59  cmp     r8, rcx
0x180004b5c  ja      short loc_180004B49
0x180004b5e  cmp     dl, 5Ch ; '\'
0x180004b61  cmovz   r8, r9
0x180004b65  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004b6c  mov     r9d, 64h ; 'd'
0x180004b72  mov     edx, 8007000Eh
0x180004b77  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180004b7c  mov     eax, 8007000Eh
0x180004b81  jmp     loc_180004F47
0x180004b86  mov     dword ptr [rax+38h], 1
0x180004b8d  mov     dword ptr [rax], 44444443h
0x180004b93  mov     [rax+30h], rbp
0x180004b97  mov     [rax+3Ch], r14d
0x180004b9b  lea     rax, ?I_CRYPT_XML_HANDLE_FREE_REFERENCE@@YAJPEAU_HXML_HANDLE@@@Z; I_CRYPT_XML_HANDLE_FREE_REFERENCE(_HXML_HANDLE *)
0x180004ba2  mov     [rbx+70h], rax
0x180004ba6  mov     qword ptr [rbx+40h], 0Ch
0x180004bae  mov     [rbx+48h], r13d
0x180004bb2  mov     [rbx+50h], r13
0x180004bb6  mov     [rbx+58h], r13
0x180004bba  mov     [rbx+60h], r13
0x180004bbe  test    r14d, r14d
0x180004bc1  js      short loc_180004BE3
0x180004bc3  lea     rcx, [rbx+8]; lpCriticalSection
0x180004bc7  call    cs:__imp_InitializeCriticalSection
0x180004bce  nop     dword ptr [rax+rax+00h]
0x180004bd3  lea     rax, _CRYPT_XML_HANDLE_UNLOCK
0x180004bda  lea     rcx, _CRYPT_XML_HANDLE_LOCK
0x180004be1  jmp     short loc_180004BE9
0x180004be3  mov     rax, r13
0x180004be6  mov     rcx, r13
0x180004be9  mov     [rbx+78h], rcx
0x180004bed  mov     [rbx+80h], rax
0x180004bf4  mov     rax, [rsp+68h+arg_20]
0x180004bfc  or      dword ptr [rbx+44h], 1
0x180004c00  mov     [rbx+50h], rax
0x180004c04  mov     rax, [rdi+2E0h]
0x180004c0b  mov     [rbx+120h], rax
0x180004c12  test    r15d, r15d
0x180004c15  jz      short loc_180004C1E
0x180004c17  or      dword ptr [rbx+48h], 80000000h
0x180004c1e  lea     rax, [rbx+128h]
0x180004c25  mov     [rbx+88h], rax
0x180004c2c  mov     dword ptr [rax], 68h ; 'h'
0x180004c32  mov     [rax+8], rbx
0x180004c36  mov     rcx, [rbx+88h]
0x180004c3d  lea     rax, [rcx+68h]
0x180004c41  mov     [rcx+60h], rax
0x180004c45  mov     rdx, [rbx+88h]
0x180004c4c  mov     r14d, [rdi+5Ch]
0x180004c50  shl     r14, 5
0x180004c54  add     r14, [rdx+60h]
0x180004c58  cmp     [rdi+8], r13d
0x180004c5c  jbe     short loc_180004C91
0x180004c5e  mov     [rdx+10h], r14
0x180004c62  mov     rcx, r14; void *
0x180004c65  mov     r8d, [rdi+8]
0x180004c69  mov     rdx, [rdi]; Src
0x180004c6c  add     r8, r8; Size
0x180004c6f  call    memcpy_0
0x180004c74  mov     eax, [rdi+8]
0x180004c77  mov     rdx, [rbx+88h]
0x180004c7e  inc     eax
0x180004c80  lea     rbp, ds:7[rax*2]
0x180004c88  and     rbp, 0FFFFFFFFFFFFFFF8h
0x180004c8c  add     rbp, r14
0x180004c8f  jmp     short loc_180004C94
0x180004c91  mov     rbp, r14
0x180004c94  cmp     [rdi+10h], r13
0x180004c98  jz      short loc_180004CCC
0x180004c9a  mov     [rdx+18h], rbp
0x180004c9e  mov     rcx, rbp; void *
0x180004ca1  mov     r8d, [rdi+18h]
0x180004ca5  mov     rdx, [rdi+10h]; Src
0x180004ca9  add     r8, r8; Size
0x180004cac  call    memcpy_0
0x180004cb1  mov     eax, [rdi+18h]
0x180004cb4  mov     rdx, [rbx+88h]
0x180004cbb  inc     eax
0x180004cbd  lea     rax, ds:7[rax*2]
0x180004cc5  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004cc9  add     rbp, rax
0x180004ccc  cmp     [rdi+20h], r13
0x180004cd0  jz      short loc_180004CFD
0x180004cd2  mov     [rdx+20h], rbp
0x180004cd6  mov     rcx, rbp; void *
0x180004cd9  mov     r8d, [rdi+28h]
0x180004cdd  mov     rdx, [rdi+20h]; Src
0x180004ce1  add     r8, r8; Size
0x180004ce4  call    memcpy_0
0x180004ce9  mov     eax, [rdi+28h]
0x180004cec  inc     eax
0x180004cee  lea     rax, ds:7[rax*2]
0x180004cf6  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004cfa  add     rbp, rax
0x180004cfd  mov     rax, [rbx+88h]
0x180004d04  mov     dword ptr [rax+28h], 20h ; ' '
0x180004d0b  cmp     [rdi+30h], r13
0x180004d0f  jz      short loc_180004D43
0x180004d11  mov     rax, [rbx+88h]
0x180004d18  mov     rcx, rbp; void *
0x180004d1b  mov     [rax+30h], rbp
0x180004d1f  mov     r8d, [rdi+38h]
0x180004d23  mov     rdx, [rdi+30h]; Src
0x180004d27  add     r8, r8; Size
0x180004d2a  call    memcpy_0
0x180004d2f  mov     eax, [rdi+38h]
0x180004d32  inc     eax
0x180004d34  lea     rax, ds:7[rax*2]
0x180004d3c  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004d40  add     rbp, rax
0x180004d43  mov     eax, [rdi+44h]
0x180004d46  mov     rcx, [rbx+88h]
0x180004d4d  mov     [rcx+3Ch], eax
0x180004d50  mov     rax, [rbx+88h]
0x180004d57  cmp     [rax+3Ch], r13d
0x180004d5b  jbe     short loc_180004D8C
0x180004d5d  mov     [rax+40h], rbp
0x180004d61  mov     rcx, [rbx+88h]
0x180004d68  mov     eax, [rdi+40h]
0x180004d6b  mov     [rcx+38h], eax
0x180004d6e  mov     rcx, rbp; void *
0x180004d71  mov     r8d, [rdi+44h]; Size
0x180004d75  mov     rdx, [rdi+48h]; Src
0x180004d79  call    memcpy_0
0x180004d7e  mov     eax, [rdi+44h]
0x180004d81  add     rax, 7
0x180004d85  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004d89  add     rbp, rax
0x180004d8c  mov     rcx, [rbx+88h]
0x180004d93  mov     eax, [rdi+58h]
0x180004d96  mov     [rcx+48h], eax
0x180004d99  mov     rcx, [rbx+88h]
0x180004da0  cmp     [rcx+48h], r13d
0x180004da4  jbe     short loc_180004DCF
0x180004da6  mov     [rcx+50h], rbp
0x180004daa  mov     rcx, rbp; void *
0x180004dad  mov     r8d, [rdi+58h]; Size
0x180004db1  mov     rdx, [rdi+50h]; Src
0x180004db5  call    memcpy_0
0x180004dba  mov     rcx, [rbx+88h]
0x180004dc1  mov     eax, [rcx+48h]
0x180004dc4  add     rax, 7
0x180004dc8  and     rax, 0FFFFFFFFFFFFFFF8h
0x180004dcc  add     rbp, rax
0x180004dcf  mov     eax, [rdi+5Ch]
0x180004dd2  mov     r14d, r13d
0x180004dd5  mov     [rcx+58h], eax
0x180004dd8  cmp     [rdi+5Ch], r13d
0x180004ddc  jbe     loc_180004ED2
0x180004de2  mov     rax, [rbx+88h]
0x180004de9  mov     r13d, r14d
0x180004dec  mov     r12d, r14d
0x180004def  shl     r12, 5
0x180004df3  mov     rcx, [rax+60h]
0x180004df7  mov     dword ptr [r12+rcx], 20h ; ' '
0x180004dff  mov     rax, [rbx+88h]
0x180004e06  mov     rcx, [rax+60h]
0x180004e0a  lea     rax, ds:0[r13*4]
0x180004e12  add     rax, r13
0x180004e15  lea     r15, [rdi+rax*8]
0x180004e19  mov     [rcx+r12+8], rbp
0x180004e1e  mov     rcx, rbp; void *
0x180004e21  mov     r8d, [r15+68h]
0x180004e25  mov     rdx, [r15+60h]; Src
0x180004e29  add     r8, r8; Size
0x180004e2c  call    memcpy_0
0x180004e31  mov     eax, [r15+68h]
0x180004e35  inc     eax
0x180004e37  lea     r9, ds:7[rax*2]
0x180004e3f  and     r9, 0FFFFFFFFFFFFFFF8h
0x180004e43  add     r9, rbp
0x180004e46  cmp     dword ptr [r15+74h], 0
0x180004e4b  mov     [rsp+68h+arg_28], r9
0x180004e53  jbe     short loc_180004EBF
0x180004e55  mov     rax, [rbx+88h]
0x180004e5c  lea     rdx, ds:0[r13*4]
0x180004e64  add     rdx, r13
0x180004e67  mov     rcx, [rax+60h]
0x180004e6b  mov     [rcx+r12+18h], r9
0x180004e70  mov     rax, [rbx+88h]
0x180004e77  mov     rcx, [rax+60h]
0x180004e7b  mov     eax, [r15+74h]
0x180004e7f  mov     [rcx+r12+14h], eax
0x180004e84  mov     rax, [rbx+88h]
0x180004e8b  mov     rcx, [rax+60h]
0x180004e8f  mov     eax, [r15+70h]
0x180004e93  mov     [rcx+r12+10h], eax
0x180004e98  mov     rcx, r9; void *
0x180004e9b  mov     r8d, [r15+74h]; Size
0x180004e9f  mov     rdx, [rdi+rdx*8+78h]; Src
0x180004ea4  call    memcpy_0
0x180004ea9  mov     ebp, [r15+74h]
0x180004ead  add     rbp, 7
0x180004eb1  and     rbp, 0FFFFFFFFFFFFFFF8h
0x180004eb5  add     rbp, [rsp+68h+arg_28]
0x180004ebd  jmp     short loc_180004EC2
0x180004ebf  mov     rbp, r9
0x180004ec2  inc     r14d
0x180004ec5  cmp     r14d, [rdi+5Ch]
0x180004ec9  jb      loc_180004DE2
  ... truncated ...
```

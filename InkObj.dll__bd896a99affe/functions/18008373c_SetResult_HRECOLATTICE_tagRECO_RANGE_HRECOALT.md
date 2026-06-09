# SetResult(HRECOLATTICE__ *,tagRECO_RANGE *,HRECOALT__ *)

- ea: `0x18008373c`
- end: `0x1800839d6`
- name: `?SetResult@@YAJPEAUHRECOLATTICE__@@PEAUtagRECO_RANGE@@PEAUHRECOALT__@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(HRECOLATTICE, struct tagRECO_RANGE *, HRECOALT)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069700`
- `0x1800c9670`

## callees

- `0x180044ac6`
- `0x1800806c0`
- `0x18008373c`
- `0x180083d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008388d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008388d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008389e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008397a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008389e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008397a`

## pseudocode

```c
__int64 __fastcall SetResult(HRECOLATTICE a1, struct tagRECO_RANGE *a2, unsigned int *a3)
{
  __int64 result; // rax
  unsigned int v6; // r12d
  HRECOALT v7; // rsi
  unsigned int v8; // r11d
  __int64 i; // rdi
  _DWORD *v10; // rcx
  __int64 v11; // rbx
  unsigned int v12; // r10d
  int v13; // r15d
  __int64 v14; // r13
  SIZE_T v15; // rbx
  unsigned int v16; // ebx
  char *v17; // r15
  char *v18; // r13
  void *v19; // rcx
  __int64 v20; // [rsp+60h] [rbp+8h]
  HRECOALT hrcalt; // [rsp+68h] [rbp+10h] BYREF

  hrcalt = 0;
  if ( !a1 || !a3 )
    return 2147500035LL;
  result = GetBestAlternate(a1, &hrcalt);
  v6 = result;
  if ( (int)result < 0 )
    return result;
  v7 = hrcalt;
  if ( !hrcalt )
    return 2147746354LL;
  v8 = *((_DWORD *)hrcalt + 2);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v8 )
      goto LABEL_27;
    v10 = (_DWORD *)*((_QWORD *)a3 + 2);
    v11 = *((_QWORD *)hrcalt + 2);
    v20 = (unsigned int)i;
    if ( *(_DWORD *)(v11 + 4 * i) == *v10 )
      break;
  }
  v12 = a3[2];
  if ( v12 )
  {
    LODWORD(hrcalt) = i;
    v13 = *(_DWORD *)(*(_QWORD *)(56LL * (unsigned int)v10[v12 - 1] + *(_QWORD *)(**(_QWORD **)a3 + 8LL) + 48)
                    + 40LL * *(unsigned int *)(*((_QWORD *)a3 + 3) + 4LL * (v12 - 1))
                    + 16);
    v14 = **(_QWORD **)v7;
    if ( *(_DWORD *)v14 != v13 )
    {
      while ( (unsigned int)i < v8 )
      {
        if ( v13 == *(_DWORD *)(*(_QWORD *)(56LL * *(unsigned int *)(v11 + 4 * i) + *(_QWORD *)(v14 + 8) + 48)
                              + 40LL * *(unsigned int *)(*((_QWORD *)v7 + 3) + 4 * i)
                              + 16) )
          goto LABEL_13;
        i = (unsigned int)(i + 1);
      }
      v16 = -2147024809;
      goto LABEL_26;
    }
    i = v8 - 1;
LABEL_13:
    LODWORD(hrcalt) = v8 + v12 - i + (_DWORD)hrcalt - 1;
    v15 = 4LL * (unsigned int)hrcalt;
    if ( v15 > 0xFFFFFFFF )
    {
      v16 = -2147418113;
LABEL_26:
      DestroyAlternate(v7);
      return v16;
    }
    v17 = (char *)CoTaskMemAlloc((unsigned int)v15);
    if ( !v17 )
    {
LABEL_19:
      v16 = -2147024882;
      goto LABEL_26;
    }
    v18 = (char *)CoTaskMemAlloc(v15);
    if ( !v18 )
    {
      CoTaskMemFree(v17);
      goto LABEL_19;
    }
    memcpy_0(v18, *((const void **)v7 + 3), 4 * v20);
    memcpy_0(&v18[4 * v20], *((const void **)a3 + 3), 4LL * a3[2]);
    memcpy_0(
      &v18[4 * v20 + 4 * a3[2]],
      (const void *)(*((_QWORD *)v7 + 3) + 4LL + 4 * i),
      4LL * (unsigned int)(~(_DWORD)i + *((_DWORD *)v7 + 2)));
    memcpy_0(v17, *((const void **)v7 + 2), 4 * v20);
    memcpy_0(&v17[4 * v20], *((const void **)a3 + 2), 4LL * a3[2]);
    memcpy_0(
      &v17[4 * v20 + 4 * a3[2]],
      (const void *)(*((_QWORD *)v7 + 2) + 4LL + 4 * i),
      4LL * (unsigned int)(~(_DWORD)i + *((_DWORD *)v7 + 2)));
    v19 = (void *)*((_QWORD *)a1 + 8);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      CoTaskMemFree(*((LPVOID *)a1 + 9));
    }
    *((_DWORD *)a1 + 14) = (_DWORD)hrcalt;
    *((_QWORD *)a1 + 8) = v17;
    *((_QWORD *)a1 + 9) = v18;
    DestroyAlternate(v7);
    return v6;
  }
  else
  {
LABEL_27:
    DestroyAlternate(hrcalt);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18008373c  mov     rax, rsp
0x18008373f  mov     [rax+18h], rbx
0x180083743  mov     [rax+10h], rdx
0x180083747  push    rbp
0x180083748  push    rsi
0x180083749  push    rdi
0x18008374a  push    r12
0x18008374c  push    r13
0x18008374e  push    r14
0x180083750  push    r15
0x180083752  sub     rsp, 20h
0x180083756  mov     qword ptr [rax+10h], 0
0x18008375e  mov     r14, r8
0x180083761  mov     rbp, rcx
0x180083764  test    rcx, rcx
0x180083767  jz      loc_1800839BC
0x18008376d  test    r8, r8
0x180083770  jz      loc_1800839BC
0x180083776  lea     rdx, [rax+10h]; HRECOALT *
0x18008377a  call    ?GetBestAlternate@@YAJPEAUHRECOLATTICE__@@PEAPEAUHRECOALT__@@@Z; GetBestAlternate(HRECOLATTICE__ *,HRECOALT__ * *)
0x18008377f  mov     r12d, eax
0x180083782  test    eax, eax
0x180083784  js      loc_1800839C1
0x18008378a  mov     rsi, [rsp+58h+hrcalt]
0x18008378f  test    rsi, rsi
0x180083792  jnz     short loc_18008379E
0x180083794  mov     eax, 80040232h
0x180083799  jmp     loc_1800839C1
0x18008379e  mov     r11d, [rsi+8]
0x1800837a2  xor     edi, edi
0x1800837a4  cmp     edi, r11d
0x1800837a7  jnb     loc_1800839AD
0x1800837ad  mov     rcx, [r14+10h]
0x1800837b1  mov     rbx, [rsi+10h]
0x1800837b5  mov     edx, edi
0x1800837b7  mov     [rsp+58h+arg_0], rdx
0x1800837bc  mov     eax, [rcx]
0x1800837be  cmp     [rbx+rdi*4], eax
0x1800837c1  jz      short loc_1800837C7
0x1800837c3  inc     edi
0x1800837c5  jmp     short loc_1800837A4
0x1800837c7  mov     r10d, [r14+8]
0x1800837cb  test    r10d, r10d
0x1800837ce  jz      loc_1800839AD
0x1800837d4  lea     eax, [r10-1]
0x1800837d8  mov     dword ptr [rsp+58h+hrcalt], edi
0x1800837dc  mov     edx, eax
0x1800837de  mov     eax, [rcx+rax*4]
0x1800837e1  imul    r9, rax, 38h ; '8'
0x1800837e5  mov     rax, [r14]
0x1800837e8  mov     rcx, [rax]
0x1800837eb  mov     rax, [r14+18h]
0x1800837ef  mov     r8, [rcx+8]
0x1800837f3  mov     ecx, [rax+rdx*4]
0x1800837f6  mov     rax, [r9+r8+30h]
0x1800837fb  lea     rdx, [rcx+rcx*4]
0x1800837ff  mov     r15d, [rax+rdx*8+10h]
0x180083804  mov     rax, [rsi]
0x180083807  mov     r13, [rax]
0x18008380a  cmp     [r13+0], r15d
0x18008380e  jnz     short loc_180083841
0x180083810  lea     edi, [r11-1]
0x180083814  mov     eax, dword ptr [rsp+58h+hrcalt]
0x180083818  sub     r10d, edi
0x18008381b  dec     eax
0x18008381d  add     r10d, r11d
0x180083820  add     eax, r10d
0x180083823  mov     ebx, eax
0x180083825  mov     dword ptr [rsp+58h+hrcalt], eax
0x180083829  mov     eax, 0FFFFFFFFh
0x18008382e  shl     rbx, 2
0x180083832  cmp     rbx, rax
0x180083835  jbe     short loc_180083870
0x180083837  mov     ebx, 8000FFFFh
0x18008383c  jmp     loc_1800839A1
0x180083841  cmp     edi, r11d
0x180083844  jnb     loc_18008399C
0x18008384a  mov     eax, [rbx+rdi*4]
0x18008384d  mov     r8, [r13+8]
0x180083851  imul    r9, rax, 38h ; '8'
0x180083855  mov     rax, [rsi+18h]
0x180083859  mov     ecx, [rax+rdi*4]
0x18008385c  mov     rax, [r9+r8+30h]
0x180083861  lea     rdx, [rcx+rcx*4]
0x180083865  cmp     r15d, [rax+rdx*8+10h]
0x18008386a  jz      short loc_180083814
0x18008386c  inc     edi
0x18008386e  jmp     short loc_180083841
0x180083870  mov     ecx, ebx; cb
0x180083872  call    cs:__imp_CoTaskMemAlloc
0x180083878  mov     r15, rax
0x18008387b  test    rax, rax
0x18008387e  jnz     short loc_18008388A
0x180083880  mov     ebx, 8007000Eh
0x180083885  jmp     loc_1800839A1
0x18008388a  mov     rcx, rbx; cb
0x18008388d  call    cs:__imp_CoTaskMemAlloc
0x180083893  mov     r13, rax
0x180083896  test    rax, rax
0x180083899  jnz     short loc_1800838A6
0x18008389b  mov     rcx, r15; pv
0x18008389e  call    cs:__imp_CoTaskMemFree
0x1800838a4  jmp     short loc_180083880
0x1800838a6  mov     rax, [rsp+58h+arg_0]
0x1800838ab  mov     rcx, r13; void *
0x1800838ae  mov     rdx, [rsi+18h]; Src
0x1800838b2  lea     rbx, ds:0[rax*4]
0x1800838ba  mov     r8, rbx; Size
0x1800838bd  call    memcpy_0
0x1800838c2  mov     r8d, [r14+8]
0x1800838c6  lea     rcx, [rbx+r13]; void *
0x1800838ca  mov     rdx, [r14+18h]; Src
0x1800838ce  shl     r8, 2; Size
0x1800838d2  call    memcpy_0
0x1800838d7  mov     r8d, [rsi+8]
0x1800838db  mov     ebx, edi
0x1800838dd  mov     eax, [r14+8]
0x1800838e1  not     ebx
0x1800838e3  add     rax, [rsp+58h+arg_0]
0x1800838e8  add     r8d, ebx
0x1800838eb  mov     rdx, [rsi+18h]
0x1800838ef  add     rdx, 4
0x1800838f3  shl     r8, 2; Size
0x1800838f7  lea     rcx, ds:0[rax*4]
0x1800838ff  add     rcx, r13; void *
0x180083902  lea     rdx, [rdx+rdi*4]; Src
0x180083906  call    memcpy_0
0x18008390b  mov     rax, [rsp+58h+arg_0]
0x180083910  mov     rcx, r15; void *
0x180083913  mov     rdx, [rsi+10h]; Src
0x180083917  lea     r8, ds:0[rax*4]; Size
0x18008391f  call    memcpy_0
0x180083924  mov     rax, [rsp+58h+arg_0]
0x180083929  mov     r8d, [r14+8]
0x18008392d  mov     rdx, [r14+10h]; Src
0x180083931  shl     r8, 2; Size
0x180083935  lea     rcx, [r15+rax*4]; void *
0x180083939  call    memcpy_0
0x18008393e  mov     r8d, [rsi+8]
0x180083942  mov     rdx, [rsi+10h]
0x180083946  add     r8d, ebx
0x180083949  mov     eax, [r14+8]
0x18008394d  add     rdx, 4
0x180083951  add     rax, [rsp+58h+arg_0]
0x180083956  shl     r8, 2; Size
0x18008395a  lea     rdx, [rdx+rdi*4]; Src
0x18008395e  lea     rcx, [r15+rax*4]; void *
0x180083962  call    memcpy_0
0x180083967  mov     rcx, [rbp+40h]; pv
0x18008396b  test    rcx, rcx
0x18008396e  jz      short loc_180083980
0x180083970  call    cs:__imp_CoTaskMemFree
0x180083976  mov     rcx, [rbp+48h]; pv
0x18008397a  call    cs:__imp_CoTaskMemFree
0x180083980  mov     eax, dword ptr [rsp+58h+hrcalt]
0x180083984  mov     rcx, rsi; hrcalt
0x180083987  mov     [rbp+38h], eax
0x18008398a  mov     [rbp+40h], r15
0x18008398e  mov     [rbp+48h], r13
0x180083992  call    DestroyAlternate
0x180083997  mov     eax, r12d
0x18008399a  jmp     short loc_1800839C1
0x18008399c  mov     ebx, 80070057h
0x1800839a1  mov     rcx, rsi; hrcalt
0x1800839a4  call    DestroyAlternate
0x1800839a9  mov     eax, ebx
0x1800839ab  jmp     short loc_1800839C1
0x1800839ad  mov     rcx, rsi; hrcalt
0x1800839b0  call    DestroyAlternate
0x1800839b5  mov     eax, 80070057h
0x1800839ba  jmp     short loc_1800839C1
0x1800839bc  mov     eax, 80004003h
0x1800839c1  mov     rbx, [rsp+58h+arg_10]
0x1800839c6  add     rsp, 20h
0x1800839ca  pop     r15
0x1800839cc  pop     r14
0x1800839ce  pop     r13
0x1800839d0  pop     r12
0x1800839d2  pop     rdi
0x1800839d3  pop     rsi
0x1800839d4  pop     rbp
0x1800839d5  retn
```

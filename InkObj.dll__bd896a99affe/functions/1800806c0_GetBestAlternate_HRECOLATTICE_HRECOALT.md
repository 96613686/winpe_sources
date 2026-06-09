# GetBestAlternate(HRECOLATTICE__ *,HRECOALT__ * *)

- ea: `0x1800806c0`
- end: `0x1800807ee`
- name: `?GetBestAlternate@@YAJPEAUHRECOLATTICE__@@PEAPEAUHRECOALT__@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(HRECOLATTICE, HRECOALT *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069390`
- `0x1800803a0`
- `0x1800832d8`
- `0x18008373c`
- `0x1800c9b90`
- `0x1800c9cf0`

## callees

- `0x180044ac6`
- `0x1800806c0`
- `0x180083b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008075f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008075f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080780`

## pseudocode

```c
__int64 __fastcall GetBestAlternate(HRECOLATTICE a1, HRECOALT *a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  HRECOALT v6; // rax
  HRECOALT v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // edi
  LPVOID v10; // rax
  LPVOID v11; // rax
  void *v12; // rcx
  const void *v13; // rdx
  size_t v14; // r8
  const void *v15; // rdx
  unsigned int v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = 0;
  if ( !a2 || !a1 )
    return 2147500035LL;
  result = l_GetBestResultString(a1, &v16, 0);
  v5 = result;
  if ( (int)result < 0 )
    return result;
  v6 = (HRECOALT)CoTaskMemAlloc(0x28u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_QWORD *)v6 = a1;
  if ( *((_QWORD *)a1 + 8) )
    v8 = *((unsigned int *)a1 + 14);
  else
    v8 = *(unsigned int *)(*(_QWORD *)a1 + 32LL);
  *((_DWORD *)v6 + 2) = v8;
  if ( (unsigned int)v8 >= 0x1FFFFFFF )
  {
    v9 = -2147418113;
LABEL_15:
    CoTaskMemFree(v7);
    return v9;
  }
  v10 = CoTaskMemAlloc(4 * v8);
  *((_QWORD *)v7 + 2) = v10;
  if ( !v10 )
  {
LABEL_14:
    v9 = -2147024882;
    goto LABEL_15;
  }
  v11 = CoTaskMemAlloc(4LL * *((unsigned int *)v7 + 2));
  v12 = (void *)*((_QWORD *)v7 + 2);
  *((_QWORD *)v7 + 3) = v11;
  if ( !v11 )
  {
    CoTaskMemFree(v12);
    goto LABEL_14;
  }
  v13 = (const void *)*((_QWORD *)a1 + 8);
  v14 = 4LL * *((unsigned int *)v7 + 2);
  if ( v13 )
  {
    memcpy_0(v12, v13, v14);
    v15 = (const void *)*((_QWORD *)a1 + 9);
  }
  else
  {
    memcpy_0(v12, *(const void **)(*(_QWORD *)a1 + 40LL), v14);
    v15 = *(const void **)(*(_QWORD *)a1 + 48LL);
  }
  memcpy_0(*((void **)v7 + 3), v15, 4LL * *((unsigned int *)v7 + 2));
  *((_DWORD *)v7 + 9) = v16;
  result = v5;
  *((_DWORD *)v7 + 8) = 0;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x1800806c0  push    rbx
0x1800806c2  push    rsi
0x1800806c3  push    rdi
0x1800806c4  push    r14
0x1800806c6  sub     rsp, 28h
0x1800806ca  mov     [rsp+48h+arg_0], 0
0x1800806d2  mov     r14, rdx
0x1800806d5  mov     rdi, rcx
0x1800806d8  test    rdx, rdx
0x1800806db  jz      loc_1800807DF
0x1800806e1  test    rcx, rcx
0x1800806e4  jz      loc_1800807DF
0x1800806ea  xor     r8d, r8d; unsigned __int16 *
0x1800806ed  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x1800806f2  call    ?l_GetBestResultString@@YAJPEAUHRECOLATTICE__@@PEAKPEAG@Z; l_GetBestResultString(HRECOLATTICE__ *,ulong *,ushort *)
0x1800806f7  mov     esi, eax
0x1800806f9  test    eax, eax
0x1800806fb  js      loc_1800807E4
0x180080701  mov     ecx, 28h ; '('; cb
0x180080706  call    cs:__imp_CoTaskMemAlloc
0x18008070c  mov     rbx, rax
0x18008070f  test    rax, rax
0x180080712  jnz     short loc_18008071E
0x180080714  mov     eax, 8007000Eh
0x180080719  jmp     loc_1800807E4
0x18008071e  mov     [rax], rdi
0x180080721  cmp     qword ptr [rdi+40h], 0
0x180080726  jnz     short loc_180080730
0x180080728  mov     rax, [rdi]
0x18008072b  mov     ecx, [rax+20h]
0x18008072e  jmp     short loc_180080733
0x180080730  mov     ecx, [rdi+38h]
0x180080733  mov     [rbx+8], ecx
0x180080736  cmp     ecx, 1FFFFFFFh
0x18008073c  jb      short loc_180080745
0x18008073e  mov     edi, 8000FFFFh
0x180080743  jmp     short loc_18008077D
0x180080745  shl     rcx, 2; cb
0x180080749  call    cs:__imp_CoTaskMemAlloc
0x18008074f  mov     [rbx+10h], rax
0x180080753  test    rax, rax
0x180080756  jz      short loc_180080778
0x180080758  mov     ecx, [rbx+8]
0x18008075b  shl     rcx, 2; cb
0x18008075f  call    cs:__imp_CoTaskMemAlloc
0x180080765  mov     rcx, [rbx+10h]; void *
0x180080769  mov     [rbx+18h], rax
0x18008076d  test    rax, rax
0x180080770  jnz     short loc_18008078A
0x180080772  call    cs:__imp_CoTaskMemFree
0x180080778  mov     edi, 8007000Eh
0x18008077d  mov     rcx, rbx; pv
0x180080780  call    cs:__imp_CoTaskMemFree
0x180080786  mov     eax, edi
0x180080788  jmp     short loc_1800807E4
0x18008078a  mov     r8d, [rbx+8]
0x18008078e  mov     rdx, [rdi+40h]; Src
0x180080792  shl     r8, 2; Size
0x180080796  test    rdx, rdx
0x180080799  jnz     short loc_1800807B0
0x18008079b  mov     rdx, [rdi]
0x18008079e  mov     rdx, [rdx+28h]; Src
0x1800807a2  call    memcpy_0
0x1800807a7  mov     rdx, [rdi]
0x1800807aa  mov     rdx, [rdx+30h]
0x1800807ae  jmp     short loc_1800807B9
0x1800807b0  call    memcpy_0
0x1800807b5  mov     rdx, [rdi+48h]; Src
0x1800807b9  mov     r8d, [rbx+8]
0x1800807bd  mov     rcx, [rbx+18h]; void *
0x1800807c1  shl     r8, 2; Size
0x1800807c5  call    memcpy_0
0x1800807ca  mov     eax, [rsp+48h+arg_0]
0x1800807ce  mov     [rbx+24h], eax
0x1800807d1  mov     eax, esi
0x1800807d3  mov     dword ptr [rbx+20h], 0
0x1800807da  mov     [r14], rbx
0x1800807dd  jmp     short loc_1800807E4
0x1800807df  mov     eax, 80004003h
0x1800807e4  add     rsp, 28h
0x1800807e8  pop     r14
0x1800807ea  pop     rdi
0x1800807eb  pop     rsi
0x1800807ec  pop     rbx
0x1800807ed  retn
```

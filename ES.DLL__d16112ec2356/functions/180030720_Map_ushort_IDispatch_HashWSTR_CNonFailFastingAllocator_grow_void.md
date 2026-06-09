# Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)

- ea: `0x180030720`
- end: `0x1800307dd`
- name: `?grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006220`

## callees

- `0x180018190`
- `0x180030720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030768`

## pseudocode

```c
__int64 __fastcall Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int v3; // edx
  __int64 v4; // rbx
  LPVOID v5; // rsi
  int v7; // eax
  __int64 v8; // rdx
  int *i; // rbx
  int **v10; // rcx
  int **v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = *(_DWORD *)(a1 + 12);
  if ( v3 >= 0x11 )
  {
    do
      v2 = (unsigned int)(v2 + 1);
    while ( v3 >= *((_DWORD *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime
                  + v2) );
  }
  v4 = (unsigned int)v2;
  v5 = CoTaskMemAlloc(
         8LL
       * *((unsigned int *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v2));
  if ( !v5 )
    return 2147942414LL;
  CoTaskMemFree(*(LPVOID *)a1);
  v7 = *((_DWORD *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v4);
  v8 = 0;
  *(_QWORD *)a1 = v5;
  for ( *(_DWORD *)(a1 + 8) = v7; (unsigned int)v8 < *(_DWORD *)(a1 + 8); v8 = (unsigned int)(v8 + 1) )
    *(_QWORD *)(*(_QWORD *)a1 + 8 * v8) = 0;
  for ( i = *(int **)(a1 + 24); i != (int *)(a1 + 24); i = *(int **)i )
  {
    if ( i[6] < 0 )
    {
      v11 = 0;
      Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(a1, i + 8, &v11);
      v10 = v11;
      *((_QWORD *)i + 2) = *v11;
      *v10 = i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180030720  push    rbx
0x180030722  push    rsi
0x180030723  push    rdi
0x180030724  push    r14
0x180030726  sub     rsp, 28h
0x18003072a  mov     rdi, rcx
0x18003072d  lea     r14, ?rgprime@?1??grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ@4QBIB; uint const near * const `Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)'::`2'::rgprime
0x180030734  xor     ecx, ecx
0x180030736  mov     edx, [rdi+0Ch]
0x180030739  cmp     edx, 11h
0x18003073c  jb      short loc_180030746
0x18003073e  inc     ecx
0x180030740  cmp     edx, [r14+rcx*4]
0x180030744  jnb     short loc_18003073E
0x180030746  mov     ebx, ecx
0x180030748  mov     ecx, [r14+rcx*4]
0x18003074c  shl     rcx, 3; cb
0x180030750  call    cs:__imp_CoTaskMemAlloc
0x180030756  mov     rsi, rax
0x180030759  test    rax, rax
0x18003075c  jnz     short loc_180030765
0x18003075e  mov     eax, 8007000Eh
0x180030763  jmp     short loc_1800307D3
0x180030765  mov     rcx, [rdi]; pv
0x180030768  call    cs:__imp_CoTaskMemFree
0x18003076e  mov     eax, [r14+rbx*4]
0x180030772  xor     edx, edx
0x180030774  mov     [rdi], rsi
0x180030777  mov     [rdi+8], eax
0x18003077a  test    eax, eax
0x18003077c  jz      short loc_180030790
0x18003077e  mov     rax, [rdi]
0x180030781  mov     qword ptr [rax+rdx*8], 0
0x180030789  inc     edx
0x18003078b  cmp     edx, [rdi+8]
0x18003078e  jb      short loc_18003077E
0x180030790  lea     rsi, [rdi+18h]
0x180030794  mov     rbx, [rsi]
0x180030797  jmp     short loc_1800307CC
0x180030799  mov     eax, [rbx+18h]
0x18003079c  test    eax, eax
0x18003079e  jns     short loc_1800307C9
0x1800307a0  lea     rdx, [rbx+20h]
0x1800307a4  mov     [rsp+48h+arg_0], 0
0x1800307ad  lea     r8, [rsp+48h+arg_0]
0x1800307b2  mov     rcx, rdi
0x1800307b5  call    ?find@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEBAHAEBQEAGPEAPEAPEAVAssoc@1@@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::find(ushort * const &,Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc * * *)
0x1800307ba  mov     rcx, [rsp+48h+arg_0]
0x1800307bf  mov     rax, [rcx]
0x1800307c2  mov     [rbx+10h], rax
0x1800307c6  mov     [rcx], rbx
0x1800307c9  mov     rbx, [rbx]
0x1800307cc  cmp     rbx, rsi
0x1800307cf  jnz     short loc_180030799
0x1800307d1  xor     eax, eax
0x1800307d3  add     rsp, 28h
0x1800307d7  pop     r14
0x1800307d9  pop     rdi
0x1800307da  pop     rsi
0x1800307db  pop     rbx
0x1800307dc  retn
```

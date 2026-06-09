# Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::grow(void)

- ea: `0x1800341e0`
- end: `0x18003429d`
- name: `?grow@?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@AEAAJXZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800342a4`

## callees

- `0x1800340f8`
- `0x1800341e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034228`

## pseudocode

```c
__int64 __fastcall Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::grow(
        __int64 a1)
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
      Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::find(
        a1,
        i + 8,
        &v11);
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
0x1800341e0  push    rbx
0x1800341e2  push    rsi
0x1800341e3  push    rdi
0x1800341e4  push    r14
0x1800341e6  sub     rsp, 28h
0x1800341ea  mov     rdi, rcx
0x1800341ed  lea     r14, ?rgprime@?1??grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ@4QBIB; uint const near * const `Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)'::`2'::rgprime
0x1800341f4  xor     ecx, ecx
0x1800341f6  mov     edx, [rdi+0Ch]
0x1800341f9  cmp     edx, 11h
0x1800341fc  jb      short loc_180034206
0x1800341fe  inc     ecx
0x180034200  cmp     edx, [r14+rcx*4]
0x180034204  jnb     short loc_1800341FE
0x180034206  mov     ebx, ecx
0x180034208  mov     ecx, [r14+rcx*4]
0x18003420c  shl     rcx, 3; cb
0x180034210  call    cs:__imp_CoTaskMemAlloc
0x180034216  mov     rsi, rax
0x180034219  test    rax, rax
0x18003421c  jnz     short loc_180034225
0x18003421e  mov     eax, 8007000Eh
0x180034223  jmp     short loc_180034293
0x180034225  mov     rcx, [rdi]; pv
0x180034228  call    cs:__imp_CoTaskMemFree
0x18003422e  mov     eax, [r14+rbx*4]
0x180034232  xor     edx, edx
0x180034234  mov     [rdi], rsi
0x180034237  mov     [rdi+8], eax
0x18003423a  test    eax, eax
0x18003423c  jz      short loc_180034250
0x18003423e  mov     rax, [rdi]
0x180034241  mov     qword ptr [rax+rdx*8], 0
0x180034249  inc     edx
0x18003424b  cmp     edx, [rdi+8]
0x18003424e  jb      short loc_18003423E
0x180034250  lea     rsi, [rdi+18h]
0x180034254  mov     rbx, [rsi]
0x180034257  jmp     short loc_18003428C
0x180034259  mov     eax, [rbx+18h]
0x18003425c  test    eax, eax
0x18003425e  jns     short loc_180034289
0x180034260  lea     rdx, [rbx+20h]
0x180034264  mov     [rsp+48h+arg_0], 0
0x18003426d  lea     r8, [rsp+48h+arg_0]
0x180034272  mov     rcx, rdi
0x180034275  call    ?find@?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::find(ushort const * const &,Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::Assoc * * *)
0x18003427a  mov     rcx, [rsp+48h+arg_0]
0x18003427f  mov     rax, [rcx]
0x180034282  mov     [rbx+10h], rax
0x180034286  mov     [rcx], rbx
0x180034289  mov     rbx, [rbx]
0x18003428c  cmp     rbx, rsi
0x18003428f  jnz     short loc_180034259
0x180034291  xor     eax, eax
0x180034293  add     rsp, 28h
0x180034297  pop     r14
0x180034299  pop     rdi
0x18003429a  pop     rsi
0x18003429b  pop     rbx
0x18003429c  retn
```

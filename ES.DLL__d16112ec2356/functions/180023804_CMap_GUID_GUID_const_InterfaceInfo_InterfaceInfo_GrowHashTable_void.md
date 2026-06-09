# CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::GrowHashTable(void)

- ea: `0x180023804`
- end: `0x1800238ac`
- name: `?GrowHashTable@?$CMap@U_GUID@@AEBU1@PEAVInterfaceInfo@@PEAV2@@@IEAAXXZ`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b10`
- `0x1800079e8`

## callees

- `0x180023804`
- `0x1800238b4`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023897`

## pseudocode

```c
void __fastcall CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::GrowHashTable(__int64 a1)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 i; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rcx

  v2 = (unsigned int)CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::RoundUpToPrime(
                       a1,
                       (unsigned int)(2 * *(_DWORD *)(a1 + 8)));
  v3 = CoTaskMemAlloc(saturated_mul(v2, 8u));
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 8 * v2);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
    {
      while ( 1 )
      {
        v8 = *(_QWORD **)a1;
        if ( !*(_QWORD *)(*(_QWORD *)a1 + 8 * i) )
          break;
        v6 = v8[i];
        v8[i] = *(_QWORD *)v6;
        v7 = *(_DWORD *)(v6 + 12) % (unsigned int)v2;
        *(_DWORD *)(v6 + 8) = *(_DWORD *)(v6 + 12) % (unsigned int)v2;
        *(_QWORD *)v6 = v4[v7];
        v4[v7] = v6;
      }
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = v4;
    *(_DWORD *)(a1 + 8) = v2;
  }
}

```

## disassembly

```asm
0x180023804  push    rbx
0x180023806  push    rbp
0x180023807  push    rsi
0x180023808  push    rdi
0x180023809  sub     rsp, 28h
0x18002380d  mov     edx, [rcx+8]
0x180023810  mov     rbx, rcx
0x180023813  add     edx, edx
0x180023815  call    ?RoundUpToPrime@?$CMap@U_GUID@@AEBU1@PEAVInterfaceInfo@@PEAV2@@@IEBAII@Z; CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::RoundUpToPrime(uint)
0x18002381a  mov     esi, eax
0x18002381c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023823  mov     eax, 8
0x180023828  mul     rsi
0x18002382b  cmovb   rax, rcx
0x18002382f  mov     rcx, rax; cb
0x180023832  call    cs:__imp_CoTaskMemAlloc
0x180023838  mov     rdi, rax
0x18002383b  test    rax, rax
0x18002383e  jz      short loc_1800238A3
0x180023840  lea     r8, ds:0[rsi*8]; Size
0x180023848  xor     edx, edx; Val
0x18002384a  mov     rcx, rax; void *
0x18002384d  call    memset_0
0x180023852  xor     r9d, r9d
0x180023855  cmp     [rbx+8], r9d
0x180023859  jbe     short loc_180023894
0x18002385b  jmp     short loc_180023881
0x18002385d  mov     r8, [rcx+r9*8]
0x180023861  xor     edx, edx
0x180023863  mov     rax, [r8]
0x180023866  mov     [rcx+r9*8], rax
0x18002386a  mov     eax, [r8+0Ch]
0x18002386e  div     esi
0x180023870  mov     ecx, edx
0x180023872  mov     [r8+8], ecx
0x180023876  mov     rax, [rdi+rdx*8]
0x18002387a  mov     [r8], rax
0x18002387d  mov     [rdi+rdx*8], r8
0x180023881  mov     rcx, [rbx]
0x180023884  cmp     qword ptr [rcx+r9*8], 0
0x180023889  jnz     short loc_18002385D
0x18002388b  inc     r9d
0x18002388e  cmp     r9d, [rbx+8]
0x180023892  jb      short loc_180023881
0x180023894  mov     rcx, [rbx]; pv
0x180023897  call    cs:__imp_CoTaskMemFree
0x18002389d  mov     [rbx], rdi
0x1800238a0  mov     [rbx+8], esi
0x1800238a3  add     rsp, 28h
0x1800238a7  pop     rdi
0x1800238a8  pop     rsi
0x1800238a9  pop     rbp
0x1800238aa  pop     rbx
0x1800238ab  retn
```

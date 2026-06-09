# CMap<CString,ushort const *,RegRow *,RegRow *>::GrowHashTable(void)

- ea: `0x180009144`
- end: `0x1800091f1`
- name: `?GrowHashTable@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEAAXXZ`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b568`
- `0x18000b6e4`

## callees

- `0x180009144`
- `0x1800097ac`
- `0x180010210`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091dc`

## pseudocode

```c
void __fastcall CMap<CString,unsigned short const *,RegRow *,RegRow *>::GrowHashTable(__int64 a1)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 i; // r9
  _QWORD *v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rcx

  v2 = (unsigned int)CMap<CString,unsigned short const *,RegRow *,RegRow *>::RoundUpToPrime(
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
        v10 = *(_QWORD **)a1;
        if ( !*(_QWORD *)(*(_QWORD *)a1 + 8 * i) )
          break;
        v6 = (_QWORD *)v10[i];
        v10[i] = *v6;
        v7 = HashKey<unsigned short const *>(v6[2]);
        v8 = v7 % (unsigned int)v2;
        *(_DWORD *)(v9 + 8) = v7 % (unsigned int)v2;
        *(_QWORD *)v9 = v4[v8];
        v4[(unsigned int)v8] = v9;
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
0x180009144  push    rbx
0x180009146  push    rbp
0x180009147  push    rsi
0x180009148  push    rdi
0x180009149  sub     rsp, 28h
0x18000914d  mov     edx, [rcx+8]
0x180009150  mov     rbx, rcx
0x180009153  add     edx, edx
0x180009155  call    ?RoundUpToPrime@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEBAII@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RoundUpToPrime(uint)
0x18000915a  mov     esi, eax
0x18000915c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009163  mov     eax, 8
0x180009168  mul     rsi
0x18000916b  cmovb   rax, rcx
0x18000916f  mov     rcx, rax; cb
0x180009172  call    cs:__imp_CoTaskMemAlloc
0x180009178  mov     rdi, rax
0x18000917b  test    rax, rax
0x18000917e  jz      short loc_1800091E8
0x180009180  lea     r8, ds:0[rsi*8]; Size
0x180009188  xor     edx, edx; Val
0x18000918a  mov     rcx, rax; void *
0x18000918d  call    memset_0
0x180009192  xor     r9d, r9d
0x180009195  cmp     [rbx+8], r9d
0x180009199  ja      short loc_1800091C6
0x18000919b  jmp     short loc_1800091D9
0x18000919d  mov     r8, [rcx+r9*8]
0x1800091a1  mov     rax, [r8]
0x1800091a4  mov     [rcx+r9*8], rax
0x1800091a8  mov     rcx, [r8+10h]
0x1800091ac  call    ??$HashKey@PEBG@@YAIPEBG@Z; HashKey<ushort const *>(ushort const *)
0x1800091b1  xor     edx, edx
0x1800091b3  div     esi
0x1800091b5  mov     ecx, edx
0x1800091b7  mov     [r8+8], ecx
0x1800091bb  mov     rax, [rdi+rdx*8]
0x1800091bf  mov     [r8], rax
0x1800091c2  mov     [rdi+rdx*8], r8
0x1800091c6  mov     rcx, [rbx]
0x1800091c9  cmp     qword ptr [rcx+r9*8], 0
0x1800091ce  jnz     short loc_18000919D
0x1800091d0  inc     r9d
0x1800091d3  cmp     r9d, [rbx+8]
0x1800091d7  jb      short loc_1800091C6
0x1800091d9  mov     rcx, [rbx]; pv
0x1800091dc  call    cs:__imp_CoTaskMemFree
0x1800091e2  mov     [rbx], rdi
0x1800091e5  mov     [rbx+8], esi
0x1800091e8  add     rsp, 28h
0x1800091ec  pop     rdi
0x1800091ed  pop     rsi
0x1800091ee  pop     rbp
0x1800091ef  pop     rbx
0x1800091f0  retn
```

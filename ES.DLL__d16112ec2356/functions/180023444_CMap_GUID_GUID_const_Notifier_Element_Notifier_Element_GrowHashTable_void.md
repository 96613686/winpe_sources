# CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::GrowHashTable(void)

- ea: `0x180023444`
- end: `0x1800234ec`
- name: `?GrowHashTable@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@IEAAXXZ`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cd8c`

## callees

- `0x1800097ac`
- `0x180023444`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234d7`

## pseudocode

```c
void __fastcall CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::GrowHashTable(__int64 a1)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 i; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  _QWORD *v8; // rcx

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
0x180023444  push    rbx
0x180023446  push    rbp
0x180023447  push    rsi
0x180023448  push    rdi
0x180023449  sub     rsp, 28h
0x18002344d  mov     edx, [rcx+8]
0x180023450  mov     rbx, rcx
0x180023453  add     edx, edx
0x180023455  call    ?RoundUpToPrime@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEBAII@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RoundUpToPrime(uint)
0x18002345a  mov     esi, eax
0x18002345c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023463  mov     eax, 8
0x180023468  mul     rsi
0x18002346b  cmovb   rax, rcx
0x18002346f  mov     rcx, rax; cb
0x180023472  call    cs:__imp_CoTaskMemAlloc
0x180023478  mov     rdi, rax
0x18002347b  test    rax, rax
0x18002347e  jz      short loc_1800234E3
0x180023480  lea     r8, ds:0[rsi*8]; Size
0x180023488  xor     edx, edx; Val
0x18002348a  mov     rcx, rax; void *
0x18002348d  call    memset_0
0x180023492  xor     r9d, r9d
0x180023495  cmp     [rbx+8], r9d
0x180023499  ja      short loc_1800234C1
0x18002349b  jmp     short loc_1800234D4
0x18002349d  mov     r8, [rcx+r9*8]
0x1800234a1  xor     edx, edx
0x1800234a3  mov     rax, [r8]
0x1800234a6  mov     [rcx+r9*8], rax
0x1800234aa  mov     eax, [r8+0Ch]
0x1800234ae  div     esi
0x1800234b0  mov     ecx, edx
0x1800234b2  mov     [r8+8], ecx
0x1800234b6  mov     rax, [rdi+rdx*8]
0x1800234ba  mov     [r8], rax
0x1800234bd  mov     [rdi+rdx*8], r8
0x1800234c1  mov     rcx, [rbx]
0x1800234c4  cmp     qword ptr [rcx+r9*8], 0
0x1800234c9  jnz     short loc_18002349D
0x1800234cb  inc     r9d
0x1800234ce  cmp     r9d, [rbx+8]
0x1800234d2  jb      short loc_1800234C1
0x1800234d4  mov     rcx, [rbx]; pv
0x1800234d7  call    cs:__imp_CoTaskMemFree
0x1800234dd  mov     [rbx], rdi
0x1800234e0  mov     [rbx+8], esi
0x1800234e3  add     rsp, 28h
0x1800234e7  pop     rdi
0x1800234e8  pop     rsi
0x1800234e9  pop     rbp
0x1800234ea  pop     rbx
0x1800234eb  retn
```

# CCertChainList::RemoveDuplicateCerts(void)

- ea: `0x1800166e8`
- end: `0x1800167c1`
- name: `?RemoveDuplicateCerts@CCertChainList@@QEAAXXZ`
- size: `217`
- prototype: `void __fastcall(CCertChainList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000caa0`

## callees

- `0x1800166e8`
- `0x18001a336`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x180016792`
- `CRYPT32!CertFreeCertificateChain` at `0x180016792`

## pseudocode

```c
void __fastcall CCertChainList::RemoveDuplicateCerts(CCertChainList *this)
{
  __int64 v2; // r12
  unsigned int v3; // ebx
  __int64 v4; // r14
  size_t v5; // r15
  __int64 v6; // rsi
  unsigned int v7; // ebp
  unsigned int v8; // esi
  __int64 v9; // rbx

  if ( *((_DWORD *)this + 2) > 1u )
  {
    v2 = *((_QWORD *)this + 2);
    v3 = 1;
    v4 = *(_QWORD *)(*(_QWORD *)(**(_QWORD **)(**(_QWORD **)(*(_QWORD *)v2 + 16LL) + 16LL) + 8LL) + 24LL);
    v5 = *(unsigned int *)(v4 + 48);
    while ( 1 )
    {
      v6 = *(_QWORD *)(*(_QWORD *)(**(_QWORD **)(**(_QWORD **)(*(_QWORD *)(v2 + 8LL * v3) + 16LL) + 16LL) + 8LL) + 24LL);
      if ( (_DWORD)v5 != *(_DWORD *)(v6 + 48) )
        break;
      v7 = *(_DWORD *)(v4 + 80);
      if ( v7 != *(_DWORD *)(v6 + 80)
        || memcmp_0(*(const void **)(v4 + 56), *(const void **)(v6 + 56), v5)
        || memcmp_0(*(const void **)(v4 + 88), *(const void **)(v6 + 88), v7) )
      {
        break;
      }
      if ( ++v3 >= *((_DWORD *)this + 2) )
      {
        v8 = 1;
        do
        {
          v9 = v8;
          CertFreeCertificateChain(*(PCCERT_CHAIN_CONTEXT *)(*((_QWORD *)this + 2) + 8LL * v8++));
          *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v9) = 0;
        }
        while ( v8 < *((_DWORD *)this + 2) );
        *((_DWORD *)this + 2) = 1;
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x1800166e8  push    rbx
0x1800166ea  push    rbp
0x1800166eb  push    rsi
0x1800166ec  push    rdi
0x1800166ed  push    r12
0x1800166ef  push    r14
0x1800166f1  push    r15
0x1800166f3  sub     rsp, 20h
0x1800166f7  cmp     dword ptr [rcx+8], 1
0x1800166fb  mov     rdi, rcx
0x1800166fe  jbe     loc_1800167B2
0x180016704  mov     r12, [rcx+10h]
0x180016708  mov     ebx, 1
0x18001670d  mov     rax, [r12]
0x180016711  mov     rcx, [rax+10h]
0x180016715  mov     rax, [rcx]
0x180016718  mov     rcx, [rax+10h]
0x18001671c  mov     rax, [rcx]
0x18001671f  mov     rcx, [rax+8]
0x180016723  mov     r14, [rcx+18h]
0x180016727  mov     r15d, [r14+30h]
0x18001672b  mov     eax, ebx
0x18001672d  mov     rcx, [r12+rax*8]
0x180016731  mov     rax, [rcx+10h]
0x180016735  mov     rcx, [rax]
0x180016738  mov     rax, [rcx+10h]
0x18001673c  mov     rcx, [rax]
0x18001673f  mov     rax, [rcx+8]
0x180016743  mov     rsi, [rax+18h]
0x180016747  cmp     r15d, [rsi+30h]
0x18001674b  jnz     short loc_1800167B2
0x18001674d  mov     ebp, [r14+50h]
0x180016751  cmp     ebp, [rsi+50h]
0x180016754  jnz     short loc_1800167B2
0x180016756  mov     rdx, [rsi+38h]; Buf2
0x18001675a  mov     r8, r15; Size
0x18001675d  mov     rcx, [r14+38h]; Buf1
0x180016761  call    memcmp_0
0x180016766  test    eax, eax
0x180016768  jnz     short loc_1800167B2
0x18001676a  mov     rdx, [rsi+58h]; Buf2
0x18001676e  mov     r8d, ebp; Size
0x180016771  mov     rcx, [r14+58h]; Buf1
0x180016775  call    memcmp_0
0x18001677a  test    eax, eax
0x18001677c  jnz     short loc_1800167B2
0x18001677e  inc     ebx
0x180016780  cmp     ebx, [rdi+8]
0x180016783  jb      short loc_18001672B
0x180016785  lea     esi, [rax+1]
0x180016788  mov     rcx, [rdi+10h]
0x18001678c  mov     ebx, esi
0x18001678e  mov     rcx, [rcx+rbx*8]; pChainContext
0x180016792  call    cs:__imp_CertFreeCertificateChain
0x180016798  mov     rax, [rdi+10h]
0x18001679c  inc     esi
0x18001679e  mov     qword ptr [rax+rbx*8], 0
0x1800167a6  cmp     esi, [rdi+8]
0x1800167a9  jb      short loc_180016788
0x1800167ab  mov     dword ptr [rdi+8], 1
0x1800167b2  add     rsp, 20h
0x1800167b6  pop     r15
0x1800167b8  pop     r14
0x1800167ba  pop     r12
0x1800167bc  pop     rdi
0x1800167bd  pop     rsi
0x1800167be  pop     rbp
0x1800167bf  pop     rbx
0x1800167c0  retn
```

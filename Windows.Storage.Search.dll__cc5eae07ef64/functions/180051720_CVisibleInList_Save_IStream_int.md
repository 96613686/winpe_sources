# CVisibleInList::Save(IStream *,int)

- ea: `0x180051720`
- end: `0x1800517f0`
- name: `?Save@CVisibleInList@@UEAAJPEAUIStream@@H@Z`
- size: `208`
- prototype: `int(CVisibleInList *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180047ae0`
- `0x180051720`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x180051747`
- `SHCORE!IStream_Write` at `0x180051775`
- `SHCORE!IStream_Write` at `0x180051747`
- `SHCORE!IStream_Write` at `0x180051775`
- `SHCORE!IStream_WriteStr` at `0x1800517c3`
- `SHCORE!IStream_WriteStr` at `0x1800517c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517d0`

## pseudocode

```c
__int64 __fastcall CVisibleInList::Save(CVisibleInList *this, struct IStream *a2)
{
  HRESULT i; // ebx
  _DWORD *v5; // rax
  unsigned int v6; // ecx
  unsigned int v7; // edi
  struct _DPA *v8; // rcx
  PVOID Ptr; // rax
  PCWSTR psz[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int pv; // [rsp+78h] [rbp+20h] BYREF

  pv = -2147483647;
  i = IStream_Write(a2, &pv, 4u);
  if ( i >= 0 )
  {
    v5 = (_DWORD *)*((_QWORD *)this + 2);
    v6 = v5 ? *v5 : 0;
    pv = v6;
    v7 = 0;
    for ( i = IStream_Write(a2, &pv, 4u); v7 < pv; ++v7 )
    {
      if ( i < 0 )
        break;
      v8 = (struct _DPA *)*((_QWORD *)this + 2);
      psz[0] = 0;
      Ptr = g_pfn_DPA_GetPtr(v8, v7);
      i = (*(__int64 (__fastcall **)(PVOID, PCWSTR *))(*(_QWORD *)Ptr + 24LL))(Ptr, psz);
      if ( i >= 0 )
      {
        i = IStream_WriteStr(a2, psz[0]);
        CoTaskMemFree((LPVOID)psz[0]);
      }
    }
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180051720  push    rbx
0x180051722  push    rbp
0x180051723  push    rsi
0x180051724  push    rdi
0x180051725  sub     rsp, 38h
0x180051729  mov     rsi, rdx
0x18005172c  mov     [rsp+58h+pv], 80000001h
0x180051734  mov     rbp, rcx
0x180051737  lea     rdx, [rsp+58h+pv]; pv
0x18005173c  mov     edi, 4
0x180051741  mov     rcx, rsi; pstm
0x180051744  mov     r8d, edi; cb
0x180051747  call    cs:__imp_IStream_Write
0x18005174d  mov     ebx, eax
0x18005174f  test    eax, eax
0x180051751  js      loc_1800517DE
0x180051757  mov     rax, [rbp+10h]
0x18005175b  test    rax, rax
0x18005175e  jz      loc_1800517E9
0x180051764  mov     ecx, [rax]
0x180051766  mov     [rsp+58h+pv], ecx
0x18005176a  lea     rdx, [rsp+58h+pv]; pv
0x18005176f  mov     rcx, rsi; pstm
0x180051772  mov     r8d, edi; cb
0x180051775  call    cs:__imp_IStream_Write
0x18005177b  xor     edi, edi
0x18005177d  mov     ebx, eax
0x18005177f  cmp     [rsp+58h+pv], edi
0x180051783  jbe     short loc_1800517DE
0x180051785  test    ebx, ebx
0x180051787  js      short loc_1800517DE
0x180051789  mov     rcx, [rbp+10h]; hdpa
0x18005178d  mov     edx, edi; i
0x18005178f  mov     [rsp+58h+psz], 0
0x180051798  call    cs:g_pfn_DPA_GetPtr
0x18005179e  mov     r8, rax
0x1800517a1  lea     rdx, [rsp+58h+psz]
0x1800517a6  mov     rcx, [rax]
0x1800517a9  mov     rax, [rcx+18h]
0x1800517ad  mov     rcx, r8
0x1800517b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517b5  mov     ebx, eax
0x1800517b7  test    eax, eax
0x1800517b9  js      short loc_1800517D6
0x1800517bb  mov     rdx, [rsp+58h+psz]; psz
0x1800517c0  mov     rcx, rsi; pstm
0x1800517c3  call    cs:__imp_IStream_WriteStr
0x1800517c9  mov     rcx, [rsp+58h+psz]; pv
0x1800517ce  mov     ebx, eax
0x1800517d0  call    cs:__imp_CoTaskMemFree
0x1800517d6  inc     edi
0x1800517d8  cmp     edi, [rsp+58h+pv]
0x1800517dc  jb      short loc_180051785
0x1800517de  mov     eax, ebx
0x1800517e0  add     rsp, 38h
0x1800517e4  pop     rdi
0x1800517e5  pop     rsi
0x1800517e6  pop     rbp
0x1800517e7  pop     rbx
0x1800517e8  retn
0x1800517e9  xor     ecx, ecx
0x1800517eb  jmp     loc_180051766
```

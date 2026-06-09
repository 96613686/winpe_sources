# CPSFactory::CreateProxy(IUnknown *,_GUID const &,IRpcProxyBuffer * *,void * *)

- ea: `0x18000ece0`
- end: `0x18000ee6b`
- name: `?CreateProxy@CPSFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAUIRpcProxyBuffer@@PEAPEAX@Z`
- size: `395`
- prototype: `int(CPSFactory *__hidden this, struct IUnknown *, const struct _GUID *, struct IRpcProxyBuffer **, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001008`
- `0x18000ece0`
- `0x18001734d`
- `0x180018010`

## import_xrefs

- `ole32!OleInitialize` at `0x18000ed82`
- `ole32!OleInitialize` at `0x18000ed82`

## pseudocode

```c
__int64 __fastcall CPSFactory::CreateProxy(
        CPSFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IRpcProxyBuffer **a4,
        void **a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rax
  bool v12; // cf
  struct IRpcProxyBuffer *v13; // rbx
  unsigned int v14; // edi
  _QWORD *v15; // rax
  _QWORD *v16; // rcx

  *a4 = 0;
  *a5 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !memcmp_0(a3, &IID_IAVIStream, 0x10u) )
  {
    v9 = operator new(0x100u);
    v10 = v9;
    if ( v9 )
    {
      ++uUseCount;
      *v9 = &CPrxAVIStream::`vftable';
      v9[2] = v9;
      v9[1] = &CPrxAVIStream::CProxyImpl::`vftable';
      *((_DWORD *)v9 + 6) = 1;
      v9[4] = a2;
      v9[5] = 0;
      *((_DWORD *)v9 + 12) = 0;
      if ( OleInitialize(0) >= 0 )
        _InterlockedIncrement(&glOleRefCount);
    }
    else
    {
      v10 = 0;
    }
    v11 = (unsigned __int64)(v10 + 1);
    v12 = v10 != 0;
  }
  else
  {
    if ( memcmp_0(a3, &IID_IAVIFile, 0x10u) )
      return 2147500034LL;
    v15 = operator new(0xE0u);
    v16 = v15;
    if ( v15 )
    {
      ++uUseCount;
      *v15 = &CPrxAVIFile::`vftable';
      v15[1] = &CPrxAVIFile::CProxyImpl::`vftable';
      v15[2] = v15;
      *((_DWORD *)v15 + 6) = 1;
      v15[4] = a2;
      v15[5] = 0;
      *((_DWORD *)v15 + 15) = 0;
    }
    else
    {
      v16 = 0;
    }
    v11 = (unsigned __int64)(v16 + 1);
    v12 = v16 != 0;
  }
  v13 = (struct IRpcProxyBuffer *)(v11 & -(__int64)v12);
  if ( !v13 )
    return 2147942414LL;
  v14 = ((__int64 (__fastcall *)(struct IRpcProxyBuffer *, const struct _GUID *, void **))v13->lpVtbl->QueryInterface)(
          v13,
          a3,
          a5);
  if ( v14 )
    ((void (__fastcall *)(struct IRpcProxyBuffer *))v13->lpVtbl->Release)(v13);
  else
    *a4 = v13;
  return v14;
}

```

## disassembly

```asm
0x18000ece0  push    rbx
0x18000ece2  push    rbp
0x18000ece3  push    rsi
0x18000ece4  push    rdi
0x18000ece5  push    r14
0x18000ece7  sub     rsp, 20h
0x18000eceb  mov     r14, [rsp+48h+arg_20]
0x18000ecf0  mov     rsi, r9
0x18000ecf3  mov     qword ptr [r9], 0
0x18000ecfa  mov     rbp, r8
0x18000ecfd  mov     rdi, rdx
0x18000ed00  mov     qword ptr [r14], 0
0x18000ed07  test    rdx, rdx
0x18000ed0a  jnz     short loc_18000ED16
0x18000ed0c  mov     eax, 80070057h
0x18000ed11  jmp     loc_18000EE60
0x18000ed16  mov     ebx, 10h
0x18000ed1b  lea     rdx, IID_IAVIStream; Buf2
0x18000ed22  mov     r8d, ebx; Size
0x18000ed25  mov     rcx, rbp; Buf1
0x18000ed28  call    memcmp_0
0x18000ed2d  test    eax, eax
0x18000ed2f  jnz     loc_18000EDD0
0x18000ed35  mov     ecx, 100h; Size
0x18000ed3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed3f  mov     rbx, rax
0x18000ed42  test    rax, rax
0x18000ed45  jz      short loc_18000ED95
0x18000ed47  inc     cs:uUseCount
0x18000ed4d  lea     rax, ??_7CPrxAVIStream@@6B@; const CPrxAVIStream::`vftable'
0x18000ed54  mov     [rbx], rax
0x18000ed57  xor     ecx, ecx; pvReserved
0x18000ed59  mov     [rbx+10h], rbx
0x18000ed5d  lea     rax, ??_7CProxyImpl@CPrxAVIStream@@6B@; const CPrxAVIStream::CProxyImpl::`vftable'
0x18000ed64  mov     [rbx+8], rax
0x18000ed68  mov     dword ptr [rbx+18h], 1
0x18000ed6f  mov     [rbx+20h], rdi
0x18000ed73  mov     qword ptr [rbx+28h], 0
0x18000ed7b  mov     dword ptr [rbx+30h], 0
0x18000ed82  call    cs:__imp_OleInitialize
0x18000ed88  test    eax, eax
0x18000ed8a  js      short loc_18000ED97
0x18000ed8c  lock inc cs:glOleRefCount
0x18000ed93  jmp     short loc_18000ED97
0x18000ed95  xor     ebx, ebx
0x18000ed97  lea     rax, [rbx+8]
0x18000ed9b  neg     rbx
0x18000ed9e  sbb     rbx, rbx
0x18000eda1  and     rbx, rax
0x18000eda4  jz      loc_18000EE41
0x18000edaa  mov     rax, [rbx]
0x18000edad  mov     r8, r14
0x18000edb0  mov     rdx, rbp
0x18000edb3  mov     rcx, rbx
0x18000edb6  mov     rax, [rax]
0x18000edb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edbe  mov     edi, eax
0x18000edc0  test    eax, eax
0x18000edc2  jnz     loc_18000EE48
0x18000edc8  mov     [rsi], rbx
0x18000edcb  jmp     loc_18000EE57
0x18000edd0  mov     r8, rbx; Size
0x18000edd3  lea     rdx, IID_IAVIFile; Buf2
0x18000edda  mov     rcx, rbp; Buf1
0x18000eddd  call    memcmp_0
0x18000ede2  test    eax, eax
0x18000ede4  jnz     short loc_18000EE5B
0x18000ede6  mov     ecx, 0E0h; Size
0x18000edeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000edf0  mov     rcx, rax
0x18000edf3  test    rax, rax
0x18000edf6  jz      short loc_18000EE33
0x18000edf8  inc     cs:uUseCount
0x18000edfe  lea     rax, ??_7CPrxAVIFile@@6B@; const CPrxAVIFile::`vftable'
0x18000ee05  mov     [rcx], rax
0x18000ee08  lea     rax, ??_7CProxyImpl@CPrxAVIFile@@6B@; const CPrxAVIFile::CProxyImpl::`vftable'
0x18000ee0f  mov     [rcx+8], rax
0x18000ee13  mov     [rcx+10h], rcx
0x18000ee17  mov     dword ptr [rcx+18h], 1
0x18000ee1e  mov     [rcx+20h], rdi
0x18000ee22  mov     qword ptr [rcx+28h], 0
0x18000ee2a  mov     dword ptr [rcx+3Ch], 0
0x18000ee31  jmp     short loc_18000EE35
0x18000ee33  xor     ecx, ecx
0x18000ee35  lea     rax, [rcx+8]
0x18000ee39  neg     rcx
0x18000ee3c  jmp     loc_18000ED9E
0x18000ee41  mov     eax, 8007000Eh
0x18000ee46  jmp     short loc_18000EE60
0x18000ee48  mov     rax, [rbx]
0x18000ee4b  mov     rcx, rbx
0x18000ee4e  mov     rax, [rax+10h]
0x18000ee52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee57  mov     eax, edi
0x18000ee59  jmp     short loc_18000EE60
0x18000ee5b  mov     eax, 80004002h
0x18000ee60  add     rsp, 20h
0x18000ee64  pop     r14
0x18000ee66  pop     rdi
0x18000ee67  pop     rsi
0x18000ee68  pop     rbp
0x18000ee69  pop     rbx
0x18000ee6a  retn
```

# StructuredQuery1::TokenInformationComplete::CreateInstance(IStream *,bool,_GUID const &,void * *)

- ea: `0x18003e3ec`
- end: `0x18003e58f`
- name: `?CreateInstance@TokenInformationComplete@StructuredQuery1@@SAJPEAUIStream@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `419`
- prototype: `__int64 __fastcall(struct IStream *pstm, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d820`

## callees

- `0x18003e3ec`
- `0x18003e598`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e4be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e4be`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e458`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e475`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e497`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e4e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e51f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e458`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e475`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e497`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e4e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e51f`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::TokenInformationComplete::CreateInstance(
        struct IStream *pstm,
        char a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v7; // ebx
  StructuredQuery1::TokenInformationComplete *v8; // rax
  StructuredQuery1::TokenInformationComplete *v9; // rax
  StructuredQuery1::TokenInformationComplete *v10; // rdi
  void *v11; // rsi
  unsigned __int64 v12; // rax
  void *v13; // rax
  const struct _GUID *pv; // [rsp+60h] [rbp+18h] BYREF
  void *v16; // [rsp+68h] [rbp+20h] BYREF

  pv = a3;
  v16 = 0;
  v7 = -2147024882;
  v8 = (StructuredQuery1::TokenInformationComplete *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  pv = (const struct _GUID *)v8;
  if ( v8 )
  {
    v9 = StructuredQuery1::TokenInformationComplete::TokenInformationComplete(v8);
    v10 = v9;
    if ( v9 )
    {
      v7 = IStream_Read(pstm, (char *)v9 + 8, 4u);
      if ( v7 >= 0 )
      {
        v7 = IStream_Read(pstm, (char *)v10 + 12, 4u);
        if ( v7 >= 0 )
        {
          v11 = 0;
          LODWORD(pv) = 0;
          v7 = IStream_Read(pstm, &pv, 4u);
          if ( v7 >= 0 && (_DWORD)pv )
          {
            v12 = 2LL * (unsigned int)pv;
            if ( v12 > 0xFFFFFFFF )
            {
              v7 = -2147024362;
            }
            else
            {
              v13 = CoTaskMemAlloc((unsigned int)v12);
              v11 = v13;
              if ( v13 )
              {
                v7 = IStream_Read(pstm, v13, 2 * (_DWORD)pv - 2);
                if ( v7 < 0 )
                {
                  CoTaskMemFree(v11);
                  v11 = 0;
                }
                else
                {
                  *((_WORD *)v11 + (unsigned int)((_DWORD)pv - 1)) = 0;
                }
              }
              else
              {
                v7 = -2147024882;
              }
            }
          }
          *((_QWORD *)v10 + 2) = v11;
          if ( v7 >= 0 )
          {
            if ( !a2 || (*((_WORD *)v10 + 12) = 3, v7 = IStream_Read(pstm, (char *)v10 + 32, 4u), v7 >= 0) )
              v7 = (**(__int64 (__fastcall ***)(StructuredQuery1::TokenInformationComplete *, GUID *, void **))v10)(
                     v10,
                     &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                     &v16);
          }
        }
      }
      (*(void (__fastcall **)(StructuredQuery1::TokenInformationComplete *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  *a4 = v16;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e3ec  mov     [rsp+arg_0], rbx
0x18003e3f1  mov     [rsp+pv], r8
0x18003e3f6  push    rbp
0x18003e3f7  push    rsi
0x18003e3f8  push    rdi
0x18003e3f9  push    r14
0x18003e3fb  push    r15
0x18003e3fd  sub     rsp, 20h
0x18003e401  mov     r14b, dl
0x18003e404  mov     [rsp+48h+arg_18], 0
0x18003e40d  mov     rbp, rcx
0x18003e410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e417  mov     ecx, 38h ; '8'; unsigned __int64
0x18003e41c  mov     r15, r9
0x18003e41f  mov     ebx, 8007000Eh
0x18003e424  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e429  mov     [rsp+48h+pv], rax
0x18003e42e  test    rax, rax
0x18003e431  jz      loc_18003E556
0x18003e437  mov     rcx, rax; this
0x18003e43a  call    ??0TokenInformationComplete@StructuredQuery1@@AEAA@XZ; StructuredQuery1::TokenInformationComplete::TokenInformationComplete(void)
0x18003e43f  mov     rdi, rax
0x18003e442  test    rax, rax
0x18003e445  jz      loc_18003E556
0x18003e44b  lea     rdx, [rax+8]; pv
0x18003e44f  mov     r8d, 4; cb
0x18003e455  mov     rcx, rbp; pstm
0x18003e458  call    cs:__imp_IStream_Read
0x18003e45e  mov     ebx, eax
0x18003e460  test    eax, eax
0x18003e462  js      loc_18003E547
0x18003e468  lea     rdx, [rdi+0Ch]; pv
0x18003e46c  mov     r8d, 4; cb
0x18003e472  mov     rcx, rbp; pstm
0x18003e475  call    cs:__imp_IStream_Read
0x18003e47b  mov     ebx, eax
0x18003e47d  test    eax, eax
0x18003e47f  js      loc_18003E547
0x18003e485  xor     esi, esi
0x18003e487  lea     rdx, [rsp+48h+pv]; pv
0x18003e48c  mov     rcx, rbp; pstm
0x18003e48f  mov     dword ptr [rsp+48h+pv], esi
0x18003e493  lea     r8d, [rsi+4]; cb
0x18003e497  call    cs:__imp_IStream_Read
0x18003e49d  mov     ebx, eax
0x18003e49f  test    eax, eax
0x18003e4a1  js      short loc_18003E4FF
0x18003e4a3  mov     eax, dword ptr [rsp+48h+pv]
0x18003e4a7  test    eax, eax
0x18003e4a9  jz      short loc_18003E4FF
0x18003e4ab  add     rax, rax
0x18003e4ae  mov     ecx, 0FFFFFFFFh
0x18003e4b3  cmp     rax, rcx
0x18003e4b6  ja      loc_18003E571
0x18003e4bc  mov     ecx, eax; cb
0x18003e4be  call    cs:__imp_CoTaskMemAlloc
0x18003e4c4  mov     rsi, rax
0x18003e4c7  test    rax, rax
0x18003e4ca  jz      loc_18003E578
0x18003e4d0  mov     r8d, dword ptr [rsp+48h+pv]
0x18003e4d5  mov     rdx, rax; pv
0x18003e4d8  mov     rcx, rbp; pstm
0x18003e4db  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003e4e3  call    cs:__imp_IStream_Read
0x18003e4e9  mov     ebx, eax
0x18003e4eb  test    eax, eax
0x18003e4ed  js      loc_18003E57F
0x18003e4f3  mov     ecx, dword ptr [rsp+48h+pv]
0x18003e4f7  dec     ecx
0x18003e4f9  xor     eax, eax
0x18003e4fb  mov     [rsi+rcx*2], ax
0x18003e4ff  mov     [rdi+10h], rsi
0x18003e503  test    ebx, ebx
0x18003e505  js      short loc_18003E547
0x18003e507  test    r14b, r14b
0x18003e50a  jz      short loc_18003E52B
0x18003e50c  lea     rdx, [rdi+20h]; pv
0x18003e510  mov     word ptr [rdi+18h], 3
0x18003e516  mov     r8d, 4; cb
0x18003e51c  mov     rcx, rbp; pstm
0x18003e51f  call    cs:__imp_IStream_Read
0x18003e525  mov     ebx, eax
0x18003e527  test    eax, eax
0x18003e529  js      short loc_18003E547
0x18003e52b  mov     rax, [rdi]
0x18003e52e  lea     r8, [rsp+48h+arg_18]
0x18003e533  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18003e53a  mov     rcx, rdi
0x18003e53d  mov     rax, [rax]
0x18003e540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e545  mov     ebx, eax
0x18003e547  mov     rax, [rdi]
0x18003e54a  mov     rcx, rdi
0x18003e54d  mov     rax, [rax+10h]
0x18003e551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e556  mov     rax, [rsp+48h+arg_18]
0x18003e55b  mov     [r15], rax
0x18003e55e  mov     eax, ebx
0x18003e560  mov     rbx, [rsp+48h+arg_0]
0x18003e565  add     rsp, 20h
0x18003e569  pop     r15
0x18003e56b  pop     r14
0x18003e56d  pop     rdi
0x18003e56e  pop     rsi
0x18003e56f  pop     rbp
0x18003e570  retn
0x18003e571  mov     ebx, 80070216h
0x18003e576  jmp     short loc_18003E4FF
0x18003e578  mov     ebx, 8007000Eh
0x18003e57d  jmp     short loc_18003E4FF
0x18003e57f  mov     rcx, rsi; pv
0x18003e582  call    cs:__imp_CoTaskMemFree
0x18003e588  xor     esi, esi
0x18003e58a  jmp     loc_18003E4FF
```

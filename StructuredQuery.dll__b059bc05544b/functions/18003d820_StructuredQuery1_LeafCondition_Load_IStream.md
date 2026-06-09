# StructuredQuery1::LeafCondition::Load(IStream *)

- ea: `0x18003d820`
- end: `0x18003db27`
- name: `?Load@LeafCondition@StructuredQuery1@@UEAAJPEAUIStream@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(StructuredQuery1::LeafCondition *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003d820`
- `0x18003db30`
- `0x18003dc94`
- `0x18003e3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d84c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d84c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003da65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003db18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d977`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d878`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d895`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d8cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d917`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d951`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d99b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d9d9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003da0e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003da43`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d878`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d895`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d8cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d917`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d951`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d99b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003d9d9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003da0e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003da43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::LeafCondition::Load(struct IStream **this, struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  int PROPVARIANT; // ebx
  struct tagPROPVARIANT *v6; // r8
  void *v7; // r14
  unsigned __int64 v8; // rax
  void *v9; // rax
  void *v10; // r14
  unsigned __int64 v11; // rax
  void *v12; // rax
  struct IStream *v13; // r14
  const struct _GUID *v14; // r8
  struct IStream *v15; // r14
  const struct _GUID *v16; // r8
  struct IStream *v17; // r14
  const struct _GUID *v18; // r8
  unsigned int pv; // [rsp+58h] [rbp+38h] BYREF
  void *v21; // [rsp+60h] [rbp+40h] BYREF
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+68h] [rbp+48h]

  if ( a2 )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)(this + 17);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 17));
    v22 = v4;
    PROPVARIANT = StructuredQuery1::BaseCondition::Load((StructuredQuery1::BaseCondition *)this, a2);
    if ( PROPVARIANT >= 0 )
    {
      PROPVARIANT = IStream_Read(a2, this + 6, 0x14u);
      if ( PROPVARIANT >= 0 )
      {
        PROPVARIANT = IStream_Read(a2, (char *)this + 68, 4u);
        if ( PROPVARIANT >= 0 )
        {
          PROPVARIANT = StructuredQuery1::ReadPROPVARIANT(a2, this + 9, v6);
          if ( PROPVARIANT >= 0 )
          {
            v7 = 0;
            pv = 0;
            PROPVARIANT = IStream_Read(a2, &pv, 4u);
            if ( PROPVARIANT >= 0 && pv )
            {
              v8 = 2LL * pv;
              if ( v8 > 0xFFFFFFFF )
              {
                PROPVARIANT = -2147024362;
              }
              else
              {
                v9 = CoTaskMemAlloc((unsigned int)v8);
                v7 = v9;
                if ( v9 )
                {
                  PROPVARIANT = IStream_Read(a2, v9, 2 * pv - 2);
                  if ( PROPVARIANT < 0 )
                  {
                    CoTaskMemFree(v7);
                    v7 = 0;
                  }
                  else
                  {
                    *((_WORD *)v7 + pv - 1) = 0;
                  }
                }
                else
                {
                  PROPVARIANT = -2147024882;
                }
              }
            }
            this[12] = (struct IStream *)v7;
            if ( PROPVARIANT >= 0 )
            {
              v10 = 0;
              pv = 0;
              PROPVARIANT = IStream_Read(a2, &pv, 4u);
              if ( PROPVARIANT >= 0 && pv )
              {
                v11 = 2LL * pv;
                if ( v11 > 0xFFFFFFFF )
                {
                  PROPVARIANT = -2147024362;
                }
                else
                {
                  v12 = CoTaskMemAlloc((unsigned int)v11);
                  v10 = v12;
                  if ( v12 )
                  {
                    PROPVARIANT = IStream_Read(a2, v12, 2 * pv - 2);
                    if ( PROPVARIANT < 0 )
                    {
                      CoTaskMemFree(v10);
                      v10 = 0;
                    }
                    else
                    {
                      *((_WORD *)v10 + pv - 1) = 0;
                    }
                  }
                  else
                  {
                    PROPVARIANT = -2147024882;
                  }
                }
              }
              this[13] = (struct IStream *)v10;
              if ( PROPVARIANT >= 0 )
              {
                v13 = 0;
                v21 = 0;
                LOBYTE(pv) = 0;
                PROPVARIANT = IStream_Read(a2, &pv, 1u);
                if ( PROPVARIANT >= 0 && (_BYTE)pv )
                {
                  PROPVARIANT = StructuredQuery1::TokenInformationComplete::CreateInstance(
                                  a2,
                                  (_BYTE)pv == 2,
                                  v14,
                                  &v21);
                  v13 = (struct IStream *)v21;
                }
                this[14] = v13;
                if ( PROPVARIANT >= 0 )
                {
                  v15 = 0;
                  v21 = 0;
                  LOBYTE(pv) = 0;
                  PROPVARIANT = IStream_Read(a2, &pv, 1u);
                  if ( PROPVARIANT >= 0 && (_BYTE)pv )
                  {
                    PROPVARIANT = StructuredQuery1::TokenInformationComplete::CreateInstance(
                                    a2,
                                    (_BYTE)pv == 2,
                                    v16,
                                    &v21);
                    v15 = (struct IStream *)v21;
                  }
                  this[15] = v15;
                  if ( PROPVARIANT >= 0 )
                  {
                    v17 = 0;
                    v21 = 0;
                    LOBYTE(pv) = 0;
                    PROPVARIANT = IStream_Read(a2, &pv, 1u);
                    if ( PROPVARIANT >= 0 && (_BYTE)pv )
                    {
                      PROPVARIANT = StructuredQuery1::TokenInformationComplete::CreateInstance(
                                      a2,
                                      (_BYTE)pv == 2,
                                      v18,
                                      &v21);
                      v17 = (struct IStream *)v21;
                    }
                    this[16] = v17;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v4 )
      LeaveCriticalSection(v4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)PROPVARIANT;
}

```

## disassembly

```asm
0x18003d820  mov     [rsp-28h+arg_0], rbx
0x18003d825  push    rbp
0x18003d826  push    rsi
0x18003d827  push    rdi
0x18003d828  push    r14
0x18003d82a  push    r15
0x18003d82c  mov     rbp, rsp
0x18003d82f  sub     rsp, 20h
0x18003d833  mov     rdi, rdx
0x18003d836  mov     rsi, rcx
0x18003d839  test    rdx, rdx
0x18003d83c  jz      loc_18003DAE6
0x18003d842  lea     r15, [rcx+88h]
0x18003d849  mov     rcx, r15; lpCriticalSection
0x18003d84c  call    cs:__imp_EnterCriticalSection
0x18003d852  mov     [rbp+arg_18], r15
0x18003d856  mov     rdx, rdi; struct IStream *
0x18003d859  mov     rcx, rsi; this
0x18003d85c  call    ?Load@BaseCondition@StructuredQuery1@@UEAAJPEAUIStream@@@Z; StructuredQuery1::BaseCondition::Load(IStream *)
0x18003d861  mov     ebx, eax
0x18003d863  test    eax, eax
0x18003d865  js      loc_18003DA5D
0x18003d86b  lea     rdx, [rsi+30h]; pv
0x18003d86f  mov     r8d, 14h; cb
0x18003d875  mov     rcx, rdi; pstm
0x18003d878  call    cs:__imp_IStream_Read
0x18003d87e  mov     ebx, eax
0x18003d880  test    eax, eax
0x18003d882  js      loc_18003DA5D
0x18003d888  lea     rdx, [rsi+44h]; pv
0x18003d88c  mov     r8d, 4; cb
0x18003d892  mov     rcx, rdi; pstm
0x18003d895  call    cs:__imp_IStream_Read
0x18003d89b  mov     ebx, eax
0x18003d89d  test    eax, eax
0x18003d89f  js      loc_18003DA5D
0x18003d8a5  lea     rdx, [rsi+48h]; struct IStream *
0x18003d8a9  mov     rcx, rdi; this
0x18003d8ac  call    ?ReadPROPVARIANT@StructuredQuery1@@YAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z; StructuredQuery1::ReadPROPVARIANT(IStream *,tagPROPVARIANT *)
0x18003d8b1  mov     ebx, eax
0x18003d8b3  test    eax, eax
0x18003d8b5  js      loc_18003DA5D
0x18003d8bb  xor     r14d, r14d
0x18003d8be  mov     [rbp+pv], r14d
0x18003d8c2  lea     r8d, [r14+4]; cb
0x18003d8c6  lea     rdx, [rbp+pv]; pv
0x18003d8ca  mov     rcx, rdi; pstm
0x18003d8cd  call    cs:__imp_IStream_Read
0x18003d8d3  mov     ebx, eax
0x18003d8d5  mov     ecx, 0FFFFFFFFh
0x18003d8da  test    eax, eax
0x18003d8dc  js      short loc_18003D933
0x18003d8de  mov     eax, [rbp+pv]
0x18003d8e1  test    eax, eax
0x18003d8e3  jz      short loc_18003D933
0x18003d8e5  add     rax, rax
0x18003d8e8  cmp     rax, rcx
0x18003d8eb  ja      loc_18003DA7E
0x18003d8f1  mov     ecx, eax; cb
0x18003d8f3  call    cs:__imp_CoTaskMemAlloc
0x18003d8f9  mov     r14, rax
0x18003d8fc  test    rax, rax
0x18003d8ff  jz      loc_18003DAF0
0x18003d905  mov     r8d, [rbp+pv]
0x18003d909  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003d911  mov     rdx, rax; pv
0x18003d914  mov     rcx, rdi; pstm
0x18003d917  call    cs:__imp_IStream_Read
0x18003d91d  mov     ebx, eax
0x18003d91f  test    eax, eax
0x18003d921  js      loc_18003DB04
0x18003d927  mov     ecx, [rbp+pv]
0x18003d92a  dec     ecx
0x18003d92c  xor     eax, eax
0x18003d92e  mov     [r14+rcx*2], ax
0x18003d933  mov     [rsi+60h], r14
0x18003d937  test    ebx, ebx
0x18003d939  js      loc_18003DA5D
0x18003d93f  xor     r14d, r14d
0x18003d942  mov     [rbp+pv], r14d
0x18003d946  lea     r8d, [r14+4]; cb
0x18003d94a  lea     rdx, [rbp+pv]; pv
0x18003d94e  mov     rcx, rdi; pstm
0x18003d951  call    cs:__imp_IStream_Read
0x18003d957  mov     ebx, eax
0x18003d959  test    eax, eax
0x18003d95b  js      short loc_18003D9B7
0x18003d95d  mov     eax, [rbp+pv]
0x18003d960  test    eax, eax
0x18003d962  jz      short loc_18003D9B7
0x18003d964  add     rax, rax
0x18003d967  mov     ecx, 0FFFFFFFFh
0x18003d96c  cmp     rax, rcx
0x18003d96f  ja      loc_18003DA88
0x18003d975  mov     ecx, eax; cb
0x18003d977  call    cs:__imp_CoTaskMemAlloc
0x18003d97d  mov     r14, rax
0x18003d980  test    rax, rax
0x18003d983  jz      loc_18003DAFA
0x18003d989  mov     r8d, [rbp+pv]
0x18003d98d  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; cb
0x18003d995  mov     rdx, rax; pv
0x18003d998  mov     rcx, rdi; pstm
0x18003d99b  call    cs:__imp_IStream_Read
0x18003d9a1  mov     ebx, eax
0x18003d9a3  test    eax, eax
0x18003d9a5  js      loc_18003DB15
0x18003d9ab  mov     ecx, [rbp+pv]
0x18003d9ae  dec     ecx
0x18003d9b0  xor     eax, eax
0x18003d9b2  mov     [r14+rcx*2], ax
0x18003d9b7  mov     [rsi+68h], r14
0x18003d9bb  test    ebx, ebx
0x18003d9bd  js      loc_18003DA5D
0x18003d9c3  xor     r14d, r14d
0x18003d9c6  mov     [rbp+arg_10], r14
0x18003d9ca  mov     byte ptr [rbp+pv], r14b
0x18003d9ce  lea     r8d, [r14+1]; cb
0x18003d9d2  lea     rdx, [rbp+pv]; pv
0x18003d9d6  mov     rcx, rdi; pstm
0x18003d9d9  call    cs:__imp_IStream_Read
0x18003d9df  mov     ebx, eax
0x18003d9e1  test    eax, eax
0x18003d9e3  js      short loc_18003D9F0
0x18003d9e5  mov     al, byte ptr [rbp+pv]
0x18003d9e8  test    al, al
0x18003d9ea  jnz     loc_18003DA92
0x18003d9f0  mov     [rsi+70h], r14
0x18003d9f4  test    ebx, ebx
0x18003d9f6  js      short loc_18003DA5D
0x18003d9f8  xor     r14d, r14d
0x18003d9fb  mov     [rbp+arg_10], r14
0x18003d9ff  mov     byte ptr [rbp+pv], r14b
0x18003da03  lea     r8d, [r14+1]; cb
0x18003da07  lea     rdx, [rbp+pv]; pv
0x18003da0b  mov     rcx, rdi; pstm
0x18003da0e  call    cs:__imp_IStream_Read
0x18003da14  mov     ebx, eax
0x18003da16  test    eax, eax
0x18003da18  js      short loc_18003DA25
0x18003da1a  mov     al, byte ptr [rbp+pv]
0x18003da1d  test    al, al
0x18003da1f  jnz     loc_18003DAAE
0x18003da25  mov     [rsi+78h], r14
0x18003da29  test    ebx, ebx
0x18003da2b  js      short loc_18003DA5D
0x18003da2d  xor     r14d, r14d
0x18003da30  mov     [rbp+arg_10], r14
0x18003da34  mov     byte ptr [rbp+pv], r14b
0x18003da38  lea     r8d, [r14+1]; cb
0x18003da3c  lea     rdx, [rbp+pv]; pv
0x18003da40  mov     rcx, rdi; pstm
0x18003da43  call    cs:__imp_IStream_Read
0x18003da49  mov     ebx, eax
0x18003da4b  test    eax, eax
0x18003da4d  js      short loc_18003DA56
0x18003da4f  mov     al, byte ptr [rbp+pv]
0x18003da52  test    al, al
0x18003da54  jnz     short loc_18003DACA
0x18003da56  mov     [rsi+80h], r14
0x18003da5d  test    r15, r15
0x18003da60  jz      short loc_18003DA6B
0x18003da62  mov     rcx, r15; lpCriticalSection
0x18003da65  call    cs:__imp_LeaveCriticalSection
0x18003da6b  mov     eax, ebx
0x18003da6d  mov     rbx, [rsp+20h+arg_0]
0x18003da72  add     rsp, 20h
0x18003da76  pop     r15
0x18003da78  pop     r14
0x18003da7a  pop     rdi
0x18003da7b  pop     rsi
0x18003da7c  pop     rbp
0x18003da7d  retn
0x18003da7e  mov     ebx, 80070216h
0x18003da83  jmp     loc_18003D933
0x18003da88  mov     ebx, 80070216h
0x18003da8d  jmp     loc_18003D9B7
0x18003da92  cmp     al, 2
0x18003da94  setz    dl; bool
0x18003da97  lea     r9, [rbp+arg_10]; void **
0x18003da9b  mov     rcx, rdi; pstm
0x18003da9e  call    ?CreateInstance@TokenInformationComplete@StructuredQuery1@@SAJPEAUIStream@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformationComplete::CreateInstance(IStream *,bool,_GUID const &,void * *)
0x18003daa3  mov     ebx, eax
0x18003daa5  mov     r14, [rbp+arg_10]
0x18003daa9  jmp     loc_18003D9F0
0x18003daae  cmp     al, 2
0x18003dab0  setz    dl; bool
0x18003dab3  lea     r9, [rbp+arg_10]; void **
0x18003dab7  mov     rcx, rdi; pstm
0x18003daba  call    ?CreateInstance@TokenInformationComplete@StructuredQuery1@@SAJPEAUIStream@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformationComplete::CreateInstance(IStream *,bool,_GUID const &,void * *)
0x18003dabf  mov     ebx, eax
0x18003dac1  mov     r14, [rbp+arg_10]
0x18003dac5  jmp     loc_18003DA25
0x18003daca  cmp     al, 2
0x18003dacc  setz    dl; bool
0x18003dacf  lea     r9, [rbp+arg_10]; void **
0x18003dad3  mov     rcx, rdi; pstm
0x18003dad6  call    ?CreateInstance@TokenInformationComplete@StructuredQuery1@@SAJPEAUIStream@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformationComplete::CreateInstance(IStream *,bool,_GUID const &,void * *)
0x18003dadb  mov     ebx, eax
0x18003dadd  mov     r14, [rbp+arg_10]
0x18003dae1  jmp     loc_18003DA56
0x18003dae6  mov     ebx, 80070057h
0x18003daeb  jmp     loc_18003DA6B
0x18003daf0  mov     ebx, 8007000Eh
0x18003daf5  jmp     loc_18003D933
0x18003dafa  mov     ebx, 8007000Eh
0x18003daff  jmp     loc_18003D9B7
0x18003db04  mov     rcx, r14; pv
0x18003db07  call    cs:__imp_CoTaskMemFree
0x18003db0d  xor     r14d, r14d
0x18003db10  jmp     loc_18003D933
0x18003db15  mov     rcx, r14; pv
0x18003db18  call    cs:__imp_CoTaskMemFree
0x18003db1e  xor     r14d, r14d
0x18003db21  jmp     loc_18003D9B7
```

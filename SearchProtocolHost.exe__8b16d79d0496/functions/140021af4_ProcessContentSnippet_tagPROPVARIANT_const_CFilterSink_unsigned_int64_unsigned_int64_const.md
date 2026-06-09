# ProcessContentSnippet(tagPROPVARIANT const &,CFilterSink &,unsigned __int64 *,unsigned __int64 const &)

- ea: `0x140021af4`
- end: `0x140021c68`
- name: `?ProcessContentSnippet@@YAJAEBUtagPROPVARIANT@@AEAVCFilterSink@@PEA_KAEB_K@Z`
- size: `372`
- prototype: `int(const struct tagPROPVARIANT *, struct CFilterSink *, unsigned __int64 *, const unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140014c94`

## callees

- `0x14000e898`
- `0x140014b6c`
- `0x140021af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021c45`
- `PROPSYS!__imp_PropVariantToStreamObjectAsBlob` at `0x140021b2b`
- `PROPSYS!__imp_PropVariantToStreamObjectAsBlob` at `0x140021b2b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_ReadStr` at `0x140021bf5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_ReadStr` at `0x140021bf5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021b4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021bb3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021bd1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021b4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021bb3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x140021bd1`
- `SHCORE!__imp_IStream_ReadStrLong` at `0x140021b67`
- `SHCORE!__imp_IStream_ReadStrLong` at `0x140021b67`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProcessContentSnippet(
        const struct tagPROPVARIANT *a1,
        struct CFilterSink *a2,
        unsigned __int64 *a3,
        const unsigned __int64 *a4)
{
  HRESULT Str; // ebx
  __int64 v8; // rdi
  unsigned int v9; // esi
  unsigned int v11; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-34h] BYREF
  unsigned int pv; // [rsp+48h] [rbp-30h] BYREF
  IStream *pstm; // [rsp+50h] [rbp-28h] BYREF
  wchar_t *v15; // [rsp+58h] [rbp-20h] BYREF
  PWSTR ppsz[3]; // [rsp+60h] [rbp-18h] BYREF

  ppsz[1] = (PWSTR)-2LL;
  pstm = 0;
  Str = PropVariantToStreamObjectAsBlob(a1, &GUID_0000000c_0000_0000_c000_000000000046, &pstm);
  if ( Str >= 0 )
  {
    pv = 0;
    Str = IStream_Read(pstm, &pv, 4u);
    if ( Str >= 0 )
    {
      v15 = 0;
      Str = IStream_ReadStrLong(pstm, &v15);
      if ( Str >= 0 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v15[v8] );
        v9 = 0;
        while ( Str != 266761 && v9 < pv )
        {
          v12 = 0;
          Str = IStream_Read(pstm, &v12, 4u);
          if ( Str >= 0 )
          {
            v11 = 0;
            Str = IStream_Read(pstm, &v11, 4u);
            if ( Str >= 0 )
            {
              if ( v11 <= v12 || v11 > (unsigned int)v8 )
              {
                Str = -2147024809;
                break;
              }
              ppsz[0] = 0;
              Str = IStream_ReadStr(pstm, ppsz);
              if ( Str >= 0 )
              {
                Str = EmitContentSnippetContent(v15, v12, v11, ppsz[0], a2, a3, a4);
                CoTaskMemFree(ppsz[0]);
              }
            }
          }
          ++v9;
          if ( Str < 0 )
            break;
        }
        CoTaskMemFree(v15);
      }
    }
  }
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&pstm);
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x140021af4  push    rbp
0x140021af6  push    rbx
0x140021af7  push    rsi
0x140021af8  push    rdi
0x140021af9  push    r12
0x140021afb  push    r13
0x140021afd  push    r14
0x140021aff  push    r15
0x140021b01  mov     rbp, rsp
0x140021b04  sub     rsp, 78h
0x140021b08  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x140021b10  mov     r14, r9
0x140021b13  mov     r15, r8
0x140021b16  mov     r12, rdx
0x140021b19  xor     r13d, r13d
0x140021b1c  mov     [rbp+pstm], r13
0x140021b20  lea     r8, [rbp+pstm]
0x140021b24  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x140021b2b  call    cs:__imp_PropVariantToStreamObjectAsBlob
0x140021b31  mov     ebx, eax
0x140021b33  test    eax, eax
0x140021b35  js      loc_140021C4C
0x140021b3b  mov     [rbp+pv], r13d
0x140021b3f  lea     r8d, [r13+4]; cb
0x140021b43  lea     rdx, [rbp+pv]; pv
0x140021b47  mov     rcx, [rbp+pstm]; pstm
0x140021b4b  call    cs:__imp_IStream_Read
0x140021b51  mov     ebx, eax
0x140021b53  test    eax, eax
0x140021b55  js      loc_140021C4C
0x140021b5b  mov     [rbp+var_20], r13
0x140021b5f  lea     rdx, [rbp+var_20]
0x140021b63  mov     rcx, [rbp+pstm]
0x140021b67  call    cs:__imp_IStream_ReadStrLong
0x140021b6d  mov     ebx, eax
0x140021b6f  test    eax, eax
0x140021b71  js      loc_140021C4C
0x140021b77  mov     rax, [rbp+var_20]
0x140021b7b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140021b7f  inc     rdi
0x140021b82  cmp     [rax+rdi*2], r13w
0x140021b87  jnz     short loc_140021B7F
0x140021b89  mov     esi, r13d
0x140021b8c  cmp     ebx, 41209h
0x140021b92  jz      loc_140021C41
0x140021b98  cmp     esi, [rbp+pv]
0x140021b9b  jnb     loc_140021C41
0x140021ba1  mov     [rbp+var_34], r13d
0x140021ba5  mov     r8d, 4; cb
0x140021bab  lea     rdx, [rbp+var_34]; pv
0x140021baf  mov     rcx, [rbp+pstm]; pstm
0x140021bb3  call    cs:__imp_IStream_Read
0x140021bb9  mov     ebx, eax
0x140021bbb  test    eax, eax
0x140021bbd  js      short loc_140021C30
0x140021bbf  mov     [rbp+var_38], r13d
0x140021bc3  mov     r8d, 4; cb
0x140021bc9  lea     rdx, [rbp+var_38]; pv
0x140021bcd  mov     rcx, [rbp+pstm]; pstm
0x140021bd1  call    cs:__imp_IStream_Read
0x140021bd7  mov     ebx, eax
0x140021bd9  test    eax, eax
0x140021bdb  js      short loc_140021C30
0x140021bdd  mov     eax, [rbp+var_38]
0x140021be0  cmp     eax, [rbp+var_34]
0x140021be3  jbe     short loc_140021C3C
0x140021be5  cmp     eax, edi
0x140021be7  ja      short loc_140021C3C
0x140021be9  mov     [rbp+ppsz], r13
0x140021bed  lea     rdx, [rbp+ppsz]; ppsz
0x140021bf1  mov     rcx, [rbp+pstm]; pstm
0x140021bf5  call    cs:__imp_IStream_ReadStr
0x140021bfb  mov     ebx, eax
0x140021bfd  test    eax, eax
0x140021bff  js      short loc_140021C30
0x140021c01  mov     [rsp+78h+var_48], r14; unsigned __int64 *
0x140021c06  mov     [rsp+78h+var_50], r15; unsigned __int64 *
0x140021c0b  mov     [rsp+78h+var_58], r12; struct CFilterSink *
0x140021c10  mov     r9, [rbp+ppsz]; wchar_t *
0x140021c14  mov     r8d, [rbp+var_38]; unsigned int
0x140021c18  mov     edx, [rbp+var_34]; unsigned int
0x140021c1b  mov     rcx, [rbp+var_20]; wchar_t *
0x140021c1f  call    ?EmitContentSnippetContent@@YAJPEB_WII0AEAVCFilterSink@@PEA_KAEB_K@Z; EmitContentSnippetContent(wchar_t const *,uint,uint,wchar_t const *,CFilterSink &,unsigned __int64 *,unsigned __int64 const &)
0x140021c24  mov     ebx, eax
0x140021c26  mov     rcx, [rbp+ppsz]; pv
0x140021c2a  call    cs:__imp_CoTaskMemFree
0x140021c30  inc     esi
0x140021c32  test    ebx, ebx
0x140021c34  jns     loc_140021B8C
0x140021c3a  jmp     short loc_140021C41
0x140021c3c  mov     ebx, 80070057h
0x140021c41  mov     rcx, [rbp+var_20]; pv
0x140021c45  call    cs:__imp_CoTaskMemFree
0x140021c4b  nop
0x140021c4c  lea     rcx, [rbp+pstm]
0x140021c50  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140021c55  mov     eax, ebx
0x140021c57  add     rsp, 78h
0x140021c5b  pop     r15
0x140021c5d  pop     r14
0x140021c5f  pop     r13
0x140021c61  pop     r12
0x140021c63  pop     rdi
0x140021c64  pop     rsi
0x140021c65  pop     rbx
0x140021c66  pop     rbp
0x140021c67  retn
```

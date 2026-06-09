# ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::Rehash(uint)

- ea: `0x1800359e8`
- end: `0x180035b0f`
- name: `?Rehash@?$CAtlMap@PEBUIUnknown@@V?$CComQIPtr@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@ATL@@V?$CElementTraits@PEBUIUnknown@@@3@V?$CComQIPtrElementTraits@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@3@@ATL@@QEAAXI@Z`
- size: `295`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180027a04`
- `0x1800358e4`
- `0x18006c174`
- `0x18006ca18`

## callees

- `0x18002078c`
- `0x18002fa28`
- `0x18002fee8`
- `0x1800359e8`
- `0x180040264`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180035af0`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180035af0`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180035a66`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180035a66`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180035a98`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180035a98`

## pseudocode

```c
void __fastcall ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  unsigned int *v5; // rsi
  unsigned __int128 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // r14
  unsigned __int64 v9; // rdx
  __int64 i; // r9
  __int64 v11; // r10
  __int64 v12; // r8

  v3 = a2;
  if ( !a2 )
    v3 = ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(
           a1,
           *(_QWORD *)(a1 + 8));
  v5 = (unsigned int *)(a1 + 16);
  if ( v3 != *(_DWORD *)(a1 + 16) )
  {
    if ( *(_QWORD *)a1 )
    {
      v6 = v3 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v3, 8u) )
        *(_QWORD *)&v6 = -1;
      BYTE8(v6) = 1;
      v7 = BasePrivate::New((BasePrivate *)v6, *((unsigned __int64 *)&v6 + 1), a3);
      v8 = v7;
      if ( !v7 )
      {
        ATL::BaseAtlThrow(-2147024882);
        __debugbreak();
      }
      memset_0(v7, 0, 8LL * v3);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
        if ( v11 )
        {
          do
          {
            v12 = *(_QWORD *)(v11 + 16);
            v9 = *(_DWORD *)(v11 + 24) % v3;
            *(_QWORD *)(v11 + 16) = v8[v9];
            v8[(unsigned int)v9] = v11;
            v11 = v12;
          }
          while ( v12 );
        }
      }
      BasePrivate::Delete(*(BasePrivate **)a1, (void *)v9);
      *(_QWORD *)a1 = v8;
      *v5 = v3;
      ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(a1);
    }
    else
    {
      ATL::CAtlMap<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::InitHashTable(
        a1,
        v3,
        0);
    }
  }
}

```

## disassembly

```asm
0x1800359e8  mov     [rsp+arg_8], edx
0x1800359ec  mov     [rsp+arg_0], rcx
0x1800359f1  push    rbx
0x1800359f2  push    rsi
0x1800359f3  push    rdi
0x1800359f4  push    r14
0x1800359f6  push    r15
0x1800359f8  sub     rsp, 30h
0x1800359fc  mov     edi, edx
0x1800359fe  mov     rbx, rcx
0x180035a01  test    edx, edx
0x180035a03  jnz     short loc_180035A14
0x180035a05  mov     rdx, [rcx+8]
0x180035a09  call    ?PickSize@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(unsigned __int64)
0x180035a0e  mov     edi, eax
0x180035a10  mov     [rsp+58h+arg_8], eax
0x180035a14  lea     rsi, [rbx+10h]
0x180035a18  mov     [rsp+58h+var_38], rsi
0x180035a1d  cmp     edi, [rsi]
0x180035a1f  jz      loc_180035B03
0x180035a25  mov     [rsp+58h+arg_10], 0
0x180035a2e  cmp     qword ptr [rbx], 0
0x180035a32  jnz     short loc_180035A46
0x180035a34  xor     r8d, r8d
0x180035a37  mov     edx, edi
0x180035a39  mov     rcx, rbx
0x180035a3c  call    ?InitHashTable@?$CAtlMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::InitHashTable(uint,bool)
0x180035a41  jmp     loc_180035B03
0x180035a46  mov     r15d, edi
0x180035a49  mov     [rsp+58h+arg_18], r15
0x180035a4e  mov     eax, 8
0x180035a53  mul     r15
0x180035a56  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180035a5d  cmovb   rax, rcx
0x180035a61  mov     dl, 1
0x180035a63  mov     rcx, rax
0x180035a66  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180035a6c  mov     r14, rax
0x180035a6f  mov     [rsp+58h+arg_10], rax
0x180035a74  jmp     short loc_180035A8E
0x180035a76  mov     rbx, [rsp+58h+arg_0]
0x180035a7b  mov     edi, [rsp+58h+arg_8]
0x180035a7f  mov     r14, [rsp+58h+arg_10]
0x180035a84  mov     r15, [rsp+58h+arg_18]
0x180035a89  mov     rsi, [rsp+58h+var_38]
0x180035a8e  test    r14, r14
0x180035a91  jnz     short loc_180035A9F
0x180035a93  mov     ecx, 8007000Eh
0x180035a98  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180035a9e  int     3; Trap to Debugger
0x180035a9f  lea     r8, ds:0[r15*8]; Size
0x180035aa7  xor     edx, edx; Val
0x180035aa9  mov     rcx, r14; void *
0x180035aac  call    memset_0
0x180035ab1  xor     r9d, r9d
0x180035ab4  cmp     [rsi], r9d
0x180035ab7  jbe     short loc_180035AED
0x180035ab9  mov     rax, [rbx]
0x180035abc  mov     r10, [rax+r9*8]
0x180035ac0  test    r10, r10
0x180035ac3  jz      short loc_180035AE5
0x180035ac5  mov     r8, [r10+10h]
0x180035ac9  xor     edx, edx
0x180035acb  mov     eax, [r10+18h]
0x180035acf  div     edi
0x180035ad1  mov     rax, [r14+rdx*8]
0x180035ad5  mov     [r10+10h], rax
0x180035ad9  mov     [r14+rdx*8], r10
0x180035add  mov     r10, r8
0x180035ae0  test    r8, r8
0x180035ae3  jnz     short loc_180035AC5
0x180035ae5  inc     r9d
0x180035ae8  cmp     r9d, [rsi]
0x180035aeb  jb      short loc_180035AB9
0x180035aed  mov     rcx, [rbx]
0x180035af0  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x180035af6  mov     [rbx], r14
0x180035af9  mov     [rsi], edi
0x180035afb  mov     rcx, rbx
0x180035afe  call    ?UpdateRehashThresholds@?$CAtlMap@PEBUIUnknown@@V?$CComQIPtr@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@ATL@@V?$CElementTraits@PEBUIUnknown@@@3@V?$CComQIPtrElementTraits@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@3@@ATL@@AEAAXXZ; ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(void)
0x180035b03  add     rsp, 30h
0x180035b07  pop     r15
0x180035b09  pop     r14
0x180035b0b  pop     rdi
0x180035b0c  pop     rsi
0x180035b0d  pop     rbx
0x180035b0e  retn
```

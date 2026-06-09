# ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::Rehash(uint)

- ea: `0x18003073c`
- end: `0x180030863`
- name: `?Rehash@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@QEAAXI@Z`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180030420`
- `0x180030580`

## callees

- `0x18002fa28`
- `0x18002fee8`
- `0x180030698`
- `0x18003073c`
- `0x180040264`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180030844`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180030844`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800307ba`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800307ba`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800307ec`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800307ec`

## pseudocode

```c
void __fastcall ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::Rehash(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  unsigned int *v5; // rsi
  __int64 v6; // r15
  unsigned __int128 v7; // rax
  void *v8; // r14
  unsigned __int64 v9; // rdx
  __int64 i; // r9
  __int64 v11; // r10
  __int64 v12; // r8
  unsigned int *v13; // [rsp+20h] [rbp-38h]
  unsigned int v15; // [rsp+68h] [rbp+10h]
  void *v16; // [rsp+70h] [rbp+18h]
  __int64 v17; // [rsp+78h] [rbp+20h]

  v15 = a2;
  v3 = a2;
  v4 = a1;
  if ( !a2 )
  {
    v3 = ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(
           a1,
           *(_QWORD *)(a1 + 8));
    v15 = v3;
  }
  v5 = (unsigned int *)(v4 + 16);
  v13 = (unsigned int *)(v4 + 16);
  if ( v3 != *(_DWORD *)(v4 + 16) )
  {
    if ( *(_QWORD *)v4 )
    {
      v6 = v3;
      v17 = v3;
      v7 = v3 * (unsigned __int128)8uLL;
      if ( !is_mul_ok(v3, 8u) )
        *(_QWORD *)&v7 = -1;
      try
      {
        BYTE8(v7) = 1;
        v8 = BasePrivate::New((BasePrivate *)v7, *((unsigned __int64 *)&v7 + 1), a3);
        v16 = v8;
      }
      catch ( ... )
      {
        v4 = a1;
        v3 = v15;
        v8 = v16;
        v6 = v17;
        v5 = v13;
      }
      if ( !v8 )
      {
        ATL::BaseAtlThrow(-2147024882);
        __debugbreak();
      }
      memset_0(v8, 0, 8 * v6);
      for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(*(_QWORD *)v4 + 8 * i);
        if ( v11 )
        {
          do
          {
            v12 = *(_QWORD *)(v11 + 16);
            v9 = *(_DWORD *)(v11 + 24) % v3;
            *(_QWORD *)(v11 + 16) = *((_QWORD *)v8 + v9);
            *((_QWORD *)v8 + (unsigned int)v9) = v11;
            v11 = v12;
          }
          while ( v12 );
        }
      }
      BasePrivate::Delete(*(BasePrivate **)v4, (void *)v9);
      *(_QWORD *)v4 = v8;
      *v5 = v3;
      ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(v4);
    }
    else
    {
      ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::InitHashTable(
        v4,
        v3,
        0);
    }
  }
}

```

## disassembly

```asm
0x18003073c  mov     [rsp+arg_8], edx
0x180030740  mov     [rsp+arg_0], rcx
0x180030745  push    rbx
0x180030746  push    rsi
0x180030747  push    rdi
0x180030748  push    r14
0x18003074a  push    r15
0x18003074c  sub     rsp, 30h
0x180030750  mov     edi, edx
0x180030752  mov     rbx, rcx
0x180030755  test    edx, edx
0x180030757  jnz     short loc_180030768
0x180030759  mov     rdx, [rcx+8]
0x18003075d  call    ?PickSize@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(unsigned __int64)
0x180030762  mov     edi, eax
0x180030764  mov     [rsp+58h+arg_8], eax
0x180030768  lea     rsi, [rbx+10h]
0x18003076c  mov     [rsp+58h+var_38], rsi
0x180030771  cmp     edi, [rsi]
0x180030773  jz      loc_180030857
0x180030779  mov     [rsp+58h+arg_10], 0
0x180030782  cmp     qword ptr [rbx], 0
0x180030786  jnz     short loc_18003079A
0x180030788  xor     r8d, r8d
0x18003078b  mov     edx, edi
0x18003078d  mov     rcx, rbx
0x180030790  call    ?InitHashTable@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::InitHashTable(uint,bool)
0x180030795  jmp     loc_180030857
0x18003079a  mov     r15d, edi
0x18003079d  mov     [rsp+58h+arg_18], r15
0x1800307a2  mov     eax, 8
0x1800307a7  mul     r15
0x1800307aa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800307b1  cmovb   rax, rcx
0x1800307b5  mov     dl, 1
0x1800307b7  mov     rcx, rax
0x1800307ba  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800307c0  mov     r14, rax
0x1800307c3  mov     [rsp+58h+arg_10], rax
0x1800307c8  jmp     short loc_1800307E2
0x1800307ca  mov     rbx, [rsp+58h+arg_0]
0x1800307cf  mov     edi, [rsp+58h+arg_8]
0x1800307d3  mov     r14, [rsp+58h+arg_10]
0x1800307d8  mov     r15, [rsp+58h+arg_18]
0x1800307dd  mov     rsi, [rsp+58h+var_38]
0x1800307e2  test    r14, r14
0x1800307e5  jnz     short loc_1800307F3
0x1800307e7  mov     ecx, 8007000Eh
0x1800307ec  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1800307f2  int     3; Trap to Debugger
0x1800307f3  lea     r8, ds:0[r15*8]; Size
0x1800307fb  xor     edx, edx; Val
0x1800307fd  mov     rcx, r14; void *
0x180030800  call    memset_0
0x180030805  xor     r9d, r9d
0x180030808  cmp     [rsi], r9d
0x18003080b  jbe     short loc_180030841
0x18003080d  mov     rax, [rbx]
0x180030810  mov     r10, [rax+r9*8]
0x180030814  test    r10, r10
0x180030817  jz      short loc_180030839
0x180030819  mov     r8, [r10+10h]
0x18003081d  xor     edx, edx
0x18003081f  mov     eax, [r10+18h]
0x180030823  div     edi
0x180030825  mov     rax, [r14+rdx*8]
0x180030829  mov     [r10+10h], rax
0x18003082d  mov     [r14+rdx*8], r10
0x180030831  mov     r10, r8
0x180030834  test    r8, r8
0x180030837  jnz     short loc_180030819
0x180030839  inc     r9d
0x18003083c  cmp     r9d, [rsi]
0x18003083f  jb      short loc_18003080D
0x180030841  mov     rcx, [rbx]
0x180030844  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18003084a  mov     [rbx], r14
0x18003084d  mov     [rsi], edi
0x18003084f  mov     rcx, rbx
0x180030852  call    ?UpdateRehashThresholds@?$CAtlMap@PEBUIUnknown@@V?$CComQIPtr@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@ATL@@V?$CElementTraits@PEBUIUnknown@@@3@V?$CComQIPtrElementTraits@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@3@@ATL@@AEAAXXZ; ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(void)
0x180030857  add     rsp, 30h
0x18003085b  pop     r15
0x18003085d  pop     r14
0x18003085f  pop     rdi
0x180030860  pop     rsi
0x180030861  pop     rbx
0x180030862  retn
```

# ATL::CAtlMap<uint,ModularWindowCommand,ATL::CElementTraits<uint>,ATL::CElementTraits<ModularWindowCommand>>::Rehash(uint)

- ea: `0x18003285c`
- end: `0x180032983`
- name: `?Rehash@?$CAtlMap@IW4ModularWindowCommand@@V?$CElementTraits@I@ATL@@V?$CElementTraits@W4ModularWindowCommand@@@3@@ATL@@QEAAXI@Z`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800203b4`
- `0x1800327f4`

## callees

- `0x18002078c`
- `0x18002fa28`
- `0x18002fee8`
- `0x18003285c`
- `0x180040264`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180032964`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180032964`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800328da`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800328da`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18003290c`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18003290c`

## pseudocode

```c
void __fastcall ATL::CAtlMap<unsigned int,enum ModularWindowCommand,ATL::CElementTraits<unsigned int>,ATL::CElementTraits<enum ModularWindowCommand>>::Rehash(
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
            v12 = *(_QWORD *)(v11 + 8);
            v9 = *(_DWORD *)(v11 + 16) % v3;
            *(_QWORD *)(v11 + 8) = v8[v9];
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
0x18003285c  mov     [rsp+arg_8], edx
0x180032860  mov     [rsp+arg_0], rcx
0x180032865  push    rbx
0x180032866  push    rsi
0x180032867  push    rdi
0x180032868  push    r14
0x18003286a  push    r15
0x18003286c  sub     rsp, 30h
0x180032870  mov     edi, edx
0x180032872  mov     rbx, rcx
0x180032875  test    edx, edx
0x180032877  jnz     short loc_180032888
0x180032879  mov     rdx, [rcx+8]
0x18003287d  call    ?PickSize@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@AEBAI_K@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::PickSize(unsigned __int64)
0x180032882  mov     edi, eax
0x180032884  mov     [rsp+58h+arg_8], eax
0x180032888  lea     rsi, [rbx+10h]
0x18003288c  mov     [rsp+58h+var_38], rsi
0x180032891  cmp     edi, [rsi]
0x180032893  jz      loc_180032977
0x180032899  mov     [rsp+58h+arg_10], 0
0x1800328a2  cmp     qword ptr [rbx], 0
0x1800328a6  jnz     short loc_1800328BA
0x1800328a8  xor     r8d, r8d
0x1800328ab  mov     edx, edi
0x1800328ad  mov     rcx, rbx
0x1800328b0  call    ?InitHashTable@?$CAtlMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::InitHashTable(uint,bool)
0x1800328b5  jmp     loc_180032977
0x1800328ba  mov     r15d, edi
0x1800328bd  mov     [rsp+58h+arg_18], r15
0x1800328c2  mov     eax, 8
0x1800328c7  mul     r15
0x1800328ca  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800328d1  cmovb   rax, rcx
0x1800328d5  mov     dl, 1
0x1800328d7  mov     rcx, rax
0x1800328da  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800328e0  mov     r14, rax
0x1800328e3  mov     [rsp+58h+arg_10], rax
0x1800328e8  jmp     short loc_180032902
0x1800328ea  mov     rbx, [rsp+58h+arg_0]
0x1800328ef  mov     edi, [rsp+58h+arg_8]
0x1800328f3  mov     r14, [rsp+58h+arg_10]
0x1800328f8  mov     r15, [rsp+58h+arg_18]
0x1800328fd  mov     rsi, [rsp+58h+var_38]
0x180032902  test    r14, r14
0x180032905  jnz     short loc_180032913
0x180032907  mov     ecx, 8007000Eh
0x18003290c  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180032912  int     3; Trap to Debugger
0x180032913  lea     r8, ds:0[r15*8]; Size
0x18003291b  xor     edx, edx; Val
0x18003291d  mov     rcx, r14; void *
0x180032920  call    memset_0
0x180032925  xor     r9d, r9d
0x180032928  cmp     [rsi], r9d
0x18003292b  jbe     short loc_180032961
0x18003292d  mov     rax, [rbx]
0x180032930  mov     r10, [rax+r9*8]
0x180032934  test    r10, r10
0x180032937  jz      short loc_180032959
0x180032939  mov     r8, [r10+8]
0x18003293d  xor     edx, edx
0x18003293f  mov     eax, [r10+10h]
0x180032943  div     edi
0x180032945  mov     rax, [r14+rdx*8]
0x180032949  mov     [r10+8], rax
0x18003294d  mov     [r14+rdx*8], r10
0x180032951  mov     r10, r8
0x180032954  test    r8, r8
0x180032957  jnz     short loc_180032939
0x180032959  inc     r9d
0x18003295c  cmp     r9d, [rsi]
0x18003295f  jb      short loc_18003292D
0x180032961  mov     rcx, [rbx]
0x180032964  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18003296a  mov     [rbx], r14
0x18003296d  mov     [rsi], edi
0x18003296f  mov     rcx, rbx
0x180032972  call    ?UpdateRehashThresholds@?$CAtlMap@PEBUIUnknown@@V?$CComQIPtr@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@ATL@@V?$CElementTraits@PEBUIUnknown@@@3@V?$CComQIPtrElementTraits@VIEaselPhodeoDisplayState@@$1?_GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444@@3U__s_GUID@@B@3@@ATL@@AEAAXXZ; ATL::CAtlMap<IUnknown const *,ATL::CComQIPtr<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>,ATL::CElementTraits<IUnknown const *>,ATL::CComQIPtrElementTraits<IEaselPhodeoDisplayState,&__s_GUID const _GUID_401107d5_c2d0_4a7f_941a_bf7ebc060444>>::UpdateRehashThresholds(void)
0x180032977  add     rsp, 30h
0x18003297b  pop     r15
0x18003297d  pop     r14
0x18003297f  pop     rdi
0x180032980  pop     rsi
0x180032981  pop     rbx
0x180032982  retn
```

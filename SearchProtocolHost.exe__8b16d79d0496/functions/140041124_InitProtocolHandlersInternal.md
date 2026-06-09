# InitProtocolHandlersInternal

- ea: `0x140041124`
- end: `0x1400412c3`
- name: `InitProtocolHandlersInternal`
- size: `415`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400412cc`
- `0x140041410`

## callees

- `0x1400055b4`
- `0x14000e8e8`
- `0x140028044`
- `0x140032e2c`
- `0x14003ed38`
- `0x14003eda4`
- `0x14003f934`
- `0x140041124`
- `0x14004425c`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14004125e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14004125e`

## string_xrefs

- `0x140041171`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrutil.cxx`
- `0x1400411db`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrutil.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitProtocolHandlersInternal(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  std::_Ref_count_base *v4; // rcx
  char *v6; // rbx
  int v7; // eax
  char *v8; // rax
  char *v9; // rbx
  __int64 **v10; // rdx
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  char v14[32]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char *v16; // [rsp+68h] [rbp+10h] BYREF

  if ( !g_pphs )
  {
    v16 = 0;
    v2 = ATL::CComObject<CProtocolHandlerSite>::CreateInstance(&v16);
    if ( v2 < 0 )
    {
      v3 = 67;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrutil.cxx",
        (const char *)(unsigned int)v2,
        v13);
LABEL_5:
      v4 = *(std::_Ref_count_base **)(a1 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      return (unsigned int)v2;
    }
    v6 = v16;
    if ( v16 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    v7 = (**(__int64 (__fastcall ***)(char *, GUID *, struct IProtocolHandlerSite **))v6)(
           v6,
           &GUID_0b63e385_9ccc_11d0_bcdb_00805fccce04,
           &g_pphs);
    v2 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrutil.cxx",
        (const char *)(unsigned int)v7,
        v13);
      TComPointer<CFileStream>::~TComPointer<CFileStream>(&v16);
      goto LABEL_5;
    }
    TComPointer<CFileStream>::~TComPointer<CFileStream>(&v16);
  }
  if ( !Block )
  {
    v8 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    v16 = v8;
    if ( v8 )
    {
      CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>::CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>(
        (_DWORD)v8,
        (unsigned int)PNameStringHash,
        (unsigned int)PSubStringHash,
        17,
        0,
        3);
      v9[96] = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 56));
    }
    else
    {
      v9 = 0;
    }
    Block = (CProtocolHandlers *)v9;
    if ( !v9 )
    {
      v2 = -2147024882;
      v3 = 76;
      goto LABEL_4;
    }
  }
  v10 = (__int64 **)std::shared_ptr<text_filter_semantic_provider>::shared_ptr<text_filter_semantic_provider>(v14, a1);
  v2 = CProtocolHandlers::Init(v11, v10);
  if ( v2 < 0 )
  {
    v3 = 79;
    goto LABEL_4;
  }
  v12 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  return 0;
}

```

## disassembly

```asm
0x140041124  mov     rax, rsp
0x140041127  mov     [rax+8], rcx
0x14004112b  push    rdi
0x14004112c  sub     rsp, 50h
0x140041130  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x140041138  mov     [rax+18h], rbx
0x14004113c  mov     rdi, rcx
0x14004113f  cmp     cs:?g_pphs@@3PEAUIProtocolHandlerSite@@EA, 0; IProtocolHandlerSite * g_pphs
0x140041147  jnz     loc_140041202
0x14004114d  mov     qword ptr [rax+10h], 0
0x140041155  lea     rcx, [rax+10h]
0x140041159  call    ?CreateInstance@?$CComObject@VCProtocolHandlerSite@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CProtocolHandlerSite>::CreateInstance(ATL::CComObject<CProtocolHandlerSite> * *)
0x14004115e  mov     ebx, eax
0x140041160  test    eax, eax
0x140041162  jns     short loc_140041193
0x140041164  mov     edx, 43h ; 'C'; void *
0x140041169  mov     rcx, [rsp+58h]; this
0x14004116e  mov     r9d, ebx; char *
0x140041171  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140041178  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004117d  nop
0x14004117e  mov     rcx, [rdi+8]; this
0x140041182  test    rcx, rcx
0x140041185  jz      short loc_14004118C
0x140041187  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14004118c  mov     eax, ebx
0x14004118e  jmp     loc_1400412B8
0x140041193  mov     rbx, [rsp+58h+arg_8]
0x140041198  mov     [rsp+58h+arg_8], rbx
0x14004119d  test    rbx, rbx
0x1400411a0  jz      short loc_1400411B1
0x1400411a2  mov     rax, [rbx]
0x1400411a5  mov     rcx, rbx
0x1400411a8  mov     rax, [rax+8]
0x1400411ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400411b1  mov     rax, [rbx]
0x1400411b4  lea     r8, ?g_pphs@@3PEAUIProtocolHandlerSite@@EA; IProtocolHandlerSite * g_pphs
0x1400411bb  lea     rdx, _GUID_0b63e385_9ccc_11d0_bcdb_00805fccce04
0x1400411c2  mov     rcx, rbx
0x1400411c5  mov     rax, [rax]
0x1400411c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400411cd  mov     ebx, eax
0x1400411cf  test    eax, eax
0x1400411d1  jns     short loc_1400411F8
0x1400411d3  mov     rcx, [rsp+58h]; this
0x1400411d8  mov     r9d, eax; char *
0x1400411db  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400411e2  mov     edx, 46h ; 'F'; void *
0x1400411e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400411ec  lea     rcx, [rsp+58h+arg_8]
0x1400411f1  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x1400411f6  jmp     short loc_14004117E
0x1400411f8  lea     rcx, [rsp+58h+arg_8]
0x1400411fd  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x140041202  cmp     cs:Block, 0
0x14004120a  jnz     short loc_140041283
0x14004120c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140041213  mov     ecx, 68h ; 'h'; unsigned __int64
0x140041218  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14004121d  mov     rbx, rax
0x140041220  mov     [rsp+58h+arg_8], rax
0x140041225  test    rax, rax
0x140041228  jz      short loc_140041266
0x14004122a  mov     [rsp+58h+var_30], 3
0x140041232  mov     [rsp+58h+var_38], 0
0x14004123a  mov     r9d, 11h
0x140041240  lea     r8, ?PSubStringHash@@YAKPEBVCLMSubStr@@@Z; PSubStringHash(CLMSubStr const *)
0x140041247  lea     rdx, ?PNameStringHash@@YAKPEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; PNameStringHash(TLMString<32,32,1024> const *)
0x14004124e  mov     rcx, rax
0x140041251  call    ??0?$CTPtrKPtrHashMap@V?$TLMString@$0CA@$0CA@$0EAA@@@VCProtocolHandler@@VCLMSubStr@@@@QEAA@P6AKPEBV?$TLMString@$0CA@$0CA@$0EAA@@@@ZP6AKPEBVCLMSubStr@@@ZKKK@Z; CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>::CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>(ulong (*)(TLMString<32,32,1024> const *),ulong (*)(CLMSubStr const *),ulong,ulong,ulong)
0x140041256  lea     rcx, [rbx+38h]; lpCriticalSection
0x14004125a  mov     byte ptr [rcx+28h], 0
0x14004125e  call    cs:__imp_InitializeCriticalSection
0x140041264  jmp     short loc_140041268
0x140041266  xor     ebx, ebx
0x140041268  mov     cs:Block, rbx
0x14004126f  test    rbx, rbx
0x140041272  jnz     short loc_140041283
0x140041274  mov     ebx, 8007000Eh
0x140041279  mov     edx, 4Ch ; 'L'
0x14004127e  jmp     loc_140041169
0x140041283  mov     rdx, rdi
0x140041286  lea     rcx, [rsp+58h+var_20]
0x14004128b  call    ??0?$shared_ptr@Utext_filter_semantic_provider@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<text_filter_semantic_provider>::shared_ptr<text_filter_semantic_provider>(std::shared_ptr<text_filter_semantic_provider> const &)
0x140041290  mov     rdx, rax
0x140041293  call    ?Init@CProtocolHandlers@@QEAAJV?$shared_ptr@UIProtocolHandlerConfigurationStore@@@std@@@Z; CProtocolHandlers::Init(std::shared_ptr<IProtocolHandlerConfigurationStore>)
0x140041298  mov     ebx, eax
0x14004129a  test    eax, eax
0x14004129c  jns     short loc_1400412A8
0x14004129e  mov     edx, 4Fh ; 'O'
0x1400412a3  jmp     loc_140041169
0x1400412a8  mov     rcx, [rdi+8]; this
0x1400412ac  test    rcx, rcx
0x1400412af  jz      short loc_1400412B6
0x1400412b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400412b6  xor     eax, eax
0x1400412b8  mov     rbx, [rsp+58h+arg_10]
0x1400412bd  add     rsp, 50h
0x1400412c1  pop     rdi
0x1400412c2  retn
```

# std::use_facet<std::numpunct<wchar_t>>(std::locale const &)

- ea: `0x18000b050`
- end: `0x18000b18d`
- name: `??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c1a0`
- `0x18000e050`
- `0x18000eee8`
- `0x18000fe64`
- `0x180012884`
- `0x180013898`
- `0x180018110`
- `0x18001bdd0`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x18000b050`
- `0x18000d5e4`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x18000b175`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x18000b175`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::numpunct<wchar_t>>(__int64 *a1)
{
  struct std::_Facet_base *v2; // rbx
  unsigned __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rsi
  struct std::_Facet_base *v6; // rcx
  struct std::locale::_Locimp *v8; // rax
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF
  char v10; // [rsp+60h] [rbp+8h] BYREF
  char v11; // [rsp+68h] [rbp+10h] BYREF
  struct std::_Facet_base *v12; // [rsp+70h] [rbp+18h] BYREF

  std::_Lockit::_Lockit((std::_Lockit *)&v11, 0);
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<wchar_t>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<wchar_t>>::_Psave;
  v3 = std::numpunct<wchar_t>::id;
  if ( !std::numpunct<wchar_t>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::numpunct<wchar_t>::id )
      std::numpunct<wchar_t>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::numpunct<wchar_t>::id;
  }
  v4 = *a1;
  v5 = 8 * v3;
  if ( v3 >= *(_QWORD *)(*a1 + 24) )
  {
    v6 = 0;
  }
  else
  {
    v6 = *(struct std::_Facet_base **)(v5 + *(_QWORD *)(v4 + 16));
    if ( v6 )
    {
LABEL_7:
      v2 = v6;
      goto LABEL_8;
    }
  }
  if ( *(_BYTE *)(v4 + 36) )
  {
    v8 = std::locale::_Getgloballocale();
    if ( v3 >= *((_QWORD *)v8 + 3) )
      v6 = 0;
    else
      v6 = *(struct std::_Facet_base **)(v5 + *((_QWORD *)v8 + 2));
  }
  if ( v6 )
    goto LABEL_7;
  if ( !v2 )
  {
    if ( std::numpunct<wchar_t>::_Getcat(&v12, a1) == -1 )
    {
      bad_cast::bad_cast((bad_cast *)pExceptionObject, "bad cast");
      throw (bad_cast *)pExceptionObject;
    }
    v2 = v12;
    std::_Facetptr<std::numpunct<wchar_t>>::_Psave = (__int64)v12;
    (*(void (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v12 + 8LL))(v12);
    std::_Facet_Register(v2);
  }
LABEL_8:
  std::_Lockit::~_Lockit((std::_Lockit *)&v11);
  return v2;
}

```

## disassembly

```asm
0x18000b050  push    rsi
0x18000b052  push    rdi
0x18000b053  push    r14
0x18000b055  sub     rsp, 40h
0x18000b059  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000b062  mov     [rsp+58h+arg_18], rbx
0x18000b067  mov     r14, rcx
0x18000b06a  xor     edx, edx; int
0x18000b06c  lea     rcx, [rsp+58h+arg_8]; this
0x18000b071  call    ??0_Lockit@std@@QEAA@H@Z
0x18000b076  nop
0x18000b077  mov     rbx, cs:?_Psave@?$_Facetptr@V?$numpunct@_W@std@@@std@@2PEBVfacet@locale@2@EB
0x18000b07e  mov     [rsp+58h+arg_10], rbx
0x18000b083  mov     rdi, cs:?id@?$numpunct@_W@std@@2V0locale@2@A
0x18000b08a  test    rdi, rdi
0x18000b08d  jnz     short loc_18000B0CC
0x18000b08f  xor     edx, edx; int
0x18000b091  lea     rcx, [rsp+58h+arg_0]; this
0x18000b096  call    ??0_Lockit@std@@QEAA@H@Z
0x18000b09b  cmp     cs:?id@?$numpunct@_W@std@@2V0locale@2@A, rdi
0x18000b0a2  jnz     short loc_18000B0BB
0x18000b0a4  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA
0x18000b0aa  inc     eax
0x18000b0ac  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax
0x18000b0b2  cdqe
0x18000b0b4  mov     cs:?id@?$numpunct@_W@std@@2V0locale@2@A, rax
0x18000b0bb  lea     rcx, [rsp+58h+arg_0]; this
0x18000b0c0  call    ??1_Lockit@std@@QEAA@XZ
0x18000b0c5  mov     rdi, cs:?id@?$numpunct@_W@std@@2V0locale@2@A
0x18000b0cc  mov     rdx, [r14]
0x18000b0cf  lea     rsi, ds:0[rdi*8]
0x18000b0d7  cmp     rdi, [rdx+18h]
0x18000b0db  jnb     short loc_18000B108
0x18000b0dd  mov     rax, [rdx+10h]
0x18000b0e1  mov     rcx, [rsi+rax]
0x18000b0e5  test    rcx, rcx
0x18000b0e8  jz      short loc_18000B10A
0x18000b0ea  mov     rbx, rcx
0x18000b0ed  lea     rcx, [rsp+58h+arg_8]; this
0x18000b0f2  call    ??1_Lockit@std@@QEAA@XZ
0x18000b0f7  mov     rax, rbx
0x18000b0fa  mov     rbx, [rsp+58h+arg_18]
0x18000b0ff  add     rsp, 40h
0x18000b103  pop     r14
0x18000b105  pop     rdi
0x18000b106  pop     rsi
0x18000b107  retn
0x18000b108  xor     ecx, ecx
0x18000b10a  cmp     byte ptr [rdx+24h], 0
0x18000b10e  jz      short loc_18000B127
0x18000b110  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ
0x18000b115  cmp     rdi, [rax+18h]
0x18000b119  jnb     short loc_18000B125
0x18000b11b  mov     rax, [rax+10h]
0x18000b11f  mov     rcx, [rsi+rax]
0x18000b123  jmp     short loc_18000B127
0x18000b125  xor     ecx, ecx
0x18000b127  test    rcx, rcx
0x18000b12a  jnz     short loc_18000B0EA
0x18000b12c  test    rbx, rbx
0x18000b12f  jnz     short loc_18000B0ED
0x18000b131  mov     rdx, r14
0x18000b134  lea     rcx, [rsp+58h+arg_10]
0x18000b139  call    ?_Getcat@?$numpunct@_W@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z
0x18000b13e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b142  jz      short loc_18000B169
0x18000b144  mov     rbx, [rsp+58h+arg_10]
0x18000b149  mov     cs:?_Psave@?$_Facetptr@V?$numpunct@_W@std@@@std@@2PEBVfacet@locale@2@EB, rbx
0x18000b150  mov     rax, [rbx]
0x18000b153  mov     rcx, rbx
0x18000b156  mov     rax, [rax+8]
0x18000b15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b15f  mov     rcx, rbx; struct std::_Facet_base *
0x18000b162  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z
0x18000b167  jmp     short loc_18000B0ED
0x18000b169  lea     rdx, aBadCast
0x18000b170  lea     rcx, [rsp+58h+pExceptionObject]
0x18000b175  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z
0x18000b17b  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x18000b182  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000b187  call    _CxxThrowException_0
```

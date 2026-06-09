# std::use_facet<std::numpunct<char>>(std::locale const &)

- ea: `0x18000314c`
- end: `0x180003289`
- name: `??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x1800034a4`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x180005b54`
- `0x1800060cc`
- `0x1800074b0`
- `0x180007f20`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x18000314c`
- `0x180003c20`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180003271`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180003271`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::numpunct<char>>(__int64 *a1)
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
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<char>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<char>>::_Psave;
  v3 = std::numpunct<char>::id;
  if ( !std::numpunct<char>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::numpunct<char>::id )
      std::numpunct<char>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::numpunct<char>::id;
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
    if ( std::numpunct<char>::_Getcat(&v12, a1) == -1 )
    {
      bad_cast::bad_cast((bad_cast *)pExceptionObject, "bad cast");
      throw (bad_cast *)pExceptionObject;
    }
    v2 = v12;
    std::_Facetptr<std::numpunct<char>>::_Psave = (__int64)v12;
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
0x18000314c  push    rsi
0x18000314e  push    rdi
0x18000314f  push    r14
0x180003151  sub     rsp, 40h
0x180003155  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000315e  mov     [rsp+58h+arg_18], rbx
0x180003163  mov     r14, rcx
0x180003166  xor     edx, edx; int
0x180003168  lea     rcx, [rsp+58h+arg_8]; this
0x18000316d  call    ??0_Lockit@std@@QEAA@H@Z
0x180003172  nop
0x180003173  mov     rbx, cs:?_Psave@?$_Facetptr@V?$numpunct@D@std@@@std@@2PEBVfacet@locale@2@EB
0x18000317a  mov     [rsp+58h+arg_10], rbx
0x18000317f  mov     rdi, cs:?id@?$numpunct@D@std@@2V0locale@2@A
0x180003186  test    rdi, rdi
0x180003189  jnz     short loc_1800031C8
0x18000318b  xor     edx, edx; int
0x18000318d  lea     rcx, [rsp+58h+arg_0]; this
0x180003192  call    ??0_Lockit@std@@QEAA@H@Z
0x180003197  cmp     cs:?id@?$numpunct@D@std@@2V0locale@2@A, rdi
0x18000319e  jnz     short loc_1800031B7
0x1800031a0  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA
0x1800031a6  inc     eax
0x1800031a8  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax
0x1800031ae  cdqe
0x1800031b0  mov     cs:?id@?$numpunct@D@std@@2V0locale@2@A, rax
0x1800031b7  lea     rcx, [rsp+58h+arg_0]; this
0x1800031bc  call    ??1_Lockit@std@@QEAA@XZ
0x1800031c1  mov     rdi, cs:?id@?$numpunct@D@std@@2V0locale@2@A
0x1800031c8  mov     rdx, [r14]
0x1800031cb  lea     rsi, ds:0[rdi*8]
0x1800031d3  cmp     rdi, [rdx+18h]
0x1800031d7  jnb     short loc_180003204
0x1800031d9  mov     rax, [rdx+10h]
0x1800031dd  mov     rcx, [rsi+rax]
0x1800031e1  test    rcx, rcx
0x1800031e4  jz      short loc_180003206
0x1800031e6  mov     rbx, rcx
0x1800031e9  lea     rcx, [rsp+58h+arg_8]; this
0x1800031ee  call    ??1_Lockit@std@@QEAA@XZ
0x1800031f3  mov     rax, rbx
0x1800031f6  mov     rbx, [rsp+58h+arg_18]
0x1800031fb  add     rsp, 40h
0x1800031ff  pop     r14
0x180003201  pop     rdi
0x180003202  pop     rsi
0x180003203  retn
0x180003204  xor     ecx, ecx
0x180003206  cmp     byte ptr [rdx+24h], 0
0x18000320a  jz      short loc_180003223
0x18000320c  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ
0x180003211  cmp     rdi, [rax+18h]
0x180003215  jnb     short loc_180003221
0x180003217  mov     rax, [rax+10h]
0x18000321b  mov     rcx, [rsi+rax]
0x18000321f  jmp     short loc_180003223
0x180003221  xor     ecx, ecx
0x180003223  test    rcx, rcx
0x180003226  jnz     short loc_1800031E6
0x180003228  test    rbx, rbx
0x18000322b  jnz     short loc_1800031E9
0x18000322d  mov     rdx, r14
0x180003230  lea     rcx, [rsp+58h+arg_10]
0x180003235  call    ?_Getcat@?$numpunct@D@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z
0x18000323a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000323e  jz      short loc_180003265
0x180003240  mov     rbx, [rsp+58h+arg_10]
0x180003245  mov     cs:?_Psave@?$_Facetptr@V?$numpunct@D@std@@@std@@2PEBVfacet@locale@2@EB, rbx
0x18000324c  mov     rax, [rbx]
0x18000324f  mov     rcx, rbx
0x180003252  mov     rax, [rax+8]
0x180003256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325b  mov     rcx, rbx; struct std::_Facet_base *
0x18000325e  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z
0x180003263  jmp     short loc_1800031E9
0x180003265  lea     rdx, aBadCast
0x18000326c  lea     rcx, [rsp+58h+pExceptionObject]
0x180003271  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z
0x180003277  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x18000327e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180003283  call    _CxxThrowException_0
```

# std::use_facet<std::ctype<wchar_t>>(std::locale const &)

- ea: `0x180009c10`
- end: `0x180009d4d`
- name: `??$use_facet@V?$ctype@_W@std@@@std@@YAAEBV?$ctype@_W@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c1a0`
- `0x18000e050`
- `0x18000eee8`
- `0x18000f850`
- `0x18000fe64`
- `0x18001108c`
- `0x180012884`
- `0x180013898`
- `0x180018890`
- `0x180019340`
- `0x180019b00`
- `0x180019e30`
- `0x18001a900`
- `0x18001ab30`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x180009c10`
- `0x18000c958`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180009d35`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180009d35`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::ctype<wchar_t>>(__int64 *a1)
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
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<wchar_t>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<wchar_t>>::_Psave;
  v3 = std::ctype<wchar_t>::id;
  if ( !std::ctype<wchar_t>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::ctype<wchar_t>::id )
      std::ctype<wchar_t>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::ctype<wchar_t>::id;
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
    if ( std::ctype<wchar_t>::_Getcat(&v12, a1) == -1 )
    {
      bad_cast::bad_cast((bad_cast *)pExceptionObject, "bad cast");
      throw (bad_cast *)pExceptionObject;
    }
    v2 = v12;
    std::_Facetptr<std::ctype<wchar_t>>::_Psave = (__int64)v12;
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
0x180009c10  push    rsi
0x180009c12  push    rdi
0x180009c13  push    r14
0x180009c15  sub     rsp, 40h
0x180009c19  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180009c22  mov     [rsp+58h+arg_18], rbx
0x180009c27  mov     r14, rcx
0x180009c2a  xor     edx, edx; int
0x180009c2c  lea     rcx, [rsp+58h+arg_8]; this
0x180009c31  call    ??0_Lockit@std@@QEAA@H@Z
0x180009c36  nop
0x180009c37  mov     rbx, cs:?_Psave@?$_Facetptr@V?$ctype@_W@std@@@std@@2PEBVfacet@locale@2@EB
0x180009c3e  mov     [rsp+58h+arg_10], rbx
0x180009c43  mov     rdi, cs:?id@?$ctype@_W@std@@2V0locale@2@A
0x180009c4a  test    rdi, rdi
0x180009c4d  jnz     short loc_180009C8C
0x180009c4f  xor     edx, edx; int
0x180009c51  lea     rcx, [rsp+58h+arg_0]; this
0x180009c56  call    ??0_Lockit@std@@QEAA@H@Z
0x180009c5b  cmp     cs:?id@?$ctype@_W@std@@2V0locale@2@A, rdi
0x180009c62  jnz     short loc_180009C7B
0x180009c64  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA
0x180009c6a  inc     eax
0x180009c6c  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax
0x180009c72  cdqe
0x180009c74  mov     cs:?id@?$ctype@_W@std@@2V0locale@2@A, rax
0x180009c7b  lea     rcx, [rsp+58h+arg_0]; this
0x180009c80  call    ??1_Lockit@std@@QEAA@XZ
0x180009c85  mov     rdi, cs:?id@?$ctype@_W@std@@2V0locale@2@A
0x180009c8c  mov     rdx, [r14]
0x180009c8f  lea     rsi, ds:0[rdi*8]
0x180009c97  cmp     rdi, [rdx+18h]
0x180009c9b  jnb     short loc_180009CC8
0x180009c9d  mov     rax, [rdx+10h]
0x180009ca1  mov     rcx, [rsi+rax]
0x180009ca5  test    rcx, rcx
0x180009ca8  jz      short loc_180009CCA
0x180009caa  mov     rbx, rcx
0x180009cad  lea     rcx, [rsp+58h+arg_8]; this
0x180009cb2  call    ??1_Lockit@std@@QEAA@XZ
0x180009cb7  mov     rax, rbx
0x180009cba  mov     rbx, [rsp+58h+arg_18]
0x180009cbf  add     rsp, 40h
0x180009cc3  pop     r14
0x180009cc5  pop     rdi
0x180009cc6  pop     rsi
0x180009cc7  retn
0x180009cc8  xor     ecx, ecx
0x180009cca  cmp     byte ptr [rdx+24h], 0
0x180009cce  jz      short loc_180009CE7
0x180009cd0  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ
0x180009cd5  cmp     rdi, [rax+18h]
0x180009cd9  jnb     short loc_180009CE5
0x180009cdb  mov     rax, [rax+10h]
0x180009cdf  mov     rcx, [rsi+rax]
0x180009ce3  jmp     short loc_180009CE7
0x180009ce5  xor     ecx, ecx
0x180009ce7  test    rcx, rcx
0x180009cea  jnz     short loc_180009CAA
0x180009cec  test    rbx, rbx
0x180009cef  jnz     short loc_180009CAD
0x180009cf1  mov     rdx, r14
0x180009cf4  lea     rcx, [rsp+58h+arg_10]
0x180009cf9  call    ?_Getcat@?$ctype@_W@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z
0x180009cfe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009d02  jz      short loc_180009D29
0x180009d04  mov     rbx, [rsp+58h+arg_10]
0x180009d09  mov     cs:?_Psave@?$_Facetptr@V?$ctype@_W@std@@@std@@2PEBVfacet@locale@2@EB, rbx
0x180009d10  mov     rax, [rbx]
0x180009d13  mov     rcx, rbx
0x180009d16  mov     rax, [rax+8]
0x180009d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d1f  mov     rcx, rbx; struct std::_Facet_base *
0x180009d22  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z
0x180009d27  jmp     short loc_180009CAD
0x180009d29  lea     rdx, aBadCast
0x180009d30  lea     rcx, [rsp+58h+pExceptionObject]
0x180009d35  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z
0x180009d3b  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x180009d42  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009d47  call    _CxxThrowException_0
```

# std::use_facet<std::ctype<ushort>>(std::locale const &)

- ea: `0x180009acc`
- end: `0x180009c09`
- name: `??$use_facet@V?$ctype@G@std@@@std@@YAAEBV?$ctype@G@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x18000bd00`
- `0x18000d948`
- `0x18000e758`
- `0x18000f678`
- `0x18000fa28`
- `0x18001046c`
- `0x1800124d0`
- `0x180012c38`
- `0x180018390`
- `0x180018d90`
- `0x180019950`
- `0x180019d10`
- `0x18001a490`
- `0x18001a6c0`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x180009acc`
- `0x18000c958`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180009bf1`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180009bf1`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::ctype<unsigned short>>(__int64 *a1)
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
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<unsigned short>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<unsigned short>>::_Psave;
  v3 = std::ctype<unsigned short>::id;
  if ( !std::ctype<unsigned short>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::ctype<unsigned short>::id )
      std::ctype<unsigned short>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::ctype<unsigned short>::id;
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
    std::_Facetptr<std::ctype<unsigned short>>::_Psave = (__int64)v12;
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
0x180009acc  push    rsi
0x180009ace  push    rdi
0x180009acf  push    r14
0x180009ad1  sub     rsp, 40h
0x180009ad5  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180009ade  mov     [rsp+58h+arg_18], rbx
0x180009ae3  mov     r14, rcx
0x180009ae6  xor     edx, edx; int
0x180009ae8  lea     rcx, [rsp+58h+arg_8]; this
0x180009aed  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180009af2  nop
0x180009af3  mov     rbx, cs:?_Psave@?$_Facetptr@V?$ctype@G@std@@@std@@2PEBVfacet@locale@2@EB; std::locale::facet const * const std::_Facetptr<std::ctype<ushort>>::_Psave
0x180009afa  mov     [rsp+58h+arg_10], rbx
0x180009aff  mov     rdi, cs:?id@?$ctype@G@std@@2V0locale@2@A; std::locale::id std::ctype<ushort>::id
0x180009b06  test    rdi, rdi
0x180009b09  jnz     short loc_180009B48
0x180009b0b  xor     edx, edx; int
0x180009b0d  lea     rcx, [rsp+58h+arg_0]; this
0x180009b12  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180009b17  cmp     cs:?id@?$ctype@G@std@@2V0locale@2@A, rdi; std::locale::id std::ctype<ushort>::id
0x180009b1e  jnz     short loc_180009B37
0x180009b20  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA; int std::locale::id::_Id_cnt
0x180009b26  inc     eax
0x180009b28  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax; int std::locale::id::_Id_cnt
0x180009b2e  cdqe
0x180009b30  mov     cs:?id@?$ctype@G@std@@2V0locale@2@A, rax; std::locale::id std::ctype<ushort>::id
0x180009b37  lea     rcx, [rsp+58h+arg_0]; this
0x180009b3c  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180009b41  mov     rdi, cs:?id@?$ctype@G@std@@2V0locale@2@A; std::locale::id std::ctype<ushort>::id
0x180009b48  mov     rdx, [r14]
0x180009b4b  lea     rsi, ds:0[rdi*8]
0x180009b53  cmp     rdi, [rdx+18h]
0x180009b57  jnb     short loc_180009B84
0x180009b59  mov     rax, [rdx+10h]
0x180009b5d  mov     rcx, [rsi+rax]
0x180009b61  test    rcx, rcx
0x180009b64  jz      short loc_180009B86
0x180009b66  mov     rbx, rcx
0x180009b69  lea     rcx, [rsp+58h+arg_8]; this
0x180009b6e  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180009b73  mov     rax, rbx
0x180009b76  mov     rbx, [rsp+58h+arg_18]
0x180009b7b  add     rsp, 40h
0x180009b7f  pop     r14
0x180009b81  pop     rdi
0x180009b82  pop     rsi
0x180009b83  retn
0x180009b84  xor     ecx, ecx
0x180009b86  cmp     byte ptr [rdx+24h], 0
0x180009b8a  jz      short loc_180009BA3
0x180009b8c  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x180009b91  cmp     rdi, [rax+18h]
0x180009b95  jnb     short loc_180009BA1
0x180009b97  mov     rax, [rax+10h]
0x180009b9b  mov     rcx, [rsi+rax]
0x180009b9f  jmp     short loc_180009BA3
0x180009ba1  xor     ecx, ecx
0x180009ba3  test    rcx, rcx
0x180009ba6  jnz     short loc_180009B66
0x180009ba8  test    rbx, rbx
0x180009bab  jnz     short loc_180009B69
0x180009bad  mov     rdx, r14
0x180009bb0  lea     rcx, [rsp+58h+arg_10]
0x180009bb5  call    ?_Getcat@?$ctype@_W@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z; std::ctype<wchar_t>::_Getcat(std::locale::facet const * *,std::locale const *)
0x180009bba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009bbe  jz      short loc_180009BE5
0x180009bc0  mov     rbx, [rsp+58h+arg_10]
0x180009bc5  mov     cs:?_Psave@?$_Facetptr@V?$ctype@G@std@@@std@@2PEBVfacet@locale@2@EB, rbx; std::locale::facet const * const std::_Facetptr<std::ctype<ushort>>::_Psave
0x180009bcc  mov     rax, [rbx]
0x180009bcf  mov     rcx, rbx
0x180009bd2  mov     rax, [rax+8]
0x180009bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bdb  mov     rcx, rbx; struct std::_Facet_base *
0x180009bde  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z; std::_Facet_Register(std::_Facet_base *)
0x180009be3  jmp     short loc_180009B69
0x180009be5  lea     rdx, aBadCast; "bad cast"
0x180009bec  lea     rcx, [rsp+58h+pExceptionObject]
0x180009bf1  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z; bad_cast::bad_cast(char const *)
0x180009bf7  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x180009bfe  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180009c03  call    _CxxThrowException_0
```

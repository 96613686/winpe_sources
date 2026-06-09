# std::use_facet<std::numpunct<ushort>>(std::locale const &)

- ea: `0x18000af0c`
- end: `0x18000b049`
- name: `??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x18000bd00`
- `0x18000d948`
- `0x18000e758`
- `0x18000fa28`
- `0x1800124d0`
- `0x180012c38`
- `0x180017300`
- `0x18001b480`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x18000af0c`
- `0x18000d508`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x18000b031`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x18000b031`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::numpunct<unsigned short>>(__int64 *a1)
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
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<unsigned short>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::numpunct<unsigned short>>::_Psave;
  v3 = std::numpunct<unsigned short>::id;
  if ( !std::numpunct<unsigned short>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::numpunct<unsigned short>::id )
      std::numpunct<unsigned short>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::numpunct<unsigned short>::id;
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
    if ( std::numpunct<unsigned short>::_Getcat(&v12, a1) == -1 )
    {
      bad_cast::bad_cast((bad_cast *)pExceptionObject, "bad cast");
      throw (bad_cast *)pExceptionObject;
    }
    v2 = v12;
    std::_Facetptr<std::numpunct<unsigned short>>::_Psave = (__int64)v12;
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
0x18000af0c  push    rsi
0x18000af0e  push    rdi
0x18000af0f  push    r14
0x18000af11  sub     rsp, 40h
0x18000af15  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000af1e  mov     [rsp+58h+arg_18], rbx
0x18000af23  mov     r14, rcx
0x18000af26  xor     edx, edx; int
0x18000af28  lea     rcx, [rsp+58h+arg_8]; this
0x18000af2d  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x18000af32  nop
0x18000af33  mov     rbx, cs:?_Psave@?$_Facetptr@V?$numpunct@G@std@@@std@@2PEBVfacet@locale@2@EB; std::locale::facet const * const std::_Facetptr<std::numpunct<ushort>>::_Psave
0x18000af3a  mov     [rsp+58h+arg_10], rbx
0x18000af3f  mov     rdi, cs:?id@?$numpunct@G@std@@2V0locale@2@A; std::locale::id std::numpunct<ushort>::id
0x18000af46  test    rdi, rdi
0x18000af49  jnz     short loc_18000AF88
0x18000af4b  xor     edx, edx; int
0x18000af4d  lea     rcx, [rsp+58h+arg_0]; this
0x18000af52  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x18000af57  cmp     cs:?id@?$numpunct@G@std@@2V0locale@2@A, rdi; std::locale::id std::numpunct<ushort>::id
0x18000af5e  jnz     short loc_18000AF77
0x18000af60  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA; int std::locale::id::_Id_cnt
0x18000af66  inc     eax
0x18000af68  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax; int std::locale::id::_Id_cnt
0x18000af6e  cdqe
0x18000af70  mov     cs:?id@?$numpunct@G@std@@2V0locale@2@A, rax; std::locale::id std::numpunct<ushort>::id
0x18000af77  lea     rcx, [rsp+58h+arg_0]; this
0x18000af7c  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x18000af81  mov     rdi, cs:?id@?$numpunct@G@std@@2V0locale@2@A; std::locale::id std::numpunct<ushort>::id
0x18000af88  mov     rdx, [r14]
0x18000af8b  lea     rsi, ds:0[rdi*8]
0x18000af93  cmp     rdi, [rdx+18h]
0x18000af97  jnb     short loc_18000AFC4
0x18000af99  mov     rax, [rdx+10h]
0x18000af9d  mov     rcx, [rsi+rax]
0x18000afa1  test    rcx, rcx
0x18000afa4  jz      short loc_18000AFC6
0x18000afa6  mov     rbx, rcx
0x18000afa9  lea     rcx, [rsp+58h+arg_8]; this
0x18000afae  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x18000afb3  mov     rax, rbx
0x18000afb6  mov     rbx, [rsp+58h+arg_18]
0x18000afbb  add     rsp, 40h
0x18000afbf  pop     r14
0x18000afc1  pop     rdi
0x18000afc2  pop     rsi
0x18000afc3  retn
0x18000afc4  xor     ecx, ecx
0x18000afc6  cmp     byte ptr [rdx+24h], 0
0x18000afca  jz      short loc_18000AFE3
0x18000afcc  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ; std::locale::_Getgloballocale(void)
0x18000afd1  cmp     rdi, [rax+18h]
0x18000afd5  jnb     short loc_18000AFE1
0x18000afd7  mov     rax, [rax+10h]
0x18000afdb  mov     rcx, [rsi+rax]
0x18000afdf  jmp     short loc_18000AFE3
0x18000afe1  xor     ecx, ecx
0x18000afe3  test    rcx, rcx
0x18000afe6  jnz     short loc_18000AFA6
0x18000afe8  test    rbx, rbx
0x18000afeb  jnz     short loc_18000AFA9
0x18000afed  mov     rdx, r14
0x18000aff0  lea     rcx, [rsp+58h+arg_10]
0x18000aff5  call    ?_Getcat@?$numpunct@G@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z; std::numpunct<ushort>::_Getcat(std::locale::facet const * *,std::locale const *)
0x18000affa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000affe  jz      short loc_18000B025
0x18000b000  mov     rbx, [rsp+58h+arg_10]
0x18000b005  mov     cs:?_Psave@?$_Facetptr@V?$numpunct@G@std@@@std@@2PEBVfacet@locale@2@EB, rbx; std::locale::facet const * const std::_Facetptr<std::numpunct<ushort>>::_Psave
0x18000b00c  mov     rax, [rbx]
0x18000b00f  mov     rcx, rbx
0x18000b012  mov     rax, [rax+8]
0x18000b016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b01b  mov     rcx, rbx; struct std::_Facet_base *
0x18000b01e  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z; std::_Facet_Register(std::_Facet_base *)
0x18000b023  jmp     short loc_18000AFA9
0x18000b025  lea     rdx, aBadCast; "bad cast"
0x18000b02c  lea     rcx, [rsp+58h+pExceptionObject]
0x18000b031  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z; bad_cast::bad_cast(char const *)
0x18000b037  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x18000b03e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000b043  call    _CxxThrowException_0
```

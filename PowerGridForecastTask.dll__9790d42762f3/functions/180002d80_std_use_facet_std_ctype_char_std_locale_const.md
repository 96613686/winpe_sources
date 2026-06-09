# std::use_facet<std::ctype<char>>(std::locale const &)

- ea: `0x180002d80`
- end: `0x180002ebd`
- name: `??$use_facet@V?$ctype@D@std@@@std@@YAAEBV?$ctype@D@0@AEBVlocale@0@@Z`
- size: `317`
- prototype: `struct std::_Facet_base *__fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `8`
- tags: ``

## callers

- `0x1800034a4`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x180005b54`
- `0x1800060cc`
- `0x18001dee0`
- `0x18001e3c0`
- `0x180020830`
- `0x180020d30`
- `0x180021520`
- `0x1800217c0`
- `0x180021980`
- `0x180021ba0`

## callees

- `0x180002394`
- `0x18000241c`
- `0x18000254c`
- `0x18000258c`
- `0x180002d80`
- `0x1800039e0`
- `0x180026778`
- `0x180037010`

## import_xrefs

- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180002ea5`
- `msvcrt!??0bad_cast@@QEAA@PEBD@Z` at `0x180002ea5`

## pseudocode

```c
struct std::_Facet_base *__fastcall std::use_facet<std::ctype<char>>(__int64 *a1)
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
  v2 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<char>>::_Psave;
  v12 = (struct std::_Facet_base *)std::_Facetptr<std::ctype<char>>::_Psave;
  v3 = std::ctype<char>::id;
  if ( !std::ctype<char>::id )
  {
    std::_Lockit::_Lockit((std::_Lockit *)&v10, 0);
    if ( !std::ctype<char>::id )
      std::ctype<char>::id = ++std::locale::id::_Id_cnt;
    std::_Lockit::~_Lockit((std::_Lockit *)&v10);
    v3 = std::ctype<char>::id;
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
    if ( std::ctype<char>::_Getcat(&v12, a1) == -1 )
    {
      bad_cast::bad_cast((bad_cast *)pExceptionObject, "bad cast");
      throw (bad_cast *)pExceptionObject;
    }
    v2 = v12;
    std::_Facetptr<std::ctype<char>>::_Psave = (__int64)v12;
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
0x180002d80  push    rsi
0x180002d82  push    rdi
0x180002d83  push    r14
0x180002d85  sub     rsp, 40h
0x180002d89  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180002d92  mov     [rsp+58h+arg_18], rbx
0x180002d97  mov     r14, rcx
0x180002d9a  xor     edx, edx; int
0x180002d9c  lea     rcx, [rsp+58h+arg_8]; this
0x180002da1  call    ??0_Lockit@std@@QEAA@H@Z
0x180002da6  nop
0x180002da7  mov     rbx, cs:?_Psave@?$_Facetptr@V?$ctype@D@std@@@std@@2PEBVfacet@locale@2@EB
0x180002dae  mov     [rsp+58h+arg_10], rbx
0x180002db3  mov     rdi, cs:?id@?$ctype@D@std@@2V0locale@2@A
0x180002dba  test    rdi, rdi
0x180002dbd  jnz     short loc_180002DFC
0x180002dbf  xor     edx, edx; int
0x180002dc1  lea     rcx, [rsp+58h+arg_0]; this
0x180002dc6  call    ??0_Lockit@std@@QEAA@H@Z
0x180002dcb  cmp     cs:?id@?$ctype@D@std@@2V0locale@2@A, rdi
0x180002dd2  jnz     short loc_180002DEB
0x180002dd4  mov     eax, cs:?_Id_cnt@id@locale@std@@0HA
0x180002dda  inc     eax
0x180002ddc  mov     cs:?_Id_cnt@id@locale@std@@0HA, eax
0x180002de2  cdqe
0x180002de4  mov     cs:?id@?$ctype@D@std@@2V0locale@2@A, rax
0x180002deb  lea     rcx, [rsp+58h+arg_0]; this
0x180002df0  call    ??1_Lockit@std@@QEAA@XZ
0x180002df5  mov     rdi, cs:?id@?$ctype@D@std@@2V0locale@2@A
0x180002dfc  mov     rdx, [r14]
0x180002dff  lea     rsi, ds:0[rdi*8]
0x180002e07  cmp     rdi, [rdx+18h]
0x180002e0b  jnb     short loc_180002E38
0x180002e0d  mov     rax, [rdx+10h]
0x180002e11  mov     rcx, [rsi+rax]
0x180002e15  test    rcx, rcx
0x180002e18  jz      short loc_180002E3A
0x180002e1a  mov     rbx, rcx
0x180002e1d  lea     rcx, [rsp+58h+arg_8]; this
0x180002e22  call    ??1_Lockit@std@@QEAA@XZ
0x180002e27  mov     rax, rbx
0x180002e2a  mov     rbx, [rsp+58h+arg_18]
0x180002e2f  add     rsp, 40h
0x180002e33  pop     r14
0x180002e35  pop     rdi
0x180002e36  pop     rsi
0x180002e37  retn
0x180002e38  xor     ecx, ecx
0x180002e3a  cmp     byte ptr [rdx+24h], 0
0x180002e3e  jz      short loc_180002E57
0x180002e40  call    ?_Getgloballocale@locale@std@@CAPEAV_Locimp@12@XZ
0x180002e45  cmp     rdi, [rax+18h]
0x180002e49  jnb     short loc_180002E55
0x180002e4b  mov     rax, [rax+10h]
0x180002e4f  mov     rcx, [rsi+rax]
0x180002e53  jmp     short loc_180002E57
0x180002e55  xor     ecx, ecx
0x180002e57  test    rcx, rcx
0x180002e5a  jnz     short loc_180002E1A
0x180002e5c  test    rbx, rbx
0x180002e5f  jnz     short loc_180002E1D
0x180002e61  mov     rdx, r14
0x180002e64  lea     rcx, [rsp+58h+arg_10]
0x180002e69  call    ?_Getcat@?$ctype@D@std@@SA_KPEAPEBVfacet@locale@2@PEBV42@@Z
0x180002e6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002e72  jz      short loc_180002E99
0x180002e74  mov     rbx, [rsp+58h+arg_10]
0x180002e79  mov     cs:?_Psave@?$_Facetptr@V?$ctype@D@std@@@std@@2PEBVfacet@locale@2@EB, rbx
0x180002e80  mov     rax, [rbx]
0x180002e83  mov     rcx, rbx
0x180002e86  mov     rax, [rax+8]
0x180002e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8f  mov     rcx, rbx; struct std::_Facet_base *
0x180002e92  call    ?_Facet_Register@std@@YAXPEAV_Facet_base@1@@Z
0x180002e97  jmp     short loc_180002E1D
0x180002e99  lea     rdx, aBadCast
0x180002ea0  lea     rcx, [rsp+58h+pExceptionObject]
0x180002ea5  call    cs:__imp_??0bad_cast@@QEAA@PEBD@Z
0x180002eab  lea     rdx, _TI2?AVbad_cast@@; pThrowInfo
0x180002eb2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180002eb7  call    _CxxThrowException_0
```

# FilterReplaceCharSur::CreateInstance(_GUID const &,void * *,uchar const *,uint)

- ea: `0x18001bd68`
- end: `0x18001bed6`
- name: `?CreateInstance@FilterReplaceCharSur@@SAJAEBU_GUID@@PEAPEAXPEBEI@Z`
- size: `366`
- prototype: `__int64 __fastcall(const struct _GUID *, void **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017840`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001b410`
- `0x18001bd68`
- `0x180021816`
- `0x180024010`

## string_xrefs

- `0x18001be3a`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`
- `0x18001be8b`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceCharSur::CreateInstance(
        const struct _GUID *a1,
        void **a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  int v7; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  FilterChar *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  __int64 result; // rax
  int v14; // eax
  unsigned int v15; // edi
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v7 = memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_5b67a2c6_4097_4004_9db9_0c604f924636, 0x10u);
  try
  {
    if ( v7 && memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_0fce1815_18d2_4528_b8ba_969ac70b00db, 0x10u) )
      return (unsigned int)-2147467262;
    v10 = (FilterChar *)operator new(0x28u);
    if ( v10 )
    {
      *(_QWORD *)v10 = &FilterReplaceCharSur::`vftable';
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_DWORD *)v10 + 8) = 0;
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    v11 = FilterChar::init(v10, a3, a4);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v14 = (**(__int64 (__fastcall ***)(FilterChar *, GUID *, void **))v10)(
              v10,
              &GUID_5b67a2c6_4097_4004_9db9_0c604f924636,
              a2);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
          (const char *)(unsigned int)v14,
          v16);
        (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 16LL))(v10);
        return v15;
      }
      v9 = 0;
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 16LL))(v10);
      return v9;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacecharsur.cpp",
      (const char *)(unsigned int)v11,
      v16);
    if ( v10 )
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 16LL))(v10);
    result = v12;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacecharsur.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001bd68  mov     [rsp+arg_0], rcx
0x18001bd6d  push    rbx
0x18001bd6e  push    rsi
0x18001bd6f  push    rdi
0x18001bd70  push    r14
0x18001bd72  sub     rsp, 28h
0x18001bd76  mov     edi, r9d
0x18001bd79  mov     r14, r8
0x18001bd7c  mov     rsi, rdx
0x18001bd7f  mov     qword ptr [rdx], 0
0x18001bd86  mov     ebx, 10h
0x18001bd8b  mov     r8d, ebx; Size
0x18001bd8e  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf2
0x18001bd95  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001bd9c  call    memcmp_0
0x18001bda1  test    eax, eax
0x18001bda3  jz      short loc_18001BDC9
0x18001bda5  mov     r8d, ebx; Size
0x18001bda8  lea     rdx, _GUID_0fce1815_18d2_4528_b8ba_969ac70b00db; Buf2
0x18001bdaf  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001bdb6  call    memcmp_0
0x18001bdbb  test    eax, eax
0x18001bdbd  jz      short loc_18001BDC9
0x18001bdbf  mov     edi, 80004002h
0x18001bdc4  jmp     loc_18001BEC3
0x18001bdc9  mov     ecx, 28h ; '('; Size
0x18001bdce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bdd3  mov     rbx, rax
0x18001bdd6  test    rbx, rbx
0x18001bdd9  jz      short loc_18001BE04
0x18001bddb  lea     rax, ??_7FilterReplaceCharSur@@6B@; const FilterReplaceCharSur::`vftable'
0x18001bde2  mov     [rbx], rax
0x18001bde5  mov     qword ptr [rbx+8], 0
0x18001bded  mov     qword ptr [rbx+10h], 0
0x18001bdf5  mov     qword ptr [rbx+18h], 0
0x18001bdfd  mov     dword ptr [rbx+20h], 0
0x18001be04  mov     [rsp+48h+arg_0], rbx
0x18001be09  test    rbx, rbx
0x18001be0c  jz      short loc_18001BE1E
0x18001be0e  mov     rax, [rbx]
0x18001be11  mov     rcx, rbx
0x18001be14  mov     rax, [rax+8]
0x18001be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be1d  nop
0x18001be1e  mov     r8d, edi; unsigned int
0x18001be21  mov     rdx, r14; unsigned __int8 *
0x18001be24  mov     rcx, rbx; this
0x18001be27  call    ?init@FilterChar@@IEAAJPEBEI@Z; FilterChar::init(uchar const *,uint)
0x18001be2c  mov     edi, eax
0x18001be2e  test    eax, eax
0x18001be30  jns     short loc_18001BE65
0x18001be32  mov     rcx, [rsp+48h]; this
0x18001be37  mov     r9d, eax; char *
0x18001be3a  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001be41  mov     edx, 3Ch ; '<'; void *
0x18001be46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be4b  nop
0x18001be4c  test    rbx, rbx
0x18001be4f  jz      short loc_18001BE61
0x18001be51  mov     rax, [rbx]
0x18001be54  mov     rcx, rbx
0x18001be57  mov     rax, [rax+10h]
0x18001be5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be60  nop
0x18001be61  mov     eax, edi
0x18001be63  jmp     short loc_18001BECB
0x18001be65  mov     rax, [rbx]
0x18001be68  mov     r8, rsi
0x18001be6b  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636
0x18001be72  mov     rcx, rbx
0x18001be75  mov     rax, [rax]
0x18001be78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be7d  mov     edi, eax
0x18001be7f  test    eax, eax
0x18001be81  jns     short loc_18001BEB1
0x18001be83  mov     rcx, [rsp+48h]; this
0x18001be88  mov     r9d, eax; char *
0x18001be8b  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001be92  mov     edx, 3Dh ; '='; void *
0x18001be97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be9c  nop
0x18001be9d  mov     rcx, [rbx]
0x18001bea0  mov     rax, [rcx+10h]
0x18001bea4  mov     rcx, rbx
0x18001bea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beac  nop
0x18001bead  mov     eax, edi
0x18001beaf  jmp     short loc_18001BECB
0x18001beb1  xor     edi, edi
0x18001beb3  mov     rcx, [rbx]
0x18001beb6  mov     rax, [rcx+10h]
0x18001beba  mov     rcx, rbx
0x18001bebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bec2  nop
0x18001bec3  mov     eax, edi
0x18001bec5  jmp     short loc_18001BECB
0x18001bec7  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001becb  add     rsp, 28h
0x18001becf  pop     r14
0x18001bed1  pop     rdi
0x18001bed2  pop     rsi
0x18001bed3  pop     rbx
0x18001bed4  retn
```

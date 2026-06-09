# ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::InsertAt(unsigned __int64,UnBCL::SmartPtr<UnBCL::String> const &,unsigned __int64)

- ea: `0x1800106a4`
- end: `0x1800107c4`
- name: `?InsertAt@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAAX_KAEBV?$SmartPtr@VString@UnBCL@@@UnBCL@@0@Z`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800105d4`

## callees

- `0x180005ef8`
- `0x18000ea88`
- `0x18000eae0`
- `0x1800106a4`
- `0x180013764`

## import_xrefs

- `msvcrt!memmove_s` at `0x180010745`
- `msvcrt!memmove_s` at `0x180010745`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180010783`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180010783`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::InsertAt(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r14
  __int64 result; // rax
  errno_t v9; // eax

  v4 = a2;
  v6 = a1[1];
  if ( a2 < v6 )
  {
    if ( (unsigned __int8)ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(
                            a1,
                            v6 + 1,
                            0xFFFFFFFFLL) )
    {
      ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(
        *a1 + 16 * v6,
        1u);
      v7 = v4 + 1;
      v9 = memmove_s(
             (void *const)(*a1 + 16 * (v4 + 1)),
             16 * (v6 - v4),
             (const void *const)(*a1 + 16 * v4),
             16 * (v6 - v4));
      if ( !v9 )
      {
LABEL_10:
        result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallConstructors(
                   16 * v4 + *a1,
                   1);
        goto LABEL_12;
      }
      if ( v9 != 12 )
      {
        if ( v9 == 22 || v9 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v9 != 80 )
          ATL::AtlThrowImpl(-2147467259);
        goto LABEL_10;
      }
    }
LABEL_14:
    ATL::AtlThrowImpl(-2147024882);
  }
  v7 = a2 + 1;
  result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(
             a1,
             a2 + 1,
             0xFFFFFFFFLL);
  if ( !(_BYTE)result )
    goto LABEL_14;
LABEL_12:
  while ( v4 < v7 )
    result = UnBCL::SmartPtr<UnBCL::String>::operator=(*a1 + 16 * v4++, a3);
  return result;
}

```

## disassembly

```asm
0x1800106a4  mov     rax, rsp
0x1800106a7  mov     [rax+18h], rbx
0x1800106ab  mov     [rax+20h], r9
0x1800106af  mov     [rax+10h], rdx
0x1800106b3  mov     [rax+8], rcx
0x1800106b7  push    rsi
0x1800106b8  push    rdi
0x1800106b9  push    r12
0x1800106bb  push    r14
0x1800106bd  push    r15
0x1800106bf  sub     rsp, 20h
0x1800106c3  mov     r12, r8
0x1800106c6  mov     rbx, rdx
0x1800106c9  mov     rdi, rcx
0x1800106cc  mov     rsi, [rcx+8]
0x1800106d0  or      r8d, 0FFFFFFFFh
0x1800106d4  cmp     rdx, rsi
0x1800106d7  jb      short loc_1800106F2
0x1800106d9  lea     r14, [rdx+1]
0x1800106dd  mov     rdx, r14
0x1800106e0  call    ?SetCount@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(unsigned __int64,int)
0x1800106e5  test    al, al
0x1800106e7  jz      loc_1800107A3
0x1800106ed  jmp     loc_18001078C
0x1800106f2  lea     rdx, [rsi+1]
0x1800106f6  call    ?SetCount@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::SetCount(unsigned __int64,int)
0x1800106fb  test    al, al
0x1800106fd  jz      loc_1800107A3
0x180010703  mov     [rsp+48h+arg_18], rsi
0x180010708  mov     rcx, rsi
0x18001070b  shl     rcx, 4
0x18001070f  add     rcx, [rdi]
0x180010712  mov     edx, 1
0x180010717  call    ?CallDestructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x18001071c  mov     rax, [rdi]
0x18001071f  mov     r15, rbx
0x180010722  shl     r15, 4
0x180010726  sub     rsi, rbx
0x180010729  shl     rsi, 4
0x18001072d  lea     r14, [rbx+1]
0x180010731  lea     r8, [rax+r15]; Source
0x180010735  mov     rcx, r14
0x180010738  shl     rcx, 4
0x18001073c  add     rcx, rax; Destination
0x18001073f  mov     r9, rsi; SourceSize
0x180010742  mov     rdx, rsi; DestinationSize
0x180010745  call    cs:__imp_memmove_s
0x18001074b  test    eax, eax
0x18001074d  jz      short loc_180010763
0x18001074f  cmp     eax, 0Ch
0x180010752  jz      short loc_1800107A3
0x180010754  cmp     eax, 16h
0x180010757  jz      short loc_1800107B9
0x180010759  cmp     eax, 22h ; '"'
0x18001075c  jz      short loc_1800107B9
0x18001075e  cmp     eax, 50h ; 'P'
0x180010761  jnz     short loc_1800107AE
0x180010763  mov     rcx, [rdi]
0x180010766  add     rcx, r15
0x180010769  mov     edx, 1
0x18001076e  call    ?CallConstructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallConstructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x180010773  nop
0x180010774  jmp     short loc_18001078C
0x180010776  mov     rcx, rbx
0x180010779  shl     rcx, 4
0x18001077d  add     rcx, [rdi]
0x180010780  mov     rdx, r12
0x180010783  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180010789  inc     rbx
0x18001078c  cmp     rbx, r14
0x18001078f  jb      short loc_180010776
0x180010791  mov     rbx, [rsp+48h+arg_10]
0x180010796  add     rsp, 20h
0x18001079a  pop     r15
0x18001079c  pop     r14
0x18001079e  pop     r12
0x1800107a0  pop     rdi
0x1800107a1  pop     rsi
0x1800107a2  retn
0x1800107a3  mov     ecx, 8007000Eh; int
0x1800107a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800107ae  mov     ecx, 80004005h; int
0x1800107b3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800107b9  mov     ecx, 80070057h; int
0x1800107be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

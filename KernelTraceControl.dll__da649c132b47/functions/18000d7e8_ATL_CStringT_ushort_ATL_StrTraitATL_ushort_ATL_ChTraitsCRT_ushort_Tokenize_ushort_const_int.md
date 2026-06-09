# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x18000d7e8`
- end: `0x18000d907`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800098d0`
- `0x1800140dc`

## callees

- `0x18000139c`
- `0x18000d7e8`
- `0x18000e76c`
- `0x180027910`

## import_xrefs

- `msvcrt!wcsspn` at `0x18000d848`
- `msvcrt!wcsspn` at `0x18000d848`
- `msvcrt!wcscspn` at `0x18000d864`
- `msvcrt!wcscspn` at `0x18000d864`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        int *a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rbp
  int v10; // r15d
  const wchar_t *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rcx

  if ( *a4 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = *a1;
  v8 = v7 + 2LL * *a4;
  v9 = v7 + 2LL * *(int *)(v7 - 16);
  if ( v8 >= v9
    || (v10 = wcsspn((const wchar_t *)(v7 + 2LL * *a4), L";"),
        v11 = (const wchar_t *)(v8 + 2LL * v10),
        (unsigned __int64)v11 >= v9) )
  {
    *a4 = -1;
    v14 = *(_QWORD *)(*a1 - 24);
    if ( v14 )
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
    if ( !v14 )
    {
      v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
      if ( !v14 )
        ATL::AtlThrowImpl(-2147467259);
    }
    *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14) + 24;
  }
  else
  {
    v12 = wcscspn(v11, L";");
    v13 = (unsigned int)(v10 + *a4);
    *a4 = v13 + v12 + 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      a1,
      a2,
      v13,
      v12,
      0,
      -2);
  }
  return a2;
}

```

## disassembly

```asm
0x18000d7e8  mov     rax, rsp
0x18000d7eb  push    rdi
0x18000d7ec  push    r14
0x18000d7ee  push    r15
0x18000d7f0  sub     rsp, 30h
0x18000d7f4  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x18000d7fc  mov     [rax+8], rbx
0x18000d800  mov     [rax+10h], rbp
0x18000d804  mov     [rax+18h], rsi
0x18000d808  mov     rdi, r9
0x18000d80b  mov     rbx, rdx
0x18000d80e  mov     rsi, rcx
0x18000d811  and     [rsp+48h+var_28], 0
0x18000d816  cmp     dword ptr [r9], 0
0x18000d81a  jge     short loc_18000D827
0x18000d81c  mov     ecx, 80070057h; int
0x18000d821  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d827  mov     rcx, [rcx]
0x18000d82a  movsxd  rax, dword ptr [r9]
0x18000d82d  lea     r14, [rcx+rax*2]
0x18000d831  movsxd  rax, dword ptr [rcx-10h]
0x18000d835  lea     rbp, [rcx+rax*2]
0x18000d839  cmp     r14, rbp
0x18000d83c  jnb     short loc_18000D888
0x18000d83e  lea     rdx, Control; ";"
0x18000d845  mov     rcx, r14; String
0x18000d848  call    cs:__imp_wcsspn
0x18000d84e  mov     r15, rax
0x18000d851  movsxd  rcx, eax
0x18000d854  lea     rcx, [r14+rcx*2]; String
0x18000d858  cmp     rcx, rbp
0x18000d85b  jnb     short loc_18000D888
0x18000d85d  lea     rdx, Control; ";"
0x18000d864  call    cs:__imp_wcscspn
0x18000d86a  mov     r8d, [rdi]
0x18000d86d  add     r8d, r15d
0x18000d870  lea     ecx, [rax+1]
0x18000d873  add     ecx, r8d
0x18000d876  mov     [rdi], ecx
0x18000d878  mov     r9d, eax
0x18000d87b  mov     rdx, rbx
0x18000d87e  mov     rcx, rsi
0x18000d881  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x18000d886  jmp     short loc_18000D8EB
0x18000d888  or      dword ptr [rdi], 0FFFFFFFFh
0x18000d88b  mov     rax, [rsi]
0x18000d88e  mov     rcx, [rax-18h]
0x18000d892  test    rcx, rcx
0x18000d895  jz      short loc_18000D8A7
0x18000d897  mov     rax, [rcx]
0x18000d89a  mov     rax, [rax+20h]
0x18000d89e  call    cs:__guard_dispatch_icall_fptr
0x18000d8a4  mov     rcx, rax
0x18000d8a7  test    rcx, rcx
0x18000d8aa  jnz     short loc_18000D8D7
0x18000d8ac  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d8b3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d8ba  mov     rax, [rax+20h]
0x18000d8be  call    cs:__guard_dispatch_icall_fptr
0x18000d8c4  mov     rcx, rax
0x18000d8c7  test    rax, rax
0x18000d8ca  jnz     short loc_18000D8D7
0x18000d8cc  mov     ecx, 80004005h; int
0x18000d8d1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d8d7  mov     rax, [rcx]
0x18000d8da  mov     rax, [rax+18h]
0x18000d8de  call    cs:__guard_dispatch_icall_fptr
0x18000d8e4  add     rax, 18h
0x18000d8e8  mov     [rbx], rax
0x18000d8eb  mov     rax, rbx
0x18000d8ee  mov     rbx, [rsp+48h+arg_0]
0x18000d8f3  mov     rbp, [rsp+48h+arg_8]
0x18000d8f8  mov     rsi, [rsp+48h+arg_10]
0x18000d8fd  add     rsp, 30h
0x18000d901  pop     r15
0x18000d903  pop     r14
0x18000d905  pop     rdi
0x18000d906  retn
```

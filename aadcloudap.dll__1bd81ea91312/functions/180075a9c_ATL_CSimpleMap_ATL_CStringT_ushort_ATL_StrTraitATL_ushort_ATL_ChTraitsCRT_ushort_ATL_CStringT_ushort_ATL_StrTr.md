# ATL::CSimpleMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleMapEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(int)

- ea: `0x180075a9c`
- end: `0x180075ba4`
- name: `?RemoveAt@?$CSimpleMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CSimpleMapEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@2@@ATL@@QEAAHH@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180075a6c`

## callees

- `0x180006424`
- `0x18000aa74`
- `0x180075a9c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180075b03`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180075b32`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180075b03`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180075b32`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180075b55`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180075b77`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180075b55`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180075b77`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleMapEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
        __int64 a1,
        int a2)
{
  __int64 v2; // rdi
  int v4; // edx
  errno_t v5; // eax
  errno_t v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax

  v2 = a2;
  if ( a2 < 0 || a2 >= *(_DWORD *)(a1 + 16) )
    return 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(*(_QWORD *)a1 + 8LL * a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::`scalar deleting destructor'(*(_QWORD *)(a1 + 8) + 8 * v2);
  v4 = *(_DWORD *)(a1 + 16);
  if ( (_DWORD)v2 != v4 - 1 )
  {
    v5 = memmove_s(
           (void *const)(*(_QWORD *)a1 + 8 * v2),
           8LL * (v4 - (int)v2),
           (const void *const)(*(_QWORD *)a1 + 8 * v2 + 8),
           8LL * (v4 - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v5);
    v6 = memmove_s(
           (void *const)(*(_QWORD *)(a1 + 8) + 8 * v2),
           8LL * (*(_DWORD *)(a1 + 16) - (int)v2),
           (const void *const)(*(_QWORD *)(a1 + 8) + 8 * v2 + 8),
           8LL * (*(_DWORD *)(a1 + 16) - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v6);
  }
  v7 = _o__recalloc(*(_QWORD *)a1, *(_DWORD *)(a1 + 16) - 1, 8);
  if ( v7 || *(_DWORD *)(a1 + 16) == 1 )
    *(_QWORD *)a1 = v7;
  v8 = _o__recalloc(*(_QWORD *)(a1 + 8), *(_DWORD *)(a1 + 16) - 1, 8);
  if ( v8 || *(_DWORD *)(a1 + 16) == 1 )
    *(_QWORD *)(a1 + 8) = v8;
  --*(_DWORD *)(a1 + 16);
  return 1;
}

```

## disassembly

```asm
0x180075a9c  mov     [rsp+arg_0], rbx
0x180075aa1  mov     [rsp+arg_8], rsi
0x180075aa6  push    rdi
0x180075aa7  sub     rsp, 20h
0x180075aab  movsxd  rdi, edx
0x180075aae  mov     rbx, rcx
0x180075ab1  test    edx, edx
0x180075ab3  js      loc_180075B92
0x180075ab9  cmp     edi, [rcx+10h]
0x180075abc  jge     loc_180075B92
0x180075ac2  mov     rax, [rcx]
0x180075ac5  lea     rcx, [rax+rdi*8]
0x180075ac9  call    ??_G?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::`scalar deleting destructor'(uint)
0x180075ace  mov     rax, [rbx+8]
0x180075ad2  lea     rcx, [rax+rdi*8]
0x180075ad6  call    ??_G?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::`scalar deleting destructor'(uint)
0x180075adb  mov     edx, [rbx+10h]
0x180075ade  lea     eax, [rdx-1]
0x180075ae1  cmp     edi, eax
0x180075ae3  jz      short loc_180075B3F
0x180075ae5  mov     rax, [rbx]
0x180075ae8  sub     edx, edi
0x180075aea  lea     rcx, [rax+rdi*8]; Destination
0x180075aee  lea     eax, [rdx-1]
0x180075af1  movsxd  rdx, edx
0x180075af4  movsxd  r9, eax
0x180075af7  lea     r8, [rcx+8]; Source
0x180075afb  shl     r9, 3; SourceSize
0x180075aff  shl     rdx, 3; DestinationSize
0x180075b03  call    cs:__imp_memmove_s
0x180075b09  mov     ecx, eax; int
0x180075b0b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180075b10  mov     edx, [rbx+10h]
0x180075b13  mov     rax, [rbx+8]
0x180075b17  sub     edx, edi
0x180075b19  lea     rcx, [rax+rdi*8]; Destination
0x180075b1d  lea     eax, [rdx-1]
0x180075b20  movsxd  rdx, edx
0x180075b23  movsxd  r9, eax
0x180075b26  lea     r8, [rcx+8]; Source
0x180075b2a  shl     r9, 3; SourceSize
0x180075b2e  shl     rdx, 3; DestinationSize
0x180075b32  call    cs:__imp_memmove_s
0x180075b38  mov     ecx, eax; int
0x180075b3a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180075b3f  mov     eax, [rbx+10h]
0x180075b42  mov     edi, 1
0x180075b47  mov     rcx, [rbx]
0x180075b4a  sub     eax, edi
0x180075b4c  movsxd  rdx, eax
0x180075b4f  lea     esi, [rdi+7]
0x180075b52  mov     r8d, esi
0x180075b55  call    cs:__imp__o__recalloc
0x180075b5b  test    rax, rax
0x180075b5e  jnz     short loc_180075B65
0x180075b60  cmp     [rbx+10h], edi
0x180075b63  jnz     short loc_180075B68
0x180075b65  mov     [rbx], rax
0x180075b68  mov     eax, [rbx+10h]
0x180075b6b  mov     r8, rsi
0x180075b6e  mov     rcx, [rbx+8]
0x180075b72  sub     eax, edi
0x180075b74  movsxd  rdx, eax
0x180075b77  call    cs:__imp__o__recalloc
0x180075b7d  test    rax, rax
0x180075b80  jnz     short loc_180075B87
0x180075b82  cmp     [rbx+10h], edi
0x180075b85  jnz     short loc_180075B8B
0x180075b87  mov     [rbx+8], rax
0x180075b8b  dec     dword ptr [rbx+10h]
0x180075b8e  mov     eax, edi
0x180075b90  jmp     short loc_180075B94
0x180075b92  xor     eax, eax
0x180075b94  mov     rbx, [rsp+28h+arg_0]
0x180075b99  mov     rsi, [rsp+28h+arg_8]
0x180075b9e  add     rsp, 20h
0x180075ba2  pop     rdi
0x180075ba3  retn
```

# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180078c40`
- end: `0x180078d8c`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180040504`
- `0x180043a40`

## callees

- `0x180027b20`
- `0x180041ca4`
- `0x180077790`
- `0x180077a68`
- `0x180078c40`
- `0x18007991c`
- `0x180079e24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180078cc5`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180078cc5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180078d6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180078d6a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180078c8e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180078c8e`

## string_xrefs

- `0x180078ca3`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  errno_t v6; // ecx
  errno_t v7; // ecx
  int v8; // eax
  __int64 v9; // rbp
  wchar_t *v11; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = a3;
  v11 = a2;
  ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(
    a1 + 2,
    0);
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v4 = (wchar_t *)malloc(0x6Au);
  v5 = v4;
  if ( !v4 )
    return 1;
  v6 = memcpy_s(v4, 0x6Au, L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})", 0x6Au);
  ATL::AtlCrtErrorCheck(v6);
  v7 = _wcslwr_s(v5, 0x35u);
  ATL::AtlCrtErrorCheck(v7);
  v11 = v5;
  v8 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v9 = v8;
  if ( v8 < 0 )
    return 1;
  if ( *v11 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) >= 0 )
      goto LABEL_7;
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) < 0 )
    return 1;
  ++v11;
LABEL_7:
  LOBYTE(v12) = 1;
  ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v11, &v12);
  if ( !*a1 )
  {
    *(_QWORD *)(ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
                  a1 + 2,
                  v9)
              + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
      return 1;
  }
  if ( v5 != L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v5);
  return *a1;
}

```

## disassembly

```asm
0x180078c40  mov     rax, rsp
0x180078c43  mov     [rax+18h], r8d
0x180078c47  mov     [rax+10h], rdx
0x180078c4b  push    rsi
0x180078c4c  push    rdi
0x180078c4d  push    r15
0x180078c4f  sub     rsp, 30h
0x180078c53  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180078c5b  mov     [rax+8], rbx
0x180078c5f  mov     [rax+20h], rbp
0x180078c63  mov     rbx, rcx
0x180078c66  xor     edx, edx
0x180078c68  add     rcx, 8
0x180078c6c  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x180078c71  nop
0x180078c72  mov     qword ptr [rbx+28h], 0
0x180078c7a  mov     dword ptr [rbx], 0
0x180078c80  mov     dword ptr [rbx+30h], 0
0x180078c87  mov     ebp, 6Ah ; 'j'
0x180078c8c  mov     ecx, ebp; Size
0x180078c8e  call    cs:__imp_malloc
0x180078c94  mov     rdi, rax
0x180078c97  test    rax, rax
0x180078c9a  jz      loc_180078D74
0x180078ca0  mov     r9d, ebp; SourceSize
0x180078ca3  lea     r15, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180078caa  mov     r8, r15; Source
0x180078cad  mov     edx, ebp; DestinationSize
0x180078caf  mov     rcx, rax; Destination
0x180078cb2  call    memcpy_s
0x180078cb7  mov     ecx, eax; int
0x180078cb9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180078cbe  nop
0x180078cbf  lea     edx, [rbp-35h]; SizeInWords
0x180078cc2  mov     rcx, rdi; String
0x180078cc5  call    cs:__imp__wcslwr_s
0x180078ccb  mov     ecx, eax; int
0x180078ccd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180078cd2  nop
0x180078cd3  mov     [rsp+48h+arg_8], rdi
0x180078cd8  lea     edx, [rbp-5Ah]
0x180078cdb  mov     rcx, rbx
0x180078cde  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180078ce3  movsxd  rbp, eax
0x180078ce6  test    eax, eax
0x180078ce8  js      loc_180078D74
0x180078cee  mov     rcx, [rsp+48h+arg_8]
0x180078cf3  cmp     word ptr [rcx], 5Eh ; '^'
0x180078cf7  mov     rcx, rbx
0x180078cfa  jnz     short loc_180078D12
0x180078cfc  mov     edx, 1Ch
0x180078d01  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180078d06  test    eax, eax
0x180078d08  js      short loc_180078D74
0x180078d0a  add     [rsp+48h+arg_8], 2
0x180078d10  jmp     short loc_180078D20
0x180078d12  mov     edx, 1Dh
0x180078d17  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180078d1c  test    eax, eax
0x180078d1e  js      short loc_180078D74
0x180078d20  mov     byte ptr [rsp+48h+arg_10], 1
0x180078d25  lea     r8, [rsp+48h+arg_10]
0x180078d2a  lea     rdx, [rsp+48h+arg_8]
0x180078d2f  mov     rcx, rbx
0x180078d32  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180078d37  cmp     dword ptr [rbx], 0
0x180078d3a  jnz     short loc_180078D62
0x180078d3c  mov     rdx, rbp
0x180078d3f  lea     rcx, [rbx+8]
0x180078d43  call    ??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)
0x180078d48  nop
0x180078d49  mov     qword ptr [rax+8], 2
0x180078d51  mov     edx, 1Eh
0x180078d56  mov     rcx, rbx
0x180078d59  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180078d5e  test    eax, eax
0x180078d60  js      short loc_180078D74
0x180078d62  cmp     rdi, r15
0x180078d65  jz      short loc_180078D70
0x180078d67  mov     rcx, rdi; Block
0x180078d6a  call    cs:__imp_free
0x180078d70  mov     eax, [rbx]
0x180078d72  jmp     short loc_180078D79
0x180078d74  mov     eax, 1
0x180078d79  mov     rbx, [rsp+48h+arg_0]
0x180078d7e  mov     rbp, [rsp+48h+arg_18]
0x180078d83  add     rsp, 30h
0x180078d87  pop     r15
0x180078d89  pop     rdi
0x180078d8a  pop     rsi
0x180078d8b  retn
```

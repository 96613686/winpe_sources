# Speller::CSpellerUtility::TrimDuplicateSuggestionsFor(CWordNode *,ulong)

- ea: `0x18008ea50`
- end: `0x18008eb99`
- name: `?TrimDuplicateSuggestionsFor@CSpellerUtility@Speller@@SAXPEAVCWordNode@@K@Z`
- size: `329`
- prototype: `static void(struct CWordNode *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18008b670`

## callees

- `0x180003d38`
- `0x1800088b0`
- `0x18002d8c4`
- `0x180035640`
- `0x18003ed6c`
- `0x18008e6d4`
- `0x18008e7a0`
- `0x18008ea50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008eb4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008eb4f`

## pseudocode

```c
void __fastcall Speller::CSpellerUtility::TrimDuplicateSuggestionsFor(struct CWordNode *a1, LCID a2)
{
  _QWORD *v3; // r9
  _QWORD *v4; // r9
  __int64 NextPropertyFor; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // ebx
  __int64 i; // r15
  LSP::CName *v11; // rax
  const WCHAR *lpString2; // r14
  int v13; // ebp
  __int64 v14; // rsi
  LSP::CName *v15; // rax
  const WCHAR *v16; // rax
  __int64 cchCount2; // rcx
  __int64 v18; // r9
  _BYTE pExceptionObject[136]; // [rsp+30h] [rbp-88h] BYREF
  const void *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = *(_QWORD **)((char *)a1 + *(int *)(*((_QWORD *)a1 + 1) + 4LL) + 88);
  if ( v3 )
  {
    NextPropertyFor = CNodeProperties::FindNextPropertyFor(a1, 245, *v3);
    v7 = CNodeProperties::FindNextPropertyFor(v6, 255, *v4);
    if ( NextPropertyFor )
    {
      if ( !v7 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v8 = *(_QWORD *)(NextPropertyFor + 16);
      v9 = 0;
      for ( i = *(_QWORD *)(v7 + 16); v9 < *(_QWORD *)(v8 + 8); ++v9 )
      {
        v11 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v8, v9);
        lpString2 = LSP::CName::ToString(v11);
        v13 = *(_DWORD *)(v8 + 8) - 1;
        if ( v13 > v9 )
        {
          v14 = v13;
          do
          {
            v15 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v8, v14);
            v16 = LSP::CName::ToString(v15);
            if ( v16 == lpString2 )
              goto LABEL_14;
            cchCount2 = -1;
            do
              ++cchCount2;
            while ( lpString2[cchCount2] );
            v18 = -1;
            do
              ++v18;
            while ( v16[v18] );
            if ( CompareStringW(a2, 0, v16, v18, lpString2, cchCount2) == 2 )
            {
LABEL_14:
              CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::RemoveAt(v8, v14);
              CArray<int,CArrayAllocator_GC<CZoneHeap>>::RemoveAt(i, v14);
            }
            --v13;
            --v14;
          }
          while ( v13 > v9 );
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18008ea50  push    rbx
0x18008ea52  push    rbp
0x18008ea53  push    rsi
0x18008ea54  push    rdi
0x18008ea55  push    r12
0x18008ea57  push    r13
0x18008ea59  push    r14
0x18008ea5b  push    r15
0x18008ea5d  sub     rsp, 78h
0x18008ea61  mov     rax, [rcx+8]
0x18008ea65  xor     r13d, r13d
0x18008ea68  mov     r12d, edx
0x18008ea6b  movsxd  r8, dword ptr [rax+4]
0x18008ea6f  mov     r9, [r8+rcx+58h]
0x18008ea74  test    r9, r9
0x18008ea77  jz      loc_18008EB88
0x18008ea7d  mov     r8, [r9]
0x18008ea80  mov     edx, 0F5h
0x18008ea85  call    ?FindNextPropertyFor@CNodeProperties@@QEAAPEAVCNodeProperty@@W4EMorphUnit@CMorphBits@@PEAV2@@Z; CNodeProperties::FindNextPropertyFor(CMorphBits::EMorphUnit,CNodeProperty *)
0x18008ea8a  mov     r8, [r9]
0x18008ea8d  mov     edx, 0FFh
0x18008ea92  mov     rdi, rax
0x18008ea95  call    ?FindNextPropertyFor@CNodeProperties@@QEAAPEAVCNodeProperty@@W4EMorphUnit@CMorphBits@@PEAV2@@Z; CNodeProperties::FindNextPropertyFor(CMorphBits::EMorphUnit,CNodeProperty *)
0x18008ea9a  test    rdi, rdi
0x18008ea9d  jz      loc_18008EB88
0x18008eaa3  test    rax, rax
0x18008eaa6  jnz     short loc_18008EAD1
0x18008eaa8  mov     r8, [rsp+0B8h]; void *
0x18008eab0  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x18008eab5  mov     edx, 80004005h; int
0x18008eaba  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18008eabf  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18008eac6  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18008eacb  call    _CxxThrowException_0
0x18008ead1  mov     rdi, [rdi+10h]
0x18008ead5  mov     ebx, r13d
0x18008ead8  mov     r15, [rax+10h]
0x18008eadc  cmp     [rdi+8], r13
0x18008eae0  jle     loc_18008EB88
0x18008eae6  movsxd  rdx, ebx
0x18008eae9  mov     rcx, rdi
0x18008eaec  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x18008eaf1  mov     rcx, rax; this
0x18008eaf4  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x18008eaf9  mov     ebp, [rdi+8]
0x18008eafc  mov     r14, rax
0x18008eaff  dec     ebp
0x18008eb01  cmp     ebp, ebx
0x18008eb03  jle     short loc_18008EB79
0x18008eb05  movsxd  rsi, ebp
0x18008eb08  mov     rdx, rsi
0x18008eb0b  mov     rcx, rdi
0x18008eb0e  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x18008eb13  mov     rcx, rax; this
0x18008eb16  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x18008eb1b  cmp     rax, r14
0x18008eb1e  jz      short loc_18008EB5A
0x18008eb20  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008eb24  mov     rcx, rdx
0x18008eb27  inc     rcx
0x18008eb2a  cmp     [r14+rcx*2], r13w
0x18008eb2f  jnz     short loc_18008EB27
0x18008eb31  mov     r9, rdx
0x18008eb34  inc     r9; cchCount1
0x18008eb37  cmp     [rax+r9*2], r13w
0x18008eb3c  jnz     short loc_18008EB34
0x18008eb3e  mov     [rsp+0B8h+cchCount2], ecx; cchCount2
0x18008eb42  mov     r8, rax; lpString1
0x18008eb45  mov     ecx, r12d; Locale
0x18008eb48  mov     [rsp+0B8h+lpString2], r14; lpString2
0x18008eb4d  xor     edx, edx; dwCmpFlags
0x18008eb4f  call    cs:__imp_CompareStringW
0x18008eb55  cmp     eax, 2
0x18008eb58  jnz     short loc_18008EB70
0x18008eb5a  mov     rdx, rsi
0x18008eb5d  mov     rcx, rdi
0x18008eb60  call    ?RemoveAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEAAX_J0@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::RemoveAt(__int64,__int64)
0x18008eb65  mov     rdx, rsi
0x18008eb68  mov     rcx, r15
0x18008eb6b  call    ?RemoveAt@?$CArray@HV?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEAAX_J0@Z; CArray<int,CArrayAllocator_GC<CZoneHeap>>::RemoveAt(__int64,__int64)
0x18008eb70  dec     ebp
0x18008eb72  dec     rsi
0x18008eb75  cmp     ebp, ebx
0x18008eb77  jg      short loc_18008EB08
0x18008eb79  inc     ebx
0x18008eb7b  movsxd  rax, ebx
0x18008eb7e  cmp     rax, [rdi+8]
0x18008eb82  jl      loc_18008EAE6
0x18008eb88  add     rsp, 78h
0x18008eb8c  pop     r15
0x18008eb8e  pop     r14
0x18008eb90  pop     r13
0x18008eb92  pop     r12
0x18008eb94  pop     rdi
0x18008eb95  pop     rsi
0x18008eb96  pop     rbp
0x18008eb97  pop     rbx
0x18008eb98  retn
```

# CNLDP::GetLangDataDll(ushort,ResourceLoader6::ILoadResources *)

- ea: `0x180001bf8`
- end: `0x180001dc8`
- name: `?GetLangDataDll@CNLDP@@QEAAPEAV?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@GPEAUILoadResources@ResourceLoader6@@@Z`
- size: `464`
- prototype: `HMODULE __fastcall(__int64, __int16, struct IUnknown *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180001b1c`
- `0x180001be0`

## callees

- `0x180001bf8`
- `0x180001dd0`
- `0x180002884`
- `0x18000b130`
- `0x180035640`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x18004e9ac`
- `0x1800b0010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001d11`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001d11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c31`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall CNLDP::GetLangDataDll(__int64 a1, __int16 a2, struct IUnknown *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  HINSTANCE v7; // r8
  unsigned __int64 v8; // r9
  __int64 v9; // rbx
  int i; // edi
  HMODULE v12; // rdi
  _WORD *v13; // rax
  __int64 v14; // rdx
  _QWORD v15[3]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+38h] [rbp-48h] BYREF
  const void *retaddr; // [rsp+B8h] [rbp+38h]
  __int16 v18; // [rsp+C8h] [rbp+48h] BYREF
  HMODULE v19; // [rsp+D8h] [rbp+58h]

  v18 = a2;
  v15[1] = -2;
  v15[2] = a1 + 112;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 120);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 120));
  v7 = 0;
  v8 = *(_QWORD *)(a1 + 16);
  while ( (int)v7 < (__int64)v8 )
  {
    if ( (int)v7 >= v8 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, -2147024809, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    _mm_lfence();
    if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * (int)v7) + 8LL) == a2 )
    {
      if ( (unsigned __int64)(int)v7 >= *(_QWORD *)(a1 + 16) )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, -2147024809, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      _mm_lfence();
      v9 = **(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL * (int)v7);
LABEL_7:
      LeaveCriticalSection(v6);
      return (HMODULE)v9;
    }
    v7 = (HINSTANCE)(unsigned int)((_DWORD)v7 + 1);
  }
  for ( i = 0; i < *(_QWORD *)(a1 + 56); ++i )
  {
    if ( *(_WORD *)CArray<unsigned short,CArrayAllocator_malloc>::ElementAt(a1 + 48) == a2 )
    {
      v9 = 0;
      goto LABEL_7;
    }
  }
  v12 = TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::Create(a2, a3, v7);
  v19 = v12;
  if ( v12 )
  {
    v13 = operator new(0x10u);
    if ( v13 )
    {
      *(_QWORD *)v13 = v12;
      v13[4] = a2;
    }
    v15[0] = v13;
    CArray<CPair<TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)> *,unsigned short> *,CArrayAllocator_malloc>::AddElement(
      a1 + 8,
      v15);
    LOBYTE(v14) = *(_BYTE *)(a1 + 172);
    (*(void (__fastcall **)(HMODULE, __int64))(*(_QWORD *)v12 + 24LL))(v12, v14);
    operator delete(0);
  }
  else if ( *(__int64 *)(a1 + 56) < 50 )
  {
    CArray<unsigned short,CArrayAllocator_malloc>::AddElement(a1 + 48, &v18);
  }
  v19 = 0;
  LeaveCriticalSection(v6);
  return v12;
}

```

## disassembly

```asm
0x180001bf8  mov     [rsp-38h+arg_8], dx
0x180001bfd  push    rbp
0x180001bfe  push    rbx
0x180001bff  push    rsi
0x180001c00  push    rdi
0x180001c01  push    r12
0x180001c03  push    r14
0x180001c05  push    r15
0x180001c07  mov     rbp, rsp
0x180001c0a  sub     rsp, 80h
0x180001c11  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFEh
0x180001c19  mov     r12, r8
0x180001c1c  movzx   esi, dx
0x180001c1f  mov     rbx, rcx
0x180001c22  lea     rax, [rcx+70h]
0x180001c26  mov     [rbp+var_50], rax
0x180001c2a  lea     r14, [rax+8]
0x180001c2e  mov     rcx, r14; lpCriticalSection
0x180001c31  call    cs:__imp_EnterCriticalSection
0x180001c37  nop
0x180001c38  xor     r8d, r8d
0x180001c3b  mov     r9, [rbx+10h]
0x180001c3f  movsxd  rdx, r8d
0x180001c42  cmp     rdx, r9
0x180001c45  jge     short loc_180001C98
0x180001c47  jnb     loc_180001D6B
0x180001c4d  lfence
0x180001c50  mov     rax, [rbx+8]
0x180001c54  mov     rcx, [rax+rdx*8]
0x180001c58  cmp     [rcx+8], si
0x180001c5c  jnz     loc_180001D40
0x180001c62  cmp     rdx, [rbx+10h]
0x180001c66  jnb     loc_180001D48
0x180001c6c  lfence
0x180001c6f  mov     rax, [rbx+8]
0x180001c73  mov     rcx, [rax+rdx*8]
0x180001c77  mov     rbx, [rcx]
0x180001c7a  mov     rcx, r14; lpCriticalSection
0x180001c7d  call    cs:__imp_LeaveCriticalSection
0x180001c83  mov     rax, rbx
0x180001c86  add     rsp, 80h
0x180001c8d  pop     r15
0x180001c8f  pop     r14
0x180001c91  pop     r12
0x180001c93  pop     rdi
0x180001c94  pop     rsi
0x180001c95  pop     rbx
0x180001c96  pop     rbp
0x180001c97  retn
0x180001c98  xor     edi, edi
0x180001c9a  movsxd  rdx, edi
0x180001c9d  cmp     rdx, [rbx+38h]
0x180001ca1  jl      loc_180001D8E
0x180001ca7  mov     rdx, r12
0x180001caa  movzx   ecx, si
0x180001cad  call    ?Create@?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@SAPEAV1@GPEAUILoadResources@ResourceLoader6@@@Z; TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::Create(ushort,ResourceLoader6::ILoadResources *)
0x180001cb2  mov     rdi, rax
0x180001cb5  mov     [rbp+arg_18], rax
0x180001cb9  test    rax, rax
0x180001cbc  jz      loc_180001DAA
0x180001cc2  mov     ecx, 10h; Size
0x180001cc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ccc  mov     [rbp+arg_0], rax
0x180001cd0  test    rax, rax
0x180001cd3  jz      short loc_180001CDC
0x180001cd5  mov     [rax], rdi
0x180001cd8  mov     [rax+8], si
0x180001cdc  mov     [rbp+arg_0], rax
0x180001ce0  mov     [rbp+var_60], rax
0x180001ce4  lea     rcx, [rbx+8]
0x180001ce8  lea     rdx, [rbp+var_60]
0x180001cec  call    ?AddElement@?$CArray@PEAV?$CPair@PEAV?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@G@@VCArrayAllocator_malloc@@@@QEAAXAEBQEAV?$CPair@PEAV?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@G@@@Z; CArray<CPair<TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)> *,ushort> *,CArrayAllocator_malloc>::AddElement(CPair<TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)> *,ushort> * const &)
0x180001cf1  mov     [rbp+arg_0], 0
0x180001cf9  mov     rax, [rdi]
0x180001cfc  mov     dl, [rbx+0ACh]
0x180001d02  mov     rcx, rdi
0x180001d05  mov     rax, [rax+18h]
0x180001d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0e  nop
0x180001d0f  xor     ecx, ecx
0x180001d11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001d17  mov     [rbp+arg_0], 0
0x180001d1f  mov     [rbp+arg_18], 0
0x180001d27  mov     [rbp+arg_18], 0
0x180001d2f  mov     rcx, r14; lpCriticalSection
0x180001d32  call    cs:__imp_LeaveCriticalSection
0x180001d38  mov     rax, rdi
0x180001d3b  jmp     loc_180001C86
0x180001d40  inc     r8d
0x180001d43  jmp     loc_180001C3F
0x180001d48  mov     r8, [rbp+38h]; void *
0x180001d4c  mov     edx, 80070057h; int
0x180001d51  lea     rcx, [rbp+pExceptionObject]; this
0x180001d55  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180001d5a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180001d61  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001d65  call    _CxxThrowException_0
0x180001d6b  mov     r8, [rbp+38h]; void *
0x180001d6f  mov     edx, 80070057h; int
0x180001d74  lea     rcx, [rbp+pExceptionObject]; this
0x180001d78  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180001d7d  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180001d84  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001d88  call    _CxxThrowException_0
0x180001d8e  lea     rcx, [rbx+30h]
0x180001d92  call    ?ElementAt@?$CArray@GVCArrayAllocator_malloc@@@@QEBAAEAG_J@Z; CArray<ushort,CArrayAllocator_malloc>::ElementAt(__int64)
0x180001d97  cmp     [rax], si
0x180001d9a  jz      short loc_180001DA3
0x180001d9c  inc     edi
0x180001d9e  jmp     loc_180001C9A
0x180001da3  xor     ebx, ebx
0x180001da5  jmp     loc_180001C7A
0x180001daa  cmp     qword ptr [rbx+38h], 32h ; '2'
0x180001daf  jge     loc_180001D1F
0x180001db5  lea     rdx, [rbp+arg_8]
0x180001db9  lea     rcx, [rbx+30h]
0x180001dbd  call    ?AddElement@?$CArray@GVCArrayAllocator_malloc@@@@QEAAXAEBG@Z; CArray<ushort,CArrayAllocator_malloc>::AddElement(ushort const &)
0x180001dc2  jmp     loc_180001D1F
```

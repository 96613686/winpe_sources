# StateRepository::Database::DetachDatabase(char const *)

- ea: `0x180018ae8`
- end: `0x180018c39`
- name: `?DetachDatabase@Database@StateRepository@@QEAAJPEBD@Z`
- size: `337`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180013bc0`

## callees

- `0x1800023f4`
- `0x180003d50`
- `0x180007f28`
- `0x18000a3c0`
- `0x180014ca0`
- `0x180018ae8`
- `0x180018c40`
- `0x180018e80`
- `0x180019adc`

## string_xrefs

- `0x180018b0f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018b92`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180018c24`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::DetachDatabase(StateRepository::Database *this, const char *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  char *v9; // rax
  char *v10; // rbx
  int v11; // eax
  int v12; // eax
  const char *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // rdx
  int v16; // edi
  int v17; // r8d
  int v18; // r9d
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF
  const char *v22; // [rsp+70h] [rbp+18h] BYREF
  const char *Filename; // [rsp+78h] [rbp+20h] BYREF

  if ( !*(_QWORD *)this )
  {
    v4 = -2147019873;
    v5 = 443;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v4,
      v19);
    return v4;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 20;
  v9 = (char *)operator new[](v7 + 20, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v4 = -2147024882;
    v5 = 450;
    goto LABEL_3;
  }
  v11 = StringCchPrintfA(v9, v8, "DETACH DATABASE '%s';", a2);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v11,
      v19);
  v12 = StateRepository::Database::Execute(this, v10, 0, 0);
  v14 = v12;
  if ( v12 >= 0 )
  {
    v16 = qword_18004BDF0;
    if ( *(_DWORD *)qword_18004BDF0 > 5u )
    {
      v21 = 0x1000000;
      v22 = a2;
      Filename = StateRepository::Database::GetFilename(this, v13);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v16,
        (unsigned int)&byte_180045A07,
        v17,
        v18,
        (__int64)&Filename,
        (__int64)&v22,
        (__int64)&v21);
    }
    operator delete(v10, (unsigned __int64)v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v12,
      v19);
    operator delete(v10, v15);
    return v14;
  }
}

```

## disassembly

```asm
0x180018ae8  mov     [rsp+arg_8], rbx
0x180018aed  push    rbp
0x180018aee  push    rsi
0x180018aef  push    rdi
0x180018af0  sub     rsp, 40h
0x180018af4  cmp     qword ptr [rcx], 0
0x180018af8  mov     rbp, rdx
0x180018afb  mov     rsi, rcx
0x180018afe  jnz     short loc_180018B25
0x180018b00  mov     ebx, 8007139Fh
0x180018b05  mov     edx, 1BBh; void *
0x180018b0a  mov     rcx, [rsp+58h]; this
0x180018b0f  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018b16  mov     r9d, ebx; char *
0x180018b19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b1e  mov     eax, ebx
0x180018b20  jmp     loc_180018C12
0x180018b25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018b29  inc     rax
0x180018b2c  cmp     byte ptr [rax+rdx], 0
0x180018b30  jnz     short loc_180018B29
0x180018b32  lea     rdi, [rax+14h]
0x180018b36  mov     rcx, rdi; unsigned __int64
0x180018b39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018b40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018b45  mov     rbx, rax
0x180018b48  test    rax, rax
0x180018b4b  jnz     short loc_180018B59
0x180018b4d  mov     ebx, 8007000Eh
0x180018b52  mov     edx, 1C2h
0x180018b57  jmp     short loc_180018B0A
0x180018b59  mov     r9, rbp
0x180018b5c  lea     r8, aDetachDatabase; "DETACH DATABASE '%s';"
0x180018b63  mov     rdx, rdi; unsigned __int64
0x180018b66  mov     rcx, rbx; char *
0x180018b69  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018b6e  test    eax, eax
0x180018b70  js      loc_180018C1F
0x180018b76  xor     r9d, r9d; void *
0x180018b79  xor     r8d, r8d; int (*)(void *)
0x180018b7c  mov     rdx, rbx; char *
0x180018b7f  mov     rcx, rsi; this
0x180018b82  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x180018b87  mov     edi, eax
0x180018b89  test    eax, eax
0x180018b8b  jns     short loc_180018BB2
0x180018b8d  mov     rcx, [rsp+58h]; this
0x180018b92  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018b99  mov     r9d, eax; char *
0x180018b9c  mov     edx, 1C5h; void *
0x180018ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ba6  mov     rcx, rbx; void *
0x180018ba9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018bae  mov     eax, edi
0x180018bb0  jmp     short loc_180018C12
0x180018bb2  mov     rdi, cs:qword_18004BDF0
0x180018bb9  mov     eax, [rdi]
0x180018bbb  cmp     eax, 5
0x180018bbe  jbe     short loc_180018C08
0x180018bc0  mov     rcx, rsi; this
0x180018bc3  mov     [rsp+58h+arg_0], 1000000h
0x180018bcc  mov     [rsp+58h+arg_10], rbp
0x180018bd1  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x180018bd6  mov     [rsp+58h+arg_18], rax
0x180018bdb  lea     rdx, byte_180045A07
0x180018be2  lea     rax, [rsp+58h+arg_0]
0x180018be7  mov     rcx, rdi
0x180018bea  mov     [rsp+58h+var_28], rax
0x180018bef  lea     rax, [rsp+58h+arg_10]
0x180018bf4  mov     [rsp+58h+var_30], rax
0x180018bf9  lea     rax, [rsp+58h+arg_18]
0x180018bfe  mov     [rsp+58h+var_38], rax
0x180018c03  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180018c08  mov     rcx, rbx; void *
0x180018c0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018c10  xor     eax, eax
0x180018c12  mov     rbx, [rsp+58h+arg_8]
0x180018c17  add     rsp, 40h
0x180018c1b  pop     rdi
0x180018c1c  pop     rsi
0x180018c1d  pop     rbp
0x180018c1e  retn
0x180018c1f  mov     rcx, [rsp+58h]; this
0x180018c24  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018c2b  mov     r9d, eax; char *
0x180018c2e  mov     edx, 1C3h; void *
0x180018c33  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

# StateRepository::Database::AttachDatabase(char const *,char const *)

- ea: `0x180018310`
- end: `0x180018493`
- name: `?AttachDatabase@Database@StateRepository@@QEAAJPEBD0@Z`
- size: `387`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180013c40`

## callees

- `0x1800022ec`
- `0x180003d50`
- `0x180007f28`
- `0x18000a3c0`
- `0x180014ca0`
- `0x180018310`
- `0x180018c40`
- `0x180018e80`
- `0x180019adc`

## string_xrefs

- `0x18001833a`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800183ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18001847e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::AttachDatabase(
        StateRepository::Database *this,
        const char *a2,
        const char *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rax
  __int64 v9; // rdi
  char *v10; // rax
  char *v11; // rbx
  int v12; // eax
  int v13; // eax
  const char *v14; // rdx
  unsigned int v15; // edi
  unsigned __int64 v16; // rdx
  int v17; // edi
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+20h] [rbp-58h]
  int v21; // [rsp+20h] [rbp-58h]
  const char *Filename; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  const char *v24; // [rsp+80h] [rbp+8h] BYREF
  __int64 v25; // [rsp+90h] [rbp+18h] BYREF
  const char *v26; // [rsp+98h] [rbp+20h] BYREF

  v25 = (__int64)a3;
  if ( !*(_QWORD *)this )
  {
    v5 = -2147019873;
    v6 = 418;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)v5,
      v20);
    return v5;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = v8 + 36;
  v10 = (char *)operator new[](v8 + 36, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    v6 = 426;
    goto LABEL_3;
  }
  v12 = StringCchPrintfA(v10, v9 + 1, "ATTACH DATABASE '%s' AS '%s';", a2, "Deployment");
  if ( v12 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v12,
      v21);
  v13 = StateRepository::Database::Execute(this, v11, 0, 0);
  v15 = v13;
  if ( v13 >= 0 )
  {
    v17 = qword_18004BDF0;
    if ( *(_DWORD *)qword_18004BDF0 > 5u )
    {
      v25 = 0x1000000;
      v24 = "Deployment";
      v26 = a2;
      Filename = StateRepository::Database::GetFilename(this, v14);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v17,
        (unsigned int)&word_180045A5E,
        v18,
        v19,
        (__int64)&Filename,
        (__int64)&v26,
        (__int64)&v24,
        (__int64)&v25);
    }
    operator delete(v11, (unsigned __int64)v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v13,
      v21);
    operator delete(v11, v16);
    return v15;
  }
}

```

## disassembly

```asm
0x180018310  mov     [rsp+arg_10], r8
0x180018315  push    rbx
0x180018316  push    rbp
0x180018317  push    rsi
0x180018318  push    rdi
0x180018319  push    r14
0x18001831b  sub     rsp, 50h
0x18001831f  cmp     qword ptr [rcx], 0
0x180018323  mov     rbp, rdx
0x180018326  mov     rsi, rcx
0x180018329  jnz     short loc_180018350
0x18001832b  mov     ebx, 8007139Fh
0x180018330  mov     edx, 1A2h; void *
0x180018335  mov     rcx, [rsp+78h]; this
0x18001833a  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018341  mov     r9d, ebx; char *
0x180018344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018349  mov     eax, ebx
0x18001834b  jmp     loc_18001846E
0x180018350  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018354  inc     rax
0x180018357  cmp     byte ptr [rax+rdx], 0
0x18001835b  jnz     short loc_180018354
0x18001835d  lea     rdi, [rax+24h]
0x180018361  mov     rcx, rdi; unsigned __int64
0x180018364  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001836b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018370  mov     rbx, rax
0x180018373  test    rax, rax
0x180018376  jnz     short loc_180018384
0x180018378  mov     ebx, 8007000Eh
0x18001837d  mov     edx, 1AAh
0x180018382  jmp     short loc_180018335
0x180018384  lea     r14, aDeployment; "Deployment"
0x18001838b  mov     r9, rbp
0x18001838e  lea     rdx, [rdi+1]; unsigned __int64
0x180018392  mov     qword ptr [rsp+78h+var_58], r14; int
0x180018397  lea     r8, aAttachDatabase; "ATTACH DATABASE '%s' AS '%s';"
0x18001839e  mov     rcx, rbx; char *
0x1800183a1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800183a6  test    eax, eax
0x1800183a8  js      loc_180018479
0x1800183ae  xor     r9d, r9d; void *
0x1800183b1  xor     r8d, r8d; int (*)(void *)
0x1800183b4  mov     rdx, rbx; char *
0x1800183b7  mov     rcx, rsi; this
0x1800183ba  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800183bf  mov     edi, eax
0x1800183c1  test    eax, eax
0x1800183c3  jns     short loc_1800183ED
0x1800183c5  mov     rcx, [rsp+78h]; this
0x1800183ca  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x1800183d1  mov     r9d, eax; char *
0x1800183d4  mov     edx, 1ADh; void *
0x1800183d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800183de  mov     rcx, rbx; void *
0x1800183e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800183e6  mov     eax, edi
0x1800183e8  jmp     loc_18001846E
0x1800183ed  mov     rdi, cs:qword_18004BDF0
0x1800183f4  mov     eax, [rdi]
0x1800183f6  cmp     eax, 5
0x1800183f9  jbe     short loc_180018464
0x1800183fb  mov     rcx, rsi; this
0x1800183fe  mov     [rsp+78h+arg_10], 1000000h
0x18001840a  mov     [rsp+78h+arg_0], r14
0x180018412  mov     [rsp+78h+arg_18], rbp
0x18001841a  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x18001841f  mov     [rsp+78h+var_38], rax
0x180018424  lea     rdx, word_180045A5E
0x18001842b  lea     rax, [rsp+78h+arg_10]
0x180018433  mov     rcx, rdi
0x180018436  mov     [rsp+78h+var_40], rax
0x18001843b  lea     rax, [rsp+78h+arg_0]
0x180018443  mov     [rsp+78h+var_48], rax
0x180018448  lea     rax, [rsp+78h+arg_18]
0x180018450  mov     [rsp+78h+var_50], rax
0x180018455  lea     rax, [rsp+78h+var_38]
0x18001845a  mov     qword ptr [rsp+78h+var_58], rax
0x18001845f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180018464  mov     rcx, rbx; void *
0x180018467  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001846c  xor     eax, eax
0x18001846e  add     rsp, 50h
0x180018472  pop     r14
0x180018474  pop     rdi
0x180018475  pop     rsi
0x180018476  pop     rbp
0x180018477  pop     rbx
0x180018478  retn
0x180018479  mov     rcx, [rsp+78h]; this
0x18001847e  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018485  mov     r9d, eax; char *
0x180018488  mov     edx, 1ABh; void *
0x18001848d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```

# _lambda_833b25c85b8f0de170b999c5d55c7a66_::operator()(wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>> &)

- ea: `0x1800146e8`
- end: `0x1800148e7`
- name: `??R_lambda_833b25c85b8f0de170b999c5d55c7a66_@@QEBA@AEAV?$unique_ptr@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@U?$default_delete@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@wistd@@@wistd@@@Z`
- size: `511`
- prototype: `_DWORD *__fastcall(__int64, const unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800149c0`

## callees

- `0x18000ac20`
- `0x18000b884`
- `0x1800146e8`
- `0x180015970`
- `0x180016cd8`

## import_xrefs

- `msvcrt!strncat_s` at `0x1800147b3`
- `msvcrt!strncat_s` at `0x1800147de`
- `msvcrt!strncat_s` at `0x180014838`
- `msvcrt!strncat_s` at `0x1800147b3`
- `msvcrt!strncat_s` at `0x1800147de`
- `msvcrt!strncat_s` at `0x180014838`

## string_xrefs

- `0x180014894`: `onecore\internal\sdk\inc\wil\opensource\wil\tracelogging.h`
- `0x1800148ab`: `onecore\internal\sdk\inc\wil\opensource\wil\tracelogging.h`
- `0x1800148d5`: `onecore\internal\sdk\inc\wil\opensource\wil\tracelogging.h`

## pseudocode

```c
_DWORD *__fastcall _lambda_833b25c85b8f0de170b999c5d55c7a66_::operator()(__int64 a1, const unsigned __int16 ***a2)
{
  const unsigned __int16 *ClassStringPointer; // rax
  unsigned __int64 **v5; // rdi
  unsigned __int16 ***v6; // rsi
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r8
  rsize_t v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *result; // rax
  int v21; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)(**(_QWORD **)a1 + 4LL * **(int **)(a1 + 8)) = _InterlockedExchange((volatile __int32 *)(*a2)[3], 0);
  ClassStringPointer = wil::details::ApiTelemetryLogger::ApiDataList::GetClassStringPointer(**a2);
  v5 = (unsigned __int64 **)(a1 + 24);
  v6 = (unsigned __int16 ***)(a1 + 16);
  if ( ClassStringPointer )
  {
    v7 = StringCchCatW(**v6, **v5, ClassStringPointer + 1);
    if ( v7 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x1959, v8, (const char *)(unsigned int)v7, v21);
    v9 = StringCchCatW(**v6, **v5, L".");
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x195A, v10, (const char *)(unsigned int)v9, v21);
  }
  v11 = StringCchCatW(**v6, **v5, (*a2)[1]);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x195D, v12, (const char *)(unsigned int)v11, v21);
  v13 = (const char *)(*a2)[2];
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), v13, v14) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1962,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\tracelogging.h",
        v15);
  }
  else if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), "-", 1u) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1966,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\tracelogging.h",
      v16);
  }
  if ( **(_DWORD **)(a1 + 8) != **(unsigned __int16 **)(a1 + 48) - 1 )
  {
    v17 = StringCchCatW(**v6, **v5, L",");
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x196B, v18, (const char *)(unsigned int)v17, v21);
    if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), ",", 1u) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x196C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\tracelogging.h",
        v19);
  }
  result = *(_DWORD **)(a1 + 8);
  ++*result;
  return result;
}

```

## disassembly

```asm
0x1800146e8  push    rbx
0x1800146ea  push    rsi
0x1800146eb  push    rdi
0x1800146ec  push    r14
0x1800146ee  sub     rsp, 28h
0x1800146f2  mov     rax, [rdx]
0x1800146f5  mov     rbx, rcx
0x1800146f8  xor     r10d, r10d
0x1800146fb  mov     r14, rdx
0x1800146fe  mov     rax, [rax+18h]
0x180014702  xchg    r10d, [rax]
0x180014705  mov     rax, [rcx+8]
0x180014709  movsxd  r9, dword ptr [rax]
0x18001470c  mov     rax, [rcx]
0x18001470f  mov     r8, [rax]
0x180014712  mov     [r8+r9*4], r10d
0x180014716  mov     rcx, [rdx]
0x180014719  mov     rcx, [rcx]; unsigned __int16 *
0x18001471c  call    ?GetClassStringPointer@ApiDataList@ApiTelemetryLogger@details@wil@@CAPEBGPEBG@Z; wil::details::ApiTelemetryLogger::ApiDataList::GetClassStringPointer(ushort const *)
0x180014721  lea     rdi, [rbx+18h]
0x180014725  lea     rsi, [rbx+10h]
0x180014729  test    rax, rax
0x18001472c  jz      short loc_18001476B
0x18001472e  mov     rdx, [rdi]
0x180014731  lea     r8, [rax+2]; unsigned __int16 *
0x180014735  mov     rcx, [rsi]
0x180014738  mov     rdx, [rdx]; unsigned __int64
0x18001473b  mov     rcx, [rcx]; unsigned __int16 *
0x18001473e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014743  test    eax, eax
0x180014745  js      loc_180014856
0x18001474b  mov     rdx, [rdi]
0x18001474e  lea     r8, asc_18005063C; "."
0x180014755  mov     rcx, [rsi]
0x180014758  mov     rdx, [rdx]; unsigned __int64
0x18001475b  mov     rcx, [rcx]; unsigned __int16 *
0x18001475e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014763  test    eax, eax
0x180014765  js      loc_180014869
0x18001476b  mov     r8, [r14]
0x18001476e  mov     rdx, [rdi]
0x180014771  mov     rcx, [rsi]
0x180014774  mov     r8, [r8+8]; unsigned __int16 *
0x180014778  mov     rdx, [rdx]; unsigned __int64
0x18001477b  mov     rcx, [rcx]; unsigned __int16 *
0x18001477e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014783  test    eax, eax
0x180014785  js      loc_18001487C
0x18001478b  mov     rax, [r14]
0x18001478e  mov     r8, [rax+10h]; Source
0x180014792  test    r8, r8
0x180014795  jz      short loc_1800147C3
0x180014797  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001479b  inc     r9; MaxCount
0x18001479e  cmp     byte ptr [r8+r9], 0
0x1800147a3  jnz     short loc_18001479B
0x1800147a5  mov     rdx, [rbx+28h]
0x1800147a9  mov     rcx, [rbx+20h]
0x1800147ad  mov     rdx, [rdx]; SizeInBytes
0x1800147b0  mov     rcx, [rcx]; Destination
0x1800147b3  call    cs:__imp_strncat_s
0x1800147b9  test    eax, eax
0x1800147bb  jnz     loc_18001488F
0x1800147c1  jmp     short loc_1800147EC
0x1800147c3  mov     rdx, [rbx+28h]
0x1800147c7  lea     r8, Source; "-"
0x1800147ce  mov     rcx, [rbx+20h]
0x1800147d2  mov     r9d, 1; MaxCount
0x1800147d8  mov     rdx, [rdx]; SizeInBytes
0x1800147db  mov     rcx, [rcx]; Destination
0x1800147de  call    cs:__imp_strncat_s
0x1800147e4  test    eax, eax
0x1800147e6  jnz     loc_1800148A6
0x1800147ec  mov     rax, [rbx+30h]
0x1800147f0  movzx   ecx, word ptr [rax]
0x1800147f3  mov     rax, [rbx+8]
0x1800147f7  dec     ecx
0x1800147f9  cmp     [rax], ecx
0x1800147fb  jz      short loc_180014846
0x1800147fd  mov     rdx, [rdi]
0x180014800  lea     r8, asc_180050644; ","
0x180014807  mov     rcx, [rsi]
0x18001480a  mov     rdx, [rdx]; unsigned __int64
0x18001480d  mov     rcx, [rcx]; unsigned __int16 *
0x180014810  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014815  test    eax, eax
0x180014817  js      loc_1800148BD
0x18001481d  mov     rdx, [rbx+28h]
0x180014821  lea     r8, asc_180050648; ","
0x180014828  mov     rcx, [rbx+20h]
0x18001482c  mov     r9d, 1; MaxCount
0x180014832  mov     rdx, [rdx]; SizeInBytes
0x180014835  mov     rcx, [rcx]; Destination
0x180014838  call    cs:__imp_strncat_s
0x18001483e  test    eax, eax
0x180014840  jnz     loc_1800148D0
0x180014846  mov     rax, [rbx+8]
0x18001484a  inc     dword ptr [rax]
0x18001484c  add     rsp, 28h
0x180014850  pop     r14
0x180014852  pop     rdi
0x180014853  pop     rsi
0x180014854  pop     rbx
0x180014855  retn
0x180014856  mov     rcx, [rsp+48h]; this
0x18001485b  mov     r9d, eax; char *
0x18001485e  mov     edx, 1959h; void *
0x180014863  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014869  mov     rcx, [rsp+48h]; this
0x18001486e  mov     r9d, eax; char *
0x180014871  mov     edx, 195Ah; void *
0x180014876  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001487c  mov     rcx, [rsp+48h]; this
0x180014881  mov     r9d, eax; char *
0x180014884  mov     edx, 195Dh; void *
0x180014889  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001488f  mov     rcx, [rsp+48h]; this
0x180014894  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001489b  mov     edx, 1962h; void *
0x1800148a0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800148a6  mov     rcx, [rsp+48h]; this
0x1800148ab  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800148b2  mov     edx, 1966h; void *
0x1800148b7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800148bd  mov     rcx, [rsp+48h]; this
0x1800148c2  mov     r9d, eax; char *
0x1800148c5  mov     edx, 196Bh; void *
0x1800148ca  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800148d0  mov     rcx, [rsp+48h]; this
0x1800148d5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800148dc  mov     edx, 196Ch; void *
0x1800148e1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

# `wil::details::ApiTelemetryLogger::ApiDataList::Flush(wistd::function<void (ushort const *,ushort const *,char const *,uint *,ushort)>)'::`7'::_lambda_2_::operator()(wistd::unique_ptr<wil::details::ApiTelemetryLogger::ApiDataList::ApiData,wistd::default_delete<wil::details::ApiTelemetryLogger::ApiDataList::ApiData>> &)

- ea: `0x1800432cc`
- end: `0x1800434df`
- name: `??R_lambda_2_@?6??Flush@ApiDataList@ApiTelemetryLogger@details@wil@@QEAAXV?$function@$$A6AXPEBG0PEBDPEAIG@Z@wistd@@@Z@QEBA@AEAV?$unique_ptr@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@U?$default_delete@UApiData@ApiDataList@ApiTelemetryLogger@details@wil@@@wistd@@@7@@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e8200`

## callees

- `0x1800431b4`
- `0x1800432cc`
- `0x1800434e8`
- `0x1800e08a0`
- `0x1800f8e54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800433a8`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180043418`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180043452`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800433a8`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180043418`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180043452`

## string_xrefs

- `0x180043333`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x18004336a`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x1800433e8`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x180043465`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x18004349c`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x1800434b6`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`
- `0x1800434cd`: `onecore\internal\sdk\inc\wil\opensource/wil/tracelogging.h`

## pseudocode

```c
_DWORD *__fastcall `wil::details::ApiTelemetryLogger::ApiDataList::Flush'::`7'::_lambda_2_::operator()(
        __int64 a1,
        const unsigned __int16 ***a2)
{
  const unsigned __int16 *ClassStringPointer; // rax
  unsigned __int64 **v5; // rdi
  unsigned __int16 ***v6; // rsi
  int v7; // eax
  int v8; // eax
  const char *v9; // r8
  const char *v10; // r9
  int v11; // eax
  const char *v12; // r9
  _DWORD *result; // rax
  rsize_t v14; // r9
  const char *v15; // r9
  int v16; // eax
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)(**(_QWORD **)a1 + 4LL * **(int **)(a1 + 8)) = _InterlockedExchange((volatile __int32 *)(*a2)[3], 0);
  ClassStringPointer = wil::details::ApiTelemetryLogger::ApiDataList::GetClassStringPointer(**a2);
  v5 = (unsigned __int64 **)(a1 + 24);
  v6 = (unsigned __int16 ***)(a1 + 16);
  if ( ClassStringPointer )
  {
    v8 = StringCchCatW(**v6, **v5, ClassStringPointer + 1);
    if ( v8 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1959,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
        (const char *)(unsigned int)v8,
        v17);
    v16 = StringCchCatW(**v6, **v5, L".");
    if ( v16 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x195A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
        (const char *)(unsigned int)v16,
        v17);
  }
  v7 = StringCchCatW(**v6, **v5, (*a2)[1]);
  if ( v7 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x195D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
      (const char *)(unsigned int)v7,
      v17);
  v9 = (const char *)(*a2)[2];
  if ( v9 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v9[v14] );
    if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), v9, v14) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1962,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
        v15);
  }
  else if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), "-", 1u) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1966,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
      v10);
  }
  if ( **(_DWORD **)(a1 + 8) != **(unsigned __int16 **)(a1 + 48) - 1 )
  {
    v11 = StringCchCatW(**v6, **v5, L",");
    if ( v11 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x196B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
        (const char *)(unsigned int)v11,
        v17);
    if ( strncat_s(**(char ***)(a1 + 32), **(_QWORD **)(a1 + 40), ",", 1u) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x196C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/tracelogging.h",
        v12);
  }
  result = *(_DWORD **)(a1 + 8);
  ++*result;
  return result;
}

```

## disassembly

```asm
0x1800432cc  push    rbx
0x1800432ce  push    rsi
0x1800432cf  push    rdi
0x1800432d0  push    r14
0x1800432d2  sub     rsp, 28h
0x1800432d6  mov     rax, [rdx]
0x1800432d9  mov     rbx, rcx
0x1800432dc  xor     r10d, r10d
0x1800432df  mov     r14, rdx
0x1800432e2  mov     rax, [rax+18h]
0x1800432e6  xchg    r10d, [rax]
0x1800432e9  mov     rax, [rcx+8]
0x1800432ed  movsxd  r9, dword ptr [rax]
0x1800432f0  mov     rax, [rcx]
0x1800432f3  mov     r8, [rax]
0x1800432f6  mov     [r8+r9*4], r10d
0x1800432fa  mov     rcx, [rdx]
0x1800432fd  mov     rcx, [rcx]; unsigned __int16 *
0x180043300  call    ?GetClassStringPointer@ApiDataList@ApiTelemetryLogger@details@wil@@CAPEBGPEBG@Z; wil::details::ApiTelemetryLogger::ApiDataList::GetClassStringPointer(ushort const *)
0x180043305  lea     rdi, [rbx+18h]
0x180043309  lea     rsi, [rbx+10h]
0x18004330d  test    rax, rax
0x180043310  jnz     short loc_180043348
0x180043312  mov     r8, [r14]
0x180043315  mov     rdx, [rdi]
0x180043318  mov     rcx, [rsi]
0x18004331b  mov     r8, [r8+8]; unsigned __int16 *
0x18004331f  mov     rdx, [rdx]; unsigned __int64
0x180043322  mov     rcx, [rcx]; unsigned __int16 *
0x180043325  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004332a  test    eax, eax
0x18004332c  jns     short loc_18004337F
0x18004332e  mov     rcx, [rsp+48h]; this
0x180043333  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004333a  mov     r9d, eax; char *
0x18004333d  mov     edx, 195Dh; void *
0x180043342  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180043348  mov     rdx, [rdi]
0x18004334b  lea     r8, [rax+2]; unsigned __int16 *
0x18004334f  mov     rcx, [rsi]
0x180043352  mov     rdx, [rdx]; unsigned __int64
0x180043355  mov     rcx, [rcx]; unsigned __int16 *
0x180043358  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004335d  test    eax, eax
0x18004335f  jns     loc_180043477
0x180043365  mov     rcx, [rsp+48h]; this
0x18004336a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180043371  mov     r9d, eax; char *
0x180043374  mov     edx, 1959h; void *
0x180043379  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004337f  mov     rax, [r14]
0x180043382  mov     r8, [rax+10h]; Source
0x180043386  test    r8, r8
0x180043389  jnz     loc_180043436
0x18004338f  mov     rdx, [rbx+28h]
0x180043393  lea     r9d, [r8+1]; MaxCount
0x180043397  mov     rcx, [rbx+20h]
0x18004339b  lea     r8, Source; "-"
0x1800433a2  mov     rdx, [rdx]; SizeInBytes
0x1800433a5  mov     rcx, [rcx]; Destination
0x1800433a8  call    cs:__imp_strncat_s
0x1800433ae  test    eax, eax
0x1800433b0  jnz     loc_1800434B1
0x1800433b6  mov     rax, [rbx+30h]
0x1800433ba  movzx   ecx, word ptr [rax]
0x1800433bd  mov     rax, [rbx+8]
0x1800433c1  dec     ecx
0x1800433c3  cmp     [rax], ecx
0x1800433c5  jz      short loc_180043426
0x1800433c7  mov     rdx, [rdi]
0x1800433ca  lea     r8, pszSrc; ","
0x1800433d1  mov     rcx, [rsi]
0x1800433d4  mov     rdx, [rdx]; unsigned __int64
0x1800433d7  mov     rcx, [rcx]; unsigned __int16 *
0x1800433da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800433df  test    eax, eax
0x1800433e1  jns     short loc_1800433FD
0x1800433e3  mov     rcx, [rsp+48h]; this
0x1800433e8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800433ef  mov     r9d, eax; char *
0x1800433f2  mov     edx, 196Bh; void *
0x1800433f7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800433fd  mov     rdx, [rbx+28h]
0x180043401  lea     r8, asc_1801B1F78; ","
0x180043408  mov     rcx, [rbx+20h]
0x18004340c  mov     r9d, 1; MaxCount
0x180043412  mov     rdx, [rdx]; SizeInBytes
0x180043415  mov     rcx, [rcx]; Destination
0x180043418  call    cs:__imp_strncat_s
0x18004341e  test    eax, eax
0x180043420  jnz     loc_1800434C8
0x180043426  mov     rax, [rbx+8]
0x18004342a  inc     dword ptr [rax]
0x18004342c  add     rsp, 28h
0x180043430  pop     r14
0x180043432  pop     rdi
0x180043433  pop     rsi
0x180043434  pop     rbx
0x180043435  retn
0x180043436  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004343a  inc     r9; MaxCount
0x18004343d  cmp     byte ptr [r8+r9], 0
0x180043442  jnz     short loc_18004343A
0x180043444  mov     rdx, [rbx+28h]
0x180043448  mov     rcx, [rbx+20h]
0x18004344c  mov     rdx, [rdx]; SizeInBytes
0x18004344f  mov     rcx, [rcx]; Destination
0x180043452  call    cs:__imp_strncat_s
0x180043458  test    eax, eax
0x18004345a  jz      loc_1800433B6
0x180043460  mov     rcx, [rsp+48h]; this
0x180043465  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004346c  mov     edx, 1962h; void *
0x180043471  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180043477  mov     rdx, [rdi]
0x18004347a  lea     r8, asc_1801B27A0; "."
0x180043481  mov     rcx, [rsi]
0x180043484  mov     rdx, [rdx]; unsigned __int64
0x180043487  mov     rcx, [rcx]; unsigned __int16 *
0x18004348a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004348f  test    eax, eax
0x180043491  jns     loc_180043312
0x180043497  mov     rcx, [rsp+48h]; this
0x18004349c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800434a3  mov     r9d, eax; char *
0x1800434a6  mov     edx, 195Ah; void *
0x1800434ab  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800434b1  mov     rcx, [rsp+48h]; this
0x1800434b6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800434bd  mov     edx, 1966h; void *
0x1800434c2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800434c8  mov     rcx, [rsp+48h]; this
0x1800434cd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800434d4  mov     edx, 196Ch; void *
0x1800434d9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

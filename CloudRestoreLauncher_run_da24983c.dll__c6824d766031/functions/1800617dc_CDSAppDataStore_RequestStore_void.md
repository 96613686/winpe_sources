# CDSAppDataStore::RequestStore(void)

- ea: `0x1800617dc`
- end: `0x180061890`
- name: `?RequestStore@CDSAppDataStore@@SA?AV?$shared_ptr@UIRestorableAppDataStore@@@std@@XZ`
- size: `180`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180068b18`
- `0x180068bc4`
- `0x18006ceec`

## callees

- `0x18001c180`
- `0x18005ec74`
- `0x1800617dc`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180061836`
- `KERNEL32!InitOnceComplete` at `0x180061836`
- `KERNEL32!InitOnceBeginInitialize` at `0x180061805`
- `KERNEL32!InitOnceBeginInitialize` at `0x180061805`

## string_xrefs

- `0x18006187e`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
_QWORD *__fastcall CDSAppDataStore::RequestStore(_QWORD *a1)
{
  const char *v2; // r9
  std::_Ref_count_base *v3; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  WINBOOL fPending; // [rsp+58h] [rbp+10h] BYREF

  fPending = 0;
  if ( !InitOnceBeginInitialize(&CDSAppDataStore::s_singletonInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      v2);
  if ( fPending )
  {
    lambda_a57f3f243c1cd74e21d7912ed4a0114f_::operator()(retaddr);
    InitOnceComplete(&CDSAppDataStore::s_singletonInitOnce, 0, 0);
  }
  *a1 = 0;
  a1[1] = 0;
  v3 = qword_18017AD70;
  if ( qword_18017AD70 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_18017AD70 + 2);
    v3 = qword_18017AD70;
  }
  *a1 = CDSAppDataStore::s_cdsAppDataStore;
  a1[1] = v3;
  return a1;
}

```

## disassembly

```asm
0x1800617dc  mov     [rsp+arg_0], rbx
0x1800617e1  push    rsi
0x1800617e2  sub     rsp, 40h
0x1800617e6  mov     rbx, rcx
0x1800617e9  mov     [rsp+48h+fPending], 0
0x1800617f1  xor     r9d, r9d; lpContext
0x1800617f4  lea     r8, [rsp+48h+fPending]; fPending
0x1800617f9  xor     edx, edx; dwFlags
0x1800617fb  lea     rsi, ?s_singletonInitOnce@CDSAppDataStore@@0T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE CDSAppDataStore::s_singletonInitOnce
0x180061802  mov     rcx, rsi; lpInitOnce
0x180061805  call    cs:__imp_InitOnceBeginInitialize
0x18006180b  mov     rcx, [rsp+48h]; this
0x180061810  test    eax, eax
0x180061812  jz      short loc_18006187E
0x180061814  cmp     [rsp+48h+fPending], 0
0x180061819  jz      short loc_18006183C
0x18006181b  mov     [rsp+48h+var_20], rsi
0x180061820  mov     [rsp+48h+var_18], 4
0x180061828  call    _lambda_a57f3f243c1cd74e21d7912ed4a0114f___operator__
0x18006182d  nop
0x18006182e  xor     r8d, r8d; lpContext
0x180061831  xor     edx, edx; dwFlags
0x180061833  mov     rcx, rsi; lpInitOnce
0x180061836  call    cs:__imp_InitOnceComplete
0x18006183c  mov     qword ptr [rbx], 0
0x180061843  mov     qword ptr [rbx+8], 0
0x18006184b  mov     rcx, cs:qword_18017AD70
0x180061852  test    rcx, rcx
0x180061855  jz      short loc_180061862
0x180061857  lock inc dword ptr [rcx+8]
0x18006185b  mov     rcx, cs:qword_18017AD70
0x180061862  mov     rax, cs:?s_cdsAppDataStore@CDSAppDataStore@@0V?$shared_ptr@VCDSAppDataStore@@@std@@A; std::shared_ptr<CDSAppDataStore> CDSAppDataStore::s_cdsAppDataStore
0x180061869  mov     [rbx], rax
0x18006186c  mov     [rbx+8], rcx
0x180061870  mov     rax, rbx
0x180061873  mov     rbx, [rsp+48h+arg_0]
0x180061878  add     rsp, 40h
0x18006187c  pop     rsi
0x18006187d  retn
0x18006187e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180061885  mov     edx, 3BCh; void *
0x18006188a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

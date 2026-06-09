# wil::WaitForDebuggerPresent(bool)

- ea: `0x1800184dc`
- end: `0x180018562`
- name: `?WaitForDebuggerPresent@wil@@YAX_N@Z`
- size: `134`
- prototype: `void __fastcall(wil *__hidden this, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001815c`
- `0x18001fd60`

## callees

- `0x1800148d0`
- `0x180017db0`
- `0x1800184dc`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018533`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018533`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180018542`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180018542`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018524`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018524`

## string_xrefs

- `0x180018550`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall wil::WaitForDebuggerPresent(wil *this, const unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  int CurrentProcessExecutionOptionNoThrow; // eax
  bool v5; // zf
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF

  LOBYTE(v8) = (_BYTE)this;
  while ( 1 )
  {
    v8 = 1;
    CurrentProcessExecutionOptionNoThrow = wil::details::GetCurrentProcessExecutionOptionNoThrow(this, a2, &v8, a4);
    if ( CurrentProcessExecutionOptionNoThrow < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)CurrentProcessExecutionOptionNoThrow,
        v6);
    if ( !v8 )
      break;
    if ( wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (v5 = !IsDebuggerPresent())
        : (v5 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(retaddr) == 0),
          !v5) )
    {
      if ( v8 == 2 )
        DebugBreak();
      return;
    }
    Sleep(0x1F4u);
  }
}

```

## disassembly

```asm
0x1800184dc  mov     byte ptr [rsp+arg_0], cl
0x1800184e0  sub     rsp, 28h
0x1800184e4  lea     r8, [rsp+28h+arg_0]; unsigned int
0x1800184e9  mov     [rsp+28h+arg_0], 1
0x1800184f1  call    ?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z; wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)
0x1800184f6  mov     rcx, [rsp+28h]; this
0x1800184fb  test    eax, eax
0x1800184fd  js      short loc_18001854D
0x1800184ff  cmp     [rsp+28h+arg_0], 0
0x180018504  jz      short loc_180018548
0x180018506  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18001850d  jnz     short loc_18001853B
0x18001850f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180018516  test    rax, rax
0x180018519  jz      short loc_180018524
0x18001851b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018520  test    al, al
0x180018522  jmp     short loc_18001852C
0x180018524  call    cs:__imp_IsDebuggerPresent
0x18001852a  test    eax, eax
0x18001852c  jnz     short loc_18001853B
0x18001852e  mov     ecx, 1F4h; dwMilliseconds
0x180018533  call    cs:__imp_Sleep
0x180018539  jmp     short loc_1800184E4
0x18001853b  cmp     [rsp+28h+arg_0], 2
0x180018540  jnz     short loc_180018548
0x180018542  call    cs:__imp_DebugBreak
0x180018548  add     rsp, 28h
0x18001854c  retn
0x18001854d  mov     r9d, eax; char *
0x180018550  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018557  mov     edx, 1CBEh; void *
0x18001855c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

# AsyncAction<NTPSync>::Run(ulong)

- ea: `0x18000cfec`
- end: `0x18000d04b`
- name: `?Run@?$AsyncAction@VNTPSync@@@@QEAAJK@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000d178`

## callees

- `0x180009194`
- `0x18000cfec`
- `0x18000d640`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d01e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d01e`

## string_xrefs

- `0x18000d00b`: `onecore\base\time\autotime\timeservice\ntpsynchelper.h`

## pseudocode

```c
__int64 __fastcall AsyncAction<NTPSync>::Run(__int64 a1)
{
  struct _TP_WORK *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(struct _TP_WORK **)(a1 + 24);
  if ( !v2 )
  {
    v3 = -2147467261;
    v4 = 36;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"onecore\\base\\time\\autotime\\timeservice\\ntpsynchelper.h",
      (const char *)v3);
    return v3;
  }
  SubmitThreadpoolWork(v2);
  if ( !(unsigned __int8)wil::slim_event_t<1>::wait(a1 + 20, 720000) )
  {
    v3 = -2147023436;
    v4 = 42;
    goto LABEL_3;
  }
  return *(unsigned int *)(a1 + 16);
}

```

## disassembly

```asm
0x18000cfec  push    rbx; int
0x18000cfee  sub     rsp, 20h
0x18000cff2  mov     rbx, rcx
0x18000cff5  mov     rcx, [rcx+18h]; pwk
0x18000cff9  test    rcx, rcx
0x18000cffc  jnz     short loc_18000D01E
0x18000cffe  mov     ebx, 80004003h
0x18000d003  lea     edx, [rcx+24h]; void *
0x18000d006  mov     rcx, [rsp+28h]; this
0x18000d00b  lea     r8, aOnecoreBaseTim_0; "onecore\\base\\time\\autotime\\timeserv"...
0x18000d012  mov     r9d, ebx; char *
0x18000d015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d01a  mov     eax, ebx
0x18000d01c  jmp     short loc_18000D045
0x18000d01e  call    cs:__imp_SubmitThreadpoolWork
0x18000d024  lea     rcx, [rbx+14h]
0x18000d028  mov     edx, 0AFC80h
0x18000d02d  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x18000d032  test    al, al
0x18000d034  jnz     short loc_18000D042
0x18000d036  mov     ebx, 800705B4h
0x18000d03b  mov     edx, 2Ah ; '*'
0x18000d040  jmp     short loc_18000D006
0x18000d042  mov     eax, [rbx+10h]
0x18000d045  add     rsp, 20h
0x18000d049  pop     rbx
0x18000d04a  retn
```

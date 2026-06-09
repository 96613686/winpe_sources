# CTPtrSList<CLinkWithTime>::Append(CLinkWithTime *)

- ea: `0x180019f6c`
- end: `0x180019fe1`
- name: `?Append@?$CTPtrSList@VCLinkWithTime@@@@QEAAXPEAVCLinkWithTime@@@Z`
- size: `117`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001947c`
- `0x180019578`
- `0x18001981c`
- `0x1800198ac`
- `0x18001993c`
- `0x180019bd8`
- `0x180019c88`
- `0x180019fe8`
- `0x18001a05c`
- `0x18001afa8`
- `0x18001bde4`
- `0x18001f7c0`

## callees

- `0x180002780`
- `0x18000da40`
- `0x180019f6c`
- `0x18002b784`

## string_xrefs

- `0x180019fc9`: `onecoreuap\base\appmodel\Search\common\include\tpslist.hxx`

## pseudocode

```c
void __fastcall CTPtrSList<CLinkWithTime>::Append(__int64 a1, __int64 a2)
{
  struct CSingleLink *v4; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (struct CSingleLink *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\tpslist.hxx",
      (const char *)0x8007000ELL,
      v5);
  *(_QWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 1) = a2;
  CLnkList::InsertAfter((CLnkList *)(a1 + 8), *(struct CSingleLink **)(a1 + 24), v4);
}

```

## disassembly

```asm
0x180019f6c  mov     [rsp+arg_8], rbx
0x180019f71  push    rdi; int
0x180019f72  sub     rsp, 20h
0x180019f76  mov     rbx, rdx
0x180019f79  mov     rdi, rcx
0x180019f7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019f83  mov     ecx, 10h; unsigned __int64
0x180019f88  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019f8d  mov     [rsp+28h+arg_0], rax
0x180019f92  test    rax, rax
0x180019f95  jz      short loc_180019FC4
0x180019f97  mov     qword ptr [rax], 0
0x180019f9e  lea     rcx, [rdi+8]; this
0x180019fa2  mov     qword ptr [rax+8], 0
0x180019faa  mov     r8, rax; struct CSingleLink *
0x180019fad  mov     [rax+8], rbx
0x180019fb1  mov     rdx, [rcx+10h]; struct CSingleLink *
0x180019fb5  mov     rbx, [rsp+28h+arg_8]
0x180019fba  add     rsp, 20h
0x180019fbe  pop     rdi
0x180019fbf  jmp     ?InsertAfter@CLnkList@@IEAAXPEAVCSingleLink@@0@Z; CLnkList::InsertAfter(CSingleLink *,CSingleLink *)
0x180019fc4  mov     rcx, [rsp+28h]; this
0x180019fc9  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180019fd0  mov     r9d, 8007000Eh; char *
0x180019fd6  mov     edx, 13Dh; void *
0x180019fdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

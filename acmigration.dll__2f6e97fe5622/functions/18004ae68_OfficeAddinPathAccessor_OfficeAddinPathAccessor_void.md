# OfficeAddinPathAccessor::OfficeAddinPathAccessor(void)

- ea: `0x18004ae68`
- end: `0x18004af50`
- name: `??0OfficeAddinPathAccessor@@AEAA@XZ`
- size: `232`
- prototype: `OfficeAddinPathAccessor *__fastcall(OfficeAddinPathAccessor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004b0d8`

## callees

- `0x1800474b4`
- `0x18004ae68`
- `0x18004b1bc`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18004ae9f`
- `KERNEL32!GetTickCount` at `0x18004aeb7`
- `KERNEL32!GetTickCount` at `0x18004ae9f`
- `KERNEL32!GetTickCount` at `0x18004aeb7`

## string_xrefs

- `0x18004aeda`: `OfficeAddinPathAccessor initialization: %d add-in is loaded in %d ms.`
- `0x18004aee7`: `OfficeAddinPathAccessor::OfficeAddinPathAccessor`
- `0x18004af23`: `OfficeAddinPathAccessor::OfficeAddinPathAccessor`
- `0x18004af16`: `[Office Addin Path Loaded] %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
OfficeAddinPathAccessor *__fastcall OfficeAddinPathAccessor::OfficeAddinPathAccessor(OfficeAddinPathAccessor *this)
{
  double TickCount; // xmm6_8
  signed int v3; // eax
  _QWORD *v4; // rsi
  _QWORD *i; // rbx
  _QWORD *v6; // rax

  *(_QWORD *)this = &OfficeAddinPathAccessor::`vftable';
  std::unordered_set<std::wstring>::unordered_set<std::wstring>((char *)this + 8);
  TickCount = (double)(int)GetTickCount();
  OfficeAddinPathAccessor::Init(this);
  v3 = GetTickCount();
  AslLogCallPrintf(
    3,
    "OfficeAddinPathAccessor::OfficeAddinPathAccessor",
    43,
    "OfficeAddinPathAccessor initialization: %d add-in is loaded in %d ms.",
    *((_DWORD *)this + 6),
    (int)((double)v3 - TickCount));
  v4 = (_QWORD *)*((_QWORD *)this + 2);
  for ( i = (_QWORD *)*v4; i != v4; i = (_QWORD *)*i )
  {
    v6 = i + 2;
    if ( i[5] > 7u )
      v6 = (_QWORD *)*v6;
    AslLogCallPrintf(3, "OfficeAddinPathAccessor::OfficeAddinPathAccessor", 47, "[Office Addin Path Loaded] %ws", v6);
  }
  return this;
}

```

## disassembly

```asm
0x18004ae68  mov     rax, rsp
0x18004ae6b  mov     [rax+8], rcx
0x18004ae6f  push    rdi
0x18004ae70  sub     rsp, 50h
0x18004ae74  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18004ae7c  mov     [rax+10h], rbx
0x18004ae80  mov     [rax+18h], rsi
0x18004ae84  movaps  xmmword ptr [rax-18h], xmm6
0x18004ae88  mov     rdi, rcx
0x18004ae8b  lea     rax, ??_7OfficeAddinPathAccessor@@6B@; const OfficeAddinPathAccessor::`vftable'
0x18004ae92  mov     [rcx], rax
0x18004ae95  add     rcx, 8
0x18004ae99  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18004ae9e  nop
0x18004ae9f  call    cs:__imp_GetTickCount
0x18004aea5  mov     eax, eax
0x18004aea7  xorps   xmm6, xmm6
0x18004aeaa  cvtsi2sd xmm6, rax
0x18004aeaf  mov     rcx, rdi; this
0x18004aeb2  call    ?Init@OfficeAddinPathAccessor@@AEAAXXZ; OfficeAddinPathAccessor::Init(void)
0x18004aeb7  call    cs:__imp_GetTickCount
0x18004aebd  mov     eax, eax
0x18004aebf  xorps   xmm0, xmm0
0x18004aec2  cvtsi2sd xmm0, rax
0x18004aec7  subsd   xmm0, xmm6
0x18004aecb  cvttsd2si eax, xmm0
0x18004aecf  mov     [rsp+58h+var_30], eax
0x18004aed3  mov     eax, [rdi+18h]
0x18004aed6  mov     dword ptr [rsp+58h+var_38], eax
0x18004aeda  lea     r9, aOfficeaddinpat_0; "OfficeAddinPathAccessor initialization:"...
0x18004aee1  mov     r8d, 2Bh ; '+'
0x18004aee7  lea     rdx, aOfficeaddinpat; "OfficeAddinPathAccessor::OfficeAddinPat"...
0x18004aeee  lea     ecx, [r8-28h]
0x18004aef2  call    AslLogCallPrintf
0x18004aef7  mov     rsi, [rdi+10h]
0x18004aefb  mov     rbx, [rsi]
0x18004aefe  cmp     rbx, rsi
0x18004af01  jz      short loc_18004AF38
0x18004af03  lea     rax, [rbx+10h]
0x18004af07  cmp     qword ptr [rbx+28h], 7
0x18004af0c  jbe     short loc_18004AF11
0x18004af0e  mov     rax, [rax]
0x18004af11  mov     [rsp+58h+var_38], rax
0x18004af16  lea     r9, aOfficeAddinPat; "[Office Addin Path Loaded] %ws"
0x18004af1d  mov     r8d, 2Fh ; '/'
0x18004af23  lea     rdx, aOfficeaddinpat; "OfficeAddinPathAccessor::OfficeAddinPat"...
0x18004af2a  lea     ecx, [r8-2Ch]
0x18004af2e  call    AslLogCallPrintf
0x18004af33  mov     rbx, [rbx]
0x18004af36  jmp     short loc_18004AEFE
0x18004af38  mov     rax, rdi
0x18004af3b  mov     rbx, [rsp+58h+arg_8]
0x18004af40  mov     rsi, [rsp+58h+arg_10]
0x18004af45  movaps  xmm6, [rsp+58h+var_18]
0x18004af4a  add     rsp, 50h
0x18004af4e  pop     rdi
0x18004af4f  retn
```

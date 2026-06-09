# CEnumStreamMapBase::~CEnumStreamMapBase(void)

- ea: `0x1800aaa90`
- end: `0x1800aab4c`
- name: `??1CEnumStreamMapBase@@UEAA@XZ`
- size: `188`
- prototype: `void __fastcall(CEnumStreamMapBase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800aa990`
- `0x1800aaa10`
- `0x1800aabe0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x18002d514`
- `0x1800aaa90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aab24`

## pseudocode

```c
void __fastcall CEnumStreamMapBase::~CEnumStreamMapBase(CEnumStreamMapBase *this)
{
  __int64 **v2; // rdi
  __int64 v3; // rcx
  LPVOID *v4; // rbx
  __int64 *v5; // rax
  __int64 *v6; // rdx
  char v7; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CEnumStreamMapBase::`vftable';
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v7, "CEnumStreamMapBase::~CEnumStreamMapBase", 107);
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 12, WPP_3461acf4a3093ec85b4914ae9289c173_Traceguids, this);
  v2 = (__int64 **)((char *)this + 32);
  while ( 1 )
  {
    v6 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v3 = *v6;
    v4 = (LPVOID *)(v6 - 4);
    v5 = (__int64 *)v6[1];
    *v5 = *v6;
    *(_QWORD *)(v3 + 8) = v5;
    CoTaskMemFree((LPVOID)*(v6 - 3));
    CoTaskMemFree(v4[3]);
    CoTaskMemFree(v4);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v7);
}

```

## disassembly

```asm
0x1800aaa90  mov     [rsp+arg_8], rbx
0x1800aaa95  push    rdi
0x1800aaa96  sub     rsp, 20h
0x1800aaa9a  lea     rax, ??_7CEnumStreamMapBase@@6B@; const CEnumStreamMapBase::`vftable'
0x1800aaaa1  mov     rdi, rcx
0x1800aaaa4  mov     [rcx], rax
0x1800aaaa7  lea     rdx, aCenumstreammap_1; "CEnumStreamMapBase::~CEnumStreamMapBase"
0x1800aaaae  lea     rcx, [rsp+28h+arg_0]; this
0x1800aaab3  mov     r8d, 6Bh ; 'k'; int
0x1800aaab9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aaabe  cmp     cs:byte_1800EACCB, 8
0x1800aaac5  jb      short loc_1800AAAE9
0x1800aaac7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaace  lea     r8, WPP_3461acf4a3093ec85b4914ae9289c173_Traceguids
0x1800aaad5  mov     edx, 0Ch
0x1800aaada  mov     r9, rdi
0x1800aaadd  mov     rcx, [rcx+88h]
0x1800aaae4  call    WPP_SF_q
0x1800aaae9  add     rdi, 20h ; ' '
0x1800aaaed  jmp     short loc_1800AAB30
0x1800aaaef  mov     rcx, [rdx]
0x1800aaaf2  lea     rbx, [rdx-20h]
0x1800aaaf6  mov     rax, [rdx+8]
0x1800aaafa  mov     [rax], rcx
0x1800aaafd  mov     [rcx+8], rax
0x1800aab01  mov     rcx, [rbx+8]; pv
0x1800aab05  call    cs:__imp_CoTaskMemFree
0x1800aab0c  nop     dword ptr [rax+rax+00h]
0x1800aab11  mov     rcx, [rbx+18h]; pv
0x1800aab15  call    cs:__imp_CoTaskMemFree
0x1800aab1c  nop     dword ptr [rax+rax+00h]
0x1800aab21  mov     rcx, rbx; pv
0x1800aab24  call    cs:__imp_CoTaskMemFree
0x1800aab2b  nop     dword ptr [rax+rax+00h]
0x1800aab30  mov     rdx, [rdi]
0x1800aab33  cmp     rdx, rdi
0x1800aab36  jnz     short loc_1800AAAEF
0x1800aab38  lea     rcx, [rsp+28h+arg_0]; this
0x1800aab3d  mov     rbx, [rsp+28h+arg_8]
0x1800aab42  add     rsp, 20h
0x1800aab46  pop     rdi
0x1800aab47  jmp     ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
```

# IFilterImpl<CMapi2DirFilter>::SetValueChunk(CLMString const &)

- ea: `0x1800258c0`
- end: `0x180025958`
- name: `?SetValueChunk@?$IFilterImpl@VCMapi2DirFilter@@@@IEAAXAEBVCLMString@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023ba0`

## callees

- `0x1800227a0`
- `0x1800258c0`
- `0x1800299d4`
- `0x18003a0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800258e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800258e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025942`

## string_xrefs

- `0x1800258f8`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IFilterImpl<CMapi2DirFilter>::SetValueChunk(__int64 a1, __int64 a2)
{
  SIZE_T v4; // rsi
  void *v5; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v4 = (unsigned int)(2 * *(_DWORD *)(a2 + 20) + 2);
  v5 = CoTaskMemAlloc(v4);
  pv = v5;
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx",
      v6);
  memcpy_0(v5, *(const void **)(a2 + 8), v4);
  CValueChunk::SetValueAndTakeMemoryOwnership(a1 + 8264, &pv);
  *(_BYTE *)(a1 + 8272) &= ~1u;
  *(_BYTE *)(a1 + 8272) |= 2u;
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1800258c0  mov     [rsp+arg_0], rbx
0x1800258c5  mov     [rsp+arg_10], rsi
0x1800258ca  push    rdi
0x1800258cb  sub     rsp, 20h
0x1800258cf  mov     rdi, rdx
0x1800258d2  mov     rbx, rcx
0x1800258d5  mov     eax, [rdx+14h]
0x1800258d8  lea     eax, ds:2[rax*2]
0x1800258df  mov     esi, eax
0x1800258e1  mov     ecx, eax; cb
0x1800258e3  call    cs:__imp_CoTaskMemAlloc
0x1800258e9  mov     [rsp+28h+pv], rax
0x1800258ee  mov     rcx, [rsp+28h]; this
0x1800258f3  test    rax, rax
0x1800258f6  jnz     short loc_18002590A
0x1800258f8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800258ff  mov     edx, 17Dh; void *
0x180025904  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002590a  mov     r8, rsi; Size
0x18002590d  mov     rdx, [rdi+8]; Src
0x180025911  mov     rcx, rax; void *
0x180025914  call    memcpy_0
0x180025919  lea     rcx, [rbx+2048h]
0x180025920  lea     rdx, [rsp+28h+pv]
0x180025925  call    ?SetValueAndTakeMemoryOwnership@CValueChunk@@QEAAXAEAV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; CValueChunk::SetValueAndTakeMemoryOwnership(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18002592a  and     byte ptr [rbx+2050h], 0FEh
0x180025931  or      byte ptr [rbx+2050h], 2
0x180025938  mov     rcx, [rsp+28h+pv]; pv
0x18002593d  test    rcx, rcx
0x180025940  jz      short loc_180025948
0x180025942  call    cs:__imp_CoTaskMemFree
0x180025948  mov     rbx, [rsp+28h+arg_0]
0x18002594d  mov     rsi, [rsp+28h+arg_10]
0x180025952  add     rsp, 20h
0x180025956  pop     rdi
0x180025957  retn
```

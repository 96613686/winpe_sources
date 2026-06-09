# IFilterImpl<CMapi2RowFilter>::SetValueChunk(CLMString const &)

- ea: `0x180021dcc`
- end: `0x180021e53`
- name: `?SetValueChunk@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXAEBVCLMString@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021ff4`

## callees

- `0x180021dcc`
- `0x180021fc4`
- `0x1800227a0`
- `0x18003a0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e3d`

## string_xrefs

- `0x180021e04`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IFilterImpl<CMapi2RowFilter>::SetValueChunk(__int64 a1, __int64 a2)
{
  SIZE_T v4; // rdi
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
  IFilterImpl<CMapi2RowFilter>::SetValueChunkAsStringAndTakeMemoryOwnership(a1, &pv);
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180021dcc  mov     [rsp+arg_0], rbx
0x180021dd1  mov     [rsp+arg_10], rsi
0x180021dd6  push    rdi
0x180021dd7  sub     rsp, 20h
0x180021ddb  mov     rbx, rdx
0x180021dde  mov     rsi, rcx
0x180021de1  mov     eax, [rdx+14h]
0x180021de4  lea     eax, ds:2[rax*2]
0x180021deb  mov     edi, eax
0x180021ded  mov     ecx, eax; cb
0x180021def  call    cs:__imp_CoTaskMemAlloc
0x180021df5  mov     [rsp+28h+pv], rax
0x180021dfa  mov     rcx, [rsp+28h]; this
0x180021dff  test    rax, rax
0x180021e02  jnz     short loc_180021E16
0x180021e04  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180021e0b  mov     edx, 17Dh; void *
0x180021e10  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021e16  mov     r8, rdi; Size
0x180021e19  mov     rdx, [rbx+8]; Src
0x180021e1d  mov     rcx, rax; void *
0x180021e20  call    memcpy_0
0x180021e25  lea     rdx, [rsp+28h+pv]
0x180021e2a  mov     rcx, rsi
0x180021e2d  call    ?SetValueChunkAsStringAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXAEAV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2RowFilter>::SetValueChunkAsStringAndTakeMemoryOwnership(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x180021e32  nop
0x180021e33  mov     rcx, [rsp+28h+pv]; pv
0x180021e38  test    rcx, rcx
0x180021e3b  jz      short loc_180021E43
0x180021e3d  call    cs:__imp_CoTaskMemFree
0x180021e43  mov     rbx, [rsp+28h+arg_0]
0x180021e48  mov     rsi, [rsp+28h+arg_10]
0x180021e4d  add     rsp, 20h
0x180021e51  pop     rdi
0x180021e52  retn
```

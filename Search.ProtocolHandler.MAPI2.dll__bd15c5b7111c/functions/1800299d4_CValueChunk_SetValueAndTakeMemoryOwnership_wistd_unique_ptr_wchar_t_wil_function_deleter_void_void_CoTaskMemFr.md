# CValueChunk::SetValueAndTakeMemoryOwnership(wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x1800299d4`
- end: `0x180029a4e`
- name: `?SetValueAndTakeMemoryOwnership@CValueChunk@@QEAAXAEAV?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021fc4`
- `0x1800258c0`

## callees

- `0x180017870`
- `0x1800227a0`
- `0x180029790`
- `0x1800299d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800299ee`

## string_xrefs

- `0x180029a0c`: `onecoreuap\base\appmodel\search\common\pkmutill\prothndlrhelp.cxx`

## pseudocode

```c
__int64 __fastcall CValueChunk::SetValueAndTakeMemoryOwnership(CValueChunk *a1, __int64 *a2)
{
  LPVOID v4; // rax
  const char *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  CValueChunk::Clear(a1);
  v4 = CoTaskMemAlloc(0x18u);
  wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(a1, v4);
  v6 = *(_QWORD *)a1;
  if ( !*(_QWORD *)a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\prothndlrhelp.cxx",
      v5);
  *(_OWORD *)v6 = 0;
  *(_QWORD *)(v6 + 16) = 0;
  **(_WORD **)a1 = 31;
  v7 = *a2;
  *a2 = 0;
  result = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = v7;
  return result;
}

```

## disassembly

```asm
0x1800299d4  mov     [rsp+arg_0], rbx
0x1800299d9  push    rdi
0x1800299da  sub     rsp, 20h
0x1800299de  mov     rdi, rdx
0x1800299e1  mov     rbx, rcx
0x1800299e4  call    ?Clear@CValueChunk@@QEAAXXZ; CValueChunk::Clear(void)
0x1800299e9  mov     ecx, 18h; cb
0x1800299ee  call    cs:__imp_CoTaskMemAlloc
0x1800299f4  mov     rdx, rax
0x1800299f7  mov     rcx, rbx
0x1800299fa  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x1800299ff  mov     rax, [rbx]
0x180029a02  test    rax, rax
0x180029a05  jnz     short loc_180029A1E
0x180029a07  mov     rcx, [rsp+28h]; this
0x180029a0c  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180029a13  mov     edx, 95h; void *
0x180029a18  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180029a1e  xor     ecx, ecx
0x180029a20  xorps   xmm0, xmm0
0x180029a23  movups  xmmword ptr [rax], xmm0
0x180029a26  mov     [rax+10h], rcx
0x180029a2a  mov     rax, [rbx]
0x180029a2d  mov     word ptr [rax], 1Fh
0x180029a32  mov     rcx, [rdi]
0x180029a35  mov     qword ptr [rdi], 0
0x180029a3c  mov     rax, [rbx]
0x180029a3f  mov     rbx, [rsp+28h+arg_0]
0x180029a44  mov     [rax+8], rcx
0x180029a48  add     rsp, 20h
0x180029a4c  pop     rdi
0x180029a4d  retn
```

# FlowEndpointBase::FlowEndpointBase(void)

- ea: `0x180021574`
- end: `0x1800215fd`
- name: `??0FlowEndpointBase@@QEAA@XZ`
- size: `137`
- prototype: `FlowEndpointBase *__fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002154c`
- `0x18003e164`

## callees

- `0x18002c6e0`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800215e3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800215e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
FlowEndpointBase *__fastcall FlowEndpointBase::FlowEndpointBase(FlowEndpointBase *this)
{
  _QWORD *v2; // rcx

  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_DWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &FlowEndpointBase::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_BYTE *)this + 92) = 0;
  v2 = (_QWORD *)((char *)this + 96);
  *v2 = 0;
  v2[1] = 0;
  std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Alloc_sentinel_and_proxy();
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_WORD *)this + 64) = 0;
  *((_DWORD *)this + 33) = SHTaskPoolGetUniqueContext();
  return this;
}

```

## disassembly

```asm
0x180021574  mov     [rsp+arg_8], rbx
0x180021579  mov     [rsp+arg_0], rcx
0x18002157e  push    rdi
0x18002157f  sub     rsp, 20h
0x180021583  mov     rbx, rcx
0x180021586  xor     edi, edi
0x180021588  mov     [rcx+8], rdi
0x18002158c  mov     [rcx+10h], dil
0x180021590  mov     [rcx+14h], edi
0x180021593  mov     [rcx+18h], rdi
0x180021597  mov     [rcx+20h], rdi
0x18002159b  lea     rax, ??_7FlowEndpointBase@@6B@; const FlowEndpointBase::`vftable'
0x1800215a2  mov     [rcx], rax
0x1800215a5  mov     [rcx+28h], rdi
0x1800215a9  mov     [rcx+30h], edi
0x1800215ac  mov     [rcx+38h], rdi
0x1800215b0  mov     [rcx+40h], rdi
0x1800215b4  mov     [rcx+48h], rdi
0x1800215b8  mov     [rcx+50h], rdi
0x1800215bc  mov     [rcx+58h], edi
0x1800215bf  mov     [rcx+5Ch], dil
0x1800215c3  add     rcx, 60h ; '`'
0x1800215c7  mov     [rcx], rdi
0x1800215ca  mov     [rcx+8], rdi
0x1800215ce  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Alloc_sentinel_and_proxy(void)
0x1800215d3  mov     [rbx+70h], edi
0x1800215d6  xor     eax, eax
0x1800215d8  mov     [rbx+78h], rax
0x1800215dc  mov     [rbx+80h], di
0x1800215e3  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800215e9  mov     [rbx+84h], eax
0x1800215ef  mov     rax, rbx
0x1800215f2  mov     rbx, [rsp+28h+arg_8]
0x1800215f7  add     rsp, 20h
0x1800215fb  pop     rdi
0x1800215fc  retn
```

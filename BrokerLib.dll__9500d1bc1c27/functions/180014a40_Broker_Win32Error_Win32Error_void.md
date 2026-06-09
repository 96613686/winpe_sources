# Broker::Win32Error::Win32Error(void)

- ea: `0x180014a40`
- end: `0x180014a73`
- name: `??0Win32Error@Broker@@QEAA@XZ`
- size: `51`
- prototype: `__int64 __fastcall(Broker::Win32Error *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001540`
- `0x180006eb0`
- `0x180007708`
- `0x180007be0`
- `0x180008210`
- `0x1800084a8`
- `0x18000f330`
- `0x180010fd8`
- `0x180019fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a61`

## pseudocode

```c
Broker::Win32Error *__fastcall Broker::Win32Error::Win32Error(Broker::Win32Error *this)
{
  *(_OWORD *)((char *)this + 8) = 0;
  *((_DWORD *)this + 6) = 1;
  *(_QWORD *)this = &Broker::Win32Error::`vftable';
  *((_DWORD *)this + 8) = GetLastError();
  return this;
}

```

## disassembly

```asm
0x180014a40  push    rbx
0x180014a42  sub     rsp, 20h
0x180014a46  xorps   xmm0, xmm0
0x180014a49  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180014a50  movups  xmmword ptr [rcx+8], xmm0
0x180014a54  mov     dword ptr [rcx+18h], 1
0x180014a5b  mov     rbx, rcx
0x180014a5e  mov     [rcx], rax
0x180014a61  call    cs:__imp_GetLastError
0x180014a67  mov     [rbx+20h], eax
0x180014a6a  mov     rax, rbx
0x180014a6d  add     rsp, 20h
0x180014a71  pop     rbx
0x180014a72  retn
```

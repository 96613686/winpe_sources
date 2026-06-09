# Broker::Win32Error::Win32Error(void)

- ea: `0x18001732c`
- end: `0x18001735f`
- name: `??0Win32Error@Broker@@QEAA@XZ`
- size: `51`
- prototype: `Broker::Win32Error *__fastcall(Broker::Win32Error *this)`
- caller_count: `12`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002e20`
- `0x180007880`
- `0x180008230`
- `0x18000bbc0`
- `0x18000c0b0`
- `0x18000cc40`
- `0x18000ec10`
- `0x180010c20`
- `0x1800116a0`
- `0x1800140e0`
- `0x180016090`
- `0x18001c228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001734d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001734d`

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
0x18001732c  push    rbx
0x18001732e  sub     rsp, 20h
0x180017332  xorps   xmm0, xmm0
0x180017335  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001733c  movups  xmmword ptr [rcx+8], xmm0
0x180017340  mov     dword ptr [rcx+18h], 1
0x180017347  mov     rbx, rcx
0x18001734a  mov     [rcx], rax
0x18001734d  call    cs:__imp_GetLastError
0x180017353  mov     [rbx+20h], eax
0x180017356  mov     rax, rbx
0x180017359  add     rsp, 20h
0x18001735d  pop     rbx
0x18001735e  retn
```

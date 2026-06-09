# Broker::Win32Error::Win32Error(void)

- ea: `0x18001181c`
- end: `0x18001184f`
- name: `??0Win32Error@Broker@@QEAA@XZ`
- size: `51`
- prototype: `Broker::Win32Error *__fastcall(Broker::Win32Error *this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003cac`
- `0x180003eac`
- `0x180004818`
- `0x180008c70`
- `0x180009200`
- `0x180009750`
- `0x18000a100`
- `0x18000a330`
- `0x18000c580`
- `0x180017e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001183d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001183d`

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
0x18001181c  push    rbx
0x18001181e  sub     rsp, 20h
0x180011822  xorps   xmm0, xmm0
0x180011825  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001182c  movups  xmmword ptr [rcx+8], xmm0
0x180011830  mov     dword ptr [rcx+18h], 1
0x180011837  mov     rbx, rcx
0x18001183a  mov     [rcx], rax
0x18001183d  call    cs:__imp_GetLastError
0x180011843  mov     [rbx+20h], eax
0x180011846  mov     rax, rbx
0x180011849  add     rsp, 20h
0x18001184d  pop     rbx
0x18001184e  retn
```

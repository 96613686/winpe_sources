# StateWebServer::StateWebServer(void)

- ea: `0x140002244`
- end: `0x14000229f`
- name: `??0StateWebServer@@QEAA@XZ`
- size: `91`
- prototype: `StateWebServer *__fastcall(StateWebServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140002a78`

## callees

- `0x140005288`

## string_xrefs

- `0x14000224d`: `StateWebServer._serviceControlEventListLock`

## pseudocode

```c
StateWebServer *__fastcall StateWebServer::StateWebServer(StateWebServer *this)
{
  StateWebServer *result; // rax

  CReadWriteSpinLock::CReadWriteSpinLock(
    (StateWebServer *)((char *)this + 112),
    "StateWebServer._serviceControlEventListLock");
  StateWebServer::s_pstweb = this;
  *((_QWORD *)this + 7) = -1;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 13) = (char *)this + 96;
  *((_QWORD *)this + 12) = (char *)this + 96;
  *((_WORD *)this + 24) = -23112;
  result = this;
  *((_DWORD *)this + 22) = 1;
  *((_DWORD *)this + 8) = 15;
  *((_BYTE *)this + 73) = 0;
  return result;
}

```

## disassembly

```asm
0x140002244  push    rbx
0x140002246  sub     rsp, 20h
0x14000224a  mov     rbx, rcx
0x14000224d  lea     rdx, aStatewebserver; "StateWebServer._serviceControlEventList"...
0x140002254  add     rcx, 70h ; 'p'; this
0x140002258  call    ??0CReadWriteSpinLock@@QEAA@PEBD@Z; CReadWriteSpinLock::CReadWriteSpinLock(char const *)
0x14000225d  mov     cs:?s_pstweb@StateWebServer@@0PEAV1@EA, rbx; StateWebServer * StateWebServer::s_pstweb
0x140002264  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002268  mov     [rbx+38h], rax
0x14000226c  mov     [rbx+40h], rax
0x140002270  lea     rax, [rbx+60h]
0x140002274  mov     [rax+8], rax
0x140002278  mov     [rax], rax
0x14000227b  mov     eax, 0A5B8h
0x140002280  mov     [rbx+30h], ax
0x140002284  mov     rax, rbx
0x140002287  mov     dword ptr [rbx+58h], 1
0x14000228e  mov     dword ptr [rbx+20h], 0Fh
0x140002295  mov     byte ptr [rbx+49h], 0
0x140002299  add     rsp, 20h
0x14000229d  pop     rbx
0x14000229e  retn
```

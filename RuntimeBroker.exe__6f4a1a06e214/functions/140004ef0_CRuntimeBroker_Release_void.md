# CRuntimeBroker::Release(void)

- ea: `0x140004ef0`
- end: `0x140004f3d`
- name: `?Release@CRuntimeBroker@@UEAAKXZ`
- size: `77`
- prototype: `unsigned int __fastcall(CRuntimeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140004ef0`
- `0x140008f38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x140004f28`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x140004f28`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::Release(CRuntimeBroker *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CRuntimeBroker::`vftable';
    CoReleaseServerProcess();
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x140004ef0  mov     [rsp+arg_0], rbx
0x140004ef5  push    rdi
0x140004ef6  sub     rsp, 20h
0x140004efa  mov     rdi, rcx
0x140004efd  mov     ebx, 0FFFFFFFFh
0x140004f02  lock xadd [rcx+8], ebx
0x140004f07  sub     ebx, 1
0x140004f0a  jz      short loc_140004F19
0x140004f0c  mov     eax, ebx
0x140004f0e  mov     rbx, [rsp+28h+arg_0]
0x140004f13  add     rsp, 20h
0x140004f17  pop     rdi
0x140004f18  retn
0x140004f19  test    rdi, rdi
0x140004f1c  jz      short loc_140004F0C
0x140004f1e  lea     rax, ??_7CRuntimeBroker@@6B@; const CRuntimeBroker::`vftable'
0x140004f25  mov     [rcx], rax
0x140004f28  call    cs:__imp_CoReleaseServerProcess
0x140004f2e  mov     edx, 10h
0x140004f33  mov     rcx, rdi; pv
0x140004f36  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004f3b  jmp     short loc_140004F0C
```

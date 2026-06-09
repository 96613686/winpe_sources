# Common::StringBuffer::operator=(Common::StringBuffer &&)

- ea: `0x140008610`
- end: `0x14000865e`
- name: `??4StringBuffer@Common@@QEAAAEAV01@$$QEAV01@@Z`
- size: `78`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140008ec8`
- `0x140009310`

## callees

- `0x140003644`
- `0x140008610`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::operator=(__int64 a1, __int64 a2)
{
  if ( a1 != a2 )
  {
    operator delete(*(void **)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 0;
    *(_DWORD *)(a1 + 16) = 0;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 16) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140008610  mov     [rsp+arg_0], rbx
0x140008615  push    rdi
0x140008616  sub     rsp, 20h
0x14000861a  mov     rdi, rdx
0x14000861d  mov     rbx, rcx
0x140008620  cmp     rcx, rdx
0x140008623  jz      short loc_140008650
0x140008625  mov     rcx, [rcx+8]; void *
0x140008629  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000862e  xor     ecx, ecx
0x140008630  mov     [rbx+8], rcx
0x140008634  mov     [rbx], ecx
0x140008636  mov     [rbx+10h], ecx
0x140008639  movups  xmm0, xmmword ptr [rdi]
0x14000863c  movdqu  xmmword ptr [rbx], xmm0
0x140008640  mov     eax, [rdi+10h]
0x140008643  mov     [rbx+10h], eax
0x140008646  xorps   xmm0, xmm0
0x140008649  movdqu  xmmword ptr [rdi], xmm0
0x14000864d  mov     [rdi+10h], ecx
0x140008650  mov     rax, rbx
0x140008653  mov     rbx, [rsp+28h+arg_0]
0x140008658  add     rsp, 20h
0x14000865c  pop     rdi
0x14000865d  retn
```

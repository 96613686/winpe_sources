# CRdpSessionAgentProxy::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x1400040f0`
- end: `0x1400041a8`
- name: `?NonDelegatingQueryInterface@CRdpSessionAgentProxy@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1400040f0`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::NonDelegatingQueryInterface(
        CRdpSessionAgentProxy *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = 0;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CRdpSessionAgentProxy *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      *a3 = 0;
    }
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IRdpSessionAgent.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IRdpSessionAgent.Data4 )
    {
      *a3 = (char *)this - 16;
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IRdpSessionAgentProxy.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IRdpSessionAgentProxy.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      *a3 = (void *)(((unsigned __int64)this - 8) & -(__int64)(this != (CRdpSessionAgentProxy *)16));
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 8LL))(*((_QWORD *)this + 4));
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1400040f0  push    rbx
0x1400040f2  sub     rsp, 20h
0x1400040f6  mov     r9, rcx
0x1400040f9  mov     rcx, qword ptr cs:IID_IUnknown.Data1
0x140004100  cmp     [rdx], rcx
0x140004103  jnz     short loc_140004138
0x140004105  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x14000410c  cmp     [rdx+8], rax
0x140004110  jnz     short loc_140004138
0x140004112  xor     ebx, ebx
0x140004114  cmp     [rdx], rcx
0x140004117  jnz     short loc_140004133
0x140004119  cmp     [rdx+8], rax
0x14000411d  jnz     short loc_140004133
0x14000411f  mov     [r8], r9
0x140004122  mov     rcx, r9
0x140004125  mov     rax, [r9]
0x140004128  mov     rax, [rax+8]
0x14000412c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004131  jmp     short loc_1400041A0
0x140004133  mov     [r8], rbx
0x140004136  jmp     short loc_1400041A0
0x140004138  mov     rax, [rdx]
0x14000413b  cmp     rax, qword ptr cs:IID_IRdpSessionAgent.Data1
0x140004142  jnz     short loc_14000415A
0x140004144  mov     rax, [rdx+8]
0x140004148  cmp     rax, qword ptr cs:IID_IRdpSessionAgent.Data4
0x14000414f  jnz     short loc_14000415A
0x140004151  lea     rax, [r9-10h]
0x140004155  mov     [r8], rax
0x140004158  jmp     short loc_140004187
0x14000415a  mov     rax, [rdx]
0x14000415d  cmp     rax, qword ptr cs:IID_IRdpSessionAgentProxy.Data1
0x140004164  jnz     short loc_14000419B
0x140004166  mov     rax, [rdx+8]
0x14000416a  cmp     rax, qword ptr cs:IID_IRdpSessionAgentProxy.Data4
0x140004171  jnz     short loc_14000419B
0x140004173  lea     rax, [r9-10h]
0x140004177  neg     rax
0x14000417a  lea     rdx, [r9-8]
0x14000417e  sbb     rcx, rcx
0x140004181  and     rcx, rdx
0x140004184  mov     [r8], rcx
0x140004187  mov     rcx, [r9+20h]
0x14000418b  mov     rax, [rcx]
0x14000418e  mov     rax, [rax+8]
0x140004192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004197  xor     ebx, ebx
0x140004199  jmp     short loc_1400041A0
0x14000419b  mov     ebx, 80004002h
0x1400041a0  mov     eax, ebx
0x1400041a2  add     rsp, 20h
0x1400041a6  pop     rbx
0x1400041a7  retn
```

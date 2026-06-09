# MSAClientTraceTelemetry::`scalar deleting destructor'(uint)

- ea: `0x180003fa0`
- end: `0x180003ff0`
- name: `??_GMSAClientTraceTelemetry@@UEAAPEAXI@Z`
- size: `80`
- prototype: `MSAClientTraceTelemetry *__fastcall(MSAClientTraceTelemetry *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800022a0`
- `0x180003fa0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003fce`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003fce`

## pseudocode

```c
MSAClientTraceTelemetry *__fastcall MSAClientTraceTelemetry::`scalar deleting destructor'(
        MSAClientTraceTelemetry *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &MSAClientTraceTelemetry::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 32) = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003fa0  mov     [rsp+arg_0], rbx
0x180003fa5  push    rdi
0x180003fa6  sub     rsp, 20h
0x180003faa  mov     edi, edx
0x180003fac  lea     rax, ??_7MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::`vftable'
0x180003fb3  xor     edx, edx
0x180003fb5  mov     [rcx], rax
0x180003fb8  mov     rbx, rcx
0x180003fbb  cmp     [rcx+10h], dl
0x180003fbe  jz      short loc_180003FD4
0x180003fc0  mov     rax, [rcx+8]
0x180003fc4  mov     rcx, [rax+20h]; RegHandle
0x180003fc8  mov     [rax], edx
0x180003fca  mov     [rax+20h], rdx
0x180003fce  call    cs:__imp_EventUnregister
0x180003fd4  test    dil, 1
0x180003fd8  jz      short loc_180003FE2
0x180003fda  mov     rcx, rbx; Block
0x180003fdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003fe2  mov     rax, rbx
0x180003fe5  mov     rbx, [rsp+28h+arg_0]
0x180003fea  add     rsp, 20h
0x180003fee  pop     rdi
0x180003fef  retn
```

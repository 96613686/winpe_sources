# CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>(wil::com_ptr_t<Rdp::Avenc::IFrameProcessor,wil::err_exception_policy> const &)

- ea: `0x180029e84`
- end: `0x180029f1c`
- name: `??0?$CSwapChainProcessor@UICpuFrameProcessor@Avenc@Rdp@@VCFrameSystemBuffer@@@@QEAA@AEBV?$com_ptr_t@UIFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cdc`

## callees

- `0x180007b38`
- `0x18001dd50`
- `0x180029e84`
- `0x18003f010`

## string_xrefs

- `0x180029f0a`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>::CSwapChainProcessor<Rdp::Avenc::ICpuFrameProcessor,CFrameSystemBuffer>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_OWORD *)a1 = 0;
  memset_0((void *)(a1 + 16), 0, 0x78u);
  *(_DWORD *)a1 = 16;
  *(_DWORD *)(a1 + 4) = 1;
  *(_QWORD *)(a1 + 136) = 0;
  if ( *a2 )
  {
    v4 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*a2)(
           *a2,
           &GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48,
           a1 + 136);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)v4,
        v6);
  }
  else
  {
    *(_QWORD *)(a1 + 136) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180029e84  mov     [rsp+arg_8], rbx
0x180029e89  mov     [rsp+arg_0], rcx
0x180029e8e  push    rdi; int
0x180029e8f  sub     rsp, 20h
0x180029e93  mov     rbx, rdx
0x180029e96  mov     rdi, rcx
0x180029e99  xorps   xmm0, xmm0
0x180029e9c  movups  xmmword ptr [rcx], xmm0
0x180029e9f  add     rcx, 10h; void *
0x180029ea3  xor     edx, edx; Val
0x180029ea5  lea     r8d, [rdx+78h]; Size
0x180029ea9  call    memset_0
0x180029eae  lea     rdx, [rdi+88h]
0x180029eb5  mov     dword ptr [rdi], 10h
0x180029ebb  mov     dword ptr [rdi+4], 1
0x180029ec2  mov     qword ptr [rdx], 0
0x180029ec9  mov     rcx, [rbx]
0x180029ecc  test    rcx, rcx
0x180029ecf  jz      short loc_180029EF1
0x180029ed1  mov     rax, [rcx]
0x180029ed4  mov     r8, rdx
0x180029ed7  lea     rdx, _GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48
0x180029ede  mov     rax, [rax]
0x180029ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ee6  mov     rcx, [rsp+28h]; this
0x180029eeb  test    eax, eax
0x180029eed  js      short loc_180029F07
0x180029eef  jmp     short loc_180029EF8
0x180029ef1  mov     qword ptr [rdx], 0
0x180029ef8  mov     rax, rdi
0x180029efb  mov     rbx, [rsp+28h+arg_8]
0x180029f00  add     rsp, 20h
0x180029f04  pop     rdi
0x180029f05  retn
0x180029f07  mov     r9d, eax; char *
0x180029f0a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029f11  mov     edx, 1CBEh; void *
0x180029f16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

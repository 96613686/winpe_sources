# ATL::CComObject<CPimcContext>::CComObject<CPimcContext>(void *)

- ea: `0x18000a328`
- end: `0x18000a426`
- name: `??0?$CComObject@VCPimcContext@@@ATL@@QEAA@PEAX@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0d4`

## callees

- `0x18000d44c`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ATL::CComObject<CPimcContext>::CComObject<CPimcContext>(__int64 a1)
{
  _DWORD *v3; // [rsp+50h] [rbp+18h]

  *(_DWORD *)(a1 + 8) = 0;
  v3 = operator new(0x10u);
  *(_QWORD *)v3 = &CPimcContext::CEventSink::`vftable';
  v3[2] = 0;
  *(_QWORD *)(a1 + 16) = v3;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 240) &= ~2u;
  *(_QWORD *)(a1 + 248) = 0;
  *(_BYTE *)(a1 + 268) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_BYTE *)(a1 + 292) = 0;
  *(_DWORD *)(a1 + 296) = 0;
  *(_BYTE *)(a1 + 312) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CPimcContext>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x18000a328  mov     [rsp+arg_8], rbx
0x18000a32d  mov     [rsp+arg_0], rcx
0x18000a332  push    rdi
0x18000a333  sub     rsp, 30h
0x18000a337  mov     rbx, rcx
0x18000a33a  xor     edi, edi
0x18000a33c  mov     [rcx+8], edi
0x18000a33f  lea     ecx, [rdi+10h]; Size
0x18000a342  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a347  mov     rdx, rax
0x18000a34a  mov     [rsp+38h+arg_10], rax
0x18000a34f  lea     rax, ??_7CEventSink@CPimcContext@@6B@; const CPimcContext::CEventSink::`vftable'
0x18000a356  mov     [rdx], rax
0x18000a359  mov     [rdx+8], edi
0x18000a35c  lea     rcx, [rbx+10h]
0x18000a360  mov     [rsp+38h+arg_18], rcx
0x18000a365  mov     [rcx], rdx
0x18000a368  mov     rcx, [rdx]
0x18000a36b  mov     rax, [rcx+8]
0x18000a36f  mov     rcx, rdx
0x18000a372  call    cs:__guard_dispatch_icall_fptr
0x18000a378  nop
0x18000a379  lea     rax, [rbx+18h]
0x18000a37d  mov     [rsp+38h+var_18], rax
0x18000a382  mov     [rax], rdi
0x18000a385  lea     rax, [rbx+20h]
0x18000a389  mov     [rsp+38h+var_10], rax
0x18000a38e  mov     [rax], rdi
0x18000a391  mov     [rbx+30h], rdi
0x18000a395  mov     [rbx+38h], rdi
0x18000a399  mov     [rbx+40h], rdi
0x18000a39d  mov     [rbx+48h], rdi
0x18000a3a1  mov     [rbx+50h], rdi
0x18000a3a5  mov     [rbx+58h], rdi
0x18000a3a9  mov     [rbx+60h], rdi
0x18000a3ad  mov     [rbx+70h], rdi
0x18000a3b1  mov     [rbx+78h], rdi
0x18000a3b5  mov     [rbx+80h], edi
0x18000a3bb  mov     [rbx+88h], rdi
0x18000a3c2  mov     [rbx+0B8h], rdi
0x18000a3c9  and     dword ptr [rbx+0F0h], 0FFFFFFFDh
0x18000a3d0  mov     [rbx+0F8h], rdi
0x18000a3d7  mov     [rbx+10Ch], dil
0x18000a3de  mov     [rbx+110h], rdi
0x18000a3e5  mov     [rbx+124h], dil
0x18000a3ec  mov     [rbx+128h], edi
0x18000a3f2  mov     [rbx+138h], dil
0x18000a3f9  lea     rax, ??_7?$CComObject@VCPimcContext@@@ATL@@6B@; const ATL::CComObject<CPimcContext>::`vftable'
0x18000a400  mov     [rbx], rax
0x18000a403  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a40a  mov     rax, [rcx]
0x18000a40d  mov     rax, [rax+8]
0x18000a411  call    cs:__guard_dispatch_icall_fptr
0x18000a417  nop
0x18000a418  mov     rax, rbx
0x18000a41b  mov     rbx, [rsp+38h+arg_8]
0x18000a420  add     rsp, 30h
0x18000a424  pop     rdi
0x18000a425  retn
```

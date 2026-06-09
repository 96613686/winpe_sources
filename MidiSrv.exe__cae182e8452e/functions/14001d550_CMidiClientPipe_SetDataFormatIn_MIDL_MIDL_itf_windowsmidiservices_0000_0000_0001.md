# CMidiClientPipe::SetDataFormatIn(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001)

- ea: `0x14001d550`
- end: `0x14001d626`
- name: `?SetDataFormatIn@CMidiClientPipe@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@@Z`
- size: `214`
- prototype: `int __high(enum __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14000a6b4`
- `0x14001d550`
- `0x14005a010`

## string_xrefs

- `0x14001d574`: `avcore\midi2\service\Inc\MidiPipe.h`
- `0x14001d5cd`: `avcore\midi2\service\Inc\MidiPipe.h`
- `0x14001d597`: `avcore\midi2\service\Inc\MidiClientPipe.h`

## pseudocode

```c
__int64 __fastcall CMidiClientPipe::SetDataFormatIn(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  bool v6; // zf
  __int64 v7; // rax
  unsigned int *v8; // rax
  unsigned int *v9; // rcx
  int v10; // [rsp+20h] [rbp-8h]
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
      (const char *)0x8007065ELL,
      v10);
    v4 = 32;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\midi2\\service\\Inc\\MidiClientPipe.h",
      (const char *)0x8007065ELL,
      v11);
    return 2147944030LL;
  }
  v6 = *(_DWORD *)(a1 + 52) == 0;
  *(_DWORD *)(a1 + 48) = a2;
  if ( !v6 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 104LL))(a1, a2) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
        (const char *)0x8007065ELL,
        v10);
      v4 = 35;
      goto LABEL_3;
    }
    *(_DWORD *)(a1 + 52) = a2;
  }
  v7 = *(_QWORD *)(a1 + 136);
  if ( v7 )
  {
    v8 = *(unsigned int **)(v7 + 104);
    if ( v8 )
      *v8 = a2;
    v9 = *(unsigned int **)(*(_QWORD *)(a1 + 136) + 112LL);
    if ( v9 )
      *v9 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x14001d550  mov     [rsp+arg_0], rbx
0x14001d555  push    rdi; int
0x14001d556  sub     rsp, 20h
0x14001d55a  mov     rax, [rcx]
0x14001d55d  mov     edi, edx
0x14001d55f  mov     rbx, rcx
0x14001d562  mov     rax, [rax+60h]
0x14001d566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d56b  test    eax, eax
0x14001d56d  jnz     short loc_14001D5AA
0x14001d56f  mov     rcx, [rsp+28h]; this
0x14001d574  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x14001d57b  mov     ebx, 8007065Eh
0x14001d580  mov     edx, 0AAh; void *
0x14001d585  mov     r9d, ebx; char *
0x14001d588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d58d  mov     edx, 20h ; ' '; void *
0x14001d592  mov     rcx, [rsp+28h]; this
0x14001d597  lea     r8, aAvcoreMidi2Ser_6; "avcore\\midi2\\service\\Inc\\MidiClient"...
0x14001d59e  mov     r9d, ebx; char *
0x14001d5a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d5a6  mov     eax, ebx
0x14001d5a8  jmp     short loc_14001D61B
0x14001d5aa  cmp     dword ptr [rbx+34h], 0
0x14001d5ae  mov     [rbx+30h], edi
0x14001d5b1  jz      short loc_14001D5F0
0x14001d5b3  mov     rax, [rbx]
0x14001d5b6  mov     edx, edi
0x14001d5b8  mov     rcx, rbx
0x14001d5bb  mov     rax, [rax+68h]
0x14001d5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d5c4  test    eax, eax
0x14001d5c6  jnz     short loc_14001D5ED
0x14001d5c8  mov     rcx, [rsp+28h]; this
0x14001d5cd  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x14001d5d4  mov     ebx, 8007065Eh
0x14001d5d9  mov     edx, 0B1h; void *
0x14001d5de  mov     r9d, ebx; char *
0x14001d5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d5e6  mov     edx, 23h ; '#'
0x14001d5eb  jmp     short loc_14001D592
0x14001d5ed  mov     [rbx+34h], edi
0x14001d5f0  mov     rax, [rbx+88h]
0x14001d5f7  test    rax, rax
0x14001d5fa  jz      short loc_14001D619
0x14001d5fc  mov     rax, [rax+68h]
0x14001d600  test    rax, rax
0x14001d603  jz      short loc_14001D607
0x14001d605  mov     [rax], edi
0x14001d607  mov     rax, [rbx+88h]
0x14001d60e  mov     rcx, [rax+70h]
0x14001d612  test    rcx, rcx
0x14001d615  jz      short loc_14001D619
0x14001d617  mov     [rcx], edi
0x14001d619  xor     eax, eax
0x14001d61b  mov     rbx, [rsp+28h+arg_0]
0x14001d620  add     rsp, 20h
0x14001d624  pop     rdi
0x14001d625  retn
```

# CMidiClientPipe::SetDataFormatOut(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001)

- ea: `0x14001d690`
- end: `0x14001d766`
- name: `?SetDataFormatOut@CMidiClientPipe@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001@@@Z`
- size: `214`
- prototype: `int __high(enum __MIDL___MIDL_itf_windowsmidiservices_0000_0000_0001)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14000a6b4`
- `0x14001d690`
- `0x14005a010`

## string_xrefs

- `0x14001d6b4`: `avcore\midi2\service\Inc\MidiPipe.h`
- `0x14001d70d`: `avcore\midi2\service\Inc\MidiPipe.h`
- `0x14001d6d7`: `avcore\midi2\service\Inc\MidiClientPipe.h`

## pseudocode

```c
__int64 __fastcall CMidiClientPipe::SetDataFormatOut(_DWORD *a1, unsigned int a2)
{
  __int64 v4; // rdx
  bool v6; // zf
  __int64 v7; // rax
  unsigned int *v8; // rax
  unsigned int *v9; // rcx
  int v10; // [rsp+20h] [rbp-8h]
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !(*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 104LL))(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
      (const char *)0x8007065ELL,
      v10);
    v4 = 50;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\midi2\\service\\Inc\\MidiClientPipe.h",
      (const char *)0x8007065ELL,
      v11);
    return 2147944030LL;
  }
  v6 = a1[12] == 0;
  a1[13] = a2;
  if ( !v6 )
  {
    if ( !(*(unsigned int (__fastcall **)(_DWORD *, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, a2) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
        (const char *)0x8007065ELL,
        v10);
      v4 = 53;
      goto LABEL_3;
    }
    a1[12] = a2;
  }
  v7 = *((_QWORD *)a1 + 17);
  if ( v7 )
  {
    v8 = *(unsigned int **)(v7 + 104);
    if ( v8 )
      *v8 = a2;
    v9 = *(unsigned int **)(*((_QWORD *)a1 + 17) + 112LL);
    if ( v9 )
      *v9 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x14001d690  mov     [rsp+arg_0], rbx
0x14001d695  push    rdi; int
0x14001d696  sub     rsp, 20h
0x14001d69a  mov     rax, [rcx]
0x14001d69d  mov     edi, edx
0x14001d69f  mov     rbx, rcx
0x14001d6a2  mov     rax, [rax+68h]
0x14001d6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d6ab  test    eax, eax
0x14001d6ad  jnz     short loc_14001D6EA
0x14001d6af  mov     rcx, [rsp+28h]; this
0x14001d6b4  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x14001d6bb  mov     ebx, 8007065Eh
0x14001d6c0  mov     edx, 0B1h; void *
0x14001d6c5  mov     r9d, ebx; char *
0x14001d6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d6cd  mov     edx, 32h ; '2'; void *
0x14001d6d2  mov     rcx, [rsp+28h]; this
0x14001d6d7  lea     r8, aAvcoreMidi2Ser_6; "avcore\\midi2\\service\\Inc\\MidiClient"...
0x14001d6de  mov     r9d, ebx; char *
0x14001d6e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d6e6  mov     eax, ebx
0x14001d6e8  jmp     short loc_14001D75B
0x14001d6ea  cmp     dword ptr [rbx+30h], 0
0x14001d6ee  mov     [rbx+34h], edi
0x14001d6f1  jz      short loc_14001D730
0x14001d6f3  mov     rax, [rbx]
0x14001d6f6  mov     edx, edi
0x14001d6f8  mov     rcx, rbx
0x14001d6fb  mov     rax, [rax+60h]
0x14001d6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d704  test    eax, eax
0x14001d706  jnz     short loc_14001D72D
0x14001d708  mov     rcx, [rsp+28h]; this
0x14001d70d  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x14001d714  mov     ebx, 8007065Eh
0x14001d719  mov     edx, 0AAh; void *
0x14001d71e  mov     r9d, ebx; char *
0x14001d721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d726  mov     edx, 35h ; '5'
0x14001d72b  jmp     short loc_14001D6D2
0x14001d72d  mov     [rbx+30h], edi
0x14001d730  mov     rax, [rbx+88h]
0x14001d737  test    rax, rax
0x14001d73a  jz      short loc_14001D759
0x14001d73c  mov     rax, [rax+68h]
0x14001d740  test    rax, rax
0x14001d743  jz      short loc_14001D747
0x14001d745  mov     [rax], edi
0x14001d747  mov     rax, [rbx+88h]
0x14001d74e  mov     rcx, [rax+70h]
0x14001d752  test    rcx, rcx
0x14001d755  jz      short loc_14001D759
0x14001d757  mov     [rcx], edi
0x14001d759  xor     eax, eax
0x14001d75b  mov     rbx, [rsp+28h+arg_0]
0x14001d760  add     rsp, 20h
0x14001d764  pop     rdi
0x14001d765  retn
```

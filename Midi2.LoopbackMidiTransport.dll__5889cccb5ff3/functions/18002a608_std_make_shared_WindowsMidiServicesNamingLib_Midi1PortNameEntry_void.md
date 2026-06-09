# std::make_shared<WindowsMidiServicesNamingLib::Midi1PortNameEntry,>(void)

- ea: `0x18002a608`
- end: `0x18002a697`
- name: `??$make_shared@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@$$V@std@@YA?AV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@0@XZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002cab8`

## callees

- `0x1800041d0`
- `0x18000500c`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<WindowsMidiServicesNamingLib::Midi1PortNameEntry,>(_QWORD *a1)
{
  char *v2; // rdi
  _QWORD *result; // rax

  v2 = (char *)operator new(0xD8u);
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  *((_DWORD *)v2 + 3) = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::`vftable';
  *(_WORD *)(v2 + 17) = 0;
  v2[19] = 0;
  v2[16] = 0;
  *((_DWORD *)v2 + 5) = 0;
  memset_0(v2 + 24, 0, 0x40u);
  memset_0(v2 + 88, 0, 0x40u);
  memset_0(v2 + 152, 0, 0x40u);
  result = a1;
  *a1 = v2 + 16;
  a1[1] = v2;
  return result;
}

```

## disassembly

```asm
0x18002a608  push    rbx
0x18002a60a  push    rbp
0x18002a60b  push    rsi
0x18002a60c  push    rdi
0x18002a60d  sub     rsp, 38h
0x18002a611  mov     rsi, rcx
0x18002a614  xor     ebp, ebp
0x18002a616  mov     ecx, 0D8h; Size
0x18002a61b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a620  mov     [rsp+58h+arg_0], rax
0x18002a625  mov     rdi, rax
0x18002a628  xorps   xmm0, xmm0
0x18002a62b  xor     edx, edx; Val
0x18002a62d  movups  xmmword ptr [rax], xmm0
0x18002a630  lea     rbx, [rdi+10h]
0x18002a634  lea     eax, [rbp+1]
0x18002a637  mov     [rdi+8], eax
0x18002a63a  lea     rcx, [rbx+8]; void *
0x18002a63e  mov     [rdi+0Ch], eax
0x18002a641  lea     rax, ??_7?$_Ref_count_obj2@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::`vftable'
0x18002a648  mov     [rdi], rax
0x18002a64b  xor     eax, eax
0x18002a64d  mov     [rbx+1], ax
0x18002a651  mov     [rbx+3], al
0x18002a654  mov     [rbx], bpl
0x18002a657  mov     [rbx+4], ebp
0x18002a65a  lea     ebp, [rax+40h]
0x18002a65d  mov     r8d, ebp; Size
0x18002a660  call    memset_0
0x18002a665  lea     rcx, [rbx+48h]; void *
0x18002a669  mov     r8d, ebp; Size
0x18002a66c  xor     edx, edx; Val
0x18002a66e  call    memset_0
0x18002a673  lea     rcx, [rbx+88h]; void *
0x18002a67a  mov     r8d, ebp; Size
0x18002a67d  xor     edx, edx; Val
0x18002a67f  call    memset_0
0x18002a684  mov     rax, rsi
0x18002a687  mov     [rsi], rbx
0x18002a68a  mov     [rsi+8], rdi
0x18002a68e  add     rsp, 38h
0x18002a692  pop     rdi
0x18002a693  pop     rsi
0x18002a694  pop     rbp
0x18002a695  pop     rbx
0x18002a696  retn
```

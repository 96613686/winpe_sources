# Broker::AdaptFormatFromBIStorage(_TbiTimeEventCreationParametersW8_ForBI const &,_TbiTimeEventCreationParameters &)

- ea: `0x1800116f4`
- end: `0x180011750`
- name: `?AdaptFormatFromBIStorage@Broker@@YAXAEBU_TbiTimeEventCreationParametersW8_ForBI@@AEAU_TbiTimeEventCreationParameters@@@Z`
- size: `92`
- prototype: `void __fastcall(Broker *__hidden this, const struct _TbiTimeEventCreationParametersW8_ForBI *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015464`

## callees

- `0x1800132ec`
- `0x180019d47`

## pseudocode

```c
void __fastcall Broker::AdaptFormatFromBIStorage(
        Broker *this,
        const struct _TbiTimeEventCreationParametersW8_ForBI *a2,
        struct _TbiTimeEventCreationParameters *a3)
{
  void *v5; // rax

  *(_OWORD *)a2 = *(_OWORD *)this;
  *((_OWORD *)a2 + 1) = *((_OWORD *)this + 1);
  *((_OWORD *)a2 + 2) = *((_OWORD *)this + 2);
  *((_QWORD *)a2 + 6) = *((_QWORD *)this + 6);
  *((_DWORD *)a2 + 14) = *((_DWORD *)this + 14);
  v5 = operator new[](*((unsigned int *)this + 14));
  *((_QWORD *)a2 + 8) = v5;
  memcpy_0(v5, *((const void **)this + 8), *((unsigned int *)this + 14));
}

```

## disassembly

```asm
0x1800116f4  mov     [rsp+arg_0], rbx
0x1800116f9  push    rdi
0x1800116fa  sub     rsp, 20h
0x1800116fe  movups  xmm0, xmmword ptr [rcx]
0x180011701  mov     rdi, rcx
0x180011704  mov     rbx, rdx
0x180011707  movaps  xmmword ptr [rdx], xmm0
0x18001170a  movups  xmm1, xmmword ptr [rcx+10h]
0x18001170e  movaps  xmmword ptr [rdx+10h], xmm1
0x180011712  movups  xmm0, xmmword ptr [rcx+20h]
0x180011716  movaps  xmmword ptr [rdx+20h], xmm0
0x18001171a  movsd   xmm1, qword ptr [rcx+30h]
0x18001171f  movsd   qword ptr [rdx+30h], xmm1
0x180011724  mov     eax, [rcx+38h]
0x180011727  mov     [rdx+38h], eax
0x18001172a  mov     ecx, [rcx+38h]; unsigned __int64
0x18001172d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011732  mov     [rbx+40h], rax
0x180011736  mov     rcx, rax; void *
0x180011739  mov     r8d, [rdi+38h]; Size
0x18001173d  mov     rdx, [rdi+40h]; Src
0x180011741  mov     rbx, [rsp+28h+arg_0]
0x180011746  add     rsp, 20h
0x18001174a  pop     rdi
0x18001174b  jmp     memcpy_0
```

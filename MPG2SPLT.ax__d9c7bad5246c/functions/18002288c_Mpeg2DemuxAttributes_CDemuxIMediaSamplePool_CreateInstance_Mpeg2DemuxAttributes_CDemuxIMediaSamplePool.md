# Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::CreateInstance(Mpeg2DemuxAttributes::CDemuxIMediaSamplePool * *)

- ea: `0x18002288c`
- end: `0x18002295f`
- name: `?CreateInstance@CDemuxIMediaSamplePool@Mpeg2DemuxAttributes@@SAJPEAPEAV12@@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct Mpeg2DemuxAttributes::CDemuxIMediaSamplePool **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002341c`
- `0x18002bf7c`

## callees

- `0x180001008`
- `0x18002288c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800228e4`
- `KERNEL32!InitializeCriticalSection` at `0x1800228e4`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::CreateInstance(
        struct Mpeg2DemuxAttributes::CDemuxIMediaSamplePool **a1)
{
  char *v2; // rdi

  v2 = (char *)operator new(0xA0u);
  if ( v2 )
  {
    *(_QWORD *)v2 = &Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CDemuxIMediaSample>::`vftable';
    *((_QWORD *)v2 + 14) = 1;
    *((_DWORD *)v2 + 30) = 0;
    *(_QWORD *)(v2 + 124) = 0x7FFFFFFF;
    *(_QWORD *)(v2 + 132) = 0x7FFFFFFF;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
    *((_QWORD *)v2 + 7) = v2 + 48;
    *((_QWORD *)v2 + 6) = v2 + 48;
    *((_QWORD *)v2 + 9) = v2 + 64;
    *((_QWORD *)v2 + 8) = v2 + 64;
    *((_QWORD *)v2 + 11) = v2 + 80;
    *((_QWORD *)v2 + 10) = v2 + 80;
    *((_QWORD *)v2 + 13) = v2 + 96;
    *((_QWORD *)v2 + 12) = v2 + 96;
    *(_QWORD *)v2 = &Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::`vftable';
    *((_QWORD *)v2 + 18) = 0x7FFFFFFF;
    *((_DWORD *)v2 + 38) = 0;
    *a1 = (struct Mpeg2DemuxAttributes::CDemuxIMediaSamplePool *)v2;
    _InterlockedIncrement((volatile signed __int32 *)v2 + 38);
    return 0;
  }
  else
  {
    *a1 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002288c  mov     [rsp+arg_0], rbx
0x180022891  mov     [rsp+arg_8], rsi
0x180022896  push    rdi
0x180022897  sub     rsp, 20h
0x18002289b  mov     rsi, rcx
0x18002289e  mov     ecx, 0A0h; Size
0x1800228a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800228a8  mov     rdi, rax
0x1800228ab  test    rax, rax
0x1800228ae  jz      loc_180022943
0x1800228b4  lea     rax, ??_7?$TCDynamicProdCons@VCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@6B@; const Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CDemuxIMediaSample>::`vftable'
0x1800228bb  mov     [rdi], rax
0x1800228be  lea     rcx, [rdi+8]; lpCriticalSection
0x1800228c2  mov     qword ptr [rdi+70h], 1
0x1800228ca  mov     dword ptr [rdi+78h], 0
0x1800228d1  mov     qword ptr [rdi+7Ch], 7FFFFFFFh
0x1800228d9  mov     qword ptr [rdi+84h], 7FFFFFFFh
0x1800228e4  call    cs:__imp_InitializeCriticalSection
0x1800228ea  lea     rax, [rdi+30h]
0x1800228ee  mov     [rdi+38h], rax
0x1800228f2  mov     [rax], rax
0x1800228f5  lea     rax, [rdi+40h]
0x1800228f9  mov     [rdi+48h], rax
0x1800228fd  mov     [rax], rax
0x180022900  lea     rax, [rdi+50h]
0x180022904  mov     [rdi+58h], rax
0x180022908  mov     [rax], rax
0x18002290b  lea     rax, [rdi+60h]
0x18002290f  mov     [rdi+68h], rax
0x180022913  mov     [rax], rax
0x180022916  lea     rax, ??_7CDemuxIMediaSamplePool@Mpeg2DemuxAttributes@@6B@; const Mpeg2DemuxAttributes::CDemuxIMediaSamplePool::`vftable'
0x18002291d  mov     [rdi], rax
0x180022920  mov     qword ptr [rdi+90h], 7FFFFFFFh
0x18002292b  mov     dword ptr [rdi+98h], 0
0x180022935  mov     [rsi], rdi
0x180022938  lock inc dword ptr [rdi+98h]
0x18002293f  xor     eax, eax
0x180022941  jmp     short loc_18002294F
0x180022943  mov     qword ptr [rsi], 0
0x18002294a  mov     eax, 8007000Eh
0x18002294f  mov     rbx, [rsp+28h+arg_0]
0x180022954  mov     rsi, [rsp+28h+arg_8]
0x180022959  add     rsp, 20h
0x18002295d  pop     rdi
0x18002295e  retn
```

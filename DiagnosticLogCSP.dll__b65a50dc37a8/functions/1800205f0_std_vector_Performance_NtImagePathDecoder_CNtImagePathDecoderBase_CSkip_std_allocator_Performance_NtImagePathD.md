# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800205f0`
- end: `0x180020670`
- name: `??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001e074`
- `0x1800377b5`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x1800205f0`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 32 )
      std::wstring::~wstring(i);
    v4 = a1[1];
    if ( (unsigned __int64)(32LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x1800205f0  mov     [rsp+arg_0], rbx
0x1800205f5  mov     [rsp+arg_8], rsi
0x1800205fa  push    rdi
0x1800205fb  sub     rsp, 20h
0x1800205ff  cmp     qword ptr [rcx+8], 0
0x180020604  mov     rbx, rcx
0x180020607  jz      short loc_18002065F
0x180020609  mov     rsi, [rcx+20h]
0x18002060d  mov     rdi, [rcx+18h]
0x180020611  jmp     short loc_18002061F
0x180020613  mov     rcx, rdi
0x180020616  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002061b  add     rdi, 20h ; ' '
0x18002061f  cmp     rdi, rsi
0x180020622  jnz     short loc_180020613
0x180020624  mov     rdx, [rbx+10h]
0x180020628  mov     rax, [rbx+8]
0x18002062c  shl     rdx, 5; unsigned __int64
0x180020630  cmp     rdx, 1000h
0x180020637  jb      short loc_180020657
0x180020639  mov     rcx, [rax-8]
0x18002063d  sub     rax, rcx
0x180020640  sub     rax, 8
0x180020644  cmp     rax, 1Fh
0x180020648  ja      short loc_180020650
0x18002064a  add     rdx, 27h ; '''
0x18002064e  jmp     short loc_18002065A
0x180020650  mov     ecx, 5
0x180020655  int     29h; Win8: RtlFailFast(ecx)
0x180020657  mov     rcx, rax; void *
0x18002065a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002065f  mov     rbx, [rsp+28h+arg_0]
0x180020664  mov     rsi, [rsp+28h+arg_8]
0x180020669  add     rsp, 20h
0x18002066d  pop     rdi
0x18002066e  retn
```

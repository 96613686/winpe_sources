# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(void)

- ea: `0x18002008c`
- end: `0x180020122`
- name: `??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `150`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800202fc`
- `0x1800204f4`
- `0x18002ab20`
- `0x18002ac44`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x18002008c`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
        char **a1)
{
  char *v1; // rbx
  char *v3; // rsi
  char *v4; // rax
  char *v5; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1);
      v1 += 32;
    }
    v4 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18002008c  mov     [rsp+arg_0], rbx
0x180020091  mov     [rsp+arg_8], rsi
0x180020096  push    rdi
0x180020097  sub     rsp, 20h
0x18002009b  mov     rbx, [rcx]
0x18002009e  mov     rdi, rcx
0x1800200a1  test    rbx, rbx
0x1800200a4  jz      short loc_180020111
0x1800200a6  mov     rsi, [rcx+8]
0x1800200aa  jmp     short loc_1800200B8
0x1800200ac  mov     rcx, rbx
0x1800200af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800200b4  add     rbx, 20h ; ' '
0x1800200b8  cmp     rbx, rsi
0x1800200bb  jnz     short loc_1800200AC
0x1800200bd  mov     rax, [rdi]
0x1800200c0  mov     rdx, [rdi+10h]
0x1800200c4  sub     rdx, rax
0x1800200c7  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x1800200cb  cmp     rdx, 1000h
0x1800200d2  jb      short loc_1800200F2
0x1800200d4  mov     rcx, [rax-8]
0x1800200d8  sub     rax, rcx
0x1800200db  sub     rax, 8
0x1800200df  cmp     rax, 1Fh
0x1800200e3  ja      short loc_1800200EB
0x1800200e5  add     rdx, 27h ; '''
0x1800200e9  jmp     short loc_1800200F5
0x1800200eb  mov     ecx, 5
0x1800200f0  int     29h; Win8: RtlFailFast(ecx)
0x1800200f2  mov     rcx, rax; void *
0x1800200f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800200fa  mov     qword ptr [rdi], 0
0x180020101  mov     qword ptr [rdi+8], 0
0x180020109  mov     qword ptr [rdi+10h], 0
0x180020111  mov     rbx, [rsp+28h+arg_0]
0x180020116  mov     rsi, [rsp+28h+arg_8]
0x18002011b  add     rsp, 20h
0x18002011f  pop     rdi
0x180020120  retn
```

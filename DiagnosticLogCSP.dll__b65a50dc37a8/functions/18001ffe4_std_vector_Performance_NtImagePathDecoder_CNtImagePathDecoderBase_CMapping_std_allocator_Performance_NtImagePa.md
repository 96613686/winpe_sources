# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x18001ffe4`
- end: `0x180020083`
- name: `??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `159`
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
- `0x18001ffe4`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(
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
      std::wstring::~wstring(v1 + 32);
      std::wstring::~wstring(v1);
      v1 += 64;
    }
    v4 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL) < 0x1000 )
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
0x18001ffe4  mov     [rsp+arg_0], rbx
0x18001ffe9  mov     [rsp+arg_8], rsi
0x18001ffee  push    rdi
0x18001ffef  sub     rsp, 20h
0x18001fff3  mov     rbx, [rcx]
0x18001fff6  mov     rdi, rcx
0x18001fff9  test    rbx, rbx
0x18001fffc  jz      short loc_180020072
0x18001fffe  mov     rsi, [rcx+8]
0x180020002  jmp     short loc_180020019
0x180020004  lea     rcx, [rbx+20h]
0x180020008  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002000d  mov     rcx, rbx
0x180020010  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020015  add     rbx, 40h ; '@'
0x180020019  cmp     rbx, rsi
0x18002001c  jnz     short loc_180020004
0x18002001e  mov     rax, [rdi]
0x180020021  mov     rdx, [rdi+10h]
0x180020025  sub     rdx, rax
0x180020028  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18002002c  cmp     rdx, 1000h
0x180020033  jb      short loc_180020053
0x180020035  mov     rcx, [rax-8]
0x180020039  sub     rax, rcx
0x18002003c  sub     rax, 8
0x180020040  cmp     rax, 1Fh
0x180020044  ja      short loc_18002004C
0x180020046  add     rdx, 27h ; '''
0x18002004a  jmp     short loc_180020056
0x18002004c  mov     ecx, 5
0x180020051  int     29h; Win8: RtlFailFast(ecx)
0x180020053  mov     rcx, rax; void *
0x180020056  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002005b  mov     qword ptr [rdi], 0
0x180020062  mov     qword ptr [rdi+8], 0
0x18002006a  mov     qword ptr [rdi+10h], 0
0x180020072  mov     rbx, [rsp+28h+arg_0]
0x180020077  mov     rsi, [rsp+28h+arg_8]
0x18002007c  add     rsp, 20h
0x180020080  pop     rdi
0x180020081  retn
```

# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x18000e3d0`
- end: `0x18000e46e`
- name: `??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e6cc`
- `0x18000e8b4`
- `0x180018a9c`
- `0x180018bc4`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e3d0`

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
0x18000e3d0  mov     [rsp+arg_0], rbx
0x18000e3d5  mov     [rsp+arg_8], rsi
0x18000e3da  push    rdi
0x18000e3db  sub     rsp, 20h
0x18000e3df  mov     rbx, [rcx]
0x18000e3e2  mov     rdi, rcx
0x18000e3e5  test    rbx, rbx
0x18000e3e8  jz      short loc_18000E45E
0x18000e3ea  mov     rsi, [rcx+8]
0x18000e3ee  jmp     short loc_18000E405
0x18000e3f0  lea     rcx, [rbx+20h]
0x18000e3f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e3f9  mov     rcx, rbx
0x18000e3fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e401  add     rbx, 40h ; '@'
0x18000e405  cmp     rbx, rsi
0x18000e408  jnz     short loc_18000E3F0
0x18000e40a  mov     rax, [rdi]
0x18000e40d  mov     rdx, [rdi+10h]
0x18000e411  sub     rdx, rax
0x18000e414  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18000e418  cmp     rdx, 1000h
0x18000e41f  jb      short loc_18000E43F
0x18000e421  mov     rcx, [rax-8]
0x18000e425  sub     rax, rcx
0x18000e428  sub     rax, 8
0x18000e42c  cmp     rax, 1Fh
0x18000e430  ja      short loc_18000E438
0x18000e432  add     rdx, 27h ; '''
0x18000e436  jmp     short loc_18000E442
0x18000e438  mov     ecx, 5
0x18000e43d  int     29h; Win8: RtlFailFast(ecx)
0x18000e43f  mov     rcx, rax; Block
0x18000e442  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e447  mov     qword ptr [rdi], 0
0x18000e44e  mov     qword ptr [rdi+8], 0
0x18000e456  mov     qword ptr [rdi+10h], 0
0x18000e45e  mov     rbx, [rsp+28h+arg_0]
0x18000e463  mov     rsi, [rsp+28h+arg_8]
0x18000e468  add     rsp, 20h
0x18000e46c  pop     rdi
0x18000e46d  retn
```

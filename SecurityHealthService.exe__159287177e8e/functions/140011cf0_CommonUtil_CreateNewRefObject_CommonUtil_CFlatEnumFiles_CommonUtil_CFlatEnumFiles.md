# CommonUtil::CreateNewRefObject<CommonUtil::CFlatEnumFiles>(CommonUtil::CFlatEnumFiles * *)

- ea: `0x140011cf0`
- end: `0x140011d71`
- name: `??$CreateNewRefObject@VCFlatEnumFiles@CommonUtil@@@CommonUtil@@YAJPEAPEAVCFlatEnumFiles@0@@Z`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011260`

## callees

- `0x14000162c`
- `0x140011cf0`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::CreateNewRefObject<CommonUtil::CFlatEnumFiles>(_QWORD *a1)
{
  _DWORD *v2; // rax
  CommonUtil *v3; // rcx
  _DWORD *v4; // rbx
  __int64 result; // rax
  __int64 v6; // [rsp+0h] [rbp-38h] BYREF
  const std::exception *v7; // [rsp+20h] [rbp-18h] BYREF

  v2 = operator new(0x288u, (const struct std::nothrow_t *)&std::nothrow);
  try
  {
    v4 = v2;
    if ( v2 )
    {
      v2[2] = 0;
      *(_QWORD *)v2 = &CommonUtil::CFlatEnumFiles::`vftable';
      *((_QWORD *)v2 + 2) = 0;
      *((_QWORD *)v2 + 3) = 0;
      *((_QWORD *)v2 + 4) = 0;
      *((_QWORD *)v2 + 79) = 0;
      v2[160] = 0;
      (**(void (__fastcall ***)(void *))v2)(v2);
      *a1 = v4;
      result = 0;
    }
    else
    {
      result = 2147942414LL;
    }
  }
  catch ( const std::exception *v7 )
  {
    CommonUtil::HrFromStdException(v3, (const struct std::exception *)&v6);
  }
  v4 = v2;
}

```

## disassembly

```asm
0x140011cf0  mov     [rsp+arg_0], rbx
0x140011cf5  push    rdi
0x140011cf6  sub     rsp, 30h
0x140011cfa  mov     rdi, rcx
0x140011cfd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011d04  mov     ecx, 288h; unsigned __int64
0x140011d09  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011d0e  mov     rbx, rax
0x140011d11  xor     eax, eax
0x140011d13  test    rbx, rbx
0x140011d16  jz      short loc_140011D53
0x140011d18  mov     [rbx+8], eax
0x140011d1b  lea     rcx, ??_7CFlatEnumFiles@CommonUtil@@6B@; const CommonUtil::CFlatEnumFiles::`vftable'
0x140011d22  mov     [rbx], rcx
0x140011d25  mov     [rbx+10h], rax
0x140011d29  mov     [rbx+18h], rax
0x140011d2d  mov     [rbx+20h], rax
0x140011d31  mov     [rbx+278h], rax
0x140011d38  mov     [rbx+280h], eax
0x140011d3e  mov     rcx, [rbx]
0x140011d41  mov     rax, [rcx]
0x140011d44  mov     rcx, rbx
0x140011d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d4c  mov     [rdi], rbx
0x140011d4f  xor     eax, eax
0x140011d51  jmp     short loc_140011D65
0x140011d53  mov     eax, 8007000Eh
0x140011d58  jmp     short loc_140011D65
0x140011d5a  xor     eax, eax
0x140011d5c  cmp     [rsp+38h+arg_8], eax
0x140011d60  cmovl   eax, [rsp+38h+arg_10]
0x140011d65  mov     rbx, [rsp+38h+arg_0]
0x140011d6a  add     rsp, 30h
0x140011d6e  pop     rdi
0x140011d6f  retn
```

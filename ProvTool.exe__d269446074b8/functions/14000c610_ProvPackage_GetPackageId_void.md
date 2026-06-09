# ProvPackage::GetPackageId(void)

- ea: `0x14000c610`
- end: `0x14000c7a8`
- name: `?GetPackageId@ProvPackage@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `408`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140008b88`
- `0x140008cd8`
- `0x140008e50`
- `0x14000c610`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000c6a1`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000c6a1`

## pseudocode

```c
_QWORD *__fastcall ProvPackage::GetPackageId(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v4; // rbp
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // r8
  int v12[2]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD *v13; // [rsp+28h] [rbp-90h]
  _WORD Src[40]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v13 = a2;
  v4 = a1 + 15;
  if ( a1[17] )
  {
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign(a2, a1 + 15, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    v5 = 0;
    v13 = 0;
    *(_QWORD *)v12 = 0;
    v6 = (_QWORD *)a1[13];
    if ( v6 )
    {
      *(_QWORD *)v12 = v6;
    }
    else
    {
      v7 = a1 + 1;
      if ( a1[4] >= 8u )
        v7 = (_QWORD *)*v7;
      v8 = OpenProvisioningPackageForRead(v7, v12);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A5,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
          (const char *)(unsigned int)v8,
          v12[0]);
      v6 = *(_QWORD **)v12;
      if ( *(_QWORD *)v12 )
        v5 = *(_QWORD **)v12;
      v13 = v5;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD *, _WORD *, __int64))(*v6 + 64LL))(v6, Src, 39);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
        (const char *)(unsigned int)v9,
        v12[0]);
    if ( Src[0] )
    {
      v10 = -1;
      do
        ++v10;
      while ( Src[v10] );
    }
    else
    {
      v10 = 0;
    }
    std::wstring::assign(v4, (char *)Src, v10);
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
    std::wstring::assign(a2, v4, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD *))(*v5 + 128LL))(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x14000c610  mov     [rsp+arg_10], rbx
0x14000c615  push    rbp
0x14000c616  push    rdi
0x14000c617  push    r14
0x14000c619  sub     rsp, 0A0h
0x14000c620  mov     rax, cs:__security_cookie
0x14000c627  xor     rax, rsp
0x14000c62a  mov     [rsp+0B8h+var_28], rax
0x14000c632  mov     rdi, rdx
0x14000c635  mov     rax, rcx
0x14000c638  mov     [rsp+0B8h+var_90], rdx
0x14000c63d  xor     r14d, r14d
0x14000c640  lea     rbp, [rcx+78h]
0x14000c644  cmp     [rbp+10h], r14
0x14000c648  jz      short loc_14000C671
0x14000c64a  mov     qword ptr [rdx+18h], 7
0x14000c652  mov     [rdx+10h], r14
0x14000c656  mov     [rdx], r14w
0x14000c65a  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000c65e  xor     r8d, r8d
0x14000c661  mov     rdx, rbp
0x14000c664  mov     rcx, rdi; void *
0x14000c667  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c66c  jmp     loc_14000C757
0x14000c671  mov     rbx, r14
0x14000c674  mov     [rsp+0B8h+var_90], rbx
0x14000c679  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x14000c67e  mov     rcx, [rcx+68h]
0x14000c682  test    rcx, rcx
0x14000c685  jz      short loc_14000C68E
0x14000c687  mov     qword ptr [rsp+0B8h+var_98], rcx
0x14000c68c  jmp     short loc_14000C6C8
0x14000c68e  lea     rcx, [rax+8]
0x14000c692  cmp     qword ptr [rcx+18h], 8
0x14000c697  jb      short loc_14000C69C
0x14000c699  mov     rcx, [rcx]
0x14000c69c  lea     rdx, [rsp+0B8h+var_98]
0x14000c6a1  call    cs:__imp_OpenProvisioningPackageForRead
0x14000c6a7  mov     rcx, [rsp+0B8h]; this
0x14000c6af  test    eax, eax
0x14000c6b1  js      loc_14000C793
0x14000c6b7  mov     rcx, qword ptr [rsp+0B8h+var_98]
0x14000c6bc  test    rcx, rcx
0x14000c6bf  cmovnz  rbx, rcx
0x14000c6c3  mov     [rsp+0B8h+var_90], rbx
0x14000c6c8  mov     rax, [rcx]
0x14000c6cb  mov     r8d, 27h ; '''
0x14000c6d1  lea     rdx, [rsp+0B8h+Src]
0x14000c6d6  mov     rax, [rax+40h]
0x14000c6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6df  mov     rcx, [rsp+0B8h]; this
0x14000c6e7  test    eax, eax
0x14000c6e9  js      loc_14000C77E
0x14000c6ef  cmp     [rsp+0B8h+Src], r14w
0x14000c6f5  jnz     short loc_14000C6FC
0x14000c6f7  mov     r8, r14
0x14000c6fa  jmp     short loc_14000C70F
0x14000c6fc  lea     rax, [rsp+0B8h+Src]
0x14000c701  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000c705  inc     r8
0x14000c708  cmp     [rax+r8*2], r14w
0x14000c70d  jnz     short loc_14000C705
0x14000c70f  lea     rdx, [rsp+0B8h+Src]; Src
0x14000c714  mov     rcx, rbp; void *
0x14000c717  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000c71c  mov     qword ptr [rdi+18h], 7
0x14000c724  mov     [rdi+10h], r14
0x14000c728  mov     [rdi], r14w
0x14000c72c  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000c730  xor     r8d, r8d
0x14000c733  mov     rdx, rbp
0x14000c736  mov     rcx, rdi; void *
0x14000c739  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000c73e  nop
0x14000c73f  test    rbx, rbx
0x14000c742  jz      short loc_14000C757
0x14000c744  mov     rax, [rbx]
0x14000c747  mov     rcx, rbx
0x14000c74a  mov     rax, [rax+80h]
0x14000c751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c756  nop
0x14000c757  mov     rax, rdi
0x14000c75a  mov     rcx, [rsp+0B8h+var_28]
0x14000c762  xor     rcx, rsp; StackCookie
0x14000c765  call    __security_check_cookie
0x14000c76a  mov     rbx, [rsp+0B8h+arg_10]
0x14000c772  add     rsp, 0A0h
0x14000c779  pop     r14
0x14000c77b  pop     rdi
0x14000c77c  pop     rbp
0x14000c77d  retn
0x14000c77e  mov     r9d, eax; char *
0x14000c781  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000c788  mov     edx, 1AAh; void *
0x14000c78d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c793  mov     r9d, eax; char *
0x14000c796  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x14000c79d  mov     edx, 1A5h; void *
0x14000c7a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

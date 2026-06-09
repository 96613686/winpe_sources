# ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)

- ea: `0x18002c264`
- end: `0x18002c32c`
- name: `?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z`
- size: `200`
- prototype: `bool __fastcall(ATL::CDacl *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18002cc8c`

## callees

- `0x18000e790`
- `0x180010ca0`
- `0x180012b70`
- `0x180019e00`
- `0x18001a414`
- `0x18001c058`
- `0x18002c264`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c307`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c307`

## pseudocode

```c
bool __fastcall ATL::CDacl::AddAllowedAce(ATL::CDacl *this, const struct ATL::CSid *a2)
{
  ATL::CDacl *v3; // rbx
  bool result; // al
  ATL::CDacl::CAccessAce *v5; // rax
  ATL::CDacl::CAccessAce *v6; // [rsp+30h] [rbp-18h] BYREF
  ATL::CDacl::CAccessAce *v7; // [rsp+38h] [rbp-10h]

  v3 = this;
  result = ATL::CSid::IsValid(a2);
  if ( result )
  {
    if ( *((_BYTE *)v3 + 16) )
    {
      (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)v3 + 16LL))(v3);
      *((_BYTE *)v3 + 16) = 0;
    }
    try
    {
      v7 = (ATL::CDacl::CAccessAce *)operator new(0x98u);
      v5 = ATL::CDacl::CAccessAce::CAccessAce(v7, a2, 2032127, 3, 1);
      v6 = v5;
    }
    catch ( ... )
    {
      v3 = this;
      v5 = v6;
    }
    if ( !v5 )
      ATL::AtlThrowImpl(-2147024882);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(
      (__int64)v3 + 24,
      (__int64 *)&v6);
    free(*((void **)v3 + 1));
    *((_QWORD *)v3 + 1) = 0;
    ATL::CAutoPtr<ATL::CDacl::CAccessAce>::Free(&v6);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002c264  mov     [rsp+arg_8], rbx
0x18002c269  mov     [rsp+arg_0], rcx
0x18002c26e  push    rdi
0x18002c26f  sub     rsp, 40h
0x18002c273  mov     rdi, rdx
0x18002c276  mov     rbx, rcx
0x18002c279  mov     rcx, rdx; this
0x18002c27c  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18002c281  test    al, al
0x18002c283  jz      loc_18002C321
0x18002c289  cmp     byte ptr [rbx+10h], 0
0x18002c28d  jz      short loc_18002C2A2
0x18002c28f  mov     rax, [rbx]
0x18002c292  mov     rcx, rbx
0x18002c295  mov     rax, [rax+10h]
0x18002c299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c29e  mov     byte ptr [rbx+10h], 0
0x18002c2a2  mov     [rsp+48h+var_18], 0
0x18002c2ab  mov     ecx, 98h; Size
0x18002c2b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c2b5  mov     [rsp+48h+var_10], rax
0x18002c2ba  mov     [rsp+48h+var_28], 1; bool
0x18002c2bf  mov     r9b, 3; unsigned __int8
0x18002c2c2  mov     r8d, 1F01FFh; unsigned int
0x18002c2c8  mov     rdx, rdi; struct ATL::CSid *
0x18002c2cb  mov     rcx, rax; this
0x18002c2ce  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x18002c2d3  nop
0x18002c2d4  mov     [rsp+48h+var_18], rax
0x18002c2d9  jmp     short loc_18002C2E5
0x18002c2db  mov     rbx, [rsp+48h+arg_0]
0x18002c2e0  mov     rax, [rsp+48h+var_18]
0x18002c2e5  test    rax, rax
0x18002c2e8  jnz     short loc_18002C2F5
0x18002c2ea  mov     ecx, 8007000Eh; int
0x18002c2ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c2f5  lea     rcx, [rbx+18h]
0x18002c2f9  lea     rdx, [rsp+48h+var_18]
0x18002c2fe  call    ?Add@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_KAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)
0x18002c303  mov     rcx, [rbx+8]; Block
0x18002c307  call    cs:__imp_free
0x18002c30d  mov     qword ptr [rbx+8], 0
0x18002c315  lea     rcx, [rsp+48h+var_18]
0x18002c31a  call    ?Free@?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@QEAAXXZ; ATL::CAutoPtr<ATL::CDacl::CAccessAce>::Free(void)
0x18002c31f  mov     al, 1
0x18002c321  mov     rbx, [rsp+48h+arg_8]
0x18002c326  add     rsp, 40h
0x18002c32a  pop     rdi
0x18002c32b  retn
```

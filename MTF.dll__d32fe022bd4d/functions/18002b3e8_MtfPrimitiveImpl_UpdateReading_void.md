# MtfPrimitiveImpl::_UpdateReading(void)

- ea: `0x18002b3e8`
- end: `0x18002b483`
- name: `?_UpdateReading@MtfPrimitiveImpl@@IEAAXXZ`
- size: `155`
- prototype: `void __fastcall(MtfPrimitiveImpl *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180028120`
- `0x180028470`
- `0x1800299b0`
- `0x180029bc0`

## callees

- `0x18001e1f4`
- `0x18002b3e8`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b45d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b45d`

## pseudocode

```c
void __fastcall MtfPrimitiveImpl::_UpdateReading(MtfPrimitiveImpl *this)
{
  int v2; // eax
  int v3[2]; // [rsp+20h] [rbp-48h] BYREF
  BSTR v4; // [rsp+28h] [rbp-40h]
  __int128 v5; // [rsp+30h] [rbp-38h]
  __int128 v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  OLECHAR *psz; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 5) )
  {
    psz = 0;
    v2 = (*(__int64 (__fastcall **)(char *, OLECHAR **))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16, &psz);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B1,
        (unsigned int)"mincore\\TextInput\\Dev\\mtf\\PredictionEngine\\Containers\\Primitive.cpp",
        (const char *)(unsigned int)v2,
        v3[0]);
    v3[1] = 0;
    v3[0] = 1;
    v5 = 0;
    v7 = 0;
    v6 = 0;
    v4 = SysAllocString(psz);
    (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, v3);
  }
}

```

## disassembly

```asm
0x18002b3e8  push    rbx
0x18002b3ea  sub     rsp, 60h
0x18002b3ee  cmp     qword ptr [rcx+28h], 0
0x18002b3f3  mov     rbx, rcx
0x18002b3f6  jnz     loc_18002B47D
0x18002b3fc  add     rcx, 10h
0x18002b400  mov     [rsp+68h+psz], 0
0x18002b409  lea     rdx, [rsp+68h+psz]
0x18002b40e  mov     rax, [rcx]
0x18002b411  mov     rax, [rax+28h]
0x18002b415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b41a  test    eax, eax
0x18002b41c  jns     short loc_18002B437
0x18002b41e  mov     rcx, [rsp+68h]; this
0x18002b423  lea     r8, aMincoreTextinp_8; "mincore\\TextInput\\Dev\\mtf\\Predictio"...
0x18002b42a  mov     r9d, eax; char *
0x18002b42d  mov     edx, 2B1h; void *
0x18002b432  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b437  mov     rcx, [rsp+68h+psz]; psz
0x18002b43c  xorps   xmm0, xmm0
0x18002b43f  xor     eax, eax
0x18002b441  movups  [rsp+68h+var_48], xmm0
0x18002b446  mov     dword ptr [rsp+68h+var_48], 1
0x18002b44e  movups  [rsp+68h+var_38], xmm0
0x18002b453  mov     [rsp+68h+var_18], rax
0x18002b458  movups  [rsp+68h+var_28], xmm0
0x18002b45d  call    cs:__imp_SysAllocString
0x18002b463  mov     qword ptr [rsp+68h+var_48+8], rax
0x18002b468  lea     rcx, [rbx+8]
0x18002b46c  mov     rax, [rcx]
0x18002b46f  lea     rdx, [rsp+68h+var_48]
0x18002b474  mov     rax, [rax+30h]
0x18002b478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b47d  add     rsp, 60h
0x18002b481  pop     rbx
0x18002b482  retn
```

# MtfPrimitiveImpl::_UpdateDisplay(void)

- ea: `0x18002b344`
- end: `0x18002b3df`
- name: `?_UpdateDisplay@MtfPrimitiveImpl@@IEAAXXZ`
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
- `0x18002b344`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b3b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b3b9`

## pseudocode

```c
void __fastcall MtfPrimitiveImpl::_UpdateDisplay(MtfPrimitiveImpl *this)
{
  int v2; // eax
  __int128 v3; // [rsp+20h] [rbp-48h] BYREF
  __int128 v4; // [rsp+30h] [rbp-38h]
  __int128 v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  OLECHAR *psz; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 4) )
  {
    psz = 0;
    v2 = (*(__int64 (__fastcall **)(char *, OLECHAR **))(*((_QWORD *)this + 2) + 32LL))((char *)this + 16, &psz);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"mincore\\TextInput\\Dev\\mtf\\PredictionEngine\\Containers\\Primitive.cpp",
        (const char *)(unsigned int)v2,
        v3);
    v3 = 0;
    LODWORD(v3) = 2;
    v4 = 0;
    v6 = 0;
    v5 = 0;
    *(_QWORD *)&v4 = SysAllocString(psz);
    (*(void (__fastcall **)(char *, __int128 *))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, &v3);
  }
}

```

## disassembly

```asm
0x18002b344  push    rbx
0x18002b346  sub     rsp, 60h
0x18002b34a  cmp     qword ptr [rcx+20h], 0
0x18002b34f  mov     rbx, rcx
0x18002b352  jnz     loc_18002B3D9
0x18002b358  add     rcx, 10h
0x18002b35c  mov     [rsp+68h+psz], 0
0x18002b365  lea     rdx, [rsp+68h+psz]
0x18002b36a  mov     rax, [rcx]
0x18002b36d  mov     rax, [rax+20h]
0x18002b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b376  test    eax, eax
0x18002b378  jns     short loc_18002B393
0x18002b37a  mov     rcx, [rsp+68h]; this
0x18002b37f  lea     r8, aMincoreTextinp_8; "mincore\\TextInput\\Dev\\mtf\\Predictio"...
0x18002b386  mov     r9d, eax; char *
0x18002b389  mov     edx, 2C0h; void *
0x18002b38e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b393  mov     rcx, [rsp+68h+psz]; psz
0x18002b398  xorps   xmm0, xmm0
0x18002b39b  xor     eax, eax
0x18002b39d  movups  [rsp+68h+var_48], xmm0
0x18002b3a2  mov     dword ptr [rsp+68h+var_48], 2
0x18002b3aa  movups  [rsp+68h+var_38], xmm0
0x18002b3af  mov     [rsp+68h+var_18], rax
0x18002b3b4  movups  [rsp+68h+var_28], xmm0
0x18002b3b9  call    cs:__imp_SysAllocString
0x18002b3bf  mov     qword ptr [rsp+68h+var_38], rax
0x18002b3c4  lea     rcx, [rbx+8]
0x18002b3c8  mov     rax, [rcx]
0x18002b3cb  lea     rdx, [rsp+68h+var_48]
0x18002b3d0  mov     rax, [rax+30h]
0x18002b3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3d9  add     rsp, 60h
0x18002b3dd  pop     rbx
0x18002b3de  retn
```

# Windows::Security::Isolation::ShellObjectBroker::ParseDisplayName(ushort const *,_ITEMIDLIST * *,ulong,ulong *,IBindCtx *)

- ea: `0x140010390`
- end: `0x1400103d9`
- name: `?ParseDisplayName@ShellObjectBroker@Isolation@Security@Windows@@UEAAJPEBGPEAPEFAU_ITEMIDLIST@@KPEAKPEAUIBindCtx@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::ShellObjectBroker *this, const unsigned __int16 *, struct _ITEMIDLIST **, SFGAOF, unsigned int *, struct IBindCtx *pbc)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005084`
- `0x140010390`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1400103a8`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1400103a8`

## string_xrefs

- `0x1400103b9`: `onecoreuap\ds\security\isolation\broker\lib\shellobjectbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::ShellObjectBroker::ParseDisplayName(
        Windows::Security::Isolation::ShellObjectBroker *this,
        const unsigned __int16 *a2,
        struct _ITEMIDLIST **a3,
        SFGAOF a4,
        unsigned int *a5,
        struct IBindCtx *pbc)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int psfgaoOut; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = SHParseDisplayName(a2, pbc, a3, a4, a5);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\shellobjectbroker.cpp",
    (const char *)(unsigned int)v6,
    psfgaoOut);
  return v7;
}

```

## disassembly

```asm
0x140010390  push    rbx
0x140010392  sub     rsp, 30h
0x140010396  mov     rax, [rsp+38h+arg_20]
0x14001039b  mov     rcx, rdx; pszName
0x14001039e  mov     rdx, [rsp+38h+pbc]; pbc
0x1400103a3  mov     qword ptr [rsp+38h+psfgaoOut], rax; int
0x1400103a8  call    cs:__imp_SHParseDisplayName
0x1400103ae  mov     ebx, eax
0x1400103b0  test    eax, eax
0x1400103b2  jns     short loc_1400103D1
0x1400103b4  mov     rcx, [rsp+38h]; this
0x1400103b9  lea     r8, aOnecoreuapDsSe_4; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400103c0  mov     r9d, eax; char *
0x1400103c3  mov     edx, 58h ; 'X'; void *
0x1400103c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400103cd  mov     eax, ebx
0x1400103cf  jmp     short loc_1400103D3
0x1400103d1  xor     eax, eax
0x1400103d3  add     rsp, 30h
0x1400103d7  pop     rbx
0x1400103d8  retn
```

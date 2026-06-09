# DiskFolder::CompareIDsInternal(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180005dc0`
- end: `0x180005e63`
- name: `?CompareIDsInternal@DiskFolder@@MEAAIPEFBU_ITEMIDLIST_RELATIVE@@0@Z`
- size: `163`
- prototype: `__int64 __fastcall(DiskFolder *this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005dc0`
- `0x180007150`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiskFolder::CompareIDsInternal(
        DiskFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3)
{
  int v3; // ecx
  int v4; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = 1;
  if ( !a2 || (v4 = 0, !*(_WORD *)a2) )
    v4 = 1;
  if ( a3 && *(_WORD *)a3 )
    v3 = 0;
  if ( !v4 && !v3 )
  {
    if ( !a2 || *(_WORD *)a2 < 0x32u )
    {
      v6 = wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\Utility.h",
        (const char *)v6,
        v8);
    }
    if ( !a3 || *(_WORD *)a3 < 0x32u )
    {
      v7 = wil::verify_hresult<long>(0x80070057);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\Utility.h",
        (const char *)v7,
        v8);
    }
    v3 = *((unsigned __int16 *)a2 + 3);
    v4 = *((unsigned __int16 *)a3 + 3);
  }
  return (unsigned int)(v3 - v4);
}

```

## disassembly

```asm
0x180005dc0  sub     rsp, 28h
0x180005dc4  xor     r9d, r9d
0x180005dc7  mov     ecx, 1
0x180005dcc  test    rdx, rdx
0x180005dcf  jz      short loc_180005DDA
0x180005dd1  mov     eax, r9d
0x180005dd4  cmp     [rdx], r9w
0x180005dd8  jnz     short loc_180005DDC
0x180005dda  mov     eax, ecx
0x180005ddc  test    r8, r8
0x180005ddf  jz      short loc_180005DEA
0x180005de1  cmp     [r8], r9w
0x180005de5  jz      short loc_180005DEA
0x180005de7  mov     ecx, r9d
0x180005dea  test    eax, eax
0x180005dec  jnz     short loc_180005E12
0x180005dee  test    ecx, ecx
0x180005df0  jnz     short loc_180005E12
0x180005df2  test    rdx, rdx
0x180005df5  jz      short loc_180005E1B
0x180005df7  cmp     word ptr [rdx], 32h ; '2'
0x180005dfb  jb      short loc_180005E1B
0x180005dfd  test    r8, r8
0x180005e00  jz      short loc_180005E3F
0x180005e02  cmp     word ptr [r8], 32h ; '2'
0x180005e07  jb      short loc_180005E3F
0x180005e09  movzx   ecx, word ptr [rdx+6]
0x180005e0d  movzx   eax, word ptr [r8+6]
0x180005e12  sub     ecx, eax
0x180005e14  mov     eax, ecx
0x180005e16  add     rsp, 28h
0x180005e1a  retn
0x180005e1b  mov     ecx, 80070057h
0x180005e20  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180005e25  mov     rcx, [rsp+28h]; this
0x180005e2a  lea     r8, aVmUxUiRemotefi_11; "vm\\ux\\ui\\remotefilebrowse\\Utility.h"
0x180005e31  mov     r9d, eax; char *
0x180005e34  mov     edx, 118h; void *
0x180005e39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005e3f  mov     ecx, 80070057h
0x180005e44  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180005e49  mov     rcx, [rsp+28h]; this
0x180005e4e  lea     r8, aVmUxUiRemotefi_11; "vm\\ux\\ui\\remotefilebrowse\\Utility.h"
0x180005e55  mov     r9d, eax; char *
0x180005e58  mov     edx, 118h; void *
0x180005e5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

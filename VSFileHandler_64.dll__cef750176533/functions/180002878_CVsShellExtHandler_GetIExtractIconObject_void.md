# CVsShellExtHandler::GetIExtractIconObject(void)

- ea: `0x180002878`
- end: `0x180002942`
- name: `?GetIExtractIconObject@CVsShellExtHandler@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CVsShellExtHandler *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002960`
- `0x1800029e0`

## callees

- `0x180002878`
- `0x180007700`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x1800028e2`
- `SHELL32!SHBindToParent` at `0x1800028e2`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x1800028bd`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x1800028bd`

## pseudocode

```c
void __fastcall CVsShellExtHandler::GetIExtractIconObject(CVsShellExtHandler *this)
{
  const ITEMIDLIST *v2; // rax
  LPCITEMIDLIST ppidlLast; // [rsp+40h] [rbp-28h] BYREF
  void *ppv; // [rsp+48h] [rbp-20h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    *((_BYTE *)this + 32) = 1;
    if ( *((int *)this + 9) >= 0 )
    {
      ppv = 0;
      v2 = SHSimpleIDListFromPath(off_18002F200[*((int *)this + 9)]);
      ppidlLast = 0;
      if ( v2 && SHBindToParent(v2, &IID_IShellFolder, &ppv, &ppidlLast) >= 0 )
        (*(void (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, char *))(*(_QWORD *)ppv + 80LL))(
          ppv,
          0,
          1,
          &ppidlLast,
          &IID_IExtractIconW,
          0,
          (char *)this + 40);
      if ( ppv )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x180002878  push    rbx
0x18000287a  sub     rsp, 60h
0x18000287e  mov     rax, cs:__security_cookie
0x180002885  xor     rax, rsp
0x180002888  mov     [rsp+68h+var_18], rax
0x18000288d  mov     rbx, rcx
0x180002890  cmp     byte ptr [rcx+20h], 0
0x180002894  jnz     loc_18000292F
0x18000289a  mov     byte ptr [rcx+20h], 1
0x18000289e  cmp     dword ptr [rcx+24h], 0
0x1800028a2  jl      loc_18000292F
0x1800028a8  and     [rsp+68h+ppv], 0
0x1800028ae  movsxd  rcx, dword ptr [rcx+24h]
0x1800028b2  lea     rax, off_18002F200; "c:\\_sln60._sln60"
0x1800028b9  mov     rcx, [rax+rcx*8]; pszPath
0x1800028bd  call    cs:__imp_SHSimpleIDListFromPath
0x1800028c3  and     [rsp+68h+ppidlLast], 0
0x1800028c9  test    rax, rax
0x1800028cc  jz      short loc_18000291F
0x1800028ce  lea     r9, [rsp+68h+ppidlLast]; ppidlLast
0x1800028d3  lea     r8, [rsp+68h+ppv]; ppv
0x1800028d8  lea     rdx, IID_IShellFolder; riid
0x1800028df  mov     rcx, rax; pidl
0x1800028e2  call    cs:__imp_SHBindToParent
0x1800028e8  test    eax, eax
0x1800028ea  js      short loc_18000291F
0x1800028ec  mov     rcx, [rsp+68h+ppv]
0x1800028f1  mov     r10, [rcx]
0x1800028f4  lea     rax, [rbx+28h]
0x1800028f8  mov     [rsp+68h+var_38], rax
0x1800028fd  and     [rsp+68h+var_40], 0
0x180002903  lea     rax, IID_IExtractIconW
0x18000290a  mov     [rsp+68h+var_48], rax
0x18000290f  lea     r9, [rsp+68h+ppidlLast]
0x180002914  xor     edx, edx
0x180002916  lea     r8d, [rdx+1]
0x18000291a  call    qword ptr [r10+50h]
0x18000291e  nop
0x18000291f  mov     rcx, [rsp+68h+ppv]
0x180002924  test    rcx, rcx
0x180002927  jz      short loc_18000292F
0x180002929  mov     rax, [rcx]
0x18000292c  call    qword ptr [rax+10h]
0x18000292f  mov     rcx, [rsp+68h+var_18]
0x180002934  xor     rcx, rsp; StackCookie
0x180002937  call    __security_check_cookie
0x18000293c  add     rsp, 60h
0x180002940  pop     rbx
0x180002941  retn
```

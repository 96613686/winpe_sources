# CompareItems(IShellItem *,IShellItem *,COMPARE_ITEMS_RESULT *)

- ea: `0x1800294fc`
- end: `0x1800295ee`
- name: `?CompareItems@@YAJPEAUIShellItem@@0PEAW4COMPARE_ITEMS_RESULT@@@Z`
- size: `242`
- prototype: `int(struct IShellItem *, struct IShellItem *, enum COMPARE_ITEMS_RESULT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039bfc`

## callees

- `0x1800294fc`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x180029527`
- `SHELL32!SHGetIDListFromObject` at `0x180029544`
- `SHELL32!SHGetIDListFromObject` at `0x180029527`
- `SHELL32!SHGetIDListFromObject` at `0x180029544`
- `SHELL32!__imp_ILIsEqual` at `0x18002958f`
- `SHELL32!__imp_ILIsEqual` at `0x18002958f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295d3`

## pseudocode

```c
__int64 __fastcall CompareItems(IUnknown *a1, IUnknown *a2, enum COMPARE_ITEMS_RESULT *a3)
{
  HRESULT v5; // esi
  LPCITEMIDLIST v6; // rcx
  LPITEMIDLIST v7; // rbx
  USHORT cb; // bp
  _WORD *v9; // rcx
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp+18h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+58h] [rbp+20h] BYREF

  *(_DWORD *)a3 = 1;
  pidl1 = 0;
  v5 = SHGetIDListFromObject(a1, (LPITEMIDLIST *)&pidl1);
  if ( v5 >= 0 )
  {
    ppidl = 0;
    v5 = SHGetIDListFromObject(a2, &ppidl);
    if ( v5 >= 0 )
    {
      v6 = pidl1;
      v7 = ppidl;
      while ( v6 && v6->mkid.cb )
      {
        if ( !v7 || !v7->mkid.cb )
          goto LABEL_15;
        v6 = (LPCITEMIDLIST)((char *)v6 + v6->mkid.cb);
        v7 = (LPITEMIDLIST)((char *)v7 + v7->mkid.cb);
      }
      cb = v7->mkid.cb;
      v7->mkid.cb = 0;
      if ( ILIsEqual(pidl1, ppidl) )
      {
        v7->mkid.cb = cb;
        if ( cb )
        {
          *(_DWORD *)a3 = 8;
          v9 = (USHORT *)((char *)&v7->mkid.cb + v7->mkid.cb);
          if ( !v9 || !*v9 )
            *(_DWORD *)a3 = 12;
        }
        else
        {
          *(_DWORD *)a3 = 2;
        }
      }
LABEL_15:
      CoTaskMemFree(ppidl);
    }
    CoTaskMemFree((LPVOID)pidl1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800294fc  mov     rax, rsp
0x1800294ff  mov     [rax+8], rbx
0x180029503  mov     [rax+10h], rbp
0x180029507  push    rsi
0x180029508  push    rdi
0x180029509  push    r14
0x18002950b  sub     rsp, 20h
0x18002950f  mov     rbx, rdx
0x180029512  mov     dword ptr [r8], 1
0x180029519  xor     r14d, r14d
0x18002951c  lea     rdx, [rax+20h]; ppidl
0x180029520  mov     [rax+20h], r14
0x180029524  mov     rdi, r8
0x180029527  call    cs:__imp_SHGetIDListFromObject
0x18002952d  mov     esi, eax
0x18002952f  test    eax, eax
0x180029531  js      loc_1800295D9
0x180029537  lea     rdx, [rsp+38h+ppidl]; ppidl
0x18002953c  mov     [rsp+38h+ppidl], r14
0x180029541  mov     rcx, rbx; punk
0x180029544  call    cs:__imp_SHGetIDListFromObject
0x18002954a  mov     esi, eax
0x18002954c  test    eax, eax
0x18002954e  js      short loc_1800295CE
0x180029550  mov     rcx, [rsp+38h+pidl1]
0x180029555  mov     rbx, [rsp+38h+ppidl]
0x18002955a  test    rcx, rcx
0x18002955d  jz      short loc_18002957E
0x18002955f  cmp     [rcx], r14w
0x180029563  jz      short loc_18002957E
0x180029565  test    rbx, rbx
0x180029568  jz      short loc_1800295C3
0x18002956a  cmp     [rbx], r14w
0x18002956e  jz      short loc_1800295C3
0x180029570  movzx   eax, word ptr [rcx]
0x180029573  add     rcx, rax
0x180029576  movzx   eax, word ptr [rbx]
0x180029579  add     rbx, rax
0x18002957c  jmp     short loc_18002955A
0x18002957e  movzx   ebp, word ptr [rbx]
0x180029581  mov     [rbx], r14w
0x180029585  mov     rdx, [rsp+38h+ppidl]; pidl2
0x18002958a  mov     rcx, [rsp+38h+pidl1]; pidl1
0x18002958f  call    cs:__imp_ILIsEqual
0x180029595  test    eax, eax
0x180029597  jz      short loc_1800295C3
0x180029599  mov     [rbx], bp
0x18002959c  test    bp, bp
0x18002959f  jnz     short loc_1800295A9
0x1800295a1  mov     dword ptr [rdi], 2
0x1800295a7  jmp     short loc_1800295C3
0x1800295a9  mov     dword ptr [rdi], 8
0x1800295af  movzx   ecx, word ptr [rbx]
0x1800295b2  add     rcx, rbx
0x1800295b5  jz      short loc_1800295BD
0x1800295b7  cmp     [rcx], r14w
0x1800295bb  jnz     short loc_1800295C3
0x1800295bd  mov     dword ptr [rdi], 0Ch
0x1800295c3  mov     rcx, [rsp+38h+ppidl]; pv
0x1800295c8  call    cs:__imp_CoTaskMemFree
0x1800295ce  mov     rcx, [rsp+38h+pidl1]; pv
0x1800295d3  call    cs:__imp_CoTaskMemFree
0x1800295d9  mov     rbx, [rsp+38h+arg_0]
0x1800295de  mov     eax, esi
0x1800295e0  mov     rbp, [rsp+38h+arg_8]
0x1800295e5  add     rsp, 20h
0x1800295e9  pop     r14
0x1800295eb  pop     rdi
0x1800295ec  pop     rsi
0x1800295ed  retn
```

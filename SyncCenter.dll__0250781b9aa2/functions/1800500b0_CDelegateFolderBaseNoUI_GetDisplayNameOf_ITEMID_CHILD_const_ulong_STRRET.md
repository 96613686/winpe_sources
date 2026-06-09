# CDelegateFolderBaseNoUI::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x1800500b0`
- end: `0x1800501b7`
- name: `?GetDisplayNameOf@CDelegateFolderBaseNoUI@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `263`
- prototype: `int(CDelegateFolderBaseNoUI *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800465a0`

## callees

- `0x18000f784`
- `0x18003482c`
- `0x1800500b0`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180050186`
- `SHLWAPI!SHStrDupW` at `0x180050186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050193`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::GetDisplayNameOf(
        CDelegateFolderBaseNoUI *this,
        const struct _ITEMID_CHILD *a2,
        __int64 a3,
        struct _STRRET *a4)
{
  __int64 *v5; // rcx
  unsigned int v7; // ebx
  __int64 v8; // r10
  int v9; // eax
  unsigned int v10; // r9d
  const ITEMIDLIST *v11; // rcx
  HRESULT v12; // ebx
  unsigned __int16 *v13; // rcx
  unsigned int *v15; // [rsp+20h] [rbp-268h]
  LPCWSTR psz[2]; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-248h] BYREF

  v5 = (__int64 *)((char *)this - 8);
  psz[0] = 0;
  v7 = a3;
  v8 = *v5;
  if ( (a3 & 0xC000) == 0x8000 )
    v9 = (*(__int64 (__fastcall **)(__int64 *, const struct _ITEMID_CHILD *, LPCWSTR *))(v8 + 88))(v5, a2, psz);
  else
    v9 = (*(__int64 (__fastcall **)(__int64 *, const struct _ITEMID_CHILD *, __int64, LPCWSTR *))(v8 + 72))(
           v5,
           a2,
           a3,
           psz);
  if ( v9 < 0 || !v7 || (v7 & 1) != 0 || (v11 = (const ITEMIDLIST *)*((_QWORD *)this + 5)) == 0 || !v11->mkid.cb )
  {
    v13 = (unsigned __int16 *)psz[0];
    goto LABEL_14;
  }
  v12 = SHGetNameAndFlagsW(v11, v7, v17, v10, v15);
  if ( v12 >= 0 )
  {
    v12 = StringCchCatW(v17, 0x104u, L"\\");
    if ( v12 >= 0 )
    {
      v12 = StringCchCatW(v17, 0x104u, psz[0]);
      if ( v12 >= 0 )
      {
        v13 = v17;
LABEL_14:
        a4->uType = 0;
        v12 = SHStrDupW(v13, &a4->pOleStr);
      }
    }
  }
  CoTaskMemFree((LPVOID)psz[0]);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800500b0  push    rbx
0x1800500b2  push    rbp
0x1800500b3  push    rsi
0x1800500b4  push    rdi
0x1800500b5  sub     rsp, 268h
0x1800500bc  mov     rax, cs:__security_cookie
0x1800500c3  xor     rax, rsp
0x1800500c6  mov     [rsp+288h+var_38], rax
0x1800500ce  xor     ebp, ebp
0x1800500d0  mov     rsi, rcx
0x1800500d3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800500d7  mov     [rsp+288h+psz], rbp
0x1800500dc  mov     eax, r8d
0x1800500df  mov     rdi, r9
0x1800500e2  and     eax, 0C000h
0x1800500e7  mov     ebx, r8d
0x1800500ea  mov     r10, [rcx]
0x1800500ed  cmp     eax, 8000h
0x1800500f2  jnz     short loc_180050104
0x1800500f4  mov     rax, [r10+58h]
0x1800500f8  lea     r8, [rsp+288h+psz]
0x1800500fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050102  jmp     short loc_180050112
0x180050104  mov     rax, [r10+48h]
0x180050108  lea     r9, [rsp+288h+psz]
0x18005010d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050112  test    eax, eax
0x180050114  js      short loc_18005017B
0x180050116  test    ebx, ebx
0x180050118  jz      short loc_18005017B
0x18005011a  test    bl, 1
0x18005011d  jnz     short loc_18005017B
0x18005011f  mov     rcx, [rsi+28h]; pidl
0x180050123  test    rcx, rcx
0x180050126  jz      short loc_18005017B
0x180050128  cmp     [rcx], bp
0x18005012b  jz      short loc_18005017B
0x18005012d  lea     r8, [rsp+288h+var_248]; unsigned __int16 *
0x180050132  mov     edx, ebx; unsigned int
0x180050134  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x180050139  mov     ebx, eax
0x18005013b  test    eax, eax
0x18005013d  js      short loc_18005018E
0x18005013f  mov     esi, 104h
0x180050144  lea     r8, asc_18005D070; "\\"
0x18005014b  mov     edx, esi; unsigned __int64
0x18005014d  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180050152  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180050157  mov     ebx, eax
0x180050159  test    eax, eax
0x18005015b  js      short loc_18005018E
0x18005015d  mov     r8, [rsp+288h+psz]; unsigned __int16 *
0x180050162  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180050167  mov     edx, esi; unsigned __int64
0x180050169  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005016e  mov     ebx, eax
0x180050170  test    eax, eax
0x180050172  js      short loc_18005018E
0x180050174  lea     rcx, [rsp+288h+var_248]
0x180050179  jmp     short loc_180050180
0x18005017b  mov     rcx, [rsp+288h+psz]; psz
0x180050180  lea     rdx, [rdi+8]; ppwsz
0x180050184  mov     [rdi], ebp
0x180050186  call    cs:__imp_SHStrDupW
0x18005018c  mov     ebx, eax
0x18005018e  mov     rcx, [rsp+288h+psz]; pv
0x180050193  call    cs:__imp_CoTaskMemFree
0x180050199  mov     eax, ebx
0x18005019b  mov     rcx, [rsp+288h+var_38]
0x1800501a3  xor     rcx, rsp; StackCookie
0x1800501a6  call    __security_check_cookie
0x1800501ab  add     rsp, 268h
0x1800501b2  pop     rdi
0x1800501b3  pop     rsi
0x1800501b4  pop     rbp
0x1800501b5  pop     rbx
0x1800501b6  retn
```

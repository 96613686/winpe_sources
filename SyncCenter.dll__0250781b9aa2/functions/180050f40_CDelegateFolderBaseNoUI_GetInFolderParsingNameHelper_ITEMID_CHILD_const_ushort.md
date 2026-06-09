# CDelegateFolderBaseNoUI::_GetInFolderParsingNameHelper(_ITEMID_CHILD const *,ushort * *)

- ea: `0x180050f40`
- end: `0x180051078`
- name: `?_GetInFolderParsingNameHelper@CDelegateFolderBaseNoUI@@MEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(CDelegateFolderBaseNoUI *this, const struct _ITEMID_CHILD *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008584`
- `0x18004f89c`
- `0x18004f98c`
- `0x180050f40`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18005103c`
- `SHLWAPI!SHStrDupW` at `0x18005103c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050fa9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051049`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::_GetInFolderParsingNameHelper(
        CDelegateFolderBaseNoUI *this,
        const struct _ITEMID_CHILD *a2,
        unsigned __int16 **a3)
{
  __int64 v4; // rax
  HRESULT v7; // ebx
  __int64 v8; // rax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  GUID rguid; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v12[68]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR psz; // [rsp+C8h] [rbp-38h]
  int v14; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[40]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v16[48]; // [rsp+130h] [rbp+30h] BYREF

  *a3 = 0;
  v4 = *(_QWORD *)this;
  rguid = 0;
  v7 = (*(__int64 (__fastcall **)(CDelegateFolderBaseNoUI *, GUID *))(v4 + 24))(this, &rguid);
  if ( v7 >= 0 )
  {
    StringFromGUID2(&rguid, sz, 39);
    v7 = StringCchPrintfW(v16, 0x2Au, L"::%s,", sz);
    if ( v7 >= 0 )
    {
      v8 = *(_QWORD *)this;
      pv = 0;
      v7 = (*(__int64 (__fastcall **)(CDelegateFolderBaseNoUI *, const struct _ITEMID_CHILD *, LPVOID *))(v8 + 80))(
             this,
             a2,
             &pv);
      if ( v7 >= 0 )
      {
        v14 = 65;
        v12[0] = 0;
        psz = v12;
        ShStrW::Append((ShStrW *)v12, v16, 0xFFFFFFFF);
        ShStrW::Append((ShStrW *)v12, (const unsigned __int16 *)pv, 0xFFFFFFFF);
        v7 = SHStrDupW(psz, a3);
        CoTaskMemFree(pv);
        ShStrW::Reset((ShStrW *)v12);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180050f40  push    rbp
0x180050f42  push    rbx
0x180050f43  push    rsi
0x180050f44  push    rdi
0x180050f45  push    r14
0x180050f47  lea     rbp, [rsp-0A0h]
0x180050f4f  sub     rsp, 1A0h
0x180050f56  mov     rax, cs:__security_cookie
0x180050f5d  xor     rax, rsp
0x180050f60  mov     [rbp+0C0h+var_30], rax
0x180050f67  mov     qword ptr [r8], 0
0x180050f6e  mov     rsi, rdx
0x180050f71  mov     rax, [rcx]
0x180050f74  lea     rdx, [rsp+1C0h+rguid]
0x180050f79  xorps   xmm0, xmm0
0x180050f7c  mov     r14, r8
0x180050f7f  mov     rdi, rcx
0x180050f82  movups  xmmword ptr [rsp+1C0h+rguid.Data1], xmm0
0x180050f87  mov     rax, [rax+18h]
0x180050f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f90  mov     ebx, eax
0x180050f92  test    eax, eax
0x180050f94  js      loc_180051059
0x180050f9a  mov     r8d, 27h ; '''; cchMax
0x180050fa0  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180050fa4  lea     rcx, [rsp+1C0h+rguid]; rguid
0x180050fa9  call    cs:__imp_StringFromGUID2
0x180050faf  lea     r9, [rbp+0C0h+sz]
0x180050fb3  mov     edx, 2Ah ; '*'; unsigned __int64
0x180050fb8  lea     r8, aS; "::%s,"
0x180050fbf  lea     rcx, [rbp+0C0h+var_90]; unsigned __int16 *
0x180050fc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180050fc8  mov     ebx, eax
0x180050fca  test    eax, eax
0x180050fcc  js      loc_180051059
0x180050fd2  mov     rax, [rdi]
0x180050fd5  lea     r8, [rsp+1C0h+pv]
0x180050fda  mov     rdx, rsi
0x180050fdd  mov     [rsp+1C0h+pv], 0
0x180050fe6  mov     rcx, rdi
0x180050fe9  mov     rax, [rax+50h]
0x180050fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ff2  mov     ebx, eax
0x180050ff4  test    eax, eax
0x180050ff6  js      short loc_180051059
0x180050ff8  xor     eax, eax
0x180050ffa  mov     [rbp+0C0h+var_F0], 41h ; 'A'
0x180051001  mov     [rsp+1C0h+var_180], ax
0x180051006  lea     rdx, [rbp+0C0h+var_90]; unsigned __int16 *
0x18005100a  lea     rax, [rsp+1C0h+var_180]
0x18005100f  or      ebx, 0FFFFFFFFh
0x180051012  mov     r8d, ebx; unsigned int
0x180051015  mov     [rbp+0C0h+psz], rax
0x180051019  lea     rcx, [rsp+1C0h+var_180]; this
0x18005101e  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x180051023  mov     rdx, [rsp+1C0h+pv]; unsigned __int16 *
0x180051028  lea     rcx, [rsp+1C0h+var_180]; this
0x18005102d  mov     r8d, ebx; unsigned int
0x180051030  call    ?Append@ShStrW@@QEAAJPEBGK@Z; ShStrW::Append(ushort const *,ulong)
0x180051035  mov     rcx, [rbp+0C0h+psz]; psz
0x180051039  mov     rdx, r14; ppwsz
0x18005103c  call    cs:__imp_SHStrDupW
0x180051042  mov     rcx, [rsp+1C0h+pv]; pv
0x180051047  mov     ebx, eax
0x180051049  call    cs:__imp_CoTaskMemFree
0x18005104f  lea     rcx, [rsp+1C0h+var_180]; this
0x180051054  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x180051059  mov     eax, ebx
0x18005105b  mov     rcx, [rbp+0C0h+var_30]
0x180051062  xor     rcx, rsp; StackCookie
0x180051065  call    __security_check_cookie
0x18005106a  add     rsp, 1A0h
0x180051071  pop     r14
0x180051073  pop     rdi
0x180051074  pop     rsi
0x180051075  pop     rbx
0x180051076  pop     rbp
0x180051077  retn
```

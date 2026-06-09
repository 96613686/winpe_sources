# CConflictFolder::_BindToConflict(CConflictFolder::tagIDCONFLICT const *,_GUID const &,void * *)

- ea: `0x180035194`
- end: `0x1800352a0`
- name: `?_BindToConflict@CConflictFolder@@AEAAJPEFBUtagIDCONFLICT@1@AEBU_GUID@@PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(CConflictFolder *this, PERCEIVED *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035134`
- `0x1800352a8`
- `0x18003625c`
- `0x1800473b4`

## callees

- `0x180032dc4`
- `0x180035194`
- `0x180036c84`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!__imp_ualstrcpynW` at `0x180035201`
- `SHLWAPI!__imp_ualstrcpynW` at `0x180035201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003527a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003527a`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_BindToConflict(
        CConflictFolder *this,
        PERCEIVED *a2,
        const struct _GUID *a3,
        void **a4)
{
  int AlignedIdAndExtra; // edi
  PWSTR *v9; // r9
  int Store; // eax
  void *v11; // rsi
  struct _BYTE_BLOB *v12; // r14
  struct ISyncMgrConflictStore *v13; // rbx
  LPVOID pv; // [rsp+30h] [rbp-89h] BYREF
  struct _BYTE_BLOB *v16[2]; // [rsp+38h] [rbp-81h] BYREF
  struct ISyncMgrConflictStore *v17; // [rsp+48h] [rbp-71h] BYREF
  WCHAR pszExt[64]; // [rsp+50h] [rbp-69h] BYREF

  pv = 0;
  v16[0] = 0;
  AlignedIdAndExtra = CConflictFolder::tagIDCONFLICT::GetAlignedIdAndExtra(
                        (CConflictFolder::tagIDCONFLICT *)a2,
                        (struct _BYTE_BLOB **)&pv,
                        v16);
  if ( AlignedIdAndExtra >= 0 )
  {
    ualstrcpynW(pszExt, a2 + 2, (PERCEIVEDFLAG *)0x40, v9);
    *a4 = 0;
    v17 = 0;
    Store = CConflictFolder::_GetStore(this, pszExt, &v17);
    v11 = pv;
    AlignedIdAndExtra = Store;
    v12 = v16[0];
    if ( Store >= 0 )
    {
      v13 = v17;
      v16[0] = (struct _BYTE_BLOB *)pv;
      v16[1] = v12;
      AlignedIdAndExtra = ((__int64 (__fastcall *)(struct ISyncMgrConflictStore *, struct _BYTE_BLOB **, const struct _GUID *, void **))v17->lpVtbl->BindToConflict)(
                            v17,
                            v16,
                            a3,
                            a4);
      ((void (__fastcall *)(struct ISyncMgrConflictStore *))v13->lpVtbl->Release)(v13);
    }
    CoTaskMemFree(v11);
    CoTaskMemFree(v12);
  }
  return (unsigned int)AlignedIdAndExtra;
}

```

## disassembly

```asm
0x180035194  push    rbp
0x180035196  push    rbx
0x180035197  push    rsi
0x180035198  push    rdi
0x180035199  push    r12
0x18003519b  push    r14
0x18003519d  push    r15
0x18003519f  lea     rbp, [rsp-27h]
0x1800351a4  sub     rsp, 0E0h
0x1800351ab  mov     rax, cs:__security_cookie
0x1800351b2  xor     rax, rsp
0x1800351b5  mov     [rbp+57h+var_40], rax
0x1800351b9  mov     rbx, rdx
0x1800351bc  mov     [rsp+110h+pv], 0
0x1800351c5  mov     r12, r8
0x1800351c8  mov     [rsp+110h+var_D8], 0
0x1800351d1  mov     rsi, rcx
0x1800351d4  lea     r8, [rsp+110h+var_D8]; struct _BYTE_BLOB **
0x1800351d9  mov     rcx, rbx; this
0x1800351dc  lea     rdx, [rsp+110h+pv]; struct _BYTE_BLOB **
0x1800351e1  mov     r15, r9
0x1800351e4  call    ?GetAlignedIdAndExtra@tagIDCONFLICT@CConflictFolder@@QEBAJPEAPEAU_BYTE_BLOB@@0@Z; CConflictFolder::tagIDCONFLICT::GetAlignedIdAndExtra(_BYTE_BLOB * *,_BYTE_BLOB * *)
0x1800351e9  mov     edi, eax
0x1800351eb  test    eax, eax
0x1800351ed  js      loc_180035280
0x1800351f3  lea     rdx, [rbx+8]; ptype
0x1800351f7  mov     r8d, 40h ; '@'; pflag
0x1800351fd  lea     rcx, [rbp+57h+pszExt]; pszExt
0x180035201  call    cs:__imp_ualstrcpynW
0x180035207  lea     r8, [rbp+57h+var_C8]; struct ISyncMgrConflictStore **
0x18003520b  mov     qword ptr [r15], 0
0x180035212  lea     rdx, [rbp+57h+pszExt]; unsigned __int16 *
0x180035216  mov     [rbp+57h+var_C8], 0
0x18003521e  mov     rcx, rsi; this
0x180035221  call    ?_GetStore@CConflictFolder@@AEAAJPEBGPEAPEAUISyncMgrConflictStore@@@Z; CConflictFolder::_GetStore(ushort const *,ISyncMgrConflictStore * *)
0x180035226  mov     rsi, [rsp+110h+pv]
0x18003522b  mov     edi, eax
0x18003522d  mov     r14, [rsp+110h+var_D8]
0x180035232  test    eax, eax
0x180035234  js      short loc_18003526E
0x180035236  mov     rbx, [rbp+57h+var_C8]
0x18003523a  lea     rdx, [rsp+110h+var_D8]
0x18003523f  mov     [rsp+110h+var_D8], rsi
0x180035244  mov     r9, r15
0x180035247  mov     [rbp+57h+var_D0], r14
0x18003524b  mov     r8, r12
0x18003524e  mov     rcx, rbx
0x180035251  mov     rax, [rbx]
0x180035254  mov     rax, [rax+20h]
0x180035258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003525d  mov     edi, eax
0x18003525f  mov     rcx, rbx
0x180035262  mov     rax, [rbx]
0x180035265  mov     rax, [rax+10h]
0x180035269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003526e  mov     rcx, rsi; pv
0x180035271  call    cs:__imp_CoTaskMemFree
0x180035277  mov     rcx, r14; pv
0x18003527a  call    cs:__imp_CoTaskMemFree
0x180035280  mov     eax, edi
0x180035282  mov     rcx, [rbp+57h+var_40]
0x180035286  xor     rcx, rsp; StackCookie
0x180035289  call    __security_check_cookie
0x18003528e  add     rsp, 0E0h
0x180035295  pop     r15
0x180035297  pop     r14
0x180035299  pop     r12
0x18003529b  pop     rdi
0x18003529c  pop     rsi
0x18003529d  pop     rbx
0x18003529e  pop     rbp
0x18003529f  retn
```

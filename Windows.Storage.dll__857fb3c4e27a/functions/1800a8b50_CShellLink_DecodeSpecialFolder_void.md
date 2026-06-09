# CShellLink::_DecodeSpecialFolder(void)

- ea: `0x1800a8b50`
- end: `0x1800a8e09`
- name: `?_DecodeSpecialFolder@CShellLink@@AEAAJXZ`
- size: `697`
- prototype: `__int64 __fastcall(CShellLink *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802406c4`
- `0x18060577c`

## callees

- `0x180041b00`
- `0x1800432f0`
- `0x18004f930`
- `0x18008b850`
- `0x180093c20`
- `0x1800a8b50`
- `0x1800a8e10`
- `0x1800a9054`
- `0x1800a90b0`
- `0x1800a9184`
- `0x180177bd0`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8bc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8dee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8bc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8dee`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800a8b88`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800a8ba2`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800a8b88`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFindDataBlock` at `0x1800a8ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellLink::_DecodeSpecialFolder(CShellLink *this)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdi
  void *v6; // rcx
  bool v8; // si
  void *v9; // rcx
  unsigned int v10; // eax
  unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rdx
  unsigned __int16 *i; // rcx
  __int64 v14; // rax
  bool v15; // zf
  void *v16; // rdi
  int v17; // esi
  struct _ITEMIDLIST_ABSOLUTE *v18; // rbp
  LPITEMIDLIST v19; // rsi
  __int64 v20; // rdx
  void *v21; // rcx
  LPVOID *p_pv; // [rsp+20h] [rbp-48h]
  struct _ITEMIDLIST_ABSOLUTE *TokenHandle; // [rsp+28h] [rbp-40h] BYREF
  char v24; // [rsp+30h] [rbp-38h]
  void *v25; // [rsp+38h] [rbp-30h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  pv = 0;
  v2 = SHFindDataBlock(*((_QWORD *)this + 57), 2684354571LL);
  v3 = v2;
  if ( v2 )
  {
    if ( !(unsigned int)CShellLink::_ShouldDecodeSpecialFolder(this, (const struct _GUID *)(v2 + 8)) )
      goto LABEL_3;
    p_pv = &pv;
    TokenHandle = 0;
    v24 = 1;
    v8 = (int)SHGetKnownFolderIDList_Internal(
                (struct _GUID *)(v3 + 8),
                (*((_DWORD *)this + 124) & 0x400000 | 0x1000000u) >> 10,
                0,
                &TokenHandle) >= 0;
    if ( v24 )
    {
      v9 = pv;
      pv = TokenHandle;
      if ( v9 )
        CoTaskMemFree(v9);
    }
    if ( !v8 )
      goto LABEL_3;
    v10 = *(_DWORD *)(v3 + 24);
  }
  else
  {
    v4 = SHFindDataBlock(*((_QWORD *)this + 57), 2684354565LL);
    v5 = v4;
    if ( !v4 || (pv = SHCloneSpecialIDList(0, *(_DWORD *)(v4 + 8), 0)) == 0 )
    {
LABEL_3:
      v6 = pv;
      pv = 0;
      if ( v6 )
        CoTaskMemFree(v6);
      return 0;
    }
    v10 = *(_DWORD *)(v5 + 12);
  }
  v11 = (unsigned __int16 *)*((_QWORD *)this + 47);
  v12 = (unsigned __int16 *)((char *)v11 + v10);
  for ( i = v11; i; i = (unsigned __int16 *)((char *)i + v14) )
  {
    v14 = *i;
    if ( !(_WORD)v14 )
      break;
    v15 = i == v12;
    if ( i >= v12 )
      goto LABEL_18;
  }
  v15 = i == v12;
LABEL_18:
  if ( !v15 )
    goto LABEL_3;
  v16 = (void *)ILCloneCB(*((void **)this + 47), (unsigned int)((_DWORD)v12 - (_DWORD)v11));
  v25 = v16;
  if ( !v16 )
  {
LABEL_26:
    if ( v16 )
      CoTaskMemFree(v16);
    goto LABEL_3;
  }
  v17 = ILValidateInnerPidlIfRooted(*((const struct _ITEMIDLIST_ABSOLUTE **)this + 47));
  if ( v17 < 0 )
  {
    v20 = 3293;
  }
  else
  {
    v17 = ILValidateInnerPidlIfRooted((const struct _ITEMIDLIST_ABSOLUTE *)v16);
    if ( v17 >= 0 )
    {
      v18 = TranslateAliasWithEvent(
              0,
              *((const struct _ITEMIDLIST_ABSOLUTE **)this + 47),
              (const struct _ITEMIDLIST_ABSOLUTE *)v16,
              (const struct _ITEMIDLIST_ABSOLUTE *)pv);
      if ( v18 )
      {
        v19 = ILClone(*((LPCITEMIDLIST *)this + 47));
        if ( (int)CShellLink::_SetPIDLPath(this, v18, 0, 2) < 0 )
        {
          *((_DWORD *)this + 154) = 0;
          Pidl_Set((char *)this + 384, 0);
        }
        else
        {
          *((_DWORD *)this + 154) = 1;
          CoTaskMemFree(*((LPVOID *)this + 48));
          *((_QWORD *)this + 48) = v19;
          v19 = 0;
        }
        CoTaskMemFree(v19);
        CoTaskMemFree(v18);
      }
      goto LABEL_26;
    }
    v20 = 3294;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\shelllnk.cpp",
    (const char *)(unsigned int)v17,
    (int)p_pv);
  CoTaskMemFree(v16);
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800a8b50  mov     [rsp+arg_8], rbx
0x1800a8b55  mov     [rsp+arg_10], rbp
0x1800a8b5a  push    rsi
0x1800a8b5b  push    rdi
0x1800a8b5c  push    r14
0x1800a8b5e  sub     rsp, 50h
0x1800a8b62  mov     rax, cs:__security_cookie
0x1800a8b69  xor     rax, rsp
0x1800a8b6c  mov     [rsp+68h+var_20], rax
0x1800a8b71  mov     rbx, rcx
0x1800a8b74  xor     r14d, r14d
0x1800a8b77  mov     [rsp+68h+pv], r14
0x1800a8b7c  mov     edx, 0A000000Bh
0x1800a8b81  mov     rcx, [rcx+1C8h]
0x1800a8b88  call    cs:__imp_SHFindDataBlock
0x1800a8b8e  mov     rdi, rax
0x1800a8b91  test    rax, rax
0x1800a8b94  jnz     short loc_1800A8BEE
0x1800a8b96  mov     edx, 0A0000005h
0x1800a8b9b  mov     rcx, [rbx+1C8h]
0x1800a8ba2  call    cs:__imp_SHFindDataBlock
0x1800a8ba8  mov     rdi, rax
0x1800a8bab  test    rax, rax
0x1800a8bae  jnz     loc_1800A8DD2
0x1800a8bb4  mov     rcx, [rsp+68h+pv]; pv
0x1800a8bb9  mov     [rsp+68h+pv], r14
0x1800a8bbe  test    rcx, rcx
0x1800a8bc1  jz      short loc_1800A8BC9
0x1800a8bc3  call    cs:__imp_CoTaskMemFree
0x1800a8bc9  xor     eax, eax
0x1800a8bcb  mov     rcx, [rsp+68h+var_20]
0x1800a8bd0  xor     rcx, rsp; StackCookie
0x1800a8bd3  call    __security_check_cookie
0x1800a8bd8  mov     rbx, [rsp+68h+arg_8]
0x1800a8bdd  mov     rbp, [rsp+68h+arg_10]
0x1800a8be5  add     rsp, 50h
0x1800a8be9  pop     r14
0x1800a8beb  pop     rdi
0x1800a8bec  pop     rsi
0x1800a8bed  retn
0x1800a8bee  lea     rdx, [rax+8]; struct _GUID *
0x1800a8bf2  mov     rcx, rbx; this
0x1800a8bf5  call    ?_ShouldDecodeSpecialFolder@CShellLink@@AEAAHAEBU_GUID@@@Z; CShellLink::_ShouldDecodeSpecialFolder(_GUID const &)
0x1800a8bfa  test    eax, eax
0x1800a8bfc  jz      short loc_1800A8BB4
0x1800a8bfe  lea     rax, [rsp+68h+pv]
0x1800a8c03  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800a8c08  mov     [rsp+68h+TokenHandle], r14
0x1800a8c0d  mov     [rsp+68h+var_38], 1
0x1800a8c12  mov     edx, [rbx+1F0h]
0x1800a8c18  and     edx, 400000h
0x1800a8c1e  bts     edx, 18h
0x1800a8c22  shr     edx, 0Ah; unsigned int
0x1800a8c25  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800a8c2a  xor     r8d, r8d; void *
0x1800a8c2d  lea     rcx, [rdi+8]; struct _GUID *
0x1800a8c31  call    SHGetKnownFolderIDList_Internal
0x1800a8c36  mov     esi, eax
0x1800a8c38  shr     esi, 1Fh
0x1800a8c3b  xor     sil, 1
0x1800a8c3f  cmp     [rsp+68h+var_38], 0
0x1800a8c44  jz      short loc_1800A8C61
0x1800a8c46  mov     r8, qword ptr [rsp+68h+var_48]
0x1800a8c4b  mov     rcx, [r8]; pv
0x1800a8c4e  mov     rdx, [rsp+68h+TokenHandle]
0x1800a8c53  mov     [r8], rdx
0x1800a8c56  test    rcx, rcx
0x1800a8c59  jz      short loc_1800A8C61
0x1800a8c5b  call    cs:__imp_CoTaskMemFree
0x1800a8c61  test    sil, sil
0x1800a8c64  jz      loc_1800A8BB4
0x1800a8c6a  mov     eax, [rdi+18h]
0x1800a8c6d  mov     r8, [rbx+178h]
0x1800a8c74  mov     edx, eax
0x1800a8c76  add     rdx, r8
0x1800a8c79  mov     rcx, r8
0x1800a8c7c  nop     dword ptr [rax+00h]
0x1800a8c80  test    rcx, rcx
0x1800a8c83  jz      short loc_1800A8C97
0x1800a8c85  movzx   eax, word ptr [rcx]
0x1800a8c88  test    ax, ax
0x1800a8c8b  jz      short loc_1800A8C97
0x1800a8c8d  cmp     rcx, rdx
0x1800a8c90  jnb     short loc_1800A8C9A
0x1800a8c92  add     rcx, rax
0x1800a8c95  jmp     short loc_1800A8C80
0x1800a8c97  cmp     rcx, rdx
0x1800a8c9a  jnz     loc_1800A8BB4
0x1800a8ca0  sub     edx, r8d; Size
0x1800a8ca3  mov     rcx, r8; Src
0x1800a8ca6  call    ILCloneCB
0x1800a8cab  mov     rdi, rax
0x1800a8cae  mov     [rsp+68h+var_30], rax
0x1800a8cb3  test    rax, rax
0x1800a8cb6  jz      loc_1800A8D5D
0x1800a8cbc  mov     rcx, [rbx+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800a8cc3  call    ?ILValidateInnerPidlIfRooted@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; ILValidateInnerPidlIfRooted(_ITEMIDLIST_ABSOLUTE const *)
0x1800a8cc8  mov     esi, eax
0x1800a8cca  test    eax, eax
0x1800a8ccc  js      loc_1800A8D8B
0x1800a8cd2  mov     rcx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x1800a8cd5  call    ?ILValidateInnerPidlIfRooted@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; ILValidateInnerPidlIfRooted(_ITEMIDLIST_ABSOLUTE const *)
0x1800a8cda  mov     esi, eax
0x1800a8cdc  test    eax, eax
0x1800a8cde  js      loc_1800A8DCB
0x1800a8ce4  mov     r9, [rsp+68h+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x1800a8ce9  mov     r8, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x1800a8cec  mov     rdx, [rbx+178h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800a8cf3  xor     ecx, ecx; int
0x1800a8cf5  call    ?TranslateAliasWithEvent@@YAPEAU_ITEMIDLIST_ABSOLUTE@@JPEBU1@00@Z; TranslateAliasWithEvent(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x1800a8cfa  mov     rbp, rax
0x1800a8cfd  test    rax, rax
0x1800a8d00  jz      short loc_1800A8D5D
0x1800a8d02  mov     rcx, [rbx+178h]; pidl
0x1800a8d09  call    ILClone
0x1800a8d0e  mov     rsi, rax
0x1800a8d11  mov     r9d, 2
0x1800a8d17  xor     r8d, r8d
0x1800a8d1a  mov     rdx, rbp
0x1800a8d1d  mov     rcx, rbx
0x1800a8d20  call    ?_SetPIDLPath@CShellLink@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGW4SLSPPFLAGS@@@Z; CShellLink::_SetPIDLPath(_ITEMIDLIST_ABSOLUTE const *,ushort const *,SLSPPFLAGS)
0x1800a8d25  test    eax, eax
0x1800a8d27  js      short loc_1800A8D74
0x1800a8d29  mov     dword ptr [rbx+268h], 1
0x1800a8d33  mov     rcx, [rbx+180h]; pv
0x1800a8d3a  call    cs:__imp_CoTaskMemFree
0x1800a8d40  mov     [rbx+180h], rsi
0x1800a8d47  mov     rsi, r14
0x1800a8d4a  mov     rcx, rsi; pv
0x1800a8d4d  call    cs:__imp_CoTaskMemFree
0x1800a8d53  mov     rcx, rbp; pv
0x1800a8d56  call    cs:__imp_CoTaskMemFree
0x1800a8d5c  nop
0x1800a8d5d  test    rdi, rdi
0x1800a8d60  jz      loc_1800A8BB4
0x1800a8d66  mov     rcx, rdi; pv
0x1800a8d69  call    cs:__imp_CoTaskMemFree
0x1800a8d6f  jmp     loc_1800A8BB4
0x1800a8d74  mov     [rbx+268h], r14d
0x1800a8d7b  lea     rcx, [rbx+180h]
0x1800a8d82  xor     edx, edx
0x1800a8d84  call    Pidl_Set
0x1800a8d89  jmp     short loc_1800A8D4A
0x1800a8d8b  mov     edx, 0CDDh; void *
0x1800a8d90  lea     r8, aOnecoreuapShel_86; "onecoreuap\\shell\\windows.storage\\she"...
0x1800a8d97  mov     r9d, esi; char *
0x1800a8d9a  mov     rcx, [rsp+68h]; this
0x1800a8d9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8da4  nop
0x1800a8da5  mov     rcx, rdi; pv
0x1800a8da8  call    cs:__imp_CoTaskMemFree
0x1800a8dae  nop
0x1800a8daf  mov     rcx, [rsp+68h+pv]; pv
0x1800a8db4  mov     [rsp+68h+pv], r14
0x1800a8db9  test    rcx, rcx
0x1800a8dbc  jz      short loc_1800A8DC4
0x1800a8dbe  call    cs:__imp_CoTaskMemFree
0x1800a8dc4  mov     eax, esi
0x1800a8dc6  jmp     loc_1800A8BCB
0x1800a8dcb  mov     edx, 0CDEh
0x1800a8dd0  jmp     short loc_1800A8D90
0x1800a8dd2  xor     r8d, r8d; fCreate
0x1800a8dd5  mov     edx, [rax+8]; csidl
0x1800a8dd8  xor     ecx, ecx; hwnd
0x1800a8dda  call    SHCloneSpecialIDList
0x1800a8ddf  mov     rcx, [rsp+68h+pv]; pv
0x1800a8de4  mov     [rsp+68h+pv], rax
0x1800a8de9  test    rcx, rcx
0x1800a8dec  jz      short loc_1800A8DF4
0x1800a8dee  call    cs:__imp_CoTaskMemFree
0x1800a8df4  cmp     [rsp+68h+pv], 0
0x1800a8dfa  jz      loc_1800A8BB4
0x1800a8e00  mov     eax, [rdi+0Ch]
0x1800a8e03  jmp     loc_1800A8C6D
```

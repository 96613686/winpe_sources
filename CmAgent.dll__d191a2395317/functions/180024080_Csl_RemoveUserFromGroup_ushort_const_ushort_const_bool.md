# Csl::RemoveUserFromGroup(ushort const *,ushort const *,bool *)

- ea: `0x180024080`
- end: `0x180024212`
- name: `?RemoveUserFromGroup@Csl@@YAJPEBG0PEA_N@Z`
- size: `402`
- prototype: `__int64 __fastcall(Csl *this, const unsigned __int16 *, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023090`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x1800239d0`
- `0x180023d78`
- `0x180024080`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241e5`
- `samcli!NetLocalGroupDelMember` at `0x180024151`
- `samcli!NetLocalGroupDelMember` at `0x180024151`

## string_xrefs

- `0x1800240b5`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x180024115`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002417e`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::RemoveUserFromGroup(Csl *this, const unsigned __int16 *a2, unsigned __int16 *a3, bool *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  HLOCAL v9; // rbx
  DWORD v10; // eax
  char v11; // al
  __int64 v12; // rdx
  unsigned int v13; // edi
  LPCWSTR groupname[2]; // [rsp+20h] [rbp-20h] BYREF
  _WORD v15[8]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HLOCAL hMem; // [rsp+58h] [rbp+18h] BYREF

  hMem = 0;
  v5 = Csl::_anonymous_namespace_::ConvertAccountNameToSid(this, &hMem, a3, a4);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v5,
      (int)groupname[0]);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return v6;
  }
  groupname[0] = v15;
  groupname[1] = v15;
  v15[0] = 0;
  v8 = Csl::_anonymous_namespace_::ConvertStringSidToAccountName(L"S-1-5-32-544", groupname);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v8,
      (int)groupname[0]);
    if ( groupname[0] != v15 )
      operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_3;
  }
  v9 = hMem;
  v10 = NetLocalGroupDelMember(0, groupname[0], hMem);
  if ( a3 )
  {
    if ( v10 == 1377 )
    {
      v11 = 1;
LABEL_20:
      *(_BYTE *)a3 = v11;
LABEL_21:
      if ( groupname[0] != v15 )
        operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 )
        LocalFree(v9);
      return 0;
    }
    if ( !v10 )
    {
      v11 = 0;
      goto LABEL_20;
    }
    v12 = 1250;
  }
  else
  {
    if ( !v10 )
      goto LABEL_21;
    v12 = 1257;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
          (const char *)v10,
          (unsigned int)groupname[0]);
  if ( groupname[0] != v15 )
    operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
    LocalFree(v9);
  return v13;
}

```

## disassembly

```asm
0x180024080  mov     [rsp-8+arg_0], rbx
0x180024085  mov     [rsp-8+arg_10], rdi
0x18002408a  mov     [rsp-8+hMem], rdx
0x18002408f  push    rbp
0x180024090  mov     rbp, rsp
0x180024093  sub     rsp, 40h
0x180024097  lea     rdx, [rbp+hMem]
0x18002409b  mov     [rbp+hMem], 0
0x1800240a3  mov     rdi, r8
0x1800240a6  call    Csl___anonymous_namespace___ConvertAccountNameToSid
0x1800240ab  mov     ebx, eax
0x1800240ad  test    eax, eax
0x1800240af  jns     short loc_1800240E5
0x1800240b1  mov     rcx, [rbp+8]; this
0x1800240b5  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800240bc  mov     r9d, eax; char *
0x1800240bf  mov     edx, 4CFh; void *
0x1800240c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800240c9  mov     rcx, [rbp+hMem]; hMem
0x1800240cd  test    rcx, rcx
0x1800240d0  jz      short loc_1800240DE
0x1800240d2  call    cs:__imp_LocalFree
0x1800240d9  nop     dword ptr [rax+rax+00h]
0x1800240de  mov     eax, ebx
0x1800240e0  jmp     loc_1800241F3
0x1800240e5  lea     rax, [rbp+var_10]
0x1800240e9  mov     [rbp+groupname], rax
0x1800240ed  lea     rdx, [rbp+groupname]
0x1800240f1  lea     rax, [rbp+var_10]
0x1800240f5  mov     [rbp+var_18], rax
0x1800240f9  lea     rcx, aS1532544; "S-1-5-32-544"
0x180024100  xor     eax, eax
0x180024102  mov     [rbp+var_10], ax
0x180024106  call    Csl___anonymous_namespace___ConvertStringSidToAccountName
0x18002410b  mov     ebx, eax
0x18002410d  test    eax, eax
0x18002410f  jns     short loc_180024144
0x180024111  mov     rcx, [rbp+8]; this
0x180024115  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002411c  mov     r9d, eax; char *
0x18002411f  mov     edx, 4D3h; void *
0x180024124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024129  mov     rcx, [rbp+groupname]; void *
0x18002412d  lea     rax, [rbp+var_10]
0x180024131  cmp     rcx, rax
0x180024134  jz      short loc_1800240C9
0x180024136  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002413d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024142  jmp     short loc_1800240C9
0x180024144  mov     rbx, [rbp+hMem]
0x180024148  xor     ecx, ecx; servername
0x18002414a  mov     rdx, [rbp+groupname]; groupname
0x18002414e  mov     r8, rbx; membersid
0x180024151  call    cs:__imp_NetLocalGroupDelMember
0x180024158  nop     dword ptr [rax+rax+00h]
0x18002415d  test    rdi, rdi
0x180024160  jz      loc_180024204
0x180024166  cmp     eax, 561h
0x18002416b  jnz     short loc_180024171
0x18002416d  mov     al, 1
0x18002416f  jmp     short loc_1800241C2
0x180024171  test    eax, eax
0x180024173  jz      short loc_1800241C0
0x180024175  mov     edx, 4E2h; void *
0x18002417a  mov     rcx, [rbp+8]; this
0x18002417e  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024185  mov     r9d, eax; char *
0x180024188  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002418d  mov     rcx, [rbp+groupname]; void *
0x180024191  mov     edi, eax
0x180024193  lea     rax, [rbp+var_10]
0x180024197  cmp     rcx, rax
0x18002419a  jz      short loc_1800241A8
0x18002419c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800241a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800241a8  test    rbx, rbx
0x1800241ab  jz      short loc_1800241BC
0x1800241ad  mov     rcx, rbx; hMem
0x1800241b0  call    cs:__imp_LocalFree
0x1800241b7  nop     dword ptr [rax+rax+00h]
0x1800241bc  mov     eax, edi
0x1800241be  jmp     short loc_1800241F3
0x1800241c0  xor     al, al
0x1800241c2  mov     [rdi], al
0x1800241c4  mov     rcx, [rbp+groupname]; void *
0x1800241c8  lea     rax, [rbp+var_10]
0x1800241cc  cmp     rcx, rax
0x1800241cf  jz      short loc_1800241DD
0x1800241d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800241d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800241dd  test    rbx, rbx
0x1800241e0  jz      short loc_1800241F1
0x1800241e2  mov     rcx, rbx; hMem
0x1800241e5  call    cs:__imp_LocalFree
0x1800241ec  nop     dword ptr [rax+rax+00h]
0x1800241f1  xor     eax, eax
0x1800241f3  mov     rbx, [rsp+40h+arg_0]
0x1800241f8  mov     rdi, [rsp+40h+arg_10]
0x1800241fd  add     rsp, 40h
0x180024201  pop     rbp
0x180024202  retn
0x180024204  test    eax, eax
0x180024206  jz      short loc_1800241C4
0x180024208  mov     edx, 4E9h
0x18002420d  jmp     loc_18002417A
```

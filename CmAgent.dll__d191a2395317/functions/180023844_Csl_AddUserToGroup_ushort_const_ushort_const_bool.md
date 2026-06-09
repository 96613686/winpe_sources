# Csl::AddUserToGroup(ushort const *,ushort const *,bool *)

- ea: `0x180023844`
- end: `0x1800239c7`
- name: `?AddUserToGroup@Csl@@YAJPEBG0PEA_N@Z`
- size: `387`
- prototype: `__int64 __fastcall(Csl *this, const unsigned __int16 *, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022894`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b4c`
- `0x180023844`
- `0x1800239d0`
- `0x180023d78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002396c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002396c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239a1`
- `samcli!NetLocalGroupAddMember` at `0x18002390d`
- `samcli!NetLocalGroupAddMember` at `0x18002390d`

## string_xrefs

- `0x180023875`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x1800238d1`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002393a`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::AddUserToGroup(Csl *this, const unsigned __int16 *a2, unsigned __int16 *a3, bool *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  HLOCAL v10; // rbx
  DWORD v11; // eax
  char v12; // al
  __int64 v13; // rdx
  unsigned int v14; // edi
  LPCWSTR groupname[2]; // [rsp+20h] [rbp-28h] BYREF
  _WORD v16[12]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HLOCAL hMem; // [rsp+70h] [rbp+28h] BYREF

  hMem = 0;
  v6 = Csl::_anonymous_namespace_::ConvertAccountNameToSid(this, &hMem, a3, a4);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x490,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v6,
      (int)groupname[0]);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  groupname[0] = v16;
  groupname[1] = v16;
  v16[0] = 0;
  v9 = Csl::_anonymous_namespace_::ConvertStringSidToAccountName(a2, groupname);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)(unsigned int)v9,
      (int)groupname[0]);
    if ( groupname[0] != v16 )
      operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_3;
  }
  v10 = hMem;
  v11 = NetLocalGroupAddMember(0, groupname[0], hMem);
  if ( a3 )
  {
    if ( v11 == 1378 )
    {
      v12 = 1;
LABEL_20:
      *(_BYTE *)a3 = v12;
LABEL_21:
      if ( groupname[0] != v16 )
        operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 )
        LocalFree(v10);
      return 0;
    }
    if ( !v11 )
    {
      v12 = 0;
      goto LABEL_20;
    }
    v13 = 1187;
  }
  else
  {
    if ( !v11 )
      goto LABEL_21;
    v13 = 1194;
  }
  v14 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
          (const char *)v11,
          (unsigned int)groupname[0]);
  if ( groupname[0] != v16 )
    operator delete((void *)groupname[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
    LocalFree(v10);
  return v14;
}

```

## disassembly

```asm
0x180023844  mov     [rsp-20h+hMem], rcx
0x180023849  push    rbp
0x18002384a  push    rbx
0x18002384b  push    rsi
0x18002384c  push    rdi
0x18002384d  mov     rbp, rsp
0x180023850  sub     rsp, 48h
0x180023854  mov     rsi, rdx
0x180023857  mov     [rbp+hMem], 0
0x18002385f  lea     rdx, [rbp+hMem]
0x180023863  mov     rdi, r8
0x180023866  call    Csl___anonymous_namespace___ConvertAccountNameToSid
0x18002386b  mov     ebx, eax
0x18002386d  test    eax, eax
0x18002386f  jns     short loc_1800238A5
0x180023871  mov     rcx, [rbp+20h]; this
0x180023875  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002387c  mov     r9d, eax; char *
0x18002387f  mov     edx, 490h; void *
0x180023884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023889  mov     rcx, [rbp+hMem]; hMem
0x18002388d  test    rcx, rcx
0x180023890  jz      short loc_18002389E
0x180023892  call    cs:__imp_LocalFree
0x180023899  nop     dword ptr [rax+rax+00h]
0x18002389e  mov     eax, ebx
0x1800238a0  jmp     loc_1800239AF
0x1800238a5  lea     rax, [rbp+var_18]
0x1800238a9  mov     rcx, rsi
0x1800238ac  mov     [rbp+groupname], rax
0x1800238b0  lea     rdx, [rbp+groupname]
0x1800238b4  lea     rax, [rbp+var_18]
0x1800238b8  mov     [rbp+var_20], rax
0x1800238bc  xor     eax, eax
0x1800238be  mov     [rbp+var_18], ax
0x1800238c2  call    Csl___anonymous_namespace___ConvertStringSidToAccountName
0x1800238c7  mov     ebx, eax
0x1800238c9  test    eax, eax
0x1800238cb  jns     short loc_180023900
0x1800238cd  mov     rcx, [rbp+20h]; this
0x1800238d1  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800238d8  mov     r9d, eax; char *
0x1800238db  mov     edx, 494h; void *
0x1800238e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238e5  mov     rcx, [rbp+groupname]; void *
0x1800238e9  lea     rax, [rbp+var_18]
0x1800238ed  cmp     rcx, rax
0x1800238f0  jz      short loc_180023889
0x1800238f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800238f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800238fe  jmp     short loc_180023889
0x180023900  mov     rbx, [rbp+hMem]
0x180023904  xor     ecx, ecx; servername
0x180023906  mov     rdx, [rbp+groupname]; groupname
0x18002390a  mov     r8, rbx; membersid
0x18002390d  call    cs:__imp_NetLocalGroupAddMember
0x180023914  nop     dword ptr [rax+rax+00h]
0x180023919  test    rdi, rdi
0x18002391c  jz      loc_1800239B9
0x180023922  cmp     eax, 562h
0x180023927  jnz     short loc_18002392D
0x180023929  mov     al, 1
0x18002392b  jmp     short loc_18002397E
0x18002392d  test    eax, eax
0x18002392f  jz      short loc_18002397C
0x180023931  mov     edx, 4A3h; void *
0x180023936  mov     rcx, [rbp+20h]; this
0x18002393a  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180023941  mov     r9d, eax; char *
0x180023944  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023949  mov     rcx, [rbp+groupname]; void *
0x18002394d  mov     edi, eax
0x18002394f  lea     rax, [rbp+var_18]
0x180023953  cmp     rcx, rax
0x180023956  jz      short loc_180023964
0x180023958  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002395f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023964  test    rbx, rbx
0x180023967  jz      short loc_180023978
0x180023969  mov     rcx, rbx; hMem
0x18002396c  call    cs:__imp_LocalFree
0x180023973  nop     dword ptr [rax+rax+00h]
0x180023978  mov     eax, edi
0x18002397a  jmp     short loc_1800239AF
0x18002397c  xor     al, al
0x18002397e  mov     [rdi], al
0x180023980  mov     rcx, [rbp+groupname]; void *
0x180023984  lea     rax, [rbp+var_18]
0x180023988  cmp     rcx, rax
0x18002398b  jz      short loc_180023999
0x18002398d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023994  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023999  test    rbx, rbx
0x18002399c  jz      short loc_1800239AD
0x18002399e  mov     rcx, rbx; hMem
0x1800239a1  call    cs:__imp_LocalFree
0x1800239a8  nop     dword ptr [rax+rax+00h]
0x1800239ad  xor     eax, eax
0x1800239af  add     rsp, 48h
0x1800239b3  pop     rdi
0x1800239b4  pop     rsi
0x1800239b5  pop     rbx
0x1800239b6  pop     rbp
0x1800239b7  retn
0x1800239b9  test    eax, eax
0x1800239bb  jz      short loc_180023980
0x1800239bd  mov     edx, 4AAh
0x1800239c2  jmp     loc_180023936
```

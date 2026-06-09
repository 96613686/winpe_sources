# _lambda_f30904bed2730fd1a7e2b38ae32a3e68_::operator()(ushort const *)

- ea: `0x1801a5e18`
- end: `0x1801a5eef`
- name: `??R_lambda_f30904bed2730fd1a7e2b38ae32a3e68_@@QEBA@PEBG@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f6964`

## callees

- `0x180015d8c`
- `0x1801a5e18`
- `0x1801a6bd4`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1801a5ec3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1801a5ec3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a5e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a5ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a5e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801a5ea9`

## string_xrefs

- `0x1801a5ed2`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinvalidatorsso.cpp`

## pseudocode

```c
void __fastcall _lambda_f30904bed2730fd1a7e2b38ae32a3e68_::operator()(__int64 a1, const WCHAR *a2)
{
  unsigned __int64 i; // rbx
  _QWORD **v5; // rdi
  _QWORD *j; // rbx
  _QWORD *CloudStoreAccount; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  for ( i = 0; i < **(_QWORD **)a1; ++i )
  {
    if ( CompareStringOrdinal(*(LPCWCH *)(**(_QWORD **)(a1 + 8) + 8 * i), -1, a2, -1, 1) == 2 )
      return;
  }
  v5 = *(_QWORD ***)(*(_QWORD *)(a1 + 16) + 8LL);
  for ( j = *v5; j != v5; j = (_QWORD *)*j )
  {
    CloudStoreAccount = (_QWORD *)EffectiveWebAccountContext::GetCloudStoreAccount(j + 8);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*CloudStoreAccount + 16LL))(*CloudStoreAccount);
    if ( *(_QWORD *)(v8 + 24) > 7u )
      v8 = *(_QWORD *)v8;
    if ( CompareStringOrdinal((LPCWCH)v8, -1, a2, -1, 1) == 2 )
      return;
  }
  v9 = RegDeleteTreeW(**(HKEY **)(a1 + 24), a2);
  if ( v9 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinvalidatorsso.cpp",
      (const char *)v9,
      bIgnoreCase);
}

```

## disassembly

```asm
0x1801a5e18  push    rbx
0x1801a5e1a  push    rbp
0x1801a5e1b  push    rsi
0x1801a5e1c  push    rdi
0x1801a5e1d  sub     rsp, 38h
0x1801a5e21  mov     rbp, rdx
0x1801a5e24  mov     rsi, rcx
0x1801a5e27  xor     ebx, ebx
0x1801a5e29  mov     rax, [rsi]
0x1801a5e2c  cmp     rbx, [rax]
0x1801a5e2f  jnb     short loc_1801A5E62
0x1801a5e31  mov     rax, [rsi+8]
0x1801a5e35  or      r9d, 0FFFFFFFFh; cchCount2
0x1801a5e39  mov     r8, rbp; lpString2
0x1801a5e3c  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1801a5e44  or      edx, r9d; cchCount1
0x1801a5e47  mov     rcx, [rax]
0x1801a5e4a  mov     rcx, [rcx+rbx*8]; lpString1
0x1801a5e4e  call    cs:__imp_CompareStringOrdinal
0x1801a5e54  cmp     eax, 2
0x1801a5e57  jz      loc_1801A5EE6
0x1801a5e5d  inc     rbx
0x1801a5e60  jmp     short loc_1801A5E29
0x1801a5e62  mov     rdi, [rsi+10h]
0x1801a5e66  mov     rdi, [rdi+8]
0x1801a5e6a  mov     rbx, [rdi]
0x1801a5e6d  cmp     rbx, rdi
0x1801a5e70  jz      short loc_1801A5EB9
0x1801a5e72  lea     rcx, [rbx+40h]
0x1801a5e76  call    ?GetCloudStoreAccount@EffectiveWebAccountContext@@QEBAAEBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@std@@XZ; EffectiveWebAccountContext::GetCloudStoreAccount(void)
0x1801a5e7b  mov     rcx, [rax]
0x1801a5e7e  mov     rax, [rcx]
0x1801a5e81  mov     rax, [rax+10h]
0x1801a5e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5e8a  cmp     qword ptr [rax+18h], 7
0x1801a5e8f  jbe     short loc_1801A5E94
0x1801a5e91  mov     rax, [rax]
0x1801a5e94  or      r9d, 0FFFFFFFFh; cchCount2
0x1801a5e98  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1801a5ea0  or      edx, r9d; cchCount1
0x1801a5ea3  mov     r8, rbp; lpString2
0x1801a5ea6  mov     rcx, rax; lpString1
0x1801a5ea9  call    cs:__imp_CompareStringOrdinal
0x1801a5eaf  cmp     eax, 2
0x1801a5eb2  jz      short loc_1801A5EE6
0x1801a5eb4  mov     rbx, [rbx]
0x1801a5eb7  jmp     short loc_1801A5E6D
0x1801a5eb9  mov     rcx, [rsi+18h]
0x1801a5ebd  mov     rdx, rbp; lpSubKey
0x1801a5ec0  mov     rcx, [rcx]; hKey
0x1801a5ec3  call    cs:__imp_RegDeleteTreeW
0x1801a5ec9  test    eax, eax
0x1801a5ecb  jz      short loc_1801A5EE6
0x1801a5ecd  mov     rcx, [rsp+58h]; this
0x1801a5ed2  lea     r8, aOnecoreuapShel_69; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a5ed9  mov     r9d, eax; char *
0x1801a5edc  mov     edx, 1ADh; void *
0x1801a5ee1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1801a5ee6  add     rsp, 38h
0x1801a5eea  pop     rdi
0x1801a5eeb  pop     rsi
0x1801a5eec  pop     rbp
0x1801a5eed  pop     rbx
0x1801a5eee  retn
```

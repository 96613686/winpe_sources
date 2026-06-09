# Windows::AutoSsShim::TryLoadFromWindowsPath(wchar_t const * const,wchar_t const * const)

- ea: `0x1400263f8`
- end: `0x1400264d8`
- name: `?TryLoadFromWindowsPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z`
- size: `224`
- prototype: `__int64 __fastcall(Windows::AutoSsShim *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140025824`

## callees

- `0x140024ac0`
- `0x140024b14`
- `0x140025934`
- `0x140025fb0`
- `0x1400263f8`
- `0x140026784`
- `0x140026e18`

## string_xrefs

- `0x140026456`: `system32\ssshim.dll`

## pseudocode

```c
__int64 __fastcall Windows::AutoSsShim::TryLoadFromWindowsPath(
        Windows::AutoSsShim *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  NTSTATUS v8; // eax
  int v9; // ebx
  const WCHAR *v10; // rax
  __int128 v12; // [rsp+20h] [rbp-50h] BYREF
  __int64 v13; // [rsp+30h] [rbp-40h]
  _QWORD v14[7]; // [rsp+38h] [rbp-38h] BYREF

  if ( !a2 || !*a2 )
    a2 = L"\\\\?\\GLOBALROOT\\SystemRoot";
  v5 = 0;
  v13 = 0;
  v12 = 0;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v5 = 2 * v6;
    v7 = v5 + 2;
  }
  else
  {
    a2 = 0;
    v7 = 0;
  }
  v14[0] = v5;
  v14[2] = a2;
  v14[5] = L"system32\\ssshim.dll";
  v14[1] = v7;
  v14[3] = 38;
  v14[4] = 40;
  v8 = RtlCombineNtPathSegments(v7, (__int64)v14, &v12);
  if ( v8 >= 0
    && (v8 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(&v12), v8 >= 0) )
  {
    v10 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v12);
    v9 = Windows::AutoSsShim::TryLoadFromDirectPath(this, v10, a3);
    if ( v9 >= 0 )
      v9 = 0;
  }
  else
  {
    v9 = ConvertNtStatusToHResult(v8);
  }
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400263f8  mov     [rsp-18h+arg_8], rbx
0x1400263fd  push    rbp
0x1400263fe  push    rsi
0x1400263ff  push    rdi
0x140026400  mov     rbp, rsp
0x140026403  sub     rsp, 70h
0x140026407  xor     esi, esi
0x140026409  mov     rdi, r8
0x14002640c  mov     rbx, rcx
0x14002640f  test    rdx, rdx
0x140026412  jz      short loc_140026419
0x140026414  cmp     [rdx], si
0x140026417  jnz     short loc_140026420
0x140026419  lea     rdx, aGlobalrootSyst; "\\\\?\\GLOBALROOT\\SystemRoot"
0x140026420  xor     eax, eax
0x140026422  xorps   xmm0, xmm0
0x140026425  mov     [rbp+var_40], rax
0x140026429  movups  [rbp+var_50], xmm0
0x14002642d  test    rdx, rdx
0x140026430  jz      short loc_140026448
0x140026432  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026436  inc     rax
0x140026439  cmp     [rdx+rax*2], si
0x14002643d  jnz     short loc_140026436
0x14002643f  add     rax, rax
0x140026442  lea     rcx, [rax+2]
0x140026446  jmp     short loc_14002644E
0x140026448  mov     rdx, rsi
0x14002644b  mov     rcx, rsi
0x14002644e  mov     [rbp+var_38], rax
0x140026452  lea     r8, [rbp+var_50]
0x140026456  lea     rax, aSystem32Ssshim; "system32\\ssshim.dll"
0x14002645d  mov     [rbp+var_28], rdx
0x140026461  lea     rdx, [rbp+var_38]
0x140026465  mov     [rbp+var_10], rax
0x140026469  mov     [rbp+var_30], rcx
0x14002646d  mov     [rbp+var_20], 26h ; '&'
0x140026475  mov     [rbp+var_18], 28h ; '('
0x14002647d  call    RtlCombineNtPathSegments
0x140026482  test    eax, eax
0x140026484  js      short loc_140026493
0x140026486  lea     rcx, [rbp+var_50]
0x14002648a  call    ??$EnsureNullTerminated@PEAV?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::Auto<_LUNICODE_STRING> *>(Windows::Auto<_LUNICODE_STRING> *)
0x14002648f  test    eax, eax
0x140026491  jns     short loc_14002649E
0x140026493  mov     ecx, eax; Status
0x140026495  call    ConvertNtStatusToHResult
0x14002649a  mov     ebx, eax
0x14002649c  jmp     short loc_1400264BD
0x14002649e  lea     rcx, [rbp+var_50]
0x1400264a2  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x1400264a7  mov     rdx, rax; wchar_t *
0x1400264aa  mov     r8, rdi; wchar_t *
0x1400264ad  mov     rcx, rbx; this
0x1400264b0  call    ?TryLoadFromDirectPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z; Windows::AutoSsShim::TryLoadFromDirectPath(wchar_t const * const,wchar_t const * const)
0x1400264b5  mov     ebx, eax
0x1400264b7  test    eax, eax
0x1400264b9  js      short loc_1400264BD
0x1400264bb  mov     ebx, esi
0x1400264bd  lea     rcx, [rbp+var_50]
0x1400264c1  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1400264c6  mov     eax, ebx
0x1400264c8  mov     rbx, [rsp+70h+arg_8]
0x1400264d0  add     rsp, 70h
0x1400264d4  pop     rdi
0x1400264d5  pop     rsi
0x1400264d6  pop     rbp
0x1400264d7  retn
```

# SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18000a0e4`
- end: `0x18000a306`
- name: `?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `546`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009710`

## callees

- `0x180009f04`
- `0x18000a0e4`
- `0x18001623a`
- `0x180016246`
- `0x180016280`
- `0x180016310`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x18000a23d`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000a23d`
- `SHLWAPI!PathIsRootW` at `0x18000a289`
- `SHLWAPI!PathIsRootW` at `0x18000a289`
- `SHLWAPI!StrStrIW` at `0x18000a20e`
- `SHLWAPI!StrStrIW` at `0x18000a229`
- `SHLWAPI!StrStrIW` at `0x18000a253`
- `SHLWAPI!StrStrIW` at `0x18000a26a`
- `SHLWAPI!StrStrIW` at `0x18000a20e`
- `SHLWAPI!StrStrIW` at `0x18000a229`
- `SHLWAPI!StrStrIW` at `0x18000a253`
- `SHLWAPI!StrStrIW` at `0x18000a26a`
- `SHLWAPI!PathStripToRootW` at `0x18000a27a`
- `SHLWAPI!PathStripToRootW` at `0x18000a27a`
- `SHLWAPI!PathIsURLW` at `0x18000a14a`
- `SHLWAPI!PathIsURLW` at `0x18000a14a`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000a166`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18000a166`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZoneEx(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  const WCHAR *v5; // rdi
  struct IUnknown *v6; // rdx
  __int64 v7; // rsi
  __int64 result; // rax
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  WCHAR v12; // cx
  WCHAR *v13; // rax
  unsigned int v14; // eax
  WCHAR pszFirst[2088]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[4176]; // [rsp+1070h] [rbp+F70h] BYREF

  v5 = a1;
  if ( !a1 )
  {
    if ( a4 )
      *a4 = -1;
    return 2147942487LL;
  }
  if ( !a4 )
    return 2147942487LL;
  memset_0(v16, 0, 0x1048u);
  v7 = 2084;
  if ( !PathIsURLW(v5) && (unsigned int)SHExpandEnvironmentStringsW(v5, v16, 2084) )
    v5 = (const WCHAR *)v16;
  result = SHMapUrlToZone(v5, v6, 1u, a4);
  if ( (int)result < 0 )
  {
    memset_0(pszFirst, 0, 0x1048u);
    v9 = 2147483646;
    v10 = pszFirst;
    do
    {
      if ( !v9 )
        break;
      if ( !*v5 )
        break;
      *v10++ = *v5++;
      --v9;
      --v7;
    }
    while ( v7 );
    v11 = v10 - 1;
    if ( v7 )
      v11 = v10;
    *v11 = 0;
    v12 = pszFirst[0];
    if ( pszFirst[0] )
    {
      v13 = pszFirst;
      do
      {
        if ( v12 == 47 )
          *v13 = 92;
        v12 = *++v13;
      }
      while ( *v13 );
    }
    if ( StrStrIW(pszFirst, L"\\??")
      || StrStrIW(pszFirst, L"\\\\?\\GLOBAL")
      || PathIsNetworkPathW(pszFirst)
      || (StrStrIW(pszFirst, L"\\\\") || StrStrIW(pszFirst, L"//"))
      && (!PathStripToRootW(pszFirst)
       || !PathIsRootW(pszFirst)
       || !wcscmp_0(pszFirst, L"\\\\?")
       || !wcscmp_0(pszFirst, L"\\\\.")) )
    {
      v14 = 4;
    }
    else
    {
      v14 = 0;
    }
    *a4 = v14;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a0e4  mov     [rsp-8+arg_8], rbx
0x18000a0e9  mov     [rsp-8+arg_10], rsi
0x18000a0ee  push    rbp
0x18000a0ef  push    rdi
0x18000a0f0  push    r14
0x18000a0f2  lea     rbp, [rsp-1FD0h]
0x18000a0fa  mov     eax, 20D0h
0x18000a0ff  call    _alloca_probe
0x18000a104  sub     rsp, rax
0x18000a107  mov     rax, cs:__security_cookie
0x18000a10e  xor     rax, rsp
0x18000a111  mov     [rbp+1FE0h+var_20], rax
0x18000a118  xor     r14d, r14d
0x18000a11b  mov     rbx, r9
0x18000a11e  mov     rdi, rcx
0x18000a121  test    rcx, rcx
0x18000a124  jz      loc_18000A2CE
0x18000a12a  test    rbx, rbx
0x18000a12d  jz      loc_18000A2DA
0x18000a133  xor     edx, edx; Val
0x18000a135  lea     rcx, [rbp+1FE0h+var_1070]; void *
0x18000a13c  mov     r8d, 1048h; Size
0x18000a142  call    memset_0
0x18000a147  mov     rcx, rdi; pszPath
0x18000a14a  call    cs:__imp_PathIsURLW
0x18000a150  mov     esi, 824h
0x18000a155  test    eax, eax
0x18000a157  jnz     short loc_18000A177
0x18000a159  mov     r8d, esi
0x18000a15c  lea     rdx, [rbp+1FE0h+var_1070]
0x18000a163  mov     rcx, rdi
0x18000a166  call    cs:__imp_SHExpandEnvironmentStringsW
0x18000a16c  test    eax, eax
0x18000a16e  jz      short loc_18000A177
0x18000a170  lea     rdi, [rbp+1FE0h+var_1070]
0x18000a177  mov     r9, rbx; unsigned int *
0x18000a17a  mov     r8d, 1; unsigned int
0x18000a180  mov     rcx, rdi; unsigned __int16 *
0x18000a183  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18000a188  test    eax, eax
0x18000a18a  jns     loc_18000A2DF
0x18000a190  xor     edx, edx; Val
0x18000a192  lea     rcx, [rsp+20E0h+pszFirst]; void *
0x18000a197  mov     r8d, 1048h; Size
0x18000a19d  call    memset_0
0x18000a1a2  mov     ecx, 7FFFFFFEh
0x18000a1a7  lea     rax, [rsp+20E0h+pszFirst]
0x18000a1ac  test    rcx, rcx
0x18000a1af  jz      short loc_18000A1CD
0x18000a1b1  movzx   edx, word ptr [rdi]
0x18000a1b4  test    dx, dx
0x18000a1b7  jz      short loc_18000A1CD
0x18000a1b9  mov     [rax], dx
0x18000a1bc  add     rdi, 2
0x18000a1c0  add     rax, 2
0x18000a1c4  dec     rcx
0x18000a1c7  sub     rsi, 1
0x18000a1cb  jnz     short loc_18000A1AC
0x18000a1cd  test    rsi, rsi
0x18000a1d0  lea     rcx, [rax-2]
0x18000a1d4  cmovnz  rcx, rax
0x18000a1d8  mov     [rcx], r14w
0x18000a1dc  movzx   ecx, [rsp+20E0h+pszFirst]
0x18000a1e1  test    cx, cx
0x18000a1e4  jz      short loc_18000A202
0x18000a1e6  lea     rax, [rsp+20E0h+pszFirst]
0x18000a1eb  cmp     cx, 2Fh ; '/'
0x18000a1ef  jnz     short loc_18000A1F6
0x18000a1f1  mov     word ptr [rax], 5Ch ; '\'
0x18000a1f6  add     rax, 2
0x18000a1fa  movzx   ecx, word ptr [rax]
0x18000a1fd  test    cx, cx
0x18000a200  jnz     short loc_18000A1EB
0x18000a202  lea     rdx, pszSrch; "\\??"
0x18000a209  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18000a20e  call    cs:__imp_StrStrIW
0x18000a214  test    rax, rax
0x18000a217  jnz     loc_18000A2C2
0x18000a21d  lea     rdx, aGlobal; "\\\\?\\GLOBAL"
0x18000a224  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18000a229  call    cs:__imp_StrStrIW
0x18000a22f  test    rax, rax
0x18000a232  jnz     loc_18000A2C2
0x18000a238  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18000a23d  call    cs:__imp_PathIsNetworkPathW
0x18000a243  test    eax, eax
0x18000a245  jnz     short loc_18000A2C2
0x18000a247  lea     rdx, asc_180019BC8; "\\\\"
0x18000a24e  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18000a253  call    cs:__imp_StrStrIW
0x18000a259  test    rax, rax
0x18000a25c  jnz     short loc_18000A275
0x18000a25e  lea     rdx, asc_180019BD0; "//"
0x18000a265  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18000a26a  call    cs:__imp_StrStrIW
0x18000a270  test    rax, rax
0x18000a273  jz      short loc_18000A2BD
0x18000a275  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18000a27a  call    cs:__imp_PathStripToRootW
0x18000a280  test    eax, eax
0x18000a282  jz      short loc_18000A2C2
0x18000a284  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18000a289  call    cs:__imp_PathIsRootW
0x18000a28f  test    eax, eax
0x18000a291  jz      short loc_18000A2C2
0x18000a293  lea     rdx, asc_180019BD8; "\\\\?"
0x18000a29a  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x18000a29f  call    wcscmp_0
0x18000a2a4  test    eax, eax
0x18000a2a6  jz      short loc_18000A2C2
0x18000a2a8  lea     rdx, asc_180019BE0; "\\\\."
0x18000a2af  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x18000a2b4  call    wcscmp_0
0x18000a2b9  test    eax, eax
0x18000a2bb  jz      short loc_18000A2C2
0x18000a2bd  mov     eax, r14d
0x18000a2c0  jmp     short loc_18000A2C7
0x18000a2c2  mov     eax, 4
0x18000a2c7  mov     [rbx], eax
0x18000a2c9  mov     eax, r14d
0x18000a2cc  jmp     short loc_18000A2DF
0x18000a2ce  test    rbx, rbx
0x18000a2d1  jz      short loc_18000A2DA
0x18000a2d3  mov     dword ptr [r9], 0FFFFFFFFh
0x18000a2da  mov     eax, 80070057h
0x18000a2df  mov     rcx, [rbp+1FE0h+var_20]
0x18000a2e6  xor     rcx, rsp; StackCookie
0x18000a2e9  call    __security_check_cookie
0x18000a2ee  lea     r11, [rsp+20E0h+var_10]
0x18000a2f6  mov     rbx, [r11+28h]
0x18000a2fa  mov     rsi, [r11+30h]
0x18000a2fe  mov     rsp, r11
0x18000a301  pop     r14
0x18000a303  pop     rdi
0x18000a304  pop     rbp
0x18000a305  retn
```

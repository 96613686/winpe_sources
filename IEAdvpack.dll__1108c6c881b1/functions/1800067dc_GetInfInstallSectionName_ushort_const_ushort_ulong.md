# GetInfInstallSectionName(ushort const *,ushort *,ulong)

- ea: `0x1800067dc`
- end: `0x1800068a5`
- name: `?GetInfInstallSectionName@@YAKPEBGPEAGK@Z`
- size: `201`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180004754`
- `0x18000f7b0`

## callees

- `0x1800022bc`
- `0x1800045e8`
- `0x1800067dc`
- `0x180008cf0`
- `0x18001b980`

## string_xrefs

- `0x18000681e`: `DefaultInstall`

## pseudocode

```c
__int64 __fastcall GetInfInstallSectionName(LPCWSTR lpFileName, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // rdi
  __int64 result; // rax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // r9d
  __int64 v9; // rax
  unsigned int v10; // r11d
  unsigned __int16 v11[264]; // [rsp+20h] [rbp-448h] BYREF
  unsigned __int16 v12[264]; // [rsp+230h] [rbp-238h] BYREF

  v3 = a3;
  result = CheckOSVersion();
  if ( (_DWORD)result )
  {
    if ( !a2 || (v7 = a2, !*a2) )
      v7 = L"DefaultInstall";
    StringCchCopyW(v11, 0x104u, v7);
    MyGetPlatformSection(v11, lpFileName, v12, v8);
    v9 = -1;
    do
      ++v9;
    while ( v12[v9] );
    v10 = v9 + 1;
    if ( a2 )
    {
      if ( v10 <= (unsigned int)v3 )
        StringCchCopyW(a2, v3, v12);
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800067dc  mov     [rsp+arg_18], rbx
0x1800067e1  push    rbp
0x1800067e2  push    rsi
0x1800067e3  push    rdi
0x1800067e4  sub     rsp, 450h
0x1800067eb  mov     rax, cs:__security_cookie
0x1800067f2  xor     rax, rsp
0x1800067f5  mov     [rsp+468h+var_28], rax
0x1800067fd  mov     edi, r8d
0x180006800  mov     rbx, rdx
0x180006803  mov     rsi, rcx
0x180006806  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x18000680b  xor     ebp, ebp
0x18000680d  test    eax, eax
0x18000680f  jz      short loc_180006882
0x180006811  test    rbx, rbx
0x180006814  jz      short loc_18000681E
0x180006816  mov     r8, rbx
0x180006819  cmp     [rbx], bp
0x18000681c  jnz     short loc_180006825
0x18000681e  lea     r8, aDefaultinstall; "DefaultInstall"
0x180006825  mov     edx, 104h; unsigned __int64
0x18000682a  lea     rcx, [rsp+468h+var_448]; unsigned __int16 *
0x18000682f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006834  lea     r8, [rsp+468h+var_238]; unsigned __int16 *
0x18000683c  mov     rdx, rsi; lpFileName
0x18000683f  lea     rcx, [rsp+468h+var_448]; unsigned __int16 *
0x180006844  call    ?MyGetPlatformSection@@YAXPEBG0PEAGK@Z; MyGetPlatformSection(ushort const *,ushort const *,ushort *,ulong)
0x180006849  lea     rcx, [rsp+468h+var_238]
0x180006851  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006855  inc     rax
0x180006858  cmp     [rcx+rax*2], bp
0x18000685c  jnz     short loc_180006855
0x18000685e  lea     r11d, [rax+1]
0x180006862  test    rbx, rbx
0x180006865  jz      short loc_18000687F
0x180006867  cmp     r11d, edi
0x18000686a  ja      short loc_18000687F
0x18000686c  mov     rdx, rdi; unsigned __int64
0x18000686f  lea     r8, [rsp+468h+var_238]; unsigned __int16 *
0x180006877  mov     rcx, rbx; unsigned __int16 *
0x18000687a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000687f  mov     eax, r11d
0x180006882  mov     rcx, [rsp+468h+var_28]
0x18000688a  xor     rcx, rsp; StackCookie
0x18000688d  call    __security_check_cookie
0x180006892  mov     rbx, [rsp+468h+arg_18]
0x18000689a  add     rsp, 450h
0x1800068a1  pop     rdi
0x1800068a2  pop     rsi
0x1800068a3  pop     rbp
0x1800068a4  retn
```

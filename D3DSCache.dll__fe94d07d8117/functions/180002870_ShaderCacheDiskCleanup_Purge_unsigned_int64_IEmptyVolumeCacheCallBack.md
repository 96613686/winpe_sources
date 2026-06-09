# ShaderCacheDiskCleanup::Purge(unsigned __int64,IEmptyVolumeCacheCallBack *)

- ea: `0x180002870`
- end: `0x180002ac5`
- name: `?Purge@ShaderCacheDiskCleanup@@UEAAJ_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(ShaderCacheDiskCleanup *__hidden this, unsigned __int64, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002870`
- `0x180003710`
- `0x1800449f0`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180002a82`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180002a82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000294f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800029b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002a0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000294f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800029b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002a0d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800028f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800028f2`

## pseudocode

```c
__int64 __fastcall ShaderCacheDiskCleanup::Purge(
        ShaderCacheDiskCleanup *this,
        unsigned __int64 a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  __int64 v3; // rax
  __int64 v6; // rbx
  __int64 v7; // rdi
  const WCHAR *v8; // rcx
  _QWORD *v9; // rsi
  _QWORD *v10; // r14
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r12
  _QWORD *v13; // r9
  __int64 v14; // rax
  _QWORD *v15; // r9
  unsigned __int64 v16; // rax
  _QWORD *v17; // r9
  unsigned __int64 v18; // r15
  unsigned __int64 v19; // rax
  const WCHAR *v20; // rcx
  __int64 v23; // [rsp+38h] [rbp-260h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-258h] BYREF

  v3 = *((_QWORD *)this + 10);
  v23 = 0;
  v6 = *(_QWORD *)(v3 + 8);
  v7 = *(_QWORD *)(v3 + 16);
  while ( v6 != v7 )
  {
    if ( *(_QWORD *)(v6 + 64) == *(_QWORD *)(v6 + 72)
      || !*((_BYTE *)this + 72)
      || *(_DWORD *)(v6 + 88) == 1
      && (*(_QWORD *)(v6 + 24) <= 7u ? (v8 = (const WCHAR *)v6) : (v8 = *(const WCHAR **)v6), !PathFileExistsW(v8)) )
    {
      v9 = *(_QWORD **)(v6 + 64);
      v10 = *(_QWORD **)(v6 + 72);
      while ( v9 != v10 )
      {
        v11 = v9[5];
        v12 = v9[4];
        if ( v9[3] <= 7u )
          v13 = v9;
        else
          v13 = (_QWORD *)*v9;
        StringCchPrintfW(FileName, 0x104u, L"%s%s", v13, &qword_1800ACF70);
        if ( DeleteFileW(FileName) )
        {
          v14 = a2;
          if ( a2 > 4 )
            v14 = 4;
          v23 += 4;
          a2 -= v14;
        }
        if ( v9[3] <= 7u )
          v15 = v9;
        else
          v15 = (_QWORD *)*v9;
        StringCchPrintfW(FileName, 0x104u, L"%s%s", v15, L"-shm");
        if ( DeleteFileW(FileName) )
        {
          v16 = a2;
          if ( v11 < a2 )
            v16 = v11;
          v23 += v11;
          a2 -= v16;
        }
        if ( v9[3] <= 7u )
          v17 = v9;
        else
          v17 = (_QWORD *)*v9;
        StringCchPrintfW(FileName, 0x104u, L"%s%s", v17, L"-wal");
        v18 = a2;
        if ( DeleteFileW(FileName) )
        {
          v19 = a2;
          if ( v12 < a2 )
            v19 = v12;
          v18 = a2 - v19;
          v23 += v12;
          a2 -= v19;
        }
        if ( ((unsigned int (__fastcall *)(struct IEmptyVolumeCacheCallBack *, __int64, unsigned __int64, _QWORD, _QWORD))a3->lpVtbl->PurgeProgress)(
               a3,
               v23,
               v18,
               0,
               0) == -2147467260 )
          return 2147500036LL;
        v9 += 6;
      }
      if ( *(_DWORD *)(v6 + 88) == 1 )
      {
        v20 = (const WCHAR *)(v6 + 32);
        if ( *(_QWORD *)(v6 + 56) > 7u )
          v20 = *(const WCHAR **)v20;
        RemoveDirectoryW(v20);
      }
    }
    v6 += 96;
  }
  return 0;
}

```

## disassembly

```asm
0x180002870  mov     [rsp+arg_18], rbx
0x180002875  push    rbp
0x180002876  push    rsi
0x180002877  push    rdi
0x180002878  push    r12
0x18000287a  push    r13
0x18000287c  push    r14
0x18000287e  push    r15
0x180002880  sub     rsp, 260h
0x180002887  mov     rax, cs:__security_cookie
0x18000288e  xor     rax, rsp
0x180002891  mov     [rsp+298h+var_48], rax
0x180002899  mov     rax, [rcx+50h]
0x18000289d  mov     r13, r8
0x1800028a0  mov     [rsp+298h+var_268], rdx
0x1800028a5  mov     rbp, rcx
0x1800028a8  mov     [rsp+298h+var_260], 0
0x1800028b1  mov     rbx, [rax+8]
0x1800028b5  mov     rdi, [rax+10h]
0x1800028b9  lea     rcx, qword_1800ACF70
0x1800028c0  cmp     rbx, rdi
0x1800028c3  jz      loc_180002A98
0x1800028c9  mov     rax, [rbx+48h]
0x1800028cd  cmp     [rbx+40h], rax
0x1800028d1  jz      short loc_180002907
0x1800028d3  cmp     byte ptr [rbp+48h], 0
0x1800028d7  jz      short loc_180002907
0x1800028d9  cmp     dword ptr [rbx+58h], 1
0x1800028dd  jnz     loc_180002A88
0x1800028e3  cmp     qword ptr [rbx+18h], 7
0x1800028e8  jbe     short loc_1800028EF
0x1800028ea  mov     rcx, [rbx]
0x1800028ed  jmp     short loc_1800028F2
0x1800028ef  mov     rcx, rbx; pszPath
0x1800028f2  call    cs:__imp_PathFileExistsW
0x1800028f8  test    eax, eax
0x1800028fa  jnz     loc_180002A88
0x180002900  lea     rcx, qword_1800ACF70
0x180002907  mov     rsi, [rbx+40h]
0x18000290b  mov     r14, [rbx+48h]
0x18000290f  cmp     rsi, r14
0x180002912  jz      loc_180002A6E
0x180002918  cmp     qword ptr [rsi+18h], 7
0x18000291d  mov     r15, [rsi+28h]
0x180002921  mov     r12, [rsi+20h]
0x180002925  jbe     short loc_18000292C
0x180002927  mov     r9, [rsi]
0x18000292a  jmp     short loc_18000292F
0x18000292c  mov     r9, rsi
0x18000292f  mov     [rsp+298h+var_278], rcx
0x180002934  lea     r8, aSS_2; "%s%s"
0x18000293b  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x180002940  mov     edx, 104h; unsigned __int64
0x180002945  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000294a  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18000294f  call    cs:__imp_DeleteFileW
0x180002955  test    eax, eax
0x180002957  jz      short loc_18000297B
0x180002959  mov     rcx, [rsp+298h+var_268]
0x18000295e  mov     edx, 4
0x180002963  cmp     rcx, 4
0x180002967  mov     rax, rcx
0x18000296a  cmova   rax, rdx
0x18000296e  sub     rcx, rax
0x180002971  add     [rsp+298h+var_260], rdx
0x180002976  mov     [rsp+298h+var_268], rcx
0x18000297b  cmp     qword ptr [rsi+18h], 7
0x180002980  jbe     short loc_180002987
0x180002982  mov     r9, [rsi]
0x180002985  jmp     short loc_18000298A
0x180002987  mov     r9, rsi
0x18000298a  lea     rax, aShm; "-shm"
0x180002991  mov     edx, 104h; unsigned __int64
0x180002996  lea     r8, aSS_2; "%s%s"
0x18000299d  mov     [rsp+298h+var_278], rax
0x1800029a2  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x1800029a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800029ac  lea     rcx, [rsp+298h+FileName]; lpFileName
0x1800029b1  call    cs:__imp_DeleteFileW
0x1800029b7  test    eax, eax
0x1800029b9  jz      short loc_1800029D7
0x1800029bb  mov     rcx, [rsp+298h+var_268]
0x1800029c0  cmp     r15, rcx
0x1800029c3  mov     rax, rcx
0x1800029c6  cmovb   rax, r15
0x1800029ca  sub     rcx, rax
0x1800029cd  add     [rsp+298h+var_260], r15
0x1800029d2  mov     [rsp+298h+var_268], rcx
0x1800029d7  cmp     qword ptr [rsi+18h], 7
0x1800029dc  jbe     short loc_1800029E3
0x1800029de  mov     r9, [rsi]
0x1800029e1  jmp     short loc_1800029E6
0x1800029e3  mov     r9, rsi
0x1800029e6  lea     rax, aWal; "-wal"
0x1800029ed  mov     edx, 104h; unsigned __int64
0x1800029f2  lea     r8, aSS_2; "%s%s"
0x1800029f9  mov     [rsp+298h+var_278], rax
0x1800029fe  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x180002a03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002a08  lea     rcx, [rsp+298h+FileName]; lpFileName
0x180002a0d  call    cs:__imp_DeleteFileW
0x180002a13  mov     r15, [rsp+298h+var_268]
0x180002a18  test    eax, eax
0x180002a1a  jz      short loc_180002A33
0x180002a1c  cmp     r12, r15
0x180002a1f  mov     rax, r15
0x180002a22  cmovb   rax, r12
0x180002a26  sub     r15, rax
0x180002a29  add     [rsp+298h+var_260], r12
0x180002a2e  mov     [rsp+298h+var_268], r15
0x180002a33  mov     rax, [r13+0]
0x180002a37  xor     r9d, r9d
0x180002a3a  mov     rdx, [rsp+298h+var_260]
0x180002a3f  mov     r8, r15
0x180002a42  mov     rcx, r13
0x180002a45  mov     [rsp+298h+var_278], 0
0x180002a4e  mov     rax, [rax+20h]
0x180002a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a57  cmp     eax, 80004004h
0x180002a5c  jz      short loc_180002A91
0x180002a5e  add     rsi, 30h ; '0'
0x180002a62  lea     rcx, qword_1800ACF70
0x180002a69  jmp     loc_18000290F
0x180002a6e  cmp     dword ptr [rbx+58h], 1
0x180002a72  jnz     short loc_180002A88
0x180002a74  cmp     qword ptr [rbx+38h], 7
0x180002a79  lea     rcx, [rbx+20h]
0x180002a7d  jbe     short loc_180002A82
0x180002a7f  mov     rcx, [rcx]; lpPathName
0x180002a82  call    cs:__imp_RemoveDirectoryW
0x180002a88  add     rbx, 60h ; '`'
0x180002a8c  jmp     loc_1800028B9
0x180002a91  mov     eax, 80004004h
0x180002a96  jmp     short loc_180002A9A
0x180002a98  xor     eax, eax
0x180002a9a  mov     rcx, [rsp+298h+var_48]
0x180002aa2  xor     rcx, rsp; StackCookie
0x180002aa5  call    __security_check_cookie
0x180002aaa  mov     rbx, [rsp+298h+arg_18]
0x180002ab2  add     rsp, 260h
0x180002ab9  pop     r15
0x180002abb  pop     r14
0x180002abd  pop     r13
0x180002abf  pop     r12
0x180002ac1  pop     rdi
0x180002ac2  pop     rsi
0x180002ac3  pop     rbp
0x180002ac4  retn
```

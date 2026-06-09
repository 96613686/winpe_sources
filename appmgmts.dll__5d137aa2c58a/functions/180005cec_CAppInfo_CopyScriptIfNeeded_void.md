# CAppInfo::CopyScriptIfNeeded(void)

- ea: `0x180005cec`
- end: `0x180005e64`
- name: `?CopyScriptIfNeeded@CAppInfo@@AEAAKXZ`
- size: `376`
- prototype: `__int64 __fastcall(CAppInfo *this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003370`
- `0x180005294`
- `0x1800079b0`
- `0x180008724`

## callees

- `0x180005cec`
- `0x18000d808`
- `0x18000d864`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005d3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005d3c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005db7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005db7`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180005dfd`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180005dfd`

## pseudocode

```c
__int64 __fastcall CAppInfo::CopyScriptIfNeeded(CAppInfo *this)
{
  const WCHAR *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // rcx
  DWORD LastError; // eax
  DWORD v9; // eax
  __int64 v10; // [rsp+40h] [rbp-48h] BYREF
  int v11; // [rsp+48h] [rbp-40h]
  __int64 v12; // [rsp+50h] [rbp-38h]
  __int64 v13; // [rsp+58h] [rbp-30h]
  __int128 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+70h] [rbp-18h]
  int v16; // [rsp+78h] [rbp-10h]

  if ( (*((_DWORD *)this + 56) & 0x400) != 0 )
    return 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 12);
  if ( !v3 )
    return 161;
  v4 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v4 + 296) )
  {
    if ( *(_DWORD *)(v4 + 396) != 1 )
      RevertToSelf();
    v5 = *(_QWORD *)(*((_QWORD *)this + 2) + 264LL);
    v10 = 0;
    v11 = 0;
    v12 = v5;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v6 = CGPOFileDownloader::AsymmetricDownload(
           (CGPOFileDownloader *)&v10,
           *((const unsigned __int16 **)this + 12),
           *((const unsigned __int16 **)this + 11));
    v7 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v7 + 396) != 1 && *(_DWORD *)(v7 + 296) && !ImpersonateLoggedOnUser(*(HANDLE *)(v7 + 264)) )
    {
      if ( *(_DWORD *)&gDebugLevel )
      {
        LastError = GetLastError();
        _DebugMsg(2u, 0xBC4u, LastError);
      }
      GetLastError();
    }
    CGPOFileDownloader::~CGPOFileDownloader((CGPOFileDownloader *)&v10);
  }
  else
  {
    v6 = 0;
    if ( CopyFileW(v3, *((LPCWSTR *)this + 11), 0) )
    {
LABEL_19:
      *((_DWORD *)this + 56) |= 0x400u;
      return v6;
    }
    v9 = GetLastError();
    v6 = v9;
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(
        2u,
        0xBDCu,
        *((_QWORD *)this + 5),
        *((_QWORD *)this + 9),
        *((_QWORD *)this + 12),
        *((_QWORD *)this + 11),
        v9);
  }
  if ( !v6 )
    goto LABEL_19;
  return v6;
}

```

## disassembly

```asm
0x180005cec  mov     [rsp+arg_0], rbx
0x180005cf1  push    rdi
0x180005cf2  sub     rsp, 80h
0x180005cf9  mov     rbx, rcx
0x180005cfc  test    dword ptr [rcx+0E0h], 400h
0x180005d06  jz      short loc_180005D0F
0x180005d08  xor     eax, eax
0x180005d0a  jmp     loc_180005E53
0x180005d0f  mov     rcx, [rcx+60h]; lpExistingFileName
0x180005d13  test    rcx, rcx
0x180005d16  jnz     short loc_180005D22
0x180005d18  mov     eax, 0A1h
0x180005d1d  jmp     loc_180005E53
0x180005d22  mov     rax, [rbx+10h]
0x180005d26  cmp     dword ptr [rax+128h], 0
0x180005d2d  jz      loc_180005DF4
0x180005d33  cmp     dword ptr [rax+18Ch], 1
0x180005d3a  jz      short loc_180005D42
0x180005d3c  call    cs:__imp_RevertToSelf
0x180005d42  mov     rax, [rbx+10h]
0x180005d46  mov     rcx, [rax+108h]
0x180005d4d  mov     [rsp+88h+var_48], 0
0x180005d56  mov     [rsp+88h+var_40], 0
0x180005d5e  mov     [rsp+88h+var_38], rcx
0x180005d63  mov     [rsp+88h+var_30], 0
0x180005d6c  xorps   xmm0, xmm0
0x180005d6f  movdqa  [rsp+88h+var_28], xmm0
0x180005d75  mov     [rsp+88h+var_18], 0
0x180005d7e  mov     [rsp+88h+var_10], 0
0x180005d86  mov     r8, [rbx+58h]; unsigned __int16 *
0x180005d8a  mov     rdx, [rbx+60h]; unsigned __int16 *
0x180005d8e  lea     rcx, [rsp+88h+var_48]; this
0x180005d93  call    ?AsymmetricDownload@CGPOFileDownloader@@QEAAKPEBG0@Z; CGPOFileDownloader::AsymmetricDownload(ushort const *,ushort const *)
0x180005d98  mov     edi, eax
0x180005d9a  mov     rcx, [rbx+10h]
0x180005d9e  cmp     dword ptr [rcx+18Ch], 1
0x180005da5  jz      short loc_180005DE8
0x180005da7  cmp     dword ptr [rcx+128h], 0
0x180005dae  jz      short loc_180005DE8
0x180005db0  mov     rcx, [rcx+108h]; hToken
0x180005db7  call    cs:__imp_ImpersonateLoggedOnUser
0x180005dbd  test    eax, eax
0x180005dbf  jnz     short loc_180005DE8
0x180005dc1  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180005dc7  jz      short loc_180005DE1
0x180005dc9  call    cs:__imp_GetLastError
0x180005dcf  mov     r8d, eax
0x180005dd2  mov     edx, 0BC4h; unsigned int
0x180005dd7  mov     ecx, 2; unsigned int
0x180005ddc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005de1  call    cs:__imp_GetLastError
0x180005de7  nop
0x180005de8  lea     rcx, [rsp+88h+var_48]; this
0x180005ded  call    ??1CGPOFileDownloader@@QEAA@XZ; CGPOFileDownloader::~CGPOFileDownloader(void)
0x180005df2  jmp     short loc_180005E45
0x180005df4  xor     edi, edi
0x180005df6  xor     r8d, r8d; bFailIfExists
0x180005df9  mov     rdx, [rbx+58h]; lpNewFileName
0x180005dfd  call    cs:__imp_CopyFileW
0x180005e03  test    eax, eax
0x180005e05  jnz     short loc_180005E49
0x180005e07  call    cs:__imp_GetLastError
0x180005e0d  mov     edi, eax
0x180005e0f  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180005e16  jz      short loc_180005E45
0x180005e18  mov     [rsp+88h+var_58], eax
0x180005e1c  mov     rax, [rbx+58h]
0x180005e20  mov     [rsp+88h+var_60], rax
0x180005e25  mov     rax, [rbx+60h]
0x180005e29  mov     [rsp+88h+var_68], rax
0x180005e2e  mov     r9, [rbx+48h]
0x180005e32  mov     r8, [rbx+28h]
0x180005e36  mov     edx, 0BDCh; unsigned int
0x180005e3b  mov     ecx, 2; unsigned int
0x180005e40  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005e45  test    edi, edi
0x180005e47  jnz     short loc_180005E51
0x180005e49  bts     dword ptr [rbx+0E0h], 0Ah
0x180005e51  mov     eax, edi
0x180005e53  mov     rbx, [rsp+88h+arg_0]
0x180005e5b  add     rsp, 80h
0x180005e62  pop     rdi
0x180005e63  retn
```

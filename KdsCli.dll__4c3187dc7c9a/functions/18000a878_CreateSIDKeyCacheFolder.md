# CreateSIDKeyCacheFolder

- ea: `0x18000a878`
- end: `0x18000a9e2`
- name: `CreateSIDKeyCacheFolder`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ce40`

## callees

- `0x18000a878`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a983`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a979`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a979`
- `ntdll!wcschr` at `0x18000a95e`
- `ntdll!wcschr` at `0x18000a95e`

## string_xrefs

- `0x18000a8d4`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000a9a3`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall CreateSIDKeyCacheFolder(__int64 a1, _WORD *a2, int a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbp
  size_t v7; // rsi
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  unsigned int v10; // ebx
  const wchar_t *v11; // rbp
  wchar_t *v12; // rax
  wchar_t *v13; // r14
  DWORD LastError; // eax
  int v15; // esi

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  do
    ++v3;
  while ( a2[v3] );
  v7 = v3;
  v8 = (WCHAR *)SIDKeyProvAlloc(v7 * 2 + (-(__int64)(a3 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 24);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    memcpy_0(v8, a2, v7 * 2);
    v9[v7] = asc_18001CD7C[0];
    if ( a3 )
    {
      *(_OWORD *)&v9[v7 + 1] = *(_OWORD *)L"PublicKey\\";
      v9[v7 + 9] = aPublickey[8];
    }
    else
    {
      *(_OWORD *)&v9[v7 + 1] = *(_OWORD *)L"PrivateKey\\";
      *(_DWORD *)&v9[v7 + 9] = *(_DWORD *)L"ey\\";
    }
    v11 = &v9[v5 + 1];
    if ( v11 )
    {
      while ( 1 )
      {
        v12 = wcschr(v11, 0x5Cu);
        v13 = v12;
        if ( v12 )
        {
          *v12 = 0;
          v11 = v12 + 1;
        }
        if ( !CreateDirectoryW(v9, 0) )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError != 183 )
            break;
        }
        if ( !v13 )
          goto LABEL_19;
        *v13 = 92;
      }
      SidKeyDebugTraceError(
        LastError,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x18Du);
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      else
        v10 = v15;
    }
LABEL_19:
    SIDKeyProvFree(v9);
  }
  else
  {
    v10 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0x167u);
  }
  return v10;
}

```

## disassembly

```asm
0x18000a878  push    rbx
0x18000a87a  push    rbp
0x18000a87b  push    rsi
0x18000a87c  push    rdi
0x18000a87d  push    r12
0x18000a87f  push    r14
0x18000a881  push    r15
0x18000a883  sub     rsp, 20h
0x18000a887  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a88b  mov     r15d, r8d
0x18000a88e  mov     rbp, rsi
0x18000a891  xor     r12d, r12d
0x18000a894  mov     r14, rdx
0x18000a897  inc     rbp
0x18000a89a  cmp     [rcx+rbp*2], r12w
0x18000a89f  jnz     short loc_18000A897
0x18000a8a1  inc     rsi
0x18000a8a4  cmp     [rdx+rsi*2], r12w
0x18000a8a9  jnz     short loc_18000A8A1
0x18000a8ab  add     rsi, rsi
0x18000a8ae  mov     eax, r15d
0x18000a8b1  neg     eax
0x18000a8b3  sbb     rcx, rcx
0x18000a8b6  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000a8ba  add     rcx, 18h
0x18000a8be  add     rcx, rsi; unsigned __int64
0x18000a8c1  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000a8c6  mov     rdi, rax
0x18000a8c9  test    rax, rax
0x18000a8cc  jnz     short loc_18000A8F6
0x18000a8ce  mov     r9d, 167h; unsigned int
0x18000a8d4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000a8db  lea     rdx, aHr; "hr"
0x18000a8e2  mov     ecx, 8007000Eh; unsigned int
0x18000a8e7  mov     ebx, 8007000Eh
0x18000a8ec  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000a8f1  jmp     loc_18000A9D1
0x18000a8f6  mov     r8, rsi; Size
0x18000a8f9  mov     rdx, r14; Src
0x18000a8fc  mov     rcx, rdi; void *
0x18000a8ff  mov     ebx, r12d
0x18000a902  call    memcpy_0
0x18000a907  mov     eax, dword ptr cs:asc_18001CD7C; "\\"
0x18000a90d  mov     [rsi+rdi], ax
0x18000a911  test    r15d, r15d
0x18000a914  jz      short loc_18000A930
0x18000a916  movups  xmm0, xmmword ptr cs:aPublickey; "PublicKey\\"
0x18000a91d  movups  xmmword ptr [rsi+rdi+2], xmm0
0x18000a922  movzx   eax, word ptr cs:aPublickey+10h; "y\\"
0x18000a929  mov     [rsi+rdi+12h], ax
0x18000a92e  jmp     short loc_18000A946
0x18000a930  movups  xmm0, xmmword ptr cs:aPrivatekey; "PrivateKey\\"
0x18000a937  movups  xmmword ptr [rsi+rdi+2], xmm0
0x18000a93c  mov     eax, dword ptr cs:aPrivatekey+10h; "ey\\"
0x18000a942  mov     [rsi+rdi+12h], eax
0x18000a946  inc     rbp
0x18000a949  lea     rbp, [rdi+rbp*2]
0x18000a94d  test    rbp, rbp
0x18000a950  jz      short loc_18000A9C9
0x18000a952  mov     r15d, 5Ch ; '\'
0x18000a958  mov     edx, r15d; Ch
0x18000a95b  mov     rcx, rbp; Str
0x18000a95e  call    cs:__imp_wcschr
0x18000a964  mov     r14, rax
0x18000a967  test    rax, rax
0x18000a96a  jz      short loc_18000A974
0x18000a96c  mov     [rax], r12w
0x18000a970  lea     rbp, [rax+2]
0x18000a974  xor     edx, edx; lpSecurityAttributes
0x18000a976  mov     rcx, rdi; lpPathName
0x18000a979  call    cs:__imp_CreateDirectoryW
0x18000a97f  test    eax, eax
0x18000a981  jnz     short loc_18000A992
0x18000a983  call    cs:__imp_GetLastError
0x18000a989  mov     esi, eax
0x18000a98b  cmp     eax, 0B7h
0x18000a990  jnz     short loc_18000A99D
0x18000a992  test    r14, r14
0x18000a995  jz      short loc_18000A9C9
0x18000a997  mov     [r14], r15w
0x18000a99b  jmp     short loc_18000A958
0x18000a99d  mov     r9d, 18Dh; unsigned int
0x18000a9a3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000a9aa  lea     rdx, aDwreturn; "dwReturn"
0x18000a9b1  mov     ecx, esi; unsigned int
0x18000a9b3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000a9b8  test    esi, esi
0x18000a9ba  jg      short loc_18000A9C0
0x18000a9bc  mov     ebx, esi
0x18000a9be  jmp     short loc_18000A9C9
0x18000a9c0  movzx   ebx, si
0x18000a9c3  or      ebx, 80070000h
0x18000a9c9  mov     rcx, rdi; lpMem
0x18000a9cc  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000a9d1  mov     eax, ebx
0x18000a9d3  add     rsp, 20h
0x18000a9d7  pop     r15
0x18000a9d9  pop     r14
0x18000a9db  pop     r12
0x18000a9dd  pop     rdi
0x18000a9de  pop     rsi
0x18000a9df  pop     rbp
0x18000a9e0  pop     rbx
0x18000a9e1  retn
```

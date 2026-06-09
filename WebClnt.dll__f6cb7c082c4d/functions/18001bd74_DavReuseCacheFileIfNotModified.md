# DavReuseCacheFileIfNotModified

- ea: `0x18001bd74`
- end: `0x18001bef3`
- name: `DavReuseCacheFileIfNotModified`
- size: `383`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001507c`

## callees

- `0x18000b4f0`
- `0x18001bd74`
- `0x18002ae00`
- `0x18002bce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be2f`
- `KERNEL32!LocalFree` at `0x18001be3a`
- `KERNEL32!LocalFree` at `0x18001bed3`
- `KERNEL32!LocalFree` at `0x18001be3a`
- `KERNEL32!LocalFree` at `0x18001bed3`
- `KERNEL32!LocalAlloc` at `0x18001be05`
- `KERNEL32!LocalAlloc` at `0x18001be05`
- `WINHTTP!WinHttpCloseHandle` at `0x18001be25`
- `WINHTTP!WinHttpCloseHandle` at `0x18001be25`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001bdce`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001bdce`

## pseudocode

```c
DWORD __fastcall DavReuseCacheFileIfNotModified(__int64 a1)
{
  _QWORD *v1; // rsi
  void *v4; // rcx
  __int64 v5; // rcx
  SIZE_T v6; // r14
  HLOCAL v7; // rax
  void *v8; // rbp
  void *v9; // rcx
  DWORD LastError; // edi
  _WORD *v11; // rax
  _WORD *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  _WORD *v15; // rcx
  __int64 v16; // rcx
  int Buffer; // [rsp+60h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+68h] [rbp+10h] BYREF

  v1 = *(_QWORD **)(a1 + 608);
  Buffer = 0;
  if ( !v1 )
    return 2;
  v4 = *(void **)(a1 + 592);
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(v4, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    return GetLastError();
  if ( Buffer == 304 )
  {
    v6 = (unsigned int)(2 * *((_DWORD *)v1 + 4) + 2);
    v7 = LocalAlloc(0x40u, v6);
    v8 = v7;
    if ( v7 )
    {
      v9 = *(void **)(a1 + 592);
      *(_QWORD *)(a1 + 576) = v7;
      if ( WinHttpCloseHandle(v9) )
      {
        *(_QWORD *)(a1 + 592) = 0;
        v11 = (_WORD *)(a1 + 2312);
        v12 = (_WORD *)v1[1];
        LastError = 0;
        v13 = 2147483646;
        v14 = 260;
        do
        {
          if ( !v13 )
            break;
          if ( !*v12 )
            break;
          *v11++ = *v12++;
          --v13;
          --v14;
        }
        while ( v14 );
        v15 = v11 - 1;
        if ( v14 )
          v15 = v11;
        *v15 = 0;
        StringCbCopyW(*(STRSAFE_LPWSTR *)(a1 + 576), v6, (STRSAFE_LPCWSTR)v1[1]);
        TfsReferenceEntry(v16, *v1);
      }
      else
      {
        LastError = GetLastError();
        LocalFree(v8);
        *(_QWORD *)(a1 + 576) = 0;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    LastError = 2;
    TfsDeleteEntry(v5, *v1);
    LocalFree(*(HLOCAL *)(a1 + 608));
    *(_QWORD *)(a1 + 608) = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001bd74  mov     [rsp+arg_10], rbx
0x18001bd79  push    rbp
0x18001bd7a  push    rsi
0x18001bd7b  push    rdi
0x18001bd7c  push    r14
0x18001bd7e  push    r15
0x18001bd80  sub     rsp, 30h
0x18001bd84  mov     rsi, [rcx+260h]
0x18001bd8b  xor     r15d, r15d
0x18001bd8e  mov     [rsp+58h+Buffer], r15d
0x18001bd93  mov     rbx, rcx
0x18001bd96  test    rsi, rsi
0x18001bd99  jnz     short loc_18001BDA3
0x18001bd9b  lea     eax, [rsi+2]
0x18001bd9e  jmp     loc_18001BEE2
0x18001bda3  mov     rcx, [rcx+250h]; hRequest
0x18001bdaa  lea     rax, [rsp+58h+dwBufferLength]
0x18001bdaf  mov     [rsp+58h+lpdwIndex], r15; lpdwIndex
0x18001bdb4  lea     r9, [rsp+58h+Buffer]; lpBuffer
0x18001bdb9  xor     r8d, r8d; pwszName
0x18001bdbc  mov     [rsp+58h+lpdwBufferLength], rax; lpdwBufferLength
0x18001bdc1  mov     edx, 20000013h; dwInfoLevel
0x18001bdc6  mov     [rsp+58h+dwBufferLength], 4
0x18001bdce  call    cs:__imp_WinHttpQueryHeaders
0x18001bdd4  test    eax, eax
0x18001bdd6  jnz     short loc_18001BDE3
0x18001bdd8  call    cs:__imp_GetLastError
0x18001bdde  jmp     loc_18001BEE2
0x18001bde3  cmp     [rsp+58h+Buffer], 130h
0x18001bdeb  jnz     loc_18001BEBF
0x18001bdf1  mov     eax, [rsi+10h]
0x18001bdf4  mov     ecx, 40h ; '@'; uFlags
0x18001bdf9  lea     eax, ds:2[rax*2]
0x18001be00  mov     edx, eax; uBytes
0x18001be02  mov     r14d, eax
0x18001be05  call    cs:__imp_LocalAlloc
0x18001be0b  mov     rbp, rax
0x18001be0e  test    rax, rax
0x18001be11  jz      loc_18001BEBA
0x18001be17  mov     rcx, [rbx+250h]; hInternet
0x18001be1e  mov     [rbx+240h], rax
0x18001be25  call    cs:__imp_WinHttpCloseHandle
0x18001be2b  test    eax, eax
0x18001be2d  jnz     short loc_18001BE4C
0x18001be2f  call    cs:__imp_GetLastError
0x18001be35  mov     rcx, rbp; hMem
0x18001be38  mov     edi, eax
0x18001be3a  call    cs:__imp_LocalFree
0x18001be40  mov     [rbx+240h], r15
0x18001be47  jmp     loc_18001BEE0
0x18001be4c  mov     [rbx+250h], r15
0x18001be53  lea     rax, [rbx+908h]
0x18001be5a  mov     r9, [rsi+8]
0x18001be5e  mov     edi, r15d
0x18001be61  mov     ecx, 7FFFFFFEh
0x18001be66  mov     r8d, 104h
0x18001be6c  test    rcx, rcx
0x18001be6f  jz      short loc_18001BE8E
0x18001be71  movzx   edx, word ptr [r9]
0x18001be75  test    dx, dx
0x18001be78  jz      short loc_18001BE8E
0x18001be7a  mov     [rax], dx
0x18001be7d  add     r9, 2
0x18001be81  add     rax, 2
0x18001be85  dec     rcx
0x18001be88  sub     r8, 1
0x18001be8c  jnz     short loc_18001BE6C
0x18001be8e  test    r8, r8
0x18001be91  lea     rcx, [rax-2]
0x18001be95  mov     rdx, r14; cbDest
0x18001be98  cmovnz  rcx, rax
0x18001be9c  mov     [rcx], r15w
0x18001bea0  mov     r8, [rsi+8]; pszSrc
0x18001bea4  mov     rcx, [rbx+240h]; pszDest
0x18001beab  call    StringCbCopyW
0x18001beb0  mov     rdx, [rsi]
0x18001beb3  call    TfsReferenceEntry
0x18001beb8  jmp     short loc_18001BEE0
0x18001beba  mov     edi, r15d
0x18001bebd  jmp     short loc_18001BEE0
0x18001bebf  mov     rdx, [rsi]
0x18001bec2  mov     edi, 2
0x18001bec7  call    TfsDeleteEntry
0x18001becc  mov     rcx, [rbx+260h]; hMem
0x18001bed3  call    cs:__imp_LocalFree
0x18001bed9  mov     [rbx+260h], r15
0x18001bee0  mov     eax, edi
0x18001bee2  mov     rbx, [rsp+58h+arg_10]
0x18001bee7  add     rsp, 30h
0x18001beeb  pop     r15
0x18001beed  pop     r14
0x18001beef  pop     rdi
0x18001bef0  pop     rsi
0x18001bef1  pop     rbp
0x18001bef2  retn
```

# AVISaveW

- ea: `0x180002d00`
- end: `0x180002eac`
- name: `AVISaveW`
- size: `428`
- prototype: `HRESULT(LPCWSTR szFile, CLSID *pclsidHandler, AVISAVECALLBACK lpfnCallback, int nStreams, PAVISTREAM pfile, LPAVICOMPRESSOPTIONS lpOptions, ...)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180001fe0`
- `0x180002d00`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002dbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e71`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002dbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e71`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002d7c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002da5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002d7c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002da5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002db6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002dc8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e44`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e7a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002db6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002dc8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e44`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002e7a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002d73`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002d9c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002d73`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002d9c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002dd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002e5f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002e83`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002dd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002e5f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002e83`

## pseudocode

```c
HRESULT AVISaveW(
        LPCWSTR szFile,
        CLSID *pclsidHandler,
        AVISAVECALLBACK lpfnCallback,
        int nStreams,
        PAVISTREAM pfile,
        LPAVICOMPRESSOPTIONS lpOptions,
        ...)
{
  SIZE_T v10; // rsi
  HGLOBAL v11; // rax
  _QWORD *ppavi; // rdi
  HGLOBAL v14; // rax
  LPAVICOMPRESSOPTIONS *plpOptions; // rsi
  HGLOBAL v16; // rax
  HGLOBAL v17; // rax
  int v18; // r11d
  va_list v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r10
  HRESULT v22; // ebx
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax
  HGLOBAL v25; // rax
  HGLOBAL v26; // rax
  va_list va; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va, lpOptions);
  if ( !is_mul_ok(nStreams, 8u) )
    return -2147024362;
  v10 = 8LL * nStreams;
  if ( !is_mul_ok(nStreams, 8u) )
    return -2147024362;
  v11 = GlobalAlloc(2u, 8LL * nStreams);
  ppavi = GlobalLock(v11);
  if ( !ppavi )
    return -2147205017;
  v14 = GlobalAlloc(2u, v10);
  plpOptions = (LPAVICOMPRESSOPTIONS *)GlobalLock(v14);
  if ( !plpOptions )
  {
    v16 = GlobalHandle(ppavi);
    GlobalUnlock(v16);
    v17 = GlobalHandle(ppavi);
    GlobalFree(v17);
    return -2147205017;
  }
  if ( nStreams )
  {
    *ppavi = pfile;
    *plpOptions = lpOptions;
  }
  v18 = 1;
  va_copy(v19, va);
  if ( nStreams > 1 )
  {
    do
    {
      v20 = *(_QWORD *)v19;
      v19 += 16;
      v21 = (unsigned int)v18++;
      ppavi[v21] = v20;
      plpOptions[v21] = (LPAVICOMPRESSOPTIONS)*((_QWORD *)v19 - 1);
    }
    while ( v18 < nStreams );
  }
  v22 = AVISaveVW(szFile, pclsidHandler, lpfnCallback, nStreams, (PAVISTREAM *)ppavi, plpOptions);
  v23 = GlobalHandle(ppavi);
  GlobalUnlock(v23);
  v24 = GlobalHandle(ppavi);
  GlobalFree(v24);
  v25 = GlobalHandle(plpOptions);
  GlobalUnlock(v25);
  v26 = GlobalHandle(plpOptions);
  GlobalFree(v26);
  return v22;
}

```

## disassembly

```asm
0x180002d00  push    rbx
0x180002d02  push    rbp
0x180002d03  push    rsi
0x180002d04  push    rdi
0x180002d05  push    r14
0x180002d07  push    r15
0x180002d09  sub     rsp, 48h
0x180002d0d  mov     rax, cs:__security_cookie
0x180002d14  xor     rax, rsp
0x180002d17  mov     [rsp+78h+var_40], rax
0x180002d1c  movsxd  rbx, r9d
0x180002d1f  mov     r14, rdx
0x180002d22  mov     r9d, 8
0x180002d28  mov     [rsp+78h+var_48], 0
0x180002d31  mov     eax, r9d
0x180002d34  mov     [rsp+78h+var_48], 0
0x180002d3d  mul     rbx
0x180002d40  mov     r15, r8
0x180002d43  mov     rbp, rcx
0x180002d46  mov     rcx, rbx
0x180002d49  mov     r8, rax
0x180002d4c  test    rdx, rdx
0x180002d4f  jnz     loc_180002E8D
0x180002d55  mov     eax, r9d
0x180002d58  mov     [rsp+78h+var_48], rdx
0x180002d5d  mul     rcx
0x180002d60  mov     rsi, rax
0x180002d63  test    rdx, rdx
0x180002d66  jnz     loc_180002E8D
0x180002d6c  mov     rdx, r8; dwBytes
0x180002d6f  lea     ecx, [r9-6]; uFlags
0x180002d73  call    cs:__imp_GlobalAlloc
0x180002d79  mov     rcx, rax; hMem
0x180002d7c  call    cs:__imp_GlobalLock
0x180002d82  mov     rdi, rax
0x180002d85  test    rax, rax
0x180002d88  jnz     short loc_180002D94
0x180002d8a  mov     eax, 80044067h
0x180002d8f  jmp     loc_180002E92
0x180002d94  mov     rdx, rsi; dwBytes
0x180002d97  mov     ecx, 2; uFlags
0x180002d9c  call    cs:__imp_GlobalAlloc
0x180002da2  mov     rcx, rax; hMem
0x180002da5  call    cs:__imp_GlobalLock
0x180002dab  mov     rsi, rax
0x180002dae  test    rax, rax
0x180002db1  jnz     short loc_180002DD9
0x180002db3  mov     rcx, rdi; pMem
0x180002db6  call    cs:__imp_GlobalHandle
0x180002dbc  mov     rcx, rax; hMem
0x180002dbf  call    cs:__imp_GlobalUnlock
0x180002dc5  mov     rcx, rdi; pMem
0x180002dc8  call    cs:__imp_GlobalHandle
0x180002dce  mov     rcx, rax; hMem
0x180002dd1  call    cs:__imp_GlobalFree
0x180002dd7  jmp     short loc_180002D8A
0x180002dd9  test    ebx, ebx
0x180002ddb  jz      short loc_180002DF3
0x180002ddd  mov     rax, [rsp+78h+pfile]
0x180002de5  mov     [rdi], rax
0x180002de8  mov     rax, [rsp+78h+lpOptions]
0x180002df0  mov     [rsi], rax
0x180002df3  mov     r11d, 1
0x180002df9  lea     rcx, [rsp+78h+arg_30]
0x180002e01  cmp     ebx, r11d
0x180002e04  jle     short loc_180002E24
0x180002e06  mov     rax, [rcx]
0x180002e09  lea     rcx, [rcx+10h]
0x180002e0d  mov     r10d, r11d
0x180002e10  inc     r11d
0x180002e13  mov     [rdi+r10*8], rax
0x180002e17  mov     rax, [rcx-8]
0x180002e1b  mov     [rsi+r10*8], rax
0x180002e1f  cmp     r11d, ebx
0x180002e22  jl      short loc_180002E06
0x180002e24  mov     [rsp+78h+plpOptions], rsi; plpOptions
0x180002e29  mov     r9d, ebx; nStreams
0x180002e2c  mov     r8, r15; lpfnCallback
0x180002e2f  mov     [rsp+78h+ppavi], rdi; ppavi
0x180002e34  mov     rdx, r14; pclsidHandler
0x180002e37  mov     rcx, rbp; szFile
0x180002e3a  call    AVISaveVW
0x180002e3f  mov     rcx, rdi; pMem
0x180002e42  mov     ebx, eax
0x180002e44  call    cs:__imp_GlobalHandle
0x180002e4a  mov     rcx, rax; hMem
0x180002e4d  call    cs:__imp_GlobalUnlock
0x180002e53  mov     rcx, rdi; pMem
0x180002e56  call    cs:__imp_GlobalHandle
0x180002e5c  mov     rcx, rax; hMem
0x180002e5f  call    cs:__imp_GlobalFree
0x180002e65  mov     rcx, rsi; pMem
0x180002e68  call    cs:__imp_GlobalHandle
0x180002e6e  mov     rcx, rax; hMem
0x180002e71  call    cs:__imp_GlobalUnlock
0x180002e77  mov     rcx, rsi; pMem
0x180002e7a  call    cs:__imp_GlobalHandle
0x180002e80  mov     rcx, rax; hMem
0x180002e83  call    cs:__imp_GlobalFree
0x180002e89  mov     eax, ebx
0x180002e8b  jmp     short loc_180002E92
0x180002e8d  mov     eax, 80070216h
0x180002e92  mov     rcx, [rsp+78h+var_40]
0x180002e97  xor     rcx, rsp; StackCookie
0x180002e9a  call    __security_check_cookie
0x180002e9f  add     rsp, 48h
0x180002ea3  pop     r15
0x180002ea5  pop     r14
0x180002ea7  pop     rdi
0x180002ea8  pop     rsi
0x180002ea9  pop     rbp
0x180002eaa  pop     rbx
0x180002eab  retn
```

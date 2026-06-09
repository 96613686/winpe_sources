# AVISaveA

- ea: `0x180001d80`
- end: `0x180001f2c`
- name: `AVISaveA`
- size: `428`
- prototype: `HRESULT(LPCSTR szFile, CLSID *pclsidHandler, AVISAVECALLBACK lpfnCallback, int nStreams, PAVISTREAM pfile, LPAVICOMPRESSOPTIONS lpOptions, ...)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d80`
- `0x180001f40`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001e3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ecd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ef1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001e3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ecd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001ef1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001dfc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e25`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001dfc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e25`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001e36`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001e48`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ec4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ed6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ee8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001efa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001e36`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001e48`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ec4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ed6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001ee8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180001efa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001df3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e1c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001df3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e1c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001e51`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001edf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f03`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001e51`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001edf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f03`

## pseudocode

```c
HRESULT AVISaveA(
        LPCSTR szFile,
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
  v22 = AVISaveVA(szFile, pclsidHandler, lpfnCallback, nStreams, (PAVISTREAM *)ppavi, plpOptions);
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
0x180001d80  push    rbx; AVISave
0x180001d82  push    rbp
0x180001d83  push    rsi
0x180001d84  push    rdi
0x180001d85  push    r14
0x180001d87  push    r15
0x180001d89  sub     rsp, 48h
0x180001d8d  mov     rax, cs:__security_cookie
0x180001d94  xor     rax, rsp
0x180001d97  mov     [rsp+78h+var_40], rax
0x180001d9c  movsxd  rbx, r9d
0x180001d9f  mov     r14, rdx
0x180001da2  mov     r9d, 8
0x180001da8  mov     [rsp+78h+var_48], 0
0x180001db1  mov     eax, r9d
0x180001db4  mov     [rsp+78h+var_48], 0
0x180001dbd  mul     rbx
0x180001dc0  mov     r15, r8
0x180001dc3  mov     rbp, rcx
0x180001dc6  mov     rcx, rbx
0x180001dc9  mov     r8, rax
0x180001dcc  test    rdx, rdx
0x180001dcf  jnz     loc_180001F0D
0x180001dd5  mov     eax, r9d
0x180001dd8  mov     [rsp+78h+var_48], rdx
0x180001ddd  mul     rcx
0x180001de0  mov     rsi, rax
0x180001de3  test    rdx, rdx
0x180001de6  jnz     loc_180001F0D
0x180001dec  mov     rdx, r8; dwBytes
0x180001def  lea     ecx, [r9-6]; uFlags
0x180001df3  call    cs:__imp_GlobalAlloc
0x180001df9  mov     rcx, rax; hMem
0x180001dfc  call    cs:__imp_GlobalLock
0x180001e02  mov     rdi, rax
0x180001e05  test    rax, rax
0x180001e08  jnz     short loc_180001E14
0x180001e0a  mov     eax, 80044067h
0x180001e0f  jmp     loc_180001F12
0x180001e14  mov     rdx, rsi; dwBytes
0x180001e17  mov     ecx, 2; uFlags
0x180001e1c  call    cs:__imp_GlobalAlloc
0x180001e22  mov     rcx, rax; hMem
0x180001e25  call    cs:__imp_GlobalLock
0x180001e2b  mov     rsi, rax
0x180001e2e  test    rax, rax
0x180001e31  jnz     short loc_180001E59
0x180001e33  mov     rcx, rdi; pMem
0x180001e36  call    cs:__imp_GlobalHandle
0x180001e3c  mov     rcx, rax; hMem
0x180001e3f  call    cs:__imp_GlobalUnlock
0x180001e45  mov     rcx, rdi; pMem
0x180001e48  call    cs:__imp_GlobalHandle
0x180001e4e  mov     rcx, rax; hMem
0x180001e51  call    cs:__imp_GlobalFree
0x180001e57  jmp     short loc_180001E0A
0x180001e59  test    ebx, ebx
0x180001e5b  jz      short loc_180001E73
0x180001e5d  mov     rax, [rsp+78h+pfile]
0x180001e65  mov     [rdi], rax
0x180001e68  mov     rax, [rsp+78h+lpOptions]
0x180001e70  mov     [rsi], rax
0x180001e73  mov     r11d, 1
0x180001e79  lea     rcx, [rsp+78h+arg_30]
0x180001e81  cmp     ebx, r11d
0x180001e84  jle     short loc_180001EA4
0x180001e86  mov     rax, [rcx]
0x180001e89  lea     rcx, [rcx+10h]
0x180001e8d  mov     r10d, r11d
0x180001e90  inc     r11d
0x180001e93  mov     [rdi+r10*8], rax
0x180001e97  mov     rax, [rcx-8]
0x180001e9b  mov     [rsi+r10*8], rax
0x180001e9f  cmp     r11d, ebx
0x180001ea2  jl      short loc_180001E86
0x180001ea4  mov     [rsp+78h+plpOptions], rsi; plpOptions
0x180001ea9  mov     r9d, ebx; nStreams
0x180001eac  mov     r8, r15; lpfnCallback
0x180001eaf  mov     [rsp+78h+ppavi], rdi; ppavi
0x180001eb4  mov     rdx, r14; pclsidHandler
0x180001eb7  mov     rcx, rbp; szFile
0x180001eba  call    AVISaveVA
0x180001ebf  mov     rcx, rdi; pMem
0x180001ec2  mov     ebx, eax
0x180001ec4  call    cs:__imp_GlobalHandle
0x180001eca  mov     rcx, rax; hMem
0x180001ecd  call    cs:__imp_GlobalUnlock
0x180001ed3  mov     rcx, rdi; pMem
0x180001ed6  call    cs:__imp_GlobalHandle
0x180001edc  mov     rcx, rax; hMem
0x180001edf  call    cs:__imp_GlobalFree
0x180001ee5  mov     rcx, rsi; pMem
0x180001ee8  call    cs:__imp_GlobalHandle
0x180001eee  mov     rcx, rax; hMem
0x180001ef1  call    cs:__imp_GlobalUnlock
0x180001ef7  mov     rcx, rsi; pMem
0x180001efa  call    cs:__imp_GlobalHandle
0x180001f00  mov     rcx, rax; hMem
0x180001f03  call    cs:__imp_GlobalFree
0x180001f09  mov     eax, ebx
0x180001f0b  jmp     short loc_180001F12
0x180001f0d  mov     eax, 80070216h
0x180001f12  mov     rcx, [rsp+78h+var_40]
0x180001f17  xor     rcx, rsp; StackCookie
0x180001f1a  call    __security_check_cookie
0x180001f1f  add     rsp, 48h
0x180001f23  pop     r15
0x180001f25  pop     r14
0x180001f27  pop     rdi
0x180001f28  pop     rsi
0x180001f29  pop     rbp
0x180001f2a  pop     rbx
0x180001f2b  retn
```

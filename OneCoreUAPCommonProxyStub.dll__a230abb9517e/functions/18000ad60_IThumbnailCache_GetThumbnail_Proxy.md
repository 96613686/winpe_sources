# IThumbnailCache_GetThumbnail_Proxy

- ea: `0x18000ad60`
- end: `0x18000ae04`
- name: `IThumbnailCache_GetThumbnail_Proxy`
- size: `164`
- prototype: `HRESULT __stdcall(IThumbnailCache *This, IShellItem *pShellItem, UINT cxyRequestedThumbSize, WTS_FLAGS flags, ISharedBitmap **ppvThumb, WTS_CACHEFLAGS *pOutFlags, WTS_THUMBNAILID *pThumbnailID)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c80`
- `0x18000ad60`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000add1`
- `RPCRT4!NdrClientCall3` at `0x18000add1`

## pseudocode

```c
HRESULT __stdcall IThumbnailCache_GetThumbnail_Proxy(
        IThumbnailCache *This,
        IShellItem *pShellItem,
        UINT cxyRequestedThumbSize,
        WTS_FLAGS flags,
        ISharedBitmap **ppvThumb,
        WTS_CACHEFLAGS *pOutFlags,
        WTS_THUMBNAILID *pThumbnailID)
{
  HRESULT result; // eax
  WTS_CACHEFLAGS v10; // [rsp+50h] [rbp-38h] BYREF
  WTS_THUMBNAILID v11; // [rsp+58h] [rbp-30h] BYREF

  v11 = 0;
  v10 = WTS_DEFAULT;
  result = (unsigned int)NdrClientCall3(
                           (MIDL_STUBLESS_PROXY_INFO *)&stru_1802386D0,
                           3u,
                           0,
                           This,
                           pShellItem,
                           cxyRequestedThumbSize,
                           flags,
                           ppvThumb,
                           &v10,
                           &v11).Pointer;
  if ( pOutFlags )
    *pOutFlags = v10;
  if ( pThumbnailID )
    *pThumbnailID = v11;
  return result;
}

```

## disassembly

```asm
0x18000ad60  mov     r11, rsp
0x18000ad63  push    rbx
0x18000ad64  push    rdi
0x18000ad65  sub     rsp, 78h
0x18000ad69  mov     rax, cs:__security_cookie
0x18000ad70  xor     rax, rsp
0x18000ad73  mov     [rsp+88h+var_20], rax
0x18000ad78  mov     rax, [rsp+88h+ppvThumb]
0x18000ad80  lea     r10, [r11-30h]
0x18000ad84  mov     rdi, [rsp+88h+pOutFlags]
0x18000ad8c  xorps   xmm0, xmm0
0x18000ad8f  mov     rbx, [rsp+88h+pThumbnailID]
0x18000ad97  mov     [r11-40h], r10
0x18000ad9b  lea     r10, [r11-38h]
0x18000ad9f  mov     [r11-48h], r10
0x18000ada3  mov     [r11-50h], rax
0x18000ada7  mov     [r11-58h], r9d
0x18000adab  mov     r9, rcx
0x18000adae  mov     [r11-60h], r8d
0x18000adb2  lea     rcx, stru_1802386D0; pProxyInfo
0x18000adb9  xor     r8d, r8d; pReturnValue
0x18000adbc  mov     [r11-68h], rdx
0x18000adc0  movups  [rsp+88h+var_30], xmm0
0x18000adc5  mov     [rsp+88h+var_38], 0
0x18000adcd  lea     edx, [r8+3]; nProcNum
0x18000add1  call    cs:__imp_NdrClientCall3
0x18000add7  test    rdi, rdi
0x18000adda  jz      short loc_18000ADE2
0x18000addc  mov     ecx, [rsp+88h+var_38]
0x18000ade0  mov     [rdi], ecx
0x18000ade2  test    rbx, rbx
0x18000ade5  jz      short loc_18000ADF0
0x18000ade7  movups  xmm0, [rsp+88h+var_30]
0x18000adec  movdqu  xmmword ptr [rbx], xmm0
0x18000adf0  mov     rcx, [rsp+88h+var_20]
0x18000adf5  xor     rcx, rsp; StackCookie
0x18000adf8  call    __security_check_cookie
0x18000adfd  add     rsp, 78h
0x18000ae01  pop     rdi
0x18000ae02  pop     rbx
0x18000ae03  retn
```

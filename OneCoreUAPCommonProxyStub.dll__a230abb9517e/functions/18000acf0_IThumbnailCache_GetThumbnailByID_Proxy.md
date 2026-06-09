# IThumbnailCache_GetThumbnailByID_Proxy

- ea: `0x18000acf0`
- end: `0x18000ad4f`
- name: `IThumbnailCache_GetThumbnailByID_Proxy`
- size: `95`
- prototype: `HRESULT __stdcall(IThumbnailCache *This, WTS_THUMBNAILID *__struct_ptr thumbnailID, UINT cxyRequestedThumbSize, ISharedBitmap **ppvThumb, WTS_CACHEFLAGS *pOutFlags)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000acf0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ad31`
- `RPCRT4!NdrClientCall3` at `0x18000ad31`

## pseudocode

```c
HRESULT __stdcall IThumbnailCache_GetThumbnailByID_Proxy(
        IThumbnailCache *This,
        WTS_THUMBNAILID *thumbnailID,
        UINT cxyRequestedThumbSize,
        ISharedBitmap **ppvThumb,
        WTS_CACHEFLAGS *pOutFlags)
{
  WTS_THUMBNAILID v5; // xmm0
  HRESULT result; // eax
  WTS_THUMBNAILID v8; // [rsp+40h] [rbp-18h] BYREF
  WTS_CACHEFLAGS v9; // [rsp+68h] [rbp+10h] BYREF

  v5 = *thumbnailID;
  v9 = WTS_DEFAULT;
  v8 = v5;
  result = (unsigned int)NdrClientCall3(
                           (MIDL_STUBLESS_PROXY_INFO *)&stru_1802386D0,
                           4u,
                           0,
                           This,
                           &v8,
                           cxyRequestedThumbSize,
                           ppvThumb,
                           &v9).Pointer;
  if ( pOutFlags )
    *pOutFlags = v9;
  return result;
}

```

## disassembly

```asm
0x18000acf0  mov     r11, rsp
0x18000acf3  sub     rsp, 58h
0x18000acf7  movups  xmm0, xmmword ptr [rdx]
0x18000acfa  lea     rax, [r11+10h]
0x18000acfe  mov     [rsp+58h+arg_8], 0
0x18000ad06  mov     [r11-20h], rax
0x18000ad0a  lea     rax, [r11-18h]
0x18000ad0e  mov     [r11-28h], r9
0x18000ad12  mov     r9, rcx
0x18000ad15  mov     [r11-30h], r8d
0x18000ad19  lea     rcx, stru_1802386D0; pProxyInfo
0x18000ad20  xor     r8d, r8d; pReturnValue
0x18000ad23  mov     [r11-38h], rax
0x18000ad27  movdqu  xmmword ptr [rsp+58h+var_18.rgbKey], xmm0
0x18000ad2d  lea     edx, [r8+4]; nProcNum
0x18000ad31  call    cs:__imp_NdrClientCall3
0x18000ad37  mov     rdx, [rsp+58h+pOutFlags]
0x18000ad3f  test    rdx, rdx
0x18000ad42  jz      short loc_18000AD4A
0x18000ad44  mov     ecx, [rsp+58h+arg_8]
0x18000ad48  mov     [rdx], ecx
0x18000ad4a  add     rsp, 58h
0x18000ad4e  retn
```

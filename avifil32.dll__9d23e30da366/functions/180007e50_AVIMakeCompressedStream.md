# AVIMakeCompressedStream

- ea: `0x180007e50`
- end: `0x180007fbe`
- name: `AVIMakeCompressedStream`
- size: `366`
- prototype: `HRESULT __stdcall(PAVISTREAM *ppsCompressed, PAVISTREAM ppsSource, AVICOMPRESSOPTIONS *lpOptions, CLSID *pclsidHandler)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001fe0`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x1800070ec`
- `0x180007e50`
- `0x180008300`
- `0x1800088ac`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ee2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ee2`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180007f7c`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180007f7c`

## string_xrefs

- `0x180007f4a`: `AVIFile\Compressors\%.4hs`

## pseudocode

```c
HRESULT __stdcall AVIMakeCompressedStream(
        PAVISTREAM *ppsCompressed,
        PAVISTREAM ppsSource,
        AVICOMPRESSOPTIONS *lpOptions,
        CLSID *pclsidHandler)
{
  HRESULT result; // eax
  HRESULT v9; // edi
  LONG cbData; // [rsp+30h] [rbp-D0h] BYREF
  IID rclsid; // [rsp+38h] [rbp-C8h] BYREF
  struct _AVISTREAMINFOW psi; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[104]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR SubKey[104]; // [rsp+1F0h] [rbp+F0h] BYREF

  rclsid = 0;
  memset_0(Data, 0, 0xC8u);
  cbData = 0;
  memset_0(&psi, 0, sizeof(psi));
  *ppsCompressed = 0;
  if ( pclsidHandler )
  {
    rclsid = *pclsidHandler;
  }
  else
  {
    result = AVIStreamInfoW(ppsSource, &psi, 204);
    if ( result < 0 )
      return result;
    StringCchPrintfW(SubKey, 0x64u, L"AVIFile\\Compressors\\%.4hs", &psi);
    cbData = 200;
    RegQueryValueW(HKEY_CLASSES_ROOT, SubKey, Data, &cbData);
    if ( !(unsigned int)GUIDFromString(Data, &rclsid) )
      return -2147205019;
  }
  result = CoCreateInstance(&rclsid, 0, 3u, &IID_IAVIStream, (LPVOID *)ppsCompressed);
  if ( result >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(PAVISTREAM, PAVISTREAM, AVICOMPRESSOPTIONS *))(*ppsCompressed)->lpVtbl->Create)(
           *ppsCompressed,
           ppsSource,
           lpOptions);
    if ( v9 >= 0 )
    {
      return 0;
    }
    else
    {
      ((void (__fastcall *)(PAVISTREAM))(*ppsCompressed)->lpVtbl->Release)(*ppsCompressed);
      result = v9;
      *ppsCompressed = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007e50  push    rbp
0x180007e52  push    rbx
0x180007e53  push    rsi
0x180007e54  push    rdi
0x180007e55  push    r14
0x180007e57  lea     rbp, [rsp-1D0h]
0x180007e5f  sub     rsp, 2D0h
0x180007e66  mov     rax, cs:__security_cookie
0x180007e6d  xor     rax, rsp
0x180007e70  mov     [rbp+1F0h+var_30], rax
0x180007e77  mov     r14, r8
0x180007e7a  mov     rsi, rdx
0x180007e7d  mov     rbx, rcx
0x180007e80  xorps   xmm0, xmm0
0x180007e83  xor     edx, edx; Val
0x180007e85  lea     rcx, [rbp+1F0h+Data]; void *
0x180007e89  mov     r8d, 0C8h; Size
0x180007e8f  mov     rdi, r9
0x180007e92  movups  xmmword ptr [rsp+2F0h+rclsid.Data1], xmm0
0x180007e97  call    memset_0
0x180007e9c  xor     edx, edx; Val
0x180007e9e  mov     [rsp+2F0h+cbData], 0
0x180007ea6  mov     r8d, 0CCh; Size
0x180007eac  lea     rcx, [rsp+2F0h+psi]; void *
0x180007eb1  call    memset_0
0x180007eb6  mov     qword ptr [rbx], 0
0x180007ebd  test    rdi, rdi
0x180007ec0  jz      short loc_180007F29
0x180007ec2  movups  xmm0, xmmword ptr [rdi]
0x180007ec5  movdqu  xmmword ptr [rsp+2F0h+rclsid.Data1], xmm0
0x180007ecb  xor     edx, edx; pUnkOuter
0x180007ecd  mov     [rsp+2F0h+ppv], rbx; ppv
0x180007ed2  lea     r9, IID_IAVIStream; riid
0x180007ed9  lea     rcx, [rsp+2F0h+rclsid]; rclsid
0x180007ede  lea     r8d, [rdx+3]; dwClsContext
0x180007ee2  call    cs:__imp_CoCreateInstance
0x180007ee8  test    eax, eax
0x180007eea  js      loc_180007FA1
0x180007ef0  mov     rcx, [rbx]
0x180007ef3  mov     r8, r14
0x180007ef6  mov     rdx, rsi
0x180007ef9  mov     rax, [rcx]
0x180007efc  mov     rax, [rax+18h]
0x180007f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f05  mov     edi, eax
0x180007f07  test    eax, eax
0x180007f09  jns     loc_180007F9F
0x180007f0f  mov     rcx, [rbx]
0x180007f12  mov     rdx, [rcx]
0x180007f15  mov     rax, [rdx+10h]
0x180007f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1e  mov     eax, edi
0x180007f20  mov     qword ptr [rbx], 0
0x180007f27  jmp     short loc_180007FA1
0x180007f29  mov     r8d, 0CCh; lSize
0x180007f2f  lea     rdx, [rsp+2F0h+psi]; psi
0x180007f34  mov     rcx, rsi; pavi
0x180007f37  call    AVIStreamInfoW
0x180007f3c  test    eax, eax
0x180007f3e  js      short loc_180007FA1
0x180007f40  lea     r9, [rsp+2F0h+psi]
0x180007f45  mov     edx, 64h ; 'd'; unsigned __int64
0x180007f4a  lea     r8, aAvifileCompres; "AVIFile\\Compressors\\%.4hs"
0x180007f51  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180007f58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007f5d  lea     r9, [rsp+2F0h+cbData]; lpcbData
0x180007f62  mov     [rsp+2F0h+cbData], 0C8h
0x180007f6a  lea     r8, [rbp+1F0h+Data]; lpData
0x180007f6e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007f75  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180007f7c  call    cs:__imp_RegQueryValueW
0x180007f82  lea     rdx, [rsp+2F0h+rclsid]
0x180007f87  lea     rcx, [rbp+1F0h+Data]
0x180007f8b  call    GUIDFromString
0x180007f90  test    eax, eax
0x180007f92  jnz     loc_180007ECB
0x180007f98  mov     eax, 80044065h
0x180007f9d  jmp     short loc_180007FA1
0x180007f9f  xor     eax, eax
0x180007fa1  mov     rcx, [rbp+1F0h+var_30]
0x180007fa8  xor     rcx, rsp; StackCookie
0x180007fab  call    __security_check_cookie
0x180007fb0  add     rsp, 2D0h
0x180007fb7  pop     r14
0x180007fb9  pop     rdi
0x180007fba  pop     rsi
0x180007fbb  pop     rbx
0x180007fbc  pop     rbp
0x180007fbd  retn
```

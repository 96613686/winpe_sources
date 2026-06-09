# SaveAuthenticatorAaguidToRegistry

- ea: `0x1800501cc`
- end: `0x180050310`
- name: `SaveAuthenticatorAaguidToRegistry`
- size: `324`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010f334`
- `0x18011a3cc`

## callees

- `0x18001687c`
- `0x18001cd78`
- `0x1800328b8`
- `0x180036da4`
- `0x18003c234`
- `0x1800501cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800502fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800502fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800502c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800502c4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005026e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005026e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800502ea`

## string_xrefs

- `0x180050233`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18005027e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
__int64 __fastcall SaveAuthenticatorAaguidToRegistry(HKEY hKey, int a2, int a3, LPOLESTR *a4)
{
  unsigned int InfoResponse; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  HLOCAL v10; // rcx
  HRESULT v12; // eax
  __int64 v13; // rax
  HLOCAL v14; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  HLOCAL hMem; // [rsp+30h] [rbp-30h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h] BYREF
  char v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v20 = 1;
  p_hMem = &hMem;
  hMem = 0;
  v19 = 0;
  InfoResponse = CtapCborDecodeGetInfoResponse(a2, a3, (unsigned int)&v19, 0, 0);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v7 = CtapCborErrorToWin32Error(InfoResponse);
  if ( v7 )
  {
    v8 = 268;
LABEL_3:
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
           (const char *)v7,
           lpData);
LABEL_4:
    v10 = hMem;
    hMem = 0;
    if ( v10 )
      LocalFree(v10);
    return v9;
  }
  lpsz = 0;
  v12 = StringFromCLSID((const IID *const)((char *)hMem + 36), &lpsz);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v12,
      lpData);
    goto LABEL_4;
  }
  v13 = -1;
  do
    ++v13;
  while ( lpsz[v13] );
  v7 = RegSetValueExW(hKey, L"AaGuid", 0, 1u, (const BYTE *)lpsz, 2 * v13);
  if ( v7 )
  {
    v8 = 274;
    goto LABEL_3;
  }
  if ( a4 )
    *a4 = lpsz;
  else
    CoTaskMemFree(lpsz);
  v14 = hMem;
  hMem = 0;
  if ( v14 )
    LocalFree(v14);
  return 0;
}

```

## disassembly

```asm
0x1800501cc  push    rbp
0x1800501ce  push    rbx
0x1800501cf  push    rsi
0x1800501d0  push    rdi
0x1800501d1  push    r14
0x1800501d3  mov     rbp, rsp
0x1800501d6  sub     rsp, 60h
0x1800501da  mov     rsi, rcx
0x1800501dd  mov     [rbp+var_10], 1
0x1800501e1  lea     rcx, [rbp+hMem]
0x1800501e5  mov     rax, r8
0x1800501e8  mov     r10d, edx
0x1800501eb  mov     [rbp+var_20], rcx
0x1800501ef  xor     r14d, r14d
0x1800501f2  lea     r8, [rbp+var_18]
0x1800501f6  mov     rdi, r9
0x1800501f9  mov     [rbp+hMem], r14
0x1800501fd  mov     ecx, r10d
0x180050200  mov     [rbp+var_18], r14
0x180050204  xor     r9d, r9d
0x180050207  mov     [rsp+60h+lpData], r14; int
0x18005020c  mov     rdx, rax
0x18005020f  call    CtapCborDecodeGetInfoResponse
0x180050214  lea     rcx, [rbp+var_20]
0x180050218  mov     ebx, eax
0x18005021a  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18005021f  mov     ecx, ebx
0x180050221  call    CtapCborErrorToWin32Error
0x180050226  test    eax, eax
0x180050228  jz      short loc_18005025E
0x18005022a  mov     edx, 10Ch; void *
0x18005022f  mov     rcx, [rbp+28h]; this
0x180050233  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18005023a  mov     r9d, eax; char *
0x18005023d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180050242  mov     ebx, eax
0x180050244  mov     rcx, [rbp+hMem]; hMem
0x180050248  mov     [rbp+hMem], r14
0x18005024c  test    rcx, rcx
0x18005024f  jz      short loc_180050257
0x180050251  call    cs:__imp_LocalFree
0x180050257  mov     eax, ebx
0x180050259  jmp     loc_180050305
0x18005025e  mov     rcx, [rbp+hMem]
0x180050262  lea     rdx, [rbp+lpsz]; lplpsz
0x180050266  add     rcx, 24h ; '$'; rclsid
0x18005026a  mov     [rbp+lpsz], r14
0x18005026e  call    cs:__imp_StringFromCLSID
0x180050274  mov     ebx, eax
0x180050276  test    eax, eax
0x180050278  jns     short loc_180050294
0x18005027a  mov     rcx, [rbp+28h]; this
0x18005027e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180050285  mov     r9d, eax; char *
0x180050288  mov     edx, 10Fh; void *
0x18005028d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050292  jmp     short loc_180050244
0x180050294  mov     rcx, [rbp+lpsz]
0x180050298  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005029c  inc     rax
0x18005029f  cmp     [rcx+rax*2], r14w
0x1800502a4  jnz     short loc_18005029C
0x1800502a6  add     eax, eax
0x1800502a8  lea     rdx, aAaguid; "AaGuid"
0x1800502af  mov     [rsp+60h+cbData], eax; cbData
0x1800502b3  mov     r9d, 1; dwType
0x1800502b9  mov     [rsp+60h+lpData], rcx; lpData
0x1800502be  xor     r8d, r8d; Reserved
0x1800502c1  mov     rcx, rsi; hKey
0x1800502c4  call    cs:__imp_RegSetValueExW
0x1800502ca  test    eax, eax
0x1800502cc  jz      short loc_1800502D8
0x1800502ce  mov     edx, 112h
0x1800502d3  jmp     loc_18005022F
0x1800502d8  test    rdi, rdi
0x1800502db  jz      short loc_1800502E6
0x1800502dd  mov     rax, [rbp+lpsz]
0x1800502e1  mov     [rdi], rax
0x1800502e4  jmp     short loc_1800502F0
0x1800502e6  mov     rcx, [rbp+lpsz]; pv
0x1800502ea  call    cs:__imp_CoTaskMemFree
0x1800502f0  mov     rcx, [rbp+hMem]; hMem
0x1800502f4  mov     [rbp+hMem], r14
0x1800502f8  test    rcx, rcx
0x1800502fb  jz      short loc_180050303
0x1800502fd  call    cs:__imp_LocalFree
0x180050303  xor     eax, eax
0x180050305  add     rsp, 60h
0x180050309  pop     r14
0x18005030b  pop     rdi
0x18005030c  pop     rsi
0x18005030d  pop     rbx
0x18005030e  pop     rbp
0x18005030f  retn
```

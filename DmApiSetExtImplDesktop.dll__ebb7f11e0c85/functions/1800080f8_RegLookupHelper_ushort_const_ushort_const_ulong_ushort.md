# RegLookupHelper(ushort const *,ushort const *,ulong,ushort *)

- ea: `0x1800080f8`
- end: `0x180008288`
- name: `?RegLookupHelper@@YAJPEBG0KPEAG@Z`
- size: `400`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int, unsigned __int16 *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008020`
- `0x1800085a0`
- `0x1800085c0`
- `0x180008610`
- `0x180008660`
- `0x1800088c0`
- `0x1800088e0`
- `0x180008d80`
- `0x180008df0`
- `0x1800092d0`
- `0x180009340`

## callees

- `0x180002e60`
- `0x180003140`
- `0x180005384`
- `0x180007fd8`
- `0x1800080f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008200`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000818d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000818d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008162`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800081d9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008162`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800081d9`
- `dmxmlhelputils!XMLHEscapeString` at `0x180008228`
- `dmxmlhelputils!XMLHEscapeString` at `0x180008228`

## pseudocode

```c
__int64 __fastcall RegLookupHelper(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int a3, unsigned __int16 *a4)
{
  unsigned __int64 v5; // r14
  LSTATUS ValueW; // eax
  signed int v9; // ebx
  bool v10; // cc
  HLOCAL pvData; // rdi
  HLOCAL v12; // rbx
  DWORD pcbData; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-1Ch] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL v17; // [rsp+50h] [rbp-10h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-8h] BYREF

  v5 = a3;
  hMem = 0;
  v17 = 0;
  v15 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 2u, 0, 0, &pcbData);
  v9 = ValueW;
  v10 = ValueW <= 0;
  if ( ValueW )
  {
LABEL_2:
    if ( !v10 )
      v9 = (unsigned __int16)ValueW | 0x80070000;
LABEL_12:
    if ( v9 >= 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
  pvData = LocalAlloc(0, pcbData);
  v17 = pvData;
  if ( !pvData )
    goto LABEL_5;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 2u, 0, pvData, &pcbData);
  v9 = ValueW;
  v10 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_2;
  v12 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    LocalFree(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  hMem = 0;
  v9 = XMLHEscapeString((const unsigned __int16 *)pvData, (unsigned __int16 **)&hMem, &v15);
  if ( v9 >= 0 )
  {
    if ( v15 <= (unsigned int)v5 )
    {
      v9 = StringCchCopyW(a4, v5, (const unsigned __int16 *)hMem);
      goto LABEL_12;
    }
LABEL_5:
    v9 = -2147024882;
  }
LABEL_13:
  if ( a4 )
    *a4 = 0;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800080f8  push    rbp
0x1800080fa  push    rbx
0x1800080fb  push    rsi
0x1800080fc  push    rdi
0x1800080fd  push    r12
0x1800080ff  push    r14
0x180008101  push    r15
0x180008103  mov     rbp, rsp
0x180008106  sub     rsp, 60h
0x18000810a  mov     rsi, r9
0x18000810d  mov     r14d, r8d
0x180008110  mov     r15, rdx
0x180008113  mov     r12, rcx
0x180008116  mov     [rbp+hMem], 0
0x18000811e  mov     [rbp+var_10], 0
0x180008126  mov     [rbp+var_1C], 0
0x18000812d  mov     [rbp+var_20], 0
0x180008134  lea     rax, [rbp+var_20]
0x180008138  mov     [rsp+60h+pcbData], rax; pcbData
0x18000813d  mov     [rsp+60h+pvData], 0; pvData
0x180008146  mov     [rsp+60h+pdwType], 0; pdwType
0x18000814f  mov     r9d, 2; dwFlags
0x180008155  mov     r8, rdx; lpValue
0x180008158  mov     rdx, rcx; lpSubKey
0x18000815b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008162  call    cs:__imp_RegGetValueW
0x180008169  nop     dword ptr [rax+rax+00h]
0x18000816e  mov     ebx, eax
0x180008170  test    eax, eax
0x180008172  jz      short loc_180008188
0x180008174  jle     loc_180008255
0x18000817a  movzx   ebx, ax
0x18000817d  or      ebx, 80070000h
0x180008183  jmp     loc_180008255
0x180008188  mov     edx, [rbp+var_20]; uBytes
0x18000818b  xor     ecx, ecx; uFlags
0x18000818d  call    cs:__imp_LocalAlloc
0x180008194  nop     dword ptr [rax+rax+00h]
0x180008199  mov     rdi, rax
0x18000819c  mov     [rbp+var_10], rax
0x1800081a0  test    rax, rax
0x1800081a3  jnz     short loc_1800081AF
0x1800081a5  mov     ebx, 8007000Eh
0x1800081aa  jmp     loc_180008259
0x1800081af  lea     rax, [rbp+var_20]
0x1800081b3  mov     [rsp+60h+pcbData], rax; pcbData
0x1800081b8  mov     [rsp+60h+pvData], rdi; pvData
0x1800081bd  mov     [rsp+60h+pdwType], 0; pdwType
0x1800081c6  mov     r9d, 2; dwFlags
0x1800081cc  mov     r8, r15; lpValue
0x1800081cf  mov     rdx, r12; lpSubKey
0x1800081d2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800081d9  call    cs:__imp_RegGetValueW
0x1800081e0  nop     dword ptr [rax+rax+00h]
0x1800081e5  mov     ebx, eax
0x1800081e7  test    eax, eax
0x1800081e9  jnz     short loc_180008174
0x1800081eb  mov     rbx, [rbp+hMem]
0x1800081ef  test    rbx, rbx
0x1800081f2  jz      short loc_180008215
0x1800081f4  lea     rcx, [rbp+var_8]; this
0x1800081f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800081fd  mov     rcx, rbx; hMem
0x180008200  call    cs:__imp_LocalFree
0x180008207  nop     dword ptr [rax+rax+00h]
0x18000820c  lea     rcx, [rbp+var_8]; this
0x180008210  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008215  mov     [rbp+hMem], 0
0x18000821d  lea     r8, [rbp+var_1C]
0x180008221  lea     rdx, [rbp+hMem]
0x180008225  mov     rcx, rdi
0x180008228  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x18000822f  nop     dword ptr [rax+rax+00h]
0x180008234  mov     ebx, eax
0x180008236  test    eax, eax
0x180008238  js      short loc_180008259
0x18000823a  cmp     [rbp+var_1C], r14d
0x18000823e  ja      loc_1800081A5
0x180008244  mov     rdx, r14; unsigned __int64
0x180008247  mov     r8, [rbp+hMem]; unsigned __int16 *
0x18000824b  mov     rcx, rsi; unsigned __int16 *
0x18000824e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008253  mov     ebx, eax
0x180008255  test    ebx, ebx
0x180008257  jns     short loc_180008263
0x180008259  test    rsi, rsi
0x18000825c  jz      short loc_180008263
0x18000825e  xor     eax, eax
0x180008260  mov     [rsi], ax
0x180008263  lea     rcx, [rbp+var_10]
0x180008267  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000826c  nop
0x18000826d  lea     rcx, [rbp+hMem]
0x180008271  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008276  mov     eax, ebx
0x180008278  add     rsp, 60h
0x18000827c  pop     r15
0x18000827e  pop     r14
0x180008280  pop     r12
0x180008282  pop     rdi
0x180008283  pop     rsi
0x180008284  pop     rbx
0x180008285  pop     rbp
0x180008286  retn
```

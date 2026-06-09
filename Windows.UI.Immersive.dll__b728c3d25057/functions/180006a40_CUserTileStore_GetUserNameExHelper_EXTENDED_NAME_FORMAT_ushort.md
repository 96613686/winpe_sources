# CUserTileStore::_GetUserNameExHelper(EXTENDED_NAME_FORMAT,ushort * *)

- ea: `0x180006a40`
- end: `0x180006b36`
- name: `?_GetUserNameExHelper@CUserTileStore@@AEAAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z`
- size: `246`
- prototype: `int(CUserTileStore *__hidden this, enum EXTENDED_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c2d50`

## callees

- `0x1800064d4`
- `0x180006a40`
- `0x18003aa84`
- `0x180051524`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b23`
- `SspiCli!GetUserNameExW` at `0x180006a6c`
- `SspiCli!GetUserNameExW` at `0x180006afb`
- `SspiCli!GetUserNameExW` at `0x180006a6c`
- `SspiCli!GetUserNameExW` at `0x180006afb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserTileStore::_GetUserNameExHelper(
        CUserTileStore *this,
        enum EXTENDED_NAME_FORMAT a2,
        unsigned __int16 **a3)
{
  int Error; // edi
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  size_t v9; // rax
  ULONG nSize; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  unsigned __int16 *v13; // [rsp+60h] [rbp+18h]

  v12 = HIDWORD(this);
  *a3 = 0;
  nSize = 0;
  if ( !GetUserNameExW(a2, 0, &nSize) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147024662 )
      return (unsigned int)Error;
    v13 = 0;
    CoTaskMemFree(0);
    v6 = 0;
    v13 = 0;
    if ( !is_mul_ok(nSize, 2u) )
    {
      Error = -2147024362;
      goto LABEL_14;
    }
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * nSize);
    v8 = v7;
    v6 = v7;
    v13 = v7;
    if ( v7 )
    {
      v9 = CTCoAllocPolicy::_CoTaskMemSize(v7);
      memset_0(v6, 0, v9);
      Error = 0;
    }
    else
    {
      Error = -2147024882;
    }
    if ( Error < 0 )
      goto LABEL_14;
    if ( GetUserNameExW(a2, v6, &nSize) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_14:
        CoTaskMemFree(v6);
        return (unsigned int)Error;
      }
    }
    v6 = 0;
    *a3 = v8;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180006a40  mov     qword ptr [rsp+nSize], rcx
0x180006a45  push    rbx
0x180006a46  push    rbp
0x180006a47  push    rsi
0x180006a48  push    rdi
0x180006a49  push    r14
0x180006a4b  sub     rsp, 20h
0x180006a4f  mov     r14, r8
0x180006a52  mov     ebp, edx
0x180006a54  mov     qword ptr [r8], 0
0x180006a5b  mov     [rsp+48h+nSize], 0
0x180006a63  lea     r8, [rsp+48h+nSize]; nSize
0x180006a68  xor     edx, edx; lpNameBuffer
0x180006a6a  mov     ecx, ebp; NameFormat
0x180006a6c  call    cs:__imp_GetUserNameExW
0x180006a72  test    al, al
0x180006a74  jz      short loc_180006A7D
0x180006a76  xor     edi, edi
0x180006a78  jmp     loc_180006B29
0x180006a7d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006a82  mov     edi, eax
0x180006a84  cmp     eax, 800700EAh
0x180006a89  jnz     loc_180006B29
0x180006a8f  mov     [rsp+48h+arg_10], 0
0x180006a98  xor     ecx, ecx; pv
0x180006a9a  call    cs:__imp_CoTaskMemFree
0x180006aa0  xor     ebx, ebx
0x180006aa2  mov     [rsp+48h+arg_10], rbx
0x180006aa7  mov     ecx, [rsp+48h+nSize]
0x180006aab  lea     eax, [rbx+2]
0x180006aae  mul     rcx
0x180006ab1  test    rdx, rdx
0x180006ab4  jnz     short loc_180006B1B
0x180006ab6  mov     rcx, rax; cb
0x180006ab9  call    cs:__imp_CoTaskMemAlloc
0x180006abf  mov     rsi, rax
0x180006ac2  mov     rbx, rax
0x180006ac5  mov     [rsp+48h+arg_10], rax
0x180006aca  test    rax, rax
0x180006acd  jz      short loc_180006AE8
0x180006acf  mov     rcx, rax; void *
0x180006ad2  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180006ad7  mov     r8, rax; Size
0x180006ada  xor     edx, edx; Val
0x180006adc  mov     rcx, rbx; void *
0x180006adf  call    memset_0
0x180006ae4  xor     edi, edi
0x180006ae6  jmp     short loc_180006AED
0x180006ae8  mov     edi, 8007000Eh
0x180006aed  test    edi, edi
0x180006aef  js      short loc_180006B20
0x180006af1  lea     r8, [rsp+48h+nSize]; nSize
0x180006af6  mov     rdx, rbx; lpNameBuffer
0x180006af9  mov     ecx, ebp; NameFormat
0x180006afb  call    cs:__imp_GetUserNameExW
0x180006b01  test    al, al
0x180006b03  jz      short loc_180006B09
0x180006b05  xor     edi, edi
0x180006b07  jmp     short loc_180006B14
0x180006b09  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006b0e  mov     edi, eax
0x180006b10  test    eax, eax
0x180006b12  js      short loc_180006B20
0x180006b14  xor     ebx, ebx
0x180006b16  mov     [r14], rsi
0x180006b19  jmp     short loc_180006B20
0x180006b1b  mov     edi, 80070216h
0x180006b20  mov     rcx, rbx; pv
0x180006b23  call    cs:__imp_CoTaskMemFree
0x180006b29  mov     eax, edi
0x180006b2b  add     rsp, 20h
0x180006b2f  pop     r14
0x180006b31  pop     rdi
0x180006b32  pop     rsi
0x180006b33  pop     rbp
0x180006b34  pop     rbx
0x180006b35  retn
```

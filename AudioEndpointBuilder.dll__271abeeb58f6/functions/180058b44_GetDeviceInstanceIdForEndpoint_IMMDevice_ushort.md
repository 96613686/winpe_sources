# GetDeviceInstanceIdForEndpoint(IMMDevice *,ushort * *)

- ea: `0x180058b44`
- end: `0x180058c63`
- name: `?GetDeviceInstanceIdForEndpoint@@YAJPEAUIMMDevice@@PEAPEAG@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct IMMDevice *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180031920`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x18001f230`
- `0x180058b44`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058bd5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c4f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180058c4f`

## string_xrefs

- `0x180058bf0`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
__int64 __fastcall GetDeviceInstanceIdForEndpoint(struct IMMDevice *a1, unsigned __int16 **a2)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  SIZE_T v9; // rbx
  unsigned __int16 *v10; // rax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v15; // [rsp+70h] [rbp+28h] BYREF

  *(_OWORD *)pvar = 0;
  v13 = 0;
  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v15 = 0;
  v4 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a1, 0, &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 168;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)v6,
      (int)pvar[0]);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    PropVariantClear(pvar);
    return v5;
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v15 + 40LL))(
         v15,
         PKEY_SWD_DeviceInstanceId_Retained,
         pvar) >= 0
    && LOWORD(pvar[0]) == 31 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)pvar[1] + v8) );
    v9 = 2 * v8 + 2;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(v9);
    *a2 = v10;
    if ( !v10 )
    {
      v5 = -2147024882;
      v6 = 2147942414LL;
      v7 = 179;
      goto LABEL_9;
    }
    StringCbCopyW(v10, v9, (const unsigned __int16 *)pvar[1]);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    PropVariantClear(pvar);
    return 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    PropVariantClear(pvar);
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180058b44  push    rbp
0x180058b46  push    rbx
0x180058b47  push    rsi
0x180058b48  push    rdi
0x180058b49  mov     rbp, rsp
0x180058b4c  sub     rsp, 48h
0x180058b50  mov     rdi, rdx
0x180058b53  xorps   xmm0, xmm0
0x180058b56  xor     eax, eax
0x180058b58  movups  xmmword ptr [rbp+pvar], xmm0
0x180058b5c  mov     [rbp+var_18], rax
0x180058b60  xor     esi, esi
0x180058b62  mov     [rdx], rsi
0x180058b65  mov     rax, [rcx]
0x180058b68  mov     [rbp+arg_0], rsi
0x180058b6c  lea     r8, [rbp+arg_0]
0x180058b70  xor     edx, edx
0x180058b72  mov     rax, [rax+20h]
0x180058b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b7b  mov     ebx, eax
0x180058b7d  test    eax, eax
0x180058b7f  jns     short loc_180058B8B
0x180058b81  mov     r9d, eax
0x180058b84  mov     edx, 0A8h
0x180058b89  jmp     short loc_180058BF0
0x180058b8b  mov     rcx, [rbp+arg_0]
0x180058b8f  mov     rax, [rcx]
0x180058b92  lea     r8, [rbp+pvar]
0x180058b96  lea     rdx, PKEY_SWD_DeviceInstanceId_Retained
0x180058b9d  mov     rax, [rax+28h]
0x180058ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ba6  test    eax, eax
0x180058ba8  js      loc_180058C41
0x180058bae  cmp     word ptr [rbp+pvar], 1Fh
0x180058bb3  jnz     loc_180058C41
0x180058bb9  mov     rcx, [rbp+pvar+8]
0x180058bbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058bc1  inc     rax
0x180058bc4  cmp     [rcx+rax*2], si
0x180058bc8  jnz     short loc_180058BC1
0x180058bca  lea     rbx, ds:2[rax*2]
0x180058bd2  mov     rcx, rbx; cb
0x180058bd5  call    cs:__imp_CoTaskMemAlloc
0x180058bdb  mov     [rdi], rax
0x180058bde  test    rax, rax
0x180058be1  jnz     short loc_180058C19
0x180058be3  mov     ebx, 8007000Eh
0x180058be8  mov     r9d, ebx; char *
0x180058beb  mov     edx, 0B3h; void *
0x180058bf0  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180058bf7  mov     rcx, [rbp+20h]; this
0x180058bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058c00  nop
0x180058c01  lea     rcx, [rbp+arg_0]
0x180058c05  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180058c0a  nop
0x180058c0b  lea     rcx, [rbp+pvar]; pvar
0x180058c0f  call    cs:__imp_PropVariantClear
0x180058c15  mov     eax, ebx
0x180058c17  jmp     short loc_180058C5A
0x180058c19  mov     r8, [rbp+pvar+8]; unsigned __int16 *
0x180058c1d  mov     rdx, rbx; unsigned __int64
0x180058c20  mov     rcx, rax; unsigned __int16 *
0x180058c23  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180058c28  nop
0x180058c29  lea     rcx, [rbp+arg_0]
0x180058c2d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180058c32  nop
0x180058c33  lea     rcx, [rbp+pvar]; pvar
0x180058c37  call    cs:__imp_PropVariantClear
0x180058c3d  xor     eax, eax
0x180058c3f  jmp     short loc_180058C5A
0x180058c41  lea     rcx, [rbp+arg_0]
0x180058c45  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180058c4a  nop
0x180058c4b  lea     rcx, [rbp+pvar]; pvar
0x180058c4f  call    cs:__imp_PropVariantClear
0x180058c55  mov     eax, 80070490h
0x180058c5a  add     rsp, 48h
0x180058c5e  pop     rdi
0x180058c5f  pop     rsi
0x180058c60  pop     rbx
0x180058c61  pop     rbp
0x180058c62  retn
```

# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180071d80`
- end: `0x180071e2a`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180070e84`

## callees

- `0x18004d0b4`
- `0x180071d80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071d95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071d95`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180071e17`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180071e17`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071dcb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071dcb`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rax
  unsigned int AgileReference; // ebx
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v9 = 0;
    AgileReference = 0;
    v13 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180071d80  push    rbx
0x180071d82  push    rbp
0x180071d83  push    rsi
0x180071d84  push    rdi
0x180071d85  sub     rsp, 38h
0x180071d89  mov     ebx, r9d
0x180071d8c  mov     rsi, r8
0x180071d8f  mov     rbp, rdx
0x180071d92  mov     rdi, rcx
0x180071d95  call    cs:__imp_GetCurrentThreadId
0x180071d9b  mov     [rdi+18h], ebx
0x180071d9e  mov     [rdi+28h], eax
0x180071da1  cmp     ebx, 2
0x180071da4  jnz     short loc_180071E04
0x180071da6  xor     eax, eax
0x180071da8  xor     ebx, ebx
0x180071daa  mov     [rsp+58h+arg_0], rax
0x180071daf  test    rsi, rsi
0x180071db2  jz      short loc_180071DD8
0x180071db4  lea     rcx, [rsp+58h+arg_0]
0x180071db9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071dbe  lea     r9, [rsp+58h+arg_0]
0x180071dc3  mov     r8, rsi
0x180071dc6  mov     rdx, rbp
0x180071dc9  xor     ecx, ecx
0x180071dcb  call    cs:__imp_RoGetAgileReference
0x180071dd1  mov     ebx, eax
0x180071dd3  mov     rax, [rsp+58h+arg_0]
0x180071dd8  mov     rcx, [rdi+20h]
0x180071ddc  mov     [rsp+58h+var_38], rcx
0x180071de1  lea     rcx, [rsp+58h+var_38]
0x180071de6  mov     [rsp+58h+arg_0], 0
0x180071def  mov     [rdi+20h], rax
0x180071df3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071df8  lea     rcx, [rsp+58h+arg_0]
0x180071dfd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071e02  jmp     short loc_180071E1F
0x180071e04  lea     rcx, [rdi+10h]
0x180071e08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071e0d  lea     r8, [rdi+10h]; ppStm
0x180071e11  mov     rdx, rsi; pUnk
0x180071e14  mov     rcx, rbp; riid
0x180071e17  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180071e1d  mov     ebx, eax
0x180071e1f  mov     eax, ebx
0x180071e21  add     rsp, 38h
0x180071e25  pop     rdi
0x180071e26  pop     rsi
0x180071e27  pop     rbp
0x180071e28  pop     rbx
0x180071e29  retn
```

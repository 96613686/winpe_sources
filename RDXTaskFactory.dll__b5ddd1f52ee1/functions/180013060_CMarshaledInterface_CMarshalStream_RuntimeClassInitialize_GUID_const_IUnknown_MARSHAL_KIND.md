# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180013060`
- end: `0x18001310a`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012120`

## callees

- `0x180008bbc`
- `0x180013060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013075`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800130f7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800130f7`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800130ab`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800130ab`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int AgileReference; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  _QWORD v16[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v11 = 0;
    AgileReference = 0;
    v17 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17, v9, v10);
      AgileReference = RoGetAgileReference(0, a2, a3, &v17);
      v11 = v17;
    }
    v16[0] = *(_QWORD *)(a1 + 32);
    v17 = 0;
    *(_QWORD *)(a1 + 32) = v11;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16, v9, v10);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17, v13, v14);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 16, v9, v10);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180013060  push    rbx
0x180013062  push    rbp
0x180013063  push    rsi
0x180013064  push    rdi
0x180013065  sub     rsp, 38h
0x180013069  mov     ebx, r9d
0x18001306c  mov     rsi, r8
0x18001306f  mov     rbp, rdx
0x180013072  mov     rdi, rcx
0x180013075  call    cs:__imp_GetCurrentThreadId
0x18001307b  mov     [rdi+18h], ebx
0x18001307e  mov     [rdi+28h], eax
0x180013081  cmp     ebx, 2
0x180013084  jnz     short loc_1800130E4
0x180013086  xor     eax, eax
0x180013088  xor     ebx, ebx
0x18001308a  mov     [rsp+58h+arg_0], rax
0x18001308f  test    rsi, rsi
0x180013092  jz      short loc_1800130B8
0x180013094  lea     rcx, [rsp+58h+arg_0]
0x180013099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001309e  lea     r9, [rsp+58h+arg_0]
0x1800130a3  mov     r8, rsi
0x1800130a6  mov     rdx, rbp
0x1800130a9  xor     ecx, ecx
0x1800130ab  call    cs:__imp_RoGetAgileReference
0x1800130b1  mov     ebx, eax
0x1800130b3  mov     rax, [rsp+58h+arg_0]
0x1800130b8  mov     rcx, [rdi+20h]
0x1800130bc  mov     [rsp+58h+var_38], rcx
0x1800130c1  lea     rcx, [rsp+58h+var_38]
0x1800130c6  mov     [rsp+58h+arg_0], 0
0x1800130cf  mov     [rdi+20h], rax
0x1800130d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800130d8  lea     rcx, [rsp+58h+arg_0]
0x1800130dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800130e2  jmp     short loc_1800130FF
0x1800130e4  lea     rcx, [rdi+10h]
0x1800130e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800130ed  lea     r8, [rdi+10h]; ppStm
0x1800130f1  mov     rdx, rsi; pUnk
0x1800130f4  mov     rcx, rbp; riid
0x1800130f7  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800130fd  mov     ebx, eax
0x1800130ff  mov     eax, ebx
0x180013101  add     rsp, 38h
0x180013105  pop     rdi
0x180013106  pop     rsi
0x180013107  pop     rbp
0x180013108  pop     rbx
0x180013109  retn
```

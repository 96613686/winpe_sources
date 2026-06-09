# IWICDevelopRaw_GetToneCurve_Proxy

- ea: `0x1800d8610`
- end: `0x1800d8728`
- name: `IWICDevelopRaw_GetToneCurve_Proxy`
- size: `280`
- prototype: `HRESULT __stdcall(IWICDevelopRaw *This, UINT cbToneCurveBufferSize, WICRawToneCurve *pToneCurve, UINT *pcbActualToneCurveBufferSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bb784`
- `0x1800d8610`
- `0x1800d87d0`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d870d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d870d`
- `RPCRT4!NdrClientCall2` at `0x1800d8683`
- `RPCRT4!NdrClientCall2` at `0x1800d8683`

## pseudocode

```c
HRESULT __stdcall IWICDevelopRaw_GetToneCurve_Proxy(
        IWICDevelopRaw *This,
        UINT cbToneCurveBufferSize,
        WICRawToneCurve *pToneCurve,
        UINT *pcbActualToneCurveBufferSize)
{
  bool v7; // zf
  HRESULT v8; // ebx
  int v9; // ecx
  int Pointer; // eax
  int ToneCurveSize; // eax
  int v12; // ecx
  HRESULT v13; // edi
  UINT v14; // eax
  void *v15; // rdx
  size_t v16; // r8
  UINT v18; // [rsp+30h] [rbp-28h] BYREF
  void *Src; // [rsp+38h] [rbp-20h] BYREF
  UINT v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = 0;
  Src = 0;
  v18 = 0;
  if ( !This )
  {
    v7 = (_DWORD)g_doStackCaptures == 0;
    v8 = -2147024809;
    goto LABEL_3;
  }
  Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_1801FAC9A, This, &v20, &Src).Pointer;
  v8 = Pointer;
  if ( Pointer < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_19;
    v9 = Pointer;
    goto LABEL_5;
  }
  ToneCurveSize = GetToneCurveSize(v20, &v18);
  v12 = (int)g_doStackCaptures;
  v13 = ToneCurveSize;
  if ( ToneCurveSize < 0 && (_DWORD)g_doStackCaptures )
  {
    DoStackCapture(ToneCurveSize);
    v8 = v13;
    goto LABEL_19;
  }
  v8 = ToneCurveSize;
  if ( ToneCurveSize >= 0 )
  {
    v14 = v18;
    if ( pcbActualToneCurveBufferSize )
      *pcbActualToneCurveBufferSize = v18;
    if ( pToneCurve )
    {
      if ( v14 <= cbToneCurveBufferSize )
      {
        v15 = Src;
        v16 = 16LL * v20;
        pToneCurve->cPoints = v20;
        memcpy_0(pToneCurve->aPoints, v15, v16);
        goto LABEL_19;
      }
      v8 = -2003292276;
      v7 = v12 == 0;
LABEL_3:
      if ( !v7 )
      {
        v9 = v8;
LABEL_5:
        DoStackCapture(v9);
      }
    }
  }
LABEL_19:
  CoTaskMemFree(Src);
  return v8;
}

```

## disassembly

```asm
0x1800d8610  mov     rax, rsp
0x1800d8613  mov     [rax+10h], rbx
0x1800d8617  mov     [rax+18h], rbp
0x1800d861b  push    rsi
0x1800d861c  push    rdi
0x1800d861d  push    r14
0x1800d861f  sub     rsp, 40h
0x1800d8623  mov     dword ptr [rax+8], 0
0x1800d862a  mov     r14, r9
0x1800d862d  mov     qword ptr [rax-20h], 0
0x1800d8635  mov     rsi, r8
0x1800d8638  mov     dword ptr [rax-28h], 0
0x1800d863f  mov     ebp, edx
0x1800d8641  test    rcx, rcx
0x1800d8644  jnz     short loc_1800D8663
0x1800d8646  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800d864c  mov     ebx, 80070057h
0x1800d8651  jz      loc_1800D8708
0x1800d8657  mov     ecx, ebx; int
0x1800d8659  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d865e  jmp     loc_1800D8708
0x1800d8663  lea     rax, [rsp+58h+Src]
0x1800d8668  mov     r8, rcx
0x1800d866b  lea     rcx, pStubDescriptor; pStubDescriptor
0x1800d8672  mov     [rsp+58h+var_38], rax
0x1800d8677  lea     r9, [rsp+58h+arg_0]
0x1800d867c  lea     rdx, byte_1801FAC9A; pFormat
0x1800d8683  call    cs:__imp_NdrClientCall2
0x1800d8689  mov     rbx, rax
0x1800d868c  test    eax, eax
0x1800d868e  jns     short loc_1800D869D
0x1800d8690  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d8697  jz      short loc_1800D8708
0x1800d8699  mov     ecx, eax
0x1800d869b  jmp     short loc_1800D8659
0x1800d869d  mov     ecx, [rsp+58h+arg_0]
0x1800d86a1  lea     rdx, [rsp+58h+var_28]
0x1800d86a6  call    GetToneCurveSize
0x1800d86ab  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800d86b1  mov     edi, eax
0x1800d86b3  test    eax, eax
0x1800d86b5  jns     short loc_1800D86C6
0x1800d86b7  test    ecx, ecx
0x1800d86b9  jz      short loc_1800D86C6
0x1800d86bb  mov     ecx, eax; int
0x1800d86bd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d86c2  mov     ebx, edi
0x1800d86c4  jmp     short loc_1800D8708
0x1800d86c6  mov     ebx, edi
0x1800d86c8  test    edi, edi
0x1800d86ca  js      short loc_1800D8708
0x1800d86cc  mov     eax, [rsp+58h+var_28]
0x1800d86d0  test    r14, r14
0x1800d86d3  jz      short loc_1800D86D8
0x1800d86d5  mov     [r14], eax
0x1800d86d8  test    rsi, rsi
0x1800d86db  jz      short loc_1800D8708
0x1800d86dd  cmp     eax, ebp
0x1800d86df  jbe     short loc_1800D86ED
0x1800d86e1  mov     ebx, 88982F8Ch
0x1800d86e6  test    ecx, ecx
0x1800d86e8  jmp     loc_1800D8651
0x1800d86ed  mov     eax, [rsp+58h+arg_0]
0x1800d86f1  lea     rcx, [rsi+8]; void *
0x1800d86f5  mov     rdx, [rsp+58h+Src]; Src
0x1800d86fa  mov     r8d, eax
0x1800d86fd  shl     r8, 4; Size
0x1800d8701  mov     [rsi], eax
0x1800d8703  call    memcpy_0
0x1800d8708  mov     rcx, [rsp+58h+Src]; pv
0x1800d870d  call    cs:__imp_CoTaskMemFree
0x1800d8713  mov     rbp, [rsp+58h+arg_10]
0x1800d8718  mov     eax, ebx
0x1800d871a  mov     rbx, [rsp+58h+arg_8]
0x1800d871f  add     rsp, 40h
0x1800d8723  pop     r14
0x1800d8725  pop     rdi
0x1800d8726  pop     rsi
0x1800d8727  retn
```

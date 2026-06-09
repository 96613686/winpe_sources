# IWICDevelopRaw_GetToneCurve_Proxy

- ea: `0x1800db180`
- end: `0x1800db2a5`
- name: `IWICDevelopRaw_GetToneCurve_Proxy`
- size: `293`
- prototype: `HRESULT __stdcall(IWICDevelopRaw *This, UINT cbToneCurveBufferSize, WICRawToneCurve *pToneCurve, UINT *pcbActualToneCurveBufferSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x1800db180`
- `0x1800db358`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db283`
- `RPCRT4!NdrClientCall2` at `0x1800db1f3`
- `RPCRT4!NdrClientCall2` at `0x1800db1f3`

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
  Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_1801FEC0A, This, &v20, &Src).Pointer;
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
0x1800db180  mov     rax, rsp
0x1800db183  mov     [rax+10h], rbx
0x1800db187  mov     [rax+18h], rbp
0x1800db18b  push    rsi
0x1800db18c  push    rdi
0x1800db18d  push    r14
0x1800db18f  sub     rsp, 40h
0x1800db193  mov     dword ptr [rax+8], 0
0x1800db19a  mov     r14, r9
0x1800db19d  mov     qword ptr [rax-20h], 0
0x1800db1a5  mov     rsi, r8
0x1800db1a8  mov     dword ptr [rax-28h], 0
0x1800db1af  mov     ebp, edx
0x1800db1b1  test    rcx, rcx
0x1800db1b4  jnz     short loc_1800DB1D3
0x1800db1b6  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800db1bc  mov     ebx, 80070057h
0x1800db1c1  jz      loc_1800DB27E
0x1800db1c7  mov     ecx, ebx; int
0x1800db1c9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800db1ce  jmp     loc_1800DB27E
0x1800db1d3  lea     rax, [rsp+58h+Src]
0x1800db1d8  mov     r8, rcx
0x1800db1db  lea     rcx, pStubDescriptor; pStubDescriptor
0x1800db1e2  mov     [rsp+58h+var_38], rax
0x1800db1e7  lea     r9, [rsp+58h+arg_0]
0x1800db1ec  lea     rdx, byte_1801FEC0A; pFormat
0x1800db1f3  call    cs:__imp_NdrClientCall2
0x1800db1fa  nop     dword ptr [rax+rax+00h]
0x1800db1ff  mov     rbx, rax
0x1800db202  test    eax, eax
0x1800db204  jns     short loc_1800DB213
0x1800db206  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800db20d  jz      short loc_1800DB27E
0x1800db20f  mov     ecx, eax
0x1800db211  jmp     short loc_1800DB1C9
0x1800db213  mov     ecx, [rsp+58h+arg_0]
0x1800db217  lea     rdx, [rsp+58h+var_28]
0x1800db21c  call    GetToneCurveSize
0x1800db221  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800db227  mov     edi, eax
0x1800db229  test    eax, eax
0x1800db22b  jns     short loc_1800DB23C
0x1800db22d  test    ecx, ecx
0x1800db22f  jz      short loc_1800DB23C
0x1800db231  mov     ecx, eax; int
0x1800db233  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800db238  mov     ebx, edi
0x1800db23a  jmp     short loc_1800DB27E
0x1800db23c  mov     ebx, edi
0x1800db23e  test    edi, edi
0x1800db240  js      short loc_1800DB27E
0x1800db242  mov     eax, [rsp+58h+var_28]
0x1800db246  test    r14, r14
0x1800db249  jz      short loc_1800DB24E
0x1800db24b  mov     [r14], eax
0x1800db24e  test    rsi, rsi
0x1800db251  jz      short loc_1800DB27E
0x1800db253  cmp     eax, ebp
0x1800db255  jbe     short loc_1800DB263
0x1800db257  mov     ebx, 88982F8Ch
0x1800db25c  test    ecx, ecx
0x1800db25e  jmp     loc_1800DB1C1
0x1800db263  mov     eax, [rsp+58h+arg_0]
0x1800db267  lea     rcx, [rsi+8]; void *
0x1800db26b  mov     rdx, [rsp+58h+Src]; Src
0x1800db270  mov     r8d, eax
0x1800db273  shl     r8, 4; Size
0x1800db277  mov     [rsi], eax
0x1800db279  call    memcpy_0
0x1800db27e  mov     rcx, [rsp+58h+Src]; pv
0x1800db283  call    cs:__imp_CoTaskMemFree
0x1800db28a  nop     dword ptr [rax+rax+00h]
0x1800db28f  mov     rbp, [rsp+58h+arg_10]
0x1800db294  mov     eax, ebx
0x1800db296  mov     rbx, [rsp+58h+arg_8]
0x1800db29b  add     rsp, 40h
0x1800db29f  pop     r14
0x1800db2a1  pop     rdi
0x1800db2a2  pop     rsi
0x1800db2a3  retn
```

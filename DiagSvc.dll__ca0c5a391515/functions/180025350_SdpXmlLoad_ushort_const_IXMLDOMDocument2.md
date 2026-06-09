# SdpXmlLoad(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x180025350`
- end: `0x1800254f8`
- name: `?SdpXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800200f0`

## callees

- `0x180024ce8`
- `0x180025350`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800253ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800253ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18002542a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002542a`
- `OLEAUT32!__imp_VariantInit` at `0x18002538a`
- `OLEAUT32!__imp_VariantInit` at `0x18002538a`
- `OLEAUT32!__imp_VariantClear` at `0x1800254c6`
- `OLEAUT32!__imp_VariantClear` at `0x1800254c6`

## string_xrefs

- `0x1800253a6`: `SdpXmlLoad`

## pseudocode

```c
__int64 __fastcall SdpXmlLoad(OLECHAR *psz, LPVOID *a2)
{
  __int64 v4; // r9
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall *v7)(LPVOID, __int128 *, __int16 *); // rax
  LPVOID v8; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int16 v14; // [rsp+90h] [rbp+20h] BYREF
  LPVOID v15; // [rsp+A0h] [rbp+30h] BYREF

  v14 = -1;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !psz )
  {
    v4 = 256;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    LODWORD(ppv) = v5;
LABEL_5:
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlLoad", v4, ppv);
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v4 = 257;
    goto LABEL_3;
  }
  v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &v15);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 264;
    goto LABEL_4;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 504LL))(v15, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 267;
    goto LABEL_4;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    v6 = -2147024882;
    v4 = 270;
    LODWORD(ppv) = -2147024882;
    goto LABEL_5;
  }
  pRecInfo = pvarg.pRecInfo;
  pvarg.vt = 8;
  v7 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)v15 + 464LL);
  v12 = *(_OWORD *)&pvarg.vt;
  v5 = v7(v15, &v12, &v14);
  v6 = v5;
  if ( v5 < 0 )
  {
    v4 = 275;
    goto LABEL_4;
  }
  if ( !v14 )
  {
    v6 = -2147467259;
    v4 = 276;
    LODWORD(ppv) = -2147467259;
    goto LABEL_5;
  }
  v8 = v15;
  *a2 = v15;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_19:
  VariantClear(&pvarg);
  if ( v15 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  return v6;
}

```

## disassembly

```asm
0x180025350  mov     [rsp-18h+arg_8], rbx
0x180025355  mov     [rsp-18h+arg_18], rsi
0x18002535a  push    rbp
0x18002535b  push    rdi
0x18002535c  push    r14
0x18002535e  mov     rbp, rsp
0x180025361  sub     rsp, 70h
0x180025365  xor     eax, eax
0x180025367  mov     rsi, rcx
0x18002536a  mov     qword ptr [rbp+pvarg+10h], rax
0x18002536e  lea     rcx, [rbp+pvarg]; pvarg
0x180025372  or      eax, 0FFFFFFFFh
0x180025375  xorps   xmm0, xmm0
0x180025378  xor     r14d, r14d
0x18002537b  mov     [rbp+arg_0], ax
0x18002537f  mov     rdi, rdx
0x180025382  mov     [rbp+arg_10], r14
0x180025386  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002538a  call    cs:__imp_VariantInit
0x180025390  test    rsi, rsi
0x180025393  jnz     short loc_1800253C3
0x180025395  mov     r9d, 100h
0x18002539b  mov     eax, 80070057h
0x1800253a0  mov     ebx, eax
0x1800253a2  mov     dword ptr [rsp+70h+ppv], eax
0x1800253a6  lea     r8, aSdpxmlload; "SdpXmlLoad"
0x1800253ad  mov     ecx, 1; Level
0x1800253b2  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x1800253b9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800253be  jmp     loc_1800254C2
0x1800253c3  test    rdi, rdi
0x1800253c6  jnz     short loc_1800253D0
0x1800253c8  mov     r9d, 101h
0x1800253ce  jmp     short loc_18002539B
0x1800253d0  xor     edx, edx; pUnkOuter
0x1800253d2  lea     rax, [rbp+arg_10]
0x1800253d6  lea     r9, IID_IXMLDOMDocument2; riid
0x1800253dd  mov     [rsp+70h+ppv], rax; ppv
0x1800253e2  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800253e9  lea     r8d, [rdx+15h]; dwClsContext
0x1800253ed  call    cs:__imp_CoCreateInstance
0x1800253f3  mov     ebx, eax
0x1800253f5  test    eax, eax
0x1800253f7  jns     short loc_180025401
0x1800253f9  mov     r9d, 108h
0x1800253ff  jmp     short loc_1800253A2
0x180025401  mov     rcx, [rbp+arg_10]
0x180025405  xor     edx, edx
0x180025407  mov     rax, [rcx]
0x18002540a  mov     rax, [rax+1F8h]
0x180025411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025416  mov     ebx, eax
0x180025418  test    eax, eax
0x18002541a  jns     short loc_180025427
0x18002541c  mov     r9d, 10Bh
0x180025422  jmp     loc_1800253A2
0x180025427  mov     rcx, rsi; psz
0x18002542a  call    cs:__imp_SysAllocString
0x180025430  mov     qword ptr [rbp+pvarg+8], rax
0x180025434  test    rax, rax
0x180025437  jnz     short loc_18002544D
0x180025439  mov     ebx, 8007000Eh
0x18002543e  mov     r9d, 10Eh
0x180025444  mov     dword ptr [rsp+70h+ppv], ebx
0x180025448  jmp     loc_1800253A6
0x18002544d  mov     rcx, [rbp+arg_10]
0x180025451  lea     r8, [rbp+arg_0]
0x180025455  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18002545a  lea     rdx, [rbp+var_20]
0x18002545e  mov     eax, 8
0x180025463  movsd   [rbp+var_10], xmm1
0x180025468  mov     word ptr [rbp+pvarg], ax
0x18002546c  mov     rax, [rcx]
0x18002546f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180025473  mov     rax, [rax+1D0h]
0x18002547a  movaps  [rbp+var_20], xmm0
0x18002547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025483  mov     ebx, eax
0x180025485  test    eax, eax
0x180025487  jns     short loc_180025494
0x180025489  mov     r9d, 113h
0x18002548f  jmp     loc_1800253A2
0x180025494  cmp     [rbp+arg_0], r14w
0x180025499  jnz     short loc_1800254AF
0x18002549b  mov     ebx, 80004005h
0x1800254a0  mov     r9d, 114h
0x1800254a6  mov     dword ptr [rsp+70h+ppv], ebx
0x1800254aa  jmp     loc_1800253A6
0x1800254af  mov     rcx, [rbp+arg_10]
0x1800254b3  mov     [rdi], rcx
0x1800254b6  mov     rax, [rcx]
0x1800254b9  mov     rax, [rax+8]
0x1800254bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254c2  lea     rcx, [rbp+pvarg]; pvarg
0x1800254c6  call    cs:__imp_VariantClear
0x1800254cc  mov     rcx, [rbp+arg_10]
0x1800254d0  test    rcx, rcx
0x1800254d3  jz      short loc_1800254E1
0x1800254d5  mov     rax, [rcx]
0x1800254d8  mov     rax, [rax+10h]
0x1800254dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254e1  lea     r11, [rsp+70h+var_s0]
0x1800254e6  mov     eax, ebx
0x1800254e8  mov     rbx, [r11+28h]
0x1800254ec  mov     rsi, [r11+38h]
0x1800254f0  mov     rsp, r11
0x1800254f3  pop     r14
0x1800254f5  pop     rdi
0x1800254f6  pop     rbp
0x1800254f7  retn
```

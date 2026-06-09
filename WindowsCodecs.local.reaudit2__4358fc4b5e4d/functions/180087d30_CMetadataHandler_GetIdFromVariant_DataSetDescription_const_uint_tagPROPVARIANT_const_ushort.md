# CMetadataHandler::GetIdFromVariant(DataSetDescription const *,uint,tagPROPVARIANT const *,ushort *)

- ea: `0x180087d30`
- end: `0x180087ed9`
- name: `?GetIdFromVariant@CMetadataHandler@@MEAAJPEBUDataSetDescription@@IPEBUtagPROPVARIANT@@PEAG@Z`
- size: `425`
- prototype: `int(CMetadataHandler *__hidden this, const struct DataSetDescription *, unsigned int, const struct tagPROPVARIANT *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180087c30`
- `0x180087cb0`

## callees

- `0x180087d30`
- `0x180087ee0`
- `0x18008e774`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087e33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087e33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087d77`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180087d77`
- `OLEAUT32!__imp_VariantInit` at `0x180087dec`
- `OLEAUT32!__imp_VariantInit` at `0x180087dec`
- `OLEAUT32!__imp_VariantChangeType` at `0x180087e09`
- `OLEAUT32!__imp_VariantChangeType` at `0x180087e09`

## pseudocode

```c
__int64 __fastcall CMetadataHandler::GetIdFromVariant(
        CMetadataHandler *this,
        const struct DataSetDescription *a2,
        unsigned int a3,
        const VARIANTARG *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // rdi
  const WCHAR *bstrVal; // rsi
  __int64 i; // rbx
  LPCWSTR *v11; // rdi
  unsigned int v12; // ebx
  bool v14; // zf
  int v15; // eax
  CMetadataHandler *v16; // rcx
  unsigned __int16 *DataSetDesc; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v14 = a4->vt == 31;
  v19 = 0;
  if ( !v14 )
  {
    if ( a4->vt == 30 )
    {
      v15 = CoerceAnsiStrToWideStr(a4->pcVal, &v19);
      v12 = v15;
      if ( v15 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v15);
        v5 = v19;
        goto LABEL_15;
      }
      v5 = v19;
      DataSetDesc = (unsigned __int16 *)CMetadataHandler::FindDataSetDesc(v16, a2, a3, v19);
      if ( !DataSetDesc )
      {
        v14 = (_DWORD)g_doStackCaptures == 0;
        v12 = -2147024809;
LABEL_17:
        if ( !v14 )
          DoStackCapture(v12);
        goto LABEL_15;
      }
      *a5 = *DataSetDesc;
    }
    else
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( VariantChangeType(&pvarg, a4, 0, 0x12u) >= 0 )
      {
        v12 = 0;
        *a5 = pvarg.uiVal;
        goto LABEL_15;
      }
      v12 = -2003292352;
      if ( (_DWORD)g_doStackCaptures )
      {
        DoStackCapture(-2003292352);
        v14 = (_DWORD)g_doStackCaptures == 0;
        goto LABEL_17;
      }
    }
LABEL_15:
    if ( v5 )
      CoTaskMemFree(v5);
    return v12;
  }
  bstrVal = a4->bstrVal;
  if ( bstrVal )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v11 = (LPCWSTR *)((char *)a2 + 24 * i);
      if ( !lstrcmpiW(bstrVal, v11[1]) )
      {
        if ( !v11 )
          break;
        v12 = 0;
        *a5 = *(_WORD *)v11;
        return v12;
      }
    }
  }
  v12 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024809);
  return v12;
}

```

## disassembly

```asm
0x180087d30  mov     [rsp+arg_0], rbx
0x180087d35  mov     [rsp+arg_8], rbp
0x180087d3a  push    rsi
0x180087d3b  push    rdi
0x180087d3c  push    r14
0x180087d3e  sub     rsp, 40h
0x180087d42  xor     edi, edi
0x180087d44  mov     rbx, r9
0x180087d47  cmp     word ptr [r9], 1Fh
0x180087d4c  mov     ebp, r8d
0x180087d4f  mov     r14, rdx
0x180087d52  mov     [rsp+58h+arg_18], rdi
0x180087d57  jnz     short loc_180087DCD
0x180087d59  mov     rsi, [r9+8]
0x180087d5d  test    rsi, rsi
0x180087d60  jz      short loc_180087D8B
0x180087d62  xor     ebx, ebx
0x180087d64  cmp     ebx, ebp
0x180087d66  jnb     short loc_180087D8B
0x180087d68  lea     rcx, [rbx+rbx*2]
0x180087d6c  lea     rdi, [r14+rcx*8]
0x180087d70  mov     rcx, rsi; lpString1
0x180087d73  mov     rdx, [rdi+8]; lpString2
0x180087d77  call    cs:__imp_lstrcmpiW
0x180087d7e  nop     dword ptr [rax+rax+00h]
0x180087d83  test    eax, eax
0x180087d85  jz      short loc_180087DA2
0x180087d87  inc     ebx
0x180087d89  jmp     short loc_180087D64
0x180087d8b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180087d92  mov     ebx, 80070057h
0x180087d97  jz      short loc_180087DB7
0x180087d99  mov     ecx, ebx; int
0x180087d9b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087da0  jmp     short loc_180087DB7
0x180087da2  test    rdi, rdi
0x180087da5  jz      short loc_180087D8B
0x180087da7  mov     rax, [rsp+58h+arg_20]
0x180087daf  xor     ebx, ebx
0x180087db1  movzx   ecx, word ptr [rdi]
0x180087db4  mov     [rax], cx
0x180087db7  mov     rbp, [rsp+58h+arg_8]
0x180087dbc  mov     eax, ebx
0x180087dbe  mov     rbx, [rsp+58h+arg_0]
0x180087dc3  add     rsp, 40h
0x180087dc7  pop     r14
0x180087dc9  pop     rdi
0x180087dca  pop     rsi
0x180087dcb  retn
0x180087dcd  cmp     word ptr [r9], 1Eh
0x180087dd2  jz      loc_180087E5E
0x180087dd8  xorps   xmm0, xmm0
0x180087ddb  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180087de0  xor     eax, eax
0x180087de2  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x180087de7  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x180087dec  call    cs:__imp_VariantInit
0x180087df3  nop     dword ptr [rax+rax+00h]
0x180087df8  mov     r9d, 12h; vt
0x180087dfe  lea     rcx, [rsp+58h+pvarg]; pvargDest
0x180087e03  xor     r8d, r8d; wFlags
0x180087e06  mov     rdx, rbx; pvarSrc
0x180087e09  call    cs:__imp_VariantChangeType
0x180087e10  nop     dword ptr [rax+rax+00h]
0x180087e15  test    eax, eax
0x180087e17  js      short loc_180087E88
0x180087e19  mov     rdx, [rsp+58h+arg_20]
0x180087e21  xor     ebx, ebx
0x180087e23  movzx   eax, word ptr [rsp+58h+pvarg+8]
0x180087e28  mov     [rdx], ax
0x180087e2b  test    rdi, rdi
0x180087e2e  jz      short loc_180087DB7
0x180087e30  mov     rcx, rdi; pv
0x180087e33  call    cs:__imp_CoTaskMemFree
0x180087e3a  nop     dword ptr [rax+rax+00h]
0x180087e3f  jmp     loc_180087DB7
0x180087e44  mov     ecx, ebx; int
0x180087e46  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087e4b  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180087e51  test    eax, eax
0x180087e53  jz      short loc_180087E2B
0x180087e55  mov     ecx, ebx; int
0x180087e57  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087e5c  jmp     short loc_180087E2B
0x180087e5e  mov     rcx, [r9+8]; lpMultiByteStr
0x180087e62  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180087e67  call    ?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z; CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)
0x180087e6c  mov     ebx, eax
0x180087e6e  test    eax, eax
0x180087e70  jns     short loc_180087E9D
0x180087e72  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180087e78  jz      short loc_180087E99
0x180087e7a  mov     ecx, eax; int
0x180087e7c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087e81  mov     rdi, [rsp+58h+arg_18]
0x180087e86  jmp     short loc_180087E2B
0x180087e88  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180087e8e  mov     ebx, 88982F40h
0x180087e93  test    eax, eax
0x180087e95  jz      short loc_180087E2B
0x180087e97  jmp     short loc_180087E44
0x180087e99  test    eax, eax
0x180087e9b  js      short loc_180087E81
0x180087e9d  mov     rdi, [rsp+58h+arg_18]
0x180087ea2  mov     r8d, ebp; unsigned int
0x180087ea5  mov     r9, rdi; unsigned __int16 *
0x180087ea8  mov     rdx, r14; struct DataSetDescription *
0x180087eab  call    ?FindDataSetDesc@CMetadataHandler@@IEAAPEBUDataSetDescription@@PEBU2@IPEBG@Z; CMetadataHandler::FindDataSetDesc(DataSetDescription const *,uint,ushort const *)
0x180087eb0  test    rax, rax
0x180087eb3  jz      short loc_180087EC8
0x180087eb5  movzx   ecx, word ptr [rax]
0x180087eb8  mov     rax, [rsp+58h+arg_20]
0x180087ec0  mov     [rax], cx
0x180087ec3  jmp     loc_180087E2B
0x180087ec8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180087ecf  mov     ebx, 80070057h
0x180087ed4  jmp     loc_180087E53
```

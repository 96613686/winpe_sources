# CInkRecoAlternate::get_Baseline(tagVARIANT *)

- ea: `0x1800d4070`
- end: `0x1800d41e6`
- name: `?get_Baseline@CInkRecoAlternate@@UEAAJPEAUtagVARIANT@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(CInkRecoAlternate *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800810c4`
- `0x1800825e4`
- `0x1800d4070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d41c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d41cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d41c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d41cf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d41a4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d41a4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d4169`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d4169`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4189`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4189`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d4150`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d4150`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d40bc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d40bc`

## pseudocode

```c
__int64 __fastcall CInkRecoAlternate::get_Baseline(CInkRecoAlternate *this, struct tagVARIANT *a2)
{
  __int64 v4; // rsi
  HRESULT String; // ebx
  DWORD v6; // edi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  struct tagLINE_SEGMENT v10; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF
  struct tagRECO_RANGE v12; // [rsp+78h] [rbp+10h] BYREF
  void *ppvData; // [rsp+80h] [rbp+18h] BYREF
  __int64 v14; // [rsp+88h] [rbp+20h]

  dwindex = 0;
  v4 = (__int64)this + 16;
  if ( this == (CInkRecoAlternate *)8 )
    v4 = 8;
  v14 = v4;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v4, &dwindex);
  if ( a2 )
  {
    ppvData = 0;
    dwindex = 0;
    v10 = 0;
    String = GetString(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), 0, &dwindex, 0);
    if ( String >= 0 )
    {
      v12.iwcBegin = 0;
      v6 = dwindex;
      v12.cCount = dwindex;
      String = GetMetrics(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), &v12, LM_BASELINE, &v10);
      if ( String >= 0 )
      {
        if ( v12.iwcBegin || v12.cCount != v6 )
        {
          String = -2147467259;
        }
        else
        {
          Vector = SafeArrayCreateVector(3u, 0, 4u);
          v8 = Vector;
          if ( Vector )
          {
            String = SafeArrayAccessData(Vector, &ppvData);
            if ( String < 0
              || (*(struct tagLINE_SEGMENT *)ppvData = v10, String = SafeArrayUnaccessData(v8), String < 0) )
            {
              SafeArrayDestroy(v8);
            }
            else
            {
              a2->vt = 8195;
              a2->llVal = (LONGLONG)v8;
            }
          }
        }
      }
    }
    ReleaseMutex(*(HANDLE *)v4);
    return (unsigned int)String;
  }
  else
  {
    ReleaseMutex(*(HANDLE *)v4);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800d4070  push    rbx
0x1800d4072  push    rsi
0x1800d4073  push    rdi
0x1800d4074  push    r14
0x1800d4076  push    r15
0x1800d4078  sub     rsp, 40h
0x1800d407c  mov     r14, rdx
0x1800d407f  mov     r15, rcx
0x1800d4082  mov     [rsp+68h+dwindex], 0
0x1800d408a  lea     rax, [rcx-8]
0x1800d408e  lea     rsi, [rcx+10h]
0x1800d4092  mov     ecx, 8
0x1800d4097  test    rax, rax
0x1800d409a  cmovz   rsi, rcx
0x1800d409e  mov     [rsp+68h+arg_18], rsi
0x1800d40a6  lea     rax, [rsp+68h+dwindex]
0x1800d40ab  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800d40b0  mov     r9, rsi; pHandles
0x1800d40b3  lea     r8d, [rcx-7]; cHandles
0x1800d40b7  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d40ba  xor     ecx, ecx; dwFlags
0x1800d40bc  call    cs:__imp_CoWaitForMultipleHandles
0x1800d40c2  test    r14, r14
0x1800d40c5  jz      loc_1800D41CC
0x1800d40cb  mov     [rsp+68h+ppvData], 0
0x1800d40d7  mov     [rsp+68h+dwindex], 0
0x1800d40df  xorps   xmm0, xmm0
0x1800d40e2  movups  xmmword ptr [rsp+68h+var_38.PtA.x], xmm0
0x1800d40e7  mov     rcx, [r15+20h]
0x1800d40eb  xor     r9d, r9d; unsigned __int16 *
0x1800d40ee  lea     r8, [rsp+68h+dwindex]; unsigned int *
0x1800d40f3  xor     edx, edx; struct tagRECO_RANGE *
0x1800d40f5  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d40f9  call    ?GetString@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@PEAKPEAG@Z; GetString(tagWispAlternate *,tagRECO_RANGE *,ulong *,ushort *)
0x1800d40fe  mov     ebx, eax
0x1800d4100  test    eax, eax
0x1800d4102  js      loc_1800D41B1
0x1800d4108  mov     [rsp+68h+arg_8.iwcBegin], 0
0x1800d4110  mov     edi, [rsp+68h+dwindex]
0x1800d4114  mov     [rsp+68h+arg_8.cCount], edi
0x1800d4118  mov     rcx, [r15+20h]
0x1800d411c  lea     r9, [rsp+68h+var_38]; struct tagLINE_SEGMENT *
0x1800d4121  xor     r8d, r8d; enum enumLINE_METRICS
0x1800d4124  lea     rdx, [rsp+68h+arg_8]; struct tagRECO_RANGE *
0x1800d4129  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d412d  call    ?GetMetrics@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@W4enumLINE_METRICS@@PEAUtagLINE_SEGMENT@@@Z; GetMetrics(tagWispAlternate *,tagRECO_RANGE *,enumLINE_METRICS,tagLINE_SEGMENT *)
0x1800d4132  mov     ebx, eax
0x1800d4134  test    eax, eax
0x1800d4136  js      short loc_1800D41B1
0x1800d4138  cmp     [rsp+68h+arg_8.iwcBegin], 0
0x1800d413d  jnz     short loc_1800D41AC
0x1800d413f  cmp     [rsp+68h+arg_8.cCount], edi
0x1800d4143  jnz     short loc_1800D41AC
0x1800d4145  mov     ecx, 3; vt
0x1800d414a  xor     edx, edx; lLbound
0x1800d414c  lea     r8d, [rcx+1]; cElements
0x1800d4150  call    cs:__imp_SafeArrayCreateVector
0x1800d4156  mov     rdi, rax
0x1800d4159  test    rax, rax
0x1800d415c  jz      short loc_1800D41B1
0x1800d415e  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800d4166  mov     rcx, rax; psa
0x1800d4169  call    cs:__imp_SafeArrayAccessData
0x1800d416f  mov     ebx, eax
0x1800d4171  test    eax, eax
0x1800d4173  js      short loc_1800D41A1
0x1800d4175  movups  xmm0, xmmword ptr [rsp+68h+var_38.PtA.x]
0x1800d417a  mov     rcx, [rsp+68h+ppvData]
0x1800d4182  movdqu  xmmword ptr [rcx], xmm0
0x1800d4186  mov     rcx, rdi; psa
0x1800d4189  call    cs:__imp_SafeArrayUnaccessData
0x1800d418f  mov     ebx, eax
0x1800d4191  test    eax, eax
0x1800d4193  js      short loc_1800D41A1
0x1800d4195  mov     word ptr [r14], 2003h
0x1800d419b  mov     [r14+8], rdi
0x1800d419f  jmp     short loc_1800D41B1
0x1800d41a1  mov     rcx, rdi; psa
0x1800d41a4  call    cs:__imp_SafeArrayDestroy
0x1800d41aa  jmp     short loc_1800D41B1
0x1800d41ac  mov     ebx, 80004005h
0x1800d41b1  jmp     short loc_1800D41BF
0x1800d41b3  mov     ebx, [rsp+68h+dwindex]
0x1800d41b7  mov     rsi, [rsp+68h+arg_18]
0x1800d41bf  mov     rcx, [rsi]; hMutex
0x1800d41c2  call    cs:__imp_ReleaseMutex
0x1800d41c8  mov     eax, ebx
0x1800d41ca  jmp     short loc_1800D41DA
0x1800d41cc  mov     rcx, [rsi]; hMutex
0x1800d41cf  call    cs:__imp_ReleaseMutex
0x1800d41d5  mov     eax, 80004003h
0x1800d41da  add     rsp, 40h
0x1800d41de  pop     r15
0x1800d41e0  pop     r14
0x1800d41e2  pop     rdi
0x1800d41e3  pop     rsi
0x1800d41e4  pop     rbx
0x1800d41e5  retn
```

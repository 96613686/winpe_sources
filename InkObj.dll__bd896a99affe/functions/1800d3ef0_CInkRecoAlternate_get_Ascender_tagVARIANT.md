# CInkRecoAlternate::get_Ascender(tagVARIANT *)

- ea: `0x1800d3ef0`
- end: `0x1800d4069`
- name: `?get_Ascender@CInkRecoAlternate@@UEAAJPEAUtagVARIANT@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CInkRecoAlternate *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800810c4`
- `0x1800825e4`
- `0x1800d3ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4052`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4052`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d4027`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d4027`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d3fec`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d3fec`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d400c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d400c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d3fd3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d3fd3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d3f3c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d3f3c`

## pseudocode

```c
__int64 __fastcall CInkRecoAlternate::get_Ascender(CInkRecoAlternate *this, struct tagVARIANT *a2)
{
  __int64 v4; // rsi
  HRESULT String; // ebx
  DWORD v6; // edi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  tagLINE_SEGMENT v10; // [rsp+30h] [rbp-38h] BYREF
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
      String = GetMetrics(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), &v12, LM_ASCENDER, &v10);
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
            if ( String < 0 || (*(tagLINE_SEGMENT *)ppvData = v10, String = SafeArrayUnaccessData(v8), String < 0) )
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
0x1800d3ef0  push    rbx
0x1800d3ef2  push    rsi
0x1800d3ef3  push    rdi
0x1800d3ef4  push    r14
0x1800d3ef6  push    r15
0x1800d3ef8  sub     rsp, 40h
0x1800d3efc  mov     r14, rdx
0x1800d3eff  mov     r15, rcx
0x1800d3f02  mov     [rsp+68h+dwindex], 0
0x1800d3f0a  lea     rax, [rcx-8]
0x1800d3f0e  lea     rsi, [rcx+10h]
0x1800d3f12  mov     ecx, 8
0x1800d3f17  test    rax, rax
0x1800d3f1a  cmovz   rsi, rcx
0x1800d3f1e  mov     [rsp+68h+arg_18], rsi
0x1800d3f26  lea     rax, [rsp+68h+dwindex]
0x1800d3f2b  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800d3f30  mov     r9, rsi; pHandles
0x1800d3f33  lea     r8d, [rcx-7]; cHandles
0x1800d3f37  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d3f3a  xor     ecx, ecx; dwFlags
0x1800d3f3c  call    cs:__imp_CoWaitForMultipleHandles
0x1800d3f42  test    r14, r14
0x1800d3f45  jz      loc_1800D404F
0x1800d3f4b  mov     [rsp+68h+ppvData], 0
0x1800d3f57  mov     [rsp+68h+dwindex], 0
0x1800d3f5f  xorps   xmm0, xmm0
0x1800d3f62  movups  xmmword ptr [rsp+68h+var_38.PtA.x], xmm0
0x1800d3f67  mov     rcx, [r15+20h]
0x1800d3f6b  xor     r9d, r9d; unsigned __int16 *
0x1800d3f6e  lea     r8, [rsp+68h+dwindex]; unsigned int *
0x1800d3f73  xor     edx, edx; struct tagRECO_RANGE *
0x1800d3f75  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d3f79  call    ?GetString@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@PEAKPEAG@Z; GetString(tagWispAlternate *,tagRECO_RANGE *,ulong *,ushort *)
0x1800d3f7e  mov     ebx, eax
0x1800d3f80  test    eax, eax
0x1800d3f82  js      loc_1800D4034
0x1800d3f88  mov     [rsp+68h+arg_8.iwcBegin], 0
0x1800d3f90  mov     edi, [rsp+68h+dwindex]
0x1800d3f94  mov     [rsp+68h+arg_8.cCount], edi
0x1800d3f98  mov     rcx, [r15+20h]
0x1800d3f9c  lea     r9, [rsp+68h+var_38]; struct tagLINE_SEGMENT *
0x1800d3fa1  mov     r8d, 2; enum enumLINE_METRICS
0x1800d3fa7  lea     rdx, [rsp+68h+arg_8]; struct tagRECO_RANGE *
0x1800d3fac  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d3fb0  call    ?GetMetrics@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@W4enumLINE_METRICS@@PEAUtagLINE_SEGMENT@@@Z; GetMetrics(tagWispAlternate *,tagRECO_RANGE *,enumLINE_METRICS,tagLINE_SEGMENT *)
0x1800d3fb5  mov     ebx, eax
0x1800d3fb7  test    eax, eax
0x1800d3fb9  js      short loc_1800D4034
0x1800d3fbb  cmp     [rsp+68h+arg_8.iwcBegin], 0
0x1800d3fc0  jnz     short loc_1800D402F
0x1800d3fc2  cmp     [rsp+68h+arg_8.cCount], edi
0x1800d3fc6  jnz     short loc_1800D402F
0x1800d3fc8  mov     ecx, 3; vt
0x1800d3fcd  xor     edx, edx; lLbound
0x1800d3fcf  lea     r8d, [rcx+1]; cElements
0x1800d3fd3  call    cs:__imp_SafeArrayCreateVector
0x1800d3fd9  mov     rdi, rax
0x1800d3fdc  test    rax, rax
0x1800d3fdf  jz      short loc_1800D4034
0x1800d3fe1  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800d3fe9  mov     rcx, rax; psa
0x1800d3fec  call    cs:__imp_SafeArrayAccessData
0x1800d3ff2  mov     ebx, eax
0x1800d3ff4  test    eax, eax
0x1800d3ff6  js      short loc_1800D4024
0x1800d3ff8  movups  xmm0, xmmword ptr [rsp+68h+var_38.PtA.x]
0x1800d3ffd  mov     rcx, [rsp+68h+ppvData]
0x1800d4005  movdqu  xmmword ptr [rcx], xmm0
0x1800d4009  mov     rcx, rdi; psa
0x1800d400c  call    cs:__imp_SafeArrayUnaccessData
0x1800d4012  mov     ebx, eax
0x1800d4014  test    eax, eax
0x1800d4016  js      short loc_1800D4024
0x1800d4018  mov     word ptr [r14], 2003h
0x1800d401e  mov     [r14+8], rdi
0x1800d4022  jmp     short loc_1800D4034
0x1800d4024  mov     rcx, rdi; psa
0x1800d4027  call    cs:__imp_SafeArrayDestroy
0x1800d402d  jmp     short loc_1800D4034
0x1800d402f  mov     ebx, 80004005h
0x1800d4034  jmp     short loc_1800D4042
0x1800d4036  mov     ebx, [rsp+68h+dwindex]
0x1800d403a  mov     rsi, [rsp+68h+arg_18]
0x1800d4042  mov     rcx, [rsi]; hMutex
0x1800d4045  call    cs:__imp_ReleaseMutex
0x1800d404b  mov     eax, ebx
0x1800d404d  jmp     short loc_1800D405D
0x1800d404f  mov     rcx, [rsi]; hMutex
0x1800d4052  call    cs:__imp_ReleaseMutex
0x1800d4058  mov     eax, 80004003h
0x1800d405d  add     rsp, 40h
0x1800d4061  pop     r15
0x1800d4063  pop     r14
0x1800d4065  pop     rdi
0x1800d4066  pop     rsi
0x1800d4067  pop     rbx
0x1800d4068  retn
```

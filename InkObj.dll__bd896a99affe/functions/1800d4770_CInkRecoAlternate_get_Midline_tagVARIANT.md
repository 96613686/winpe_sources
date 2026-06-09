# CInkRecoAlternate::get_Midline(tagVARIANT *)

- ea: `0x1800d4770`
- end: `0x1800d48e9`
- name: `?get_Midline@CInkRecoAlternate@@UEAAJPEAUtagVARIANT@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CInkRecoAlternate *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800810c4`
- `0x1800825e4`
- `0x1800d4770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d48c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d48d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d48c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d48d2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d48a7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d48a7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d486c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d486c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d488c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d488c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d4853`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d4853`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d47bc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d47bc`

## pseudocode

```c
__int64 __fastcall CInkRecoAlternate::get_Midline(CInkRecoAlternate *this, struct tagVARIANT *a2)
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
      String = GetMetrics(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), &v12, LM_MIDLINE, &v10);
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
0x1800d4770  push    rbx
0x1800d4772  push    rsi
0x1800d4773  push    rdi
0x1800d4774  push    r14
0x1800d4776  push    r15
0x1800d4778  sub     rsp, 40h
0x1800d477c  mov     r14, rdx
0x1800d477f  mov     r15, rcx
0x1800d4782  mov     [rsp+68h+dwindex], 0
0x1800d478a  lea     rax, [rcx-8]
0x1800d478e  lea     rsi, [rcx+10h]
0x1800d4792  mov     ecx, 8
0x1800d4797  test    rax, rax
0x1800d479a  cmovz   rsi, rcx
0x1800d479e  mov     [rsp+68h+arg_18], rsi
0x1800d47a6  lea     rax, [rsp+68h+dwindex]
0x1800d47ab  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800d47b0  mov     r9, rsi; pHandles
0x1800d47b3  lea     r8d, [rcx-7]; cHandles
0x1800d47b7  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d47ba  xor     ecx, ecx; dwFlags
0x1800d47bc  call    cs:__imp_CoWaitForMultipleHandles
0x1800d47c2  test    r14, r14
0x1800d47c5  jz      loc_1800D48CF
0x1800d47cb  mov     [rsp+68h+ppvData], 0
0x1800d47d7  mov     [rsp+68h+dwindex], 0
0x1800d47df  xorps   xmm0, xmm0
0x1800d47e2  movups  xmmword ptr [rsp+68h+var_38.PtA.x], xmm0
0x1800d47e7  mov     rcx, [r15+20h]
0x1800d47eb  xor     r9d, r9d; unsigned __int16 *
0x1800d47ee  lea     r8, [rsp+68h+dwindex]; unsigned int *
0x1800d47f3  xor     edx, edx; struct tagRECO_RANGE *
0x1800d47f5  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d47f9  call    ?GetString@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@PEAKPEAG@Z; GetString(tagWispAlternate *,tagRECO_RANGE *,ulong *,ushort *)
0x1800d47fe  mov     ebx, eax
0x1800d4800  test    eax, eax
0x1800d4802  js      loc_1800D48B4
0x1800d4808  mov     [rsp+68h+arg_8.iwcBegin], 0
0x1800d4810  mov     edi, [rsp+68h+dwindex]
0x1800d4814  mov     [rsp+68h+arg_8.cCount], edi
0x1800d4818  mov     rcx, [r15+20h]
0x1800d481c  lea     r9, [rsp+68h+var_38]; struct tagLINE_SEGMENT *
0x1800d4821  mov     r8d, 1; enum enumLINE_METRICS
0x1800d4827  lea     rdx, [rsp+68h+arg_8]; struct tagRECO_RANGE *
0x1800d482c  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d4830  call    ?GetMetrics@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@W4enumLINE_METRICS@@PEAUtagLINE_SEGMENT@@@Z; GetMetrics(tagWispAlternate *,tagRECO_RANGE *,enumLINE_METRICS,tagLINE_SEGMENT *)
0x1800d4835  mov     ebx, eax
0x1800d4837  test    eax, eax
0x1800d4839  js      short loc_1800D48B4
0x1800d483b  cmp     [rsp+68h+arg_8.iwcBegin], 0
0x1800d4840  jnz     short loc_1800D48AF
0x1800d4842  cmp     [rsp+68h+arg_8.cCount], edi
0x1800d4846  jnz     short loc_1800D48AF
0x1800d4848  mov     ecx, 3; vt
0x1800d484d  xor     edx, edx; lLbound
0x1800d484f  lea     r8d, [rcx+1]; cElements
0x1800d4853  call    cs:__imp_SafeArrayCreateVector
0x1800d4859  mov     rdi, rax
0x1800d485c  test    rax, rax
0x1800d485f  jz      short loc_1800D48B4
0x1800d4861  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800d4869  mov     rcx, rax; psa
0x1800d486c  call    cs:__imp_SafeArrayAccessData
0x1800d4872  mov     ebx, eax
0x1800d4874  test    eax, eax
0x1800d4876  js      short loc_1800D48A4
0x1800d4878  movups  xmm0, xmmword ptr [rsp+68h+var_38.PtA.x]
0x1800d487d  mov     rcx, [rsp+68h+ppvData]
0x1800d4885  movdqu  xmmword ptr [rcx], xmm0
0x1800d4889  mov     rcx, rdi; psa
0x1800d488c  call    cs:__imp_SafeArrayUnaccessData
0x1800d4892  mov     ebx, eax
0x1800d4894  test    eax, eax
0x1800d4896  js      short loc_1800D48A4
0x1800d4898  mov     word ptr [r14], 2003h
0x1800d489e  mov     [r14+8], rdi
0x1800d48a2  jmp     short loc_1800D48B4
0x1800d48a4  mov     rcx, rdi; psa
0x1800d48a7  call    cs:__imp_SafeArrayDestroy
0x1800d48ad  jmp     short loc_1800D48B4
0x1800d48af  mov     ebx, 80004005h
0x1800d48b4  jmp     short loc_1800D48C2
0x1800d48b6  mov     ebx, [rsp+68h+dwindex]
0x1800d48ba  mov     rsi, [rsp+68h+arg_18]
0x1800d48c2  mov     rcx, [rsi]; hMutex
0x1800d48c5  call    cs:__imp_ReleaseMutex
0x1800d48cb  mov     eax, ebx
0x1800d48cd  jmp     short loc_1800D48DD
0x1800d48cf  mov     rcx, [rsi]; hMutex
0x1800d48d2  call    cs:__imp_ReleaseMutex
0x1800d48d8  mov     eax, 80004003h
0x1800d48dd  add     rsp, 40h
0x1800d48e1  pop     r15
0x1800d48e3  pop     r14
0x1800d48e5  pop     rdi
0x1800d48e6  pop     rsi
0x1800d48e7  pop     rbx
0x1800d48e8  retn
```

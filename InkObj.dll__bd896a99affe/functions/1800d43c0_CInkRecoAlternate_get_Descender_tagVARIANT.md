# CInkRecoAlternate::get_Descender(tagVARIANT *)

- ea: `0x1800d43c0`
- end: `0x1800d453b`
- name: `?get_Descender@CInkRecoAlternate@@UEAAJPEAUtagVARIANT@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(CInkRecoAlternate *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800810c4`
- `0x1800825e4`
- `0x1800d43c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4517`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4524`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4517`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800d4524`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d44f9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d44f9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d44be`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d44be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d44de`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d44de`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d44a5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d44a5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d440c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800d440c`

## pseudocode

```c
__int64 __fastcall CInkRecoAlternate::get_Descender(CInkRecoAlternate *this, struct tagVARIANT *a2)
{
  __int64 v4; // rsi
  HRESULT String; // ebx
  DWORD v6; // r15d
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
      String = GetMetrics(*(struct tagWispAlternate **)(*((_QWORD *)this + 4) + 16LL), &v12, LM_DESCENDER, &v10);
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
0x1800d43c0  push    rbx
0x1800d43c2  push    rsi
0x1800d43c3  push    rdi
0x1800d43c4  push    r14
0x1800d43c6  push    r15
0x1800d43c8  sub     rsp, 40h
0x1800d43cc  mov     r14, rdx
0x1800d43cf  mov     rdi, rcx
0x1800d43d2  mov     [rsp+68h+dwindex], 0
0x1800d43da  lea     rax, [rcx-8]
0x1800d43de  lea     rsi, [rcx+10h]
0x1800d43e2  mov     ecx, 8
0x1800d43e7  test    rax, rax
0x1800d43ea  cmovz   rsi, rcx
0x1800d43ee  mov     [rsp+68h+arg_18], rsi
0x1800d43f6  lea     rax, [rsp+68h+dwindex]
0x1800d43fb  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800d4400  mov     r9, rsi; pHandles
0x1800d4403  lea     r8d, [rcx-7]; cHandles
0x1800d4407  or      edx, 0FFFFFFFFh; dwTimeout
0x1800d440a  xor     ecx, ecx; dwFlags
0x1800d440c  call    cs:__imp_CoWaitForMultipleHandles
0x1800d4412  test    r14, r14
0x1800d4415  jz      loc_1800D4521
0x1800d441b  mov     [rsp+68h+ppvData], 0
0x1800d4427  mov     [rsp+68h+dwindex], 0
0x1800d442f  xorps   xmm0, xmm0
0x1800d4432  movups  xmmword ptr [rsp+68h+var_38.PtA.x], xmm0
0x1800d4437  mov     rcx, [rdi+20h]
0x1800d443b  xor     r9d, r9d; unsigned __int16 *
0x1800d443e  lea     r8, [rsp+68h+dwindex]; unsigned int *
0x1800d4443  xor     edx, edx; struct tagRECO_RANGE *
0x1800d4445  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d4449  call    ?GetString@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@PEAKPEAG@Z; GetString(tagWispAlternate *,tagRECO_RANGE *,ulong *,ushort *)
0x1800d444e  mov     ebx, eax
0x1800d4450  test    eax, eax
0x1800d4452  js      loc_1800D4506
0x1800d4458  mov     [rsp+68h+arg_8.iwcBegin], 0
0x1800d4460  mov     r15d, [rsp+68h+dwindex]
0x1800d4465  mov     [rsp+68h+arg_8.cCount], r15d
0x1800d446a  mov     rcx, [rdi+20h]
0x1800d446e  lea     r9, [rsp+68h+var_38]; struct tagLINE_SEGMENT *
0x1800d4473  mov     edi, 3
0x1800d4478  mov     r8d, edi; enum enumLINE_METRICS
0x1800d447b  lea     rdx, [rsp+68h+arg_8]; struct tagRECO_RANGE *
0x1800d4480  mov     rcx, [rcx+10h]; struct tagWispAlternate *
0x1800d4484  call    ?GetMetrics@@YAJPEAUtagWispAlternate@@PEAUtagRECO_RANGE@@W4enumLINE_METRICS@@PEAUtagLINE_SEGMENT@@@Z; GetMetrics(tagWispAlternate *,tagRECO_RANGE *,enumLINE_METRICS,tagLINE_SEGMENT *)
0x1800d4489  mov     ebx, eax
0x1800d448b  test    eax, eax
0x1800d448d  js      short loc_1800D4506
0x1800d448f  cmp     [rsp+68h+arg_8.iwcBegin], 0
0x1800d4494  jnz     short loc_1800D4501
0x1800d4496  cmp     [rsp+68h+arg_8.cCount], r15d
0x1800d449b  jnz     short loc_1800D4501
0x1800d449d  mov     ecx, edi; vt
0x1800d449f  xor     edx, edx; lLbound
0x1800d44a1  lea     r8d, [rdi+1]; cElements
0x1800d44a5  call    cs:__imp_SafeArrayCreateVector
0x1800d44ab  mov     rdi, rax
0x1800d44ae  test    rax, rax
0x1800d44b1  jz      short loc_1800D4506
0x1800d44b3  lea     rdx, [rsp+68h+ppvData]; ppvData
0x1800d44bb  mov     rcx, rax; psa
0x1800d44be  call    cs:__imp_SafeArrayAccessData
0x1800d44c4  mov     ebx, eax
0x1800d44c6  test    eax, eax
0x1800d44c8  js      short loc_1800D44F6
0x1800d44ca  movups  xmm0, xmmword ptr [rsp+68h+var_38.PtA.x]
0x1800d44cf  mov     rcx, [rsp+68h+ppvData]
0x1800d44d7  movdqu  xmmword ptr [rcx], xmm0
0x1800d44db  mov     rcx, rdi; psa
0x1800d44de  call    cs:__imp_SafeArrayUnaccessData
0x1800d44e4  mov     ebx, eax
0x1800d44e6  test    eax, eax
0x1800d44e8  js      short loc_1800D44F6
0x1800d44ea  mov     word ptr [r14], 2003h
0x1800d44f0  mov     [r14+8], rdi
0x1800d44f4  jmp     short loc_1800D4506
0x1800d44f6  mov     rcx, rdi; psa
0x1800d44f9  call    cs:__imp_SafeArrayDestroy
0x1800d44ff  jmp     short loc_1800D4506
0x1800d4501  mov     ebx, 80004005h
0x1800d4506  jmp     short loc_1800D4514
0x1800d4508  mov     ebx, [rsp+68h+dwindex]
0x1800d450c  mov     rsi, [rsp+68h+arg_18]
0x1800d4514  mov     rcx, [rsi]; hMutex
0x1800d4517  call    cs:__imp_ReleaseMutex
0x1800d451d  mov     eax, ebx
0x1800d451f  jmp     short loc_1800D452F
0x1800d4521  mov     rcx, [rsi]; hMutex
0x1800d4524  call    cs:__imp_ReleaseMutex
0x1800d452a  mov     eax, 80004003h
0x1800d452f  add     rsp, 40h
0x1800d4533  pop     r15
0x1800d4535  pop     r14
0x1800d4537  pop     rdi
0x1800d4538  pop     rsi
0x1800d4539  pop     rbx
0x1800d453a  retn
```

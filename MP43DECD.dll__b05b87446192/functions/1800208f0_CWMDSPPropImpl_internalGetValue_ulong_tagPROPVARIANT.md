# CWMDSPPropImpl::internalGetValue(ulong,tagPROPVARIANT *)

- ea: `0x1800208f0`
- end: `0x1800209e7`
- name: `?internalGetValue@CWMDSPPropImpl@@MEAAJKPEAUtagPROPVARIANT@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800208f0`
- `0x180020f45`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800209bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800209bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020977`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::internalGetValue(CWMDSPPropImpl *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rdi
  BYTE *pData; // rcx
  unsigned int v7; // eax
  BYTE *v8; // rax
  OLECHAR *bstrVal; // rcx
  BSTR v10; // rbp

  v3 = *((_QWORD *)this + 3);
  v5 = 9LL * a2;
  switch ( a3->vt )
  {
    case 3u:
    case 4u:
      goto LABEL_21;
    case 5u:
LABEL_10:
      a3->hVal.QuadPart = *(_QWORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 8u:
      bstrVal = a3->bstrVal;
      v10 = 0;
      if ( *(_QWORD *)(v3 + 72LL * a2 + 8) )
      {
        SysFreeString(bstrVal);
        v10 = SysAllocString(*(const OLECHAR **)(v3 + 8 * v5 + 8));
      }
      else
      {
        SysFreeString(bstrVal);
      }
      a3->hVal.QuadPart = (LONGLONG)v10;
      return 0;
    case 0xBu:
      a3->iVal = *(_WORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 0x13u:
LABEL_21:
      a3->lVal = *(_DWORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 0x14u:
      goto LABEL_10;
    case 0x41u:
      pData = a3->bstrblobVal.pData;
      if ( pData )
        CoTaskMemFree(pData);
      v7 = *(_DWORD *)(v3 + 8 * v5 + 8);
      a3->lVal = v7;
      a3->bstrblobVal.pData = 0;
      if ( v7 )
      {
        v8 = (BYTE *)CoTaskMemAlloc(v7);
        a3->bstrblobVal.pData = v8;
        if ( v8 )
          memcpy_0(v8, *(const void **)(v3 + 8 * v5 + 16), a3->ulVal);
      }
      break;
    case 0x48u:
      goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800208f0  push    rbx
0x1800208f2  push    rbp
0x1800208f3  push    rsi
0x1800208f4  push    rdi
0x1800208f5  sub     rsp, 28h
0x1800208f9  mov     rsi, [rcx+18h]
0x1800208fd  mov     rbx, r8
0x180020900  movzx   ecx, word ptr [r8]
0x180020904  mov     eax, edx
0x180020906  lea     rdi, [rax+rax*8]
0x18002090a  sub     ecx, 3
0x18002090d  jz      loc_1800209D4
0x180020913  sub     ecx, 1
0x180020916  jz      loc_1800209D4
0x18002091c  sub     ecx, 1
0x18002091f  jz      short loc_180020947
0x180020921  sub     ecx, 3
0x180020924  jz      short loc_1800209A5
0x180020926  sub     ecx, 3
0x180020929  jz      short loc_180020999
0x18002092b  sub     ecx, 8
0x18002092e  jz      loc_1800209D4
0x180020934  sub     ecx, 1
0x180020937  jz      short loc_180020947
0x180020939  sub     ecx, 2Dh ; '-'
0x18002093c  jz      short loc_180020955
0x18002093e  cmp     ecx, 7
0x180020941  jnz     loc_1800209DC
0x180020947  mov     rax, [rsi+rdi*8+8]
0x18002094c  mov     [r8+8], rax
0x180020950  jmp     loc_1800209DC
0x180020955  mov     rcx, [r8+10h]; pv
0x180020959  xor     ebp, ebp
0x18002095b  test    rcx, rcx
0x18002095e  jz      short loc_180020966
0x180020960  call    cs:__imp_CoTaskMemFree
0x180020966  mov     eax, [rsi+rdi*8+8]
0x18002096a  mov     [rbx+8], eax
0x18002096d  mov     [rbx+10h], rbp
0x180020971  test    eax, eax
0x180020973  jz      short loc_1800209DC
0x180020975  mov     ecx, eax; cb
0x180020977  call    cs:__imp_CoTaskMemAlloc
0x18002097d  mov     [rbx+10h], rax
0x180020981  test    rax, rax
0x180020984  jz      short loc_1800209DC
0x180020986  mov     r8d, [rbx+8]; Size
0x18002098a  mov     rcx, rax; void *
0x18002098d  mov     rdx, [rsi+rdi*8+10h]; Src
0x180020992  call    memcpy_0
0x180020997  jmp     short loc_1800209DC
0x180020999  movzx   eax, word ptr [rsi+rdi*8+8]
0x18002099e  mov     [r8+8], ax
0x1800209a3  jmp     short loc_1800209DC
0x1800209a5  mov     rcx, [r8+8]; bstrString
0x1800209a9  xor     ebp, ebp
0x1800209ab  cmp     [rsi+rdi*8+8], rbp
0x1800209b0  jz      short loc_1800209C8
0x1800209b2  call    cs:__imp_SysFreeString
0x1800209b8  mov     rcx, [rsi+rdi*8+8]; psz
0x1800209bd  call    cs:__imp_SysAllocString
0x1800209c3  mov     rbp, rax
0x1800209c6  jmp     short loc_1800209CE
0x1800209c8  call    cs:__imp_SysFreeString
0x1800209ce  mov     [rbx+8], rbp
0x1800209d2  jmp     short loc_1800209DC
0x1800209d4  mov     eax, [rsi+rdi*8+8]
0x1800209d8  mov     [r8+8], eax
0x1800209dc  xor     eax, eax
0x1800209de  add     rsp, 28h
0x1800209e2  pop     rdi
0x1800209e3  pop     rsi
0x1800209e4  pop     rbp
0x1800209e5  pop     rbx
0x1800209e6  retn
```

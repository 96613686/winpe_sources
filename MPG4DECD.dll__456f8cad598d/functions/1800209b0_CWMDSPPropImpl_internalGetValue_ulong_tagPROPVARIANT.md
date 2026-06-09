# CWMDSPPropImpl::internalGetValue(ulong,tagPROPVARIANT *)

- ea: `0x1800209b0`
- end: `0x180020aa7`
- name: `?internalGetValue@CWMDSPPropImpl@@MEAAJKPEAUtagPROPVARIANT@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800209b0`
- `0x180021005`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180020a7d`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a72`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a88`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a72`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020a37`

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
0x1800209b0  push    rbx
0x1800209b2  push    rbp
0x1800209b3  push    rsi
0x1800209b4  push    rdi
0x1800209b5  sub     rsp, 28h
0x1800209b9  mov     rsi, [rcx+18h]
0x1800209bd  mov     rbx, r8
0x1800209c0  movzx   ecx, word ptr [r8]
0x1800209c4  mov     eax, edx
0x1800209c6  lea     rdi, [rax+rax*8]
0x1800209ca  sub     ecx, 3
0x1800209cd  jz      loc_180020A94
0x1800209d3  sub     ecx, 1
0x1800209d6  jz      loc_180020A94
0x1800209dc  sub     ecx, 1
0x1800209df  jz      short loc_180020A07
0x1800209e1  sub     ecx, 3
0x1800209e4  jz      short loc_180020A65
0x1800209e6  sub     ecx, 3
0x1800209e9  jz      short loc_180020A59
0x1800209eb  sub     ecx, 8
0x1800209ee  jz      loc_180020A94
0x1800209f4  sub     ecx, 1
0x1800209f7  jz      short loc_180020A07
0x1800209f9  sub     ecx, 2Dh ; '-'
0x1800209fc  jz      short loc_180020A15
0x1800209fe  cmp     ecx, 7
0x180020a01  jnz     loc_180020A9C
0x180020a07  mov     rax, [rsi+rdi*8+8]
0x180020a0c  mov     [r8+8], rax
0x180020a10  jmp     loc_180020A9C
0x180020a15  mov     rcx, [r8+10h]; pv
0x180020a19  xor     ebp, ebp
0x180020a1b  test    rcx, rcx
0x180020a1e  jz      short loc_180020A26
0x180020a20  call    cs:__imp_CoTaskMemFree
0x180020a26  mov     eax, [rsi+rdi*8+8]
0x180020a2a  mov     [rbx+8], eax
0x180020a2d  mov     [rbx+10h], rbp
0x180020a31  test    eax, eax
0x180020a33  jz      short loc_180020A9C
0x180020a35  mov     ecx, eax; cb
0x180020a37  call    cs:__imp_CoTaskMemAlloc
0x180020a3d  mov     [rbx+10h], rax
0x180020a41  test    rax, rax
0x180020a44  jz      short loc_180020A9C
0x180020a46  mov     r8d, [rbx+8]; Size
0x180020a4a  mov     rcx, rax; void *
0x180020a4d  mov     rdx, [rsi+rdi*8+10h]; Src
0x180020a52  call    memcpy_0
0x180020a57  jmp     short loc_180020A9C
0x180020a59  movzx   eax, word ptr [rsi+rdi*8+8]
0x180020a5e  mov     [r8+8], ax
0x180020a63  jmp     short loc_180020A9C
0x180020a65  mov     rcx, [r8+8]; bstrString
0x180020a69  xor     ebp, ebp
0x180020a6b  cmp     [rsi+rdi*8+8], rbp
0x180020a70  jz      short loc_180020A88
0x180020a72  call    cs:__imp_SysFreeString
0x180020a78  mov     rcx, [rsi+rdi*8+8]; psz
0x180020a7d  call    cs:__imp_SysAllocString
0x180020a83  mov     rbp, rax
0x180020a86  jmp     short loc_180020A8E
0x180020a88  call    cs:__imp_SysFreeString
0x180020a8e  mov     [rbx+8], rbp
0x180020a92  jmp     short loc_180020A9C
0x180020a94  mov     eax, [rsi+rdi*8+8]
0x180020a98  mov     [r8+8], eax
0x180020a9c  xor     eax, eax
0x180020a9e  add     rsp, 28h
0x180020aa2  pop     rdi
0x180020aa3  pop     rsi
0x180020aa4  pop     rbp
0x180020aa5  pop     rbx
0x180020aa6  retn
```

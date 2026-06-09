# CMessagingNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800b5b50`
- end: `0x1800b5cee`
- name: `?GetChildNodeNames@CMessagingNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `414`
- prototype: `__int64 __fastcall(CMessagingNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b5b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800b5bf0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5c3f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5c94`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5bf0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5c3f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5c94`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5cb9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5cb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5bc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5bc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5c6f`

## pseudocode

```c
__int64 __fastcall CMessagingNode::GetChildNodeNames(CMessagingNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  __int64 v5; // rsi
  int v6; // ecx
  int v7; // ecx
  unsigned int i; // ebx
  _QWORD *v9; // rdi
  BSTR v10; // rax
  BSTR v11; // rax
  _OWORD *v12; // rax
  BSTR v13; // rax
  __int64 v14; // rbp
  OLECHAR *psz; // [rsp+20h] [rbp-58h]
  const wchar_t *v17; // [rsp+28h] [rbp-50h]
  const wchar_t *v18; // [rsp+30h] [rbp-48h]
  OLECHAR *v19; // [rsp+88h] [rbp+10h]

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v5 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = *((_DWORD *)this + 11);
  if ( !v6 )
  {
    psz = L"AuditingLevel";
    v17 = L"Auditing";
    v12 = CoTaskMemAlloc(0x10u);
    v9 = v12;
    if ( v12 )
    {
      *v12 = 0;
      while ( (unsigned int)v5 < 2 )
      {
        v13 = SysAllocString((&psz)[v5]);
        v9[v5] = v13;
        if ( !v13 )
        {
LABEL_23:
          v14 = 0;
          for ( i = -2147024882; (unsigned int)v14 < (unsigned int)v5; v14 = (unsigned int)(v14 + 1) )
            SysFreeString((BSTR)v9[v14]);
          CoTaskMemFree(v9);
          return i;
        }
        v5 = (unsigned int)(v5 + 1);
      }
      goto LABEL_26;
    }
    return (unsigned int)-2147024882;
  }
  v7 = v6 - 2;
  if ( !v7 )
  {
    v19 = L"Messages";
    v9 = CoTaskMemAlloc(8u);
    if ( v9 )
    {
      *v9 = 0;
      while ( !(_DWORD)v5 )
      {
        v11 = SysAllocString((&v19)[v5]);
        v9[v5] = v11;
        if ( !v11 )
          goto LABEL_23;
        v5 = 1;
      }
      goto LABEL_26;
    }
    return (unsigned int)-2147024882;
  }
  if ( v7 == 1 )
  {
    psz = L"Count";
    v17 = L"RevisionId";
    v18 = L"Data";
    v9 = CoTaskMemAlloc(0x18u);
    if ( v9 )
    {
      *(_OWORD *)v9 = 0;
      v9[2] = 0;
      while ( (unsigned int)v5 < 3 )
      {
        v10 = SysAllocString((&psz)[v5]);
        v9[v5] = v10;
        if ( !v10 )
          goto LABEL_23;
        v5 = (unsigned int)(v5 + 1);
      }
LABEL_26:
      *a3 = (unsigned __int16 **)v9;
      i = 0;
      *a2 = v5;
      return i;
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)-2046820335;
}

```

## disassembly

```asm
0x1800b5b50  push    rbx
0x1800b5b52  push    rbp
0x1800b5b53  push    rsi
0x1800b5b54  push    rdi
0x1800b5b55  push    r14
0x1800b5b57  push    r15
0x1800b5b59  sub     rsp, 48h
0x1800b5b5d  mov     r14, r8
0x1800b5b60  mov     r15, rdx
0x1800b5b63  test    rdx, rdx
0x1800b5b66  jz      loc_1800B5CDA
0x1800b5b6c  test    r8, r8
0x1800b5b6f  jz      loc_1800B5CDA
0x1800b5b75  xor     esi, esi
0x1800b5b77  mov     [rdx], esi
0x1800b5b79  mov     [r8], rsi
0x1800b5b7c  mov     ecx, [rcx+2Ch]
0x1800b5b7f  test    ecx, ecx
0x1800b5b81  jz      loc_1800B5C52
0x1800b5b87  sub     ecx, 2
0x1800b5b8a  jz      short loc_1800B5C07
0x1800b5b8c  cmp     ecx, 1
0x1800b5b8f  jz      short loc_1800B5B9B
0x1800b5b91  mov     ebx, 86000011h
0x1800b5b96  jmp     loc_1800B5CDF
0x1800b5b9b  lea     rax, aCount_0; "Count"
0x1800b5ba2  mov     ecx, 18h; cb
0x1800b5ba7  mov     [rsp+78h+psz], rax
0x1800b5bac  lea     rax, aRevisionid; "RevisionId"
0x1800b5bb3  mov     [rsp+78h+var_50], rax
0x1800b5bb8  lea     rax, aData; "Data"
0x1800b5bbf  mov     [rsp+78h+var_48], rax
0x1800b5bc4  call    cs:__imp_CoTaskMemAlloc
0x1800b5bca  mov     rdi, rax
0x1800b5bcd  test    rax, rax
0x1800b5bd0  jz      loc_1800B5C7D
0x1800b5bd6  xorps   xmm0, xmm0
0x1800b5bd9  xor     eax, eax
0x1800b5bdb  movups  xmmword ptr [rdi], xmm0
0x1800b5bde  mov     [rdi+10h], rax
0x1800b5be2  cmp     esi, 3
0x1800b5be5  jnb     loc_1800B5CD0
0x1800b5beb  mov     rcx, [rsp+rsi*8+78h+psz]; psz
0x1800b5bf0  call    cs:__imp_SysAllocString
0x1800b5bf6  mov     [rdi+rsi*8], rax
0x1800b5bfa  test    rax, rax
0x1800b5bfd  jz      loc_1800B5CA7
0x1800b5c03  inc     esi
0x1800b5c05  jmp     short loc_1800B5BE2
0x1800b5c07  lea     rax, aMessages; "Messages"
0x1800b5c0e  mov     ecx, 8; cb
0x1800b5c13  mov     [rsp+78h+arg_8], rax
0x1800b5c1b  call    cs:__imp_CoTaskMemAlloc
0x1800b5c21  mov     rdi, rax
0x1800b5c24  test    rax, rax
0x1800b5c27  jz      short loc_1800B5C7D
0x1800b5c29  xor     eax, eax
0x1800b5c2b  mov     [rdi], rax
0x1800b5c2e  cmp     esi, 1
0x1800b5c31  jnb     loc_1800B5CD0
0x1800b5c37  mov     rcx, [rsp+rsi*8+78h+arg_8]; psz
0x1800b5c3f  call    cs:__imp_SysAllocString
0x1800b5c45  mov     [rdi+rsi*8], rax
0x1800b5c49  test    rax, rax
0x1800b5c4c  jz      short loc_1800B5CA7
0x1800b5c4e  inc     esi
0x1800b5c50  jmp     short loc_1800B5C2E
0x1800b5c52  lea     rax, aAuditinglevel; "AuditingLevel"
0x1800b5c59  mov     ecx, 10h; cb
0x1800b5c5e  mov     [rsp+78h+psz], rax
0x1800b5c63  lea     rax, aAuditing; "Auditing"
0x1800b5c6a  mov     [rsp+78h+var_50], rax
0x1800b5c6f  call    cs:__imp_CoTaskMemAlloc
0x1800b5c75  mov     rdi, rax
0x1800b5c78  test    rax, rax
0x1800b5c7b  jnz     short loc_1800B5C84
0x1800b5c7d  mov     ebx, 8007000Eh
0x1800b5c82  jmp     short loc_1800B5CDF
0x1800b5c84  xorps   xmm0, xmm0
0x1800b5c87  movups  xmmword ptr [rax], xmm0
0x1800b5c8a  cmp     esi, 2
0x1800b5c8d  jnb     short loc_1800B5CD0
0x1800b5c8f  mov     rcx, [rsp+rsi*8+78h+psz]; psz
0x1800b5c94  call    cs:__imp_SysAllocString
0x1800b5c9a  mov     [rdi+rsi*8], rax
0x1800b5c9e  test    rax, rax
0x1800b5ca1  jz      short loc_1800B5CA7
0x1800b5ca3  inc     esi
0x1800b5ca5  jmp     short loc_1800B5C8A
0x1800b5ca7  xor     ebp, ebp
0x1800b5ca9  mov     ebx, 8007000Eh
0x1800b5cae  mov     r14, rdi
0x1800b5cb1  test    esi, esi
0x1800b5cb3  jz      short loc_1800B5CC5
0x1800b5cb5  mov     rcx, [r14+rbp*8]; bstrString
0x1800b5cb9  call    cs:__imp_SysFreeString
0x1800b5cbf  inc     ebp
0x1800b5cc1  cmp     ebp, esi
0x1800b5cc3  jb      short loc_1800B5CB5
0x1800b5cc5  mov     rcx, rdi; pv
0x1800b5cc8  call    cs:__imp_CoTaskMemFree
0x1800b5cce  jmp     short loc_1800B5CDF
0x1800b5cd0  mov     [r14], rdi
0x1800b5cd3  xor     ebx, ebx
0x1800b5cd5  mov     [r15], esi
0x1800b5cd8  jmp     short loc_1800B5CDF
0x1800b5cda  mov     ebx, 80070057h
0x1800b5cdf  mov     eax, ebx
0x1800b5ce1  add     rsp, 48h
0x1800b5ce5  pop     r15
0x1800b5ce7  pop     r14
0x1800b5ce9  pop     rdi
0x1800b5cea  pop     rsi
0x1800b5ceb  pop     rbp
0x1800b5cec  pop     rbx
0x1800b5ced  retn
```

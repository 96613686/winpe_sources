# FindProgIdMoniker

- ea: `0x18005ba40`
- end: `0x18005bcd8`
- name: `FindProgIdMoniker`
- size: `664`
- prototype: `HRESULT __fastcall(IBindCtx *pbc, const wchar_t *pszDisplayName, unsigned int *pcchEaten, IMoniker **ppmk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008e20`

## callees

- `0x180052390`
- `0x18005ba40`
- `0x18005bce0`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005bc98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005bc98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bb73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005bb73`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18005bc24`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18005bc24`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18005bbca`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18005bbca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005bc4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005bc4a`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18005ba9d`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18005ba9d`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18005bbde`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18005bbde`

## pseudocode

```c
__int64 __fastcall FindProgIdMoniker(
        IBindCtx *pbc,
        const wchar_t *pszDisplayName,
        unsigned int *pcchEaten,
        IMoniker **ppmk)
{
  _DWORD *ReservedForOle; // rax
  HRESULT v6; // edi
  int v7; // ebx
  const wchar_t *v8; // r12
  const wchar_t *v9; // rsi
  int v10; // ecx
  _DWORD *v11; // rcx
  __int64 v13; // r8
  __int64 v14; // r14
  OLECHAR *v15; // rax
  OLECHAR *v16; // r15
  _DWORD *v17; // rcx
  _DWORD *v18; // rcx
  IParseDisplayName *pPDN; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v20; // [rsp+38h] [rbp-40h] BYREF
  IMoniker **v21; // [rsp+40h] [rbp-38h]
  const wchar_t *v22; // [rsp+48h] [rbp-30h]
  IBindCtx *v23; // [rsp+50h] [rbp-28h]
  _GUID cid; // [rsp+58h] [rbp-20h] BYREF

  pPDN = 0;
  cid = 0;
  v21 = ppmk;
  v22 = pszDisplayName;
  v23 = pbc;
  ReservedForOle = NtCurrentTeb()->ReservedForOle;
  v20 = ReservedForOle;
  if ( !ReservedForOle )
  {
    v6 = InternalTlsAllocData(&v20);
    if ( v6 < 0 )
    {
      v7 = (int)pPDN;
      goto LABEL_26;
    }
    ReservedForOle = v20;
    ppmk = v21;
    pszDisplayName = v22;
  }
  v7 = ReservedForOle[128];
  ReservedForOle[128] = v7 | 1;
  if ( (v20[5] & 0x2000000) != 0 )
  {
    v6 = -2147467231;
LABEL_26:
    v18 = NtCurrentTeb()->ReservedForOle;
    if ( v18 )
      v18[128] = v7;
    return (unsigned int)v6;
  }
  *pcchEaten = 0;
  v8 = pszDisplayName + 1;
  *ppmk = 0;
  v9 = pszDisplayName + 1;
  v10 = pszDisplayName[1];
  if ( (unsigned __int16)(v10 - 48) > 9u )
  {
    while ( 1 )
    {
      if ( (unsigned __int16)(v10 - 46) > 0x2Cu || (v13 = 0x1FFFFFF80FFDLL, !_bittest64(&v13, (unsigned int)(v10 - 46))) )
      {
        if ( (unsigned __int16)(v10 - 97) > 0x19u )
          break;
      }
      v10 = *++v9;
    }
    v14 = v9 - pszDisplayName;
    v15 = (OLECHAR *)HeapAlloc(g_hHeap, 0, 2LL * (int)v14);
    v16 = v15;
    if ( v15 )
    {
      memcpy_0(v15, v8, 2LL * (int)v14 - 2);
      v16[(int)v14 - 1] = 0;
      v6 = CLSIDFromProgID(v16, &cid);
      if ( !v6 )
      {
        if ( CoIsOle1Class(&cid) )
        {
          v6 = Parse10DisplayName(&cid, v9 + 1, pcchEaten, v14 + 1, v21);
        }
        else if ( !CoGetClassObject(&cid, 0x417u, 0, &IID_IParseDisplayName, (LPVOID *)&pPDN)
               || (v6 = CoCreateInstance(&cid, 0, 0x403u, &IID_IParseDisplayName, (LPVOID *)&pPDN)) == 0 )
        {
          v6 = ((__int64 (__fastcall *)(IParseDisplayName *, IBindCtx *, const wchar_t *, unsigned int *, IMoniker **))pPDN->lpVtbl[1].QueryInterface)(
                 pPDN,
                 v23,
                 v22,
                 pcchEaten,
                 v21);
          ((void (__fastcall *)(IParseDisplayName *))pPDN->lpVtbl->Release)(pPDN);
        }
      }
      HeapFree(g_hHeap, 0, v16);
      goto LABEL_26;
    }
    v17 = NtCurrentTeb()->ReservedForOle;
    if ( v17 )
      v17[128] = v7;
    return 2147942414LL;
  }
  else
  {
    v11 = NtCurrentTeb()->ReservedForOle;
    if ( v11 )
      v11[128] = v7;
    return 2147746276LL;
  }
}

```

## disassembly

```asm
0x18005ba40  push    rbp
0x18005ba42  push    rbx
0x18005ba43  push    rsi
0x18005ba44  push    rdi
0x18005ba45  push    r12
0x18005ba47  push    r13
0x18005ba49  push    r14
0x18005ba4b  push    r15
0x18005ba4d  mov     rbp, rsp
0x18005ba50  sub     rsp, 78h
0x18005ba54  mov     rax, cs:__security_cookie
0x18005ba5b  xor     rax, rsp
0x18005ba5e  mov     [rbp+var_10], rax
0x18005ba62  mov     [rbp+pPDN], 0
0x18005ba6a  xorps   xmm0, xmm0
0x18005ba6d  movups  xmmword ptr [rbp+cid.Data1], xmm0
0x18005ba71  mov     rax, gs:30h
0x18005ba7a  mov     r13, pcchEaten
0x18005ba7d  mov     [rbp+var_38], ppmk
0x18005ba81  mov     [rbp+var_30], pszDisplayName
0x18005ba85  mov     [rbp+var_28], pbc
0x18005ba89  mov     rax, [rax+1758h]
0x18005ba90  mov     [rbp+var_40], rax
0x18005ba94  test    rax, rax
0x18005ba97  jnz     short loc_18005BAB5
0x18005ba99  lea     pbc, [rbp+var_40]
0x18005ba9d  call    cs:__imp_InternalTlsAllocData
0x18005baa3  mov     edi, eax
0x18005baa5  test    eax, eax
0x18005baa7  js      short loc_18005BADD
0x18005baa9  mov     rax, [rbp+var_40]
0x18005baad  mov     ppmk, [rbp+var_38]
0x18005bab1  mov     pszDisplayName, [rbp+var_30]
0x18005bab5  mov     ebx, [rax+200h]
0x18005babb  mov     ecx, ebx
0x18005babd  or      ecx, 1
0x18005bac0  mov     [rax+200h], ecx
0x18005bac6  mov     rax, [rbp+var_40]
0x18005baca  test    dword ptr [rax+14h], 2000000h
0x18005bad1  jz      short loc_18005BAE5
0x18005bad3  mov     edi, 80004021h
0x18005bad8  jmp     loc_18005BC9E
0x18005badd  mov     ebx, dword ptr [rbp+pPDN]
0x18005bae0  jmp     loc_18005BC9E
0x18005bae5  mov     dword ptr [r13+0], 0
0x18005baed  lea     r12, [pszDisplayName+2]
0x18005baf1  mov     qword ptr [ppmk], 0
0x18005baf8  mov     rsi, r12
0x18005bafb  movzx   ecx, word ptr [r12]
0x18005bb00  lea     eax, [pbc-30h]
0x18005bb03  cmp     ax, 9
0x18005bb07  ja      short loc_18005BB2E
0x18005bb09  mov     rax, gs:30h
0x18005bb12  mov     pbc, [rax+1758h]
0x18005bb19  test    pbc, pbc
0x18005bb1c  jz      short loc_18005BB24
0x18005bb1e  mov     [pbc+200h], ebx
0x18005bb24  mov     eax, 800401E4h
0x18005bb29  jmp     loc_18005BCBB
0x18005bb2e  lea     eax, [pbc-2Eh]
0x18005bb31  cmp     ax, 2Ch ; ','
0x18005bb35  ja      short loc_18005BB47
0x18005bb37  mov     pcchEaten, 1FFFFFF80FFDh
0x18005bb41  bt      pcchEaten, rax
0x18005bb45  jb      short loc_18005BB51
0x18005bb47  sub     cx, 61h ; 'a'
0x18005bb4b  cmp     cx, 19h
0x18005bb4f  ja      short loc_18005BB5A
0x18005bb51  add     rsi, 2
0x18005bb55  movzx   ecx, word ptr [rsi]
0x18005bb58  jmp     short loc_18005BB2E
0x18005bb5a  mov     pbc, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005bb61  mov     r14, rsi
0x18005bb64  sub     r14, pszDisplayName
0x18005bb67  xor     edx, edx; dwFlags
0x18005bb69  sar     r14, 1
0x18005bb6c  movsxd  rdi, r14d
0x18005bb6f  lea     pcchEaten, [rdi+rdi]; dwBytes
0x18005bb73  call    cs:__imp_HeapAlloc
0x18005bb79  mov     r15, rax
0x18005bb7c  test    rax, rax
0x18005bb7f  jnz     short loc_18005BBA6
0x18005bb81  mov     rax, gs:30h
0x18005bb8a  mov     pbc, [rax+1758h]
0x18005bb91  test    pbc, pbc
0x18005bb94  jz      short loc_18005BB9C
0x18005bb96  mov     [pbc+200h], ebx
0x18005bb9c  mov     eax, 8007000Eh
0x18005bba1  jmp     loc_18005BCBB
0x18005bba6  lea     rdi, ds:0FFFFFFFFFFFFFFFEh[rdi*2]
0x18005bbae  mov     pszDisplayName, r12; Src
0x18005bbb1  mov     pcchEaten, rdi; Size
0x18005bbb4  mov     pbc, r15; void *
0x18005bbb7  call    memcpy_0
0x18005bbbc  xor     eax, eax
0x18005bbbe  lea     pszDisplayName, [rbp+cid]; lpclsid
0x18005bbc2  mov     pbc, r15; lpszProgID
0x18005bbc5  mov     [rdi+r15], ax
0x18005bbca  call    cs:__imp_CLSIDFromProgID
0x18005bbd0  mov     edi, eax
0x18005bbd2  test    eax, eax
0x18005bbd4  jnz     $errRet_18
0x18005bbda  lea     pbc, [rbp+cid]; rclsid
0x18005bbde  call    cs:__imp_CoIsOle1Class
0x18005bbe4  lea     pbc, [rbp+cid]; rclsid
0x18005bbe8  test    eax, eax
0x18005bbea  jz      short loc_18005BC0C
0x18005bbec  mov     pcchEaten, [rbp+var_38]
0x18005bbf0  lea     r9d, [r14+1]; cchEatenSoFar
0x18005bbf4  mov     [rsp+78h+ppv], pcchEaten; ppmk
0x18005bbf9  lea     pszDisplayName, [rsi+2]; szDisplayName
0x18005bbfd  mov     pcchEaten, r13; pcchEaten
0x18005bc00  call    Parse10DisplayName
0x18005bc05  mov     edi, eax
0x18005bc07  jmp     $errRet_18
0x18005bc0c  lea     rax, [rbp+pPDN]
0x18005bc10  xor     r8d, r8d; pvReserved
0x18005bc13  lea     ppmk, IID_IParseDisplayName; riid
0x18005bc1a  mov     [rsp+78h+ppv], rax; ppv
0x18005bc1f  mov     edx, 417h; dwClsContext
0x18005bc24  call    cs:__imp_CoGetClassObject
0x18005bc2a  test    eax, eax
0x18005bc2c  jz      short loc_18005BC56
0x18005bc2e  lea     rax, [rbp+pPDN]
0x18005bc32  xor     edx, edx; pUnkOuter
0x18005bc34  lea     ppmk, IID_IParseDisplayName; riid
0x18005bc3b  mov     [rsp+78h+ppv], rax; ppv
0x18005bc40  mov     r8d, 403h; dwClsContext
0x18005bc46  lea     pbc, [rbp+cid]; rclsid
0x18005bc4a  call    cs:__imp_CoCreateInstance
0x18005bc50  mov     edi, eax
0x18005bc52  test    eax, eax
0x18005bc54  jnz     short $errRet_18
0x18005bc56  mov     pbc, [rbp+pPDN]
0x18005bc5a  mov     ppmk, r13
0x18005bc5d  mov     pcchEaten, [rbp+var_38]
0x18005bc61  mov     pszDisplayName, [rbp+var_28]
0x18005bc65  mov     [rsp+78h+ppv], pcchEaten
0x18005bc6a  mov     rax, [pbc]
0x18005bc6d  mov     pcchEaten, [rbp+var_30]
0x18005bc71  mov     rax, [rax+18h]
0x18005bc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc7a  mov     pbc, [rbp+pPDN]
0x18005bc7e  mov     edi, eax
0x18005bc80  mov     rax, [pbc]
0x18005bc83  mov     rax, [rax+10h]
0x18005bc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc8c  mov     pbc, cs:?g_hHeap@@3QEAXEA; hHeap
0x18005bc93  mov     pcchEaten, r15; lpMem
0x18005bc96  xor     edx, edx; dwFlags
0x18005bc98  call    cs:__imp_HeapFree
0x18005bc9e  mov     rax, gs:30h
0x18005bca7  mov     pbc, [rax+1758h]
0x18005bcae  test    pbc, pbc
0x18005bcb1  jz      short loc_18005BCB9
0x18005bcb3  mov     [pbc+200h], ebx
0x18005bcb9  mov     eax, edi
0x18005bcbb  mov     pbc, [rbp+var_10]
0x18005bcbf  xor     pbc, rsp; StackCookie
0x18005bcc2  call    __security_check_cookie
0x18005bcc7  add     rsp, 78h
0x18005bccb  pop     r15
0x18005bccd  pop     r14
0x18005bccf  pop     r13
0x18005bcd1  pop     r12
0x18005bcd3  pop     rdi
0x18005bcd4  pop     rsi
0x18005bcd5  pop     rbx
0x18005bcd6  pop     rbp
0x18005bcd7  retn
```

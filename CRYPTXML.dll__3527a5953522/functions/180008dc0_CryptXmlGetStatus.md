# CryptXmlGetStatus

- ea: `0x180008dc0`
- end: `0x180008ff3`
- name: `CryptXmlGetStatus`
- size: `563`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, CRYPT_XML_STATUS *pStatus)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008dc0`

## callees

- `0x1800070d0`
- `0x180008dc0`
- `0x180009478`
- `0x180014ce0`
- `0x180019010`

## string_xrefs

- `0x180008f64`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`
- `0x180008fa9`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetStatus(HCRYPTXML hCryptXml, CRYPT_XML_STATUS *pStatus)
{
  int Status; // ebp
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // r14
  void (__fastcall *v8)(__int64); // rax
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // r14
  void (__fastcall *v12)(__int64); // rax
  __int64 i; // rsi
  __int64 v14; // rax
  const char *v15; // rax
  void (__fastcall *v16)(HCRYPTXML); // rax
  const char *v17; // r8
  const char *v18; // rax
  bool v19; // zf
  CRYPT_XML_STATUS pStatusa; // [rsp+20h] [rbp-28h] BYREF

  if ( hCryptXml && pStatus )
  {
    Status = 0;
    I_CryptXmlLock(hCryptXml);
    *(_QWORD *)&pStatus->cbSize = *((_QWORD *)hCryptXml + 8);
    pStatus->dwInfoStatus = *((_DWORD *)hCryptXml + 18);
    switch ( *(_DWORD *)hCryptXml )
    {
      case 0x44444444:
        if ( *(_DWORD *)(*((_QWORD *)hCryptXml + 17) + 40LL) )
          pStatus->dwInfoStatus |= 8u;
        v5 = *((_QWORD *)hCryptXml + 17);
        if ( *(_DWORD *)(v5 + 40) )
        {
          v6 = 0;
          do
          {
            v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 48) + 8 * v6) + 8LL);
            I_CryptXmlLock(v7);
            pStatus->dwErrorStatus |= *(_DWORD *)(v7 + 68);
            if ( (*(_DWORD *)(v7 + 72) & 8) == 0 )
              pStatus->dwInfoStatus &= ~8u;
            v8 = *(void (__fastcall **)(__int64))(v7 + 128);
            if ( v8 )
              v8(v7);
            v5 = *((_QWORD *)hCryptXml + 17);
            v6 = (unsigned int)(v6 + 1);
          }
          while ( (unsigned int)v6 < *(_DWORD *)(v5 + 40) );
        }
        break;
      case 0x44444442:
        if ( *(_DWORD *)(*((_QWORD *)hCryptXml + 18) + 104LL) )
          pStatus->dwInfoStatus |= 8u;
        v9 = *((_QWORD *)hCryptXml + 18);
        if ( *(_DWORD *)(v9 + 104) )
        {
          v10 = 0;
          do
          {
            v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 112) + 8 * v10) + 8LL);
            I_CryptXmlLock(v11);
            pStatus->dwErrorStatus |= *(_DWORD *)(v11 + 68);
            if ( (*(_DWORD *)(v11 + 72) & 8) == 0 )
              pStatus->dwInfoStatus &= ~8u;
            v12 = *(void (__fastcall **)(__int64))(v11 + 128);
            if ( v12 )
              v12(v11);
            v9 = *((_QWORD *)hCryptXml + 18);
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < *(_DWORD *)(v9 + 104) );
        }
        break;
      case 0x44444441:
        if ( *(_DWORD *)(*((_QWORD *)hCryptXml + 17) + 24LL) )
          pStatus->dwInfoStatus |= 0x10000u;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v14 = *((_QWORD *)hCryptXml + 17);
          if ( (unsigned int)i >= *(_DWORD *)(v14 + 24) )
            break;
          *(_QWORD *)&pStatusa.cbSize = 12;
          pStatusa.dwInfoStatus = 0;
          Status = CryptXmlGetStatus(*(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(v14 + 32) + 8 * i) + 8LL), &pStatusa);
          if ( Status < 0 )
          {
            v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", Status, v15, 429);
            goto LABEL_35;
          }
          pStatus->dwErrorStatus |= pStatusa.dwErrorStatus;
          if ( (pStatusa.dwInfoStatus & 0x10000) == 0 )
            pStatus->dwInfoStatus &= ~0x10000u;
        }
        break;
    }
LABEL_35:
    v16 = (void (__fastcall *)(HCRYPTXML))*((_QWORD *)hCryptXml + 16);
    if ( v16 )
      v16(hCryptXml);
  }
  else
  {
    Status = -2147024809;
    v17 = "";
    while ( 1 )
    {
      v18 = v17--;
      v19 = *v17 == 92;
      if ( *v17 == 92 )
        break;
      if ( v17 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp" )
      {
        v19 = *v17 == 92;
        break;
      }
    }
    if ( v19 )
      v17 = v18;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v17, 350);
  }
  return Status;
}

```

## disassembly

```asm
0x180008dc0  mov     [rsp+arg_10], rbx
0x180008dc5  mov     [rsp+arg_18], rbp
0x180008dca  push    rsi
0x180008dcb  push    rdi
0x180008dcc  push    r14
0x180008dce  sub     rsp, 30h
0x180008dd2  mov     rbx, rdx
0x180008dd5  mov     rdi, rcx
0x180008dd8  test    rcx, rcx
0x180008ddb  jz      loc_180008F9D
0x180008de1  test    rdx, rdx
0x180008de4  jz      loc_180008F9D
0x180008dea  xor     ebp, ebp
0x180008dec  call    I_CryptXmlLock
0x180008df1  movsd   xmm0, qword ptr [rdi+40h]
0x180008df6  movsd   qword ptr [rbx], xmm0
0x180008dfa  mov     eax, [rdi+48h]
0x180008dfd  mov     [rbx+8], eax
0x180008e00  cmp     dword ptr [rdi], 44444444h
0x180008e06  jnz     short loc_180008E78
0x180008e08  mov     rax, [rdi+88h]
0x180008e0f  cmp     [rax+28h], ebp
0x180008e12  jbe     short loc_180008E18
0x180008e14  or      dword ptr [rbx+8], 8
0x180008e18  mov     rax, [rdi+88h]
0x180008e1f  cmp     [rax+28h], ebp
0x180008e22  jbe     loc_180008F87
0x180008e28  xor     esi, esi
0x180008e2a  mov     rax, [rax+30h]
0x180008e2e  mov     rcx, [rax+rsi*8]
0x180008e32  mov     r14, [rcx+8]
0x180008e36  mov     rcx, r14
0x180008e39  call    I_CryptXmlLock
0x180008e3e  mov     eax, [r14+44h]
0x180008e42  or      [rbx+4], eax
0x180008e45  mov     eax, [r14+48h]
0x180008e49  test    al, 8
0x180008e4b  jnz     short loc_180008E51
0x180008e4d  and     dword ptr [rbx+8], 0FFFFFFF7h
0x180008e51  mov     rax, [r14+80h]
0x180008e58  test    rax, rax
0x180008e5b  jz      short loc_180008E65
0x180008e5d  mov     rcx, r14
0x180008e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e65  mov     rax, [rdi+88h]
0x180008e6c  inc     esi
0x180008e6e  cmp     esi, [rax+28h]
0x180008e71  jb      short loc_180008E2A
0x180008e73  jmp     loc_180008F87
0x180008e78  cmp     dword ptr [rdi], 44444442h
0x180008e7e  jnz     short loc_180008EF0
0x180008e80  mov     rax, [rdi+90h]
0x180008e87  cmp     [rax+68h], ebp
0x180008e8a  jbe     short loc_180008E90
0x180008e8c  or      dword ptr [rbx+8], 8
0x180008e90  mov     rax, [rdi+90h]
0x180008e97  cmp     [rax+68h], ebp
0x180008e9a  jbe     loc_180008F87
0x180008ea0  xor     esi, esi
0x180008ea2  mov     rax, [rax+70h]
0x180008ea6  mov     rcx, [rax+rsi*8]
0x180008eaa  mov     r14, [rcx+8]
0x180008eae  mov     rcx, r14
0x180008eb1  call    I_CryptXmlLock
0x180008eb6  mov     eax, [r14+44h]
0x180008eba  or      [rbx+4], eax
0x180008ebd  mov     eax, [r14+48h]
0x180008ec1  test    al, 8
0x180008ec3  jnz     short loc_180008EC9
0x180008ec5  and     dword ptr [rbx+8], 0FFFFFFF7h
0x180008ec9  mov     rax, [r14+80h]
0x180008ed0  test    rax, rax
0x180008ed3  jz      short loc_180008EDD
0x180008ed5  mov     rcx, r14
0x180008ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008edd  mov     rax, [rdi+90h]
0x180008ee4  inc     esi
0x180008ee6  cmp     esi, [rax+68h]
0x180008ee9  jb      short loc_180008EA2
0x180008eeb  jmp     loc_180008F87
0x180008ef0  cmp     dword ptr [rdi], 44444441h
0x180008ef6  jnz     loc_180008F87
0x180008efc  mov     rax, [rdi+88h]
0x180008f03  mov     r14d, 10000h
0x180008f09  cmp     [rax+18h], ebp
0x180008f0c  jbe     short loc_180008F12
0x180008f0e  or      [rbx+8], r14d
0x180008f12  xor     esi, esi
0x180008f14  mov     rax, [rdi+88h]
0x180008f1b  cmp     esi, [rax+18h]
0x180008f1e  jnb     short loc_180008F87
0x180008f20  mov     qword ptr [rsp+48h+pStatus.cbSize], 0Ch
0x180008f29  lea     rdx, [rsp+48h+pStatus]; pStatus
0x180008f2e  mov     [rsp+48h+pStatus.dwInfoStatus], 0
0x180008f36  mov     rax, [rax+20h]
0x180008f3a  mov     rcx, [rax+rsi*8]
0x180008f3e  mov     rcx, [rcx+8]; hCryptXml
0x180008f42  call    CryptXmlGetStatus
0x180008f47  mov     ebp, eax
0x180008f49  test    eax, eax
0x180008f4b  js      short loc_180008F64
0x180008f4d  mov     ecx, [rsp+48h+pStatus.dwErrorStatus]
0x180008f51  or      [rbx+4], ecx
0x180008f54  test    [rsp+48h+pStatus.dwInfoStatus], r14d
0x180008f59  jnz     short loc_180008F60
0x180008f5b  btr     dword ptr [rbx+8], 10h
0x180008f60  inc     esi
0x180008f62  jmp     short loc_180008F14
0x180008f64  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008f6b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180008f70  mov     r8, rax
0x180008f73  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008f7a  mov     edx, ebp
0x180008f7c  mov     r9d, 1ADh
0x180008f82  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008f87  mov     rax, [rdi+80h]
0x180008f8e  test    rax, rax
0x180008f91  jz      short loc_180008FDD
0x180008f93  mov     rcx, rdi
0x180008f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9b  jmp     short loc_180008FDD
0x180008f9d  mov     ebp, 80070057h
0x180008fa2  lea     r8, aOnecoreDsSecur_7+30h; ""
0x180008fa9  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008fb0  mov     rax, r8
0x180008fb3  dec     r8
0x180008fb6  cmp     byte ptr [r8], 5Ch ; '\'
0x180008fba  jz      short loc_180008FC5
0x180008fbc  cmp     r8, rcx
0x180008fbf  ja      short loc_180008FB0
0x180008fc1  cmp     byte ptr [r8], 5Ch ; '\'
0x180008fc5  cmovz   r8, rax
0x180008fc9  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180008fd0  mov     r9d, 15Eh
0x180008fd6  mov     edx, ebp
0x180008fd8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180008fdd  mov     rbx, [rsp+48h+arg_10]
0x180008fe2  mov     eax, ebp
0x180008fe4  mov     rbp, [rsp+48h+arg_18]
0x180008fe9  add     rsp, 30h
0x180008fed  pop     r14
0x180008fef  pop     rdi
0x180008ff0  pop     rsi
0x180008ff1  retn
```

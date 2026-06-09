# I_CryptXmlExportKeyValueFromHandle(unsigned __int64,ushort const *,CRYPT_XML_CHARSET,_CRYPT_XML_KEY_VALUE * *)

- ea: `0x18000b1e0`
- end: `0x18000b2f6`
- name: `?I_CryptXmlExportKeyValueFromHandle@@YAJ_KPEBGW4CRYPT_XML_CHARSET@@PEAPEAU_CRYPT_XML_KEY_VALUE@@@Z`
- size: `278`
- prototype: `int(unsigned __int64, const unsigned __int16 *, enum CRYPT_XML_CHARSET, struct _CRYPT_XML_KEY_VALUE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a310`

## callees

- `0x1800070d0`
- `0x18000b1a0`
- `0x18000b1e0`
- `0x18000b300`
- `0x180014ce0`
- `0x18001860d`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2dc`

## string_xrefs

- `0x18000b22e`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000b26b`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlExportKeyValueFromHandle(
        __int64 a1,
        const unsigned __int16 *a2,
        enum CRYPT_XML_CHARSET a3,
        struct _CRYPT_XML_KEY_VALUE **a4)
{
  __int64 (__fastcall *EncodeKeyValueProc)(__int64, __int64, void **, void *); // rax
  int v7; // ebx
  __int64 v8; // rcx
  const char *v9; // rax
  struct _CRYPT_XML_KEY_VALUE *v10; // rax
  const char *v11; // rax
  void *v12; // rdi
  HANDLE ProcessHeap; // rax
  void *Src[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)Src = 0;
  EncodeKeyValueProc = (__int64 (__fastcall *)(__int64, __int64, void **, void *))GetEncodeKeyValueProc(a2);
  if ( EncodeKeyValueProc )
  {
    v7 = EncodeKeyValueProc(a1, 1, Src, &CRYPT_XML_ENCODE_ALGORITHM_CALLBACK);
    if ( v7 >= 0 )
    {
      v10 = (struct _CRYPT_XML_KEY_VALUE *)CryptXmlAlloc(v8, LODWORD(Src[1]) + 120LL);
      *a4 = v10;
      if ( v10 )
      {
        v10->dwType = 4;
        v10->DSAKeyValue.P.pbData = (BYTE *)&v10[1];
        v10->Custom.cbData = (ULONG)Src[1];
        memcpy_0(&v10[1], Src[0], LODWORD(Src[1]));
        v7 = 0;
      }
      else
      {
        v7 = -2147024882;
        v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v11, 1942);
      }
    }
    else
    {
      v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v9, 1927);
    }
  }
  else
  {
    v7 = -2147467263;
  }
  v12 = Src[0];
  if ( Src[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, v12);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b1e0  mov     [rsp+arg_0], rbx
0x18000b1e5  push    rdi
0x18000b1e6  sub     rsp, 40h
0x18000b1ea  mov     rbx, rcx
0x18000b1ed  xorps   xmm0, xmm0
0x18000b1f0  mov     rcx, rdx; lpString2
0x18000b1f3  mov     rdi, r9
0x18000b1f6  movups  xmmword ptr [rsp+48h+Src], xmm0
0x18000b1fb  call    _GetEncodeKeyValueProc
0x18000b200  test    rax, rax
0x18000b203  jnz     short loc_18000B20F
0x18000b205  mov     ebx, 80004001h
0x18000b20a  jmp     loc_18000B2BB
0x18000b20f  lea     r9, CRYPT_XML_ENCODE_ALGORITHM_CALLBACK
0x18000b216  mov     edx, 1
0x18000b21b  lea     r8, [rsp+48h+Src]
0x18000b220  mov     rcx, rbx
0x18000b223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b228  mov     ebx, eax
0x18000b22a  test    eax, eax
0x18000b22c  jns     short loc_18000B253
0x18000b22e  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b235  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b23a  mov     r8, rax
0x18000b23d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000b244  mov     edx, ebx
0x18000b246  mov     r9d, 787h
0x18000b24c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000b251  jmp     short loc_18000B2BB
0x18000b253  mov     edx, dword ptr [rsp+48h+Src+8]
0x18000b257  add     rdx, 78h ; 'x'
0x18000b25b  call    CryptXmlAlloc
0x18000b260  mov     [rdi], rax
0x18000b263  mov     rdx, rax
0x18000b266  test    rax, rax
0x18000b269  jnz     short loc_18000B295
0x18000b26b  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b272  mov     ebx, 8007000Eh
0x18000b277  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b27c  mov     r8, rax
0x18000b27f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000b286  mov     edx, ebx
0x18000b288  mov     r9d, 796h
0x18000b28e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000b293  jmp     short loc_18000B2BB
0x18000b295  mov     dword ptr [rax], 4
0x18000b29b  lea     rcx, [rax+78h]; void *
0x18000b29f  mov     [rax+10h], rcx
0x18000b2a3  mov     eax, dword ptr [rsp+48h+Src+8]
0x18000b2a7  mov     [rdx+0Ch], eax
0x18000b2aa  mov     r8d, dword ptr [rsp+48h+Src+8]; Size
0x18000b2af  mov     rdx, [rsp+48h+Src]; Src
0x18000b2b4  call    memcpy_0
0x18000b2b9  xor     ebx, ebx
0x18000b2bb  mov     rdi, [rsp+48h+Src]
0x18000b2c0  test    rdi, rdi
0x18000b2c3  jz      short loc_18000B2E8
0x18000b2c5  call    cs:__imp_GetProcessHeap
0x18000b2cc  nop     dword ptr [rax+rax+00h]
0x18000b2d1  mov     r8, rdi; lpMem
0x18000b2d4  mov     edx, 8; dwFlags
0x18000b2d9  mov     rcx, rax; hHeap
0x18000b2dc  call    cs:__imp_HeapFree
0x18000b2e3  nop     dword ptr [rax+rax+00h]
0x18000b2e8  mov     eax, ebx
0x18000b2ea  mov     rbx, [rsp+48h+arg_0]
0x18000b2ef  add     rsp, 40h
0x18000b2f3  pop     rdi
0x18000b2f4  retn
```

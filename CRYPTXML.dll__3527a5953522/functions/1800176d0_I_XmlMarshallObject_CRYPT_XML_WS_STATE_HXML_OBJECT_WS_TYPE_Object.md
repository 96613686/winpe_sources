# I_XmlMarshallObject(_CRYPT_XML_WS_STATE *,_HXML_OBJECT *,WS_TYPE_Object *)

- ea: `0x1800176d0`
- end: `0x180017930`
- name: `?I_XmlMarshallObject@@YAJPEAU_CRYPT_XML_WS_STATE@@PEAU_HXML_OBJECT@@PEAUWS_TYPE_Object@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(struct _CRYPT_XML_WS_STATE *, struct _HXML_OBJECT *, struct WS_TYPE_Object *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c75c`

## callees

- `0x1800070d0`
- `0x180010730`
- `0x180014ce0`
- `0x1800176d0`
- `0x180017938`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001778f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800177b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800177de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001778f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800177b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800177de`
- `webservices!WsAlloc` at `0x180017732`
- `webservices!WsAlloc` at `0x180017811`
- `webservices!WsAlloc` at `0x180017732`
- `webservices!WsAlloc` at `0x180017811`

## string_xrefs

- `0x180017744`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017823`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017891`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800178ca`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallObject(WS_HEAP **a1, struct _HXML_OBJECT *a2, struct WS_TYPE_Object *a3)
{
  __int64 v3; // rdi
  _OWORD *v7; // rax
  HRESULT v8; // ebx
  const char *v9; // rax
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 i; // r14
  const struct _CRYPT_XML_BLOB *v18; // rcx
  void *ptr; // [rsp+58h] [rbp+38h] BYREF

  v3 = *((_QWORD *)a2 + 17);
  ptr = 0;
  memset_0(a3, 0, 0x48u);
  v7 = (_OWORD *)*((_QWORD *)a2 + 18);
  if ( v7 )
    goto LABEL_23;
  v8 = WsAlloc(a1[6], 0x48u, &ptr, *a1);
  if ( v8 >= 0 )
  {
    memset_0(ptr, 0, 0x48u);
    v11 = *(_QWORD *)(v3 + 16);
    if ( v11 )
    {
      *((_QWORD *)ptr + 1) = v11;
      v12 = lstrlenW(*(LPCWSTR *)(v3 + 16));
      *(_DWORD *)ptr = v12;
    }
    v13 = *(_QWORD *)(v3 + 24);
    if ( v13 )
    {
      *((_QWORD *)ptr + 3) = v13;
      v14 = lstrlenW(*(LPCWSTR *)(v3 + 24));
      *((_DWORD *)ptr + 4) = v14;
    }
    v15 = *(_QWORD *)(v3 + 32);
    if ( v15 )
    {
      *((_QWORD *)ptr + 5) = v15;
      v16 = lstrlenW(*(LPCWSTR *)(v3 + 32));
      *((_DWORD *)ptr + 8) = v16;
    }
    if ( *(_DWORD *)(v3 + 40) )
    {
      v8 = WsAlloc(a1[6], 104LL * *(unsigned int *)(v3 + 40), (void **)ptr + 7, *a1);
      if ( v8 < 0 )
      {
        v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v10 = 2617;
        goto LABEL_4;
      }
      *((_DWORD *)ptr + 12) = *(_DWORD *)(v3 + 40);
      memset_0(*((void **)ptr + 7), 0, 104LL * *(unsigned int *)(v3 + 40));
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v3 + 40); i = (unsigned int)(i + 1) )
      {
        v8 = I_XmlMarshallReference(
               *(const struct _HXML_REFERENCE **)(*(_QWORD *)(*(_QWORD *)(v3 + 48) + 8 * i) + 8LL),
               (struct _CRYPT_XML_WS_STATE *)a1,
               (struct WS_TYPE_Reference *)(*((_QWORD *)ptr + 7) + 104LL * (unsigned int)i));
        if ( v8 < 0 )
        {
          v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          v10 = 2635;
          goto LABEL_4;
        }
      }
    }
    v18 = (const struct _CRYPT_XML_BLOB *)*((_QWORD *)a2 + 19);
    if ( v18 )
    {
      v8 = I_XmlSetEncoded(v18, (struct _CRYPT_XML_WS_STATE *)a1, (struct _WS_XML_BUFFER **)ptr + 8);
      if ( v8 < 0 )
      {
        v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v10 = 2650;
        goto LABEL_4;
      }
    }
    v7 = ptr;
    *((_QWORD *)a2 + 18) = ptr;
LABEL_23:
    v8 = 0;
    *(_OWORD *)a3 = *v7;
    *((_OWORD *)a3 + 1) = v7[1];
    *((_OWORD *)a3 + 2) = v7[2];
    *((_OWORD *)a3 + 3) = v7[3];
    *((_QWORD *)a3 + 8) = *((_QWORD *)v7 + 8);
    return (unsigned int)v8;
  }
  v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
  v10 = 2583;
LABEL_4:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v8, v9, v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800176d0  mov     [rsp-28h+arg_0], rbx
0x1800176d5  mov     [rsp-28h+arg_10], rsi
0x1800176da  push    rbp
0x1800176db  push    rdi
0x1800176dc  push    r13
0x1800176de  push    r14
0x1800176e0  push    r15
0x1800176e2  mov     rbp, rsp
0x1800176e5  sub     rsp, 20h
0x1800176e9  mov     rdi, [rdx+88h]
0x1800176f0  mov     rsi, r8
0x1800176f3  mov     r13, rdx
0x1800176f6  mov     [rbp+ptr], 0
0x1800176fe  mov     r15, rcx
0x180017701  mov     r14d, 48h ; 'H'
0x180017707  mov     r8d, r14d; Size
0x18001770a  mov     rcx, rsi; void *
0x18001770d  xor     edx, edx; Val
0x18001770f  call    memset_0
0x180017714  mov     rax, [r13+90h]
0x18001771b  test    rax, rax
0x18001771e  jnz     loc_1800178EC
0x180017724  mov     r9, [r15]; error
0x180017727  lea     r8, [rbp+ptr]; ptr
0x18001772b  mov     rcx, [r15+30h]; heap
0x18001772f  mov     edx, r14d; size
0x180017732  call    cs:__imp_WsAlloc
0x180017739  nop     dword ptr [rax+rax+00h]
0x18001773e  mov     ebx, eax
0x180017740  test    eax, eax
0x180017742  jns     short loc_18001776C
0x180017744  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001774b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017750  mov     r9d, 0A17h
0x180017756  mov     r8, rax
0x180017759  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180017760  mov     edx, ebx
0x180017762  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180017767  jmp     loc_180017916
0x18001776c  mov     rcx, [rbp+ptr]; void *
0x180017770  mov     r8, r14; Size
0x180017773  xor     edx, edx; Val
0x180017775  call    memset_0
0x18001777a  mov     rcx, [rdi+10h]
0x18001777e  test    rcx, rcx
0x180017781  jz      short loc_1800177A1
0x180017783  mov     rax, [rbp+ptr]
0x180017787  mov     [rax+8], rcx
0x18001778b  mov     rcx, [rdi+10h]; lpString
0x18001778f  call    cs:__imp_lstrlenW
0x180017796  nop     dword ptr [rax+rax+00h]
0x18001779b  mov     rcx, [rbp+ptr]
0x18001779f  mov     [rcx], eax
0x1800177a1  mov     rcx, [rdi+18h]
0x1800177a5  test    rcx, rcx
0x1800177a8  jz      short loc_1800177C9
0x1800177aa  mov     rax, [rbp+ptr]
0x1800177ae  mov     [rax+18h], rcx
0x1800177b2  mov     rcx, [rdi+18h]; lpString
0x1800177b6  call    cs:__imp_lstrlenW
0x1800177bd  nop     dword ptr [rax+rax+00h]
0x1800177c2  mov     rcx, [rbp+ptr]
0x1800177c6  mov     [rcx+10h], eax
0x1800177c9  mov     rcx, [rdi+20h]
0x1800177cd  test    rcx, rcx
0x1800177d0  jz      short loc_1800177F1
0x1800177d2  mov     rax, [rbp+ptr]
0x1800177d6  mov     [rax+28h], rcx
0x1800177da  mov     rcx, [rdi+20h]; lpString
0x1800177de  call    cs:__imp_lstrlenW
0x1800177e5  nop     dword ptr [rax+rax+00h]
0x1800177ea  mov     rcx, [rbp+ptr]
0x1800177ee  mov     [rcx+20h], eax
0x1800177f1  cmp     dword ptr [rdi+28h], 0
0x1800177f5  jbe     loc_1800178A8
0x1800177fb  mov     eax, [rdi+28h]
0x1800177fe  mov     r8, [rbp+ptr]
0x180017802  mov     r9, [r15]; error
0x180017805  add     r8, 38h ; '8'; ptr
0x180017809  mov     rcx, [r15+30h]; heap
0x18001780d  imul    rdx, rax, 68h ; 'h'; size
0x180017811  call    cs:__imp_WsAlloc
0x180017818  nop     dword ptr [rax+rax+00h]
0x18001781d  mov     ebx, eax
0x18001781f  test    eax, eax
0x180017821  jns     short loc_18001783A
0x180017823  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001782a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001782f  mov     r9d, 0A39h
0x180017835  jmp     loc_180017756
0x18001783a  mov     rax, [rbp+ptr]
0x18001783e  xor     edx, edx; Val
0x180017840  mov     ecx, [rdi+28h]
0x180017843  mov     [rax+30h], ecx
0x180017846  mov     eax, [rdi+28h]
0x180017849  mov     rcx, [rbp+ptr]
0x18001784d  imul    r8, rax, 68h ; 'h'; Size
0x180017851  mov     rcx, [rcx+38h]; void *
0x180017855  call    memset_0
0x18001785a  xor     r14d, r14d
0x18001785d  cmp     r14d, [rdi+28h]
0x180017861  jnb     short loc_1800178A8
0x180017863  mov     rax, [rbp+ptr]
0x180017867  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x18001786a  mov     ecx, r14d
0x18001786d  imul    r8, rcx, 68h ; 'h'
0x180017871  add     r8, [rax+38h]; struct WS_TYPE_Reference *
0x180017875  mov     rax, [rdi+30h]
0x180017879  mov     rcx, [rax+r14*8]
0x18001787d  mov     rcx, [rcx+8]; struct _HXML_REFERENCE *
0x180017881  call    ?I_XmlMarshallReference@@YAJPEBU_HXML_REFERENCE@@PEAU_CRYPT_XML_WS_STATE@@PEAUWS_TYPE_Reference@@@Z; I_XmlMarshallReference(_HXML_REFERENCE const *,_CRYPT_XML_WS_STATE *,WS_TYPE_Reference *)
0x180017886  mov     ebx, eax
0x180017888  test    eax, eax
0x18001788a  js      short loc_180017891
0x18001788c  inc     r14d
0x18001788f  jmp     short loc_18001785D
0x180017891  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017898  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001789d  mov     r9d, 0A4Bh
0x1800178a3  jmp     loc_180017756
0x1800178a8  mov     rcx, [r13+98h]; struct _CRYPT_XML_BLOB *
0x1800178af  test    rcx, rcx
0x1800178b2  jz      short loc_1800178E1
0x1800178b4  mov     r8, [rbp+ptr]
0x1800178b8  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x1800178bb  add     r8, 40h ; '@'; struct _WS_XML_BUFFER **
0x1800178bf  call    ?I_XmlSetEncoded@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncoded(_CRYPT_XML_BLOB const *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER * *)
0x1800178c4  mov     ebx, eax
0x1800178c6  test    eax, eax
0x1800178c8  jns     short loc_1800178E1
0x1800178ca  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800178d1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800178d6  mov     r9d, 0A5Ah
0x1800178dc  jmp     loc_180017756
0x1800178e1  mov     rax, [rbp+ptr]
0x1800178e5  mov     [r13+90h], rax
0x1800178ec  movups  xmm0, xmmword ptr [rax]
0x1800178ef  xor     ebx, ebx
0x1800178f1  movups  xmmword ptr [rsi], xmm0
0x1800178f4  movups  xmm1, xmmword ptr [rax+10h]
0x1800178f8  movups  xmmword ptr [rsi+10h], xmm1
0x1800178fc  movups  xmm0, xmmword ptr [rax+20h]
0x180017900  movups  xmmword ptr [rsi+20h], xmm0
0x180017904  movups  xmm1, xmmword ptr [rax+30h]
0x180017908  movups  xmmword ptr [rsi+30h], xmm1
0x18001790c  movsd   xmm0, qword ptr [rax+40h]
0x180017911  movsd   qword ptr [rsi+40h], xmm0
0x180017916  mov     rsi, [rsp+20h+arg_10]
0x18001791b  mov     eax, ebx
0x18001791d  mov     rbx, [rsp+20h+arg_0]
0x180017922  add     rsp, 20h
0x180017926  pop     r15
0x180017928  pop     r14
0x18001792a  pop     r13
0x18001792c  pop     rdi
0x18001792d  pop     rbp
0x18001792e  retn
```

# I_CryptXmlWsStateInitialize

- ea: `0x180004670`
- end: `0x1800049b2`
- name: `I_CryptXmlWsStateInitialize`
- size: `834`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001fe0`
- `0x180003fb0`

## callees

- `0x180004670`
- `0x1800070d0`
- `0x180014ce0`
- `0x1800164cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004711`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004711`
- `webservices!WsCreateReader` at `0x1800047bd`
- `webservices!WsCreateReader` at `0x1800047bd`
- `webservices!WsCreateHeap` at `0x18000487f`
- `webservices!WsCreateHeap` at `0x180004910`
- `webservices!WsCreateHeap` at `0x18000487f`
- `webservices!WsCreateHeap` at `0x180004910`
- `webservices!WsCreateWriter` at `0x180004815`
- `webservices!WsCreateWriter` at `0x180004815`
- `webservices!WsCreateXmlBuffer` at `0x1800048c3`
- `webservices!WsCreateXmlBuffer` at `0x180004951`
- `webservices!WsCreateXmlBuffer` at `0x1800048c3`
- `webservices!WsCreateXmlBuffer` at `0x180004951`
- `webservices!WsCreateError` at `0x180004765`
- `webservices!WsCreateError` at `0x180004765`

## string_xrefs

- `0x1800046c1`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000472c`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000477e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800047d6`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000482e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180004891`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800048d5`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180004922`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180004963`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
HRESULT __fastcall I_CryptXmlWsStateInitialize(unsigned __int64 a1, unsigned int a2, __int64 a3)
{
  struct _WS_ERROR **v3; // r14
  SIZE_T v6; // rsi
  SIZE_T v7; // rdi
  HRESULT Error; // ebp
  const char *v9; // rax
  char v10; // dl
  const char *v11; // r8
  const char *v12; // r10
  __int64 v13; // r9
  WS_ERROR **v14; // rax
  WS_ERROR **v15; // rbx
  char v16; // dl
  const char *v17; // r8
  char v18; // dl
  const char *v19; // r8
  char v20; // dl
  const char *v21; // r8
  HRESULT result; // eax
  int v23; // edx

  v3 = 0;
  v6 = a1;
  v7 = 0x10000;
  if ( a1 )
  {
    if ( a1 <= 0x10000 )
      v7 = a1;
  }
  else
  {
    v6 = 2147483640;
  }
  if ( *(_QWORD *)(a3 + 152) )
  {
    Error = -2146885369;
    v9 = "";
    do
    {
      v10 = *(v9 - 1);
      v11 = v9--;
    }
    while ( v10 != 92 && v9 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
    v12 = "ERROR  : (0x%08x) %s:%u";
    v13 = 87;
    if ( v10 == 92 )
      v9 = v11;
  }
  else
  {
    v14 = (WS_ERROR **)HeapAlloc(*(HANDLE *)(a3 + 48), ((*(int *)(a3 + 60) >> 31) & 1u) + 8, 40 * (a2 + 2LL));
    *(_QWORD *)(a3 + 152) = v14;
    v15 = v14;
    if ( v14 )
    {
      *((_DWORD *)v14 + 16) = a2;
      v14[9] = (WS_ERROR *)(v14 + 10);
      v3 = v14;
      Error = WsCreateError(0, 0, v14);
      if ( Error >= 0 )
      {
        Error = WsCreateReader(0, 0, v15 + 1, *v15);
        if ( Error >= 0 )
        {
          Error = WsCreateWriter(0, 0, v15 + 2, *v15);
          if ( Error >= 0 )
          {
            Error = WsCreateHeap(v6, v7, 0, 0, v15 + 4, *v15);
            if ( Error >= 0 )
            {
              Error = WsCreateXmlBuffer(v15[4], 0, 0, v15 + 5, *v15);
              if ( Error >= 0 )
              {
                Error = WsCreateHeap(v6, v7, 0, 0, v15 + 6, *v15);
                if ( Error >= 0 )
                {
                  result = WsCreateXmlBuffer(v15[6], 0, 0, v15 + 7, *v15);
                  Error = result;
                  if ( result >= 0 )
                    return result;
                  v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                  v13 = 227;
                }
                else
                {
                  v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                  v13 = 214;
                }
              }
              else
              {
                v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                v13 = 196;
              }
            }
            else
            {
              v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
              v13 = 178;
            }
          }
          else
          {
            v9 = "";
            do
            {
              v20 = *(v9 - 1);
              v21 = v9--;
            }
            while ( v20 != 92 && v9 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
            v12 = "ERROR  : (0x%08x) %s:%u";
            v13 = 160;
            if ( v20 == 92 )
              v9 = v21;
          }
        }
        else
        {
          v9 = "";
          do
          {
            v18 = *(v9 - 1);
            v19 = v9--;
          }
          while ( v18 != 92 && v9 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
          v12 = "ERROR  : (0x%08x) %s:%u";
          v13 = 144;
          if ( v18 == 92 )
            v9 = v19;
        }
      }
      else
      {
        v9 = "";
        do
        {
          v16 = *(v9 - 1);
          v17 = v9--;
        }
        while ( v16 != 92 && v9 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
        v12 = "ERROR  : (0x%08x) %s:%u";
        v13 = 128;
        if ( v16 == 92 )
          v9 = v17;
      }
    }
    else
    {
      Error = -2147024882;
      v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v13 = 109;
    }
  }
  WPPTraceLogA(v12, (unsigned int)Error, v9, v13);
  if ( *v3 )
    I_TraceWsError(*v3, v23);
  return Error;
}

```

## disassembly

```asm
0x180004670  mov     [rsp+arg_8], rbp
0x180004675  mov     [rsp+arg_10], rsi
0x18000467a  push    rdi
0x18000467b  push    r14
0x18000467d  push    r15
0x18000467f  sub     rsp, 30h
0x180004683  xor     r14d, r14d
0x180004686  mov     r15d, edx
0x180004689  mov     rbp, r8
0x18000468c  mov     rsi, rcx
0x18000468f  mov     edi, 10000h
0x180004694  test    rcx, rcx
0x180004697  jnz     short loc_1800046A0
0x180004699  mov     esi, 7FFFFFF8h
0x18000469e  jmp     short loc_1800046A7
0x1800046a0  cmp     rcx, rdi
0x1800046a3  cmovbe  rdi, rcx
0x1800046a7  mov     [rsp+48h+arg_0], rbx
0x1800046ac  cmp     [r8+98h], r14
0x1800046b3  jz      short loc_1800046F5
0x1800046b5  mov     ebp, 80092107h
0x1800046ba  lea     rax, aOnecoreDsSecur_1+35h; ""
0x1800046c1  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800046c8  movzx   edx, byte ptr [rax-1]
0x1800046cc  mov     r8, rax
0x1800046cf  dec     rax
0x1800046d2  cmp     dl, 5Ch ; '\'
0x1800046d5  jz      short loc_1800046DC
0x1800046d7  cmp     rax, rcx
0x1800046da  ja      short loc_1800046C8
0x1800046dc  cmp     dl, 5Ch ; '\'
0x1800046df  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800046e6  mov     r9d, 57h ; 'W'
0x1800046ec  cmovz   rax, r8
0x1800046f0  jmp     loc_18000497C
0x1800046f5  mov     edx, [rbp+3Ch]
0x1800046f8  lea     rax, [r15+2]
0x1800046fc  mov     rcx, [rbp+30h]; hHeap
0x180004700  lea     r8, [rax+rax*4]
0x180004704  sar     edx, 1Fh
0x180004707  and     edx, 1
0x18000470a  shl     r8, 3; dwBytes
0x18000470e  add     edx, 8; dwFlags
0x180004711  call    cs:__imp_HeapAlloc
0x180004718  nop     dword ptr [rax+rax+00h]
0x18000471d  mov     [rbp+98h], rax
0x180004724  mov     rbx, rax
0x180004727  test    rax, rax
0x18000472a  jnz     short loc_18000474F
0x18000472c  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004733  mov     ebp, 8007000Eh
0x180004738  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000473f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004744  mov     r9d, 6Dh ; 'm'
0x18000474a  jmp     loc_18000497C
0x18000474f  mov     [rax+40h], r15d
0x180004753  mov     r8, rbx; error
0x180004756  add     rax, 50h ; 'P'
0x18000475a  xor     edx, edx; propertyCount
0x18000475c  xor     ecx, ecx; properties
0x18000475e  mov     [rbx+48h], rax
0x180004762  mov     r14, rbx
0x180004765  call    cs:__imp_WsCreateError
0x18000476c  nop     dword ptr [rax+rax+00h]
0x180004771  mov     ebp, eax
0x180004773  test    eax, eax
0x180004775  jns     short loc_1800047B2
0x180004777  lea     rax, aOnecoreDsSecur_1+35h; ""
0x18000477e  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004785  movzx   edx, byte ptr [rax-1]
0x180004789  mov     r8, rax
0x18000478c  dec     rax
0x18000478f  cmp     dl, 5Ch ; '\'
0x180004792  jz      short loc_180004799
0x180004794  cmp     rax, rcx
0x180004797  ja      short loc_180004785
0x180004799  cmp     dl, 5Ch ; '\'
0x18000479c  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800047a3  mov     r9d, 80h
0x1800047a9  cmovz   rax, r8
0x1800047ad  jmp     loc_18000497C
0x1800047b2  mov     r9, [rbx]; error
0x1800047b5  lea     r8, [rbx+8]; reader
0x1800047b9  xor     edx, edx; propertyCount
0x1800047bb  xor     ecx, ecx; properties
0x1800047bd  call    cs:__imp_WsCreateReader
0x1800047c4  nop     dword ptr [rax+rax+00h]
0x1800047c9  mov     ebp, eax
0x1800047cb  test    eax, eax
0x1800047cd  jns     short loc_18000480A
0x1800047cf  lea     rax, aOnecoreDsSecur_1+35h; ""
0x1800047d6  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800047dd  movzx   edx, byte ptr [rax-1]
0x1800047e1  mov     r8, rax
0x1800047e4  dec     rax
0x1800047e7  cmp     dl, 5Ch ; '\'
0x1800047ea  jz      short loc_1800047F1
0x1800047ec  cmp     rax, rcx
0x1800047ef  ja      short loc_1800047DD
0x1800047f1  cmp     dl, 5Ch ; '\'
0x1800047f4  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800047fb  mov     r9d, 90h
0x180004801  cmovz   rax, r8
0x180004805  jmp     loc_18000497C
0x18000480a  mov     r9, [rbx]; error
0x18000480d  lea     r8, [rbx+10h]; writer
0x180004811  xor     edx, edx; propertyCount
0x180004813  xor     ecx, ecx; properties
0x180004815  call    cs:__imp_WsCreateWriter
0x18000481c  nop     dword ptr [rax+rax+00h]
0x180004821  mov     ebp, eax
0x180004823  test    eax, eax
0x180004825  jns     short loc_180004862
0x180004827  lea     rax, aOnecoreDsSecur_1+35h; ""
0x18000482e  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004835  movzx   edx, byte ptr [rax-1]
0x180004839  mov     r8, rax
0x18000483c  dec     rax
0x18000483f  cmp     dl, 5Ch ; '\'
0x180004842  jz      short loc_180004849
0x180004844  cmp     rax, rcx
0x180004847  ja      short loc_180004835
0x180004849  cmp     dl, 5Ch ; '\'
0x18000484c  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004853  mov     r9d, 0A0h
0x180004859  cmovz   rax, r8
0x18000485d  jmp     loc_18000497C
0x180004862  mov     rax, [rbx]
0x180004865  lea     r15, [rbx+20h]
0x180004869  mov     [rsp+48h+error], rax; error
0x18000486e  xor     r9d, r9d; propertyCount
0x180004871  xor     r8d, r8d; properties
0x180004874  mov     [rsp+48h+heap], r15; heap
0x180004879  mov     rdx, rdi; trimSize
0x18000487c  mov     rcx, rsi; maxSize
0x18000487f  call    cs:__imp_WsCreateHeap
0x180004886  nop     dword ptr [rax+rax+00h]
0x18000488b  mov     ebp, eax
0x18000488d  test    eax, eax
0x18000488f  jns     short loc_1800048AF
0x180004891  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004898  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000489f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800048a4  mov     r9d, 0B2h
0x1800048aa  jmp     loc_18000497C
0x1800048af  mov     rax, [rbx]
0x1800048b2  lea     r9, [rbx+28h]; buffer
0x1800048b6  mov     rcx, [r15]; heap
0x1800048b9  xor     r8d, r8d; propertyCount
0x1800048bc  xor     edx, edx; properties
0x1800048be  mov     [rsp+48h+heap], rax; error
0x1800048c3  call    cs:__imp_WsCreateXmlBuffer
0x1800048ca  nop     dword ptr [rax+rax+00h]
0x1800048cf  mov     ebp, eax
0x1800048d1  test    eax, eax
0x1800048d3  jns     short loc_1800048F3
0x1800048d5  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800048dc  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800048e3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800048e8  mov     r9d, 0C4h
0x1800048ee  jmp     loc_18000497C
0x1800048f3  mov     rax, [rbx]
0x1800048f6  lea     r15, [rbx+30h]
0x1800048fa  mov     [rsp+48h+error], rax; error
0x1800048ff  xor     r9d, r9d; propertyCount
0x180004902  xor     r8d, r8d; properties
0x180004905  mov     [rsp+48h+heap], r15; heap
0x18000490a  mov     rdx, rdi; trimSize
0x18000490d  mov     rcx, rsi; maxSize
0x180004910  call    cs:__imp_WsCreateHeap
0x180004917  nop     dword ptr [rax+rax+00h]
0x18000491c  mov     ebp, eax
0x18000491e  test    eax, eax
0x180004920  jns     short loc_18000493D
0x180004922  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004929  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004930  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004935  mov     r9d, 0D6h
0x18000493b  jmp     short loc_18000497C
0x18000493d  mov     rax, [rbx]
0x180004940  lea     r9, [rbx+38h]; buffer
0x180004944  mov     rcx, [r15]; heap
0x180004947  xor     r8d, r8d; propertyCount
0x18000494a  xor     edx, edx; properties
0x18000494c  mov     [rsp+48h+heap], rax; error
0x180004951  call    cs:__imp_WsCreateXmlBuffer
0x180004958  nop     dword ptr [rax+rax+00h]
0x18000495d  mov     ebp, eax
0x18000495f  test    eax, eax
0x180004961  jns     short loc_180004998
0x180004963  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000496a  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004971  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004976  mov     r9d, 0E3h
0x18000497c  mov     r8, rax
0x18000497f  mov     edx, ebp
0x180004981  mov     rcx, r10; char *
0x180004984  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180004989  mov     rcx, [r14]; error
0x18000498c  test    rcx, rcx
0x18000498f  jz      short loc_180004996
0x180004991  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x180004996  mov     eax, ebp
0x180004998  mov     rbx, [rsp+48h+arg_0]
0x18000499d  mov     rbp, [rsp+48h+arg_8]
0x1800049a2  mov     rsi, [rsp+48h+arg_10]
0x1800049a7  add     rsp, 30h
0x1800049ab  pop     r15
0x1800049ad  pop     r14
0x1800049af  pop     rdi
0x1800049b0  retn
```

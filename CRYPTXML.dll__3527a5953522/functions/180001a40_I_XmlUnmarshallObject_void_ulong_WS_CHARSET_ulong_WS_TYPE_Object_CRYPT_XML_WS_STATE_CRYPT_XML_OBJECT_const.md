# I_XmlUnmarshallObject(void *,ulong,WS_CHARSET,ulong,WS_TYPE_Object *,_CRYPT_XML_WS_STATE *,_CRYPT_XML_OBJECT const * *)

- ea: `0x180001a40`
- end: `0x180001cf8`
- name: `?I_XmlUnmarshallObject@@YAJPEAXKW4WS_CHARSET@@KPEAUWS_TYPE_Object@@PEAU_CRYPT_XML_WS_STATE@@PEAPEBU_CRYPT_XML_OBJECT@@@Z`
- size: `696`
- prototype: `__int64 __usercall@<rax>(HANDLE hHeap@<rcx>, unsigned int@<edx>, enum WS_CHARSET@<r8d>, unsigned int@<r9d>, struct WS_TYPE_Object *, struct _CRYPT_XML_WS_STATE *, const struct _CRYPT_XML_OBJECT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016a0c`

## callees

- `0x180001010`
- `0x180001a40`
- `0x180001d00`
- `0x1800070d0`
- `0x1800110e0`
- `0x180014ce0`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ce0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ce0`

## string_xrefs

- `0x180001b3d`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180001b9a`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180001c2a`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180001c4d`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlUnmarshallObject(
        HANDLE hHeap,
        int a2,
        __int32 a3,
        unsigned int a4,
        struct WS_TYPE_Object *a5,
        WS_ERROR **a6,
        const struct _CRYPT_XML_OBJECT **a7)
{
  int v11; // r10d
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  struct _CRYPT_XML_WS_STATE *v14; // rsi
  int EncodedElement; // edi
  const char *v16; // r8
  int v17; // r9d
  char v18; // al
  const char *v19; // rdx
  bool v20; // zf
  __int64 v21; // r12
  char v22; // al
  HANDLE ProcessHeap; // rax
  __int64 v25; // [rsp+50h] [rbp-78h] BYREF
  int v26; // [rsp+58h] [rbp-70h]
  __int64 v27; // [rsp+60h] [rbp-68h]
  unsigned int v28; // [rsp+68h] [rbp-60h]
  __int64 v29; // [rsp+70h] [rbp-58h]
  unsigned int v30; // [rsp+78h] [rbp-50h]
  struct _CRYPT_XML_BLOB v31; // [rsp+80h] [rbp-48h] BYREF
  int v32; // [rsp+90h] [rbp-38h]
  struct WS_TYPE_Object *v33; // [rsp+98h] [rbp-30h]

  memset_0(&v25, 0, 0x50u);
  v11 = *(_DWORD *)a5;
  if ( *(_DWORD *)a5 > 0x100u
    || (v12 = *((_DWORD *)a5 + 4), v12 > 0x2000)
    || (v13 = *((_DWORD *)a5 + 8), v13 > 0x2000)
    || *((_DWORD *)a5 + 12) > 0x7FF8u )
  {
    EncodedElement = -2146885375;
    v16 = "";
    while ( 1 )
    {
      v22 = *(v16 - 1);
      v19 = v16--;
      v20 = v22 == 92;
      if ( v22 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v20 = v22 == 92;
        break;
      }
    }
    v17 = 810;
    goto LABEL_26;
  }
  v20 = *((_QWORD *)a5 + 8) == 0;
  v25 = *((_QWORD *)a5 + 1);
  v27 = *((_QWORD *)a5 + 3);
  v29 = *((_QWORD *)a5 + 5);
  v26 = v11;
  v28 = v12;
  v30 = v13;
  v33 = a5;
  if ( v20 && (a2 & 0x40000000) == 0 )
  {
    v14 = (struct _CRYPT_XML_WS_STATE *)a6;
    goto LABEL_8;
  }
  v14 = (struct _CRYPT_XML_WS_STATE *)a6;
  EncodedElement = I_XmlGetEncodedElement(a3, a6, &Object_ElementDescription, a5, 0x48u, a4, &v31);
  if ( EncodedElement < 0 )
  {
    v16 = "";
    while ( 1 )
    {
      v18 = *(v16 - 1);
      v19 = v16--;
      v20 = v18 == 92;
      if ( v18 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v20 = v18 == 92;
        break;
      }
    }
    v17 = 837;
LABEL_26:
    if ( v20 )
      v16 = v19;
    goto LABEL_28;
  }
LABEL_8:
  v32 = *((_DWORD *)a5 + 12);
  EncodedElement = I_CryptXmlHandleAllocObject(hHeap);
  if ( EncodedElement < 0 )
  {
    v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v17 = 853;
LABEL_28:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v16, v17);
    goto LABEL_29;
  }
  v21 = 0;
  *a7 = (const struct _CRYPT_XML_OBJECT *)MEMORY[0x88];
  while ( (unsigned int)v21 < *((_DWORD *)a5 + 12) )
  {
    EncodedElement = I_XmlUnmarshallReference(
                       hHeap,
                       (enum WS_CHARSET)a3,
                       a4,
                       (struct WS_TYPE_Reference *)(*((_QWORD *)a5 + 7) + 104LL * (unsigned int)v21),
                       v14,
                       (struct _HXML_HANDLE *)(*a7)->hObject,
                       (const struct _CRYPT_XML_REFERENCE **)&(*a7)->Manifest.rgpReference[v21]);
    if ( EncodedElement < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v17 = 874;
      goto LABEL_28;
    }
    v21 = (unsigned int)(v21 + 1);
  }
LABEL_29:
  if ( v31.cbData )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, v31.pbData);
  }
  return (unsigned int)EncodedElement;
}

```

## disassembly

```asm
0x180001a40  mov     rax, rsp
0x180001a43  push    rdi
0x180001a44  sub     rsp, 0C0h
0x180001a4b  mov     [rax+8], rbx
0x180001a4f  mov     edi, edx
0x180001a51  mov     [rax+10h], rbp
0x180001a55  xor     edx, edx; Val
0x180001a57  mov     [rax+18h], rsi
0x180001a5b  mov     ebp, r9d
0x180001a5e  mov     [rax-10h], r12
0x180001a62  mov     [rax-18h], r13
0x180001a66  mov     [rax-20h], r14
0x180001a6a  mov     r14d, r8d
0x180001a6d  mov     [rax-28h], r15
0x180001a71  mov     r8d, 50h ; 'P'; Size
0x180001a77  mov     r15, rcx
0x180001a7a  mov     [rsp+0C8h+var_88], 0
0x180001a83  lea     rcx, [rax-78h]; void *
0x180001a87  call    memset_0
0x180001a8c  mov     rbx, [rsp+0C8h+arg_20]
0x180001a94  mov     r10d, [rbx]
0x180001a97  cmp     r10d, 100h
0x180001a9e  ja      loc_180001C41
0x180001aa4  mov     r8d, [rbx+10h]
0x180001aa8  cmp     r8d, 2000h
0x180001aaf  ja      loc_180001C41
0x180001ab5  mov     ecx, [rbx+20h]
0x180001ab8  cmp     ecx, 2000h
0x180001abe  ja      loc_180001C41
0x180001ac4  cmp     dword ptr [rbx+30h], 7FF8h
0x180001acb  ja      loc_180001C41
0x180001ad1  cmp     qword ptr [rbx+40h], 0
0x180001ad6  mov     rax, [rbx+8]
0x180001ada  mov     [rsp+0C8h+var_78], rax
0x180001adf  mov     rax, [rbx+18h]
0x180001ae3  mov     [rsp+0C8h+var_68], rax
0x180001ae8  mov     rax, [rbx+28h]
0x180001aec  mov     [rsp+0C8h+var_58], rax
0x180001af1  mov     [rsp+0C8h+var_70], r10d
0x180001af6  mov     [rsp+0C8h+var_60], r8d
0x180001afb  mov     [rsp+0C8h+var_50], ecx
0x180001aff  mov     [rsp+0C8h+var_30], rbx
0x180001b07  jnz     short loc_180001B57
0x180001b09  bt      edi, 1Eh
0x180001b0d  jb      short loc_180001B57
0x180001b0f  mov     rsi, [rsp+0C8h+arg_28]
0x180001b17  mov     eax, [rbx+30h]
0x180001b1a  lea     r9, [rsp+0C8h+var_88]
0x180001b1f  lea     r8, [rsp+0C8h+var_78]
0x180001b24  mov     [rsp+0C8h+var_38], eax
0x180001b2b  mov     rcx, r15; hHeap
0x180001b2e  call    I_CryptXmlHandleAllocObject
0x180001b33  mov     edi, eax
0x180001b35  test    eax, eax
0x180001b37  jns     loc_180001BC2
0x180001b3d  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001b44  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001b49  mov     r8, rax
0x180001b4c  mov     r9d, 355h
0x180001b52  jmp     loc_180001C74
0x180001b57  mov     rsi, [rsp+0C8h+arg_28]
0x180001b5f  lea     rax, [rsp+0C8h+var_48]
0x180001b67  mov     [rsp+0C8h+var_98], rax; struct _CRYPT_XML_BLOB *
0x180001b6c  lea     r8, ?Object_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x180001b73  mov     dword ptr [rsp+0C8h+var_A0], ebp; unsigned int
0x180001b77  mov     r9, rbx; void *
0x180001b7a  mov     rdx, rsi; struct _CRYPT_XML_WS_STATE *
0x180001b7d  mov     dword ptr [rsp+0C8h+var_A8], 48h ; 'H'; unsigned int
0x180001b85  mov     ecx, r14d; enum WS_CHARSET
0x180001b88  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180001b8d  mov     edi, eax
0x180001b8f  test    eax, eax
0x180001b91  jns     short loc_180001B17
0x180001b93  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180001b9a  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001ba1  movzx   eax, byte ptr [r8-1]
0x180001ba6  mov     rdx, r8
0x180001ba9  dec     r8
0x180001bac  cmp     al, 5Ch ; '\'
0x180001bae  jz      short loc_180001BB7
0x180001bb0  cmp     r8, rcx
0x180001bb3  ja      short loc_180001BA1
0x180001bb5  cmp     al, 5Ch ; '\'
0x180001bb7  mov     r9d, 345h
0x180001bbd  jmp     loc_180001C70
0x180001bc2  mov     rax, [rsp+0C8h+var_88]
0x180001bc7  xor     r12d, r12d
0x180001bca  mov     r13, [rsp+0C8h+arg_30]
0x180001bd2  mov     rcx, [rax+88h]
0x180001bd9  mov     [r13+0], rcx
0x180001bdd  cmp     r12d, [rbx+30h]
0x180001be1  jnb     loc_180001C82
0x180001be7  mov     r8, [r13+0]
0x180001beb  mov     edx, r12d
0x180001bee  imul    r9, rdx, 68h ; 'h'
0x180001bf2  mov     rax, [r8+30h]
0x180001bf6  mov     edx, r14d; enum WS_CHARSET
0x180001bf9  add     r9, [rbx+38h]; struct WS_TYPE_Reference *
0x180001bfd  lea     rcx, [rax+r12*8]
0x180001c01  mov     rax, [r8+8]
0x180001c05  mov     [rsp+0C8h+var_98], rcx; struct _CRYPT_XML_REFERENCE **
0x180001c0a  mov     r8d, ebp; unsigned int
0x180001c0d  mov     [rsp+0C8h+var_A0], rax; struct _HXML_HANDLE *
0x180001c12  mov     rcx, r15; hHeap
0x180001c15  mov     [rsp+0C8h+var_A8], rsi; struct _CRYPT_XML_WS_STATE *
0x180001c1a  call    ?I_XmlUnmarshallReference@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_Reference@@PEAU_CRYPT_XML_WS_STATE@@PEAU_HXML_HANDLE@@PEAPEBU_CRYPT_XML_REFERENCE@@@Z; I_XmlUnmarshallReference(void *,WS_CHARSET,ulong,WS_TYPE_Reference *,_CRYPT_XML_WS_STATE *,_HXML_HANDLE *,_CRYPT_XML_REFERENCE const * *)
0x180001c1f  mov     edi, eax
0x180001c21  test    eax, eax
0x180001c23  js      short loc_180001C2A
0x180001c25  inc     r12d
0x180001c28  jmp     short loc_180001BDD
0x180001c2a  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001c31  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001c36  mov     r8, rax
0x180001c39  mov     r9d, 36Ah
0x180001c3f  jmp     short loc_180001C74
0x180001c41  mov     edi, 80092101h
0x180001c46  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180001c4d  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001c54  movzx   eax, byte ptr [r8-1]
0x180001c59  mov     rdx, r8
0x180001c5c  dec     r8
0x180001c5f  cmp     al, 5Ch ; '\'
0x180001c61  jz      short loc_180001C6A
0x180001c63  cmp     r8, rcx
0x180001c66  ja      short loc_180001C54
0x180001c68  cmp     al, 5Ch ; '\'
0x180001c6a  mov     r9d, 32Ah
0x180001c70  cmovz   r8, rdx
0x180001c74  mov     edx, edi
0x180001c76  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001c7d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001c82  cmp     [rsp+0C8h+var_48.cbData], 0
0x180001c8a  mov     r15, [rsp+0C8h+var_28]
0x180001c92  mov     r14, [rsp+0C8h+var_20]
0x180001c9a  mov     r13, [rsp+0C8h+var_18]
0x180001ca2  mov     r12, [rsp+0C8h+var_10]
0x180001caa  mov     rsi, [rsp+0C8h+arg_10]
0x180001cb2  mov     rbp, [rsp+0C8h+arg_8]
0x180001cba  mov     rbx, [rsp+0C8h+arg_0]
0x180001cc2  jbe     short loc_180001CEC
0x180001cc4  call    cs:__imp_GetProcessHeap
0x180001ccb  nop     dword ptr [rax+rax+00h]
0x180001cd0  mov     r8, [rsp+0C8h+var_48.pbData]; lpMem
0x180001cd8  mov     edx, 8; dwFlags
0x180001cdd  mov     rcx, rax; hHeap
0x180001ce0  call    cs:__imp_HeapFree
0x180001ce7  nop     dword ptr [rax+rax+00h]
0x180001cec  mov     eax, edi
0x180001cee  add     rsp, 0C0h
0x180001cf5  pop     rdi
0x180001cf6  retn
```

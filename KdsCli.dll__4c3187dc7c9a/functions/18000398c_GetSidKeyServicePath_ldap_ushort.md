# GetSidKeyServicePath(ldap *,ushort * *)

- ea: `0x18000398c`
- end: `0x180003b14`
- name: `?GetSidKeyServicePath@@YAJPEAUldap@@PEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800035a0`
- `0x1800038c0`

## callees

- `0x18000398c`
- `0x180003b1c`
- `0x180003e08`
- `0x180003e70`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x180003a07`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003a2b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x1800039e5`: `configurationNamingContext`
- `0x180003a71`: `cn=Group Key Distribution Service,cn=Services,`

## pseudocode

```c
__int64 __fastcall GetSidKeyServicePath(LDAP *ld, unsigned __int16 **a2)
{
  signed int SingleStringAttr; // eax
  void *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // r9d
  unsigned int v8; // ecx
  __int64 v9; // rax
  size_t v10; // rbp
  _OWORD *v11; // rax
  unsigned __int16 *v12; // rsi
  int v14; // [rsp+20h] [rbp-38h]
  void *Src; // [rsp+70h] [rbp+18h] BYREF

  Src = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids);
  SingleStringAttr = GetSingleStringAttr(ld, (PWSTR)L"configurationNamingContext", v14, (__int64)&Src);
  v5 = Src;
  v6 = SingleStringAttr;
  if ( SingleStringAttr >= 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)Src + v9) );
    v10 = 2 * v9;
    v11 = SIDKeyProvAlloc(2 * v9 + 94);
    v12 = (unsigned __int16 *)v11;
    if ( v11 )
    {
      *v11 = *(_OWORD *)L"cn=Group Key Distribution Service,cn=Services,";
      v11[1] = *(_OWORD *)L" Key Distribution Service,cn=Services,";
      v11[2] = *(_OWORD *)L"tribution Service,cn=Services,";
      v11[3] = *(_OWORD *)L"n Service,cn=Services,";
      v11[4] = *(_OWORD *)L"e,cn=Services,";
      *(_OWORD *)((char *)v11 + 76) = *(_OWORD *)L"ervices,";
      memcpy_0((char *)v11 + 92, v5, v10);
      *a2 = v12;
      goto LABEL_12;
    }
    v6 = -2147024882;
    v7 = 1016;
    v8 = -2147024882;
  }
  else
  {
    SidKeyDebugTraceError(
      SingleStringAttr,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
      0x10Eu);
    v7 = 1004;
    v8 = v6;
  }
  SidKeyDebugTraceError(v8, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v7);
LABEL_12:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids, *a2);
  if ( v5 )
    SIDKeyProvFree(v5);
  return v6;
}

```

## disassembly

```asm
0x18000398c  mov     [rsp+arg_0], rbx
0x180003991  mov     [rsp+arg_8], rbp
0x180003996  push    rsi
0x180003997  push    rdi
0x180003998  push    r12
0x18000399a  push    r14
0x18000399c  push    r15
0x18000399e  sub     rsp, 30h
0x1800039a2  xor     r15d, r15d
0x1800039a5  mov     r14, rdx
0x1800039a8  mov     [rsp+58h+Src], r15
0x1800039ad  mov     rbx, rcx
0x1800039b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039b7  lea     r12, WPP_GLOBAL_Control
0x1800039be  cmp     rcx, r12
0x1800039c1  jz      short loc_1800039DD
0x1800039c3  test    byte ptr [rcx+1Ch], 4
0x1800039c7  jz      short loc_1800039DD
0x1800039c9  mov     rcx, [rcx+10h]
0x1800039cd  lea     edx, [r15+10h]
0x1800039d1  lea     r8, WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids
0x1800039d8  call    WPP_SF_
0x1800039dd  lea     rax, [rsp+58h+Src]
0x1800039e2  mov     rcx, rbx; ld
0x1800039e5  lea     rdx, aConfigurationn; "configurationNamingContext"
0x1800039ec  mov     [rsp+58h+var_30], rax; __int64
0x1800039f1  call    GetSingleStringAttr
0x1800039f6  mov     rdi, [rsp+58h+Src]
0x1800039fb  mov     ebx, eax
0x1800039fd  test    eax, eax
0x1800039ff  jns     short loc_180003A3C
0x180003a01  mov     r9d, 10Eh; unsigned int
0x180003a07  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003a0e  lea     rdx, aHr; "hr"
0x180003a15  mov     ecx, eax; unsigned int
0x180003a17  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003a1c  mov     r9d, 3ECh; unsigned int
0x180003a22  mov     ecx, ebx; unsigned int
0x180003a24  lea     rdx, aHr; "hr"
0x180003a2b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003a32  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003a37  jmp     loc_180003AC4
0x180003a3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a40  inc     rax
0x180003a43  cmp     [rdi+rax*2], r15w
0x180003a48  jnz     short loc_180003A40
0x180003a4a  lea     rbp, [rax+rax]
0x180003a4e  lea     rcx, [rbp+5Eh]; unsigned __int64
0x180003a52  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180003a57  mov     rsi, rax
0x180003a5a  test    rax, rax
0x180003a5d  jnz     short loc_180003A71
0x180003a5f  mov     ebx, 8007000Eh
0x180003a64  mov     r9d, 3F8h
0x180003a6a  mov     ecx, 8007000Eh
0x180003a6f  jmp     short loc_180003A24
0x180003a71  movaps  xmm0, xmmword ptr cs:aCnGroupKeyDist_0; "cn=Group Key Distribution Service,cn=Se"...
0x180003a78  lea     rcx, [rax+5Ch]; void *
0x180003a7c  movups  xmmword ptr [rax], xmm0
0x180003a7f  mov     r8, rbp; Size
0x180003a82  mov     rdx, rdi; Src
0x180003a85  movaps  xmm1, xmmword ptr cs:aCnGroupKeyDist_0+10h; " Key Distribution Service,cn=Services,"
0x180003a8c  movups  xmmword ptr [rax+10h], xmm1
0x180003a90  movaps  xmm0, xmmword ptr cs:aCnGroupKeyDist_0+20h; "tribution Service,cn=Services,"
0x180003a97  movups  xmmword ptr [rax+20h], xmm0
0x180003a9b  movaps  xmm1, xmmword ptr cs:aCnGroupKeyDist_0+30h; "n Service,cn=Services,"
0x180003aa2  movups  xmmword ptr [rax+30h], xmm1
0x180003aa6  movaps  xmm0, xmmword ptr cs:aCnGroupKeyDist_0+40h; "e,cn=Services,"
0x180003aad  movups  xmmword ptr [rax+40h], xmm0
0x180003ab1  movups  xmm1, xmmword ptr cs:aCnGroupKeyDist_0+4Ch; "ervices,"
0x180003ab8  movups  xmmword ptr [rax+4Ch], xmm1
0x180003abc  call    memcpy_0
0x180003ac1  mov     [r14], rsi
0x180003ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003acb  cmp     rcx, r12
0x180003ace  jz      short loc_180003AEE
0x180003ad0  test    byte ptr [rcx+1Ch], 4
0x180003ad4  jz      short loc_180003AEE
0x180003ad6  mov     r9, [r14]
0x180003ad9  lea     r8, WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids
0x180003ae0  mov     rcx, [rcx+10h]
0x180003ae4  mov     edx, 11h
0x180003ae9  call    WPP_SF_S
0x180003aee  test    rdi, rdi
0x180003af1  jz      short loc_180003AFB
0x180003af3  mov     rcx, rdi; lpMem
0x180003af6  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180003afb  mov     rbp, [rsp+58h+arg_8]
0x180003b00  mov     eax, ebx
0x180003b02  mov     rbx, [rsp+58h+arg_0]
0x180003b07  add     rsp, 30h
0x180003b0b  pop     r15
0x180003b0d  pop     r14
0x180003b0f  pop     r12
0x180003b11  pop     rdi
0x180003b12  pop     rsi
0x180003b13  retn
```

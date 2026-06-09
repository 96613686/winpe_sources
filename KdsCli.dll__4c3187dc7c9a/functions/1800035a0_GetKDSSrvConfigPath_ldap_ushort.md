# GetKDSSrvConfigPath(ldap *,ushort * *)

- ea: `0x1800035a0`
- end: `0x180003665`
- name: `?GetKDSSrvConfigPath@@YAJPEAUldap@@PEAPEAG@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001fdc`
- `0x1800035a0`
- `0x18000398c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x1800035df`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003628`: `cn=Group Key Distribution Service Server Configuration,cn=Server Configuration,`

## pseudocode

```c
__int64 __fastcall GetKDSSrvConfigPath(struct ldap *a1, unsigned __int16 **a2)
{
  int SidKeyServicePath; // eax
  void *v4; // rbx
  unsigned int v5; // edi
  unsigned int v6; // r9d
  unsigned int v7; // ecx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rbp
  void *lpMem; // [rsp+80h] [rbp+18h] BYREF

  lpMem = 0;
  SidKeyServicePath = GetSidKeyServicePath(a1, (unsigned __int16 **)&lpMem);
  v4 = lpMem;
  v5 = SidKeyServicePath;
  if ( SidKeyServicePath < 0 )
  {
    v6 = 1054;
    v7 = SidKeyServicePath;
LABEL_3:
    SidKeyDebugTraceError(v7, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v6);
    goto LABEL_9;
  }
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)lpMem + v8) );
  v9 = 2 * v8 + 160;
  v10 = (wchar_t *)SIDKeyProvAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    v6 = 1064;
    v7 = -2147024882;
    goto LABEL_3;
  }
  swprintf_s(
    v10,
    v9 >> 1,
    L"%s%s",
    L"cn=Group Key Distribution Service Server Configuration,cn=Server Configuration,",
    v4);
  *a2 = v11;
LABEL_9:
  if ( v4 )
    SIDKeyProvFree(v4);
  return v5;
}

```

## disassembly

```asm
0x1800035a0  mov     rax, rsp
0x1800035a3  push    rbx
0x1800035a4  push    rbp
0x1800035a5  push    rsi
0x1800035a6  push    rdi
0x1800035a7  push    r14
0x1800035a9  push    r15
0x1800035ab  sub     rsp, 38h
0x1800035af  mov     r14, rdx
0x1800035b2  xor     r15d, r15d
0x1800035b5  lea     rdx, [rax+18h]; unsigned __int16 **
0x1800035b9  mov     [rax+18h], r15
0x1800035bd  call    ?GetSidKeyServicePath@@YAJPEAUldap@@PEAPEAG@Z; GetSidKeyServicePath(ldap *,ushort * *)
0x1800035c2  mov     rbx, [rsp+68h+lpMem]
0x1800035ca  mov     edi, eax
0x1800035cc  test    eax, eax
0x1800035ce  jns     short loc_1800035ED
0x1800035d0  mov     r9d, 41Eh; unsigned int
0x1800035d6  mov     ecx, eax; unsigned int
0x1800035d8  lea     rdx, aHr; "hr"
0x1800035df  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800035e6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800035eb  jmp     short loc_180003649
0x1800035ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035f1  inc     rax
0x1800035f4  cmp     [rbx+rax*2], r15w
0x1800035f9  jnz     short loc_1800035F1
0x1800035fb  lea     rsi, ds:0A0h[rax*2]
0x180003603  mov     rcx, rsi; unsigned __int64
0x180003606  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000360b  mov     rbp, rax
0x18000360e  test    rax, rax
0x180003611  jnz     short loc_180003625
0x180003613  mov     edi, 8007000Eh
0x180003618  mov     r9d, 428h
0x18000361e  mov     ecx, 8007000Eh
0x180003623  jmp     short loc_1800035D8
0x180003625  shr     rsi, 1
0x180003628  lea     r9, aCnGroupKeyDist; "cn=Group Key Distribution Service Serve"...
0x18000362f  mov     rdx, rsi; BufferCount
0x180003632  mov     [rsp+68h+var_48], rbx
0x180003637  lea     r8, aSS; "%s%s"
0x18000363e  mov     rcx, rbp; Buffer
0x180003641  call    swprintf_s
0x180003646  mov     [r14], rbp
0x180003649  test    rbx, rbx
0x18000364c  jz      short loc_180003656
0x18000364e  mov     rcx, rbx; lpMem
0x180003651  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180003656  mov     eax, edi
0x180003658  add     rsp, 38h
0x18000365c  pop     r15
0x18000365e  pop     r14
0x180003660  pop     rdi
0x180003661  pop     rsi
0x180003662  pop     rbp
0x180003663  pop     rbx
0x180003664  retn
```

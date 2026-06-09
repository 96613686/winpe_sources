# GenerateL2KeyLdap(_L0_key *,uchar * const,ulong,ulong,uchar * const)

- ea: `0x180008850`
- end: `0x180008985`
- name: `?GenerateL2KeyLdap@@YAJPEAU_L0_key@@QEAEKK1@Z`
- size: `309`
- prototype: `int(struct _L0_key *, unsigned __int8 *const, unsigned int, unsigned int, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e98`

## callees

- `0x180008850`
- `0x18000d6a0`
- `0x18000d9d0`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x18000894e`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GenerateL2KeyLdap(struct _L0_key *a1, unsigned __int8 *const a2, int a3)
{
  struct _GUID v3; // xmm0
  DWORD v4; // r14d
  int v5; // edx
  int DerivedKey; // eax
  void *v8; // rsi
  unsigned int v9; // ebx
  char v10; // r9
  BYTE *pNonce; // [rsp+20h] [rbp-88h]
  PBYTE *ppKey; // [rsp+48h] [rbp-60h]
  DWORD offset; // [rsp+70h] [rbp-38h] BYREF
  DWORD derivedKeyLength[2]; // [rsp+78h] [rbp-30h] BYREF
  struct _GUID v16; // [rsp+80h] [rbp-28h] BYREF
  unsigned int algId; // [rsp+B0h] [rbp+8h] BYREF

  v3 = *(struct _GUID *)((char *)a1 + 12);
  *(_QWORD *)derivedKeyLength = 0;
  v4 = (unsigned int)a2;
  v5 = *(_DWORD *)a1;
  offset = 0;
  algId = 0;
  v16 = v3;
  DerivedKey = GenerateKDFContext(&v16, v5, a3, 31, 2u, (unsigned __int8 **)derivedKeyLength, &offset, &algId);
  v8 = *(void **)derivedKeyLength;
  v9 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v10 = 98;
LABEL_5:
    SidKeyDebugTraceError(DerivedKey, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v10);
    goto LABEL_6;
  }
  LODWORD(ppKey) = 0;
  LODWORD(pNonce) = 64;
  DerivedKey = GenerateDerivedKey(
                 *((PINFORMATIONCARD_CRYPTO_HANDLE *)a1 + 5),
                 *((_QWORD *)a1 + 6),
                 (PBYTE)*((unsigned int *)a1 + 14),
                 v4,
                 pNonce,
                 derivedKeyLength[0],
                 offset,
                 (LPCWSTR)&algId,
                 0,
                 ppKey);
  v9 = DerivedKey;
  if ( DerivedKey < 0 )
  {
    v10 = 120;
    goto LABEL_5;
  }
LABEL_6:
  SIDKeyProvFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180008850  mov     r11, rsp
0x180008853  mov     [r11+10h], rbx
0x180008857  mov     [r11+18h], rbp
0x18000885b  push    rsi
0x18000885c  push    rdi
0x18000885d  push    r14
0x18000885f  sub     rsp, 90h
0x180008866  movups  xmm0, xmmword ptr [rcx+0Ch]
0x18000886a  lea     rax, [r11+8]
0x18000886e  mov     qword ptr [r11-30h], 0
0x180008876  mov     [r11-70h], rax
0x18000887a  mov     r14, rdx
0x18000887d  mov     edx, [rcx]; unsigned int
0x18000887f  lea     rax, [r11-38h]
0x180008883  mov     [r11-78h], rax
0x180008887  mov     ebp, r9d
0x18000888a  lea     rax, [r11-30h]
0x18000888e  mov     [rsp+0A8h+var_38], 0
0x180008896  mov     rdi, rcx
0x180008899  mov     [r11-80h], rax
0x18000889d  mov     r9d, 1Fh; int
0x1800088a3  mov     dword ptr [rsp+0A8h+pNonce], 2; unsigned int
0x1800088ab  lea     rcx, [r11-28h]; struct _GUID *
0x1800088af  mov     dword ptr [r11+8], 0
0x1800088b7  movdqu  xmmword ptr [r11-28h], xmm0
0x1800088bd  call    ?GenerateKDFContext@@YAJU_GUID@@KJJKPEAPEAEPEAK2@Z; GenerateKDFContext(_GUID,ulong,long,long,ulong,uchar * *,ulong *,ulong *)
0x1800088c2  mov     rsi, qword ptr [rsp+0A8h+var_30]
0x1800088c7  mov     ebx, eax
0x1800088c9  test    eax, eax
0x1800088cb  jns     short loc_1800088D5
0x1800088cd  mov     r9d, 362h
0x1800088d3  jmp     short loc_18000894E
0x1800088d5  mov     rax, [rsp+0A8h+arg_20]
0x1800088dd  mov     edx, 40h ; '@'
0x1800088e2  mov     r8d, [rdi+38h]; pLabel
0x1800088e6  mov     ecx, 20h ; ' '
0x1800088eb  mov     [rsp+0A8h+var_40], 0
0x1800088f4  sub     ecx, ebp
0x1800088f6  mov     [rsp+0A8h+var_48], edx
0x1800088fa  mov     r9, r14; cbNonce
0x1800088fd  mov     [rsp+0A8h+var_50], rax
0x180008902  lea     rax, [rsp+0A8h+arg_0]
0x18000890a  mov     [rsp+0A8h+var_58], ecx
0x18000890e  mov     rcx, [rdi+28h]; hCrypto
0x180008912  mov     dword ptr [rsp+0A8h+ppKey], 0; ppKey
0x18000891a  mov     [rsp+0A8h+pcbKey], 0; pcbKey
0x180008923  mov     [rsp+0A8h+algId], rax; algId
0x180008928  mov     eax, [rsp+0A8h+var_38]
0x18000892c  mov     [rsp+0A8h+offset], eax; offset
0x180008930  mov     qword ptr [rsp+0A8h+derivedKeyLength], rsi; derivedKeyLength
0x180008935  mov     dword ptr [rsp+0A8h+pNonce], edx; pNonce
0x180008939  mov     rdx, [rdi+30h]; cbLabel
0x18000893d  call    ?GenerateDerivedKey@@YAJPEBGPEAEK1K1KPEAK1KK1KPEAPEAG@Z; GenerateDerivedKey(ushort const *,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong *,uchar *,ulong,ulong,uchar *,ulong,ushort * *)
0x180008942  mov     ebx, eax
0x180008944  test    eax, eax
0x180008946  jns     short loc_180008963
0x180008948  mov     r9d, 378h; unsigned int
0x18000894e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008955  mov     ecx, eax; unsigned int
0x180008957  lea     rdx, aHr; "hr"
0x18000895e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008963  mov     rcx, rsi; lpMem
0x180008966  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000896b  lea     r11, [rsp+0A8h+var_18]
0x180008973  mov     eax, ebx
0x180008975  mov     rbx, [r11+28h]
0x180008979  mov     rbp, [r11+30h]
0x18000897d  mov     rsp, r11
0x180008980  pop     r14
0x180008982  pop     rdi
0x180008983  pop     rsi
0x180008984  retn
```

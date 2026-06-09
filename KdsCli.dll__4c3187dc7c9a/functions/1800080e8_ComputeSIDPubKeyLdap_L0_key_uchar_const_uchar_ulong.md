# ComputeSIDPubKeyLdap(_L0_key *,uchar * const,uchar * *,ulong *)

- ea: `0x1800080e8`
- end: `0x18000823a`
- name: `?ComputeSIDPubKeyLdap@@YAJPEAU_L0_key@@QEAEPEAPEAEPEAK@Z`
- size: `338`
- prototype: `int(struct _L0_key *, unsigned __int8 *const, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`

## callees

- `0x180001630`
- `0x180006cb8`
- `0x1800080e8`
- `0x18000de80`
- `0x18000dfc0`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180008217`
- `bcrypt!BCryptDestroyKey` at `0x180008217`

## string_xrefs

- `0x1800081f9`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall ComputeSIDPubKeyLdap(
        struct _L0_key *a1,
        unsigned __int8 *const a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  DWORD v4; // r10d
  __int64 v6; // r9
  struct _INFORMATIONCARD_CRYPTO_HANDLE *v8; // r8
  WCHAR *v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  unsigned int v15; // r9d
  unsigned int v16; // ecx
  int SIDPublicKeyBlob; // eax
  UCHAR *v19; // [rsp+28h] [rbp-51h]
  ULONG v20; // [rsp+30h] [rbp-49h]
  unsigned int v21; // [rsp+38h] [rbp-41h]
  ULONG v22; // [rsp+40h] [rbp-39h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+60h] [rbp-19h] BYREF
  int v24; // [rsp+68h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+70h] [rbp-9h] BYREF
  char *v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+88h] [rbp+Fh]
  int *v28; // [rsp+90h] [rbp+17h]
  __int64 v29; // [rsp+98h] [rbp+1Fh]

  *a3 = 0;
  *a4 = 0;
  v4 = (unsigned int)a2;
  v6 = *((_QWORD *)a1 + 6);
  v8 = (struct _INFORMATIONCARD_CRYPTO_HANDLE *)*((_QWORD *)a1 + 5);
  v22 = *((_DWORD *)a1 + 22);
  v21 = (unsigned int)(*((_DWORD *)a1 + 21) + 7) >> 3;
  v10 = (WCHAR *)*((_QWORD *)a1 + 8);
  v20 = *((_DWORD *)a1 + 20);
  v19 = (UCHAR *)*((_QWORD *)a1 + 9);
  v11 = *((_DWORD *)a1 + 14);
  hKey = 0;
  v12 = GenerateSecretAgreementPrivateKey(v4, v10, v8, v6, v11, v19, v20, v21, v22, 2, &hKey, 0);
  v14 = v12;
  if ( v12 >= 0 )
  {
    SIDPublicKeyBlob = GenerateSIDPublicKeyBlob(hKey, a3, a4);
    v14 = SIDPublicKeyBlob;
    if ( SIDPublicKeyBlob >= 0 )
      goto LABEL_8;
    v15 = 1022;
    v16 = SIDPublicKeyBlob;
  }
  else
  {
    if ( (Microsoft_Windows_KdsSvcEnableBits & 1) != 0 )
    {
      v24 = v12;
      v26 = (char *)a1 + 12;
      v28 = &v24;
      v27 = 16;
      v29 = 4;
      McGenEventWrite_EventWriteTransfer(
        (__int64)a1 + 12,
        (const EVENT_DESCRIPTOR *)KdsKeyGenerationFailure,
        v13,
        3u,
        &v25);
    }
    v15 = 1012;
    v16 = v14;
  }
  SidKeyDebugTraceError(v16, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v15);
LABEL_8:
  if ( hKey )
    BCryptDestroyKey(hKey);
  return v14;
}

```

## disassembly

```asm
0x1800080e8  push    rbp
0x1800080ea  push    rbx
0x1800080eb  push    rsi
0x1800080ec  push    r14
0x1800080ee  push    r15
0x1800080f0  lea     rbp, [rsp-37h]
0x1800080f5  sub     rsp, 0B0h
0x1800080fc  mov     rax, cs:__security_cookie
0x180008103  xor     rax, rsp
0x180008106  mov     [rbp+57h+var_30], rax
0x18000810a  mov     qword ptr [r8], 0
0x180008111  lea     rax, [rbp+57h+hKey]
0x180008115  mov     dword ptr [r9], 0
0x18000811c  mov     r10, rdx
0x18000811f  mov     edx, [rcx+54h]
0x180008122  mov     r15, r9
0x180008125  mov     r9, [rcx+30h]
0x180008129  add     edx, 7
0x18000812c  mov     [rsp+0D0h+var_78], 0
0x180008135  mov     r14, r8
0x180008138  mov     r8, [rcx+28h]
0x18000813c  mov     rsi, rcx
0x18000813f  mov     [rsp+0D0h+var_80], rax
0x180008144  mov     eax, [rcx+58h]
0x180008147  mov     [rsp+0D0h+var_88], 2
0x18000814f  mov     [rsp+0D0h+var_90], eax
0x180008153  mov     eax, [rcx+50h]
0x180008156  shr     edx, 3
0x180008159  mov     [rsp+0D0h+var_98], edx
0x18000815d  mov     rdx, [rcx+40h]
0x180008161  mov     [rsp+0D0h+var_A0], eax
0x180008165  mov     rax, [rcx+48h]
0x180008169  mov     [rsp+0D0h+var_A8], rax
0x18000816e  mov     eax, [rcx+38h]
0x180008171  mov     rcx, r10
0x180008174  mov     [rbp+57h+hKey], 0
0x18000817c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180008180  call    ?GenerateSecretAgreementPrivateKey@@YAJQEAEPEAG1PEAEK2KKKW4_SID_KEY_BLOB_VER@@PEAPEAXPEAPEAG@Z; GenerateSecretAgreementPrivateKey(uchar * const,ushort *,ushort *,uchar *,ulong,uchar *,ulong,ulong,ulong,_SID_KEY_BLOB_VER,void * *,ushort * *)
0x180008185  mov     ebx, eax
0x180008187  test    eax, eax
0x180008189  jns     short loc_1800081DC
0x18000818b  test    cs:Microsoft_Windows_KdsSvcEnableBits, 1
0x180008192  jz      short loc_1800081D2
0x180008194  mov     [rbp+57h+var_68], eax
0x180008197  lea     rcx, [rsi+0Ch]
0x18000819b  lea     rax, [rbp+57h+var_68]
0x18000819f  mov     [rbp+57h+var_50], rcx
0x1800081a3  mov     [rbp+57h+var_40], rax
0x1800081a7  lea     rdx, KdsKeyGenerationFailure
0x1800081ae  lea     rax, [rbp+57h+var_60]
0x1800081b2  mov     [rbp+57h+var_48], 10h
0x1800081ba  mov     r9d, 3
0x1800081c0  mov     [rsp+0D0h+var_B0], rax
0x1800081c5  mov     [rbp+57h+var_38], 4
0x1800081cd  call    McGenEventWrite_EventWriteTransfer
0x1800081d2  mov     r9d, 3F4h
0x1800081d8  mov     ecx, ebx
0x1800081da  jmp     short loc_1800081F9
0x1800081dc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800081e0  mov     r8, r15; unsigned int *
0x1800081e3  mov     rdx, r14; unsigned __int8 **
0x1800081e6  call    ?GenerateSIDPublicKeyBlob@@YAJPEAXPEAPEAEPEAK@Z; GenerateSIDPublicKeyBlob(void *,uchar * *,ulong *)
0x1800081eb  mov     ebx, eax
0x1800081ed  test    eax, eax
0x1800081ef  jns     short loc_18000820C
0x1800081f1  mov     r9d, 3FEh; unsigned int
0x1800081f7  mov     ecx, eax; unsigned int
0x1800081f9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008200  lea     rdx, aHr; "hr"
0x180008207  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000820c  cmp     [rbp+57h+hKey], 0
0x180008211  jz      short loc_18000821D
0x180008213  mov     rcx, [rbp+57h+hKey]; hKey
0x180008217  call    cs:__imp_BCryptDestroyKey
0x18000821d  mov     eax, ebx
0x18000821f  mov     rcx, [rbp+57h+var_30]
0x180008223  xor     rcx, rsp; StackCookie
0x180008226  call    __security_check_cookie
0x18000822b  add     rsp, 0B0h
0x180008232  pop     r15
0x180008234  pop     r14
0x180008236  pop     rsi
0x180008237  pop     rbx
0x180008238  pop     rbp
0x180008239  retn
```

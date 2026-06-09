# ValidateSrvConfig(_KDS_CONFIGURATION *,ushort * *)

- ea: `0x180007c20`
- end: `0x180007d22`
- name: `?ValidateSrvConfig@@YAJPEAU_KDS_CONFIGURATION@@PEAPEAG@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct _KDS_CONFIGURATION *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007b60`
- `0x180007c20`
- `0x18001a450`

## string_xrefs

- `0x180007c4a`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x180007ce1`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall ValidateSrvConfig(struct _KDS_CONFIGURATION *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v5; // r9d
  unsigned int v6; // edi
  unsigned __int8 *v7; // rcx
  signed int v8; // eax

  if ( *(_DWORD *)a1 != 1 )
  {
    v4 = L"msKds-Version";
    v5 = 721;
LABEL_3:
    *a2 = v4;
    v6 = -2146893819;
    SidKeyDebugTraceError(0x80090005, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", v5);
    goto LABEL_15;
  }
  if ( !*((_DWORD *)a1 + 14) )
  {
    v4 = L"msKds-PublicKeyLength";
    v5 = 729;
    goto LABEL_3;
  }
  if ( !*((_DWORD *)a1 + 13) )
  {
    v4 = L"msKds-PrivateKeyLength";
    v5 = 737;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)a1 + 1) )
  {
    v4 = L"msKds-KDFAlgorithmID";
    v5 = 745;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)a1 + 4) )
  {
    v4 = L"msKds-SecretAgreementAlgorithmID";
    v5 = 753;
    goto LABEL_3;
  }
  v7 = (unsigned __int8 *)*((_QWORD *)a1 + 2);
  v6 = 0;
  if ( !v7 || (v8 = ValidateKDFParam(v7, *((_DWORD *)a1 + 6)), v6 = v8, v8 >= 0) )
  {
    *a2 = 0;
    return v6;
  }
  SidKeyDebugTraceError(v8, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", 0x2FCu);
  *a2 = L"msKds-KDFParam";
LABEL_15:
  *((_DWORD *)a1 + 18) = 0;
  return v6;
}

```

## disassembly

```asm
0x180007c20  mov     [rsp+arg_0], rbx
0x180007c25  mov     [rsp+arg_8], rsi
0x180007c2a  push    rdi
0x180007c2b  sub     rsp, 20h
0x180007c2f  cmp     dword ptr [rcx], 1
0x180007c32  mov     rsi, rdx
0x180007c35  mov     rbx, rcx
0x180007c38  jz      short loc_180007C6C
0x180007c3a  lea     rax, aMskdsVersion; "msKds-Version"
0x180007c41  mov     r9d, 2D1h; unsigned int
0x180007c47  mov     [rdx], rax
0x180007c4a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007c51  lea     rdx, aHr; "hr"
0x180007c58  mov     ecx, 80090005h; unsigned int
0x180007c5d  mov     edi, 80090005h
0x180007c62  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007c67  jmp     loc_180007D00
0x180007c6c  cmp     dword ptr [rcx+38h], 0
0x180007c70  jnz     short loc_180007C81
0x180007c72  lea     rax, aMskdsPublickey; "msKds-PublicKeyLength"
0x180007c79  mov     r9d, 2D9h
0x180007c7f  jmp     short loc_180007C47
0x180007c81  cmp     dword ptr [rcx+34h], 0
0x180007c85  jnz     short loc_180007C96
0x180007c87  lea     rax, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x180007c8e  mov     r9d, 2E1h
0x180007c94  jmp     short loc_180007C47
0x180007c96  cmp     qword ptr [rcx+8], 0
0x180007c9b  jnz     short loc_180007CAC
0x180007c9d  lea     rax, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x180007ca4  mov     r9d, 2E9h
0x180007caa  jmp     short loc_180007C47
0x180007cac  cmp     qword ptr [rcx+20h], 0
0x180007cb1  jnz     short loc_180007CC2
0x180007cb3  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x180007cba  mov     r9d, 2F1h
0x180007cc0  jmp     short loc_180007C47
0x180007cc2  mov     rcx, [rcx+10h]; unsigned __int8 *
0x180007cc6  xor     edi, edi
0x180007cc8  test    rcx, rcx
0x180007ccb  jz      short loc_180007D09
0x180007ccd  mov     edx, [rbx+18h]; unsigned int
0x180007cd0  call    ?ValidateKDFParam@@YAJPEAEK@Z; ValidateKDFParam(uchar *,ulong)
0x180007cd5  mov     edi, eax
0x180007cd7  test    eax, eax
0x180007cd9  jns     short loc_180007D09
0x180007cdb  mov     r9d, 2FCh; unsigned int
0x180007ce1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007ce8  lea     rdx, aHr; "hr"
0x180007cef  mov     ecx, eax; unsigned int
0x180007cf1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007cf6  lea     rax, aMskdsKdfparam; "msKds-KDFParam"
0x180007cfd  mov     [rsi], rax
0x180007d00  mov     dword ptr [rbx+48h], 0
0x180007d07  jmp     short loc_180007D10
0x180007d09  mov     qword ptr [rsi], 0
0x180007d10  mov     rbx, [rsp+28h+arg_0]
0x180007d15  mov     eax, edi
0x180007d17  mov     rsi, [rsp+28h+arg_8]
0x180007d1c  add     rsp, 20h
0x180007d20  pop     rdi
0x180007d21  retn
```

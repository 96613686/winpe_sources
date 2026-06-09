# GetSpecifiedL0KeyLdap(ldap *,ushort *,_GUID *,ulong,unsigned __int64,_L0_key * *)

- ea: `0x180009a14`
- end: `0x180009b9e`
- name: `?GetSpecifiedL0KeyLdap@@YAJPEAUldap@@PEAGPEAU_GUID@@K_KPEAPEAU_L0_key@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, UUID *Uuid, unsigned int, unsigned __int64, struct _L0_key **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000898c`

## callees

- `0x180004624`
- `0x180004d5c`
- `0x180004e20`
- `0x180008e1c`
- `0x180009a14`
- `0x18001a450`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180009a4f`
- `RPCRT4!UuidToStringW` at `0x180009a4f`
- `RPCRT4!RpcStringFreeW` at `0x180009b85`
- `RPCRT4!RpcStringFreeW` at `0x180009b85`

## string_xrefs

- `0x180009a61`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009ab5`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009af3`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009b48`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetSpecifiedL0KeyLdap(
        struct ldap *a1,
        unsigned __int16 *a2,
        UUID *Uuid,
        unsigned int a4,
        unsigned __int64 a5,
        struct _L0_key **a6)
{
  struct _L0_key *v6; // rsi
  struct _ROOT_KEY_HEADER *v9; // rdi
  RPC_STATUS v11; // eax
  unsigned __int64 v12; // r9
  signed int v13; // ebx
  signed int RootKeyLdap; // eax
  unsigned int v15; // r9d
  unsigned int v16; // ecx
  signed int v17; // eax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-28h] BYREF
  struct _ROOT_KEY_HEADER *v20; // [rsp+38h] [rbp-20h] BYREF
  struct _L0_key *v21; // [rsp+40h] [rbp-18h] BYREF

  v6 = 0;
  v21 = 0;
  StringUuid = 0;
  v9 = 0;
  *a6 = 0;
  v20 = 0;
  v11 = UuidToStringW(Uuid, &StringUuid);
  v13 = v11;
  if ( !v11 )
  {
    RootKeyLdap = GetRootKeyLdap(a1, a2, StringUuid, v12, 0, &v20);
    v13 = RootKeyLdap;
    if ( RootKeyLdap < 0 )
    {
      SidKeyDebugTraceError(
        RootKeyLdap,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
        0x59Bu);
      v9 = v20;
      goto LABEL_14;
    }
    v9 = v20;
    if ( *((_DWORD *)v20 + 28) )
    {
      if ( *((_QWORD *)v20 + 17) - 363000000000LL <= a5 )
      {
        v17 = ComputeL0Key(v20, a4, &v21);
        v13 = v17;
        if ( v17 >= 0 )
        {
          *a6 = v21;
        }
        else
        {
          SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x5B7u);
          v6 = v21;
        }
        goto LABEL_14;
      }
      v13 = -2147024809;
      v15 = 1452;
      v16 = -2147024809;
    }
    else
    {
      v13 = -2146893821;
      v15 = 1442;
      v16 = -2146893821;
    }
    SidKeyDebugTraceError(v16, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v15);
    goto LABEL_14;
  }
  SidKeyDebugTraceError(v11, "rpcError", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x58Cu);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
LABEL_14:
  FreeL0Key(v6);
  FreeRootKey(v9);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180009a14  push    rbp
0x180009a16  push    rbx
0x180009a17  push    rsi
0x180009a18  push    rdi
0x180009a19  push    r12
0x180009a1b  push    r13
0x180009a1d  push    r14
0x180009a1f  push    r15
0x180009a21  mov     rbp, rsp
0x180009a24  sub     rsp, 58h
0x180009a28  mov     r14, [rbp+arg_28]
0x180009a2c  xor     esi, esi
0x180009a2e  mov     r12, rdx
0x180009a31  mov     [rbp+var_18], rsi
0x180009a35  mov     r13, rcx
0x180009a38  mov     [rbp+StringUuid], rsi
0x180009a3c  xor     edi, edi
0x180009a3e  lea     rdx, [rbp+StringUuid]; StringUuid
0x180009a42  mov     rcx, r8; Uuid
0x180009a45  mov     [r14], rsi
0x180009a48  mov     r15d, r9d
0x180009a4b  mov     [rbp+var_20], rdi
0x180009a4f  call    cs:__imp_UuidToStringW
0x180009a55  mov     ebx, eax
0x180009a57  test    eax, eax
0x180009a59  jz      short loc_180009A8C
0x180009a5b  mov     r9d, 58Ch; unsigned int
0x180009a61  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009a68  lea     rdx, aRpcerror; "rpcError"
0x180009a6f  mov     ecx, eax; unsigned int
0x180009a71  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009a76  test    ebx, ebx
0x180009a78  jle     loc_180009B6A
0x180009a7e  movzx   ebx, bx
0x180009a81  or      ebx, 80070000h
0x180009a87  jmp     loc_180009B6A
0x180009a8c  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x180009a90  lea     rax, [rbp+var_20]
0x180009a94  mov     [rsp+58h+var_30], rax; struct _ROOT_KEY_HEADER **
0x180009a99  mov     rdx, r12; unsigned __int16 *
0x180009a9c  mov     rcx, r13; struct ldap *
0x180009a9f  mov     [rsp+58h+var_38], rsi; unsigned __int64
0x180009aa4  call    ?GetRootKeyLdap@@YAJPEAUldap@@PEAGPEBG_K3PEAPEAU_ROOT_KEY_HEADER@@@Z; GetRootKeyLdap(ldap *,ushort *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)
0x180009aa9  mov     ebx, eax
0x180009aab  test    eax, eax
0x180009aad  jns     short loc_180009AD3
0x180009aaf  mov     r9d, 59Bh; unsigned int
0x180009ab5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009abc  lea     rdx, aHr; "hr"
0x180009ac3  mov     ecx, eax; unsigned int
0x180009ac5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009aca  mov     rdi, [rbp+var_20]
0x180009ace  jmp     loc_180009B6A
0x180009ad3  mov     rdi, [rbp+var_20]
0x180009ad7  cmp     [rdi+70h], esi
0x180009ada  jnz     short loc_180009B01
0x180009adc  mov     ebx, 80090003h
0x180009ae1  mov     r9d, 5A2h; unsigned int
0x180009ae7  mov     ecx, 80090003h; unsigned int
0x180009aec  lea     rdx, aHr; "hr"
0x180009af3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009afa  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009aff  jmp     short loc_180009B6A
0x180009b01  mov     rax, [rdi+88h]
0x180009b08  mov     rcx, 54847C6E00h
0x180009b12  sub     rax, rcx
0x180009b15  cmp     rax, [rbp+arg_20]
0x180009b19  jbe     short loc_180009B2D
0x180009b1b  mov     ebx, 80070057h
0x180009b20  mov     r9d, 5ACh
0x180009b26  mov     ecx, 80070057h
0x180009b2b  jmp     short loc_180009AEC
0x180009b2d  lea     r8, [rbp+var_18]; struct _L0_key **
0x180009b31  mov     edx, r15d; unsigned int
0x180009b34  mov     rcx, rdi; struct _ROOT_KEY_HEADER *
0x180009b37  call    ?ComputeL0Key@@YAJPEAU_ROOT_KEY_HEADER@@KPEAPEAU_L0_key@@@Z; ComputeL0Key(_ROOT_KEY_HEADER *,ulong,_L0_key * *)
0x180009b3c  mov     ebx, eax
0x180009b3e  test    eax, eax
0x180009b40  jns     short loc_180009B63
0x180009b42  mov     r9d, 5B7h; unsigned int
0x180009b48  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009b4f  lea     rdx, aHr; "hr"
0x180009b56  mov     ecx, eax; unsigned int
0x180009b58  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009b5d  mov     rsi, [rbp+var_18]
0x180009b61  jmp     short loc_180009B6A
0x180009b63  mov     rax, [rbp+var_18]
0x180009b67  mov     [r14], rax
0x180009b6a  mov     rcx, rsi; lpMem
0x180009b6d  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x180009b72  mov     rcx, rdi; lpMem
0x180009b75  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x180009b7a  cmp     [rbp+StringUuid], 0
0x180009b7f  jz      short loc_180009B8B
0x180009b81  lea     rcx, [rbp+StringUuid]; String
0x180009b85  call    cs:__imp_RpcStringFreeW
0x180009b8b  mov     eax, ebx
0x180009b8d  add     rsp, 58h
0x180009b91  pop     r15
0x180009b93  pop     r14
0x180009b95  pop     r13
0x180009b97  pop     r12
0x180009b99  pop     rdi
0x180009b9a  pop     rsi
0x180009b9b  pop     rbx
0x180009b9c  pop     rbp
0x180009b9d  retn
```

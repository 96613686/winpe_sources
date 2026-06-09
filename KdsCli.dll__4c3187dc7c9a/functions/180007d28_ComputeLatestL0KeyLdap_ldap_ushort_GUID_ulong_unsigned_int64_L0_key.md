# ComputeLatestL0KeyLdap(ldap *,ushort *,_GUID *,ulong,unsigned __int64,_L0_key * *)

- ea: `0x180007d28`
- end: `0x180007e92`
- name: `?ComputeLatestL0KeyLdap@@YAJPEAUldap@@PEAGPEAU_GUID@@K_KPEAPEAU_L0_key@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, UUID *Uuid, unsigned int, struct _ROOT_KEY_HEADER *, struct _L0_key **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008cf0`

## callees

- `0x180004624`
- `0x180004d5c`
- `0x180004e20`
- `0x180007d28`
- `0x180008e1c`
- `0x1800100d0`
- `0x18001a450`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180007d68`
- `RPCRT4!UuidToStringW` at `0x180007d68`
- `RPCRT4!RpcStringFreeW` at `0x180007e79`
- `RPCRT4!RpcStringFreeW` at `0x180007e79`

## string_xrefs

- `0x180007d7a`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180007dd3`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180007e02`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180007e3c`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall ComputeLatestL0KeyLdap(
        struct ldap *a1,
        unsigned __int16 *a2,
        UUID *Uuid,
        unsigned int a4,
        struct _ROOT_KEY_HEADER *a5,
        struct _L0_key **a6)
{
  struct _L0_key **v6; // r14
  struct _L0_key *v7; // rsi
  struct _ROOT_KEY_HEADER *v8; // rdi
  RPC_STATUS v12; // eax
  signed int v13; // ebx
  unsigned __int64 CurrentTimeInULL; // rax
  unsigned __int64 v15; // r9
  signed int RootKeyLdap; // eax
  signed int v17; // eax
  struct _L0_key *v19; // [rsp+30h] [rbp-18h] BYREF
  RPC_WSTR StringUuid; // [rsp+A0h] [rbp+58h] BYREF

  v6 = a6;
  v7 = 0;
  v8 = 0;
  v19 = 0;
  StringUuid = 0;
  a5 = 0;
  *a6 = 0;
  if ( Uuid && (v12 = UuidToStringW(Uuid, &StringUuid), (v13 = v12) != 0) )
  {
    SidKeyDebugTraceError(v12, "rpcStatus", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x5E7u);
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
  }
  else
  {
    CurrentTimeInULL = GetCurrentTimeInULL();
    RootKeyLdap = GetRootKeyLdap(a1, a2, StringUuid, v15, CurrentTimeInULL, &a5);
    v13 = RootKeyLdap;
    if ( RootKeyLdap >= 0 )
    {
      v8 = a5;
      if ( !a5 || *((_DWORD *)a5 + 28) )
      {
        v17 = ComputeL0Key(a5, a4, &v19);
        v13 = v17;
        if ( v17 >= 0 )
        {
          *v6 = v19;
        }
        else
        {
          SidKeyDebugTraceError(v17, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x60Au);
          v7 = v19;
        }
      }
      else
      {
        v13 = -2146893821;
        SidKeyDebugTraceError(
          0x80090003,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
          0x5FFu);
      }
    }
    else
    {
      SidKeyDebugTraceError(
        RootKeyLdap,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
        0x5F7u);
      v8 = a5;
    }
  }
  FreeL0Key(v7);
  FreeRootKey(v8);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007d28  push    rbp
0x180007d2a  push    rbx
0x180007d2b  push    rsi
0x180007d2c  push    rdi
0x180007d2d  push    r12
0x180007d2f  push    r13
0x180007d31  push    r14
0x180007d33  push    r15
0x180007d35  mov     rbp, rsp
0x180007d38  sub     rsp, 48h
0x180007d3c  mov     r14, [rbp+arg_28]
0x180007d40  xor     esi, esi
0x180007d42  xor     edi, edi
0x180007d44  mov     [rbp+var_18], rsi
0x180007d48  mov     [rbp+StringUuid], rsi
0x180007d4c  mov     r15d, r9d
0x180007d4f  mov     [rbp+arg_20], rdi
0x180007d53  mov     r12, rdx
0x180007d56  mov     [r14], rsi
0x180007d59  mov     r13, rcx
0x180007d5c  test    r8, r8
0x180007d5f  jz      short loc_180007DA5
0x180007d61  lea     rdx, [rbp+StringUuid]; StringUuid
0x180007d65  mov     rcx, r8; Uuid
0x180007d68  call    cs:__imp_UuidToStringW
0x180007d6e  mov     ebx, eax
0x180007d70  test    eax, eax
0x180007d72  jz      short loc_180007DA5
0x180007d74  mov     r9d, 5E7h; unsigned int
0x180007d7a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007d81  lea     rdx, aRpcstatus; "rpcStatus"
0x180007d88  mov     ecx, eax; unsigned int
0x180007d8a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007d8f  test    ebx, ebx
0x180007d91  jle     loc_180007E5E
0x180007d97  movzx   ebx, bx
0x180007d9a  or      ebx, 80070000h
0x180007da0  jmp     loc_180007E5E
0x180007da5  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x180007daa  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x180007dae  lea     rcx, [rbp+arg_20]
0x180007db2  mov     [rsp+48h+var_20], rcx; struct _ROOT_KEY_HEADER **
0x180007db7  mov     rdx, r12; unsigned __int16 *
0x180007dba  mov     rcx, r13; struct ldap *
0x180007dbd  mov     [rsp+48h+var_28], rax; unsigned __int64
0x180007dc2  call    ?GetRootKeyLdap@@YAJPEAUldap@@PEAGPEBG_K3PEAPEAU_ROOT_KEY_HEADER@@@Z; GetRootKeyLdap(ldap *,ushort *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)
0x180007dc7  mov     ebx, eax
0x180007dc9  test    eax, eax
0x180007dcb  jns     short loc_180007DEE
0x180007dcd  mov     r9d, 5F7h; unsigned int
0x180007dd3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007dda  lea     rdx, aHr; "hr"
0x180007de1  mov     ecx, eax; unsigned int
0x180007de3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007de8  mov     rdi, [rbp+arg_20]
0x180007dec  jmp     short loc_180007E5E
0x180007dee  mov     rdi, [rbp+arg_20]
0x180007df2  test    rdi, rdi
0x180007df5  jz      short loc_180007E21
0x180007df7  cmp     [rdi+70h], esi
0x180007dfa  jnz     short loc_180007E21
0x180007dfc  mov     r9d, 5FFh; unsigned int
0x180007e02  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007e09  lea     rdx, aHr; "hr"
0x180007e10  mov     ecx, 80090003h; unsigned int
0x180007e15  mov     ebx, 80090003h
0x180007e1a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007e1f  jmp     short loc_180007E5E
0x180007e21  lea     r8, [rbp+var_18]; struct _L0_key **
0x180007e25  mov     edx, r15d; unsigned int
0x180007e28  mov     rcx, rdi; struct _ROOT_KEY_HEADER *
0x180007e2b  call    ?ComputeL0Key@@YAJPEAU_ROOT_KEY_HEADER@@KPEAPEAU_L0_key@@@Z; ComputeL0Key(_ROOT_KEY_HEADER *,ulong,_L0_key * *)
0x180007e30  mov     ebx, eax
0x180007e32  test    eax, eax
0x180007e34  jns     short loc_180007E57
0x180007e36  mov     r9d, 60Ah; unsigned int
0x180007e3c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007e43  lea     rdx, aHr; "hr"
0x180007e4a  mov     ecx, eax; unsigned int
0x180007e4c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007e51  mov     rsi, [rbp+var_18]
0x180007e55  jmp     short loc_180007E5E
0x180007e57  mov     rax, [rbp+var_18]
0x180007e5b  mov     [r14], rax
0x180007e5e  mov     rcx, rsi; lpMem
0x180007e61  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x180007e66  mov     rcx, rdi; lpMem
0x180007e69  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x180007e6e  cmp     [rbp+StringUuid], 0
0x180007e73  jz      short loc_180007E7F
0x180007e75  lea     rcx, [rbp+StringUuid]; String
0x180007e79  call    cs:__imp_RpcStringFreeW
0x180007e7f  mov     eax, ebx
0x180007e81  add     rsp, 48h
0x180007e85  pop     r15
0x180007e87  pop     r14
0x180007e89  pop     r13
0x180007e8b  pop     r12
0x180007e8d  pop     rdi
0x180007e8e  pop     rsi
0x180007e8f  pop     rbx
0x180007e90  pop     rbp
0x180007e91  retn
```

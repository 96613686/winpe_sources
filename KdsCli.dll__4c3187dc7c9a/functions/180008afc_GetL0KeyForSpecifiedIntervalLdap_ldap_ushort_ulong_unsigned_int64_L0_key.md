# GetL0KeyForSpecifiedIntervalLdap(ldap *,ushort *,ulong,unsigned __int64,_L0_key * *)

- ea: `0x180008afc`
- end: `0x180008ce8`
- name: `?GetL0KeyForSpecifiedIntervalLdap@@YAJPEAUldap@@PEAGK_KPEAPEAU_L0_key@@@Z`
- size: `492`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, struct _L0_key **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000898c`

## callees

- `0x180004624`
- `0x180004d5c`
- `0x180004e20`
- `0x180004f40`
- `0x1800054e0`
- `0x180008afc`
- `0x180008e1c`
- `0x18001a450`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180008be4`
- `RPCRT4!UuidToStringW` at `0x180008be4`
- `RPCRT4!RpcStringFreeW` at `0x180008cc0`
- `RPCRT4!RpcStringFreeW` at `0x180008cc0`

## string_xrefs

- `0x180008bc2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180008bf6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180008c5d`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180008c92`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetL0KeyForSpecifiedIntervalLdap(
        LDAP *ld,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 a4,
        struct _L0_key **a5)
{
  struct _ROOT_KEY_HEADER *v6; // rdi
  struct _L0_key *v7; // r14
  int AllRootKeysMetaData; // eax
  unsigned __int64 v10; // r9
  struct _LIST_ENTRY *v11; // rsi
  signed int v12; // ebx
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  struct _LIST_ENTRY *i; // rax
  const UUID *Blink; // rcx
  signed int RootKeyLdap; // eax
  RPC_STATUS v18; // eax
  signed int v19; // eax
  unsigned int v21; // [rsp+30h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-28h] BYREF
  struct _ROOT_KEY_HEADER *v23; // [rsp+40h] [rbp-20h] BYREF
  struct _L0_key *v24; // [rsp+48h] [rbp-18h] BYREF
  struct _LIST_ENTRY *lpMem; // [rsp+50h] [rbp-10h] BYREF

  v21 = 0;
  v6 = 0;
  *a5 = 0;
  v7 = 0;
  v23 = 0;
  lpMem = 0;
  StringUuid = 0;
  v24 = 0;
  AllRootKeysMetaData = GetAllRootKeysMetaData(ld, a2, &v21, &lpMem);
  v11 = lpMem;
  v12 = AllRootKeysMetaData;
  if ( AllRootKeysMetaData < 0 )
  {
    v13 = 1312;
    v14 = AllRootKeysMetaData;
LABEL_21:
    SidKeyDebugTraceError(v14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v13);
    goto LABEL_22;
  }
  if ( !v21 || !lpMem )
  {
    v12 = -2146893807;
    v13 = 1321;
    v14 = -2146893807;
    goto LABEL_21;
  }
  for ( i = lpMem->Flink; i != lpMem; i = i->Flink )
  {
    Blink = (const UUID *)i[-1].Blink;
    if ( *(_QWORD *)Blink[1].Data4 < a4 )
    {
      v18 = UuidToStringW(Blink, &StringUuid);
      v12 = v18;
      if ( v18 )
      {
        SidKeyDebugTraceError(
          v18,
          "rpcError",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
          0x538u);
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        goto LABEL_22;
      }
      break;
    }
  }
  RootKeyLdap = GetRootKeyLdap(ld, a2, StringUuid, v10, a4, &v23);
  v12 = RootKeyLdap;
  if ( RootKeyLdap < 0 )
  {
    SidKeyDebugTraceError(
      RootKeyLdap,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx",
      0x548u);
    v6 = v23;
    goto LABEL_22;
  }
  v6 = v23;
  if ( v23 && !*((_DWORD *)v23 + 28) )
  {
    v12 = -2146893821;
    v13 = 1360;
    v14 = -2146893821;
    goto LABEL_21;
  }
  v19 = ComputeL0Key(v23, a3, &v24);
  v12 = v19;
  if ( v19 >= 0 )
  {
    *a5 = v24;
  }
  else
  {
    SidKeyDebugTraceError(v19, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x55Bu);
    v7 = v24;
  }
LABEL_22:
  FreeL0Key(v7);
  FreeRootKey(v6);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  FreeRootKeyMetaDataList(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008afc  mov     [rsp-38h+arg_8], rbx
0x180008b01  mov     [rsp-38h+arg_10], r8d
0x180008b06  mov     [rsp-38h+arg_0], rcx
0x180008b0b  push    rbp
0x180008b0c  push    rsi
0x180008b0d  push    rdi
0x180008b0e  push    r12
0x180008b10  push    r13
0x180008b12  push    r14
0x180008b14  push    r15
0x180008b16  mov     rbp, rsp
0x180008b19  sub     rsp, 60h
0x180008b1d  mov     r12, [rbp+arg_20]
0x180008b21  lea     r8, [rbp+var_30]; unsigned int *
0x180008b25  mov     rax, rcx
0x180008b28  mov     r15, r9
0x180008b2b  xor     ecx, ecx
0x180008b2d  lea     r9, [rbp+lpMem]; struct _LIST_ENTRY **
0x180008b31  mov     [rbp+var_30], ecx
0x180008b34  mov     edi, ecx
0x180008b36  mov     [r12], rcx
0x180008b3a  mov     r14d, ecx
0x180008b3d  mov     [rbp+var_20], rcx
0x180008b41  mov     r13, rdx
0x180008b44  mov     [rbp+lpMem], rcx
0x180008b48  mov     [rbp+StringUuid], rcx
0x180008b4c  mov     [rbp+var_18], rcx
0x180008b50  mov     rcx, rax; ld
0x180008b53  call    ?GetAllRootKeysMetaData@@YAJPEAUldap@@PEBGPEAKPEAPEAU_LIST_ENTRY@@@Z; GetAllRootKeysMetaData(ldap *,ushort const *,ulong *,_LIST_ENTRY * *)
0x180008b58  mov     rsi, [rbp+lpMem]
0x180008b5c  mov     ebx, eax
0x180008b5e  test    eax, eax
0x180008b60  jns     short loc_180008B6F
0x180008b62  mov     r9d, 520h; unsigned __int64
0x180008b68  mov     ecx, eax
0x180008b6a  jmp     loc_180008C92
0x180008b6f  cmp     [rbp+var_30], edi
0x180008b72  jz      loc_180008C82
0x180008b78  test    rsi, rsi
0x180008b7b  jz      loc_180008C82
0x180008b81  mov     rax, [rsi]
0x180008b84  jmp     short loc_180008B93
0x180008b86  mov     rcx, [rax-8]; Uuid
0x180008b8a  cmp     [rcx+18h], r15
0x180008b8e  jb      short loc_180008BE0
0x180008b90  mov     rax, [rax]
0x180008b93  cmp     rax, rsi
0x180008b96  jnz     short loc_180008B86
0x180008b98  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x180008b9c  lea     rax, [rbp+var_20]
0x180008ba0  mov     rcx, [rbp+arg_0]; struct ldap *
0x180008ba4  mov     rdx, r13; unsigned __int16 *
0x180008ba7  mov     [rsp+60h+var_38], rax; struct _ROOT_KEY_HEADER **
0x180008bac  mov     [rsp+60h+var_40], r15; unsigned __int64
0x180008bb1  call    ?GetRootKeyLdap@@YAJPEAUldap@@PEAGPEBG_K3PEAPEAU_ROOT_KEY_HEADER@@@Z; GetRootKeyLdap(ldap *,ushort *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)
0x180008bb6  mov     ebx, eax
0x180008bb8  test    eax, eax
0x180008bba  jns     short loc_180008C21
0x180008bbc  mov     r9d, 548h; unsigned int
0x180008bc2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008bc9  lea     rdx, aHr; "hr"
0x180008bd0  mov     ecx, eax; unsigned int
0x180008bd2  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008bd7  mov     rdi, [rbp+var_20]
0x180008bdb  jmp     loc_180008CA5
0x180008be0  lea     rdx, [rbp+StringUuid]; StringUuid
0x180008be4  call    cs:__imp_UuidToStringW
0x180008bea  mov     ebx, eax
0x180008bec  test    eax, eax
0x180008bee  jz      short loc_180008B98
0x180008bf0  mov     r9d, 538h; unsigned int
0x180008bf6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008bfd  lea     rdx, aRpcerror; "rpcError"
0x180008c04  mov     ecx, eax; unsigned int
0x180008c06  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008c0b  test    ebx, ebx
0x180008c0d  jle     loc_180008CA5
0x180008c13  movzx   ebx, bx
0x180008c16  or      ebx, 80070000h
0x180008c1c  jmp     loc_180008CA5
0x180008c21  mov     rdi, [rbp+var_20]
0x180008c25  test    rdi, rdi
0x180008c28  jz      short loc_180008C42
0x180008c2a  cmp     [rdi+70h], r14d
0x180008c2e  jnz     short loc_180008C42
0x180008c30  mov     ebx, 80090003h
0x180008c35  mov     r9d, 550h
0x180008c3b  mov     ecx, 80090003h
0x180008c40  jmp     short loc_180008C92
0x180008c42  mov     edx, [rbp+arg_10]; unsigned int
0x180008c45  lea     r8, [rbp+var_18]; struct _L0_key **
0x180008c49  mov     rcx, rdi; struct _ROOT_KEY_HEADER *
0x180008c4c  call    ?ComputeL0Key@@YAJPEAU_ROOT_KEY_HEADER@@KPEAPEAU_L0_key@@@Z; ComputeL0Key(_ROOT_KEY_HEADER *,ulong,_L0_key * *)
0x180008c51  mov     ebx, eax
0x180008c53  test    eax, eax
0x180008c55  jns     short loc_180008C78
0x180008c57  mov     r9d, 55Bh; unsigned int
0x180008c5d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008c64  lea     rdx, aHr; "hr"
0x180008c6b  mov     ecx, eax; unsigned int
0x180008c6d  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008c72  mov     r14, [rbp+var_18]
0x180008c76  jmp     short loc_180008CA5
0x180008c78  mov     rax, [rbp+var_18]
0x180008c7c  mov     [r12], rax
0x180008c80  jmp     short loc_180008CA5
0x180008c82  mov     ebx, 80090011h
0x180008c87  mov     r9d, 529h; unsigned int
0x180008c8d  mov     ecx, 80090011h; unsigned int
0x180008c92  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008c99  lea     rdx, aHr; "hr"
0x180008ca0  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008ca5  mov     rcx, r14; lpMem
0x180008ca8  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x180008cad  mov     rcx, rdi; lpMem
0x180008cb0  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x180008cb5  cmp     [rbp+StringUuid], 0
0x180008cba  jz      short loc_180008CC6
0x180008cbc  lea     rcx, [rbp+StringUuid]; String
0x180008cc0  call    cs:__imp_RpcStringFreeW
0x180008cc6  mov     rcx, rsi; lpMem
0x180008cc9  call    ?FreeRootKeyMetaDataList@@YAXPEAU_LIST_ENTRY@@@Z; FreeRootKeyMetaDataList(_LIST_ENTRY *)
0x180008cce  mov     eax, ebx
0x180008cd0  mov     rbx, [rsp+60h+arg_8]
0x180008cd8  add     rsp, 60h
0x180008cdc  pop     r15
0x180008cde  pop     r14
0x180008ce0  pop     r13
0x180008ce2  pop     r12
0x180008ce4  pop     rdi
0x180008ce5  pop     rsi
0x180008ce6  pop     rbp
0x180008ce7  retn
```

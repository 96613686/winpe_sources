# GetLatestL0KeyLdap(ldap *,ushort *,ulong,_L0_key * *)

- ea: `0x180008cf0`
- end: `0x180008e16`
- name: `?GetLatestL0KeyLdap@@YAJPEAUldap@@PEAGKPEAPEAU_L0_key@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, unsigned int, struct _L0_key **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000898c`

## callees

- `0x180004d5c`
- `0x180004f40`
- `0x1800054e0`
- `0x180007d28`
- `0x180008cf0`
- `0x1800100d0`
- `0x18001a450`

## string_xrefs

- `0x180008daa`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180008de0`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetLatestL0KeyLdap(struct ldap *a1, unsigned __int16 *a2, unsigned int a3, struct _L0_key **a4)
{
  struct _L0_key *v5; // rsi
  unsigned __int64 CurrentTimeInULL; // rax
  unsigned __int64 v10; // rbp
  int AllRootKeysMetaData; // eax
  struct _LIST_ENTRY *v12; // rdi
  unsigned int v13; // ebx
  unsigned int v14; // r9d
  unsigned int v15; // ecx
  struct _LIST_ENTRY *i; // rax
  UUID *Blink; // r8
  signed int v18; // eax
  struct _ROOT_KEY_HEADER *v20; // [rsp+20h] [rbp-68h]
  struct _L0_key *v21; // [rsp+30h] [rbp-58h] BYREF
  struct _LIST_ENTRY *lpMem; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+20h] BYREF

  v23 = 0;
  v5 = 0;
  v21 = 0;
  lpMem = 0;
  CurrentTimeInULL = GetCurrentTimeInULL();
  *a4 = 0;
  v10 = CurrentTimeInULL;
  AllRootKeysMetaData = GetAllRootKeysMetaData(a1, a2, &v23, &lpMem);
  v12 = lpMem;
  v13 = AllRootKeysMetaData;
  if ( AllRootKeysMetaData < 0 )
  {
    v14 = 1593;
    v15 = AllRootKeysMetaData;
LABEL_15:
    SidKeyDebugTraceError(v15, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v14);
    goto LABEL_16;
  }
  if ( !v23 || !lpMem )
  {
    v14 = 1602;
LABEL_14:
    v15 = -2146893807;
    v13 = -2146893807;
    goto LABEL_15;
  }
  for ( i = lpMem->Flink; ; i = i->Flink )
  {
    if ( i == lpMem )
    {
      v14 = 1613;
      goto LABEL_14;
    }
    Blink = (UUID *)i[-1].Blink;
    if ( *(_QWORD *)Blink[1].Data4 < v10 )
      break;
  }
  v18 = ComputeLatestL0KeyLdap(a1, a2, Blink, a3, v20, &v21);
  v13 = v18;
  if ( v18 >= 0 )
  {
    *a4 = v21;
  }
  else
  {
    SidKeyDebugTraceError(v18, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x65Au);
    v5 = v21;
  }
LABEL_16:
  FreeL0Key(v5);
  FreeRootKeyMetaDataList(v12);
  return v13;
}

```

## disassembly

```asm
0x180008cf0  mov     rax, rsp
0x180008cf3  push    rbx
0x180008cf4  push    rbp
0x180008cf5  push    rsi
0x180008cf6  push    rdi
0x180008cf7  push    r12
0x180008cf9  push    r13
0x180008cfb  push    r14
0x180008cfd  push    r15
0x180008cff  sub     rsp, 48h
0x180008d03  xor     ebx, ebx
0x180008d05  mov     r14, r9
0x180008d08  mov     [rax+20h], ebx
0x180008d0b  mov     esi, ebx
0x180008d0d  mov     [rax-58h], rbx
0x180008d11  mov     r13d, r8d
0x180008d14  mov     [rax-50h], rbx
0x180008d18  mov     r15, rdx
0x180008d1b  mov     r12, rcx
0x180008d1e  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x180008d23  lea     r9, [rsp+88h+lpMem]; struct _LIST_ENTRY **
0x180008d28  mov     [r14], rbx
0x180008d2b  lea     r8, [rsp+88h+arg_18]; unsigned int *
0x180008d33  mov     rdx, r15; unsigned __int16 *
0x180008d36  mov     rcx, r12; ld
0x180008d39  mov     rbp, rax
0x180008d3c  call    ?GetAllRootKeysMetaData@@YAJPEAUldap@@PEBGPEAKPEAPEAU_LIST_ENTRY@@@Z; GetAllRootKeysMetaData(ldap *,ushort const *,ulong *,_LIST_ENTRY * *)
0x180008d41  mov     rdi, [rsp+88h+lpMem]
0x180008d46  mov     ebx, eax
0x180008d48  test    eax, eax
0x180008d4a  jns     short loc_180008D59
0x180008d4c  mov     r9d, 639h
0x180008d52  mov     ecx, eax
0x180008d54  jmp     loc_180008DE0
0x180008d59  cmp     [rsp+88h+arg_18], esi
0x180008d60  jz      short loc_180008DD0
0x180008d62  test    rdi, rdi
0x180008d65  jz      short loc_180008DD0
0x180008d67  mov     rax, [rdi]
0x180008d6a  jmp     short loc_180008D79
0x180008d6c  mov     r8, [rax-8]; Uuid
0x180008d70  cmp     [r8+18h], rbp
0x180008d74  jb      short loc_180008D86
0x180008d76  mov     rax, [rax]
0x180008d79  cmp     rax, rdi
0x180008d7c  jnz     short loc_180008D6C
0x180008d7e  mov     r9d, 64Dh
0x180008d84  jmp     short loc_180008DD6
0x180008d86  lea     rax, [rsp+88h+var_58]
0x180008d8b  mov     r9d, r13d; unsigned int
0x180008d8e  mov     rdx, r15; unsigned __int16 *
0x180008d91  mov     [rsp+88h+var_60], rax; struct _L0_key **
0x180008d96  mov     rcx, r12; struct ldap *
0x180008d99  call    ?ComputeLatestL0KeyLdap@@YAJPEAUldap@@PEAGPEAU_GUID@@K_KPEAPEAU_L0_key@@@Z; ComputeLatestL0KeyLdap(ldap *,ushort *,_GUID *,ulong,unsigned __int64,_L0_key * *)
0x180008d9e  mov     ebx, eax
0x180008da0  test    eax, eax
0x180008da2  jns     short loc_180008DC6
0x180008da4  mov     r9d, 65Ah; unsigned int
0x180008daa  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008db1  lea     rdx, aHr; "hr"
0x180008db8  mov     ecx, eax; unsigned int
0x180008dba  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008dbf  mov     rsi, [rsp+88h+var_58]
0x180008dc4  jmp     short loc_180008DF3
0x180008dc6  mov     rax, [rsp+88h+var_58]
0x180008dcb  mov     [r14], rax
0x180008dce  jmp     short loc_180008DF3
0x180008dd0  mov     r9d, 642h; unsigned int
0x180008dd6  mov     ecx, 80090011h; unsigned int
0x180008ddb  mov     ebx, 80090011h
0x180008de0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008de7  lea     rdx, aHr; "hr"
0x180008dee  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008df3  mov     rcx, rsi; lpMem
0x180008df6  call    ?FreeL0Key@@YAXPEAU_L0_key@@@Z; FreeL0Key(_L0_key *)
0x180008dfb  mov     rcx, rdi; lpMem
0x180008dfe  call    ?FreeRootKeyMetaDataList@@YAXPEAU_LIST_ENTRY@@@Z; FreeRootKeyMetaDataList(_LIST_ENTRY *)
0x180008e03  mov     eax, ebx
0x180008e05  add     rsp, 48h
0x180008e09  pop     r15
0x180008e0b  pop     r14
0x180008e0d  pop     r13
0x180008e0f  pop     r12
0x180008e11  pop     rdi
0x180008e12  pop     rsi
0x180008e13  pop     rbp
0x180008e14  pop     rbx
0x180008e15  retn
```

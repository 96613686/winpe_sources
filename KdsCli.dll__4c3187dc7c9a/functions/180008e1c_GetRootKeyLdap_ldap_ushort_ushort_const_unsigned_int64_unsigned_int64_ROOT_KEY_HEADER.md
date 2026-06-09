# GetRootKeyLdap(ldap *,ushort *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)

- ea: `0x180008e1c`
- end: `0x180008eab`
- name: `?GetRootKeyLdap@@YAJPEAUldap@@PEAGPEBG_K3PEAPEAU_ROOT_KEY_HEADER@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned __int64, struct _ROOT_KEY_HEADER **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007d28`
- `0x180008afc`
- `0x180009a14`

## callees

- `0x180004e20`
- `0x1800058a0`
- `0x180008e1c`
- `0x18001a450`

## string_xrefs

- `0x180008e65`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetRootKeyLdap(
        struct ldap *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _ROOT_KEY_HEADER **a6)
{
  struct _ROOT_KEY_HEADER **v6; // rdi
  int RootKey; // ebx
  struct _ROOT_KEY_HEADER *v8; // rcx
  unsigned __int64 v10; // [rsp+20h] [rbp-18h]
  struct _ROOT_KEY_HEADER *v11; // [rsp+58h] [rbp+20h] BYREF

  v6 = a6;
  v10 = a5;
  *a6 = 0;
  v11 = 0;
  RootKey = GetRootKey(a1, a2, a3, 0, v10, &v11);
  if ( RootKey >= 0 )
  {
    v8 = 0;
    *v6 = v11;
  }
  else
  {
    if ( RootKey == -2147024864 )
      RootKey = -2146893811;
    SidKeyDebugTraceError(RootKey, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 245);
    v8 = v11;
  }
  FreeRootKey(v8);
  return (unsigned int)RootKey;
}

```

## disassembly

```asm
0x180008e1c  mov     r11, rsp
0x180008e1f  mov     [r11+8], rbx
0x180008e23  mov     [r11+20h], r9
0x180008e27  push    rdi
0x180008e28  sub     rsp, 30h
0x180008e2c  mov     rdi, [rsp+38h+arg_28]
0x180008e31  lea     rax, [r11+20h]
0x180008e35  mov     [r11-10h], rax
0x180008e39  xor     r9d, r9d; unsigned __int64
0x180008e3c  mov     rax, [rsp+38h+arg_20]
0x180008e41  mov     [r11-18h], rax
0x180008e45  mov     qword ptr [rdi], 0
0x180008e4c  mov     qword ptr [r11+20h], 0
0x180008e54  call    ?GetRootKey@@YAJPEAUldap@@PEBG1_K2PEAPEAU_ROOT_KEY_HEADER@@@Z; GetRootKey(ldap *,ushort const *,ushort const *,unsigned __int64,unsigned __int64,_ROOT_KEY_HEADER * *)
0x180008e59  mov     ebx, eax
0x180008e5b  test    eax, eax
0x180008e5d  jns     short loc_180008E8F
0x180008e5f  cmp     ebx, 80070020h
0x180008e65  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180008e6c  mov     eax, 8009000Dh
0x180008e71  lea     rdx, aHr; "hr"
0x180008e78  cmovz   ebx, eax
0x180008e7b  mov     r9d, 4F5h; unsigned int
0x180008e81  mov     ecx, ebx; unsigned int
0x180008e83  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180008e88  mov     rcx, [rsp+38h+arg_18]
0x180008e8d  jmp     short loc_180008E99
0x180008e8f  mov     rax, [rsp+38h+arg_18]
0x180008e94  xor     ecx, ecx; lpMem
0x180008e96  mov     [rdi], rax
0x180008e99  call    ?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z; FreeRootKey(_ROOT_KEY_HEADER *)
0x180008e9e  mov     eax, ebx
0x180008ea0  mov     rbx, [rsp+38h+arg_0]
0x180008ea5  add     rsp, 30h
0x180008ea9  pop     rdi
0x180008eaa  retn
```

# KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)

- ea: `0x14001ea54`
- end: `0x14001eaed`
- name: `?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140018ff0`
- `0x14001b45c`
- `0x14001b7cc`
- `0x14001bad8`

## callees

- `0x14001ab10`
- `0x14001ab60`
- `0x14001de00`
- `0x14001e8dc`
- `0x14001ea54`

## pseudocode

```c
_QWORD *__fastcall KerberosCryptoPolicy::FromKerberosKey(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  _BYTE v7[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+28h] [rbp-10h]
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    KerberosCryptoPolicy::Create(&v9);
    v4 = v9;
    if ( v9 )
    {
      v5 = *(_QWORD *)(v9 + 112);
      v7[0] = 0;
      v8 = 0;
      *(_QWORD *)(v9 + 112) = a2;
      if ( v5 && *(_BYTE *)(v4 + 104) )
        KerbFreeKey(v5);
      *(_BYTE *)(v4 + 104) = 0;
      utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(v7);
      *(_BYTE *)(v4 + 8) = 1;
      *a1 = v4;
      v9 = 0;
    }
    else
    {
      *a1 = 0;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v9);
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14001ea54  mov     [rsp+arg_0], rbx
0x14001ea59  mov     [rsp+arg_10], rsi
0x14001ea5e  push    rdi
0x14001ea5f  sub     rsp, 30h
0x14001ea63  mov     rsi, rdx
0x14001ea66  mov     rbx, rcx
0x14001ea69  test    rdx, rdx
0x14001ea6c  jnz     short loc_14001EA73
0x14001ea6e  mov     [rcx], rdx
0x14001ea71  jmp     short loc_14001EADA
0x14001ea73  lea     rcx, [rsp+38h+arg_8]
0x14001ea78  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x14001ea7d  mov     rdi, [rsp+38h+arg_8]
0x14001ea82  test    rdi, rdi
0x14001ea85  jnz     short loc_14001EA8C
0x14001ea87  mov     [rbx], rdi
0x14001ea8a  jmp     short loc_14001EAD0
0x14001ea8c  mov     rcx, [rdi+70h]
0x14001ea90  mov     [rsp+38h+var_18], 0
0x14001ea95  mov     [rsp+38h+var_10], 0
0x14001ea9e  mov     [rdi+70h], rsi
0x14001eaa2  test    rcx, rcx
0x14001eaa5  jz      short loc_14001EAB2
0x14001eaa7  cmp     byte ptr [rdi+68h], 0
0x14001eaab  jz      short loc_14001EAB2
0x14001eaad  call    KerbFreeKey
0x14001eab2  lea     rcx, [rsp+38h+var_18]
0x14001eab7  mov     byte ptr [rdi+68h], 0
0x14001eabb  call    ??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ; utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)
0x14001eac0  mov     byte ptr [rdi+8], 1
0x14001eac4  mov     [rbx], rdi
0x14001eac7  mov     [rsp+38h+arg_8], 0
0x14001ead0  lea     rcx, [rsp+38h+arg_8]
0x14001ead5  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x14001eada  mov     rsi, [rsp+38h+arg_10]
0x14001eadf  mov     rax, rbx
0x14001eae2  mov     rbx, [rsp+38h+arg_0]
0x14001eae7  add     rsp, 30h
0x14001eaeb  pop     rdi
0x14001eaec  retn
```

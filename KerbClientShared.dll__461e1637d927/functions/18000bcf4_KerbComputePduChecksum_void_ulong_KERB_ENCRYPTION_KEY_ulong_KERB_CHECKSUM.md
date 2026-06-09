# KerbComputePduChecksum(void *,ulong,_KERB_ENCRYPTION_KEY *,ulong,KERB_CHECKSUM *)

- ea: `0x18000bcf4`
- end: `0x18000bdb2`
- name: `?KerbComputePduChecksum@@YAJPEAXKPEAU_KERB_ENCRYPTION_KEY@@KPEAUKERB_CHECKSUM@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _KERB_ENCRYPTION_KEY *, unsigned int, struct KERB_CHECKSUM *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a920`
- `0x18000aed0`

## callees

- `0x1800060d0`
- `0x18000bcf4`
- `0x18000bdb8`
- `0x18000bdf8`
- `0x18000c074`

## pseudocode

```c
__int64 __fastcall KerbComputePduChecksum(
        void *a1,
        unsigned int a2,
        struct _KERB_ENCRYPTION_KEY *a3,
        unsigned int a4,
        struct KERB_CHECKSUM *a5)
{
  KerberosCryptoPolicy *v9; // rbx
  unsigned int v10; // ebx
  KerberosCryptoPolicy *v12; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    KerberosCryptoPolicy::Create(&v12);
    v9 = v12;
    if ( v12 )
    {
      KerberosCryptoPolicy::SetKey(v12, a3, 0);
      *((_BYTE *)v9 + 8) = 1;
      v12 = 0;
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>((__int64 *)&v12);
      v12 = v9;
      v10 = KerbComputePduChecksumEx(a1, a2, v9, a4, a5);
      goto LABEL_6;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>((__int64 *)&v12);
  }
  v12 = 0;
  v10 = -1073741670;
LABEL_6:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>((__int64 *)&v12);
  return v10;
}

```

## disassembly

```asm
0x18000bcf4  mov     [rsp+arg_0], rbx
0x18000bcf9  mov     [rsp+arg_8], rbp
0x18000bcfe  push    rsi
0x18000bcff  push    rdi
0x18000bd00  push    r14
0x18000bd02  sub     rsp, 30h
0x18000bd06  mov     esi, r9d
0x18000bd09  mov     rdi, r8
0x18000bd0c  mov     ebp, edx
0x18000bd0e  mov     r14, rcx
0x18000bd11  test    r8, r8
0x18000bd14  jnz     short loc_18000BD21
0x18000bd16  mov     [rsp+48h+arg_10], 0
0x18000bd1f  jmp     short loc_18000BD70
0x18000bd21  lea     rcx, [rsp+48h+arg_10]
0x18000bd26  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18000bd2b  mov     rbx, [rsp+48h+arg_10]
0x18000bd30  test    rbx, rbx
0x18000bd33  jnz     short loc_18000BD41
0x18000bd35  lea     rcx, [rsp+48h+arg_10]
0x18000bd3a  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000bd3f  jmp     short loc_18000BD16
0x18000bd41  xor     r8d, r8d; bool
0x18000bd44  mov     rdx, rdi; struct _KERB_ENCRYPTION_KEY *
0x18000bd47  mov     rcx, rbx; this
0x18000bd4a  call    ?SetKey@KerberosCryptoPolicy@@QEAAXPEAU_KERB_ENCRYPTION_KEY@@_N@Z; KerberosCryptoPolicy::SetKey(_KERB_ENCRYPTION_KEY *,bool)
0x18000bd4f  lea     rcx, [rsp+48h+arg_10]
0x18000bd54  mov     byte ptr [rbx+8], 1
0x18000bd58  mov     [rsp+48h+arg_10], 0
0x18000bd61  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000bd66  mov     [rsp+48h+arg_10], rbx
0x18000bd6b  test    rbx, rbx
0x18000bd6e  jnz     short loc_18000BD77
0x18000bd70  mov     ebx, 0C000009Ah
0x18000bd75  jmp     short loc_18000BD93
0x18000bd77  mov     rax, [rsp+48h+arg_20]
0x18000bd7c  mov     r9d, esi; unsigned int
0x18000bd7f  mov     r8, rbx; struct KerberosCryptoPolicy *
0x18000bd82  mov     [rsp+48h+var_28], rax; struct KERB_CHECKSUM *
0x18000bd87  mov     edx, ebp; unsigned int
0x18000bd89  mov     rcx, r14; void *
0x18000bd8c  call    ?KerbComputePduChecksumEx@@YAJPEAXKPEAVKerberosCryptoPolicy@@KPEAUKERB_CHECKSUM@@@Z; KerbComputePduChecksumEx(void *,ulong,KerberosCryptoPolicy *,ulong,KERB_CHECKSUM *)
0x18000bd91  mov     ebx, eax
0x18000bd93  lea     rcx, [rsp+48h+arg_10]
0x18000bd98  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000bd9d  mov     rbp, [rsp+48h+arg_8]
0x18000bda2  mov     eax, ebx
0x18000bda4  mov     rbx, [rsp+48h+arg_0]
0x18000bda9  add     rsp, 30h
0x18000bdad  pop     r14
0x18000bdaf  pop     rdi
0x18000bdb0  pop     rsi
0x18000bdb1  retn
```

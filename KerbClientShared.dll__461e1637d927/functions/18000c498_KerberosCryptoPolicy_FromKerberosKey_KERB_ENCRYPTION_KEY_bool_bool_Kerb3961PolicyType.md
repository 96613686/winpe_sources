# KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)

- ea: `0x18000c498`
- end: `0x18000c506`
- name: `?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a920`
- `0x18000c2d0`

## callees

- `0x1800060d0`
- `0x18000bdb8`
- `0x18000c074`
- `0x18000c498`

## pseudocode

```c
KerberosCryptoPolicy **__fastcall KerberosCryptoPolicy::FromKerberosKey(
        KerberosCryptoPolicy **a1,
        struct _KERB_ENCRYPTION_KEY *a2,
        __int64 a3,
        char a4)
{
  KerberosCryptoPolicy *v7; // rdi
  KerberosCryptoPolicy *v9; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    KerberosCryptoPolicy::Create(&v9);
    v7 = v9;
    if ( v9 )
    {
      KerberosCryptoPolicy::SetKey(v9, a2, 0);
      if ( a4 )
        *((_BYTE *)v7 + 8) = 1;
      v9 = 0;
      *a1 = v7;
    }
    else
    {
      *a1 = 0;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>((__int64 *)&v9);
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
0x18000c498  push    rbx
0x18000c49a  push    rbp
0x18000c49b  push    rsi
0x18000c49c  push    rdi
0x18000c49d  sub     rsp, 28h
0x18000c4a1  mov     bpl, r9b
0x18000c4a4  mov     rsi, rdx
0x18000c4a7  mov     rbx, rcx
0x18000c4aa  test    rdx, rdx
0x18000c4ad  jnz     short loc_18000C4B4
0x18000c4af  mov     [rcx], rdx
0x18000c4b2  jmp     short loc_18000C4FA
0x18000c4b4  lea     rcx, [rsp+48h+arg_8]
0x18000c4b9  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18000c4be  mov     rdi, [rsp+48h+arg_8]
0x18000c4c3  test    rdi, rdi
0x18000c4c6  jnz     short loc_18000C4CD
0x18000c4c8  mov     [rbx], rdi
0x18000c4cb  jmp     short loc_18000C4F0
0x18000c4cd  xor     r8d, r8d; bool
0x18000c4d0  mov     rdx, rsi; struct _KERB_ENCRYPTION_KEY *
0x18000c4d3  mov     rcx, rdi; this
0x18000c4d6  call    ?SetKey@KerberosCryptoPolicy@@QEAAXPEAU_KERB_ENCRYPTION_KEY@@_N@Z; KerberosCryptoPolicy::SetKey(_KERB_ENCRYPTION_KEY *,bool)
0x18000c4db  test    bpl, bpl
0x18000c4de  jz      short loc_18000C4E4
0x18000c4e0  mov     byte ptr [rdi+8], 1
0x18000c4e4  mov     [rsp+48h+arg_8], 0
0x18000c4ed  mov     [rbx], rdi
0x18000c4f0  lea     rcx, [rsp+48h+arg_8]
0x18000c4f5  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000c4fa  mov     rax, rbx
0x18000c4fd  add     rsp, 28h
0x18000c501  pop     rdi
0x18000c502  pop     rsi
0x18000c503  pop     rbp
0x18000c504  pop     rbx
0x18000c505  retn
```

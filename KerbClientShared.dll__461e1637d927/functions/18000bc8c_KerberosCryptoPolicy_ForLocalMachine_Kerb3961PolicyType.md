# KerberosCryptoPolicy::ForLocalMachine(Kerb3961PolicyType)

- ea: `0x18000bc8c`
- end: `0x18000bcec`
- name: `?ForLocalMachine@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009c50`
- `0x180009d60`
- `0x180009fa0`
- `0x18000a1b0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000b790`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180016190`

## callees

- `0x1800060d0`
- `0x18000bc8c`
- `0x18000c074`
- `0x180017ae8`

## pseudocode

```c
__int64 *__fastcall KerberosCryptoPolicy::ForLocalMachine(__int64 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdi
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  KerberosCryptoPolicy::Create(&v5);
  v3 = v5;
  if ( v5 && (unsigned __int8)KerberosCryptoPolicy::SetPartnerAttributes(v5, v2, 256) )
  {
    v5 = 0;
    *a1 = v3;
  }
  else
  {
    *a1 = 0;
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v5);
  return a1;
}

```

## disassembly

```asm
0x18000bc8c  mov     [rsp+arg_0], rbx
0x18000bc91  push    rdi
0x18000bc92  sub     rsp, 20h
0x18000bc96  mov     rbx, rcx
0x18000bc99  lea     rcx, [rsp+28h+arg_10]
0x18000bc9e  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18000bca3  mov     rdi, [rsp+28h+arg_10]
0x18000bca8  test    rdi, rdi
0x18000bcab  jz      short loc_18000BCCD
0x18000bcad  mov     r8d, 100h
0x18000bcb3  mov     rcx, rdi
0x18000bcb6  call    ?SetPartnerAttributes@KerberosCryptoPolicy@@QEAA_NKW4UserPolicyAttributes@Kerb3961@@@Z; KerberosCryptoPolicy::SetPartnerAttributes(ulong,Kerb3961::UserPolicyAttributes)
0x18000bcbb  test    al, al
0x18000bcbd  jz      short loc_18000BCCD
0x18000bcbf  mov     [rsp+28h+arg_10], 0
0x18000bcc8  mov     [rbx], rdi
0x18000bccb  jmp     short loc_18000BCD4
0x18000bccd  mov     qword ptr [rbx], 0
0x18000bcd4  lea     rcx, [rsp+28h+arg_10]
0x18000bcd9  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000bcde  mov     rax, rbx
0x18000bce1  mov     rbx, [rsp+28h+arg_0]
0x18000bce6  add     rsp, 20h
0x18000bcea  pop     rdi
0x18000bceb  retn
```

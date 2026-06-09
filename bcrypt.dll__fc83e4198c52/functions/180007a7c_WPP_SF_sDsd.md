# WPP_SF_sDsd

- ea: `0x180007a7c`
- end: `0x180007b3d`
- name: `WPP_SF_sDsd`
- size: `193`
- prototype: ``
- caller_count: `54`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001590`
- `0x180002de0`
- `0x180004230`
- `0x180004390`
- `0x18000466c`
- `0x180004800`
- `0x1800049a0`
- `0x180005060`
- `0x180005280`
- `0x180005470`
- `0x180005b00`
- `0x180005bc0`
- `0x180006020`
- `0x1800066f0`
- `0x180006da0`
- `0x1800078e0`
- `0x180007b50`
- `0x180007d60`
- `0x180008890`
- `0x1800090a0`
- `0x180009454`
- `0x180009570`
- `0x180009764`
- `0x180009ba0`
- `0x18000a070`
- `0x18000a230`
- `0x18000a4e0`
- `0x18000a768`
- `0x18000ab58`
- `0x18000acc0`
- `0x18000af30`
- `0x18000b1d0`
- `0x18000b680`
- `0x18000b824`
- `0x18000bac0`
- `0x18000bba0`
- `0x18000c1e0`
- `0x18000cc10`
- `0x18000ce50`
- `0x18000d030`
- `0x18000dac4`
- `0x18000e2c4`
- `0x18000e368`
- `0x18000e628`
- `0x18000e7fc`
- `0x18000e910`
- `0x18000edac`
- `0x18000f1fc`
- `0x18000fb30`
- `0x180010680`

## callees

- `0x180007a7c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007b2a`
- `ntdll!EtwTraceMessage` at `0x180007b2a`

## pseudocode

```c
__int64 WPP_SF_sDsd(__int64 a1, __int64 a2, __int64 a3, const char *a4, ...)
{
  const char *v4; // r8
  __int64 v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // rdx
  bool v9; // zf
  __int64 v11; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  const char *v13; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, const char *);
  v4 = v13;
  v5 = -1;
  v6 = 5;
  if ( v13 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v13[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  if ( !v13 )
    v4 = "NULL";
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = "NULL";
  return EtwTraceMessage(
           a1,
           43,
           WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids,
           10,
           a4,
           v6,
           (__int64 *)va,
           4,
           v4,
           v8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x180007a7c  push    rbx
0x180007a7e  sub     rsp, 70h
0x180007a82  mov     r8, [rsp+78h+arg_28]
0x180007a8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007a8e  xor     r11d, r11d
0x180007a91  mov     r10d, 5
0x180007a97  test    r8, r8
0x180007a9a  jz      short loc_180007AAD
0x180007a9c  mov     rdx, rax
0x180007a9f  inc     rdx
0x180007aa2  cmp     [r8+rdx], r11b
0x180007aa6  jnz     short loc_180007A9F
0x180007aa8  inc     rdx
0x180007aab  jmp     short loc_180007AB0
0x180007aad  mov     rdx, r10
0x180007ab0  test    r8, r8
0x180007ab3  lea     rbx, aNull; "NULL"
0x180007aba  cmovz   r8, rbx
0x180007abe  test    r9, r9
0x180007ac1  jz      short loc_180007AD3
0x180007ac3  inc     rax
0x180007ac6  cmp     [r9+rax], r11b
0x180007aca  jnz     short loc_180007AC3
0x180007acc  lea     r10, [rax+1]
0x180007ad0  test    r9, r9
0x180007ad3  mov     [rsp+78h+var_18], r11
0x180007ad8  lea     rax, [rsp+78h+arg_30]
0x180007ae0  cmovz   r9, rbx
0x180007ae4  mov     ebx, 0Ah
0x180007ae9  lea     r11d, [rbx-6]
0x180007aed  mov     [rsp+78h+var_20], r11
0x180007af2  mov     [rsp+78h+var_28], rax
0x180007af7  lea     rax, [rsp+78h+arg_20]
0x180007aff  mov     [rsp+78h+var_30], rdx
0x180007b04  lea     edx, [rbx+21h]
0x180007b07  mov     [rsp+78h+var_38], r8
0x180007b0c  lea     r8, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids
0x180007b13  mov     [rsp+78h+var_40], r11
0x180007b18  mov     [rsp+78h+var_48], rax
0x180007b1d  mov     [rsp+78h+var_50], r10
0x180007b22  mov     [rsp+78h+var_58], r9
0x180007b27  mov     r9d, ebx
0x180007b2a  call    cs:__imp_EtwTraceMessage
0x180007b31  nop     dword ptr [rax+rax+00h]
0x180007b36  add     rsp, 70h
0x180007b3a  pop     rbx
0x180007b3b  retn
```

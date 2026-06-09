# McTemplateU0qzz_EventWriteTransfer

- ea: `0x180019cc0`
- end: `0x180019d91`
- name: `McTemplateU0qzz_EventWriteTransfer`
- size: `209`
- prototype: `ULONG __fastcall(__int64, __int64, int, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000aa90`

## callees

- `0x18000b448`
- `0x180019cc0`
- `0x18001a380`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  const wchar_t *v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-50h] BYREF
  int *v13; // [rsp+40h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-38h]
  const wchar_t *v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+58h] [rbp-28h]
  int v17; // [rsp+5Ch] [rbp-24h]
  const wchar_t *v18; // [rsp+60h] [rbp-20h]
  int v19; // [rsp+68h] [rbp-18h]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = a3;
  v13 = &v21;
  v5 = -1;
  v14 = 4;
  v6 = 10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v16 = v8;
  v9 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
  v10 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v6 = 2 * v5 + 2;
    v10 = a5 == 0;
  }
  if ( v10 )
    v9 = L"NULL";
  v19 = v6;
  v18 = v9;
  v20 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)RegistryFailureEvent,
           0,
           4u,
           &v12);
}

```

## disassembly

```asm
0x180019cc0  mov     [rsp-8+arg_10], r8d
0x180019cc5  push    rbp
0x180019cc6  mov     rbp, rsp
0x180019cc9  sub     rsp, 80h
0x180019cd0  mov     rax, cs:__security_cookie
0x180019cd7  xor     rax, rsp
0x180019cda  mov     [rbp+var_10], rax
0x180019cde  lea     rax, [rbp+arg_10]
0x180019ce2  mov     r11d, 4
0x180019ce8  mov     [rbp+var_40], rax
0x180019cec  xor     r8d, r8d
0x180019cef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019cf3  mov     [rbp+var_38], r11
0x180019cf7  lea     edx, [r11+6]
0x180019cfb  test    r9, r9
0x180019cfe  jz      short loc_180019D16
0x180019d00  mov     rcx, rax
0x180019d03  inc     rcx
0x180019d06  cmp     [r9+rcx*2], r8w
0x180019d0b  jnz     short loc_180019D03
0x180019d0d  lea     ecx, ds:2[rcx*2]
0x180019d14  jmp     short loc_180019D18
0x180019d16  mov     ecx, edx
0x180019d18  test    r9, r9
0x180019d1b  mov     [rbp+var_28], ecx
0x180019d1e  mov     rcx, [rbp+arg_20]
0x180019d22  lea     r10, aNull_1; "NULL"
0x180019d29  cmovz   r9, r10
0x180019d2d  mov     [rbp+var_24], r8d
0x180019d31  mov     [rbp+var_30], r9
0x180019d35  test    rcx, rcx
0x180019d38  jz      short loc_180019D4E
0x180019d3a  inc     rax
0x180019d3d  cmp     [rcx+rax*2], r8w
0x180019d42  jnz     short loc_180019D3A
0x180019d44  lea     edx, ds:2[rax*2]
0x180019d4b  test    rcx, rcx
0x180019d4e  cmovz   rcx, r10
0x180019d52  mov     [rbp+var_18], edx
0x180019d55  mov     [rbp+var_20], rcx
0x180019d59  lea     rax, [rbp+var_50]
0x180019d5d  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180019d64  mov     [rbp+var_14], r8d
0x180019d68  mov     r9d, r11d
0x180019d6b  mov     [rsp+80h+var_60], rax
0x180019d70  lea     rdx, RegistryFailureEvent
0x180019d77  call    McGenEventWrite_EventWriteTransfer
0x180019d7c  mov     rcx, [rbp+var_10]
0x180019d80  xor     rcx, rsp; StackCookie
0x180019d83  call    __security_check_cookie
0x180019d88  add     rsp, 80h
0x180019d8f  pop     rbp
0x180019d90  retn
```

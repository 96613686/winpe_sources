# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000aebc`
- end: `0x18000af74`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `184`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae60`

## callees

- `0x18000aebc`
- `0x18000b448`
- `0x18001a380`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  int v7; // ecx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x18000aebc  sub     rsp, 78h
0x18000aec0  mov     rax, cs:__security_cookie
0x18000aec7  xor     rax, rsp
0x18000aeca  mov     [rsp+78h+var_18], rax
0x18000aecf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aed3  xor     r10d, r10d
0x18000aed6  mov     edx, 0Ah
0x18000aedb  test    r8, r8
0x18000aede  jz      short loc_18000AEF6
0x18000aee0  mov     rcx, rax
0x18000aee3  inc     rcx
0x18000aee6  cmp     [r8+rcx*2], r10w
0x18000aeeb  jnz     short loc_18000AEE3
0x18000aeed  lea     ecx, ds:2[rcx*2]
0x18000aef4  jmp     short loc_18000AEF8
0x18000aef6  mov     ecx, edx
0x18000aef8  test    r8, r8
0x18000aefb  mov     [rsp+78h+var_30], ecx
0x18000aeff  lea     r11, aNull_1; "NULL"
0x18000af06  mov     [rsp+78h+var_2C], r10d
0x18000af0b  cmovz   r8, r11
0x18000af0f  mov     [rsp+78h+var_38], r8
0x18000af14  test    r9, r9
0x18000af17  jz      short loc_18000AF2D
0x18000af19  inc     rax
0x18000af1c  cmp     [r9+rax*2], r10w
0x18000af21  jnz     short loc_18000AF19
0x18000af23  lea     edx, ds:2[rax*2]
0x18000af2a  test    r9, r9
0x18000af2d  cmovz   r9, r11
0x18000af31  mov     [rsp+78h+var_20], edx
0x18000af35  mov     [rsp+78h+var_28], r9
0x18000af3a  lea     rax, [rsp+78h+var_48]
0x18000af3f  mov     r9d, 3
0x18000af45  mov     [rsp+78h+var_1C], r10d
0x18000af4a  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000af51  mov     [rsp+78h+var_58], rax
0x18000af56  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000af5d  call    McGenEventWrite_EventWriteTransfer
0x18000af62  mov     rcx, [rsp+78h+var_18]
0x18000af67  xor     rcx, rsp; StackCookie
0x18000af6a  call    __security_check_cookie
0x18000af6f  add     rsp, 78h
0x18000af73  retn
```

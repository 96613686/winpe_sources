# McTemplateU0zz_EventWriteTransfer

- ea: `0x180011eb4`
- end: `0x180011f6d`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012a58`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011eb4`

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
           (REGHANDLE *)MDM_ENTERPRISE_DIAGNOSTICS_Context,
           (const EVENT_DESCRIPTOR *)SIDMismatchDuringImpersonation,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x180011eb4  sub     rsp, 78h
0x180011eb8  mov     rax, cs:__security_cookie
0x180011ebf  xor     rax, rsp
0x180011ec2  mov     [rsp+78h+var_18], rax
0x180011ec7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011ecb  xor     r10d, r10d
0x180011ece  mov     edx, 0Ah
0x180011ed3  test    r8, r8
0x180011ed6  jz      short loc_180011EEE
0x180011ed8  mov     rcx, rax
0x180011edb  inc     rcx
0x180011ede  cmp     [r8+rcx*2], r10w
0x180011ee3  jnz     short loc_180011EDB
0x180011ee5  lea     ecx, ds:2[rcx*2]
0x180011eec  jmp     short loc_180011EF0
0x180011eee  mov     ecx, edx
0x180011ef0  test    r8, r8
0x180011ef3  mov     [rsp+78h+var_30], ecx
0x180011ef7  lea     r11, aNull_0; "NULL"
0x180011efe  mov     [rsp+78h+var_2C], r10d
0x180011f03  cmovz   r8, r11
0x180011f07  mov     [rsp+78h+var_38], r8
0x180011f0c  test    r9, r9
0x180011f0f  jz      short loc_180011F25
0x180011f11  inc     rax
0x180011f14  cmp     [r9+rax*2], r10w
0x180011f19  jnz     short loc_180011F11
0x180011f1b  lea     edx, ds:2[rax*2]
0x180011f22  test    r9, r9
0x180011f25  cmovz   r9, r11
0x180011f29  mov     [rsp+78h+var_20], edx
0x180011f2d  mov     [rsp+78h+var_28], r9
0x180011f32  lea     rax, [rsp+78h+var_48]
0x180011f37  mov     r9d, 3
0x180011f3d  mov     [rsp+78h+var_1C], r10d
0x180011f42  lea     rdx, SIDMismatchDuringImpersonation
0x180011f49  mov     [rsp+78h+var_58], rax
0x180011f4e  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180011f55  call    McGenEventWrite_EventWriteTransfer
0x180011f5a  mov     rcx, [rsp+78h+var_18]
0x180011f5f  xor     rcx, rsp; StackCookie
0x180011f62  call    __security_check_cookie
0x180011f67  add     rsp, 78h
0x180011f6b  retn
```

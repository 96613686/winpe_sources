# McTemplateU0z_EventWriteTransfer

- ea: `0x18000bd60`
- end: `0x18000bde6`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000913c`
- `0x18000dabc`

## callees

- `0x180004d70`
- `0x18000bd60`
- `0x180013700`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer(
           MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
           &MetadataPackageBlocked,
           (__int64)a3,
           2u,
           &v6);
}

```

## disassembly

```asm
0x18000bd60  sub     rsp, 68h
0x18000bd64  mov     rax, cs:__security_cookie
0x18000bd6b  xor     rax, rsp
0x18000bd6e  mov     [rsp+68h+var_18], rax
0x18000bd73  xor     edx, edx
0x18000bd75  test    r8, r8
0x18000bd78  jz      short loc_18000BD91
0x18000bd7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bd7e  inc     rax
0x18000bd81  cmp     [r8+rax*2], dx
0x18000bd86  jnz     short loc_18000BD7E
0x18000bd88  lea     eax, ds:2[rax*2]
0x18000bd8f  jmp     short loc_18000BD96
0x18000bd91  mov     eax, 0Ah
0x18000bd96  test    r8, r8
0x18000bd99  mov     [rsp+68h+var_20], eax
0x18000bd9d  lea     rcx, aNull; "NULL"
0x18000bda4  mov     [rsp+68h+var_1C], edx
0x18000bda8  cmovz   r8, rcx
0x18000bdac  lea     rax, [rsp+68h+var_38]
0x18000bdb1  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18000bdb8  mov     [rsp+68h+var_28], r8
0x18000bdbd  mov     r9d, 2
0x18000bdc3  mov     [rsp+68h+var_48], rax
0x18000bdc8  lea     rdx, MetadataPackageBlocked
0x18000bdcf  call    McGenEventWrite_EventWriteTransfer
0x18000bdd4  mov     rcx, [rsp+68h+var_18]
0x18000bdd9  xor     rcx, rsp; StackCookie
0x18000bddc  call    __security_check_cookie
0x18000bde1  add     rsp, 68h
0x18000bde5  retn
```

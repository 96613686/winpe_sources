# LogFileError(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,int)

- ea: `0x1800044f4`
- end: `0x1800045c6`
- name: `?LogFileError@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1H@Z`
- size: `210`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029fc`
- `0x180002a88`
- `0x1800040a8`

## callees

- `0x1800044f4`
- `0x1800051c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800045a9`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800045a9`

## pseudocode

```c
void __fastcall LogFileError(
        PCEVENT_DESCRIPTOR EventDescriptor,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v4; // rax
  int v6; // r9d
  __int64 v7; // rcx
  ULONG v8; // ecx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-40h] BYREF
  const unsigned __int16 *v11; // [rsp+30h] [rbp-30h]
  int v12; // [rsp+38h] [rbp-28h]
  int v13; // [rsp+3Ch] [rbp-24h]
  int *v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+88h] [rbp+28h] BYREF

  v16 = a4;
  v4 = -1;
  v6 = 10;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  UserData.Size = v8;
  UserData.Reserved = 0;
  if ( !a2 )
    a2 = L"NULL";
  UserData.Ptr = (ULONGLONG)a2;
  v9 = a3 == 0;
  if ( a3 )
  {
    do
      ++v4;
    while ( a3[v4] );
    v6 = 2 * v4 + 2;
    v9 = a3 == 0;
  }
  if ( v9 )
    a3 = L"NULL";
  v12 = v6;
  v11 = a3;
  v13 = 0;
  v14 = &v16;
  v15 = 4;
  EventWrite(RegHandle, EventDescriptor, 3u, &UserData);
}

```

## disassembly

```asm
0x1800044f4  mov     [rsp-8+arg_8], rbx
0x1800044f9  mov     [rsp-8+arg_18], r9d
0x1800044fe  push    rbp
0x1800044ff  mov     rbp, rsp
0x180004502  sub     rsp, 60h
0x180004506  mov     rax, cs:__security_cookie
0x18000450d  xor     rax, rsp
0x180004510  mov     [rbp+var_10], rax
0x180004514  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004518  xor     r11d, r11d
0x18000451b  mov     r10, rcx
0x18000451e  mov     r9d, 0Ah
0x180004524  test    rdx, rdx
0x180004527  jz      short loc_18000453F
0x180004529  mov     rcx, rax
0x18000452c  inc     rcx
0x18000452f  cmp     [rdx+rcx*2], r11w
0x180004534  jnz     short loc_18000452C
0x180004536  lea     ecx, ds:2[rcx*2]
0x18000453d  jmp     short loc_180004542
0x18000453f  mov     ecx, r9d
0x180004542  test    rdx, rdx
0x180004545  mov     [rbp+UserData.Size], ecx
0x180004548  lea     rbx, aNull; "NULL"
0x18000454f  mov     dword ptr [rbp+UserData.0Ch], r11d
0x180004553  cmovz   rdx, rbx
0x180004557  mov     [rbp+UserData.Ptr], rdx
0x18000455b  test    r8, r8
0x18000455e  jz      short loc_180004575
0x180004560  inc     rax
0x180004563  cmp     [r8+rax*2], r11w
0x180004568  jnz     short loc_180004560
0x18000456a  lea     r9d, ds:2[rax*2]
0x180004572  test    r8, r8
0x180004575  mov     rcx, cs:RegHandle; RegHandle
0x18000457c  lea     rax, [rbp+arg_18]
0x180004580  cmovz   r8, rbx
0x180004584  mov     [rbp+var_28], r9d
0x180004588  mov     [rbp+var_30], r8
0x18000458c  lea     r9, [rbp+UserData]; UserData
0x180004590  mov     r8d, 3; UserDataCount
0x180004596  mov     [rbp+var_24], r11d
0x18000459a  mov     rdx, r10; EventDescriptor
0x18000459d  mov     [rbp+var_20], rax
0x1800045a1  mov     [rbp+var_18], 4
0x1800045a9  call    cs:__imp_EventWrite
0x1800045af  mov     rcx, [rbp+var_10]
0x1800045b3  xor     rcx, rsp; StackCookie
0x1800045b6  call    __security_check_cookie
0x1800045bb  mov     rbx, [rsp+60h+arg_8]
0x1800045c0  add     rsp, 60h
0x1800045c4  pop     rbp
0x1800045c5  retn
```

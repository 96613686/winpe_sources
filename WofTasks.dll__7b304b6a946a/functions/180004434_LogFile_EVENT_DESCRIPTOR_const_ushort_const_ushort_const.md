# LogFile(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)

- ea: `0x180004434`
- end: `0x1800044ee`
- name: `?LogFile@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1@Z`
- size: `186`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019d4`
- `0x180001e9c`
- `0x1800040a8`

## callees

- `0x180004434`
- `0x1800051c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800044d5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800044d5`

## pseudocode

```c
void __fastcall LogFile(PCEVENT_DESCRIPTOR EventDescriptor, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rax
  int v5; // r9d
  __int64 v6; // rcx
  ULONG v7; // ecx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int16 *v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+3Ch] [rbp-1Ch]

  v3 = -1;
  v5 = 10;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  UserData.Size = v7;
  UserData.Reserved = 0;
  if ( !a2 )
    a2 = L"NULL";
  UserData.Ptr = (ULONGLONG)a2;
  v8 = a3 == 0;
  if ( a3 )
  {
    do
      ++v3;
    while ( a3[v3] );
    v5 = 2 * v3 + 2;
    v8 = a3 == 0;
  }
  if ( v8 )
    a3 = L"NULL";
  v10 = a3;
  v11 = v5;
  v12 = 0;
  EventWrite(RegHandle, EventDescriptor, 2u, &UserData);
}

```

## disassembly

```asm
0x180004434  push    rbx
0x180004436  sub     rsp, 50h
0x18000443a  mov     rax, cs:__security_cookie
0x180004441  xor     rax, rsp
0x180004444  mov     [rsp+58h+var_18], rax
0x180004449  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000444d  xor     r11d, r11d
0x180004450  mov     r10, rcx
0x180004453  mov     r9d, 0Ah
0x180004459  test    rdx, rdx
0x18000445c  jz      short loc_180004474
0x18000445e  mov     rcx, rax
0x180004461  inc     rcx
0x180004464  cmp     [rdx+rcx*2], r11w
0x180004469  jnz     short loc_180004461
0x18000446b  lea     ecx, ds:2[rcx*2]
0x180004472  jmp     short loc_180004477
0x180004474  mov     ecx, r9d
0x180004477  test    rdx, rdx
0x18000447a  mov     [rsp+58h+UserData.Size], ecx
0x18000447e  lea     rbx, aNull; "NULL"
0x180004485  mov     dword ptr [rsp+58h+UserData.0Ch], r11d
0x18000448a  cmovz   rdx, rbx
0x18000448e  mov     [rsp+58h+UserData.Ptr], rdx
0x180004493  test    r8, r8
0x180004496  jz      short loc_1800044AD
0x180004498  inc     rax
0x18000449b  cmp     [r8+rax*2], r11w
0x1800044a0  jnz     short loc_180004498
0x1800044a2  lea     r9d, ds:2[rax*2]
0x1800044aa  test    r8, r8
0x1800044ad  mov     rcx, cs:RegHandle; RegHandle
0x1800044b4  cmovz   r8, rbx
0x1800044b8  mov     [rsp+58h+var_28], r8
0x1800044bd  mov     rdx, r10; EventDescriptor
0x1800044c0  mov     [rsp+58h+var_20], r9d
0x1800044c5  mov     r8d, 2; UserDataCount
0x1800044cb  lea     r9, [rsp+58h+UserData]; UserData
0x1800044d0  mov     [rsp+58h+var_1C], r11d
0x1800044d5  call    cs:__imp_EventWrite
0x1800044db  mov     rcx, [rsp+58h+var_18]
0x1800044e0  xor     rcx, rsp; StackCookie
0x1800044e3  call    __security_check_cookie
0x1800044e8  add     rsp, 50h
0x1800044ec  pop     rbx
0x1800044ed  retn
```

# LogFileOffset(_EVENT_DESCRIPTOR const *,ushort const *,unsigned __int64)

- ea: `0x1800045cc`
- end: `0x180004664`
- name: `?LogFileOffset@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG_K@Z`
- size: `152`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002474`
- `0x1800040a8`

## callees

- `0x1800045cc`
- `0x1800051c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000464c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000464c`

## pseudocode

```c
void __fastcall LogFileOffset(PCEVENT_DESCRIPTOR EventDescriptor, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v3; // rax
  ULONG v4; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v6; // [rsp+30h] [rbp-28h]
  __int64 v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF

  v8 = a3;
  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  UserData.Size = v4;
  UserData.Reserved = 0;
  if ( !a2 )
    a2 = L"NULL";
  v7 = 8;
  UserData.Ptr = (ULONGLONG)a2;
  v6 = &v8;
  EventWrite(RegHandle, EventDescriptor, 2u, &UserData);
}

```

## disassembly

```asm
0x1800045cc  mov     [rsp+arg_10], r8
0x1800045d1  sub     rsp, 58h
0x1800045d5  mov     rax, cs:__security_cookie
0x1800045dc  xor     rax, rsp
0x1800045df  mov     [rsp+58h+var_18], rax
0x1800045e4  xor     r9d, r9d
0x1800045e7  test    rdx, rdx
0x1800045ea  jz      short loc_180004603
0x1800045ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800045f0  inc     rax
0x1800045f3  cmp     [rdx+rax*2], r9w
0x1800045f8  jnz     short loc_1800045F0
0x1800045fa  lea     eax, ds:2[rax*2]
0x180004601  jmp     short loc_180004608
0x180004603  mov     eax, 0Ah
0x180004608  test    rdx, rdx
0x18000460b  mov     [rsp+58h+UserData.Size], eax
0x18000460f  lea     r8, aNull; "NULL"
0x180004616  mov     dword ptr [rsp+58h+UserData.0Ch], r9d
0x18000461b  cmovz   rdx, r8
0x18000461f  mov     [rsp+58h+var_20], 8
0x180004628  mov     [rsp+58h+UserData.Ptr], rdx
0x18000462d  lea     rax, [rsp+58h+arg_10]
0x180004632  mov     rdx, rcx; EventDescriptor
0x180004635  mov     [rsp+58h+var_28], rax
0x18000463a  mov     rcx, cs:RegHandle; RegHandle
0x180004641  lea     r9, [rsp+58h+UserData]; UserData
0x180004646  mov     r8d, 2; UserDataCount
0x18000464c  call    cs:__imp_EventWrite
0x180004652  mov     rcx, [rsp+58h+var_18]
0x180004657  xor     rcx, rsp; StackCookie
0x18000465a  call    __security_check_cookie
0x18000465f  add     rsp, 58h
0x180004663  retn
```

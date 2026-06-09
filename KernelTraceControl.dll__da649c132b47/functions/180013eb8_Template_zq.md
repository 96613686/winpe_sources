# Template_zq

- ea: `0x180013eb8`
- end: `0x180013f4d`
- name: `Template_zq`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014e44`

## callees

- `0x180013eb8`
- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013f35`
- `ADVAPI32!EventWrite` at `0x180013f35`

## pseudocode

```c
ULONG __fastcall Template_zq(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  ULONG v5; // ecx
  const wchar_t *v6; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  int *v9; // [rsp+30h] [rbp-28h]
  __int64 v10; // [rsp+38h] [rbp-20h]
  int v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  UserData.Size = v5;
  UserData.Reserved = 0;
  v6 = L"NULL";
  if ( a3 )
    v6 = a3;
  v10 = 4;
  UserData.Ptr = (ULONGLONG)v6;
  v9 = &v11;
  return EventWrite(0, &TraceMerge_NGEN_BinaryNotFound, 2u, &UserData);
}

```

## disassembly

```asm
0x180013eb8  mov     [rsp+arg_18], r9d
0x180013ebd  sub     rsp, 58h
0x180013ec1  mov     rax, cs:__security_cookie
0x180013ec8  xor     rax, rsp
0x180013ecb  mov     [rsp+58h+var_10], rax
0x180013ed0  xor     edx, edx
0x180013ed2  test    r8, r8
0x180013ed5  jz      short loc_180013EEE
0x180013ed7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013edb  inc     rax
0x180013ede  cmp     [r8+rax*2], dx
0x180013ee3  jnz     short loc_180013EDB
0x180013ee5  lea     ecx, ds:2[rax*2]
0x180013eec  jmp     short loc_180013EF3
0x180013eee  mov     ecx, 0Ah
0x180013ef3  test    r8, r8
0x180013ef6  mov     [rsp+58h+UserData.Size], ecx
0x180013efa  mov     dword ptr [rsp+58h+UserData.0Ch], edx
0x180013efe  lea     rax, aNull; "NULL"
0x180013f05  cmovnz  rax, r8
0x180013f09  mov     [rsp+58h+var_20], 4
0x180013f12  mov     [rsp+58h+UserData.Ptr], rax
0x180013f17  lea     r9, [rsp+58h+UserData]; UserData
0x180013f1c  lea     rax, [rsp+58h+arg_18]
0x180013f21  mov     r8d, 2; UserDataCount
0x180013f27  lea     rdx, TraceMerge_NGEN_BinaryNotFound; EventDescriptor
0x180013f2e  mov     [rsp+58h+var_28], rax
0x180013f33  xor     ecx, ecx; RegHandle
0x180013f35  call    cs:__imp_EventWrite
0x180013f3b  mov     rcx, [rsp+58h+var_10]
0x180013f40  xor     rcx, rsp; StackCookie
0x180013f43  call    __security_check_cookie
0x180013f48  add     rsp, 58h
0x180013f4c  retn
```

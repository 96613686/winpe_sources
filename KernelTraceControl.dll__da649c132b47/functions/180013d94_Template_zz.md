# Template_zz

- ea: `0x180013d94`
- end: `0x180013e4c`
- name: `Template_zz`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800153f0`

## callees

- `0x180013d94`
- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013e33`
- `ADVAPI32!EventWrite` at `0x180013e33`

## pseudocode

```c
ULONG __fastcall Template_zz(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rcx
  int v6; // edx
  __int64 v7; // rax
  ULONG v8; // r9d
  const wchar_t *v9; // r11
  const wchar_t *v10; // rax
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v14; // [rsp+30h] [rbp-28h]
  int v15; // [rsp+38h] [rbp-20h]
  int v16; // [rsp+3Ch] [rbp-1Ch]

  v4 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  UserData.Size = v8;
  v9 = L"NULL";
  UserData.Reserved = 0;
  v10 = L"NULL";
  if ( a3 )
    v10 = a3;
  UserData.Ptr = (ULONGLONG)v10;
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v6 = 2 * v4 + 2;
    v11 = a4 == 0;
  }
  if ( !v11 )
    v9 = a4;
  v15 = v6;
  v14 = v9;
  v16 = 0;
  return EventWrite(0, &TraceMerge_NGEN_CopyingPDB_Start, 2u, &UserData);
}

```

## disassembly

```asm
0x180013d94  push    rbx
0x180013d96  sub     rsp, 50h
0x180013d9a  mov     rax, cs:__security_cookie
0x180013da1  xor     rax, rsp
0x180013da4  mov     [rsp+58h+var_10], rax
0x180013da9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013dad  xor     ebx, ebx
0x180013daf  mov     r10, r9
0x180013db2  mov     edx, 0Ah
0x180013db7  test    r8, r8
0x180013dba  jz      short loc_180013DD3
0x180013dbc  mov     rax, rcx
0x180013dbf  inc     rax
0x180013dc2  cmp     [r8+rax*2], bx
0x180013dc7  jnz     short loc_180013DBF
0x180013dc9  lea     r9d, ds:2[rax*2]
0x180013dd1  jmp     short loc_180013DD6
0x180013dd3  mov     r9d, edx
0x180013dd6  test    r8, r8
0x180013dd9  mov     [rsp+58h+UserData.Size], r9d
0x180013dde  lea     r11, aNull; "NULL"
0x180013de5  mov     dword ptr [rsp+58h+UserData.0Ch], ebx
0x180013de9  mov     rax, r11
0x180013dec  cmovnz  rax, r8
0x180013df0  mov     [rsp+58h+UserData.Ptr], rax
0x180013df5  test    r10, r10
0x180013df8  jz      short loc_180013E0E
0x180013dfa  inc     rcx
0x180013dfd  cmp     [r10+rcx*2], bx
0x180013e02  jnz     short loc_180013DFA
0x180013e04  lea     edx, ds:2[rcx*2]
0x180013e0b  test    r10, r10
0x180013e0e  cmovnz  r11, r10
0x180013e12  mov     [rsp+58h+var_20], edx
0x180013e16  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start; EventDescriptor
0x180013e1d  mov     [rsp+58h+var_28], r11
0x180013e22  xor     ecx, ecx; RegHandle
0x180013e24  mov     [rsp+58h+var_1C], ebx
0x180013e28  lea     r9, [rsp+58h+UserData]; UserData
0x180013e2d  mov     r8d, 2; UserDataCount
0x180013e33  call    cs:__imp_EventWrite
0x180013e39  mov     rcx, [rsp+58h+var_10]
0x180013e3e  xor     rcx, rsp; StackCookie
0x180013e41  call    __security_check_cookie
0x180013e46  add     rsp, 50h
0x180013e4a  pop     rbx
0x180013e4b  retn
```

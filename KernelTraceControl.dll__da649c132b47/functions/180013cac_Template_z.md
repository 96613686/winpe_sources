# Template_z

- ea: `0x180013cac`
- end: `0x180013d22`
- name: `Template_z`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800149c4`
- `0x1800150e8`

## callees

- `0x180013cac`
- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013d0a`
- `ADVAPI32!EventWrite` at `0x180013d0a`

## pseudocode

```c
ULONG __fastcall Template_z(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  ULONG v4; // ecx
  const wchar_t *v5; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

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
  UserData.Size = v4;
  UserData.Reserved = 0;
  v5 = L"NULL";
  if ( a3 )
    v5 = a3;
  UserData.Ptr = (ULONGLONG)v5;
  return EventWrite(0, a2, 1u, &UserData);
}

```

## disassembly

```asm
0x180013cac  sub     rsp, 48h
0x180013cb0  mov     rax, cs:__security_cookie
0x180013cb7  xor     rax, rsp
0x180013cba  mov     [rsp+48h+var_10], rax
0x180013cbf  xor     r9d, r9d
0x180013cc2  test    r8, r8
0x180013cc5  jz      short loc_180013CDE
0x180013cc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013ccb  inc     rax
0x180013cce  cmp     [r8+rax*2], r9w
0x180013cd3  jnz     short loc_180013CCB
0x180013cd5  lea     ecx, ds:2[rax*2]
0x180013cdc  jmp     short loc_180013CE3
0x180013cde  mov     ecx, 0Ah
0x180013ce3  test    r8, r8
0x180013ce6  mov     [rsp+48h+UserData.Size], ecx
0x180013cea  mov     dword ptr [rsp+48h+UserData.0Ch], r9d
0x180013cef  lea     rax, aNull; "NULL"
0x180013cf6  cmovnz  rax, r8
0x180013cfa  lea     r9, [rsp+48h+UserData]; UserData
0x180013cff  xor     ecx, ecx; RegHandle
0x180013d01  mov     [rsp+48h+UserData.Ptr], rax
0x180013d06  lea     r8d, [rcx+1]; UserDataCount
0x180013d0a  call    cs:__imp_EventWrite
0x180013d10  mov     rcx, [rsp+48h+var_10]
0x180013d15  xor     rcx, rsp; StackCookie
0x180013d18  call    __security_check_cookie
0x180013d1d  add     rsp, 48h
0x180013d21  retn
```

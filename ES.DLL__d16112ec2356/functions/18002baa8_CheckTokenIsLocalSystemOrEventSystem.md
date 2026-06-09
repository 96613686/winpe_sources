# CheckTokenIsLocalSystemOrEventSystem

- ea: `0x18002baa8`
- end: `0x18002bb3d`
- name: `CheckTokenIsLocalSystemOrEventSystem`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800146c0`

## callees

- `0x18002baa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb12`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002bac7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002bb08`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002bac7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002bb08`

## pseudocode

```c
signed int __fastcall CheckTokenIsLocalSystemOrEventSystem(__int64 a1)
{
  signed int result; // eax
  bool v2; // sf
  bool v3; // sf
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]
  WINBOOL v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = HIDWORD(a1);
  IsMember = 0;
  if ( CheckTokenMembership(0, pSid, &IsMember) )
  {
    result = 0;
    goto LABEL_7;
  }
  result = GetLastError();
  v2 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v2 = result < 0;
  }
  if ( !v2 )
  {
LABEL_7:
    if ( IsMember )
      return result;
    v6 = 0;
    if ( CheckTokenMembership(0, hMem, &v6) )
    {
      result = 0;
    }
    else
    {
      result = GetLastError();
      v3 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v3 = result < 0;
      }
      if ( v3 )
        return result;
    }
    if ( !v6 )
      return -2147024891;
  }
  return result;
}

```

## disassembly

```asm
0x18002baa8  mov     qword ptr [rsp+IsMember], rcx
0x18002baad  sub     rsp, 28h
0x18002bab1  mov     rdx, cs:pSid; SidToCheck
0x18002bab8  lea     r8, [rsp+28h+IsMember]; IsMember
0x18002babd  xor     ecx, ecx; TokenHandle
0x18002babf  mov     [rsp+28h+IsMember], 0
0x18002bac7  call    cs:__imp_CheckTokenMembership
0x18002bacd  test    eax, eax
0x18002bacf  jnz     short loc_18002BAE9
0x18002bad1  call    cs:__imp_GetLastError
0x18002bad7  test    eax, eax
0x18002bad9  jle     short loc_18002BAE5
0x18002badb  movzx   eax, ax
0x18002bade  or      eax, 80070000h
0x18002bae3  test    eax, eax
0x18002bae5  jns     short loc_18002BAEB
0x18002bae7  jmp     short loc_18002BB38
0x18002bae9  xor     eax, eax
0x18002baeb  cmp     [rsp+28h+IsMember], 0
0x18002baf0  jnz     short loc_18002BB38
0x18002baf2  mov     rdx, cs:hMem; SidToCheck
0x18002baf9  lea     r8, [rsp+28h+arg_8]; IsMember
0x18002bafe  xor     ecx, ecx; TokenHandle
0x18002bb00  mov     [rsp+28h+arg_8], 0
0x18002bb08  call    cs:__imp_CheckTokenMembership
0x18002bb0e  test    eax, eax
0x18002bb10  jnz     short loc_18002BB2A
0x18002bb12  call    cs:__imp_GetLastError
0x18002bb18  test    eax, eax
0x18002bb1a  jle     short loc_18002BB26
0x18002bb1c  movzx   eax, ax
0x18002bb1f  or      eax, 80070000h
0x18002bb24  test    eax, eax
0x18002bb26  js      short loc_18002BB38
0x18002bb28  jmp     short loc_18002BB2C
0x18002bb2a  xor     eax, eax
0x18002bb2c  cmp     [rsp+28h+arg_8], 0
0x18002bb31  jnz     short loc_18002BB38
0x18002bb33  mov     eax, 80070005h
0x18002bb38  add     rsp, 28h
0x18002bb3c  retn
```

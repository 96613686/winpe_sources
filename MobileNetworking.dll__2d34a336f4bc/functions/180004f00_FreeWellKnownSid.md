# FreeWellKnownSid

- ea: `0x180004f00`
- end: `0x180004f98`
- name: `FreeWellKnownSid`
- size: `152`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180004db0`
- `0x180004fa0`

## callees

- `0x180004b80`
- `0x180004f00`
- `0x180008ff0`
- `0x180009130`

## string_xrefs

- `0x180004f52`: `FreeWellKnownSid`

## pseudocode

```c
__int64 __fastcall FreeWellKnownSid(void *a1)
{
  PVOID *v2; // rcx
  __int64 result; // rax
  LPVOID v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    result = FreeMemory(&v4, (int)"FreeWellKnownSid", 119);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    return WPP_SF_L(v2[2], 67, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180004f00  mov     [rsp+arg_8], rbx
0x180004f05  mov     [rsp+arg_0], rcx
0x180004f0a  push    rdi
0x180004f0b  sub     rsp, 20h
0x180004f0f  mov     rbx, rcx
0x180004f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f19  lea     rdi, WPP_GLOBAL_Control
0x180004f20  cmp     rcx, rdi
0x180004f23  jz      short loc_180004F47
0x180004f25  test    byte ptr [rcx+1Ch], 8
0x180004f29  jz      short loc_180004F47
0x180004f2b  mov     rcx, [rcx+10h]
0x180004f2f  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004f36  mov     edx, 42h ; 'B'
0x180004f3b  call    WPP_SF_
0x180004f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f47  test    rbx, rbx
0x180004f4a  jz      short loc_180004F6A
0x180004f4c  mov     r8d, 277h
0x180004f52  lea     rdx, aFreewellknowns; "FreeWellKnownSid"
0x180004f59  lea     rcx, [rsp+28h+arg_0]
0x180004f5e  call    FreeMemory
0x180004f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f6a  cmp     rcx, rdi
0x180004f6d  jz      short loc_180004F8D
0x180004f6f  test    byte ptr [rcx+1Ch], 8
0x180004f73  jz      short loc_180004F8D
0x180004f75  mov     rcx, [rcx+10h]
0x180004f79  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004f80  mov     edx, 43h ; 'C'
0x180004f85  xor     r9d, r9d
0x180004f88  call    WPP_SF_L
0x180004f8d  mov     rbx, [rsp+28h+arg_8]
0x180004f92  add     rsp, 20h
0x180004f96  pop     rdi
0x180004f97  retn
```

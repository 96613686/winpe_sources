# SdbpGetExeEntryFlags

- ea: `0x140040c08`
- end: `0x140040d55`
- name: `SdbpGetExeEntryFlags`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003bea8`

## callees

- `0x1400079f0`
- `0x14003d820`
- `0x14003e364`
- `0x14003f570`
- `0x140040820`
- `0x140040c08`
- `0x140046274`

## string_xrefs

- `0x140040cb1`: `Failed to read the GUID for tiExe 0x%x`
- `0x140040cf4`: `Failed to read TAG_EXE_ID for tiExe 0x%x`

## pseudocode

```c
__int64 __fastcall SdbpGetExeEntryFlags(__int64 a1, __int64 a2, int *a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // esi
  unsigned int FirstTag; // eax
  int EntryFlags; // eax
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  unsigned int v15; // eax
  int v16; // [rsp+30h] [rbp-38h] BYREF
  __int128 v17; // [rsp+38h] [rbp-30h] BYREF

  v4 = 0;
  v17 = 0;
  v16 = 0;
  v5 = a2;
  FirstTag = SdbFindFirstTag(a1, a2, 36868);
  if ( !FirstTag )
  {
    v12 = "Failed to read TAG_EXE_ID for tiExe 0x%x";
    v13 = 718;
    goto LABEL_8;
  }
  if ( !(unsigned int)SdbReadBinaryTag(a1, FirstTag, (__int64)&v17, 0x10u) )
  {
    v12 = "Failed to read the GUID for tiExe 0x%x";
    v13 = 723;
LABEL_8:
    AslLogCallPrintf(1, "SdbpGetExeEntryFlags", v13, v12, v5);
    return v4;
  }
  EntryFlags = SdbGetEntryFlags(&v17, &v16);
  v9 = EntryFlags != 0 ? v16 : 0;
  v10 = SdbFindFirstTag(a1, v5, 28685);
  if ( v10 )
  {
    v9 |= 0x1000u;
    v15 = SdbFindFirstTag(a1, v10, 16400);
    if ( v15 )
    {
      if ( (unsigned int)SdbReadDWORDTag(a1, v15, 0) == 2 )
        v9 |= 0x2000u;
    }
  }
  v11 = SdbFindFirstTag(a1, v5, 16434);
  if ( v11 )
    v9 |= (unsigned int)SdbReadDWORDTag(a1, v11, 0) << 16;
  *a3 = v9;
  return 1;
}

```

## disassembly

```asm
0x140040c08  mov     [rsp+arg_18], rbx
0x140040c0d  push    rsi
0x140040c0e  push    rdi
0x140040c0f  push    r14
0x140040c11  sub     rsp, 50h
0x140040c15  mov     rax, cs:__security_cookie
0x140040c1c  xor     rax, rsp
0x140040c1f  mov     [rsp+68h+var_20], rax
0x140040c24  mov     r14, r8
0x140040c27  xorps   xmm0, xmm0
0x140040c2a  xor     ebx, ebx
0x140040c2c  mov     r8d, 9004h
0x140040c32  movups  [rsp+68h+var_30], xmm0
0x140040c37  mov     [rsp+68h+var_38], ebx
0x140040c3b  mov     esi, edx
0x140040c3d  mov     rdi, rcx
0x140040c40  call    SdbFindFirstTag
0x140040c45  test    eax, eax
0x140040c47  jz      loc_140040CF4
0x140040c4d  lea     r9d, [rbx+10h]
0x140040c51  mov     edx, eax
0x140040c53  lea     r8, [rsp+68h+var_30]
0x140040c58  mov     rcx, rdi
0x140040c5b  call    SdbReadBinaryTag
0x140040c60  test    eax, eax
0x140040c62  jz      short loc_140040CB1
0x140040c64  lea     rdx, [rsp+68h+var_38]
0x140040c69  lea     rcx, [rsp+68h+var_30]
0x140040c6e  call    SdbGetEntryFlags
0x140040c73  neg     eax
0x140040c75  mov     r8d, 700Dh
0x140040c7b  mov     edx, esi
0x140040c7d  mov     rcx, rdi
0x140040c80  sbb     ebx, ebx
0x140040c82  and     ebx, [rsp+68h+var_38]
0x140040c86  call    SdbFindFirstTag
0x140040c8b  test    eax, eax
0x140040c8d  jnz     short loc_140040D03
0x140040c8f  mov     r8d, 4032h
0x140040c95  mov     edx, esi
0x140040c97  mov     rcx, rdi
0x140040c9a  call    SdbFindFirstTag
0x140040c9f  test    eax, eax
0x140040ca1  jnz     loc_140040D3E
0x140040ca7  mov     [r14], ebx
0x140040caa  mov     ebx, 1
0x140040caf  jmp     short loc_140040CD3
0x140040cb1  lea     r9, aFailedToReadTh; "Failed to read the GUID for tiExe 0x%x"
0x140040cb8  mov     r8d, 2D3h
0x140040cbe  lea     rdx, aSdbpgetexeentr; "SdbpGetExeEntryFlags"
0x140040cc5  mov     [rsp+68h+var_48], esi
0x140040cc9  mov     ecx, 1
0x140040cce  call    AslLogCallPrintf
0x140040cd3  mov     eax, ebx
0x140040cd5  mov     rcx, [rsp+68h+var_20]
0x140040cda  xor     rcx, rsp; StackCookie
0x140040cdd  call    __security_check_cookie
0x140040ce2  mov     rbx, [rsp+68h+arg_18]
0x140040cea  add     rsp, 50h
0x140040cee  pop     r14
0x140040cf0  pop     rdi
0x140040cf1  pop     rsi
0x140040cf2  retn
0x140040cf4  lea     r9, aFailedToReadTa; "Failed to read TAG_EXE_ID for tiExe 0x%"...
0x140040cfb  mov     r8d, 2CEh
0x140040d01  jmp     short loc_140040CBE
0x140040d03  mov     r8d, 4010h
0x140040d09  mov     edx, eax
0x140040d0b  mov     rcx, rdi
0x140040d0e  bts     ebx, 0Ch
0x140040d12  call    SdbFindFirstTag
0x140040d17  test    eax, eax
0x140040d19  jz      loc_140040C8F
0x140040d1f  xor     r8d, r8d
0x140040d22  mov     edx, eax
0x140040d24  mov     rcx, rdi
0x140040d27  call    SdbReadDWORDTag
0x140040d2c  cmp     eax, 2
0x140040d2f  jnz     loc_140040C8F
0x140040d35  bts     ebx, 0Dh
0x140040d39  jmp     loc_140040C8F
0x140040d3e  xor     r8d, r8d
0x140040d41  mov     edx, eax
0x140040d43  mov     rcx, rdi
0x140040d46  call    SdbReadDWORDTag
0x140040d4b  shl     eax, 10h
0x140040d4e  or      ebx, eax
0x140040d50  jmp     loc_140040CA7
```

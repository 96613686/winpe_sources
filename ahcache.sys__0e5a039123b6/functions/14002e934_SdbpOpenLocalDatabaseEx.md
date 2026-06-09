# SdbpOpenLocalDatabaseEx

- ea: `0x14002e934`
- end: `0x14002eb81`
- name: `SdbpOpenLocalDatabaseEx`
- size: `589`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14003a364`
- `0x1400520dc`

## callees

- `0x1400079f0`
- `0x14002d038`
- `0x14002e934`
- `0x14003e364`
- `0x140041f78`
- `0x1400426ec`
- `0x140042ad4`
- `0x1400543f4`

## string_xrefs

- `0x14002ea36`: `SdbpOpenLocalDatabaseEx`
- `0x14002eb47`: `SdbpOpenLocalDatabaseEx`
- `0x14002eb37`: `Cannot resolve database, the path length is 0x%lx`
- `0x14002ea9b`: `Custom database has invalid path %S`
- `0x14002eabf`: `Failed to open database`

## pseudocode

```c
__int64 __fastcall SdbpOpenLocalDatabaseEx(__int64 a1, __int128 *a2, __int64 a3, _QWORD *a4, unsigned int *a5)
{
  unsigned int v8; // ecx
  unsigned int v9; // r14d
  unsigned int v10; // edi
  __int64 v11; // rdi
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // ecx
  const char *v15; // r9
  __int64 v16; // r8
  int FileTimestamp; // eax
  __int64 v18; // rdx
  _QWORD *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int128 v22; // xmm0
  __int64 v24; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h]
  wchar_t v29[264]; // [rsp+50h] [rbp-B0h] BYREF

  v28 = 0;
  v8 = *a5;
  v9 = 0;
  v10 = *a5;
  LODWORD(v27) = 0;
  v11 = v10 >> 28;
  v25 = 0;
  v26 = 0;
  if ( (v8 & 0xF0000000) == 0 )
    v11 = v8;
  if ( (_DWORD)v11 != 1 && (unsigned int)(v11 - 3) > 0xC )
  {
    LODWORD(v24) = v11;
    v12 = "Bad index 0x%lx";
    v13 = 1123;
LABEL_28:
    AslLogCallPrintf(1, "SdbpOpenLocalDatabaseEx", v13, v12, v24);
    return v9;
  }
  SdbpCloseLocalDatabaseEx(a1, 0, (unsigned int)v11);
  v14 = SdbResolveDatabaseEx(a1, (_DWORD)a2, (unsigned int)&v27, (unsigned int)&v25, (__int64)v29);
  if ( (unsigned int)(v14 - 1) > 0x102 )
  {
    LODWORD(v24) = v14;
    v12 = "Cannot resolve database, the path length is 0x%lx";
    v13 = 1157;
    goto LABEL_28;
  }
  if ( *(_WORD *)(a1 + 584) != 0x7FFF )
  {
    if ( !(unsigned int)SdbpCheckRuntimePlatformImpl(&v26, 0, *(unsigned int *)(a1 + 552), v25) )
    {
      AslLogCallPrintf(
        1,
        "SdbpOpenLocalDatabaseEx",
        1174,
        "Cannot check database runtime platform against current process");
      return v9;
    }
    if ( !v26 )
    {
      v15 = "Database \"%ws\" is not of the same type as the main EXE";
      v16 = 1178;
LABEL_13:
      AslLogCallPrintf(3, "SdbpOpenLocalDatabaseEx", v16, v15, v29);
      return v9;
    }
  }
  v27 = 0;
  FileTimestamp = SdbpGetFileTimestamp(&v27, v29, 0);
  if ( FileTimestamp < 0 && FileTimestamp != -1073741790 && FileTimestamp != -1073741757 )
  {
    v15 = "Custom database has invalid path %S";
    v16 = 1196;
    goto LABEL_13;
  }
  v19 = SdbOpenDatabaseEx(v29, v18, 0);
  if ( v19 )
  {
    v20 = 32LL * (unsigned int)v11;
    v21 = 32 * (v11 + 2);
    *(_QWORD *)(v20 + a1 + 56) = v19;
    *(_DWORD *)(v21 + a1) = 2;
    *(_DWORD *)(a1 + 36) |= 1 << v11;
    if ( a2 )
    {
      v22 = *a2;
      *(_DWORD *)(v21 + a1) |= 1u;
      *(_OWORD *)(v20 + a1 + 40) = v22;
    }
    else
    {
      *(_OWORD *)(v20 + a1 + 40) = 0;
    }
    v9 = 1;
    if ( (_DWORD)v11 == 1 )
      *(_QWORD *)(a1 + 24) = v19;
    *a5 = (_DWORD)v11 << 28;
    if ( a4 )
      *a4 = v19;
  }
  else
  {
    AslLogCallPrintf(1, "SdbpOpenLocalDatabaseEx", 1202, "Failed to open database");
  }
  return v9;
}

```

## disassembly

```asm
0x14002e934  mov     [rsp-8+arg_10], rbx
0x14002e939  push    rbp
0x14002e93a  push    rsi
0x14002e93b  push    rdi
0x14002e93c  push    r12
0x14002e93e  push    r13
0x14002e940  push    r14
0x14002e942  push    r15
0x14002e944  lea     rbp, [rsp-170h]
0x14002e94c  sub     rsp, 270h
0x14002e953  mov     rax, cs:__security_cookie
0x14002e95a  xor     rax, rsp
0x14002e95d  mov     [rbp+1A0h+var_40], rax
0x14002e964  mov     r12, [rbp+1A0h+arg_20]
0x14002e96b  mov     rbx, rcx
0x14002e96e  mov     r15, rdx
0x14002e971  xorps   xmm0, xmm0
0x14002e974  xor     edx, edx
0x14002e976  mov     rsi, r9
0x14002e979  movups  [rsp+2A0h+var_260], xmm0
0x14002e97e  mov     ecx, [r12]
0x14002e982  mov     r14d, edx
0x14002e985  mov     edi, ecx
0x14002e987  mov     dword ptr [rsp+2A0h+var_268], edx
0x14002e98b  shr     edi, 1Ch
0x14002e98e  lea     r13d, [rdx+1]
0x14002e992  test    ecx, 0F0000000h
0x14002e998  mov     [rsp+2A0h+var_270], edx
0x14002e99c  mov     [rsp+2A0h+var_26C], edx
0x14002e9a0  cmovz   edi, ecx
0x14002e9a3  cmp     edi, r13d
0x14002e9a6  jz      short loc_14002E9C6
0x14002e9a8  lea     eax, [rdi-3]
0x14002e9ab  cmp     eax, 0Ch
0x14002e9ae  jbe     short loc_14002E9C6
0x14002e9b0  mov     dword ptr [rsp+2A0h+var_280], edi
0x14002e9b4  lea     r9, aBadIndex0xLx; "Bad index 0x%lx"
0x14002e9bb  mov     r8d, 463h
0x14002e9c1  jmp     loc_14002EB44
0x14002e9c6  mov     r8d, edi
0x14002e9c9  mov     rcx, rbx
0x14002e9cc  call    SdbpCloseLocalDatabaseEx
0x14002e9d1  lea     rax, [rsp+2A0h+var_250]
0x14002e9d6  mov     rdx, r15
0x14002e9d9  lea     r9, [rsp+2A0h+var_270]
0x14002e9de  mov     [rsp+2A0h+var_280], rax
0x14002e9e3  lea     r8, [rsp+2A0h+var_268]
0x14002e9e8  mov     rcx, rbx
0x14002e9eb  call    SdbResolveDatabaseEx
0x14002e9f0  mov     ecx, eax
0x14002e9f2  dec     eax
0x14002e9f4  cmp     eax, 102h
0x14002e9f9  ja      loc_14002EB33
0x14002e9ff  mov     eax, 7FFFh
0x14002ea04  cmp     [rbx+248h], ax
0x14002ea0b  jz      short loc_14002EA72
0x14002ea0d  mov     r9d, [rsp+2A0h+var_270]
0x14002ea12  lea     rcx, [rsp+2A0h+var_26C]
0x14002ea17  mov     r8d, [rbx+228h]
0x14002ea1e  xor     edx, edx
0x14002ea20  call    SdbpCheckRuntimePlatformImpl
0x14002ea25  test    eax, eax
0x14002ea27  jnz     short loc_14002EA4A
0x14002ea29  lea     r9, aCannotCheckDat; "Cannot check database runtime platform "...
0x14002ea30  mov     r8d, 496h
0x14002ea36  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x14002ea3d  mov     ecx, r13d
0x14002ea40  call    AslLogCallPrintf
0x14002ea45  jmp     loc_14002EB53
0x14002ea4a  cmp     [rsp+2A0h+var_26C], r14d
0x14002ea4f  jnz     short loc_14002EA72
0x14002ea51  lea     r9, aDatabaseWsIsNo; "Database \"%ws\" is not of the same typ"...
0x14002ea58  mov     r8d, 49Ah
0x14002ea5e  lea     rax, [rsp+2A0h+var_250]
0x14002ea63  mov     ecx, 3
0x14002ea68  mov     [rsp+2A0h+var_280], rax
0x14002ea6d  jmp     loc_14002EB47
0x14002ea72  xor     r8d, r8d
0x14002ea75  mov     [rsp+2A0h+var_268], r14
0x14002ea7a  lea     rdx, [rsp+2A0h+var_250]
0x14002ea7f  lea     rcx, [rsp+2A0h+var_268]
0x14002ea84  call    SdbpGetFileTimestamp
0x14002ea89  test    eax, eax
0x14002ea8b  jns     short loc_14002EAAA
0x14002ea8d  cmp     eax, 0C0000022h
0x14002ea92  jz      short loc_14002EAAA
0x14002ea94  cmp     eax, 0C0000043h
0x14002ea99  jz      short loc_14002EAAA
0x14002ea9b  lea     r9, aCustomDatabase; "Custom database has invalid path %S"
0x14002eaa2  mov     r8d, 4ACh
0x14002eaa8  jmp     short loc_14002EA5E
0x14002eaaa  xor     r8d, r8d
0x14002eaad  lea     rcx, [rsp+2A0h+var_250]
0x14002eab2  call    SdbOpenDatabaseEx
0x14002eab7  mov     rdx, rax
0x14002eaba  test    rax, rax
0x14002eabd  jnz     short loc_14002EAD1
0x14002eabf  lea     r9, aFailedToOpenDa; "Failed to open database"
0x14002eac6  mov     r8d, 4B2h
0x14002eacc  jmp     loc_14002EA36
0x14002ead1  mov     r8d, edi
0x14002ead4  lea     r9, [rdi+2]
0x14002ead8  shl     r8, 5
0x14002eadc  mov     ecx, edi
0x14002eade  shl     r9, 5
0x14002eae2  mov     eax, r13d
0x14002eae5  shl     eax, cl
0x14002eae7  mov     [r8+rbx+38h], rdx
0x14002eaec  mov     dword ptr [r9+rbx], 2
0x14002eaf4  or      [rbx+24h], eax
0x14002eaf7  test    r15, r15
0x14002eafa  jz      short loc_14002EB0D
0x14002eafc  movups  xmm0, xmmword ptr [r15]
0x14002eb00  or      [r9+rbx], r13d
0x14002eb04  movdqu  xmmword ptr [r8+rbx+28h], xmm0
0x14002eb0b  jmp     short loc_14002EB16
0x14002eb0d  xorps   xmm0, xmm0
0x14002eb10  movups  xmmword ptr [r8+rbx+28h], xmm0
0x14002eb16  mov     r14d, r13d
0x14002eb19  cmp     edi, r13d
0x14002eb1c  jnz     short loc_14002EB22
0x14002eb1e  mov     [rbx+18h], rdx
0x14002eb22  shl     edi, 1Ch
0x14002eb25  mov     [r12], edi
0x14002eb29  test    rsi, rsi
0x14002eb2c  jz      short loc_14002EB53
0x14002eb2e  mov     [rsi], rdx
0x14002eb31  jmp     short loc_14002EB53
0x14002eb33  mov     dword ptr [rsp+2A0h+var_280], ecx
0x14002eb37  lea     r9, aCannotResolveD; "Cannot resolve database, the path lengt"...
0x14002eb3e  mov     r8d, 485h
0x14002eb44  mov     ecx, r13d
0x14002eb47  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x14002eb4e  call    AslLogCallPrintf
0x14002eb53  mov     eax, r14d
0x14002eb56  mov     rcx, [rbp+1A0h+var_40]
0x14002eb5d  xor     rcx, rsp; StackCookie
0x14002eb60  call    __security_check_cookie
0x14002eb65  mov     rbx, [rsp+2A0h+arg_10]
0x14002eb6d  add     rsp, 270h
0x14002eb74  pop     r15
0x14002eb76  pop     r14
0x14002eb78  pop     r13
0x14002eb7a  pop     r12
0x14002eb7c  pop     rdi
0x14002eb7d  pop     rsi
0x14002eb7e  pop     rbp
0x14002eb7f  retn
```

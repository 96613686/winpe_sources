# BcdOpenObject

- ea: `0x140013ee8`
- end: `0x1400140bc`
- name: `BcdOpenObject`
- size: `468`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `35`
- callee_count: `9`
- tags: ``

## callers

- `0x140003d30`
- `0x140004828`
- `0x140004a60`
- `0x140004e20`
- `0x140004e98`
- `0x1400052bc`
- `0x1400058e4`
- `0x140005b98`
- `0x140005fc4`
- `0x140006b08`
- `0x1400078f4`
- `0x140007e20`
- `0x140008104`
- `0x140008400`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x140008e68`
- `0x140009094`
- `0x140009170`
- `0x140009528`
- `0x140009658`
- `0x14000efc8`
- `0x140014448`
- `0x14001474c`
- `0x140014ec8`
- `0x14001a264`
- `0x140021990`
- `0x140021c10`
- `0x140021f58`
- `0x140022258`
- `0x140022cb8`
- `0x140023824`
- `0x140024cf0`
- `0x14002515c`

## callees

- `0x1400133e4`
- `0x140013ee8`
- `0x140014448`
- `0x14001ae94`
- `0x14001c014`
- `0x14001e5e4`
- `0x14001f980`
- `0x140020720`
- `0x140026650`

## string_xrefs

- `0x140013fbf`: `Failed to open key for all objects. Status: %x`
- `0x140014065`: `Failed to open object's key. Status: %x`
- `0x140013f46`: `Opening object %s`
- `0x140013f79`: `BcdOpenObject: Failed to acquire BCD sync mutant. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdOpenObject(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  char *v6; // r15
  unsigned int v7; // edi
  unsigned int v8; // r12d
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  int AliasedIdentifier; // eax
  HANDLE v13; // r14
  const wchar_t *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // [rsp+28h] [rbp-71h] BYREF
  char *v19; // [rsp+30h] [rbp-69h]
  HANDLE Handle; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-59h]
  __int128 v22; // [rsp+48h] [rbp-51h] BYREF
  char v23; // [rsp+60h] [rbp-39h] BYREF

  v21 = a3;
  v18 = 5111808;
  v19 = &v23;
  v22 = 0;
  BiStringFromGUID(a2, &v18);
  v6 = v19;
  v7 = 2;
  BiLogMessage(2, L"Opening object %s", v19);
  v8 = 1;
  LOBYTE(v9) = a1 & 1;
  v10 = BiAcquireBcdSyncMutant(v9);
  v11 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(4, L"BcdOpenObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v10);
    return v11;
  }
  *a3 = 0;
  Handle = 0;
  AliasedIdentifier = BiOpenKey(a1, L"Objects", 131097, &Handle);
  v13 = Handle;
  v11 = AliasedIdentifier;
  if ( AliasedIdentifier < 0 )
  {
    v14 = L"Failed to open key for all objects. Status: %x";
LABEL_5:
    v15 = 4;
LABEL_18:
    BiLogMessage(v15, v14, (unsigned int)AliasedIdentifier);
    goto LABEL_19;
  }
  if ( *a2 != *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 || a2[1] != *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4 )
  {
    if ( *a2 != *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1 || a2[1] != *(_QWORD *)GUID_DEFAULT_BOOT_ENTRY.Data4 )
      goto LABEL_14;
    v8 = 2;
  }
  AliasedIdentifier = BiGetAliasedIdentifier(a1, v8, &v22);
  v11 = AliasedIdentifier;
  if ( AliasedIdentifier < 0 )
  {
    v14 = L"Failed to get aliased identifier. Status: %x";
    goto LABEL_5;
  }
  BiStringFromGUID(&v22, &v18);
  v6 = v19;
  BiLogMessage(2, L"Object alias resolves to %s", v19);
LABEL_14:
  AliasedIdentifier = BiOpenKey(v13, v6, 983103, v21);
  v11 = AliasedIdentifier;
  if ( AliasedIdentifier < 0 )
  {
    v14 = L"Failed to open object's key. Status: %x";
    if ( AliasedIdentifier != -1073741772 )
      v7 = 4;
    v15 = v7;
    goto LABEL_18;
  }
LABEL_19:
  if ( v13 )
    BiCloseKey(v13);
  LOBYTE(v16) = a1 & 1;
  BiReleaseBcdSyncMutant(v16);
  return v11;
}

```

## disassembly

```asm
0x140013ee8  mov     [rsp-8+arg_18], rbx
0x140013eed  push    rbp
0x140013eee  push    rsi
0x140013eef  push    rdi
0x140013ef0  push    r12
0x140013ef2  push    r13
0x140013ef4  push    r14
0x140013ef6  push    r15
0x140013ef8  lea     rbp, [rsp-27h]
0x140013efd  sub     rsp, 0C0h
0x140013f04  mov     rax, cs:__security_cookie
0x140013f0b  xor     rax, rsp
0x140013f0e  mov     [rbp+57h+var_40], rax
0x140013f12  mov     rsi, rdx
0x140013f15  mov     [rbp+57h+var_B0], r8
0x140013f19  mov     r13, rcx
0x140013f1c  mov     [rbp+57h+var_C8], 4E0000h
0x140013f24  lea     rax, [rbp+57h+var_90]
0x140013f28  xorps   xmm0, xmm0
0x140013f2b  mov     rcx, rsi
0x140013f2e  mov     [rbp+57h+var_C0], rax
0x140013f32  lea     rdx, [rbp+57h+var_C8]
0x140013f36  mov     r14, r8
0x140013f39  movups  [rbp+57h+var_A8], xmm0
0x140013f3d  call    BiStringFromGUID
0x140013f42  mov     r15, [rbp+57h+var_C0]
0x140013f46  lea     rdx, aOpeningObjectS; "Opening object %s"
0x140013f4d  mov     edi, 2
0x140013f52  mov     r8, r15
0x140013f55  mov     ecx, edi
0x140013f57  call    BiLogMessage
0x140013f5c  mov     al, r13b
0x140013f5f  lea     r12d, [rdi-1]
0x140013f63  and     al, r12b
0x140013f66  mov     cl, al
0x140013f68  mov     [rbp+57h+var_D0], al
0x140013f6b  call    BiAcquireBcdSyncMutant
0x140013f70  mov     ebx, eax
0x140013f72  test    eax, eax
0x140013f74  jns     short loc_140013F8D
0x140013f76  mov     r8d, eax
0x140013f79  lea     rdx, aBcdopenobjectF; "BcdOpenObject: Failed to acquire BCD sy"...
0x140013f80  lea     ecx, [rdi+2]
0x140013f83  call    BiLogMessage
0x140013f88  jmp     loc_140014093
0x140013f8d  lea     r9, [rbp+57h+Handle]
0x140013f91  mov     qword ptr [r14], 0
0x140013f98  mov     r8d, 20019h
0x140013f9e  mov     [rbp+57h+Handle], 0
0x140013fa6  lea     rdx, aObjects; "Objects"
0x140013fad  mov     rcx, r13
0x140013fb0  call    BiOpenKey
0x140013fb5  mov     r14, [rbp+57h+Handle]
0x140013fb9  mov     ebx, eax
0x140013fbb  test    eax, eax
0x140013fbd  jns     short loc_140013FD0
0x140013fbf  lea     rdx, aFailedToOpenKe_2; "Failed to open key for all objects. Sta"...
0x140013fc6  mov     ecx, 4
0x140013fcb  jmp     loc_140014076
0x140013fd0  mov     rax, [rsi]
0x140013fd3  cmp     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x140013fda  jnz     short loc_140013FE9
0x140013fdc  mov     rax, [rsi+8]
0x140013fe0  cmp     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x140013fe7  jz      short loc_140014005
0x140013fe9  mov     rax, [rsi]
0x140013fec  cmp     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data1
0x140013ff3  jnz     short loc_140014045
0x140013ff5  mov     rax, [rsi+8]
0x140013ff9  cmp     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data4
0x140014000  jnz     short loc_140014045
0x140014002  mov     r12d, edi
0x140014005  lea     r8, [rbp+57h+var_A8]
0x140014009  mov     edx, r12d
0x14001400c  mov     rcx, r13
0x14001400f  call    BiGetAliasedIdentifier
0x140014014  mov     ebx, eax
0x140014016  test    eax, eax
0x140014018  jns     short loc_140014023
0x14001401a  lea     rdx, aFailedToGetAli; "Failed to get aliased identifier. Statu"...
0x140014021  jmp     short loc_140013FC6
0x140014023  lea     rdx, [rbp+57h+var_C8]
0x140014027  lea     rcx, [rbp+57h+var_A8]
0x14001402b  call    BiStringFromGUID
0x140014030  mov     r15, [rbp+57h+var_C0]
0x140014034  lea     rdx, aObjectAliasRes; "Object alias resolves to %s"
0x14001403b  mov     r8, r15
0x14001403e  mov     ecx, edi
0x140014040  call    BiLogMessage
0x140014045  mov     r9, [rbp+57h+var_B0]
0x140014049  mov     r8d, 0F003Fh
0x14001404f  mov     rdx, r15
0x140014052  mov     rcx, r14
0x140014055  call    BiOpenKey
0x14001405a  mov     ebx, eax
0x14001405c  test    eax, eax
0x14001405e  jns     short loc_14001407E
0x140014060  mov     ecx, 4
0x140014065  lea     rdx, aFailedToOpenOb; "Failed to open object's key. Status: %x"
0x14001406c  cmp     eax, 0C0000034h
0x140014071  cmovnz  edi, ecx
0x140014074  mov     ecx, edi
0x140014076  mov     r8d, eax
0x140014079  call    BiLogMessage
0x14001407e  test    r14, r14
0x140014081  jz      short loc_14001408B
0x140014083  mov     rcx, r14; Handle
0x140014086  call    BiCloseKey
0x14001408b  mov     cl, [rbp+57h+var_D0]
0x14001408e  call    BiReleaseBcdSyncMutant
0x140014093  mov     eax, ebx
0x140014095  mov     rcx, [rbp+57h+var_40]
0x140014099  xor     rcx, rsp; StackCookie
0x14001409c  call    __security_check_cookie
0x1400140a1  mov     rbx, [rsp+0F0h+arg_18]
0x1400140a9  add     rsp, 0C0h
0x1400140b0  pop     r15
0x1400140b2  pop     r14
0x1400140b4  pop     r13
0x1400140b6  pop     r12
0x1400140b8  pop     rdi
0x1400140b9  pop     rsi
0x1400140ba  pop     rbp
0x1400140bb  retn
```

# SdbpOpenDatabaseInMemory

- ea: `0x14002e118`
- end: `0x14002e269`
- name: `SdbpOpenDatabaseInMemory`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140031938`

## callees

- `0x1400055d4`
- `0x1400079f0`
- `0x14002e118`
- `0x14002e3b8`
- `0x14002e4cc`
- `0x14003e248`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`

## string_xrefs

- `0x14002e1ae`: `Can't read database header`
- `0x14002e16b`: `SdbpOpenDatabaseInMemory`
- `0x14002e1bb`: `SdbpOpenDatabaseInMemory`
- `0x14002e214`: `SdbpOpenDatabaseInMemory`
- `0x14002e252`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
void *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  __int64 v6; // rax
  void *v7; // rbx
  __int64 v8; // rcx
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+38h] [rbp-40h]

  v13 = 0;
  v14 = 0;
  v6 = AslAlloc(a1, 2688, 1);
  v7 = (void *)v6;
  if ( !v6 )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2891, "Failed to allocate DB structure");
    return 0;
  }
  *(_DWORD *)(v6 + 24) |= 1u;
  *(_DWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 8) = a1;
  *(_DWORD *)(v6 + 20) = a2;
  *(_QWORD *)v6 = 0;
  if ( !(unsigned int)SdbpReadMappedData(v6, 0, &v13, 0xCu) )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2902, "Can't read database header");
LABEL_5:
    AslFree(v8, v7);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v10 = v14;
    if ( v14 != 1717724275 && (a3 & 2) == 0 )
    {
      v11 = "Magic does not match a valid value: [0x%lx]";
      v12 = 2908;
LABEL_11:
      AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", v12, v11, v10);
      goto LABEL_5;
    }
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v13, a3) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v10 = SdbpValidateRootTagSizes(v7);
    if ( v10 < 0 )
    {
      v11 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v12 = 2920;
      goto LABEL_11;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14002e118  push    rbx
0x14002e11a  push    rbp
0x14002e11b  push    rsi
0x14002e11c  push    rdi
0x14002e11d  push    r14
0x14002e11f  sub     rsp, 50h
0x14002e123  mov     rax, cs:__security_cookie
0x14002e12a  xor     rax, rsp
0x14002e12d  mov     [rsp+78h+var_38], rax
0x14002e132  xor     eax, eax
0x14002e134  mov     edi, r8d
0x14002e137  mov     esi, edx
0x14002e139  mov     [rsp+78h+var_48], rax
0x14002e13e  mov     edx, 0A80h
0x14002e143  mov     [rsp+78h+var_40], eax
0x14002e147  mov     rbp, rcx
0x14002e14a  lea     r14d, [rax+1]
0x14002e14e  mov     r8d, r14d
0x14002e151  call    AslAlloc
0x14002e156  mov     rbx, rax
0x14002e159  test    rax, rax
0x14002e15c  jnz     short loc_14002E17C
0x14002e15e  lea     r9, aFailedToAlloca_19; "Failed to allocate DB structure"
0x14002e165  mov     r8d, 0B4Bh
0x14002e16b  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14002e172  mov     ecx, r14d
0x14002e175  call    AslLogCallPrintf
0x14002e17a  jmp     short loc_14002E1D2
0x14002e17c  or      [rax+18h], r14d
0x14002e180  lea     r8, [rsp+78h+var_48]
0x14002e185  mov     r9d, 0Ch
0x14002e18b  mov     dword ptr [rax+10h], 0
0x14002e192  xor     edx, edx
0x14002e194  mov     [rax+8], rbp
0x14002e198  mov     rcx, rbx
0x14002e19b  mov     [rax+14h], esi
0x14002e19e  mov     qword ptr [rax], 0
0x14002e1a5  call    SdbpReadMappedData
0x14002e1aa  test    eax, eax
0x14002e1ac  jnz     short loc_14002E1ED
0x14002e1ae  lea     r9, aCanTReadDataba; "Can't read database header"
0x14002e1b5  mov     r8d, 0B56h
0x14002e1bb  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14002e1c2  mov     ecx, r14d
0x14002e1c5  call    AslLogCallPrintf
0x14002e1ca  mov     rdx, rbx
0x14002e1cd  call    AslFree
0x14002e1d2  xor     eax, eax
0x14002e1d4  mov     rcx, [rsp+78h+var_38]
0x14002e1d9  xor     rcx, rsp; StackCookie
0x14002e1dc  call    __security_check_cookie
0x14002e1e1  add     rsp, 50h
0x14002e1e5  pop     r14
0x14002e1e7  pop     rdi
0x14002e1e8  pop     rsi
0x14002e1e9  pop     rbp
0x14002e1ea  pop     rbx
0x14002e1eb  retn
0x14002e1ed  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14002e1f2  test    eax, eax
0x14002e1f4  jz      short loc_14002E229
0x14002e1f6  mov     eax, [rsp+78h+var_40]
0x14002e1fa  cmp     eax, 66626473h
0x14002e1ff  jz      short loc_14002E229
0x14002e201  test    dil, 2
0x14002e205  jnz     short loc_14002E229
0x14002e207  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x14002e20e  mov     r8d, 0B5Ch
0x14002e214  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14002e21b  mov     [rsp+78h+var_58], eax
0x14002e21f  mov     ecx, r14d
0x14002e222  call    AslLogCallPrintf
0x14002e227  jmp     short loc_14002E1CA
0x14002e229  mov     r8d, edi
0x14002e22c  lea     rdx, [rsp+78h+var_48]
0x14002e231  mov     rcx, rbx
0x14002e234  call    SdbpValidateAndApplyCompatFlags
0x14002e239  test    eax, eax
0x14002e23b  jz      short loc_14002E1CA
0x14002e23d  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14002e242  test    eax, eax
0x14002e244  jz      short loc_14002E261
0x14002e246  mov     rcx, rbx
0x14002e249  call    SdbpValidateRootTagSizes
0x14002e24e  test    eax, eax
0x14002e250  jns     short loc_14002E261
0x14002e252  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x14002e259  mov     r8d, 0B68h
0x14002e25f  jmp     short loc_14002E214
0x14002e261  mov     rax, rbx
0x14002e264  jmp     loc_14002E1D4
```

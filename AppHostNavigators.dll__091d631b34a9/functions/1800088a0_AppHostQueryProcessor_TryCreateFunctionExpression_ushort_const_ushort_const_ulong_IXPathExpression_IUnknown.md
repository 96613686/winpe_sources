# AppHostQueryProcessor::TryCreateFunctionExpression(ushort const *,ushort const *,ulong,IXPathExpression * *,IUnknown * *)

- ea: `0x1800088a0`
- end: `0x180008a97`
- name: `?TryCreateFunctionExpression@AppHostQueryProcessor@@UEAAJPEBG0KPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(AppHostQueryProcessor *this, const unsigned __int16 *, char *, unsigned int, struct IXPathExpression **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800088a0`
- `0x18000e210`
- `0x18001307a`
- `0x180014010`

## string_xrefs

- `0x18000890a`: `get-config`
- `0x1800089b5`: `get-raw-config`

## pseudocode

```c
__int64 __fastcall AppHostQueryProcessor::TryCreateFunctionExpression(
        AppHostQueryProcessor *this,
        const unsigned __int16 *a2,
        char *a3,
        unsigned int a4,
        struct IXPathExpression **a5,
        struct IUnknown **a6)
{
  struct IXPathExpression **v8; // r14
  __int64 result; // rax
  struct IUnknown **v10; // rbp
  int v11; // eax
  struct IXPathExpression *v12; // rcx
  __int64 (__fastcall *v13)(); // rax
  struct IXPathExpression *v14; // rcx
  unsigned __int16 i; // ax
  char *v16; // rcx
  int v17; // r8d
  int v18; // edx
  unsigned int v19; // ecx
  int v20; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 || !*(_WORD *)a3 )
    return 2147942487LL;
  v8 = a5;
  if ( a4 )
  {
    if ( !a5 )
      return 2147942487LL;
  }
  else if ( a5 )
  {
    return 2147942487LL;
  }
  v10 = a6;
  if ( !a6 || *a6 )
    return 2147942487LL;
  if ( wcscmp_0((const wchar_t *)a3, L"get-config") )
  {
    if ( !wcscmp_0((const wchar_t *)a3, L"get-locations") )
    {
      if ( !a4 )
      {
        v11 = ((__int64 (__fastcall *)(_QWORD, struct IXPathExpression **, struct IUnknown **))SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateContextNodeProjection)(
                0,
                v8,
                v10);
        goto LABEL_41;
      }
      if ( a4 == 1 )
      {
        v13 = SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateIteratorProjection;
LABEL_39:
        if ( v13 )
        {
          v11 = ((__int64 (__fastcall *)(_QWORD, struct IXPathExpression **, struct IUnknown **))v13)(a4, v8, v10);
          goto LABEL_41;
        }
      }
    }
    else
    {
      if ( wcscmp_0((const wchar_t *)a3, L"get-raw-config") )
      {
        for ( i = 0; i < 2u; ++i )
        {
          v16 = a3;
          do
          {
            v17 = *(unsigned __int16 *)&v16[(char *)(&off_18001C000)[2 * (__int16)i] - a3];
            v18 = *(unsigned __int16 *)v16 - v17;
            if ( v18 )
              break;
            v16 += 2;
          }
          while ( v17 );
          if ( !v18 )
          {
            v13 = (__int64 (__fastcall *)())*(&funcs_180008A7C + 2 * (__int16)i);
            goto LABEL_39;
          }
        }
        return 1;
      }
      if ( !a4 )
      {
        v11 = ((__int64 (__fastcall *)(_QWORD, struct IXPathExpression **, struct IUnknown **))SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateContextNodeProjection)(
                0,
                v8,
                v10);
        goto LABEL_41;
      }
      if ( a4 == 1 )
      {
        v14 = *v8;
        v20 = 4;
        result = (*(__int64 (__fastcall **)(struct IXPathExpression *, int *))(*(_QWORD *)v14 + 24LL))(v14, &v20);
        if ( (int)result < 0 )
          return result;
        if ( v20 == 3 )
        {
          v11 = ((__int64 (__fastcall *)(__int64, struct IXPathExpression **, struct IUnknown **))SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateIteratorProjection)(
                  1,
                  v8,
                  v10);
          goto LABEL_41;
        }
        v13 = SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateCustomProjection<FileConfigPathStringToPositionIterator>;
        goto LABEL_39;
      }
    }
    return 1;
  }
  if ( a4 )
  {
    if ( a4 != 1 )
      return 1;
    v12 = *v8;
    v20 = 4;
    result = (*(__int64 (__fastcall **)(struct IXPathExpression *, int *))(*(_QWORD *)v12 + 24LL))(v12, &v20);
    if ( (int)result < 0 )
      return result;
    if ( v20 == 3 )
    {
      v11 = ((__int64 (__fastcall *)(__int64, struct IXPathExpression **, struct IUnknown **))SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateIteratorProjection)(
              1,
              v8,
              v10);
      goto LABEL_41;
    }
    v13 = SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateCustomProjection<ConfigPathStringToPositionIterator>;
    goto LABEL_39;
  }
  v11 = ((__int64 (__fastcall *)(_QWORD, struct IXPathExpression **, struct IUnknown **))SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateContextNodeProjection)(
          0,
          v8,
          v10);
LABEL_41:
  v19 = 0;
  if ( v11 < 0 )
    return (unsigned int)v11;
  return v19;
}

```

## disassembly

```asm
0x1800088a0  mov     [rsp+arg_0], rbx
0x1800088a5  mov     [rsp+arg_8], rbp
0x1800088aa  push    rsi
0x1800088ab  push    rdi
0x1800088ac  push    r12
0x1800088ae  push    r14
0x1800088b0  push    r15
0x1800088b2  sub     rsp, 20h
0x1800088b6  xor     r15d, r15d
0x1800088b9  mov     edi, r9d
0x1800088bc  mov     rsi, r8
0x1800088bf  test    r8, r8
0x1800088c2  jz      short loc_1800088D9
0x1800088c4  cmp     [r8], r15w
0x1800088c8  jz      short loc_1800088D9
0x1800088ca  mov     r14, [rsp+48h+arg_20]
0x1800088cf  test    r9d, r9d
0x1800088d2  jnz     short loc_1800088F5
0x1800088d4  test    r14, r14
0x1800088d7  jz      short loc_1800088FA
0x1800088d9  mov     eax, 80070057h
0x1800088de  mov     rbx, [rsp+48h+arg_0]
0x1800088e3  mov     rbp, [rsp+48h+arg_8]
0x1800088e8  add     rsp, 20h
0x1800088ec  pop     r15
0x1800088ee  pop     r14
0x1800088f0  pop     r12
0x1800088f2  pop     rdi
0x1800088f3  pop     rsi
0x1800088f4  retn
0x1800088f5  test    r14, r14
0x1800088f8  jz      short loc_1800088D9
0x1800088fa  mov     rbp, [rsp+48h+arg_28]
0x1800088ff  test    rbp, rbp
0x180008902  jz      short loc_1800088D9
0x180008904  cmp     [rbp+0], r15
0x180008908  jnz     short loc_1800088D9
0x18000890a  lea     rdx, aGetConfig; "get-config"
0x180008911  mov     rcx, rsi; String1
0x180008914  call    wcscmp_0
0x180008919  test    eax, eax
0x18000891b  jnz     short loc_180008979
0x18000891d  test    edi, edi
0x18000891f  jnz     short loc_18000892D
0x180008921  lea     rax, ?CreateContextNodeProjection@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)
0x180008928  jmp     loc_180008A74
0x18000892d  mov     ebx, 1
0x180008932  cmp     edi, ebx
0x180008934  jnz     loc_180008A90
0x18000893a  mov     rcx, [r14]
0x18000893d  lea     rdx, [rsp+48h+arg_10]
0x180008942  mov     [rsp+48h+arg_10], 4
0x18000894a  mov     rax, [rcx]
0x18000894d  mov     rax, [rax+18h]
0x180008951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008956  test    eax, eax
0x180008958  js      short loc_1800088DE
0x18000895a  cmp     [rsp+48h+arg_10], 3
0x18000895f  jnz     short loc_18000896D
0x180008961  lea     rax, ?CreateIteratorProjection@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateIteratorProjection(ulong,IXPathExpression * *,IUnknown * *)
0x180008968  jmp     loc_180008A74
0x18000896d  lea     rax, ??$CreateCustomProjection@VConfigPathStringToPositionIterator@@@?$SelectorTemplate@VConfigPathToMergedConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigPathToMergedConfigSelector>::CreateCustomProjection<ConfigPathStringToPositionIterator>(ulong,IXPathExpression * *,IUnknown * *)
0x180008974  jmp     loc_180008A6F
0x180008979  lea     rdx, aGetLocations; "get-locations"
0x180008980  mov     rcx, rsi; String1
0x180008983  call    wcscmp_0
0x180008988  test    eax, eax
0x18000898a  jnz     short loc_1800089B5
0x18000898c  test    edi, edi
0x18000898e  jnz     short loc_18000899C
0x180008990  lea     rax, ?CreateContextNodeProjection@?$SelectorTemplate@VConfigPathToConfigLocationSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)
0x180008997  jmp     loc_180008A74
0x18000899c  mov     ebx, 1
0x1800089a1  cmp     edi, ebx
0x1800089a3  jnz     loc_180008A90
0x1800089a9  lea     rax, ?CreateIteratorProjection@?$SelectorTemplate@VConfigPathToConfigLocationSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigPathToConfigLocationSelector>::CreateIteratorProjection(ulong,IXPathExpression * *,IUnknown * *)
0x1800089b0  jmp     loc_180008A6F
0x1800089b5  lea     rdx, aGetRawConfig; "get-raw-config"
0x1800089bc  mov     rcx, rsi; String1
0x1800089bf  call    wcscmp_0
0x1800089c4  test    eax, eax
0x1800089c6  jnz     short loc_180008A22
0x1800089c8  test    edi, edi
0x1800089ca  jnz     short loc_1800089D8
0x1800089cc  lea     rax, ?CreateContextNodeProjection@?$SelectorTemplate@VConfigLocationToRawConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateContextNodeProjection(ulong,IXPathExpression * *,IUnknown * *)
0x1800089d3  jmp     loc_180008A74
0x1800089d8  mov     ebx, 1
0x1800089dd  cmp     edi, ebx
0x1800089df  jnz     loc_180008A90
0x1800089e5  mov     rcx, [r14]
0x1800089e8  lea     rdx, [rsp+48h+arg_10]
0x1800089ed  mov     [rsp+48h+arg_10], 4
0x1800089f5  mov     rax, [rcx]
0x1800089f8  mov     rax, [rax+18h]
0x1800089fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a01  test    eax, eax
0x180008a03  js      loc_1800088DE
0x180008a09  cmp     [rsp+48h+arg_10], 3
0x180008a0e  jnz     short loc_180008A19
0x180008a10  lea     rax, ?CreateIteratorProjection@?$SelectorTemplate@VConfigLocationToRawConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateIteratorProjection(ulong,IXPathExpression * *,IUnknown * *)
0x180008a17  jmp     short loc_180008A74
0x180008a19  lea     rax, ??$CreateCustomProjection@VFileConfigPathStringToPositionIterator@@@?$SelectorTemplate@VConfigLocationToRawConfigSelector@@@@SAJKPEAPEAUIXPathExpression@@PEAPEAUIUnknown@@@Z; SelectorTemplate<ConfigLocationToRawConfigSelector>::CreateCustomProjection<FileConfigPathStringToPositionIterator>(ulong,IXPathExpression * *,IUnknown * *)
0x180008a20  jmp     short loc_180008A6F
0x180008a22  mov     ebx, 1
0x180008a27  lea     r12, off_18001C000; "get-metadata"
0x180008a2e  mov     eax, r15d
0x180008a31  lea     r11d, [rbx+1]
0x180008a35  cmp     ax, r11w
0x180008a39  jnb     short loc_180008A90
0x180008a3b  movsx   r9, ax
0x180008a3f  mov     rcx, rsi
0x180008a42  add     r9, r9
0x180008a45  mov     r10, [r12+r9*8]
0x180008a49  sub     r10, rsi
0x180008a4c  movzx   edx, word ptr [rcx]
0x180008a4f  movzx   r8d, word ptr [rcx+r10]
0x180008a54  sub     edx, r8d
0x180008a57  jnz     short loc_180008A61
0x180008a59  add     rcx, r11
0x180008a5c  test    r8d, r8d
0x180008a5f  jnz     short loc_180008A4C
0x180008a61  test    edx, edx
0x180008a63  jz      short loc_180008A6A
0x180008a65  add     ax, bx
0x180008a68  jmp     short loc_180008A35
0x180008a6a  mov     rax, (funcs_180008A7C - 18001C000h)[r12+r9*8]
0x180008a6f  test    rax, rax
0x180008a72  jz      short loc_180008A90
0x180008a74  mov     r8, rbp; struct IUnknown **
0x180008a77  mov     rdx, r14; struct IXPathExpression **
0x180008a7a  mov     ecx, edi; unsigned int
0x180008a7c  call    _guard_dispatch_icall$thunk$10345483385596137414; GetMetadataFunction::CreateInstance(ulong,IXPathExpression * *,IUnknown * *) ...
0x180008a81  test    eax, eax
0x180008a83  mov     ecx, r15d
0x180008a86  cmovs   ecx, eax
0x180008a89  mov     eax, ecx
0x180008a8b  jmp     loc_1800088DE
0x180008a90  mov     eax, ebx
0x180008a92  jmp     loc_1800088DE
```

# WPP_SF_ssdd

- ea: `0x1800256d0`
- end: `0x18002576e`
- name: `WPP_SF_ssdd`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f160`

## callees

- `0x1800256d0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180025763`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180025763`

## string_xrefs

- `0x18002573d`: `DllUnregisterServer`

## pseudocode

```c
ULONG WPP_SF_ssdd(TRACEHANDLE a1, __int64 a2, __int64 a3, const char *a4, int a5, ...)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids,
           0x10u,
           a4,
           v6,
           "DllUnregisterServer",
           20,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1800256d0  sub     rsp, 78h
0x1800256d4  test    r9, r9
0x1800256d7  jz      short loc_1800256EC
0x1800256d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800256dd  inc     rax
0x1800256e0  cmp     byte ptr [r9+rax], 0
0x1800256e5  jnz     short loc_1800256DD
0x1800256e7  inc     rax
0x1800256ea  jmp     short loc_1800256F1
0x1800256ec  mov     eax, 5
0x1800256f1  mov     [rsp+78h+var_18], 0
0x1800256fa  lea     rdx, aNull; "NULL"
0x180025701  mov     r10d, 10h
0x180025707  test    r9, r9
0x18002570a  cmovz   r9, rdx
0x18002570e  lea     rdx, [rsp+78h+arg_30]
0x180025716  lea     r8d, [r10-0Ch]
0x18002571a  mov     [rsp+78h+var_20], r8
0x18002571f  mov     [rsp+78h+var_28], rdx
0x180025724  lea     rdx, [rsp+78h+arg_28]
0x18002572c  mov     [rsp+78h+var_30], r8
0x180025731  lea     r8, WPP_a84eb28aad63382c633638e94ebf5e29_Traceguids; MessageGuid
0x180025738  mov     [rsp+78h+var_38], rdx
0x18002573d  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x180025744  mov     [rsp+78h+var_40], 14h
0x18002574d  mov     [rsp+78h+var_48], rdx
0x180025752  lea     edx, [r10+1Bh]; MessageFlags
0x180025756  mov     [rsp+78h+var_50], rax
0x18002575b  mov     [rsp+78h+var_58], r9
0x180025760  mov     r9d, r10d; MessageNumber
0x180025763  call    cs:__imp_TraceMessage
0x180025769  add     rsp, 78h
0x18002576d  retn
```

# __lambda_463403af73c19f5d1214a3baa98735ac_::operator()_::_1_::catch$9

- ea: `0x18008db6d`
- end: `0x18008dbcb`
- name: `__lambda_463403af73c19f5d1214a3baa98735ac_::operator()_::_1_::catch$9`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180098010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18008dbb3`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18008dbb3`

## string_xrefs

- `0x18008dbaa`: `MapsStoreManager::FetchCopyrightAsync::<lambda_463403af73c19f5d1214a3baa98735ac>::operator ()`
- `0x18008db9d`: `Exception processing Bing imagery copyright response: %s`

## pseudocode

```c
__int64 __fastcall _lambda_463403af73c19f5d1214a3baa98735ac_::operator()_::_1_::catch_9(__int64 a1, __int64 a2)
{
  const char *v2; // rax

  *(_DWORD *)(**(_QWORD **)(a2 + 48) + 76LL) = 3;
  v2 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 72) + 8LL))(*(_QWORD *)(a2 + 72));
  ZTraceHelperNoThis(
    0,
    "MapsStoreManager::FetchCopyrightAsync::<lambda_463403af73c19f5d1214a3baa98735ac>::operator ()",
    1106,
    "Exception processing Bing imagery copyright response: %s",
    v2);
  return 0;
}

```

## disassembly

```asm
0x18008db6d  mov     [rsp+arg_8], rdx
0x18008db72  push    rbp
0x18008db73  sub     rsp, 30h
0x18008db77  mov     rbp, rdx
0x18008db7a  mov     rax, [rbp+30h]
0x18008db7e  mov     rcx, [rax]
0x18008db81  mov     dword ptr [rcx+4Ch], 3
0x18008db88  mov     rcx, [rbp+48h]
0x18008db8c  mov     rax, [rcx]
0x18008db8f  mov     rax, [rax+8]
0x18008db93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008db98  mov     [rsp+38h+var_18], rax
0x18008db9d  lea     r9, aExceptionProce; "Exception processing Bing imagery copyr"...
0x18008dba4  mov     r8d, 452h
0x18008dbaa  lea     rdx, aMapsstoremanag; "MapsStoreManager::FetchCopyrightAsync::"...
0x18008dbb1  xor     ecx, ecx
0x18008dbb3  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18008dbb9  nop
0x18008dbba  mov     rax, 0
0x18008dbc4  add     rsp, 30h
0x18008dbc8  pop     rbp
0x18008dbc9  retn
```

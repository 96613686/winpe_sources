# __AfxCompareSafeArrays_::_1_::catch$0

- ea: `0x1800d4d97`
- end: `0x1800d4e0c`
- name: `__AfxCompareSafeArrays_::_1_::catch$0`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180024fc0`
- `0x1800d1de2`
- `0x1800d4d97`

## import_xrefs

- `msvcrt!free` at `0x1800d4da8`
- `msvcrt!free` at `0x1800d4db2`
- `msvcrt!free` at `0x1800d4dbc`
- `msvcrt!free` at `0x1800d4dc6`
- `msvcrt!free` at `0x1800d4da8`
- `msvcrt!free` at `0x1800d4db2`
- `msvcrt!free` at `0x1800d4dbc`
- `msvcrt!free` at `0x1800d4dc6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4dda`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4df5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4dda`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d4df5`

## pseudocode

```c
void __fastcall __noreturn _AfxCompareSafeArrays_::_1_::catch_0(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  HRESULT v4; // eax

  free(*(void **)(a2 + 64));
  free(*(void **)(a2 + 72));
  free(*(void **)(a2 + 80));
  free(*(void **)(a2 + 88));
  if ( *(_QWORD *)(a2 + 48) )
  {
    v3 = SafeArrayUnaccessData(*(SAFEARRAY **)(a2 + 192));
    AfxCheckError(v3);
  }
  if ( *(_QWORD *)(a2 + 56) )
  {
    v4 = SafeArrayUnaccessData(*(SAFEARRAY **)(a2 + 200));
    AfxCheckError(v4);
  }
  throw;
}

```

## disassembly

```asm
0x1800d4d97  mov     [rsp+arg_8], rdx
0x1800d4d9c  push    rbp
0x1800d4d9d  sub     rsp, 20h
0x1800d4da1  mov     rbp, rdx
0x1800d4da4  mov     rcx, [rbp+40h]; Block
0x1800d4da8  call    cs:__imp_free
0x1800d4dae  mov     rcx, [rbp+48h]; Block
0x1800d4db2  call    cs:__imp_free
0x1800d4db8  mov     rcx, [rbp+50h]; Block
0x1800d4dbc  call    cs:__imp_free
0x1800d4dc2  mov     rcx, [rbp+58h]; Block
0x1800d4dc6  call    cs:__imp_free
0x1800d4dcc  cmp     qword ptr [rbp+30h], 0
0x1800d4dd1  jz      short loc_1800D4DE7
0x1800d4dd3  mov     rcx, [rbp+0C0h]; psa
0x1800d4dda  call    cs:__imp_SafeArrayUnaccessData
0x1800d4de0  mov     ecx, eax; int
0x1800d4de2  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x1800d4de7  cmp     qword ptr [rbp+38h], 0
0x1800d4dec  jz      short loc_1800D4E02
0x1800d4dee  mov     rcx, [rbp+0C8h]; psa
0x1800d4df5  call    cs:__imp_SafeArrayUnaccessData
0x1800d4dfb  mov     ecx, eax; int
0x1800d4dfd  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x1800d4e02  xor     edx, edx; pThrowInfo
0x1800d4e04  xor     ecx, ecx; pExceptionObject
0x1800d4e06  call    _CxxThrowException_0
```

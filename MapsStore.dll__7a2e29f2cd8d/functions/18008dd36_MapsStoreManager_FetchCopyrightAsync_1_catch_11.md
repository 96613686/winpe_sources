# _MapsStoreManager::FetchCopyrightAsync_::_1_::catch$11

- ea: `0x18008dd36`
- end: `0x18008dd94`
- name: `_MapsStoreManager::FetchCopyrightAsync_::_1_::catch$11`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180098010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18008dd7c`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18008dd7c`

## string_xrefs

- `0x18008dd66`: `Exception executing Bing imagery copyright response: %s`
- `0x18008dd73`: `MapsStoreManager::FetchCopyrightAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::FetchCopyrightAsync_::_1_::catch_11(__int64 a1, __int64 a2)
{
  const char *v2; // rax

  *(_DWORD *)(*(_QWORD *)(a2 + 96) + 76LL) = 3;
  v2 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 136) + 8LL))(*(_QWORD *)(a2 + 136));
  ZTraceHelperNoThis(
    0,
    "MapsStoreManager::FetchCopyrightAsync",
    1113,
    "Exception executing Bing imagery copyright response: %s",
    v2);
  return 0;
}

```

## disassembly

```asm
0x18008dd36  mov     [rsp+arg_8], rdx
0x18008dd3b  push    rbp
0x18008dd3c  sub     rsp, 30h
0x18008dd40  mov     rbp, rdx
0x18008dd43  mov     rax, [rbp+60h]
0x18008dd47  mov     dword ptr [rax+4Ch], 3
0x18008dd4e  mov     rcx, [rbp+88h]
0x18008dd55  mov     rax, [rcx]
0x18008dd58  mov     rax, [rax+8]
0x18008dd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd61  mov     [rsp+38h+var_18], rax
0x18008dd66  lea     r9, aExceptionExecu; "Exception executing Bing imagery copyri"...
0x18008dd6d  mov     r8d, 459h
0x18008dd73  lea     rdx, aMapsstoremanag_0; "MapsStoreManager::FetchCopyrightAsync"
0x18008dd7a  xor     ecx, ecx
0x18008dd7c  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18008dd82  nop
0x18008dd83  mov     rax, 0
0x18008dd8d  add     rsp, 30h
0x18008dd91  pop     rbp
0x18008dd92  retn
```

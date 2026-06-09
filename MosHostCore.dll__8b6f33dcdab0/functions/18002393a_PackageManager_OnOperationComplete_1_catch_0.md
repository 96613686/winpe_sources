# _PackageManager::OnOperationComplete_::_1_::catch$0

- ea: `0x18002393a`
- end: `0x180023979`
- name: `_PackageManager::OnOperationComplete_::_1_::catch$0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800109a4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18002395f`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18002395f`

## string_xrefs

- `0x180023956`: `PackageManager::OnOperationComplete`

## pseudocode

```c
__int64 __fastcall PackageManager::OnOperationComplete_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 64) = ZTraceReportOrigination(
                           v3,
                           "PackageManager::OnOperationComplete",
                           272,
                           *(const void **)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x18002393a  mov     [rsp+arg_8], rdx
0x18002393f  push    rbp
0x180023940  sub     rsp, 20h
0x180023944  mov     rbp, rdx
0x180023947  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18002394c  mov     r9, [rbp+40h]
0x180023950  mov     r8d, 110h
0x180023956  lea     rdx, aPackagemanager_12; "PackageManager::OnOperationComplete"
0x18002395d  mov     ecx, eax
0x18002395f  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180023965  mov     [rbp+40h], eax
0x180023968  mov     rax, 0
0x180023972  add     rsp, 20h
0x180023976  pop     rbp
0x180023977  retn
```

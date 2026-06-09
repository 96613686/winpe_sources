# wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset(void)

- ea: `0x18000fe1c`
- end: `0x18000fe7c`
- name: `?reset@?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAXXZ`
- size: `96`
- prototype: `void __fastcall(__int64, struct PrintJobCleanUpUtil::StalePrintJobInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a688`
- `0x18000ab74`

## callees

- `0x18000c06c`
- `0x18000fe1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe57`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::reset(
        __int64 a1,
        struct PrintJobCleanUpUtil::StalePrintJobInfo *a2)
{
  LPVOID *v2; // rbx
  LPVOID *v4; // rsi

  v2 = *(LPVOID **)a1;
  if ( *(_QWORD *)a1 )
  {
    v4 = &v2[2 * *(_QWORD *)(a1 + 8)];
    while ( v2 != v4 )
    {
      PrintJobCleanUpUtil::FreeStalePrintJobInfo(v2, a2);
      v2 += 2;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000fe1c  mov     [rsp+arg_0], rbx
0x18000fe21  mov     [rsp+arg_8], rsi
0x18000fe26  push    rdi
0x18000fe27  sub     rsp, 20h
0x18000fe2b  mov     rbx, [rcx]
0x18000fe2e  mov     rdi, rcx
0x18000fe31  test    rbx, rbx
0x18000fe34  jz      short loc_18000FE6C
0x18000fe36  mov     rsi, [rcx+8]
0x18000fe3a  shl     rsi, 4
0x18000fe3e  add     rsi, rbx
0x18000fe41  jmp     short loc_18000FE4F
0x18000fe43  mov     rcx, rbx; this
0x18000fe46  call    ?FreeStalePrintJobInfo@PrintJobCleanUpUtil@@YAXPEAUStalePrintJobInfo@1@@Z; PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)
0x18000fe4b  add     rbx, 10h
0x18000fe4f  cmp     rbx, rsi
0x18000fe52  jnz     short loc_18000FE43
0x18000fe54  mov     rcx, [rdi]; pv
0x18000fe57  call    cs:__imp_CoTaskMemFree
0x18000fe5d  mov     qword ptr [rdi], 0
0x18000fe64  mov     qword ptr [rdi+8], 0
0x18000fe6c  mov     rbx, [rsp+28h+arg_0]
0x18000fe71  mov     rsi, [rsp+28h+arg_8]
0x18000fe76  add     rsp, 20h
0x18000fe7a  pop     rdi
0x18000fe7b  retn
```

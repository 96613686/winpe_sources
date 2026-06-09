# MultiWorkQueueWorkCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180008640`
- end: `0x1800086af`
- name: `?MultiWorkQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `111`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008640`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180008691`
- `iisutil!PuDbgPrintError` at `0x180008691`

## string_xrefs

- `0x180008686`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_item.cxx`

## pseudocode

```c
void __fastcall MultiWorkQueueWorkCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD **Context)
{
  int v3; // eax

  v3 = (*(__int64 (__fastcall **)(_QWORD *))(*Context[3] + 16LL))(Context[3]);
  if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_item.cxx",
      150,
      "MULTI_WORK_ITEM::Execute",
      v3,
      "Work item execution returned an error\n");
  ((void (__fastcall *)(_QWORD **, __int64))**Context)(Context, 1);
}

```

## disassembly

```asm
0x180008640  push    rbx
0x180008642  sub     rsp, 30h
0x180008646  mov     rcx, [rdx+18h]
0x18000864a  mov     rbx, rdx
0x18000864d  mov     rax, [rcx]
0x180008650  mov     rax, [rax+10h]
0x180008654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008659  test    eax, eax
0x18000865b  jns     short loc_180008697
0x18000865d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180008664  jz      short loc_180008697
0x180008666  lea     rcx, aWorkItemExecut; "Work item execution returned an error\n"
0x18000866d  mov     r8d, 96h
0x180008673  mov     [rsp+38h+var_10], rcx
0x180008678  lea     r9, aMultiWorkItemE; "MULTI_WORK_ITEM::Execute"
0x18000867f  mov     rcx, cs:g_pDebug
0x180008686  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000868d  mov     [rsp+38h+var_18], eax
0x180008691  call    cs:__imp_PuDbgPrintError
0x180008697  mov     rax, [rbx]
0x18000869a  mov     edx, 1
0x18000869f  mov     rcx, rbx
0x1800086a2  mov     rax, [rax]
0x1800086a5  add     rsp, 30h
0x1800086a9  pop     rbx
0x1800086aa  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

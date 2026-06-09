# EVENT_LOG::DestroyEventLogSource(_EVENT_LOG_SOURCE *)

- ea: `0x180007fbc`
- end: `0x18000805b`
- name: `?DestroyEventLogSource@EVENT_LOG@@CAXPEAU_EVENT_LOG_SOURCE@@@Z`
- size: `159`
- prototype: `void __fastcall(struct _EVENT_LOG_SOURCE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800080ac`

## callees

- `0x180007234`
- `0x180007fbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007ff0`
- `KERNEL32!GetLastError` at `0x180007ff0`
- `KERNEL32!GetProcessHeap` at `0x180008034`
- `KERNEL32!GetProcessHeap` at `0x180008034`
- `KERNEL32!HeapFree` at `0x180008042`
- `KERNEL32!HeapFree` at `0x180008042`
- `ADVAPI32!DeregisterEventSource` at `0x180007fd2`
- `ADVAPI32!DeregisterEventSource` at `0x180007fd2`

## string_xrefs

- `0x180008008`: `servercommon\inetsrv\iis\iisrearc\core\common\util\eventlog.cxx`

## pseudocode

```c
void __fastcall EVENT_LOG::DestroyEventLogSource(struct _EVENT_LOG_SOURCE *a1)
{
  void *v2; // rcx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax

  v2 = (void *)*((_QWORD *)a1 + 1);
  if ( v2 && !DeregisterEventSource(v2) && (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
  {
    GetLastError();
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\eventlog.cxx",
      0x1A5u,
      "EVENT_LOG::DestroyEventLogSource",
      "Destruction of EVENT_LOG_SOURCE[%p] failed. error %lu\n",
      (char)a1);
  }
  v3 = (void *)*((_QWORD *)a1 + 2);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x180007fbc  mov     [rsp+arg_0], rbx
0x180007fc1  push    rdi
0x180007fc2  sub     rsp, 40h
0x180007fc6  mov     rbx, rcx
0x180007fc9  mov     rcx, [rcx+8]; hEventLog
0x180007fcd  test    rcx, rcx
0x180007fd0  jz      short loc_18000802B
0x180007fd2  call    cs:__imp_DeregisterEventSource
0x180007fd8  test    eax, eax
0x180007fda  jnz     short loc_18000802B
0x180007fdc  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180007fe2  test    al, 3
0x180007fe4  setnz   cl
0x180007fe7  test    al, 4
0x180007fe9  setnz   al
0x180007fec  test    al, cl
0x180007fee  jz      short loc_18000802B
0x180007ff0  call    cs:__imp_GetLastError
0x180007ff6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180007ffd  lea     r9, aEventLogDestro; "EVENT_LOG::DestroyEventLogSource"
0x180008004  mov     [rsp+48h+var_18], eax
0x180008008  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000800f  lea     rax, aDestructionOfE; "Destruction of EVENT_LOG_SOURCE[%p] fai"...
0x180008016  mov     qword ptr [rsp+48h+var_20], rbx; char
0x18000801b  mov     r8d, 1A5h; unsigned int
0x180008021  mov     [rsp+48h+var_28], rax; char *
0x180008026  call    PuDbgPrint
0x18000802b  mov     rdi, [rbx+10h]
0x18000802f  test    rdi, rdi
0x180008032  jz      short loc_180008050
0x180008034  call    cs:__imp_GetProcessHeap
0x18000803a  mov     r8, rdi; lpMem
0x18000803d  xor     edx, edx; dwFlags
0x18000803f  mov     rcx, rax; hHeap
0x180008042  call    cs:__imp_HeapFree
0x180008048  mov     qword ptr [rbx+10h], 0
0x180008050  mov     rbx, [rsp+48h+arg_0]
0x180008055  add     rsp, 40h
0x180008059  pop     rdi
0x18000805a  retn
```

# CDirMonitorEntry::RequestNotification(void)

- ea: `0x180018d1c`
- end: `0x180018da9`
- name: `?RequestNotification@CDirMonitorEntry@@AEAAHXZ`
- size: `141`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018b30`
- `0x180063d14`

## callees

- `0x180018d1c`
- `0x180063e44`

## import_xrefs

- `KERNEL32!ReadDirectoryChangesW` at `0x180018d8c`
- `KERNEL32!ReadDirectoryChangesW` at `0x180018d8c`
- `iisutil!PuDbgPrint` at `0x18002eea7`
- `iisutil!PuDbgPrint` at `0x18002eea7`

## string_xrefs

- `0x18002eea0`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

## pseudocode

```c
__int64 __fastcall CDirMonitorEntry::RequestNotification(CDirMonitorEntry *this)
{
  unsigned int v2; // edi
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      237,
      "CDirMonitorEntry::RequestNotification",
      "[CDirMonitorEntry] Request change notification\n");
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 9);
  v2 = ReadDirectoryChangesW(
         *((HANDLE *)this + 5),
         *((LPVOID *)this + 3),
         *((_DWORD *)this + 22),
         *((_DWORD *)this + 12),
         *((_DWORD *)this + 13),
         &BytesReturned,
         (LPOVERLAPPED)((char *)this + 56),
         0);
  if ( !v2 )
    CDirMonitorEntry::IORelease(this);
  return v2;
}

```

## disassembly

```asm
0x180018d1c  mov     [rsp+arg_8], rbx
0x180018d21  push    rdi
0x180018d22  sub     rsp, 40h
0x180018d26  mov     eax, cs:g_dwDebugFlags
0x180018d2c  mov     rbx, rcx
0x180018d2f  test    al, 3
0x180018d31  mov     [rsp+48h+BytesReturned], 0
0x180018d39  setnz   dl
0x180018d3c  bt      eax, 10h
0x180018d40  setb    al
0x180018d43  test    al, dl
0x180018d45  jnz     loc_18002EE80
0x180018d4b  lea     rax, [rbx+38h]
0x180018d4f  xorps   xmm0, xmm0
0x180018d52  movups  xmmword ptr [rax], xmm0
0x180018d55  movups  xmmword ptr [rax+10h], xmm0
0x180018d59  lock inc dword ptr [rbx+24h]
0x180018d5d  mov     r9d, [rbx+30h]; bWatchSubtree
0x180018d61  mov     r8d, [rbx+58h]; nBufferLength
0x180018d65  mov     rdx, [rbx+18h]; lpBuffer
0x180018d69  mov     rcx, [rbx+28h]; hDirectory
0x180018d6d  mov     [rsp+48h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180018d76  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x180018d7b  lea     rax, [rsp+48h+BytesReturned]
0x180018d80  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180018d85  mov     eax, [rbx+34h]
0x180018d88  mov     [rsp+48h+dwNotifyFilter], eax; dwNotifyFilter
0x180018d8c  call    cs:__imp_ReadDirectoryChangesW
0x180018d92  mov     edi, eax
0x180018d94  test    eax, eax
0x180018d96  jz      loc_18002EEB3
0x180018d9c  mov     rbx, [rsp+48h+arg_8]
0x180018da1  mov     eax, edi
0x180018da3  add     rsp, 40h
0x180018da7  pop     rdi
0x180018da8  retn
0x18002ee80  mov     rcx, cs:g_pDebug
0x18002ee87  lea     rax, aCdirmonitorent_0; "[CDirMonitorEntry] Request change notif"...
0x18002ee8e  lea     r9, aCdirmonitorent_2; "CDirMonitorEntry::RequestNotification"
0x18002ee95  mov     qword ptr [rsp+48h+dwNotifyFilter], rax
0x18002ee9a  mov     r8d, 0EDh
0x18002eea0  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18002eea7  call    cs:__imp_PuDbgPrint
0x18002eead  nop
0x18002eeae  jmp     loc_180018D4B
0x18002eeb3  mov     rcx, rbx; this
0x18002eeb6  call    ?IORelease@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::IORelease(void)
0x18002eebb  nop
0x18002eebc  jmp     loc_180018D9C
```

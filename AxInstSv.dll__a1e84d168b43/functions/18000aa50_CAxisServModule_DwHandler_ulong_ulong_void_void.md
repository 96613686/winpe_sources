# CAxisServModule::DwHandler(ulong,ulong,void *,void *)

- ea: `0x18000aa50`
- end: `0x18000ab1b`
- name: `?DwHandler@CAxisServModule@@QEAAKKKPEAX0@Z`
- size: `203`
- prototype: `unsigned int __fastcall(CAxisServModule *__hidden this, unsigned int, unsigned int, void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180010e10`

## callees

- `0x18000725c`
- `0x18000aa50`
- `0x18000fb54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aad3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000aac9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000aac9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000aa75`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000aa75`

## string_xrefs

- `0x18000aa9f`: `Receive service stop request. dwControl=0x%x\n`

## pseudocode

```c
__int64 __fastcall CAxisServModule::DwHandler(CAxisServModule *this, int a2, __int64 a3, void *a4)
{
  __int64 v6; // [rsp+20h] [rbp-18h]

  if ( ((a2 - 1) & 0xFFFFFFFB) != 0 )
  {
    if ( a2 != 4 )
      return 120;
    SetServiceStatus(hServiceStatus, &ServiceStatus);
  }
  else
  {
    CAxisServModule::SetServiceStatus((CAxisServModule *)&_AtlModule, 3u);
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 5u, L"Receive service stop request. dwControl=0x%x\n", a2);
    if ( hEvent )
    {
      if ( !SetEvent(hEvent) )
      {
        LODWORD(v6) = GetLastError();
        AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"SetEvent failed, lasterr=0x%x\n", v6);
      }
    }
    else
    {
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"m_hShutdownEvent=NULL.\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000aa50  push    rbx
0x18000aa52  sub     rsp, 30h
0x18000aa56  lea     eax, [rdx-1]
0x18000aa59  mov     ebx, edx
0x18000aa5b  test    eax, 0FFFFFFFBh
0x18000aa60  jz      short loc_18000AA8A
0x18000aa62  cmp     edx, 4
0x18000aa65  jnz     short loc_18000AA80
0x18000aa67  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000aa6e  lea     rdx, ServiceStatus; lpServiceStatus
0x18000aa75  call    cs:__imp_SetServiceStatus
0x18000aa7b  jmp     loc_18000AB13
0x18000aa80  mov     eax, 78h ; 'x'
0x18000aa85  jmp     loc_18000AB15
0x18000aa8a  mov     edx, 3; unsigned int
0x18000aa8f  lea     rcx, ?_AtlModule@@3VCAxisServModule@@A; this
0x18000aa96  call    ?SetServiceStatus@CAxisServModule@@QEAAXK@Z; CAxisServModule::SetServiceStatus(ulong)
0x18000aa9b  mov     dword ptr [rsp+38h+var_18], ebx
0x18000aa9f  lea     r9, aReceiveService; "Receive service stop request. dwControl"...
0x18000aaa6  mov     ebx, 8
0x18000aaab  lea     rcx, qword_180021AD8; this
0x18000aab2  mov     edx, ebx; unsigned int
0x18000aab4  lea     r8d, [rbx-3]; unsigned __int8
0x18000aab8  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000aabd  mov     rcx, qword ptr cs:hEvent; hEvent
0x18000aac4  test    rcx, rcx
0x18000aac7  jz      short loc_18000AAF8
0x18000aac9  call    cs:__imp_SetEvent
0x18000aacf  test    eax, eax
0x18000aad1  jnz     short loc_18000AB13
0x18000aad3  call    cs:__imp_GetLastError
0x18000aad9  lea     r9, aSeteventFailed; "SetEvent failed, lasterr=0x%x\n"
0x18000aae0  mov     edx, ebx; unsigned int
0x18000aae2  lea     r8d, [rbx-6]; unsigned __int8
0x18000aae6  mov     dword ptr [rsp+38h+var_18], eax
0x18000aaea  lea     rcx, qword_180021AD8; this
0x18000aaf1  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000aaf6  jmp     short loc_18000AB13
0x18000aaf8  lea     r9, aMHshutdowneven; "m_hShutdownEvent=NULL.\n"
0x18000aaff  mov     r8d, 2; unsigned __int8
0x18000ab05  mov     edx, ebx; unsigned int
0x18000ab07  lea     rcx, qword_180021AD8; this
0x18000ab0e  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000ab13  xor     eax, eax
0x18000ab15  add     rsp, 30h
0x18000ab19  pop     rbx
0x18000ab1a  retn
```

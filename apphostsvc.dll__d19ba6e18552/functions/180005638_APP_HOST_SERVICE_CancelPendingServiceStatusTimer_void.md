# APP_HOST_SERVICE::CancelPendingServiceStatusTimer(void)

- ea: `0x180005638`
- end: `0x1800056c3`
- name: `?CancelPendingServiceStatusTimer@APP_HOST_SERVICE@@AEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005a44`
- `0x180006494`

## callees

- `0x180005638`

## import_xrefs

- `ntdll!RtlDeleteTimer` at `0x180005663`
- `ntdll!RtlDeleteTimer` at `0x180005663`
- `iisutil!PuDbgPrintError` at `0x1800056a7`
- `iisutil!PuDbgPrintError` at `0x1800056a7`

## string_xrefs

- `0x1800056a0`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x18000568f`: `APP_HOST_SERVICE::CancelPendingServiceStatusTimer`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::CancelPendingServiceStatusTimer(APP_HOST_SERVICE *this)
{
  unsigned int v2; // ebx
  void *v3; // rcx
  void *v4; // rdx
  NTSTATUS v5; // eax

  v2 = 0;
  v3 = (void *)*((_QWORD *)this + 32);
  if ( v3 )
  {
    v4 = (void *)*((_QWORD *)this + 31);
    if ( v4 )
    {
      v5 = RtlDeleteTimer(v3, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      if ( v5 >= 0 )
      {
        *((_QWORD *)this + 31) = 0;
      }
      else
      {
        v2 = v5 | 0x10000000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
            1787,
            "APP_HOST_SERVICE::CancelPendingServiceStatusTimer",
            v2,
            "Could not cancel timer\n");
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180005638  mov     [rsp+arg_0], rbx
0x18000563d  push    rdi
0x18000563e  sub     rsp, 30h
0x180005642  mov     rdi, rcx
0x180005645  xor     ebx, ebx
0x180005647  mov     rcx, [rcx+100h]; TimerQueue
0x18000564e  test    rcx, rcx
0x180005651  jz      short loc_1800056B6
0x180005653  mov     rdx, [rdi+0F8h]; Timer
0x18000565a  test    rdx, rdx
0x18000565d  jz      short loc_1800056B6
0x18000565f  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180005663  call    cs:__imp_RtlDeleteTimer
0x180005669  test    eax, eax
0x18000566b  jns     short loc_1800056AF
0x18000566d  mov     ebx, eax
0x18000566f  bts     ebx, 1Ch
0x180005673  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000567a  jz      short loc_1800056B6
0x18000567c  mov     rcx, cs:g_pDebug
0x180005683  lea     rax, aCouldNotCancel_0; "Could not cancel timer\n"
0x18000568a  mov     [rsp+38h+var_10], rax
0x18000568f  lea     r9, aAppHostService_1; "APP_HOST_SERVICE::CancelPendingServiceS"...
0x180005696  mov     r8d, 6FBh
0x18000569c  mov     [rsp+38h+var_18], ebx
0x1800056a0  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800056a7  call    cs:__imp_PuDbgPrintError
0x1800056ad  jmp     short loc_1800056B6
0x1800056af  mov     [rdi+0F8h], rbx
0x1800056b6  mov     eax, ebx
0x1800056b8  mov     rbx, [rsp+38h+arg_0]
0x1800056bd  add     rsp, 30h
0x1800056c1  pop     rdi
0x1800056c2  retn
```

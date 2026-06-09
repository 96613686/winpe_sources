# APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus(long)

- ea: `0x1800066e4`
- end: `0x1800067b4`
- name: `?TerminateServiceAndReportFinalStatus@APP_HOST_SERVICE@@AEAAXJ@Z`
- size: `208`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005704`

## callees

- `0x180006494`
- `0x1800066e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000677b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000677b`
- `iisutil!PuDbgPrintError` at `0x180006738`
- `iisutil!PuDbgPrintError` at `0x180006738`

## string_xrefs

- `0x180006731`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180006714`: `Fatal service error, shutting down\n`
- `0x180006720`: `APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus(APP_HOST_SERVICE *this, int a2)
{
  int v2; // ebp
  int v3; // ebx
  int v5; // esi

  v2 = 0;
  v3 = a2;
  if ( a2 < 0 || (v3 = *((_DWORD *)this + 35), v5 = 0, v3 < 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
        1447,
        "APP_HOST_SERVICE::TerminateServiceAndReportFinalStatus",
        v3,
        "Fatal service error, shutting down\n");
    if ( (v3 & 0x1FFF0000) == 0x70000 )
    {
      if ( v3 >= 0 )
        v5 = v3;
      else
        v5 = (unsigned __int16)v3;
    }
    else
    {
      v5 = 1066;
      v2 = v3;
    }
  }
  APP_HOST_SERVICE::Terminate(this);
  if ( *((_DWORD *)this + 48) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    *((_DWORD *)this + 53) = 1;
    *((_DWORD *)this + 55) = v5;
    *((_DWORD *)this + 56) = v2;
    *(_QWORD *)((char *)this + 228) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  }
}

```

## disassembly

```asm
0x1800066e4  push    rbx
0x1800066e6  push    rbp
0x1800066e7  push    rsi
0x1800066e8  push    rdi
0x1800066e9  sub     rsp, 38h
0x1800066ed  xor     ebp, ebp
0x1800066ef  mov     ebx, edx
0x1800066f1  mov     rdi, rcx
0x1800066f4  test    edx, edx
0x1800066f6  js      short loc_180006704
0x1800066f8  mov     ebx, [rcx+8Ch]
0x1800066fe  xor     esi, esi
0x180006700  test    ebx, ebx
0x180006702  jns     short loc_180006760
0x180006704  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000670b  jz      short loc_18000673E
0x18000670d  mov     rcx, cs:g_pDebug
0x180006714  lea     rax, aFatalServiceEr; "Fatal service error, shutting down\n"
0x18000671b  mov     [rsp+58h+var_30], rax
0x180006720  lea     r9, aAppHostService_7; "APP_HOST_SERVICE::TerminateServiceAndRe"...
0x180006727  mov     r8d, 5A7h
0x18000672d  mov     [rsp+58h+var_38], ebx
0x180006731  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006738  call    cs:__imp_PuDbgPrintError
0x18000673e  mov     eax, ebx
0x180006740  and     eax, 1FFF0000h
0x180006745  cmp     eax, 70000h
0x18000674a  jnz     short loc_180006759
0x18000674c  test    ebx, ebx
0x18000674e  jns     short loc_180006755
0x180006750  movzx   esi, bx
0x180006753  jmp     short loc_180006760
0x180006755  mov     esi, ebx
0x180006757  jmp     short loc_180006760
0x180006759  mov     esi, 42Ah
0x18000675e  mov     ebp, ebx
0x180006760  mov     rcx, rdi; this
0x180006763  call    ?Terminate@APP_HOST_SERVICE@@AEAAXXZ; APP_HOST_SERVICE::Terminate(void)
0x180006768  cmp     dword ptr [rdi+0C0h], 0
0x18000676f  jz      short loc_1800067AB
0x180006771  lea     rbx, [rdi+98h]
0x180006778  mov     rcx, rbx; lpCriticalSection
0x18000677b  call    cs:__imp_EnterCriticalSection
0x180006781  mov     rcx, rbx; lpCriticalSection
0x180006784  mov     dword ptr [rdi+0D4h], 1
0x18000678e  mov     [rdi+0DCh], esi
0x180006794  mov     [rdi+0E0h], ebp
0x18000679a  mov     qword ptr [rdi+0E4h], 0
0x1800067a5  call    cs:__imp_LeaveCriticalSection
0x1800067ab  add     rsp, 38h
0x1800067af  pop     rdi
0x1800067b0  pop     rsi
0x1800067b1  pop     rbp
0x1800067b2  pop     rbx
0x1800067b3  retn
```

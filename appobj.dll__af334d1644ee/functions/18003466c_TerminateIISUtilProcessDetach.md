# TerminateIISUtilProcessDetach

- ea: `0x18003466c`
- end: `0x18003472b`
- name: `TerminateIISUtilProcessDetach`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800133cc`
- `0x180034558`

## callees

- `0x18003254c`
- `0x180033218`
- `0x180034218`
- `0x18003466c`
- `0x180034a30`
- `0x180034b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800346ff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034716`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800346ff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034716`

## string_xrefs

- `0x1800346a4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
void TerminateIISUtilProcessDetach()
{
  char v0; // [rsp+28h] [rbp-10h]

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0xE0u,
      "TerminateIISUtilProcessDetach",
      "TerminateIISUtilProcessDetach\n",
      v0);
  if ( dword_18006000C != 2 )
  {
    switch ( dword_18006000C )
    {
      case 3:
LABEL_16:
        DeleteCriticalSection(&CriticalSection);
        break;
      case 5:
LABEL_14:
        if ( g_fInitCsTimerWrap )
        {
          DeleteCriticalSection(&g_csTimerWrap);
          g_fInitCsTimerWrap = 0;
        }
        goto LABEL_16;
      case 6:
LABEL_13:
        ALLOC_CACHE_HANDLER::Cleanup();
        goto LABEL_14;
      case 7:
LABEL_12:
        LKRHashTableUninit();
        goto LABEL_13;
      case 8:
LABEL_11:
        BIG_REF_TRACE::TerminateStatic();
        goto LABEL_12;
      case 9:
        EVENT_LOG::Terminate();
        goto LABEL_11;
    }
  }
  dword_18006000C = 0;
}

```

## disassembly

```asm
0x18003466c  sub     rsp, 38h
0x180034670  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180034676  test    al, 3
0x180034678  setnz   cl
0x18003467b  test    al, 4
0x18003467d  setnz   al
0x180034680  test    al, cl
0x180034682  jz      short loc_1800346B0
0x180034684  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18003468b  lea     rax, aTerminateiisut; "TerminateIISUtilProcessDetach\n"
0x180034692  lea     r9, aTerminateiisut_0; "TerminateIISUtilProcessDetach"
0x180034699  mov     [rsp+38h+var_18], rax; char *
0x18003469e  mov     r8d, 0E0h; unsigned int
0x1800346a4  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800346ab  call    PuDbgPrint
0x1800346b0  mov     ecx, cs:dword_18006000C
0x1800346b6  sub     ecx, 2
0x1800346b9  jz      short loc_18003471C
0x1800346bb  sub     ecx, 1
0x1800346be  jz      short loc_18003470F
0x1800346c0  sub     ecx, 2
0x1800346c3  jz      short loc_1800346EF
0x1800346c5  sub     ecx, 1
0x1800346c8  jz      short loc_1800346E8
0x1800346ca  sub     ecx, 1
0x1800346cd  jz      short loc_1800346E3
0x1800346cf  sub     ecx, 1
0x1800346d2  jz      short loc_1800346DE
0x1800346d4  cmp     ecx, 1
0x1800346d7  jnz     short loc_18003471C
0x1800346d9  call    ?Terminate@EVENT_LOG@@SAXXZ; EVENT_LOG::Terminate(void)
0x1800346de  call    ?TerminateStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::TerminateStatic(void)
0x1800346e3  call    LKRHashTableUninit
0x1800346e8  xor     ecx, ecx; int
0x1800346ea  call    ?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z; ALLOC_CACHE_HANDLER::Cleanup(int)
0x1800346ef  cmp     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x1800346f6  jz      short loc_18003470F
0x1800346f8  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800346ff  call    cs:__imp_DeleteCriticalSection
0x180034705  mov     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x18003470f  lea     rcx, CriticalSection; lpCriticalSection
0x180034716  call    cs:__imp_DeleteCriticalSection
0x18003471c  mov     cs:dword_18006000C, 0
0x180034726  add     rsp, 38h
0x18003472a  retn
```

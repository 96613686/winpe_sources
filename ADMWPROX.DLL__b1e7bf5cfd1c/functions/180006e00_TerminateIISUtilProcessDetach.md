# TerminateIISUtilProcessDetach

- ea: `0x180006e00`
- end: `0x180006ebf`
- name: `TerminateIISUtilProcessDetach`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002400`
- `0x180006bcc`

## callees

- `0x180006e00`
- `0x180007234`
- `0x1800076b4`
- `0x180007e44`
- `0x180007f80`
- `0x1800080ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006e93`
- `KERNEL32!DeleteCriticalSection` at `0x180006eaa`
- `KERNEL32!DeleteCriticalSection` at `0x180006e93`
- `KERNEL32!DeleteCriticalSection` at `0x180006eaa`

## string_xrefs

- `0x180006e38`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

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
  if ( dword_180010134 != 2 )
  {
    switch ( dword_180010134 )
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
        ALLOC_CACHE_HANDLER::Cleanup(0);
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
  dword_180010134 = 0;
}

```

## disassembly

```asm
0x180006e00  sub     rsp, 38h
0x180006e04  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180006e0a  test    al, 3
0x180006e0c  setnz   cl
0x180006e0f  test    al, 4
0x180006e11  setnz   al
0x180006e14  test    al, cl
0x180006e16  jz      short loc_180006E44
0x180006e18  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006e1f  lea     rax, aTerminateiisut; "TerminateIISUtilProcessDetach\n"
0x180006e26  lea     r9, aTerminateiisut_0; "TerminateIISUtilProcessDetach"
0x180006e2d  mov     [rsp+38h+var_18], rax; char *
0x180006e32  mov     r8d, 0E0h; unsigned int
0x180006e38  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006e3f  call    PuDbgPrint
0x180006e44  mov     ecx, cs:dword_180010134
0x180006e4a  sub     ecx, 2
0x180006e4d  jz      short loc_180006EB0
0x180006e4f  sub     ecx, 1
0x180006e52  jz      short loc_180006EA3
0x180006e54  sub     ecx, 2
0x180006e57  jz      short loc_180006E83
0x180006e59  sub     ecx, 1
0x180006e5c  jz      short loc_180006E7C
0x180006e5e  sub     ecx, 1
0x180006e61  jz      short loc_180006E77
0x180006e63  sub     ecx, 1
0x180006e66  jz      short loc_180006E72
0x180006e68  cmp     ecx, 1
0x180006e6b  jnz     short loc_180006EB0
0x180006e6d  call    ?Terminate@EVENT_LOG@@SAXXZ; EVENT_LOG::Terminate(void)
0x180006e72  call    ?TerminateStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::TerminateStatic(void)
0x180006e77  call    LKRHashTableUninit
0x180006e7c  xor     ecx, ecx; int
0x180006e7e  call    ?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z; ALLOC_CACHE_HANDLER::Cleanup(int)
0x180006e83  cmp     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x180006e8a  jz      short loc_180006EA3
0x180006e8c  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006e93  call    cs:__imp_DeleteCriticalSection
0x180006e99  mov     cs:?g_fInitCsTimerWrap@@3HA, 0; int g_fInitCsTimerWrap
0x180006ea3  lea     rcx, CriticalSection; lpCriticalSection
0x180006eaa  call    cs:__imp_DeleteCriticalSection
0x180006eb0  mov     cs:dword_180010134, 0
0x180006eba  add     rsp, 38h
0x180006ebe  retn
```

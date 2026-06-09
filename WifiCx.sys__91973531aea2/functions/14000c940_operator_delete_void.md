# operator delete(void *)

- ea: `0x14000c940`
- end: `0x14000c9ce`
- name: `??3@YAXPEAX@Z`
- size: `142`
- prototype: `void __fastcall(void *)`
- caller_count: `300`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140002df8`
- `0x14000a390`
- `0x14000ab40`
- `0x14000b640`
- `0x14000c110`
- `0x14000c864`
- `0x14000c9e0`
- `0x14000cc50`
- `0x14000d120`
- `0x14000ffd0`
- `0x140012f80`
- `0x140013920`
- `0x140013ca0`
- `0x140014344`
- `0x140015ac0`
- `0x140017524`
- `0x1400183f4`
- `0x1400188c0`
- `0x14001a844`
- `0x14001a8c0`
- `0x14001b910`
- `0x14001bf50`
- `0x14001d420`
- `0x14001d690`
- `0x14001d7f0`
- `0x14001e430`
- `0x14001ec8c`
- `0x14001fa34`
- `0x140020a10`
- `0x140022970`
- `0x140022c50`
- `0x140022db4`
- `0x140024230`
- `0x1400245e4`
- `0x140024f60`
- `0x1400257a0`
- `0x140026010`
- `0x14002afb4`
- `0x14002b0b4`
- `0x14002b148`
- `0x14002e080`
- `0x14002ec58`
- `0x14002ee90`
- `0x14002f0a4`
- `0x140030b60`
- `0x140030d88`
- `0x140032d30`
- `0x140032f4c`
- `0x140033378`
- `0x140034a50`

## callees

- `0x14000c940`
- `0x14000d054`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9bc`

## pseudocode

```c
void __fastcall operator delete(_QWORD *a1)
{
  if ( g_Feature_56544556_MoveToWDFMemory_IsEnabled )
  {
    if ( a1 )
    {
      if ( (unsigned __int64)a1 < 0x10 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            1,
            13,
            (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
      }
      else
      {
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, *(a1 - 1));
      }
    }
  }
  else if ( a1 )
  {
    ExFreePoolWithTag(a1, 0x47696457u);
  }
}

```

## disassembly

```asm
0x14000c940  sub     rsp, 38h
0x14000c944  cmp     cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA, 0; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14000c94b  jz      short loc_14000C9B2
0x14000c94d  test    rcx, rcx
0x14000c950  jz      short loc_14000C9C8
0x14000c952  cmp     rcx, 10h
0x14000c956  jb      short loc_14000C978
0x14000c958  mov     rax, cs:WdfFunctions_01031
0x14000c95f  mov     rdx, [rcx-8]
0x14000c963  mov     rcx, cs:WdfDriverGlobals
0x14000c96a  mov     rax, [rax+680h]
0x14000c971  call    _guard_dispatch_icall
0x14000c976  jmp     short loc_14000C9C8
0x14000c978  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c97f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c986  jz      short loc_14000C9C8
0x14000c988  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c98f  lea     rax, WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids
0x14000c996  mov     r9d, 0Dh
0x14000c99c  mov     [rsp+38h+var_18], rax
0x14000c9a1  mov     dl, 2
0x14000c9a3  mov     rcx, [rcx+40h]
0x14000c9a7  lea     r8d, [r9-0Ch]
0x14000c9ab  call    WPP_RECORDER_SF_
0x14000c9b0  jmp     short loc_14000C9C8
0x14000c9b2  test    rcx, rcx
0x14000c9b5  jz      short loc_14000C9C8
0x14000c9b7  mov     edx, 47696457h; Tag
0x14000c9bc  call    cs:__imp_ExFreePoolWithTag
0x14000c9c3  nop     dword ptr [rax+rax+00h]
0x14000c9c8  add     rsp, 38h
0x14000c9cc  retn
```

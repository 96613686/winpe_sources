# _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)

- ea: `0x180005620`
- end: `0x180005650`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180005574`
- `0x1800061ac`
- `0x180006350`
- `0x180006598`
- `0x1800084c4`
- `0x180008798`
- `0x18000891c`

## callees

- `0x180004c64`
- `0x180005620`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(
        _DWORD *a1)
{
  __int64 result; // rax

  if ( *a1 == 1 )
  {
    *a1 = 2;
    result = _tlgWriteActivityAutoStop<768,4>((unsigned int *)&dword_18001C010);
  }
  *a1 = 3;
  return result;
}

```

## disassembly

```asm
0x180005620  push    rbx
0x180005622  sub     rsp, 20h
0x180005626  cmp     dword ptr [rcx], 1
0x180005629  mov     rbx, rcx
0x18000562c  jnz     short loc_180005644
0x18000562e  mov     dword ptr [rcx], 2
0x180005634  lea     rdx, [rcx+8]
0x180005638  lea     rcx, dword_18001C010
0x18000563f  call    ??$_tlgWriteActivityAutoStop@$0DAA@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<768,4>(_tlgProvider_t const *,_GUID const *)
0x180005644  mov     dword ptr [rbx], 3
0x18000564a  add     rsp, 20h
0x18000564e  pop     rbx
0x18000564f  retn
```

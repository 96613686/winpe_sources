# _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)

- ea: `0x18000ad28`
- end: `0x18000ad75`
- name: `?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ`
- size: `77`
- prototype: `ULONG __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061ac`
- `0x180006350`
- `0x180006598`
- `0x1800084c4`
- `0x180008798`
- `0x18000891c`

## callees

- `0x1800012f0`
- `0x18000ad28`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ad5a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ad5a`

## pseudocode

```c
ULONG __fastcall _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(
        __int64 a1)
{
  ULONG result; // eax

  result = dword_18001C010;
  if ( (unsigned int)dword_18001C010 > 4 && (result = tlgKeywordOn(&dword_18001C010, 768), (_BYTE)result) )
    result = EventActivityIdControl(3u, (LPGUID)(a1 + 8));
  else
    *(_OWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 1;
  return result;
}

```

## disassembly

```asm
0x18000ad28  push    rbx
0x18000ad2a  sub     rsp, 20h
0x18000ad2e  mov     eax, cs:dword_18001C010
0x18000ad34  mov     rbx, rcx
0x18000ad37  cmp     eax, 4
0x18000ad3a  jbe     short loc_18000AD62
0x18000ad3c  mov     edx, 300h
0x18000ad41  lea     rcx, dword_18001C010
0x18000ad48  call    _tlgKeywordOn
0x18000ad4d  test    al, al
0x18000ad4f  jz      short loc_18000AD62
0x18000ad51  lea     rdx, [rbx+8]; ActivityId
0x18000ad55  mov     ecx, 3; ControlCode
0x18000ad5a  call    cs:__imp_EventActivityIdControl
0x18000ad60  jmp     short loc_18000AD69
0x18000ad62  xorps   xmm0, xmm0
0x18000ad65  movups  xmmword ptr [rbx+8], xmm0
0x18000ad69  mov     dword ptr [rbx], 1
0x18000ad6f  add     rsp, 20h
0x18000ad73  pop     rbx
0x18000ad74  retn
```

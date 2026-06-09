# AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x180025724`
- end: `0x18002579d`
- name: `?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `121`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b828`
- `0x18003d3d0`
- `0x18003da80`

## callees

- `0x180025724`
- `0x180042950`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002577a`
- `ntdll!EtwEventWrite` at `0x18002577a`

## pseudocode

```c
__int64 __fastcall AiLogPerfTrackEvent(const struct _EVENT_DESCRIPTOR *a1)
{
  __int64 result; // rax
  unsigned int v2; // [rsp+20h] [rbp-28h] BYREF
  unsigned int *v3; // [rsp+28h] [rbp-20h] BYREF
  int v4; // [rsp+30h] [rbp-18h]
  int v5; // [rsp+34h] [rbp-14h]

  v5 = 0;
  result = (unsigned int)_InterlockedIncrement(&g_ulPerfTrackId);
  v3 = &v2;
  v2 = result;
  v4 = 4;
  if ( g_EventRegHandleLua )
  {
    EtwEventWrite(g_EventRegHandleLua, a1, 1, &v3);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180025724  sub     rsp, 48h
0x180025728  mov     rax, cs:__security_cookie
0x18002572f  xor     rax, rsp
0x180025732  mov     [rsp+48h+var_10], rax
0x180025737  mov     r8d, 1
0x18002573d  mov     rdx, rcx
0x180025740  mov     eax, r8d
0x180025743  lock xadd cs:?g_ulPerfTrackId@@3JC, eax; long volatile g_ulPerfTrackId
0x18002574b  and     [rsp+48h+var_14], 0
0x180025750  lea     rcx, [rsp+48h+var_28]
0x180025755  add     eax, r8d
0x180025758  mov     [rsp+48h+var_20], rcx
0x18002575d  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x180025764  mov     [rsp+48h+var_28], eax
0x180025768  mov     [rsp+48h+var_18], 4
0x180025770  test    rcx, rcx
0x180025773  jz      short loc_18002578A
0x180025775  lea     r9, [rsp+48h+var_20]
0x18002577a  call    cs:__imp_EtwEventWrite
0x180025781  nop     dword ptr [rax+rax+00h]
0x180025786  mov     eax, [rsp+48h+var_28]
0x18002578a  mov     rcx, [rsp+48h+var_10]
0x18002578f  xor     rcx, rsp; StackCookie
0x180025792  call    __security_check_cookie
0x180025797  add     rsp, 48h
0x18002579b  retn
```

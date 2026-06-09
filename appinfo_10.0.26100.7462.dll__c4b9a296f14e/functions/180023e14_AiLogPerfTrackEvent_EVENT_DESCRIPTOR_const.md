# AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x180023e14`
- end: `0x180023e8d`
- name: `?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `121`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a2a8`
- `0x18003f4e0`
- `0x18003fb90`

## callees

- `0x180023e14`
- `0x180044a20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180023e6a`
- `ntdll!EtwEventWrite` at `0x180023e6a`

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
0x180023e14  sub     rsp, 48h
0x180023e18  mov     rax, cs:__security_cookie
0x180023e1f  xor     rax, rsp
0x180023e22  mov     [rsp+48h+var_10], rax
0x180023e27  mov     r8d, 1
0x180023e2d  mov     rdx, rcx
0x180023e30  mov     eax, r8d
0x180023e33  lock xadd cs:?g_ulPerfTrackId@@3JC, eax; long volatile g_ulPerfTrackId
0x180023e3b  and     [rsp+48h+var_14], 0
0x180023e40  lea     rcx, [rsp+48h+var_28]
0x180023e45  add     eax, r8d
0x180023e48  mov     [rsp+48h+var_20], rcx
0x180023e4d  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x180023e54  mov     [rsp+48h+var_28], eax
0x180023e58  mov     [rsp+48h+var_18], 4
0x180023e60  test    rcx, rcx
0x180023e63  jz      short loc_180023E7A
0x180023e65  lea     r9, [rsp+48h+var_20]
0x180023e6a  call    cs:__imp_EtwEventWrite
0x180023e71  nop     dword ptr [rax+rax+00h]
0x180023e76  mov     eax, [rsp+48h+var_28]
0x180023e7a  mov     rcx, [rsp+48h+var_10]
0x180023e7f  xor     rcx, rsp; StackCookie
0x180023e82  call    __security_check_cookie
0x180023e87  add     rsp, 48h
0x180023e8b  retn
```

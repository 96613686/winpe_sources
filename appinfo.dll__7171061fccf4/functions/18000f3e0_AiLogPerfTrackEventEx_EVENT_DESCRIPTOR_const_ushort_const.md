# AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)

- ea: `0x18000f3e0`
- end: `0x18000f48e`
- name: `?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `174`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003d070`
- `0x180041700`
- `0x180041dc0`

## callees

- `0x18000f3e0`
- `0x180046e50`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000f45d`
- `ntdll!EtwEventWrite` at `0x18000f45d`

## pseudocode

```c
__int64 __fastcall AiLogPerfTrackEventEx(const struct _EVENT_DESCRIPTOR *a1, const unsigned __int16 *a2)
{
  unsigned __int32 v2; // r8d
  __int64 v3; // rax
  unsigned __int32 v5; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v6[3]; // [rsp+28h] [rbp-30h] BYREF
  int v7; // [rsp+40h] [rbp-18h]
  int v8; // [rsp+44h] [rbp-14h]

  v6[1] = 4;
  v2 = _InterlockedIncrement(&g_ulPerfTrackId);
  v6[0] = &v5;
  v3 = -1;
  v5 = v2;
  v6[2] = a2;
  do
    ++v3;
  while ( a2[v3] );
  v8 = 0;
  v7 = 2 * v3;
  if ( !g_EventRegHandleLua )
    return v2;
  EtwEventWrite(g_EventRegHandleLua, a1, 2, v6);
  return v5;
}

```

## disassembly

```asm
0x18000f3e0  sub     rsp, 58h
0x18000f3e4  mov     rax, cs:__security_cookie
0x18000f3eb  xor     rax, rsp
0x18000f3ee  mov     [rsp+58h+var_10], rax
0x18000f3f3  mov     r10, rcx
0x18000f3f6  mov     r8d, 1
0x18000f3fc  lock xadd cs:?g_ulPerfTrackId@@3JC, r8d; long volatile g_ulPerfTrackId
0x18000f405  lea     rax, [rsp+58h+var_38]
0x18000f40a  mov     [rsp+58h+var_28], 4
0x18000f413  inc     r8d
0x18000f416  mov     [rsp+58h+var_30], rax
0x18000f41b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f422  mov     [rsp+58h+var_38], r8d
0x18000f427  xor     ecx, ecx
0x18000f429  mov     [rsp+58h+var_20], rdx
0x18000f42e  xchg    ax, ax
0x18000f430  inc     rax
0x18000f433  cmp     [rdx+rax*2], cx
0x18000f437  jnz     short loc_18000F430
0x18000f439  add     eax, eax
0x18000f43b  mov     [rsp+58h+var_14], ecx
0x18000f43f  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x18000f446  mov     [rsp+58h+var_18], eax
0x18000f44a  test    rcx, rcx
0x18000f44d  jz      short loc_18000F479
0x18000f44f  lea     r9, [rsp+58h+var_30]
0x18000f454  mov     r8d, 2
0x18000f45a  mov     rdx, r10
0x18000f45d  call    cs:__imp_EtwEventWrite
0x18000f463  mov     eax, [rsp+58h+var_38]
0x18000f467  mov     rcx, [rsp+58h+var_10]
0x18000f46c  xor     rcx, rsp; StackCookie
0x18000f46f  call    __security_check_cookie
0x18000f474  add     rsp, 58h
0x18000f478  retn
0x18000f479  mov     eax, r8d
0x18000f47c  mov     rcx, [rsp+58h+var_10]
0x18000f481  xor     rcx, rsp; StackCookie
0x18000f484  call    __security_check_cookie
0x18000f489  add     rsp, 58h
0x18000f48d  retn
```

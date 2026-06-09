# AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)

- ea: `0x18000f190`
- end: `0x18000f246`
- name: `?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `182`
- prototype: `unsigned int __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003a8b0`
- `0x18003eaa0`
- `0x18003f160`

## callees

- `0x18000f190`
- `0x1800444e0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000f20d`
- `ntdll!EtwEventWrite` at `0x18000f20d`

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
0x18000f190  sub     rsp, 58h
0x18000f194  mov     rax, cs:__security_cookie
0x18000f19b  xor     rax, rsp
0x18000f19e  mov     [rsp+58h+var_10], rax
0x18000f1a3  mov     r10, rcx
0x18000f1a6  mov     r8d, 1
0x18000f1ac  lock xadd cs:?g_ulPerfTrackId@@3JC, r8d; long volatile g_ulPerfTrackId
0x18000f1b5  lea     rax, [rsp+58h+var_38]
0x18000f1ba  mov     [rsp+58h+var_28], 4
0x18000f1c3  inc     r8d
0x18000f1c6  mov     [rsp+58h+var_30], rax
0x18000f1cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f1d2  mov     [rsp+58h+var_38], r8d
0x18000f1d7  xor     ecx, ecx
0x18000f1d9  mov     [rsp+58h+var_20], rdx
0x18000f1de  xchg    ax, ax
0x18000f1e0  inc     rax
0x18000f1e3  cmp     [rdx+rax*2], cx
0x18000f1e7  jnz     short loc_18000F1E0
0x18000f1e9  add     eax, eax
0x18000f1eb  mov     [rsp+58h+var_14], ecx
0x18000f1ef  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x18000f1f6  mov     [rsp+58h+var_18], eax
0x18000f1fa  test    rcx, rcx
0x18000f1fd  jz      short loc_18000F230
0x18000f1ff  lea     r9, [rsp+58h+var_30]
0x18000f204  mov     r8d, 2
0x18000f20a  mov     rdx, r10
0x18000f20d  call    cs:__imp_EtwEventWrite
0x18000f214  nop     dword ptr [rax+rax+00h]
0x18000f219  mov     eax, [rsp+58h+var_38]
0x18000f21d  mov     rcx, [rsp+58h+var_10]
0x18000f222  xor     rcx, rsp; StackCookie
0x18000f225  call    __security_check_cookie
0x18000f22a  add     rsp, 58h
0x18000f22e  retn
0x18000f230  mov     eax, r8d
0x18000f233  mov     rcx, [rsp+58h+var_10]
0x18000f238  xor     rcx, rsp; StackCookie
0x18000f23b  call    __security_check_cookie
0x18000f240  add     rsp, 58h
0x18000f244  retn
```

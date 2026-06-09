# CGroupPolicy::StartProcessGPSettings(void)

- ea: `0x1800038d0`
- end: `0x180003974`
- name: `?StartProcessGPSettings@CGroupPolicy@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800018c0`
- `0x1800031b0`

## callees

- `0x1800038d0`
- `0x180007f28`
- `0x18000e1b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003965`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180003965`

## pseudocode

```c
void __fastcall CGroupPolicy::StartProcessGPSettings(CGroupPolicy *this)
{
  CGroupPolicy *v1; // rsi
  signed __int32 v2; // edi
  signed __int32 v3; // ebx

  v1 = g_GroupPolicy;
  v2 = _InterlockedExchangeAdd(&g_RefCount, 1u);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
      (unsigned int)(v2 + 1));
  }
  v3 = _InterlockedIncrement((volatile signed __int32 *)v1);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids,
      (unsigned int)(v2 + 1),
      v3);
  }
  if ( v3 == 1 )
    SubmitThreadpoolWork(*((PTP_WORK *)v1 + 5));
}

```

## disassembly

```asm
0x1800038d0  push    rbx
0x1800038d2  push    rbp
0x1800038d3  push    rsi
0x1800038d4  push    rdi
0x1800038d5  sub     rsp, 38h
0x1800038d9  mov     rsi, cs:?g_GroupPolicy@@3PEAVCGroupPolicy@@EA; CGroupPolicy * g_GroupPolicy
0x1800038e0  mov     ebx, 1
0x1800038e5  mov     edi, ebx
0x1800038e7  lock xadd cs:?g_RefCount@@3JA, edi; long g_RefCount
0x1800038ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f6  lea     rbp, WPP_GLOBAL_Control
0x1800038fd  cmp     rcx, rbp
0x180003900  jz      short loc_180003924
0x180003902  test    dword ptr [rcx+1Ch], 200h
0x180003909  jz      short loc_180003924
0x18000390b  mov     rcx, [rcx+10h]
0x18000390f  lea     r9d, [rdi+1]
0x180003913  mov     edx, 12h
0x180003918  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x18000391f  call    WPP_SF_d
0x180003924  lock xadd [rsi], ebx
0x180003928  inc     ebx
0x18000392a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003931  cmp     rcx, rbp
0x180003934  jz      short loc_18000395C
0x180003936  test    dword ptr [rcx+1Ch], 200h
0x18000393d  jz      short loc_18000395C
0x18000393f  mov     rcx, [rcx+10h]
0x180003943  lea     r9d, [rdi+1]
0x180003947  mov     edx, 0Dh
0x18000394c  mov     [rsp+58h+var_38], ebx
0x180003950  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180003957  call    WPP_SF_dd
0x18000395c  cmp     ebx, 1
0x18000395f  jnz     short loc_18000396B
0x180003961  mov     rcx, [rsi+28h]; pwk
0x180003965  call    cs:__imp_SubmitThreadpoolWork
0x18000396b  add     rsp, 38h
0x18000396f  pop     rdi
0x180003970  pop     rsi
0x180003971  pop     rbp
0x180003972  pop     rbx
0x180003973  retn
```

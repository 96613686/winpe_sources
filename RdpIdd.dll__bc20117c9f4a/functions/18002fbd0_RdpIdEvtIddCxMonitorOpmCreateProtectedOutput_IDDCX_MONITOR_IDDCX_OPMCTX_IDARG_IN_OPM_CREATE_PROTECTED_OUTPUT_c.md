# RdpIdEvtIddCxMonitorOpmCreateProtectedOutput(IDDCX_MONITOR__ *,IDDCX_OPMCTX__ *,IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT const *)

- ea: `0x18002fbd0`
- end: `0x18002fcd9`
- name: `?RdpIdEvtIddCxMonitorOpmCreateProtectedOutput@@YAJPEAUIDDCX_MONITOR__@@PEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_CREATE_PROTECTED_OUTPUT@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_MONITOR__ *, struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18002fbd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fc91`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOpmCreateProtectedOutput(
        struct IDDCX_MONITOR__ *a1,
        struct IDDCX_OPMCTX__ *a2,
        const struct IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT *a3)
{
  PVOID *v3; // rax
  char v4; // bl
  bool v5; // di
  _UNKNOWN **v6; // rcx
  bool v7; // si
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+28h] [rbp-60h]

  v3 = (PVOID *)WPP_GLOBAL_Control;
  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      14,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      CurrentThreadId);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    v6 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v3 == &WPP_GLOBAL_Control || (*((_BYTE *)v3 + 28) & 1) == 0 || *((_BYTE *)v3 + 25) < 4u )
    v4 = 0;
  v11 = v6 != &WPP_RECORDER_INITIALIZED;
  if ( v4 || v6 != &WPP_RECORDER_INITIALIZED )
  {
    v12 = GetCurrentThreadId();
    LOBYTE(v13) = v11;
    LOBYTE(v14) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      15,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v12);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002fbd0  push    rbx
0x18002fbd2  push    rbp
0x18002fbd3  push    rsi
0x18002fbd4  push    rdi
0x18002fbd5  push    r14
0x18002fbd7  push    r15
0x18002fbd9  sub     rsp, 58h
0x18002fbdd  mov     rax, cs:WPP_GLOBAL_Control
0x18002fbe4  lea     rbp, WPP_GLOBAL_Control
0x18002fbeb  mov     bl, 1
0x18002fbed  cmp     rax, rbp
0x18002fbf0  jz      short loc_18002FC02
0x18002fbf2  test    [rax+1Ch], bl
0x18002fbf5  jz      short loc_18002FC02
0x18002fbf7  cmp     byte ptr [rax+19h], 4
0x18002fbfb  jb      short loc_18002FC02
0x18002fbfd  mov     dil, bl
0x18002fc00  jmp     short loc_18002FC05
0x18002fc02  xor     dil, dil
0x18002fc05  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fc0c  lea     r14, WPP_RECORDER_INITIALIZED
0x18002fc13  cmp     rcx, r14
0x18002fc16  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002fc1d  setnz   sil
0x18002fc21  test    dil, dil
0x18002fc24  jnz     short loc_18002FC2B
0x18002fc26  test    sil, sil
0x18002fc29  jz      short loc_18002FC6F
0x18002fc2b  call    cs:__imp_GetCurrentThreadId
0x18002fc32  nop     dword ptr [rax+rax+00h]
0x18002fc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc3e  mov     r8b, sil; int
0x18002fc41  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fc45  mov     dl, dil; int
0x18002fc48  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fc4d  mov     [rsp+88h+var_58], 0Eh; __int16
0x18002fc54  mov     r9, [rcx+28h]; int
0x18002fc58  mov     rcx, [rcx+10h]; int
0x18002fc5c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fc61  mov     rax, cs:WPP_GLOBAL_Control
0x18002fc68  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fc6f  cmp     rax, rbp
0x18002fc72  jz      short loc_18002FC7F
0x18002fc74  test    [rax+1Ch], bl
0x18002fc77  jz      short loc_18002FC7F
0x18002fc79  cmp     byte ptr [rax+19h], 4
0x18002fc7d  jnb     short loc_18002FC81
0x18002fc7f  xor     bl, bl
0x18002fc81  cmp     rcx, r14
0x18002fc84  setnz   dil
0x18002fc88  test    bl, bl
0x18002fc8a  jnz     short loc_18002FC91
0x18002fc8c  test    dil, dil
0x18002fc8f  jz      short loc_18002FCC6
0x18002fc91  call    cs:__imp_GetCurrentThreadId
0x18002fc98  nop     dword ptr [rax+rax+00h]
0x18002fc9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fca4  mov     r8b, dil; int
0x18002fca7  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fcab  mov     dl, bl; int
0x18002fcad  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fcb2  mov     [rsp+88h+var_58], 0Fh; __int16
0x18002fcb9  mov     r9, [rcx+28h]; int
0x18002fcbd  mov     rcx, [rcx+10h]; int
0x18002fcc1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fcc6  mov     eax, 0C0000002h
0x18002fccb  add     rsp, 58h
0x18002fccf  pop     r15
0x18002fcd1  pop     r14
0x18002fcd3  pop     rdi
0x18002fcd4  pop     rsi
0x18002fcd5  pop     rbp
0x18002fcd6  pop     rbx
0x18002fcd7  retn
```

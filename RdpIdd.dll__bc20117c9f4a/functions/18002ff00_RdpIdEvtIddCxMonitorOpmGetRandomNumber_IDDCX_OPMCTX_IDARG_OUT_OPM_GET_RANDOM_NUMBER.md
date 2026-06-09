# RdpIdEvtIddCxMonitorOpmGetRandomNumber(IDDCX_OPMCTX__ *,IDARG_OUT_OPM_GET_RANDOM_NUMBER *)

- ea: `0x18002ff00`
- end: `0x180030009`
- name: `?RdpIdEvtIddCxMonitorOpmGetRandomNumber@@YAJPEAUIDDCX_OPMCTX__@@PEAUIDARG_OUT_OPM_GET_RANDOM_NUMBER@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_OPMCTX__ *, struct IDARG_OUT_OPM_GET_RANDOM_NUMBER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18002ff00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ff5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ffc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ff5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ffc1`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOpmGetRandomNumber(
        struct IDDCX_OPMCTX__ *a1,
        struct IDARG_OUT_OPM_GET_RANDOM_NUMBER *a2)
{
  PVOID *v2; // rax
  char v3; // bl
  bool v4; // di
  _UNKNOWN **v5; // rcx
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  bool v10; // di
  char v11; // al
  int v12; // r8d
  int v13; // edx
  int v15; // [rsp+20h] [rbp-68h]
  int v16; // [rsp+28h] [rbp-60h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      16,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      CurrentThreadId);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 1) == 0 || *((_BYTE *)v2 + 25) < 4u )
    v3 = 0;
  v10 = v5 != &WPP_RECORDER_INITIALIZED;
  if ( v3 || v5 != &WPP_RECORDER_INITIALIZED )
  {
    v11 = GetCurrentThreadId();
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      17,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v11);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002ff00  push    rbx
0x18002ff02  push    rbp
0x18002ff03  push    rsi
0x18002ff04  push    rdi
0x18002ff05  push    r14
0x18002ff07  push    r15
0x18002ff09  sub     rsp, 58h
0x18002ff0d  mov     rax, cs:WPP_GLOBAL_Control
0x18002ff14  lea     rbp, WPP_GLOBAL_Control
0x18002ff1b  mov     bl, 1
0x18002ff1d  cmp     rax, rbp
0x18002ff20  jz      short loc_18002FF32
0x18002ff22  test    [rax+1Ch], bl
0x18002ff25  jz      short loc_18002FF32
0x18002ff27  cmp     byte ptr [rax+19h], 4
0x18002ff2b  jb      short loc_18002FF32
0x18002ff2d  mov     dil, bl
0x18002ff30  jmp     short loc_18002FF35
0x18002ff32  xor     dil, dil
0x18002ff35  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002ff3c  lea     r14, WPP_RECORDER_INITIALIZED
0x18002ff43  cmp     rcx, r14
0x18002ff46  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002ff4d  setnz   sil
0x18002ff51  test    dil, dil
0x18002ff54  jnz     short loc_18002FF5B
0x18002ff56  test    sil, sil
0x18002ff59  jz      short loc_18002FF9F
0x18002ff5b  call    cs:__imp_GetCurrentThreadId
0x18002ff62  nop     dword ptr [rax+rax+00h]
0x18002ff67  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff6e  mov     r8b, sil; int
0x18002ff71  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002ff75  mov     dl, dil; int
0x18002ff78  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002ff7d  mov     [rsp+88h+var_58], 10h; __int16
0x18002ff84  mov     r9, [rcx+28h]; int
0x18002ff88  mov     rcx, [rcx+10h]; int
0x18002ff8c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002ff91  mov     rax, cs:WPP_GLOBAL_Control
0x18002ff98  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002ff9f  cmp     rax, rbp
0x18002ffa2  jz      short loc_18002FFAF
0x18002ffa4  test    [rax+1Ch], bl
0x18002ffa7  jz      short loc_18002FFAF
0x18002ffa9  cmp     byte ptr [rax+19h], 4
0x18002ffad  jnb     short loc_18002FFB1
0x18002ffaf  xor     bl, bl
0x18002ffb1  cmp     rcx, r14
0x18002ffb4  setnz   dil
0x18002ffb8  test    bl, bl
0x18002ffba  jnz     short loc_18002FFC1
0x18002ffbc  test    dil, dil
0x18002ffbf  jz      short loc_18002FFF6
0x18002ffc1  call    cs:__imp_GetCurrentThreadId
0x18002ffc8  nop     dword ptr [rax+rax+00h]
0x18002ffcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffd4  mov     r8b, dil; int
0x18002ffd7  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002ffdb  mov     dl, bl; int
0x18002ffdd  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002ffe2  mov     [rsp+88h+var_58], 11h; __int16
0x18002ffe9  mov     r9, [rcx+28h]; int
0x18002ffed  mov     rcx, [rcx+10h]; int
0x18002fff1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fff6  mov     eax, 0C0000002h
0x18002fffb  add     rsp, 58h
0x18002ffff  pop     r15
0x180030001  pop     r14
0x180030003  pop     rdi
0x180030004  pop     rsi
0x180030005  pop     rbp
0x180030006  pop     rbx
0x180030007  retn
```

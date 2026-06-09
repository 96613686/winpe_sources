# RdpIdEvtIddCxMonitorOPMGetInformation(IDDCX_OPMCTX__ *,IDARG_IN_OPM_GET_INFOMATION const *,IDARG_OUT_OPM_GET_INFOMATION *)

- ea: `0x18002fac0`
- end: `0x18002fbc9`
- name: `?RdpIdEvtIddCxMonitorOPMGetInformation@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_GET_INFOMATION@@PEAUIDARG_OUT_OPM_GET_INFOMATION@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_GET_INFOMATION *, struct IDARG_OUT_OPM_GET_INFOMATION *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18002fac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fb1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fb81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fb1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fb81`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOPMGetInformation(
        struct IDDCX_OPMCTX__ *a1,
        const struct IDARG_IN_OPM_GET_INFOMATION *a2,
        struct IDARG_OUT_OPM_GET_INFOMATION *a3)
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
      20,
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
      21,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v12);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002fac0  push    rbx
0x18002fac2  push    rbp
0x18002fac3  push    rsi
0x18002fac4  push    rdi
0x18002fac5  push    r14
0x18002fac7  push    r15
0x18002fac9  sub     rsp, 58h
0x18002facd  mov     rax, cs:WPP_GLOBAL_Control
0x18002fad4  lea     rbp, WPP_GLOBAL_Control
0x18002fadb  mov     bl, 1
0x18002fadd  cmp     rax, rbp
0x18002fae0  jz      short loc_18002FAF2
0x18002fae2  test    [rax+1Ch], bl
0x18002fae5  jz      short loc_18002FAF2
0x18002fae7  cmp     byte ptr [rax+19h], 4
0x18002faeb  jb      short loc_18002FAF2
0x18002faed  mov     dil, bl
0x18002faf0  jmp     short loc_18002FAF5
0x18002faf2  xor     dil, dil
0x18002faf5  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fafc  lea     r14, WPP_RECORDER_INITIALIZED
0x18002fb03  cmp     rcx, r14
0x18002fb06  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002fb0d  setnz   sil
0x18002fb11  test    dil, dil
0x18002fb14  jnz     short loc_18002FB1B
0x18002fb16  test    sil, sil
0x18002fb19  jz      short loc_18002FB5F
0x18002fb1b  call    cs:__imp_GetCurrentThreadId
0x18002fb22  nop     dword ptr [rax+rax+00h]
0x18002fb27  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb2e  mov     r8b, sil; int
0x18002fb31  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fb35  mov     dl, dil; int
0x18002fb38  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fb3d  mov     [rsp+88h+var_58], 14h; __int16
0x18002fb44  mov     r9, [rcx+28h]; int
0x18002fb48  mov     rcx, [rcx+10h]; int
0x18002fb4c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fb51  mov     rax, cs:WPP_GLOBAL_Control
0x18002fb58  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fb5f  cmp     rax, rbp
0x18002fb62  jz      short loc_18002FB6F
0x18002fb64  test    [rax+1Ch], bl
0x18002fb67  jz      short loc_18002FB6F
0x18002fb69  cmp     byte ptr [rax+19h], 4
0x18002fb6d  jnb     short loc_18002FB71
0x18002fb6f  xor     bl, bl
0x18002fb71  cmp     rcx, r14
0x18002fb74  setnz   dil
0x18002fb78  test    bl, bl
0x18002fb7a  jnz     short loc_18002FB81
0x18002fb7c  test    dil, dil
0x18002fb7f  jz      short loc_18002FBB6
0x18002fb81  call    cs:__imp_GetCurrentThreadId
0x18002fb88  nop     dword ptr [rax+rax+00h]
0x18002fb8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb94  mov     r8b, dil; int
0x18002fb97  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fb9b  mov     dl, bl; int
0x18002fb9d  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fba2  mov     [rsp+88h+var_58], 15h; __int16
0x18002fba9  mov     r9, [rcx+28h]; int
0x18002fbad  mov     rcx, [rcx+10h]; int
0x18002fbb1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fbb6  mov     eax, 0C0000002h
0x18002fbbb  add     rsp, 58h
0x18002fbbf  pop     r15
0x18002fbc1  pop     r14
0x18002fbc3  pop     rdi
0x18002fbc4  pop     rsi
0x18002fbc5  pop     rbp
0x18002fbc6  pop     rbx
0x18002fbc7  retn
```

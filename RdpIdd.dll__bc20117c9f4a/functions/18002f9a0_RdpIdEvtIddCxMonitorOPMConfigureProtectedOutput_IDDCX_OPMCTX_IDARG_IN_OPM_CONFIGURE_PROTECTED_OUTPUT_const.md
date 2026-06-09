# RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput(IDDCX_OPMCTX__ *,IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT const *)

- ea: `0x18002f9a0`
- end: `0x18002faa9`
- name: `?RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000dbd8`
- `0x18002f9a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fa61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fa61`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOPMConfigureProtectedOutput(
        struct IDDCX_OPMCTX__ *a1,
        const struct IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT *a2)
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
      22,
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
      23,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v11);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002f9a0  push    rbx
0x18002f9a2  push    rbp
0x18002f9a3  push    rsi
0x18002f9a4  push    rdi
0x18002f9a5  push    r14
0x18002f9a7  push    r15
0x18002f9a9  sub     rsp, 58h
0x18002f9ad  mov     rax, cs:WPP_GLOBAL_Control
0x18002f9b4  lea     rbp, WPP_GLOBAL_Control
0x18002f9bb  mov     bl, 1
0x18002f9bd  cmp     rax, rbp
0x18002f9c0  jz      short loc_18002F9D2
0x18002f9c2  test    [rax+1Ch], bl
0x18002f9c5  jz      short loc_18002F9D2
0x18002f9c7  cmp     byte ptr [rax+19h], 4
0x18002f9cb  jb      short loc_18002F9D2
0x18002f9cd  mov     dil, bl
0x18002f9d0  jmp     short loc_18002F9D5
0x18002f9d2  xor     dil, dil
0x18002f9d5  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002f9dc  lea     r14, WPP_RECORDER_INITIALIZED
0x18002f9e3  cmp     rcx, r14
0x18002f9e6  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002f9ed  setnz   sil
0x18002f9f1  test    dil, dil
0x18002f9f4  jnz     short loc_18002F9FB
0x18002f9f6  test    sil, sil
0x18002f9f9  jz      short loc_18002FA3F
0x18002f9fb  call    cs:__imp_GetCurrentThreadId
0x18002fa02  nop     dword ptr [rax+rax+00h]
0x18002fa07  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa0e  mov     r8b, sil; int
0x18002fa11  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fa15  mov     dl, dil; int
0x18002fa18  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fa1d  mov     [rsp+88h+var_58], 16h; __int16
0x18002fa24  mov     r9, [rcx+28h]; int
0x18002fa28  mov     rcx, [rcx+10h]; int
0x18002fa2c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fa31  mov     rax, cs:WPP_GLOBAL_Control
0x18002fa38  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fa3f  cmp     rax, rbp
0x18002fa42  jz      short loc_18002FA4F
0x18002fa44  test    [rax+1Ch], bl
0x18002fa47  jz      short loc_18002FA4F
0x18002fa49  cmp     byte ptr [rax+19h], 4
0x18002fa4d  jnb     short loc_18002FA51
0x18002fa4f  xor     bl, bl
0x18002fa51  cmp     rcx, r14
0x18002fa54  setnz   dil
0x18002fa58  test    bl, bl
0x18002fa5a  jnz     short loc_18002FA61
0x18002fa5c  test    dil, dil
0x18002fa5f  jz      short loc_18002FA96
0x18002fa61  call    cs:__imp_GetCurrentThreadId
0x18002fa68  nop     dword ptr [rax+rax+00h]
0x18002fa6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa74  mov     r8b, dil; int
0x18002fa77  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fa7b  mov     dl, bl; int
0x18002fa7d  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fa82  mov     [rsp+88h+var_58], 17h; __int16
0x18002fa89  mov     r9, [rcx+28h]; int
0x18002fa8d  mov     rcx, [rcx+10h]; int
0x18002fa91  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fa96  mov     eax, 0C0000002h
0x18002fa9b  add     rsp, 58h
0x18002fa9f  pop     r15
0x18002faa1  pop     r14
0x18002faa3  pop     rdi
0x18002faa4  pop     rsi
0x18002faa5  pop     rbp
0x18002faa6  pop     rbx
0x18002faa7  retn
```

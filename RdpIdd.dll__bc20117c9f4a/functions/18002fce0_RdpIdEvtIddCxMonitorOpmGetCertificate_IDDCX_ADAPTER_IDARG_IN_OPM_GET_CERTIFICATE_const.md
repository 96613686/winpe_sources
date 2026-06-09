# RdpIdEvtIddCxMonitorOpmGetCertificate(IDDCX_ADAPTER__ *,IDARG_IN_OPM_GET_CERTIFICATE const *)

- ea: `0x18002fce0`
- end: `0x18002fde9`
- name: `?RdpIdEvtIddCxMonitorOpmGetCertificate@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_OPM_GET_CERTIFICATE@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_OPM_GET_CERTIFICATE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18002fce0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fd3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fda1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fd3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fda1`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOpmGetCertificate(
        struct IDDCX_ADAPTER__ *a1,
        const struct IDARG_IN_OPM_GET_CERTIFICATE *a2)
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
      12,
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
      13,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v11);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002fce0  push    rbx
0x18002fce2  push    rbp
0x18002fce3  push    rsi
0x18002fce4  push    rdi
0x18002fce5  push    r14
0x18002fce7  push    r15
0x18002fce9  sub     rsp, 58h
0x18002fced  mov     rax, cs:WPP_GLOBAL_Control
0x18002fcf4  lea     rbp, WPP_GLOBAL_Control
0x18002fcfb  mov     bl, 1
0x18002fcfd  cmp     rax, rbp
0x18002fd00  jz      short loc_18002FD12
0x18002fd02  test    [rax+1Ch], bl
0x18002fd05  jz      short loc_18002FD12
0x18002fd07  cmp     byte ptr [rax+19h], 4
0x18002fd0b  jb      short loc_18002FD12
0x18002fd0d  mov     dil, bl
0x18002fd10  jmp     short loc_18002FD15
0x18002fd12  xor     dil, dil
0x18002fd15  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fd1c  lea     r14, WPP_RECORDER_INITIALIZED
0x18002fd23  cmp     rcx, r14
0x18002fd26  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002fd2d  setnz   sil
0x18002fd31  test    dil, dil
0x18002fd34  jnz     short loc_18002FD3B
0x18002fd36  test    sil, sil
0x18002fd39  jz      short loc_18002FD7F
0x18002fd3b  call    cs:__imp_GetCurrentThreadId
0x18002fd42  nop     dword ptr [rax+rax+00h]
0x18002fd47  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd4e  mov     r8b, sil; int
0x18002fd51  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fd55  mov     dl, dil; int
0x18002fd58  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fd5d  mov     [rsp+88h+var_58], 0Ch; __int16
0x18002fd64  mov     r9, [rcx+28h]; int
0x18002fd68  mov     rcx, [rcx+10h]; int
0x18002fd6c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fd71  mov     rax, cs:WPP_GLOBAL_Control
0x18002fd78  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fd7f  cmp     rax, rbp
0x18002fd82  jz      short loc_18002FD8F
0x18002fd84  test    [rax+1Ch], bl
0x18002fd87  jz      short loc_18002FD8F
0x18002fd89  cmp     byte ptr [rax+19h], 4
0x18002fd8d  jnb     short loc_18002FD91
0x18002fd8f  xor     bl, bl
0x18002fd91  cmp     rcx, r14
0x18002fd94  setnz   dil
0x18002fd98  test    bl, bl
0x18002fd9a  jnz     short loc_18002FDA1
0x18002fd9c  test    dil, dil
0x18002fd9f  jz      short loc_18002FDD6
0x18002fda1  call    cs:__imp_GetCurrentThreadId
0x18002fda8  nop     dword ptr [rax+rax+00h]
0x18002fdad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdb4  mov     r8b, dil; int
0x18002fdb7  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fdbb  mov     dl, bl; int
0x18002fdbd  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fdc2  mov     [rsp+88h+var_58], 0Dh; __int16
0x18002fdc9  mov     r9, [rcx+28h]; int
0x18002fdcd  mov     rcx, [rcx+10h]; int
0x18002fdd1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fdd6  mov     eax, 0C0000002h
0x18002fddb  add     rsp, 58h
0x18002fddf  pop     r15
0x18002fde1  pop     r14
0x18002fde3  pop     rdi
0x18002fde4  pop     rsi
0x18002fde5  pop     rbp
0x18002fde6  pop     rbx
0x18002fde7  retn
```

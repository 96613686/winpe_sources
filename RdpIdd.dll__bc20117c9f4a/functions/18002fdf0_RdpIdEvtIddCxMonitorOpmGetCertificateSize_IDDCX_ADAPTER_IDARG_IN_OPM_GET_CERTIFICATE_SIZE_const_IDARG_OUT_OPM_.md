# RdpIdEvtIddCxMonitorOpmGetCertificateSize(IDDCX_ADAPTER__ *,IDARG_IN_OPM_GET_CERTIFICATE_SIZE const *,IDARG_OUT_OPM_GET_CERTIFICATE_SIZE *)

- ea: `0x18002fdf0`
- end: `0x18002fef9`
- name: `?RdpIdEvtIddCxMonitorOpmGetCertificateSize@@YAJPEAUIDDCX_ADAPTER__@@PEBUIDARG_IN_OPM_GET_CERTIFICATE_SIZE@@PEAUIDARG_OUT_OPM_GET_CERTIFICATE_SIZE@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_ADAPTER__ *, const struct IDARG_IN_OPM_GET_CERTIFICATE_SIZE *, struct IDARG_OUT_OPM_GET_CERTIFICATE_SIZE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18002fdf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fe4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002feb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fe4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002feb1`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOpmGetCertificateSize(
        struct IDDCX_ADAPTER__ *a1,
        const struct IDARG_IN_OPM_GET_CERTIFICATE_SIZE *a2,
        struct IDARG_OUT_OPM_GET_CERTIFICATE_SIZE *a3)
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
      10,
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
      11,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v12);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x18002fdf0  push    rbx
0x18002fdf2  push    rbp
0x18002fdf3  push    rsi
0x18002fdf4  push    rdi
0x18002fdf5  push    r14
0x18002fdf7  push    r15
0x18002fdf9  sub     rsp, 58h
0x18002fdfd  mov     rax, cs:WPP_GLOBAL_Control
0x18002fe04  lea     rbp, WPP_GLOBAL_Control
0x18002fe0b  mov     bl, 1
0x18002fe0d  cmp     rax, rbp
0x18002fe10  jz      short loc_18002FE22
0x18002fe12  test    [rax+1Ch], bl
0x18002fe15  jz      short loc_18002FE22
0x18002fe17  cmp     byte ptr [rax+19h], 4
0x18002fe1b  jb      short loc_18002FE22
0x18002fe1d  mov     dil, bl
0x18002fe20  jmp     short loc_18002FE25
0x18002fe22  xor     dil, dil
0x18002fe25  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fe2c  lea     r14, WPP_RECORDER_INITIALIZED
0x18002fe33  cmp     rcx, r14
0x18002fe36  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18002fe3d  setnz   sil
0x18002fe41  test    dil, dil
0x18002fe44  jnz     short loc_18002FE4B
0x18002fe46  test    sil, sil
0x18002fe49  jz      short loc_18002FE8F
0x18002fe4b  call    cs:__imp_GetCurrentThreadId
0x18002fe52  nop     dword ptr [rax+rax+00h]
0x18002fe57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe5e  mov     r8b, sil; int
0x18002fe61  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fe65  mov     dl, dil; int
0x18002fe68  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fe6d  mov     [rsp+88h+var_58], 0Ah; __int16
0x18002fe74  mov     r9, [rcx+28h]; int
0x18002fe78  mov     rcx, [rcx+10h]; int
0x18002fe7c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fe81  mov     rax, cs:WPP_GLOBAL_Control
0x18002fe88  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18002fe8f  cmp     rax, rbp
0x18002fe92  jz      short loc_18002FE9F
0x18002fe94  test    [rax+1Ch], bl
0x18002fe97  jz      short loc_18002FE9F
0x18002fe99  cmp     byte ptr [rax+19h], 4
0x18002fe9d  jnb     short loc_18002FEA1
0x18002fe9f  xor     bl, bl
0x18002fea1  cmp     rcx, r14
0x18002fea4  setnz   dil
0x18002fea8  test    bl, bl
0x18002feaa  jnz     short loc_18002FEB1
0x18002feac  test    dil, dil
0x18002feaf  jz      short loc_18002FEE6
0x18002feb1  call    cs:__imp_GetCurrentThreadId
0x18002feb8  nop     dword ptr [rax+rax+00h]
0x18002febd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fec4  mov     r8b, dil; int
0x18002fec7  mov     dword ptr [rsp+88h+var_48], eax; char
0x18002fecb  mov     dl, bl; int
0x18002fecd  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18002fed2  mov     [rsp+88h+var_58], 0Bh; __int16
0x18002fed9  mov     r9, [rcx+28h]; int
0x18002fedd  mov     rcx, [rcx+10h]; int
0x18002fee1  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002fee6  mov     eax, 0C0000002h
0x18002feeb  add     rsp, 58h
0x18002feef  pop     r15
0x18002fef1  pop     r14
0x18002fef3  pop     rdi
0x18002fef4  pop     rsi
0x18002fef5  pop     rbp
0x18002fef6  pop     rbx
0x18002fef7  retn
```

# RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers(IDDCX_OPMCTX__ *,IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS const *)

- ea: `0x180030010`
- end: `0x180030119`
- name: `?RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers@@YAJPEAUIDDCX_OPMCTX__@@PEBUIDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct IDDCX_OPMCTX__ *, const struct IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003006b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800300d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003006b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800300d1`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxMonitorOpmSetSigningKeyAndSequenceNumbers(
        struct IDDCX_OPMCTX__ *a1,
        const struct IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS *a2)
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
      18,
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
      19,
      &WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids,
      v11);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x180030010  push    rbx
0x180030012  push    rbp
0x180030013  push    rsi
0x180030014  push    rdi
0x180030015  push    r14
0x180030017  push    r15
0x180030019  sub     rsp, 58h
0x18003001d  mov     rax, cs:WPP_GLOBAL_Control
0x180030024  lea     rbp, WPP_GLOBAL_Control
0x18003002b  mov     bl, 1
0x18003002d  cmp     rax, rbp
0x180030030  jz      short loc_180030042
0x180030032  test    [rax+1Ch], bl
0x180030035  jz      short loc_180030042
0x180030037  cmp     byte ptr [rax+19h], 4
0x18003003b  jb      short loc_180030042
0x18003003d  mov     dil, bl
0x180030040  jmp     short loc_180030045
0x180030042  xor     dil, dil
0x180030045  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18003004c  lea     r14, WPP_RECORDER_INITIALIZED
0x180030053  cmp     rcx, r14
0x180030056  lea     r15, WPP_f632781b2e903e8cb0d894cc5bcd2305_Traceguids
0x18003005d  setnz   sil
0x180030061  test    dil, dil
0x180030064  jnz     short loc_18003006B
0x180030066  test    sil, sil
0x180030069  jz      short loc_1800300AF
0x18003006b  call    cs:__imp_GetCurrentThreadId
0x180030072  nop     dword ptr [rax+rax+00h]
0x180030077  mov     rcx, cs:WPP_GLOBAL_Control
0x18003007e  mov     r8b, sil; int
0x180030081  mov     dword ptr [rsp+88h+var_48], eax; char
0x180030085  mov     dl, dil; int
0x180030088  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18003008d  mov     [rsp+88h+var_58], 12h; __int16
0x180030094  mov     r9, [rcx+28h]; int
0x180030098  mov     rcx, [rcx+10h]; int
0x18003009c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800300a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800300a8  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x1800300af  cmp     rax, rbp
0x1800300b2  jz      short loc_1800300BF
0x1800300b4  test    [rax+1Ch], bl
0x1800300b7  jz      short loc_1800300BF
0x1800300b9  cmp     byte ptr [rax+19h], 4
0x1800300bd  jnb     short loc_1800300C1
0x1800300bf  xor     bl, bl
0x1800300c1  cmp     rcx, r14
0x1800300c4  setnz   dil
0x1800300c8  test    bl, bl
0x1800300ca  jnz     short loc_1800300D1
0x1800300cc  test    dil, dil
0x1800300cf  jz      short loc_180030106
0x1800300d1  call    cs:__imp_GetCurrentThreadId
0x1800300d8  nop     dword ptr [rax+rax+00h]
0x1800300dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300e4  mov     r8b, dil; int
0x1800300e7  mov     dword ptr [rsp+88h+var_48], eax; char
0x1800300eb  mov     dl, bl; int
0x1800300ed  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x1800300f2  mov     [rsp+88h+var_58], 13h; __int16
0x1800300f9  mov     r9, [rcx+28h]; int
0x1800300fd  mov     rcx, [rcx+10h]; int
0x180030101  call    WPP_RECORDER_AND_TRACE_SF_D
0x180030106  mov     eax, 0C0000002h
0x18003010b  add     rsp, 58h
0x18003010f  pop     r15
0x180030111  pop     r14
0x180030113  pop     rdi
0x180030114  pop     rsi
0x180030115  pop     rbp
0x180030116  pop     rbx
0x180030117  retn
```

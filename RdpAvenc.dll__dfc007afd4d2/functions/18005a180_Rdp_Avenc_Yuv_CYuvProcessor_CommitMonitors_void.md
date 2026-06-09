# Rdp::Avenc::Yuv::CYuvProcessor::CommitMonitors(void)

- ea: `0x18005a180`
- end: `0x18005a2d7`
- name: `?CommitMonitors@CYuvProcessor@Yuv@Avenc@Rdp@@UEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800146bc`
- `0x180015480`
- `0x18005a180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a282`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Yuv::CYuvProcessor::CommitMonitors(Rdp::Avenc::Yuv::CYuvProcessor *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  const char *v8; // r9
  bool v9; // di
  char v10; // al
  int v11; // r8d
  int v12; // edx
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+28h] [rbp-50h]
  int v17; // [rsp+28h] [rbp-50h]
  char *v18; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v14,
      v16,
      16,
      &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v14) = *((_BYTE *)this + 168) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v14,
      (bool)"Processor is not started",
      v18);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = GetCurrentThreadId();
      LOBYTE(v11) = v9;
      LOBYTE(v12) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v15,
        v17,
        17,
        &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
        v10);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBF,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18005a180  mov     [rsp+arg_8], rbx
0x18005a185  mov     [rsp+arg_10], rsi
0x18005a18a  push    rdi
0x18005a18b  push    r12
0x18005a18d  push    r13
0x18005a18f  push    r14
0x18005a191  push    r15
0x18005a193  sub     rsp, 50h
0x18005a197  mov     r15, rcx
0x18005a19a  lea     r12, WPP_GLOBAL_Control
0x18005a1a1  mov     rax, cs:WPP_GLOBAL_Control
0x18005a1a8  mov     bl, 1
0x18005a1aa  cmp     rax, r12
0x18005a1ad  jz      short loc_18005A1BF
0x18005a1af  test    [rax+1Ch], bl
0x18005a1b2  jz      short loc_18005A1BF
0x18005a1b4  cmp     byte ptr [rax+19h], 4
0x18005a1b8  jb      short loc_18005A1BF
0x18005a1ba  mov     dil, bl
0x18005a1bd  jmp     short loc_18005A1C2
0x18005a1bf  xor     dil, dil
0x18005a1c2  lea     r13, WPP_RECORDER_INITIALIZED
0x18005a1c9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005a1d0  setnz   sil
0x18005a1d4  test    dil, dil
0x18005a1d7  jnz     short loc_18005A1E7
0x18005a1d9  test    sil, sil
0x18005a1dc  jnz     short loc_18005A1E7
0x18005a1de  lea     r14, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005a1e5  jmp     short loc_18005A21E
0x18005a1e7  call    cs:__imp_GetCurrentThreadId
0x18005a1ed  mov     dword ptr [rsp+78h+var_38], eax; char
0x18005a1f1  lea     r14, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005a1f8  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x18005a1fd  mov     word ptr [rsp+78h+var_48], 10h; char *
0x18005a204  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a20b  mov     r9, [rcx+28h]; int
0x18005a20f  mov     r8b, sil; int
0x18005a212  mov     dl, dil; int
0x18005a215  mov     rcx, [rcx+10h]; int
0x18005a219  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005a21e  cmp     byte ptr [r15+0A8h], 0
0x18005a226  setz    al
0x18005a229  mov     rcx, [rsp+78h]; this
0x18005a22e  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18005a235  mov     qword ptr [rsp+78h+var_50], rdx; int
0x18005a23a  mov     byte ptr [rsp+78h+var_58], al; int
0x18005a23e  mov     r9d, 8000FFFFh; char *
0x18005a244  lea     r8, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005a24b  mov     edx, 0BAh; void *
0x18005a250  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005a255  mov     rax, cs:WPP_GLOBAL_Control
0x18005a25c  cmp     rax, r12
0x18005a25f  jz      short loc_18005A26C
0x18005a261  test    [rax+1Ch], bl
0x18005a264  jz      short loc_18005A26C
0x18005a266  cmp     byte ptr [rax+19h], 4
0x18005a26a  jnb     short loc_18005A26E
0x18005a26c  xor     bl, bl
0x18005a26e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005a275  setnz   dil
0x18005a279  test    bl, bl
0x18005a27b  jnz     short loc_18005A282
0x18005a27d  test    dil, dil
0x18005a280  jz      short loc_18005A2B1
0x18005a282  call    cs:__imp_GetCurrentThreadId
0x18005a288  mov     dword ptr [rsp+78h+var_38], eax; char
0x18005a28c  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x18005a291  mov     word ptr [rsp+78h+var_48], 11h; __int16
0x18005a298  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a29f  mov     r9, [rcx+28h]; int
0x18005a2a3  mov     r8b, dil; int
0x18005a2a6  mov     dl, bl; int
0x18005a2a8  mov     rcx, [rcx+10h]; int
0x18005a2ac  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005a2b1  xor     eax, eax
0x18005a2b3  jmp     short loc_18005A2BC
0x18005a2b5  mov     eax, [rsp+78h+arg_0]
0x18005a2bc  lea     r11, [rsp+78h+var_28]
0x18005a2c1  mov     rbx, [r11+38h]
0x18005a2c5  mov     rsi, [r11+40h]
0x18005a2c9  mov     rsp, r11
0x18005a2cc  pop     r15
0x18005a2ce  pop     r14
0x18005a2d0  pop     r13
0x18005a2d2  pop     r12
0x18005a2d4  pop     rdi
0x18005a2d5  retn
```

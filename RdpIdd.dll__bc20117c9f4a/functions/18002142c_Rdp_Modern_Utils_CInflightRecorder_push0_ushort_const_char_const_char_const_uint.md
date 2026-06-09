# Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)

- ea: `0x18002142c`
- end: `0x180021567`
- name: `?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z`
- size: `315`
- prototype: `void __usercall(Rdp::Modern::Utils::CInflightRecorder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const char *@<r8>, const char *@<r9>, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180013fdc`
- `0x18001638c`
- `0x180017e5c`
- `0x1800185bc`
- `0x18001d810`
- `0x180021570`
- `0x180023578`

## callees

- `0x18000d82c`
- `0x18002142c`
- `0x1800219a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002148f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002148f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214da`

## pseudocode

```c
void __fastcall Rdp::Modern::Utils::CInflightRecorder::push0(
        Rdp::Modern::Utils::CInflightRecorder *this,
        const unsigned __int16 *a2,
        const char *a3,
        const char *a4,
        unsigned int a5)
{
  bool v9; // bl
  char CurrentThreadId; // al
  int v11; // [rsp+20h] [rbp-C1h]
  int v12; // [rsp+28h] [rbp-B9h]
  int v13; // [rsp+30h] [rbp-B1h]
  int v14; // [rsp+38h] [rbp-A9h]
  int v15; // [rsp+60h] [rbp-81h] BYREF
  __int128 v16; // [rsp+64h] [rbp-7Dh]
  int v17; // [rsp+74h] [rbp-6Dh]
  const unsigned __int16 *v18; // [rsp+78h] [rbp-69h]
  DWORD v19; // [rsp+80h] [rbp-61h]
  int v20; // [rsp+84h] [rbp-5Dh]
  __int64 v21; // [rsp+88h] [rbp-59h]
  const char *v22; // [rsp+90h] [rbp-51h]
  const char *v23; // [rsp+98h] [rbp-49h]
  unsigned int v24; // [rsp+A0h] [rbp-41h]
  int v25; // [rsp+A4h] [rbp-3Dh]
  __int64 v26; // [rsp+A8h] [rbp-39h]
  __int64 v27; // [rsp+B0h] [rbp-31h]
  __int64 v28; // [rsp+B8h] [rbp-29h]
  __int64 v29; // [rsp+C0h] [rbp-21h]
  __int64 v30; // [rsp+C8h] [rbp-19h]
  __int128 v31; // [rsp+D0h] [rbp-11h]
  __int128 v32; // [rsp+E0h] [rbp-1h]
  __int64 v33; // [rsp+F0h] [rbp+Fh]

  v9 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_RECORDER_AND_TRACE_SF_DsS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v12,
      v13,
      v14,
      CurrentThreadId,
      (__int64)a3,
      (__int64)a2);
  }
  v15 = 2;
  v18 = a2;
  v16 = 0;
  v17 = 0;
  v22 = a3;
  v19 = GetCurrentThreadId();
  v23 = a4;
  v20 = 0;
  v21 = 0;
  v24 = a5;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Rdp::Modern::Utils::CInflightRecorder::pushInternal(this, (const struct wil::FailureInfo *)&v15);
}

```

## disassembly

```asm
0x18002142c  push    rbp
0x18002142e  push    rbx
0x18002142f  push    rsi
0x180021430  push    rdi
0x180021431  push    r12
0x180021433  push    r14
0x180021435  push    r15
0x180021437  lea     rbp, [rsp-1Fh]
0x18002143c  sub     rsp, 100h
0x180021443  mov     r15, r9
0x180021446  mov     rsi, r8
0x180021449  mov     r14, rdx
0x18002144c  mov     r12, rcx
0x18002144f  mov     rax, cs:WPP_GLOBAL_Control
0x180021456  lea     rcx, WPP_GLOBAL_Control
0x18002145d  cmp     rax, rcx
0x180021460  jz      short loc_180021472
0x180021462  test    byte ptr [rax+1Ch], 2
0x180021466  jz      short loc_180021472
0x180021468  cmp     byte ptr [rax+19h], 4
0x18002146c  jb      short loc_180021472
0x18002146e  mov     bl, 1
0x180021470  jmp     short loc_180021474
0x180021472  xor     bl, bl
0x180021474  lea     rax, WPP_RECORDER_INITIALIZED
0x18002147b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180021482  setnz   dil
0x180021486  test    bl, bl
0x180021488  jnz     short loc_18002148F
0x18002148a  test    dil, dil
0x18002148d  jz      short loc_1800214C2
0x18002148f  call    cs:__imp_GetCurrentThreadId
0x180021496  nop     dword ptr [rax+rax+00h]
0x18002149b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214a2  mov     r8b, dil
0x1800214a5  mov     [rsp+130h+var_E0], r14; __int64
0x1800214aa  mov     dl, bl
0x1800214ac  mov     [rsp+130h+var_E8], rsi; __int64
0x1800214b1  mov     dword ptr [rsp+130h+var_F0], eax; char
0x1800214b5  mov     r9, [rcx+28h]
0x1800214b9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800214bd  call    WPP_RECORDER_AND_TRACE_SF_DsS
0x1800214c2  xorps   xmm0, xmm0
0x1800214c5  mov     [rsp+130h+var_D0], 2
0x1800214cd  xor     eax, eax
0x1800214cf  mov     [rbp+4Fh+var_B8], r14
0x1800214d3  movups  [rbp+4Fh+var_CC], xmm0
0x1800214d7  mov     [rbp+4Fh+var_BC], eax
0x1800214da  call    cs:__imp_GetCurrentThreadId
0x1800214e1  nop     dword ptr [rax+rax+00h]
0x1800214e6  xorps   xmm0, xmm0
0x1800214e9  mov     [rbp+4Fh+var_A0], rsi
0x1800214ed  mov     [rbp+4Fh+var_B0], eax
0x1800214f0  lea     rdx, [rsp+130h+var_D0]; struct wil::FailureInfo *
0x1800214f5  xor     eax, eax
0x1800214f7  mov     [rbp+4Fh+var_98], r15
0x1800214fb  mov     [rbp+4Fh+var_AC], eax
0x1800214fe  xorps   xmm1, xmm1
0x180021501  mov     [rbp+4Fh+var_A8], rax
0x180021505  mov     rcx, r12; this
0x180021508  mov     eax, [rbp+4Fh+arg_20]
0x18002150b  mov     [rbp+4Fh+var_90], eax
0x18002150e  mov     [rbp+4Fh+var_8C], 0
0x180021515  mov     [rbp+4Fh+var_88], 0
0x18002151d  mov     [rbp+4Fh+var_80], 0
0x180021525  mov     [rbp+4Fh+var_78], 0
0x18002152d  mov     [rbp+4Fh+var_70], 0
0x180021535  mov     [rbp+4Fh+var_68], 0
0x18002153d  movdqa  [rbp+4Fh+var_60], xmm0
0x180021542  movdqa  [rbp+4Fh+var_50], xmm1
0x180021547  mov     [rbp+4Fh+var_40], 0
0x18002154f  call    ?pushInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAAXAEBUFailureInfo@wil@@@Z; Rdp::Modern::Utils::CInflightRecorder::pushInternal(wil::FailureInfo const &)
0x180021554  add     rsp, 100h
0x18002155b  pop     r15
0x18002155d  pop     r14
0x18002155f  pop     r12
0x180021561  pop     rdi
0x180021562  pop     rsi
0x180021563  pop     rbx
0x180021564  pop     rbp
0x180021565  retn
```

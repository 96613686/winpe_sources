# SpeechMicDiagnostic::CaptureStream::ReceiveThread(void *)

- ea: `0x18000f4b0`
- end: `0x18000f5e8`
- name: `?ReceiveThread@CaptureStream@SpeechMicDiagnostic@@CAKPEAX@Z`
- size: `312`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007c38`
- `0x18000d5fc`
- `0x18000df50`
- `0x18000f090`
- `0x18000f4b0`
- `0x180011010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x18000f502`
- `KERNEL32!WaitForMultipleObjects` at `0x18000f502`
- `ole32!CoInitializeEx` at `0x18000f4e4`
- `ole32!CoInitializeEx` at `0x18000f4e4`
- `ole32!CoUninitialize` at `0x18000f5ce`
- `ole32!CoUninitialize` at `0x18000f5ce`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::ReceiveThread(
        SpeechMicDiagnostic::CaptureStream *lpThreadParameter)
{
  void *v1; // rax
  __int64 v3; // rcx
  DWORD v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  int LastError; // eax
  signed int v9; // ebx
  int v10; // eax
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (void *)*((_QWORD *)lpThreadParameter + 23);
  v3 = *(_QWORD *)lpThreadParameter;
  Handles[0] = v1;
  Handles[1] = (HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 168LL))(v3);
  CoInitializeEx(0, 0);
  while ( 1 )
  {
    v4 = WaitForMultipleObjects(2u, Handles, 0, 0x7D0u);
    if ( !v4 )
      break;
    switch ( v4 )
    {
      case 1u:
        v10 = SpeechMicDiagnostic::CaptureStream::HandleIncomingData(lpThreadParameter);
        v9 = v10;
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x22A,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
            (const char *)(unsigned int)v10,
            (int)Handles[0]);
        break;
      case 0x102u:
        v9 = -2147023436;
        goto LABEL_14;
      case 0xFFFFFFFF:
        LastError = wil::details::in1diag3::Log_GetLastError(retaddr, v5, v6, v7);
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        break;
      default:
        v9 = -2147418113;
LABEL_14:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
          (const char *)(unsigned int)v9,
          (int)Handles[0]);
        SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(
          *((SpeechMicDiagnostic::DiagnosticStatus **)lpThreadParameter + 8),
          0,
          0.0,
          v9);
        goto LABEL_15;
    }
    if ( v9 < 0 )
      goto LABEL_14;
  }
LABEL_15:
  if ( *((_BYTE *)lpThreadParameter + 201) && *((_DWORD *)lpThreadParameter + 39) != 10001 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)lpThreadParameter + 184LL))(*(_QWORD *)lpThreadParameter);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18000f4b0  mov     [rsp+arg_0], rbx
0x18000f4b5  push    rdi
0x18000f4b6  sub     rsp, 30h
0x18000f4ba  mov     rax, [rcx+0B8h]
0x18000f4c1  mov     rdi, rcx
0x18000f4c4  mov     rcx, [rcx]
0x18000f4c7  mov     [rsp+38h+Handles], rax; int
0x18000f4cc  mov     rax, [rcx]
0x18000f4cf  mov     rax, [rax+0A8h]
0x18000f4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4db  xor     edx, edx; dwCoInit
0x18000f4dd  mov     [rsp+38h+var_10], rax
0x18000f4e2  xor     ecx, ecx; pvReserved
0x18000f4e4  call    cs:__imp_CoInitializeEx
0x18000f4eb  nop     dword ptr [rax+rax+00h]
0x18000f4f0  xor     r8d, r8d; bWaitAll
0x18000f4f3  lea     rdx, [rsp+38h+Handles]; lpHandles
0x18000f4f8  mov     r9d, 7D0h; dwMilliseconds
0x18000f4fe  lea     ecx, [r8+2]; nCount
0x18000f502  call    cs:__imp_WaitForMultipleObjects
0x18000f509  nop     dword ptr [rax+rax+00h]
0x18000f50e  test    eax, eax
0x18000f510  jz      loc_18000F5A5
0x18000f516  cmp     eax, 1
0x18000f519  jz      short loc_18000F542
0x18000f51b  cmp     eax, 102h
0x18000f520  jz      short loc_18000F576
0x18000f522  cmp     eax, 0FFFFFFFFh
0x18000f525  jnz     short loc_18000F56F
0x18000f527  mov     rcx, [rsp+38h]; this
0x18000f52c  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000f531  mov     ebx, eax
0x18000f533  test    eax, eax
0x18000f535  jle     short loc_18000F569
0x18000f537  movzx   ebx, ax
0x18000f53a  or      ebx, 80070000h
0x18000f540  jmp     short loc_18000F569
0x18000f542  mov     rcx, rdi; this
0x18000f545  call    ?HandleIncomingData@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::HandleIncomingData(void)
0x18000f54a  mov     ebx, eax
0x18000f54c  test    eax, eax
0x18000f54e  jns     short loc_18000F569
0x18000f550  mov     rcx, [rsp+38h]; this
0x18000f555  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f55c  mov     r9d, eax; char *
0x18000f55f  mov     edx, 22Ah; void *
0x18000f564  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f569  test    ebx, ebx
0x18000f56b  jns     short loc_18000F4F0
0x18000f56d  jmp     short loc_18000F57B
0x18000f56f  mov     ebx, 8000FFFFh
0x18000f574  jmp     short loc_18000F57B
0x18000f576  mov     ebx, 800705B4h
0x18000f57b  mov     rcx, [rsp+38h]; this
0x18000f580  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f587  mov     r9d, ebx; char *
0x18000f58a  mov     edx, 236h; void *
0x18000f58f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f594  mov     rcx, [rdi+40h]; this
0x18000f598  mov     r9d, ebx; int
0x18000f59b  xorps   xmm2, xmm2; double
0x18000f59e  xor     edx, edx; unsigned int
0x18000f5a0  call    ?CompleteDiagnostic@DiagnosticStatus@SpeechMicDiagnostic@@QEAAXKNJ@Z; SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(ulong,double,long)
0x18000f5a5  cmp     byte ptr [rdi+0C9h], 0
0x18000f5ac  jz      short loc_18000F5CE
0x18000f5ae  mov     edx, [rdi+9Ch]
0x18000f5b4  cmp     edx, 2711h
0x18000f5ba  jz      short loc_18000F5CE
0x18000f5bc  mov     rcx, [rdi]
0x18000f5bf  mov     rax, [rcx]
0x18000f5c2  mov     rax, [rax+0B8h]
0x18000f5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ce  call    cs:__imp_CoUninitialize
0x18000f5d5  nop     dword ptr [rax+rax+00h]
0x18000f5da  mov     rbx, [rsp+38h+arg_0]
0x18000f5df  xor     eax, eax
0x18000f5e1  add     rsp, 30h
0x18000f5e5  pop     rdi
0x18000f5e6  retn
```

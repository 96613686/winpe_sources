# UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)

- ea: `0x140033c34`
- end: `0x14003414a`
- name: `?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z`
- size: `1302`
- prototype: `__int64 __usercall@<rax>(DWORD dwProcessId@<ecx>, DWORD dwThreadId@<edx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400339d8`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140004198`
- `0x140033748`
- `0x140033c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034104`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140033cc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140033cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140033dbf`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140033d81`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x140033d81`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140033ea0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140033ea0`
- `dbghelp!SymGetModuleBase64` at `0x140033f10`
- `dbghelp!SymSetExtendedOption` at `0x140033ebd`
- `dbghelp!SymSetExtendedOption` at `0x140033ebd`
- `dbghelp!SymCleanup` at `0x1400340db`
- `dbghelp!SymCleanup` at `0x1400340db`
- `dbghelp!SymInitialize` at `0x140033ed1`
- `dbghelp!SymInitialize` at `0x140033ed1`
- `dbghelp!SymFunctionTableAccess64` at `0x140033f32`
- `dbghelp!StackWalk64` at `0x140033f58`
- `dbghelp!StackWalk64` at `0x140033f58`

## pseudocode

```c
__int64 __fastcall UtilGetStackTrace(
        DWORD dwProcessId,
        DWORD dwThreadId,
        void **a3,
        unsigned int *a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  char *v11; // r14
  __int64 v12; // rdx
  CONTEXT *p_Context; // rax
  _OWORD *v14; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  char *v26; // rbx
  signed int LastError; // eax
  unsigned int v28; // r15d
  _tagSTACKFRAME64 *p_StackFrame; // rcx
  __int64 v30; // rdx
  ADDRESS64 *v31; // rax
  ADDRESS64 v32; // xmm1
  ADDRESS64 v33; // xmm0
  ADDRESS64 v34; // xmm1
  ADDRESS64 v35; // xmm0
  ADDRESS64 v36; // xmm1
  ADDRESS64 v37; // xmm0
  ADDRESS64 v38; // xmm1
  _QWORD *v39; // rax
  _QWORD *v40; // rdi
  unsigned int i; // r15d
  ADDRESS64 *v42; // rcx
  __int64 v43; // rdx
  _tagSTACKFRAME64 *v44; // rax
  ADDRESS64 AddrReturn; // xmm1
  ADDRESS64 AddrFrame; // xmm0
  ADDRESS64 AddrStack; // xmm1
  ADDRESS64 AddrBStore; // xmm0
  ADDRESS64 v49; // xmm1
  ADDRESS64 v50; // xmm0
  ADDRESS64 v51; // xmm1
  __int64 v52; // rcx
  _OWORD *v53; // rax
  _OWORD *v54; // r8
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  unsigned __int64 v62; // rax
  const struct std::nothrow_t *v63; // rdx
  char *v64; // rsi
  struct _WER_STACK_FRAME *v65; // r9
  unsigned int j; // r12d
  void *v67; // rcx
  const struct std::nothrow_t *v68; // rdx
  signed int v69; // eax
  _BYTE v72[1232]; // [rsp+60h] [rbp-A0h] BYREF
  _tagSTACKFRAME64 StackFrame; // [rsp+530h] [rbp+430h] BYREF
  CONTEXT Context; // [rsp+640h] [rbp+540h] BYREF

  memset_0(&StackFrame, 0, sizeof(StackFrame));
  memset_0(&Context, 0, sizeof(Context));
  if ( !a3 || !a4 )
    return (unsigned int)-2147024809;
  v11 = (char *)OpenThread(0x48u, 0, dwThreadId);
  if ( v11 != (char *)-1LL && v11 + 1 != (char *)1 )
  {
    memset_0(v72, 0, sizeof(v72));
    v12 = 9;
    p_Context = &Context;
    v14 = v72;
    do
    {
      v15 = v14[1];
      *(_OWORD *)&p_Context->P1Home = *v14;
      v16 = v14[2];
      *(_OWORD *)&p_Context->P3Home = v15;
      v17 = v14[3];
      *(_OWORD *)&p_Context->P5Home = v16;
      v18 = v14[4];
      *(_OWORD *)&p_Context->ContextFlags = v17;
      v19 = v14[5];
      *(_OWORD *)&p_Context->SegGs = v18;
      v20 = v14[6];
      *(_OWORD *)&p_Context->Dr1 = v19;
      v21 = v14[7];
      v14 += 8;
      *(_OWORD *)&p_Context->Dr3 = v20;
      *(_OWORD *)&p_Context->Dr7 = v21;
      p_Context = (CONTEXT *)((char *)p_Context + 128);
      --v12;
    }
    while ( v12 );
    v22 = v14[1];
    *(_OWORD *)&p_Context->P1Home = *v14;
    v23 = v14[2];
    *(_OWORD *)&p_Context->P3Home = v22;
    v24 = v14[3];
    *(_OWORD *)&p_Context->P5Home = v23;
    v25 = v14[4];
    *(_OWORD *)&p_Context->ContextFlags = v24;
    *(_OWORD *)&p_Context->SegGs = v25;
    Context.ContextFlags = 1048607;
    if ( !GetThreadContext(v11, &Context) )
    {
      v26 = 0;
      goto LABEL_8;
    }
    memset_0(v72, 0, 0x108u);
    p_StackFrame = &StackFrame;
    v30 = 2;
    v31 = (ADDRESS64 *)v72;
    do
    {
      v32 = v31[1];
      p_StackFrame->AddrPC = *v31;
      v33 = v31[2];
      p_StackFrame->AddrReturn = v32;
      v34 = v31[3];
      p_StackFrame->AddrFrame = v33;
      v35 = v31[4];
      p_StackFrame->AddrStack = v34;
      v36 = v31[5];
      p_StackFrame->AddrBStore = v35;
      v37 = v31[6];
      *(ADDRESS64 *)&p_StackFrame->FuncTableEntry = v36;
      v38 = v31[7];
      v31 += 8;
      *(ADDRESS64 *)&p_StackFrame->Params[1] = v37;
      *(ADDRESS64 *)&p_StackFrame->Params[3] = v38;
      p_StackFrame = (_tagSTACKFRAME64 *)((char *)p_StackFrame + 128);
      --v30;
    }
    while ( v30 );
    p_StackFrame->AddrPC.Offset = v31->Offset;
    StackFrame.AddrPC.Mode = AddrModeFlat;
    StackFrame.AddrPC.Segment = 0;
    StackFrame.AddrStack.Segment = 0;
    StackFrame.AddrFrame.Segment = 0;
    StackFrame.AddrPC.Offset = Context.Rip;
    StackFrame.AddrStack.Offset = Context.Rsp;
    StackFrame.AddrFrame.Offset = Context.Rbp;
    StackFrame.AddrStack.Mode = AddrModeFlat;
    StackFrame.AddrFrame.Mode = AddrModeFlat;
    v26 = (char *)OpenProcess(0x410u, 0, dwProcessId);
    if ( v26 == (char *)-1LL
      || v26 + 1 == (char *)1
      || (SymSetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)3, 1), !SymInitialize(v26, UserSearchPath, 1)) )
    {
LABEL_8:
      LastError = GetLastError();
      v28 = LastError;
      if ( LastError > 0 )
        v28 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
      CloseHandle(v11);
      if ( (unsigned __int64)(v26 + 1) > 1 )
        CloseHandle(v26);
      return v28;
    }
    v39 = operator new[](0x8400u, (const struct std::nothrow_t *)&std::nothrow);
    v40 = v39;
    if ( v39 )
    {
      memset_0(v39, 0, 0x8400u);
      for ( i = 0; i < 0x80; ++i )
      {
        if ( !StackWalk64(0x8664u, v26, v11, &StackFrame, &Context, 0, SymFunctionTableAccess64, SymGetModuleBase64, 0) )
          break;
        v42 = (ADDRESS64 *)v72;
        v43 = 2;
        v44 = &StackFrame;
        do
        {
          AddrReturn = v44->AddrReturn;
          *v42 = v44->AddrPC;
          AddrFrame = v44->AddrFrame;
          v42[1] = AddrReturn;
          AddrStack = v44->AddrStack;
          v42[2] = AddrFrame;
          AddrBStore = v44->AddrBStore;
          v42[3] = AddrStack;
          v49 = *(ADDRESS64 *)&v44->FuncTableEntry;
          v42[4] = AddrBStore;
          v50 = *(ADDRESS64 *)&v44->Params[1];
          v42[5] = v49;
          v51 = *(ADDRESS64 *)&v44->Params[3];
          v44 = (_tagSTACKFRAME64 *)((char *)v44 + 128);
          v42[6] = v50;
          v42[7] = v51;
          v42 += 8;
          --v43;
        }
        while ( v43 );
        v42->Offset = v44->AddrPC.Offset;
        v52 = 2;
        v53 = v72;
        v54 = &v40[33 * i];
        do
        {
          v55 = v53[1];
          *v54 = *v53;
          v56 = v53[2];
          v54[1] = v55;
          v57 = v53[3];
          v54[2] = v56;
          v58 = v53[4];
          v54[3] = v57;
          v59 = v53[5];
          v54[4] = v58;
          v60 = v53[6];
          v54[5] = v59;
          v61 = v53[7];
          v53 += 8;
          v54[6] = v60;
          v54[7] = v61;
          v54 += 8;
          --v52;
        }
        while ( v52 );
        *(_QWORD *)v54 = *(_QWORD *)v53;
      }
      v62 = 1048LL * i;
      if ( !is_mul_ok(i, 0x418u) )
        v62 = -1;
      v64 = (char *)operator new[](v62, (const struct std::nothrow_t *)&std::nothrow);
      if ( v64 )
      {
        for ( j = 0; j < i; ++j )
          _werDetail::UtilConvertDbgFrameToWerFrame((_werDetail *)v26, &v40[33 * j], &v64[1048 * j], v65);
        if ( a7 )
          *a7 = *v40;
        v67 = *a3;
        *a3 = v64;
        if ( v67 )
          operator delete(v67, v63);
        *a4 = i;
        v28 = 0;
        goto LABEL_36;
      }
    }
    else
    {
      v40 = 0;
    }
    v28 = -2147024882;
LABEL_36:
    SymCleanup(v26);
    if ( v40 )
      operator delete(v40, v68);
    goto LABEL_10;
  }
  v69 = GetLastError();
  v28 = v69;
  if ( v69 > 0 )
    return (unsigned __int16)v69 | 0x80070000;
  return v28;
}

```

## disassembly

```asm
0x140033c34  push    rbp
0x140033c36  push    rbx
0x140033c37  push    rsi
0x140033c38  push    rdi
0x140033c39  push    r12
0x140033c3b  push    r13
0x140033c3d  push    r14
0x140033c3f  push    r15
0x140033c41  lea     rbp, [rsp-0A28h]
0x140033c49  sub     rsp, 0B28h
0x140033c50  mov     rax, cs:__security_cookie
0x140033c57  xor     rax, rsp
0x140033c5a  mov     [rbp+0A60h+var_50], rax
0x140033c61  mov     rax, [rbp+0A60h+arg_30]
0x140033c68  mov     r13, r8
0x140033c6b  mov     ebx, edx
0x140033c6d  mov     [rsp+0B60h+var_B08], r9
0x140033c72  mov     edi, ecx
0x140033c74  mov     [rsp+0B60h+var_B10], rax
0x140033c79  mov     r12d, 108h
0x140033c7f  lea     rcx, [rbp+0A60h+StackFrame]; void *
0x140033c86  mov     r8d, r12d; Size
0x140033c89  xor     edx, edx; Val
0x140033c8b  mov     rsi, r9
0x140033c8e  call    memset_0
0x140033c93  mov     r15d, 4D0h
0x140033c99  lea     rcx, [rbp+0A60h+Context]; void *
0x140033ca0  mov     r8d, r15d; Size
0x140033ca3  xor     edx, edx; Val
0x140033ca5  call    memset_0
0x140033caa  test    r13, r13
0x140033cad  jz      loc_14003411E
0x140033cb3  test    rsi, rsi
0x140033cb6  jz      loc_14003411E
0x140033cbc  xor     edx, edx; bInheritHandle
0x140033cbe  mov     r8d, ebx; dwThreadId
0x140033cc1  lea     ecx, [rdx+48h]; dwDesiredAccess
0x140033cc4  call    cs:__imp_OpenThread
0x140033cca  mov     r14, rax
0x140033ccd  inc     rax
0x140033cd0  cmp     rax, 1
0x140033cd4  jbe     loc_140034104
0x140033cda  mov     r8d, r15d; Size
0x140033cdd  lea     rcx, [rsp+0B60h+var_B00]; void *
0x140033ce2  xor     edx, edx; Val
0x140033ce4  call    memset_0
0x140033ce9  mov     edx, 9
0x140033cee  lea     rax, [rbp+0A60h+Context]
0x140033cf5  lea     rcx, [rsp+0B60h+var_B00]
0x140033cfa  lea     esi, [rdx+77h]
0x140033cfd  movups  xmm0, xmmword ptr [rcx]
0x140033d00  movups  xmm1, xmmword ptr [rcx+10h]
0x140033d04  movups  xmmword ptr [rax], xmm0
0x140033d07  movups  xmm0, xmmword ptr [rcx+20h]
0x140033d0b  movups  xmmword ptr [rax+10h], xmm1
0x140033d0f  movups  xmm1, xmmword ptr [rcx+30h]
0x140033d13  movups  xmmword ptr [rax+20h], xmm0
0x140033d17  movups  xmm0, xmmword ptr [rcx+40h]
0x140033d1b  movups  xmmword ptr [rax+30h], xmm1
0x140033d1f  movups  xmm1, xmmword ptr [rcx+50h]
0x140033d23  movups  xmmword ptr [rax+40h], xmm0
0x140033d27  movups  xmm0, xmmword ptr [rcx+60h]
0x140033d2b  movups  xmmword ptr [rax+50h], xmm1
0x140033d2f  movups  xmm1, xmmword ptr [rcx+70h]
0x140033d33  add     rcx, rsi
0x140033d36  movups  xmmword ptr [rax+60h], xmm0
0x140033d3a  movups  xmmword ptr [rax+70h], xmm1
0x140033d3e  add     rax, rsi
0x140033d41  sub     rdx, 1
0x140033d45  jnz     short loc_140033CFD
0x140033d47  movups  xmm0, xmmword ptr [rcx]
0x140033d4a  lea     rdx, [rbp+0A60h+Context]; lpContext
0x140033d51  movups  xmm1, xmmword ptr [rcx+10h]
0x140033d55  movups  xmmword ptr [rax], xmm0
0x140033d58  movups  xmm0, xmmword ptr [rcx+20h]
0x140033d5c  movups  xmmword ptr [rax+10h], xmm1
0x140033d60  movups  xmm1, xmmword ptr [rcx+30h]
0x140033d64  movups  xmmword ptr [rax+20h], xmm0
0x140033d68  movups  xmm0, xmmword ptr [rcx+40h]
0x140033d6c  mov     rcx, r14; hThread
0x140033d6f  movups  xmmword ptr [rax+30h], xmm1
0x140033d73  movups  xmmword ptr [rax+40h], xmm0
0x140033d77  mov     [rbp+0A60h+Context.ContextFlags], 10001Fh
0x140033d81  call    cs:__imp_GetThreadContext
0x140033d87  test    eax, eax
0x140033d89  jnz     short loc_140033DCA
0x140033d8b  xor     ebx, ebx
0x140033d8d  call    cs:__imp_GetLastError
0x140033d93  mov     r15d, eax
0x140033d96  test    eax, eax
0x140033d98  jle     short loc_140033DA5
0x140033d9a  movzx   r15d, ax
0x140033d9e  or      r15d, 80070000h
0x140033da5  mov     rcx, r14; hObject
0x140033da8  call    cs:__imp_CloseHandle
0x140033dae  lea     rax, [rbx+1]
0x140033db2  cmp     rax, 1
0x140033db6  jbe     loc_140034124
0x140033dbc  mov     rcx, rbx; hObject
0x140033dbf  call    cs:__imp_CloseHandle
0x140033dc5  jmp     loc_140034124
0x140033dca  mov     r8, r12; Size
0x140033dcd  lea     rcx, [rsp+0B60h+var_B00]; void *
0x140033dd2  xor     edx, edx; Val
0x140033dd4  call    memset_0
0x140033dd9  mov     r12d, 2
0x140033ddf  lea     rcx, [rbp+0A60h+StackFrame]
0x140033de6  mov     edx, r12d
0x140033de9  lea     rax, [rsp+0B60h+var_B00]
0x140033dee  movups  xmm0, xmmword ptr [rax]
0x140033df1  movups  xmm1, xmmword ptr [rax+10h]
0x140033df5  movups  xmmword ptr [rcx], xmm0
0x140033df8  movups  xmm0, xmmword ptr [rax+20h]
0x140033dfc  movups  xmmword ptr [rcx+10h], xmm1
0x140033e00  movups  xmm1, xmmword ptr [rax+30h]
0x140033e04  movups  xmmword ptr [rcx+20h], xmm0
0x140033e08  movups  xmm0, xmmword ptr [rax+40h]
0x140033e0c  movups  xmmword ptr [rcx+30h], xmm1
0x140033e10  movups  xmm1, xmmword ptr [rax+50h]
0x140033e14  movups  xmmword ptr [rcx+40h], xmm0
0x140033e18  movups  xmm0, xmmword ptr [rax+60h]
0x140033e1c  movups  xmmword ptr [rcx+50h], xmm1
0x140033e20  movups  xmm1, xmmword ptr [rax+70h]
0x140033e24  add     rax, rsi
0x140033e27  movups  xmmword ptr [rcx+60h], xmm0
0x140033e2b  movups  xmmword ptr [rcx+70h], xmm1
0x140033e2f  add     rcx, rsi
0x140033e32  sub     rdx, 1; bInheritHandle
0x140033e36  jnz     short loc_140033DEE
0x140033e38  mov     rax, [rax]
0x140033e3b  lea     r15d, [rdx+3]
0x140033e3f  mov     [rcx], rax
0x140033e42  mov     r8d, edi; dwProcessId
0x140033e45  xor     eax, eax
0x140033e47  mov     [rbp+0A60h+StackFrame.AddrPC.Mode], r15d
0x140033e4e  mov     [rbp+0A60h+StackFrame.AddrPC.Segment], ax
0x140033e55  mov     ecx, 410h; dwDesiredAccess
0x140033e5a  mov     [rbp+0A60h+StackFrame.AddrStack.Segment], ax
0x140033e61  mov     [rbp+0A60h+StackFrame.AddrFrame.Segment], ax
0x140033e68  mov     rax, [rbp+0A60h+Context.Rip]
0x140033e6f  mov     [rbp+0A60h+StackFrame.AddrPC.Offset], rax
0x140033e76  mov     rax, [rbp+0A60h+Context.Rsp]
0x140033e7d  mov     [rbp+0A60h+StackFrame.AddrStack.Offset], rax
0x140033e84  mov     rax, [rbp+0A60h+Context.Rbp]
0x140033e8b  mov     [rbp+0A60h+StackFrame.AddrFrame.Offset], rax
0x140033e92  mov     [rbp+0A60h+StackFrame.AddrStack.Mode], r15d
0x140033e99  mov     [rbp+0A60h+StackFrame.AddrFrame.Mode], r15d
0x140033ea0  call    cs:__imp_OpenProcess
0x140033ea6  mov     rbx, rax
0x140033ea9  inc     rax
0x140033eac  cmp     rax, 1
0x140033eb0  jbe     loc_140033D8D
0x140033eb6  lea     edx, [r15-2]; value
0x140033eba  mov     ecx, r15d; option
0x140033ebd  call    cs:__imp_SymSetExtendedOption
0x140033ec3  lea     r8d, [r15-2]; fInvadeProcess
0x140033ec7  mov     rcx, rbx; hProcess
0x140033eca  lea     rdx, UserSearchPath; UserSearchPath
0x140033ed1  call    cs:__imp_SymInitialize
0x140033ed7  test    eax, eax
0x140033ed9  jz      loc_140033D8D
0x140033edf  mov     r15d, 8400h
0x140033ee5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140033eec  mov     ecx, r15d; unsigned __int64
0x140033eef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140033ef4  mov     rdi, rax
0x140033ef7  test    rax, rax
0x140033efa  jz      loc_1400340CE
0x140033f00  mov     r8d, r15d; Size
0x140033f03  xor     edx, edx; Val
0x140033f05  mov     rcx, rax; void *
0x140033f08  call    memset_0
0x140033f0d  xor     r15d, r15d
0x140033f10  mov     rax, cs:__imp_SymGetModuleBase64
0x140033f17  lea     r9, [rbp+0A60h+StackFrame]; StackFrame
0x140033f1e  mov     [rsp+0B60h+TranslateAddress], 0; TranslateAddress
0x140033f27  mov     r8, r14; hThread
0x140033f2a  mov     [rsp+0B60h+GetModuleBaseRoutine], rax; GetModuleBaseRoutine
0x140033f2f  mov     rdx, rbx; hProcess
0x140033f32  mov     rax, cs:__imp_SymFunctionTableAccess64
0x140033f39  mov     ecx, 8664h; MachineType
0x140033f3e  mov     [rsp+0B60h+FunctionTableAccessRoutine], rax; FunctionTableAccessRoutine
0x140033f43  lea     rax, [rbp+0A60h+Context]
0x140033f4a  mov     [rsp+0B60h+ReadMemoryRoutine], 0; ReadMemoryRoutine
0x140033f53  mov     [rsp+0B60h+ContextRecord], rax; ContextRecord
0x140033f58  call    cs:__imp_StackWalk64
0x140033f5e  test    eax, eax
0x140033f60  jz      loc_14003403E
0x140033f66  lea     rcx, [rsp+0B60h+var_B00]
0x140033f6b  mov     rdx, r12
0x140033f6e  lea     rax, [rbp+0A60h+StackFrame]
0x140033f75  movups  xmm0, xmmword ptr [rax]
0x140033f78  movups  xmm1, xmmword ptr [rax+10h]
0x140033f7c  movups  xmmword ptr [rcx], xmm0
0x140033f7f  movups  xmm0, xmmword ptr [rax+20h]
0x140033f83  movups  xmmword ptr [rcx+10h], xmm1
0x140033f87  movups  xmm1, xmmword ptr [rax+30h]
0x140033f8b  movups  xmmword ptr [rcx+20h], xmm0
0x140033f8f  movups  xmm0, xmmword ptr [rax+40h]
0x140033f93  movups  xmmword ptr [rcx+30h], xmm1
0x140033f97  movups  xmm1, xmmword ptr [rax+50h]
0x140033f9b  movups  xmmword ptr [rcx+40h], xmm0
0x140033f9f  movups  xmm0, xmmword ptr [rax+60h]
0x140033fa3  movups  xmmword ptr [rcx+50h], xmm1
0x140033fa7  movups  xmm1, xmmword ptr [rax+70h]
0x140033fab  add     rax, rsi
0x140033fae  movups  xmmword ptr [rcx+60h], xmm0
0x140033fb2  movups  xmmword ptr [rcx+70h], xmm1
0x140033fb6  add     rcx, rsi
0x140033fb9  sub     rdx, 1
0x140033fbd  jnz     short loc_140033F75
0x140033fbf  mov     rax, [rax]
0x140033fc2  mov     [rcx], rax
0x140033fc5  mov     rcx, r12
0x140033fc8  mov     eax, r15d
0x140033fcb  imul    r8, rax, 108h
0x140033fd2  lea     rax, [rsp+0B60h+var_B00]
0x140033fd7  add     r8, rdi
0x140033fda  movups  xmm0, xmmword ptr [rax]
0x140033fdd  movups  xmm1, xmmword ptr [rax+10h]
0x140033fe1  movups  xmmword ptr [r8], xmm0
0x140033fe5  movups  xmm0, xmmword ptr [rax+20h]
0x140033fe9  movups  xmmword ptr [r8+10h], xmm1
0x140033fee  movups  xmm1, xmmword ptr [rax+30h]
0x140033ff2  movups  xmmword ptr [r8+20h], xmm0
0x140033ff7  movups  xmm0, xmmword ptr [rax+40h]
0x140033ffb  movups  xmmword ptr [r8+30h], xmm1
0x140034000  movups  xmm1, xmmword ptr [rax+50h]
0x140034004  movups  xmmword ptr [r8+40h], xmm0
0x140034009  movups  xmm0, xmmword ptr [rax+60h]
0x14003400d  movups  xmmword ptr [r8+50h], xmm1
0x140034012  movups  xmm1, xmmword ptr [rax+70h]
0x140034016  add     rax, rsi
0x140034019  movups  xmmword ptr [r8+60h], xmm0
0x14003401e  movups  xmmword ptr [r8+70h], xmm1
0x140034023  add     r8, rsi
0x140034026  sub     rcx, 1
0x14003402a  jnz     short loc_140033FDA
0x14003402c  mov     rax, [rax]
0x14003402f  inc     r15d
0x140034032  mov     [r8], rax
0x140034035  cmp     r15d, esi
0x140034038  jb      loc_140033F10
0x14003403e  mov     ecx, r15d
0x140034041  mov     eax, 418h
0x140034046  mul     rcx
0x140034049  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140034050  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140034057  cmovb   rax, rcx
0x14003405b  mov     rcx, rax; unsigned __int64
0x14003405e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140034063  mov     rsi, rax
0x140034066  test    rax, rax
0x140034069  jz      short loc_1400340D2
0x14003406b  xor     r12d, r12d
0x14003406e  test    r15d, r15d
0x140034071  jz      short loc_14003409A
0x140034073  mov     eax, r12d
0x140034076  mov     rcx, rbx; this
0x140034079  imul    r8, rax, 418h
0x140034080  imul    rdx, rax, 108h
0x140034087  add     r8, rsi; void *
0x14003408a  add     rdx, rdi; void *
0x14003408d  call    ?UtilConvertDbgFrameToWerFrame@_werDetail@@YAJPEAX0PEAU_WER_STACK_FRAME@@@Z; _werDetail::UtilConvertDbgFrameToWerFrame(void *,void *,_WER_STACK_FRAME *)
0x140034092  inc     r12d
0x140034095  cmp     r12d, r15d
0x140034098  jb      short loc_140034073
0x14003409a  mov     rcx, [rsp+0B60h+var_B10]
0x14003409f  test    rcx, rcx
0x1400340a2  jz      short loc_1400340AA
0x1400340a4  mov     rax, [rdi]
0x1400340a7  mov     [rcx], rax
0x1400340aa  mov     rcx, [r13+0]; void *
0x1400340ae  mov     rax, rsi
0x1400340b1  xor     esi, esi
0x1400340b3  mov     [r13+0], rax
0x1400340b7  test    rcx, rcx
0x1400340ba  jz      short loc_1400340C1
0x1400340bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400340c1  mov     rax, [rsp+0B60h+var_B08]
0x1400340c6  mov     [rax], r15d
0x1400340c9  xor     r15d, r15d
0x1400340cc  jmp     short loc_1400340D8
0x1400340ce  xor     esi, esi
0x1400340d0  xor     edi, edi
0x1400340d2  mov     r15d, 8007000Eh
0x1400340d8  mov     rcx, rbx; hProcess
0x1400340db  call    cs:__imp_SymCleanup
0x1400340e1  test    rsi, rsi
0x1400340e4  jz      short loc_1400340EE
0x1400340e6  mov     rcx, rsi; void *
0x1400340e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400340ee  test    rdi, rdi
0x1400340f1  jz      loc_140033DA5
0x1400340f7  mov     rcx, rdi; void *
0x1400340fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400340ff  jmp     loc_140033DA5
0x140034104  call    cs:__imp_GetLastError
0x14003410a  mov     r15d, eax
0x14003410d  test    eax, eax
  ... truncated ...
```

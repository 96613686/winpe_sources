# UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)

- ea: `0x140036054`
- end: `0x1400365ad`
- name: `?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z`
- size: `1369`
- prototype: `__int64 __usercall@<rax>(DWORD dwProcessId@<ecx>, DWORD dwThreadId@<edx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140035de0`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400041e8`
- `0x140035b38`
- `0x140036054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400361b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400361b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140036560`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1400360e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1400360e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361f7`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1400361a7`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1400361a7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400362de`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400362de`
- `dbghelp!SymGetModuleBase64` at `0x140036360`
- `dbghelp!SymSetExtendedOption` at `0x140036301`
- `dbghelp!SymSetExtendedOption` at `0x140036301`
- `dbghelp!SymCleanup` at `0x140036531`
- `dbghelp!SymCleanup` at `0x140036531`
- `dbghelp!SymInitialize` at `0x14003631b`
- `dbghelp!SymInitialize` at `0x14003631b`
- `dbghelp!SymFunctionTableAccess64` at `0x140036382`
- `dbghelp!StackWalk64` at `0x1400363a8`
- `dbghelp!StackWalk64` at `0x1400363a8`

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
0x140036054  push    rbp
0x140036056  push    rbx
0x140036057  push    rsi
0x140036058  push    rdi
0x140036059  push    r12
0x14003605b  push    r13
0x14003605d  push    r14
0x14003605f  push    r15
0x140036061  lea     rbp, [rsp-0A28h]
0x140036069  sub     rsp, 0B28h
0x140036070  mov     rax, cs:__security_cookie
0x140036077  xor     rax, rsp
0x14003607a  mov     [rbp+0A60h+var_50], rax
0x140036081  mov     rax, [rbp+0A60h+arg_30]
0x140036088  mov     r13, r8
0x14003608b  mov     ebx, edx
0x14003608d  mov     [rsp+0B60h+var_B08], r9
0x140036092  mov     edi, ecx
0x140036094  mov     [rsp+0B60h+var_B10], rax
0x140036099  mov     r12d, 108h
0x14003609f  lea     rcx, [rbp+0A60h+StackFrame]; void *
0x1400360a6  mov     r8d, r12d; Size
0x1400360a9  xor     edx, edx; Val
0x1400360ab  mov     rsi, r9
0x1400360ae  call    memset_0
0x1400360b3  mov     r15d, 4D0h
0x1400360b9  lea     rcx, [rbp+0A60h+Context]; void *
0x1400360c0  mov     r8d, r15d; Size
0x1400360c3  xor     edx, edx; Val
0x1400360c5  call    memset_0
0x1400360ca  test    r13, r13
0x1400360cd  jz      loc_140036580
0x1400360d3  test    rsi, rsi
0x1400360d6  jz      loc_140036580
0x1400360dc  xor     edx, edx; bInheritHandle
0x1400360de  mov     r8d, ebx; dwThreadId
0x1400360e1  lea     ecx, [rdx+48h]; dwDesiredAccess
0x1400360e4  call    cs:__imp_OpenThread
0x1400360eb  nop     dword ptr [rax+rax+00h]
0x1400360f0  mov     r14, rax
0x1400360f3  inc     rax
0x1400360f6  cmp     rax, 1
0x1400360fa  jbe     loc_140036560
0x140036100  mov     r8d, r15d; Size
0x140036103  lea     rcx, [rsp+0B60h+var_B00]; void *
0x140036108  xor     edx, edx; Val
0x14003610a  call    memset_0
0x14003610f  mov     edx, 9
0x140036114  lea     rax, [rbp+0A60h+Context]
0x14003611b  lea     rcx, [rsp+0B60h+var_B00]
0x140036120  lea     esi, [rdx+77h]
0x140036123  movups  xmm0, xmmword ptr [rcx]
0x140036126  movups  xmm1, xmmword ptr [rcx+10h]
0x14003612a  movups  xmmword ptr [rax], xmm0
0x14003612d  movups  xmm0, xmmword ptr [rcx+20h]
0x140036131  movups  xmmword ptr [rax+10h], xmm1
0x140036135  movups  xmm1, xmmword ptr [rcx+30h]
0x140036139  movups  xmmword ptr [rax+20h], xmm0
0x14003613d  movups  xmm0, xmmword ptr [rcx+40h]
0x140036141  movups  xmmword ptr [rax+30h], xmm1
0x140036145  movups  xmm1, xmmword ptr [rcx+50h]
0x140036149  movups  xmmword ptr [rax+40h], xmm0
0x14003614d  movups  xmm0, xmmword ptr [rcx+60h]
0x140036151  movups  xmmword ptr [rax+50h], xmm1
0x140036155  movups  xmm1, xmmword ptr [rcx+70h]
0x140036159  add     rcx, rsi
0x14003615c  movups  xmmword ptr [rax+60h], xmm0
0x140036160  movups  xmmword ptr [rax+70h], xmm1
0x140036164  add     rax, rsi
0x140036167  sub     rdx, 1
0x14003616b  jnz     short loc_140036123
0x14003616d  movups  xmm0, xmmword ptr [rcx]
0x140036170  lea     rdx, [rbp+0A60h+Context]; lpContext
0x140036177  movups  xmm1, xmmword ptr [rcx+10h]
0x14003617b  movups  xmmword ptr [rax], xmm0
0x14003617e  movups  xmm0, xmmword ptr [rcx+20h]
0x140036182  movups  xmmword ptr [rax+10h], xmm1
0x140036186  movups  xmm1, xmmword ptr [rcx+30h]
0x14003618a  movups  xmmword ptr [rax+20h], xmm0
0x14003618e  movups  xmm0, xmmword ptr [rcx+40h]
0x140036192  mov     rcx, r14; hThread
0x140036195  movups  xmmword ptr [rax+30h], xmm1
0x140036199  movups  xmmword ptr [rax+40h], xmm0
0x14003619d  mov     [rbp+0A60h+Context.ContextFlags], 10001Fh
0x1400361a7  call    cs:__imp_GetThreadContext
0x1400361ae  nop     dword ptr [rax+rax+00h]
0x1400361b3  test    eax, eax
0x1400361b5  jnz     short loc_140036208
0x1400361b7  xor     ebx, ebx
0x1400361b9  call    cs:__imp_GetLastError
0x1400361c0  nop     dword ptr [rax+rax+00h]
0x1400361c5  mov     r15d, eax
0x1400361c8  test    eax, eax
0x1400361ca  jle     short loc_1400361D7
0x1400361cc  movzx   r15d, ax
0x1400361d0  or      r15d, 80070000h
0x1400361d7  mov     rcx, r14; hObject
0x1400361da  call    cs:__imp_CloseHandle
0x1400361e1  nop     dword ptr [rax+rax+00h]
0x1400361e6  lea     rax, [rbx+1]
0x1400361ea  cmp     rax, 1
0x1400361ee  jbe     loc_140036586
0x1400361f4  mov     rcx, rbx; hObject
0x1400361f7  call    cs:__imp_CloseHandle
0x1400361fe  nop     dword ptr [rax+rax+00h]
0x140036203  jmp     loc_140036586
0x140036208  mov     r8, r12; Size
0x14003620b  lea     rcx, [rsp+0B60h+var_B00]; void *
0x140036210  xor     edx, edx; Val
0x140036212  call    memset_0
0x140036217  mov     r12d, 2
0x14003621d  lea     rcx, [rbp+0A60h+StackFrame]
0x140036224  mov     edx, r12d
0x140036227  lea     rax, [rsp+0B60h+var_B00]
0x14003622c  movups  xmm0, xmmword ptr [rax]
0x14003622f  movups  xmm1, xmmword ptr [rax+10h]
0x140036233  movups  xmmword ptr [rcx], xmm0
0x140036236  movups  xmm0, xmmword ptr [rax+20h]
0x14003623a  movups  xmmword ptr [rcx+10h], xmm1
0x14003623e  movups  xmm1, xmmword ptr [rax+30h]
0x140036242  movups  xmmword ptr [rcx+20h], xmm0
0x140036246  movups  xmm0, xmmword ptr [rax+40h]
0x14003624a  movups  xmmword ptr [rcx+30h], xmm1
0x14003624e  movups  xmm1, xmmword ptr [rax+50h]
0x140036252  movups  xmmword ptr [rcx+40h], xmm0
0x140036256  movups  xmm0, xmmword ptr [rax+60h]
0x14003625a  movups  xmmword ptr [rcx+50h], xmm1
0x14003625e  movups  xmm1, xmmword ptr [rax+70h]
0x140036262  add     rax, rsi
0x140036265  movups  xmmword ptr [rcx+60h], xmm0
0x140036269  movups  xmmword ptr [rcx+70h], xmm1
0x14003626d  add     rcx, rsi
0x140036270  sub     rdx, 1; bInheritHandle
0x140036274  jnz     short loc_14003622C
0x140036276  mov     rax, [rax]
0x140036279  lea     r15d, [rdx+3]
0x14003627d  mov     [rcx], rax
0x140036280  mov     r8d, edi; dwProcessId
0x140036283  xor     eax, eax
0x140036285  mov     [rbp+0A60h+StackFrame.AddrPC.Mode], r15d
0x14003628c  mov     [rbp+0A60h+StackFrame.AddrPC.Segment], ax
0x140036293  mov     ecx, 410h; dwDesiredAccess
0x140036298  mov     [rbp+0A60h+StackFrame.AddrStack.Segment], ax
0x14003629f  mov     [rbp+0A60h+StackFrame.AddrFrame.Segment], ax
0x1400362a6  mov     rax, [rbp+0A60h+Context.Rip]
0x1400362ad  mov     [rbp+0A60h+StackFrame.AddrPC.Offset], rax
0x1400362b4  mov     rax, [rbp+0A60h+Context.Rsp]
0x1400362bb  mov     [rbp+0A60h+StackFrame.AddrStack.Offset], rax
0x1400362c2  mov     rax, [rbp+0A60h+Context.Rbp]
0x1400362c9  mov     [rbp+0A60h+StackFrame.AddrFrame.Offset], rax
0x1400362d0  mov     [rbp+0A60h+StackFrame.AddrStack.Mode], r15d
0x1400362d7  mov     [rbp+0A60h+StackFrame.AddrFrame.Mode], r15d
0x1400362de  call    cs:__imp_OpenProcess
0x1400362e5  nop     dword ptr [rax+rax+00h]
0x1400362ea  mov     rbx, rax
0x1400362ed  inc     rax
0x1400362f0  cmp     rax, 1
0x1400362f4  jbe     loc_1400361B9
0x1400362fa  lea     edx, [r15-2]; value
0x1400362fe  mov     ecx, r15d; option
0x140036301  call    cs:__imp_SymSetExtendedOption
0x140036308  nop     dword ptr [rax+rax+00h]
0x14003630d  lea     r8d, [r15-2]; fInvadeProcess
0x140036311  mov     rcx, rbx; hProcess
0x140036314  lea     rdx, UserSearchPath; UserSearchPath
0x14003631b  call    cs:__imp_SymInitialize
0x140036322  nop     dword ptr [rax+rax+00h]
0x140036327  test    eax, eax
0x140036329  jz      loc_1400361B9
0x14003632f  mov     r15d, 8400h
0x140036335  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003633c  mov     ecx, r15d; unsigned __int64
0x14003633f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140036344  mov     rdi, rax
0x140036347  test    rax, rax
0x14003634a  jz      loc_140036524
0x140036350  mov     r8d, r15d; Size
0x140036353  xor     edx, edx; Val
0x140036355  mov     rcx, rax; void *
0x140036358  call    memset_0
0x14003635d  xor     r15d, r15d
0x140036360  mov     rax, cs:__imp_SymGetModuleBase64
0x140036367  lea     r9, [rbp+0A60h+StackFrame]; StackFrame
0x14003636e  mov     [rsp+0B60h+TranslateAddress], 0; TranslateAddress
0x140036377  mov     r8, r14; hThread
0x14003637a  mov     [rsp+0B60h+GetModuleBaseRoutine], rax; GetModuleBaseRoutine
0x14003637f  mov     rdx, rbx; hProcess
0x140036382  mov     rax, cs:__imp_SymFunctionTableAccess64
0x140036389  mov     ecx, 8664h; MachineType
0x14003638e  mov     [rsp+0B60h+FunctionTableAccessRoutine], rax; FunctionTableAccessRoutine
0x140036393  lea     rax, [rbp+0A60h+Context]
0x14003639a  mov     [rsp+0B60h+ReadMemoryRoutine], 0; ReadMemoryRoutine
0x1400363a3  mov     [rsp+0B60h+ContextRecord], rax; ContextRecord
0x1400363a8  call    cs:__imp_StackWalk64
0x1400363af  nop     dword ptr [rax+rax+00h]
0x1400363b4  test    eax, eax
0x1400363b6  jz      loc_140036494
0x1400363bc  lea     rcx, [rsp+0B60h+var_B00]
0x1400363c1  mov     rdx, r12
0x1400363c4  lea     rax, [rbp+0A60h+StackFrame]
0x1400363cb  movups  xmm0, xmmword ptr [rax]
0x1400363ce  movups  xmm1, xmmword ptr [rax+10h]
0x1400363d2  movups  xmmword ptr [rcx], xmm0
0x1400363d5  movups  xmm0, xmmword ptr [rax+20h]
0x1400363d9  movups  xmmword ptr [rcx+10h], xmm1
0x1400363dd  movups  xmm1, xmmword ptr [rax+30h]
0x1400363e1  movups  xmmword ptr [rcx+20h], xmm0
0x1400363e5  movups  xmm0, xmmword ptr [rax+40h]
0x1400363e9  movups  xmmword ptr [rcx+30h], xmm1
0x1400363ed  movups  xmm1, xmmword ptr [rax+50h]
0x1400363f1  movups  xmmword ptr [rcx+40h], xmm0
0x1400363f5  movups  xmm0, xmmword ptr [rax+60h]
0x1400363f9  movups  xmmword ptr [rcx+50h], xmm1
0x1400363fd  movups  xmm1, xmmword ptr [rax+70h]
0x140036401  add     rax, rsi
0x140036404  movups  xmmword ptr [rcx+60h], xmm0
0x140036408  movups  xmmword ptr [rcx+70h], xmm1
0x14003640c  add     rcx, rsi
0x14003640f  sub     rdx, 1
0x140036413  jnz     short loc_1400363CB
0x140036415  mov     rax, [rax]
0x140036418  mov     [rcx], rax
0x14003641b  mov     rcx, r12
0x14003641e  mov     eax, r15d
0x140036421  imul    r8, rax, 108h
0x140036428  lea     rax, [rsp+0B60h+var_B00]
0x14003642d  add     r8, rdi
0x140036430  movups  xmm0, xmmword ptr [rax]
0x140036433  movups  xmm1, xmmword ptr [rax+10h]
0x140036437  movups  xmmword ptr [r8], xmm0
0x14003643b  movups  xmm0, xmmword ptr [rax+20h]
0x14003643f  movups  xmmword ptr [r8+10h], xmm1
0x140036444  movups  xmm1, xmmword ptr [rax+30h]
0x140036448  movups  xmmword ptr [r8+20h], xmm0
0x14003644d  movups  xmm0, xmmword ptr [rax+40h]
0x140036451  movups  xmmword ptr [r8+30h], xmm1
0x140036456  movups  xmm1, xmmword ptr [rax+50h]
0x14003645a  movups  xmmword ptr [r8+40h], xmm0
0x14003645f  movups  xmm0, xmmword ptr [rax+60h]
0x140036463  movups  xmmword ptr [r8+50h], xmm1
0x140036468  movups  xmm1, xmmword ptr [rax+70h]
0x14003646c  add     rax, rsi
0x14003646f  movups  xmmword ptr [r8+60h], xmm0
0x140036474  movups  xmmword ptr [r8+70h], xmm1
0x140036479  add     r8, rsi
0x14003647c  sub     rcx, 1
0x140036480  jnz     short loc_140036430
0x140036482  mov     rax, [rax]
0x140036485  inc     r15d
0x140036488  mov     [r8], rax
0x14003648b  cmp     r15d, esi
0x14003648e  jb      loc_140036360
0x140036494  mov     ecx, r15d
0x140036497  mov     eax, 418h
0x14003649c  mul     rcx
0x14003649f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400364a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400364ad  cmovb   rax, rcx
0x1400364b1  mov     rcx, rax; unsigned __int64
0x1400364b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400364b9  mov     rsi, rax
0x1400364bc  test    rax, rax
0x1400364bf  jz      short loc_140036528
0x1400364c1  xor     r12d, r12d
0x1400364c4  test    r15d, r15d
0x1400364c7  jz      short loc_1400364F0
0x1400364c9  mov     eax, r12d
0x1400364cc  mov     rcx, rbx; this
0x1400364cf  imul    r8, rax, 418h
0x1400364d6  imul    rdx, rax, 108h
0x1400364dd  add     r8, rsi; void *
0x1400364e0  add     rdx, rdi; void *
0x1400364e3  call    ?UtilConvertDbgFrameToWerFrame@_werDetail@@YAJPEAX0PEAU_WER_STACK_FRAME@@@Z; _werDetail::UtilConvertDbgFrameToWerFrame(void *,void *,_WER_STACK_FRAME *)
0x1400364e8  inc     r12d
0x1400364eb  cmp     r12d, r15d
0x1400364ee  jb      short loc_1400364C9
0x1400364f0  mov     rcx, [rsp+0B60h+var_B10]
0x1400364f5  test    rcx, rcx
0x1400364f8  jz      short loc_140036500
0x1400364fa  mov     rax, [rdi]
0x1400364fd  mov     [rcx], rax
0x140036500  mov     rcx, [r13+0]; void *
0x140036504  mov     rax, rsi
0x140036507  xor     esi, esi
0x140036509  mov     [r13+0], rax
0x14003650d  test    rcx, rcx
0x140036510  jz      short loc_140036517
0x140036512  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140036517  mov     rax, [rsp+0B60h+var_B08]
0x14003651c  mov     [rax], r15d
0x14003651f  xor     r15d, r15d
0x140036522  jmp     short loc_14003652E
0x140036524  xor     esi, esi
0x140036526  xor     edi, edi
0x140036528  mov     r15d, 8007000Eh
0x14003652e  mov     rcx, rbx; hProcess
0x140036531  call    cs:__imp_SymCleanup
0x140036538  nop     dword ptr [rax+rax+00h]
0x14003653d  test    rsi, rsi
0x140036540  jz      short loc_14003654A
  ... truncated ...
```

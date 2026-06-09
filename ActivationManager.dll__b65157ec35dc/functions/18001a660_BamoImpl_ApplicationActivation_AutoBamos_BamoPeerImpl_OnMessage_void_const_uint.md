# BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl::OnMessage(void const *,uint)

- ea: `0x18001a660`
- end: `0x18001ab70`
- name: `?OnMessage@BamoPeerImpl@ApplicationActivation_AutoBamos@BamoImpl@@UEAAJPEBXI@Z`
- size: `1296`
- prototype: `__int64 __fastcall(BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl *__hidden this, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001a660`
- `0x18001ab80`
- `0x18005b840`
- `0x18005ba40`
- `0x18007ac88`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a70f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a70f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aacd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aacd`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18001aaa4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18001aaa4`
- `CoreMessaging!CoreUICallReceive` at `0x18001a6a4`
- `CoreMessaging!CoreUICallReceive` at `0x18001a6a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl::OnMessage(
        BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl *this,
        const void *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rbp
  _QWORD *v9; // rsi
  __int64 v10; // rax
  int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v11 = (int)this;
  v3 = CoreUICallReceive(
         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 32LL) + 80LL),
         &IBamoPeer_ApplicationActivation_AutoBamos_Receive<BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl>::Type,
         &Microsoft::CoreUI::MessageCall::ApplicationActivation_g_parameters_0TuT0PGbKlAHjshO1oOUJ1ZZeRQ_BamoGroup$25977ff8,
         41);
  v4 = v3;
  if ( v3 == -2018375668 )
  {
    v6 = *(_QWORD *)(*((_QWORD *)this + 3) + 32LL);
    v7 = *(_QWORD *)(v6 + 96);
    v13 = 0;
    v8 = *(_QWORD *)(v7 + 32);
    if ( *(_DWORD *)(v8 + 184) != GetCurrentThreadId() )
    {
      v13 = v7;
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 16) + 24LL))(*(_QWORD *)(v8 + 16));
      *(_DWORD *)(v8 + 184) = GetCurrentThreadId();
    }
    if ( *(_DWORD *)(v6 + 232) < 0xAu )
    {
      v9 = operator new(0x218u);
      memset_0(v9, 0, 0x218u);
      v10 = *(_QWORD *)(v6 + 224);
      if ( v10 )
      {
        v9[66] = *(_QWORD *)(v10 + 528);
        *(_QWORD *)(*(_QWORD *)(v6 + 224) + 528LL) = v9;
        *(_QWORD *)(v6 + 224) = v9;
      }
      else
      {
        *(_QWORD *)(v6 + 224) = v9;
        v9[66] = v9;
        v9 = *(_QWORD **)(v6 + 224);
      }
      ++*(_DWORD *)(v6 + 232);
    }
    else
    {
      v9 = *(_QWORD **)(*(_QWORD *)(v6 + 224) + 528LL);
      *(_QWORD *)(v6 + 224) = v9;
    }
    v9[2] = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 24LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 32LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 40LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 48LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 56LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 64LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 72LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 80LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 88LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 96LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 104LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 112LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 120LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 128LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 136LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 144LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 152LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 160LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 168LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 176LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 184LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 192LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 200LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 208LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 216LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 224LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 232LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 240LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 248LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 256LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 264LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 272LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 280LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 288LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 296LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 304LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 312LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 320LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 328LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 336LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 344LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 352LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 360LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 368LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 376LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 384LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 392LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 400LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 408LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 416LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 424LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 432LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 440LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 448LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 456LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 464LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 472LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 480LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 488LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 496LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 504LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 512LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v6 + 224) + 520LL) = 0;
    *(_WORD *)(*(_QWORD *)(v6 + 224) + 12LL) = RtlCaptureStackBackTrace(
                                                 1u,
                                                 0x40u,
                                                 (PVOID *)(*(_QWORD *)(v6 + 224) + 16LL),
                                                 0);
    **(_DWORD **)(v6 + 224) = -2018375668;
    GetSystemTimeAsFileTime((LPFILETIME)(*(_QWORD *)(v6 + 224) + 4LL));
    ++*(_DWORD *)(v6 + 236);
    Microsoft::BamoImpl::InternalLock::~InternalLock((Microsoft::BamoImpl::InternalLock *)&v13);
  }
  else if ( v3 < 0 )
  {
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2E9B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\applicationactivationwatcher\\codegen\\objfre\\amd64\\"
                    "ApplicationActivation.Bamo.h",
      (const char *)(unsigned int)v3,
      v11);
  }
  return v4;
}

```

## disassembly

```asm
0x18001a660  mov     [rsp+arg_8], rbx
0x18001a665  mov     [rsp+arg_10], rbp
0x18001a66a  push    rsi
0x18001a66b  push    rdi
0x18001a66c  push    r14
0x18001a66e  sub     rsp, 40h
0x18001a672  mov     rdi, rcx
0x18001a675  mov     rax, [rcx+18h]
0x18001a679  mov     rcx, [rax+20h]
0x18001a67d  mov     [rsp+58h+var_28], r8d
0x18001a682  mov     [rsp+58h+var_30], rdx
0x18001a687  mov     qword ptr [rsp+58h+var_38], rdi; int
0x18001a68c  mov     r9d, 29h ; ')'
0x18001a692  lea     r8, ?ApplicationActivation_g_parameters_0TuT0PGbKlAHjshO1oOUJ1ZZeRQ_BamoGroup$25977ff8@MessageCall@CoreUI@Microsoft@@3QBEB; uchar const near * const Microsoft::CoreUI::MessageCall::ApplicationActivation_g_parameters_0TuT0PGbKlAHjshO1oOUJ1ZZeRQ_BamoGroup$25977ff8
0x18001a699  lea     rdx, ?Type@?$IBamoPeer_ApplicationActivation_AutoBamos_Receive@VBamoPeerImpl@ApplicationActivation_AutoBamos@BamoImpl@@@@2UMsgCallTypeDefinition@@B; MsgCallTypeDefinition const IBamoPeer_ApplicationActivation_AutoBamos_Receive<BamoImpl::ApplicationActivation_AutoBamos::BamoPeerImpl>::Type
0x18001a6a0  mov     rcx, [rcx+50h]
0x18001a6a4  call    cs:__imp_CoreUICallReceive
0x18001a6aa  mov     ebx, eax
0x18001a6ac  cmp     eax, 87B2080Ch
0x18001a6b1  jz      short loc_18001A6D0
0x18001a6b3  test    eax, eax
0x18001a6b5  js      loc_18001AB56
0x18001a6bb  mov     eax, ebx
0x18001a6bd  mov     rbx, [rsp+58h+arg_8]
0x18001a6c2  mov     rbp, [rsp+58h+arg_10]
0x18001a6c7  add     rsp, 40h
0x18001a6cb  pop     r14
0x18001a6cd  pop     rdi
0x18001a6ce  pop     rsi
0x18001a6cf  retn
0x18001a6d0  mov     rax, [rdi+18h]
0x18001a6d4  mov     rdi, [rax+20h]
0x18001a6d8  mov     rsi, [rdi+60h]
0x18001a6dc  xor     r14d, r14d
0x18001a6df  mov     [rsp+58h+arg_0], r14
0x18001a6e4  mov     rbp, [rsi+20h]
0x18001a6e8  call    cs:__imp_GetCurrentThreadId
0x18001a6ee  cmp     [rbp+0B8h], eax
0x18001a6f4  jz      short loc_18001A71B
0x18001a6f6  mov     [rsp+58h+arg_0], rsi
0x18001a6fb  lock inc dword ptr [rsi+8]
0x18001a6ff  mov     rcx, [rbp+10h]
0x18001a703  mov     rax, [rcx]
0x18001a706  mov     rax, [rax+18h]
0x18001a70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a70f  call    cs:__imp_GetCurrentThreadId
0x18001a715  mov     [rbp+0B8h], eax
0x18001a71b  cmp     dword ptr [rdi+0E8h], 0Ah
0x18001a722  jb      loc_18001AAE8
0x18001a728  mov     rax, [rdi+0E0h]
0x18001a72f  mov     rsi, [rax+210h]
0x18001a736  mov     [rdi+0E0h], rsi
0x18001a73d  mov     [rsi+10h], r14
0x18001a741  mov     rax, [rdi+0E0h]
0x18001a748  mov     [rax+18h], r14
0x18001a74c  mov     rax, [rdi+0E0h]
0x18001a753  mov     [rax+20h], r14
0x18001a757  mov     rax, [rdi+0E0h]
0x18001a75e  mov     [rax+28h], r14
0x18001a762  mov     rax, [rdi+0E0h]
0x18001a769  mov     [rax+30h], r14
0x18001a76d  mov     rax, [rdi+0E0h]
0x18001a774  mov     [rax+38h], r14
0x18001a778  mov     rax, [rdi+0E0h]
0x18001a77f  mov     [rax+40h], r14
0x18001a783  mov     rax, [rdi+0E0h]
0x18001a78a  mov     [rax+48h], r14
0x18001a78e  mov     rax, [rdi+0E0h]
0x18001a795  mov     [rax+50h], r14
0x18001a799  mov     rax, [rdi+0E0h]
0x18001a7a0  mov     [rax+58h], r14
0x18001a7a4  mov     rax, [rdi+0E0h]
0x18001a7ab  mov     [rax+60h], r14
0x18001a7af  mov     rax, [rdi+0E0h]
0x18001a7b6  mov     [rax+68h], r14
0x18001a7ba  mov     rax, [rdi+0E0h]
0x18001a7c1  mov     [rax+70h], r14
0x18001a7c5  mov     rax, [rdi+0E0h]
0x18001a7cc  mov     [rax+78h], r14
0x18001a7d0  mov     rax, [rdi+0E0h]
0x18001a7d7  mov     [rax+80h], r14
0x18001a7de  mov     rax, [rdi+0E0h]
0x18001a7e5  mov     [rax+88h], r14
0x18001a7ec  mov     rax, [rdi+0E0h]
0x18001a7f3  mov     [rax+90h], r14
0x18001a7fa  mov     rax, [rdi+0E0h]
0x18001a801  mov     [rax+98h], r14
0x18001a808  mov     rax, [rdi+0E0h]
0x18001a80f  mov     [rax+0A0h], r14
0x18001a816  mov     rax, [rdi+0E0h]
0x18001a81d  mov     [rax+0A8h], r14
0x18001a824  mov     rax, [rdi+0E0h]
0x18001a82b  mov     [rax+0B0h], r14
0x18001a832  mov     rax, [rdi+0E0h]
0x18001a839  mov     [rax+0B8h], r14
0x18001a840  mov     rax, [rdi+0E0h]
0x18001a847  mov     [rax+0C0h], r14
0x18001a84e  mov     rax, [rdi+0E0h]
0x18001a855  mov     [rax+0C8h], r14
0x18001a85c  mov     rax, [rdi+0E0h]
0x18001a863  mov     [rax+0D0h], r14
0x18001a86a  mov     rax, [rdi+0E0h]
0x18001a871  mov     [rax+0D8h], r14
0x18001a878  mov     rax, [rdi+0E0h]
0x18001a87f  mov     [rax+0E0h], r14
0x18001a886  mov     rax, [rdi+0E0h]
0x18001a88d  mov     [rax+0E8h], r14
0x18001a894  mov     rax, [rdi+0E0h]
0x18001a89b  mov     [rax+0F0h], r14
0x18001a8a2  mov     rax, [rdi+0E0h]
0x18001a8a9  mov     [rax+0F8h], r14
0x18001a8b0  mov     rax, [rdi+0E0h]
0x18001a8b7  mov     [rax+100h], r14
0x18001a8be  mov     rax, [rdi+0E0h]
0x18001a8c5  mov     [rax+108h], r14
0x18001a8cc  mov     rax, [rdi+0E0h]
0x18001a8d3  mov     [rax+110h], r14
0x18001a8da  mov     rax, [rdi+0E0h]
0x18001a8e1  mov     [rax+118h], r14
0x18001a8e8  mov     rax, [rdi+0E0h]
0x18001a8ef  mov     [rax+120h], r14
0x18001a8f6  mov     rax, [rdi+0E0h]
0x18001a8fd  mov     [rax+128h], r14
0x18001a904  mov     rax, [rdi+0E0h]
0x18001a90b  mov     [rax+130h], r14
0x18001a912  mov     rax, [rdi+0E0h]
0x18001a919  mov     [rax+138h], r14
0x18001a920  mov     rax, [rdi+0E0h]
0x18001a927  mov     [rax+140h], r14
0x18001a92e  mov     rax, [rdi+0E0h]
0x18001a935  mov     [rax+148h], r14
0x18001a93c  mov     rax, [rdi+0E0h]
0x18001a943  mov     [rax+150h], r14
0x18001a94a  mov     rax, [rdi+0E0h]
0x18001a951  mov     [rax+158h], r14
0x18001a958  mov     rax, [rdi+0E0h]
0x18001a95f  mov     [rax+160h], r14
0x18001a966  mov     rax, [rdi+0E0h]
0x18001a96d  mov     [rax+168h], r14
0x18001a974  mov     rax, [rdi+0E0h]
0x18001a97b  mov     [rax+170h], r14
0x18001a982  mov     rax, [rdi+0E0h]
0x18001a989  mov     [rax+178h], r14
0x18001a990  mov     rax, [rdi+0E0h]
0x18001a997  mov     [rax+180h], r14
0x18001a99e  mov     rax, [rdi+0E0h]
0x18001a9a5  mov     [rax+188h], r14
0x18001a9ac  mov     rax, [rdi+0E0h]
0x18001a9b3  mov     [rax+190h], r14
0x18001a9ba  mov     rax, [rdi+0E0h]
0x18001a9c1  mov     [rax+198h], r14
0x18001a9c8  mov     rax, [rdi+0E0h]
0x18001a9cf  mov     [rax+1A0h], r14
0x18001a9d6  mov     rax, [rdi+0E0h]
0x18001a9dd  mov     [rax+1A8h], r14
0x18001a9e4  mov     rax, [rdi+0E0h]
0x18001a9eb  mov     [rax+1B0h], r14
0x18001a9f2  mov     rax, [rdi+0E0h]
0x18001a9f9  mov     [rax+1B8h], r14
0x18001aa00  mov     rax, [rdi+0E0h]
0x18001aa07  mov     [rax+1C0h], r14
0x18001aa0e  mov     rax, [rdi+0E0h]
0x18001aa15  mov     [rax+1C8h], r14
0x18001aa1c  mov     rax, [rdi+0E0h]
0x18001aa23  mov     [rax+1D0h], r14
0x18001aa2a  mov     rax, [rdi+0E0h]
0x18001aa31  mov     [rax+1D8h], r14
0x18001aa38  mov     rax, [rdi+0E0h]
0x18001aa3f  mov     [rax+1E0h], r14
0x18001aa46  mov     rax, [rdi+0E0h]
0x18001aa4d  mov     [rax+1E8h], r14
0x18001aa54  mov     rax, [rdi+0E0h]
0x18001aa5b  mov     [rax+1F0h], r14
0x18001aa62  mov     rax, [rdi+0E0h]
0x18001aa69  mov     [rax+1F8h], r14
0x18001aa70  mov     rax, [rdi+0E0h]
0x18001aa77  mov     [rax+200h], r14
0x18001aa7e  mov     rax, [rdi+0E0h]
0x18001aa85  mov     [rax+208h], r14
0x18001aa8c  mov     r8, [rdi+0E0h]
0x18001aa93  add     r8, 10h; BackTrace
0x18001aa97  xor     r9d, r9d; BackTraceHash
0x18001aa9a  mov     edx, 40h ; '@'; FramesToCapture
0x18001aa9f  mov     ecx, 1; FramesToSkip
0x18001aaa4  call    cs:__imp_RtlCaptureStackBackTrace
0x18001aaaa  mov     rcx, [rdi+0E0h]
0x18001aab1  mov     [rcx+0Ch], ax
0x18001aab5  mov     rax, [rdi+0E0h]
0x18001aabc  mov     dword ptr [rax], 87B2080Ch
0x18001aac2  mov     rcx, [rdi+0E0h]
0x18001aac9  add     rcx, 4; lpSystemTimeAsFileTime
0x18001aacd  call    cs:__imp_GetSystemTimeAsFileTime
0x18001aad3  inc     dword ptr [rdi+0ECh]
0x18001aad9  lea     rcx, [rsp+58h+arg_0]; this
0x18001aade  call    ??1InternalLock@BamoImpl@Microsoft@@QEAA@XZ; Microsoft::BamoImpl::InternalLock::~InternalLock(void)
0x18001aae3  jmp     loc_18001A6BB
0x18001aae8  mov     ecx, 218h; Size
0x18001aaed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aaf2  mov     rsi, rax
0x18001aaf5  xor     edx, edx; Val
0x18001aaf7  mov     r8d, 218h; Size
0x18001aafd  mov     rcx, rax; void *
0x18001ab00  call    memset_0
0x18001ab05  mov     rax, [rdi+0E0h]
0x18001ab0c  test    rax, rax
0x18001ab0f  jnz     short loc_18001AB28
0x18001ab11  mov     [rdi+0E0h], rsi
0x18001ab18  mov     [rsi+210h], rsi
0x18001ab1f  mov     rsi, [rdi+0E0h]
0x18001ab26  jmp     short loc_18001AB4B
0x18001ab28  mov     rax, [rax+210h]
0x18001ab2f  mov     [rsi+210h], rax
0x18001ab36  mov     rax, [rdi+0E0h]
0x18001ab3d  mov     [rax+210h], rsi
0x18001ab44  mov     [rdi+0E0h], rsi
0x18001ab4b  inc     dword ptr [rdi+0E8h]
0x18001ab51  jmp     loc_18001A73D
0x18001ab56  mov     rcx, [rsp+58h]; this
0x18001ab5b  mov     r9d, ebx; char *
0x18001ab5e  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001ab65  mov     edx, 2E9Bh; void *
0x18001ab6a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```

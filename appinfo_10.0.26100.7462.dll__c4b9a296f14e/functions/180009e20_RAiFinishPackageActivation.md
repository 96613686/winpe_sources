# RAiFinishPackageActivation

- ea: `0x180009e20`
- end: `0x18000a1dc`
- name: `RAiFinishPackageActivation`
- size: `956`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009e20`
- `0x18000a1f0`
- `0x1800234a0`
- `0x1800241b4`
- `0x180026ba4`
- `0x180028604`
- `0x18002bf84`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180009ffe`
- `msvcrt!wcsrchr` at `0x180009ffe`
- `msvcrt!wcsnlen` at `0x18000a03d`
- `msvcrt!wcsnlen` at `0x18000a0a6`
- `msvcrt!wcsnlen` at `0x18000a0ce`
- `msvcrt!wcsnlen` at `0x18000a100`
- `msvcrt!wcsnlen` at `0x18000a03d`
- `msvcrt!wcsnlen` at `0x18000a0a6`
- `msvcrt!wcsnlen` at `0x18000a0ce`
- `msvcrt!wcsnlen` at `0x18000a100`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000a1ac`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000a1ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a158`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a158`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180009f96`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180009f96`
- `ntdll!EtwEventWrite` at `0x18000a142`
- `ntdll!EtwEventWrite` at `0x18000a142`

## pseudocode

```c
RPC_STATUS __fastcall RAiFinishPackageActivation(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        void *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        void *a9)
{
  HANDLE v9; // rax
  __int64 *v14; // rax
  int v15; // edi
  const unsigned __int16 *v16; // rax
  wchar_t *v17; // rbx
  wchar_t *v18; // rax
  int v19; // eax
  wchar_t *v20; // rsi
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+74h] [rbp-8Ch] BYREF
  wchar_t *Str; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hProcess; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+88h] [rbp-78h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+98h] [rbp-68h] BYREF
  int Reply; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v39; // [rsp+D0h] [rbp-30h] BYREF
  char v40; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v41[3]; // [rsp+140h] [rbp+40h] BYREF
  int v42; // [rsp+158h] [rbp+58h]
  int v43; // [rsp+15Ch] [rbp+5Ch]
  wchar_t *v44; // [rsp+160h] [rbp+60h]
  int v45; // [rsp+168h] [rbp+68h]
  int v46; // [rsp+16Ch] [rbp+6Ch]
  WCHAR *v47; // [rsp+170h] [rbp+70h]
  int v48; // [rsp+178h] [rbp+78h]
  int v49; // [rsp+17Ch] [rbp+7Ch]
  const wchar_t *v50; // [rsp+180h] [rbp+80h]
  int v51; // [rsp+188h] [rbp+88h]
  int v52; // [rsp+18Ch] [rbp+8Ch]
  __int64 v53; // [rsp+190h] [rbp+90h] BYREF
  int v54; // [rsp+198h] [rbp+98h]
  wchar_t v55; // [rsp+19Ch] [rbp+9Ch]
  wchar_t Source[128]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v9 = a9;
  hProcess = a9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids);
    v9 = hProcess;
  }
  v39 = v9;
  v35 = a6;
  v37 = a8;
  v26 = 0;
  v27 = 0;
  v34 = a7;
  v30 = a5;
  v36 = a4;
  hProcess = a3;
  v38 = a2;
  memset_0(Source, 0, sizeof(Source));
  Str = 0;
  v14 = (__int64 *)lambda_d2d6648289e25899624fc46bf4b71f49_::_lambda_d2d6648289e25899624fc46bf4b71f49_(
                     (unsigned int)&v40,
                     (unsigned int)&v39,
                     (unsigned int)&v38,
                     (unsigned int)&v37,
                     (__int64)&v27,
                     (__int64)&hProcess,
                     (__int64)&v36,
                     (__int64)Source,
                     (__int64)&Str,
                     (__int64)&v26,
                     (__int64)&v35,
                     (__int64)&v34,
                     (__int64)&v30);
  v15 = lambda_d2d6648289e25899624fc46bf4b71f49_::operator()(v14);
  memset_0(applicationUserModelId, 0, 0x104u);
  applicationUserModelIdLength = 130;
  GetApplicationUserModelId(hProcess, &applicationUserModelIdLength, applicationUserModelId);
  if ( v15 >= 0 )
  {
    v17 = Str;
    if ( Str )
    {
      v18 = wcsrchr(Str, 0x5Cu);
      if ( v18 )
        v17 = v18 + 1;
    }
    else
    {
      v17 = 0;
    }
    v32 = v27;
    v41[1] = 4;
    v41[0] = &v32;
    v19 = wcsnlen(Source, 0x7Fu);
    v41[2] = Source;
    v43 = 0;
    v42 = 2 * (v19 + 1);
    v20 = (wchar_t *)&v53;
    v54 = *(_DWORD *)L"L>";
    v55 = aNull_1[6];
    v21 = 7;
    v53 = *(_QWORD *)L"<NULL>";
    if ( v17 )
    {
      v20 = v17;
      v21 = wcsnlen(v17, 0x104u) + 1;
    }
    v44 = v20;
    v45 = 2 * v21;
    v46 = 0;
    v22 = wcsnlen(applicationUserModelId, 0x82u);
    v49 = 0;
    v47 = applicationUserModelId;
    v48 = 2 * (v22 + 1);
    v23 = wcsnlen(L"[FinishPackageActivation]", 0x104u);
    v50 = L"[FinishPackageActivation]";
    v51 = 2 * (v23 + 1);
    v52 = 0;
    if ( g_EventRegHandleAppModelRuntime )
      EtwEventWrite(g_EventRegHandleAppModelRuntime, &AppModelDesktopAppXProcessStartSuccess, 5, v41);
  }
  else
  {
    if ( Str )
      v16 = AipJustFileName(Str);
    else
      v16 = 0;
    AipLogDesktopAppXProcessStartFailure(
      v26,
      (unsigned int)v15,
      Source,
      v16,
      applicationUserModelId,
      L"[FinishPackageActivation]");
  }
  if ( Str )
    LocalFree(Str);
  if ( v15 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
      (unsigned int)v15);
  }
  v24 = (unsigned __int16)v15;
  if ( v15 >= 0 )
    v24 = 0;
  Reply = v24;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180009e20  push    rbp
0x180009e22  push    rbx
0x180009e23  push    rsi
0x180009e24  push    rdi
0x180009e25  push    r12
0x180009e27  push    r13
0x180009e29  push    r14
0x180009e2b  push    r15
0x180009e2d  lea     rbp, [rsp-2C8h]
0x180009e35  sub     rsp, 3C8h
0x180009e3c  mov     rax, cs:__security_cookie
0x180009e43  xor     rax, rsp
0x180009e46  mov     [rbp+300h+var_50], rax
0x180009e4d  mov     rax, [rbp+300h+arg_40]
0x180009e54  mov     rsi, r9
0x180009e57  mov     r15, [rbp+300h+arg_28]
0x180009e5e  mov     rdi, r8
0x180009e61  mov     r12, [rbp+300h+arg_30]
0x180009e68  mov     rbx, rdx
0x180009e6b  mov     r13, [rbp+300h+arg_38]
0x180009e72  mov     r14, rcx
0x180009e75  mov     [rbp+300h+hProcess], rax
0x180009e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e80  lea     rdx, WPP_GLOBAL_Control
0x180009e87  cmp     rcx, rdx
0x180009e8a  jz      short loc_180009EAB
0x180009e8c  test    byte ptr [rcx+1Ch], 1
0x180009e90  jz      short loc_180009EAB
0x180009e92  mov     rcx, [rcx+10h]
0x180009e96  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x180009e9d  mov     edx, 29h ; ')'
0x180009ea2  call    WPP_SF_
0x180009ea7  mov     rax, [rbp+300h+hProcess]
0x180009eab  mov     [rbp+300h+var_330], rax
0x180009eaf  lea     rcx, [rbp+300h+Source]; void *
0x180009eb6  mov     eax, [rbp+300h+arg_20]
0x180009ebc  xor     edx, edx; Val
0x180009ebe  mov     [rbp+300h+var_350], r15
0x180009ec2  mov     r8d, 100h; Size
0x180009ec8  xor     r15d, r15d
0x180009ecb  mov     [rbp+300h+var_340], r13
0x180009ecf  mov     [rsp+400h+var_390], r15d
0x180009ed4  mov     [rsp+400h+var_38C], r15d
0x180009ed9  mov     [rbp+300h+var_358], r12
0x180009edd  mov     [rbp+300h+var_378], eax
0x180009ee0  mov     [rbp+300h+var_348], rsi
0x180009ee4  mov     [rbp+300h+hProcess], rdi
0x180009ee8  mov     [rbp+300h+var_338], rbx
0x180009eec  call    memset_0
0x180009ef1  lea     rax, [rbp+300h+var_378]
0x180009ef5  mov     [rsp+400h+Str], r15
0x180009efa  mov     [rsp+400h+var_3A0], rax
0x180009eff  lea     r9, [rbp+300h+var_340]
0x180009f03  lea     rax, [rbp+300h+var_358]
0x180009f07  mov     [rsp+400h+var_3A8], rax
0x180009f0c  lea     r8, [rbp+300h+var_338]
0x180009f10  lea     rax, [rbp+300h+var_350]
0x180009f14  mov     [rsp+400h+var_3B0], rax
0x180009f19  lea     rdx, [rbp+300h+var_330]
0x180009f1d  lea     rax, [rsp+400h+var_390]
0x180009f22  mov     [rsp+400h+var_3B8], rax
0x180009f27  lea     rcx, [rbp+300h+var_328]
0x180009f2b  lea     rax, [rsp+400h+Str]
0x180009f30  mov     [rsp+400h+var_3C0], rax
0x180009f35  lea     rax, [rbp+300h+Source]
0x180009f3c  mov     [rsp+400h+var_3C8], rax
0x180009f41  lea     rax, [rbp+300h+var_348]
0x180009f45  mov     [rsp+400h+var_3D0], rax
0x180009f4a  lea     rax, [rbp+300h+hProcess]
0x180009f4e  mov     [rsp+400h+var_3D8], rax
0x180009f53  lea     rax, [rsp+400h+var_38C]
0x180009f58  mov     [rsp+400h+var_3E0], rax
0x180009f5d  call    _lambda_d2d6648289e25899624fc46bf4b71f49____lambda_d2d6648289e25899624fc46bf4b71f49_
0x180009f62  mov     rcx, rax
0x180009f65  call    _lambda_d2d6648289e25899624fc46bf4b71f49___operator__
0x180009f6a  xor     edx, edx; Val
0x180009f6c  lea     rcx, [rbp+300h+applicationUserModelId]; void *
0x180009f73  mov     r8d, 104h; Size
0x180009f79  mov     edi, eax
0x180009f7b  call    memset_0
0x180009f80  mov     rcx, [rbp+300h+hProcess]; hProcess
0x180009f84  lea     r8, [rbp+300h+applicationUserModelId]; applicationUserModelId
0x180009f8b  lea     rdx, [rbp+300h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180009f8f  mov     [rbp+300h+applicationUserModelIdLength], 82h
0x180009f96  call    cs:__imp_GetApplicationUserModelId
0x180009f9d  nop     dword ptr [rax+rax+00h]
0x180009fa2  test    edi, edi
0x180009fa4  jns     short loc_180009FEC
0x180009fa6  mov     rcx, [rsp+400h+Str]; unsigned __int16 *
0x180009fab  test    rcx, rcx
0x180009fae  jz      short loc_180009FB7
0x180009fb0  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x180009fb5  jmp     short loc_180009FBA
0x180009fb7  mov     rax, r15
0x180009fba  lea     rcx, [rbp+300h+applicationUserModelId]
0x180009fc1  mov     r9, rax
0x180009fc4  lea     rbx, aFinishpackagea_0; "[FinishPackageActivation]"
0x180009fcb  mov     edx, edi
0x180009fcd  mov     [rsp+400h+var_3D8], rbx
0x180009fd2  lea     r8, [rbp+300h+Source]
0x180009fd9  mov     [rsp+400h+var_3E0], rcx
0x180009fde  mov     ecx, [rsp+400h+var_390]
0x180009fe2  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x180009fe7  jmp     loc_18000A14E
0x180009fec  mov     rbx, [rsp+400h+Str]
0x180009ff1  test    rbx, rbx
0x180009ff4  jz      short loc_18000A017
0x180009ff6  mov     edx, 5Ch ; '\'; Ch
0x180009ffb  mov     rcx, rbx; Str
0x180009ffe  call    cs:__imp_wcsrchr
0x18000a005  nop     dword ptr [rax+rax+00h]
0x18000a00a  test    rax, rax
0x18000a00d  lea     rcx, [rax+2]
0x18000a011  cmovnz  rbx, rcx
0x18000a015  jmp     short loc_18000A01A
0x18000a017  mov     rbx, r15
0x18000a01a  mov     eax, [rsp+400h+var_38C]
0x18000a01e  lea     rcx, [rbp+300h+Source]; Source
0x18000a025  mov     [rbp+300h+var_368], eax
0x18000a028  mov     edx, 7Fh; MaxCount
0x18000a02d  lea     rax, [rbp+300h+var_368]
0x18000a031  mov     [rbp+300h+var_2B8], 4
0x18000a039  mov     [rbp+300h+var_2C0], rax
0x18000a03d  call    cs:__imp_wcsnlen
0x18000a044  nop     dword ptr [rax+rax+00h]
0x18000a049  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x18000a051  lea     rcx, [rbp+300h+Source]
0x18000a058  inc     rax
0x18000a05b  mov     [rbp+300h+var_2B0], rcx
0x18000a05f  add     eax, eax
0x18000a061  mov     [rbp+300h+var_2A4], r15d
0x18000a065  mov     [rbp+300h+var_2A8], eax
0x18000a068  lea     rsi, [rbp+300h+var_270]
0x18000a06f  mov     eax, dword ptr cs:aNull_1+8; "L>"
0x18000a075  mov     [rbp+300h+var_268], eax
0x18000a07b  movzx   eax, word ptr cs:aNull_1+0Ch; ""
0x18000a082  mov     [rbp+300h+var_264], ax
0x18000a089  mov     eax, 7
0x18000a08e  movsd   [rbp+300h+var_270], xmm0
0x18000a096  test    rbx, rbx
0x18000a099  jz      short loc_18000A0B5
0x18000a09b  mov     edx, 104h; MaxCount
0x18000a0a0  mov     rcx, rbx; Source
0x18000a0a3  mov     rsi, rbx
0x18000a0a6  call    cs:__imp_wcsnlen
0x18000a0ad  nop     dword ptr [rax+rax+00h]
0x18000a0b2  inc     rax
0x18000a0b5  add     eax, eax
0x18000a0b7  mov     [rbp+300h+var_2A0], rsi
0x18000a0bb  mov     edx, 82h; MaxCount
0x18000a0c0  mov     [rbp+300h+var_298], eax
0x18000a0c3  lea     rcx, [rbp+300h+applicationUserModelId]; Source
0x18000a0ca  mov     [rbp+300h+var_294], r15d
0x18000a0ce  call    cs:__imp_wcsnlen
0x18000a0d5  nop     dword ptr [rax+rax+00h]
0x18000a0da  lea     rcx, [rbp+300h+applicationUserModelId]
0x18000a0e1  mov     [rbp+300h+var_284], r15d
0x18000a0e5  inc     rax
0x18000a0e8  mov     [rbp+300h+var_290], rcx
0x18000a0ec  add     eax, eax
0x18000a0ee  lea     rbx, aFinishpackagea_0; "[FinishPackageActivation]"
0x18000a0f5  mov     edx, 104h; MaxCount
0x18000a0fa  mov     [rbp+300h+var_288], eax
0x18000a0fd  mov     rcx, rbx; Source
0x18000a100  call    cs:__imp_wcsnlen
0x18000a107  nop     dword ptr [rax+rax+00h]
0x18000a10c  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18000a113  inc     rax
0x18000a116  add     eax, eax
0x18000a118  mov     [rbp+300h+var_280], rbx
0x18000a11f  mov     [rbp+300h+var_278], eax
0x18000a125  mov     [rbp+300h+var_274], r15d
0x18000a12c  test    rcx, rcx
0x18000a12f  jz      short loc_18000A14E
0x18000a131  lea     r9, [rbp+300h+var_2C0]
0x18000a135  mov     r8d, 5
0x18000a13b  lea     rdx, AppModelDesktopAppXProcessStartSuccess
0x18000a142  call    cs:__imp_EtwEventWrite
0x18000a149  nop     dword ptr [rax+rax+00h]
0x18000a14e  mov     rcx, [rsp+400h+Str]; hMem
0x18000a153  test    rcx, rcx
0x18000a156  jz      short loc_18000A164
0x18000a158  call    cs:__imp_LocalFree
0x18000a15f  nop     dword ptr [rax+rax+00h]
0x18000a164  test    edi, edi
0x18000a166  jns     short loc_18000A199
0x18000a168  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a16f  lea     rax, WPP_GLOBAL_Control
0x18000a176  cmp     rcx, rax
0x18000a179  jz      short loc_18000A199
0x18000a17b  test    byte ptr [rcx+1Ch], 1
0x18000a17f  jz      short loc_18000A199
0x18000a181  mov     rcx, [rcx+10h]
0x18000a185  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x18000a18c  mov     edx, 2Ah ; '*'
0x18000a191  mov     r9d, edi
0x18000a194  call    WPP_SF_D
0x18000a199  test    edi, edi
0x18000a19b  movzx   eax, di
0x18000a19e  lea     rdx, [rbp+300h+Reply]; Reply
0x18000a1a2  mov     rcx, r14; pAsync
0x18000a1a5  cmovns  eax, r15d
0x18000a1a9  mov     [rbp+300h+Reply], eax
0x18000a1ac  call    cs:__imp_RpcAsyncCompleteCall
0x18000a1b3  nop     dword ptr [rax+rax+00h]
0x18000a1b8  mov     rcx, [rbp+300h+var_50]
0x18000a1bf  xor     rcx, rsp; StackCookie
0x18000a1c2  call    __security_check_cookie
0x18000a1c7  add     rsp, 3C8h
0x18000a1ce  pop     r15
0x18000a1d0  pop     r14
0x18000a1d2  pop     r13
0x18000a1d4  pop     r12
0x18000a1d6  pop     rdi
0x18000a1d7  pop     rsi
0x18000a1d8  pop     rbx
0x18000a1d9  pop     rbp
0x18000a1da  retn
```

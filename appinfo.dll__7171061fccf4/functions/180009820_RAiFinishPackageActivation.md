# RAiFinishPackageActivation

- ea: `0x180009820`
- end: `0x180009ba0`
- name: `RAiFinishPackageActivation`
- size: `896`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, void *, __int64, int, __int64, __int64, __int64, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009820`
- `0x180009ba8`
- `0x180009d10`
- `0x180026f40`
- `0x180028838`
- `0x18002a9cc`
- `0x18002b27c`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800099ef`
- `msvcrt!wcsrchr` at `0x1800099ef`
- `msvcrt!wcsnlen` at `0x180009a3f`
- `msvcrt!wcsnlen` at `0x180009a89`
- `msvcrt!wcsnlen` at `0x180009ab6`
- `msvcrt!wcsnlen` at `0x180009ae4`
- `msvcrt!wcsnlen` at `0x180009a3f`
- `msvcrt!wcsnlen` at `0x180009a89`
- `msvcrt!wcsnlen` at `0x180009ab6`
- `msvcrt!wcsnlen` at `0x180009ae4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180009b77`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180009b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b29`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180009990`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180009990`
- `ntdll!EtwEventWrite` at `0x180009b19`
- `ntdll!EtwEventWrite` at `0x180009b19`

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
  __int64 v14; // rax
  int v15; // edi
  const unsigned __int16 *v16; // rax
  wchar_t *v17; // rbx
  wchar_t *v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // edx
  unsigned int v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+74h] [rbp-8Ch] BYREF
  wchar_t *Str; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hProcess; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+88h] [rbp-78h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+98h] [rbp-68h] BYREF
  int Reply; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v38; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v39[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v40; // [rsp+F0h] [rbp-10h]
  __int128 v41; // [rsp+100h] [rbp+0h]
  __int128 v42; // [rsp+110h] [rbp+10h]
  __int128 v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+140h] [rbp+40h] BYREF
  int v45; // [rsp+148h] [rbp+48h]
  wchar_t v46; // [rsp+14Ch] [rbp+4Ch]
  wchar_t Source[128]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+250h] [rbp+150h] BYREF

  v9 = a9;
  hProcess = a9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids);
    v9 = hProcess;
  }
  v38 = v9;
  v35 = a4;
  v36 = a8;
  v25 = 0;
  v26 = 0;
  v33 = a7;
  v34 = a6;
  v29 = a5;
  hProcess = a3;
  v37 = a2;
  memset_0(Source, 0, sizeof(Source));
  Str = 0;
  v14 = lambda_12563928270045ed26aca7a35a7a0e49_::_lambda_12563928270045ed26aca7a35a7a0e49_(
          (unsigned int)v39,
          (unsigned int)&v38,
          (unsigned int)&v37,
          (unsigned int)&v36,
          (__int64)&v26,
          (__int64)&hProcess,
          (__int64)&v35,
          (__int64)Source,
          (__int64)&Str,
          (__int64)&v25,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v29);
  v15 = lambda_12563928270045ed26aca7a35a7a0e49_::operator()(v14);
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
    v31 = v26;
    v40 = 0;
    v41 = 0;
    v39[0] = &v31;
    v42 = 0;
    v43 = 0;
    v39[1] = 4;
    v19 = wcsnlen(Source, 0x7Fu);
    *(_QWORD *)&v40 = Source;
    v44 = *(_QWORD *)L"<NULL>";
    *((_QWORD *)&v40 + 1) = (unsigned int)(2 * v19 + 2);
    v45 = *(_DWORD *)L"L>";
    v46 = aNull_1[6];
    if ( v17 )
    {
      v20 = wcsnlen(v17, 0x104u) + 1;
    }
    else
    {
      v17 = (wchar_t *)&v44;
      v20 = 7;
    }
    *(_QWORD *)&v41 = v17;
    *((_QWORD *)&v41 + 1) = (unsigned int)(2 * v20);
    v21 = wcsnlen(applicationUserModelId, 0x82u);
    *(_QWORD *)&v42 = applicationUserModelId;
    *((_QWORD *)&v42 + 1) = (unsigned int)(2 * v21 + 2);
    v22 = wcsnlen(L"[FinishPackageActivation]", 0x104u);
    *(_QWORD *)&v43 = L"[FinishPackageActivation]";
    *((_QWORD *)&v43 + 1) = (unsigned int)(2 * v22 + 2);
    if ( g_EventRegHandleAppModelRuntime )
      EtwEventWrite(g_EventRegHandleAppModelRuntime, AppModelDesktopAppXProcessStartSuccess, 5, v39);
  }
  else
  {
    if ( Str )
      v16 = AipJustFileName(Str);
    else
      v16 = 0;
    AipLogDesktopAppXProcessStartFailure(
      v25,
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
      WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
      (unsigned int)v15);
  }
  v23 = (unsigned __int16)v15;
  if ( v15 >= 0 )
    v23 = 0;
  Reply = v23;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180009820  push    rbp
0x180009822  push    rbx
0x180009823  push    rsi
0x180009824  push    rdi
0x180009825  push    r12
0x180009827  push    r13
0x180009829  push    r14
0x18000982b  push    r15
0x18000982d  lea     rbp, [rsp-278h]
0x180009835  sub     rsp, 378h
0x18000983c  mov     rax, cs:__security_cookie
0x180009843  xor     rax, rsp
0x180009846  mov     [rbp+2B0h+var_50], rax
0x18000984d  mov     rax, [rbp+2B0h+arg_40]
0x180009854  mov     r14, r9
0x180009857  mov     r15, [rbp+2B0h+arg_28]
0x18000985e  mov     rdi, r8
0x180009861  mov     r12, [rbp+2B0h+arg_30]
0x180009868  mov     rbx, rdx
0x18000986b  mov     r13, [rbp+2B0h+arg_38]
0x180009872  mov     rsi, rcx
0x180009875  mov     [rbp+2B0h+hProcess], rax
0x180009879  mov     rcx, cs:WPP_GLOBAL_Control
0x180009880  lea     rdx, WPP_GLOBAL_Control
0x180009887  cmp     rcx, rdx
0x18000988a  jz      short loc_1800098AB
0x18000988c  test    byte ptr [rcx+1Ch], 1
0x180009890  jz      short loc_1800098AB
0x180009892  mov     rcx, [rcx+10h]
0x180009896  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x18000989d  mov     edx, 29h ; ')'
0x1800098a2  call    WPP_SF_
0x1800098a7  mov     rax, [rbp+2B0h+hProcess]
0x1800098ab  mov     [rbp+2B0h+var_2E0], rax
0x1800098af  lea     rcx, [rbp+2B0h+Source]; void *
0x1800098b3  mov     eax, [rbp+2B0h+arg_20]
0x1800098b9  xor     edx, edx; Val
0x1800098bb  mov     [rbp+2B0h+var_2F8], r14
0x1800098bf  mov     r8d, 100h; Size
0x1800098c5  xor     r14d, r14d
0x1800098c8  mov     [rbp+2B0h+var_2F0], r13
0x1800098cc  mov     [rsp+3B0h+var_340], r14d
0x1800098d1  mov     [rsp+3B0h+var_33C], r14d
0x1800098d6  mov     [rbp+2B0h+var_308], r12
0x1800098da  mov     [rbp+2B0h+var_300], r15
0x1800098de  mov     [rbp+2B0h+var_328], eax
0x1800098e1  mov     [rbp+2B0h+hProcess], rdi
0x1800098e5  mov     [rbp+2B0h+var_2E8], rbx
0x1800098e9  call    memset_0
0x1800098ee  lea     rax, [rbp+2B0h+var_328]
0x1800098f2  mov     [rsp+3B0h+Str], r14
0x1800098f7  mov     [rsp+3B0h+var_350], rax
0x1800098fc  lea     r9, [rbp+2B0h+var_2F0]
0x180009900  lea     rax, [rbp+2B0h+var_308]
0x180009904  mov     [rsp+3B0h+var_358], rax
0x180009909  lea     r8, [rbp+2B0h+var_2E8]
0x18000990d  lea     rax, [rbp+2B0h+var_300]
0x180009911  mov     [rsp+3B0h+var_360], rax
0x180009916  lea     rdx, [rbp+2B0h+var_2E0]
0x18000991a  lea     rax, [rsp+3B0h+var_340]
0x18000991f  mov     [rsp+3B0h+var_368], rax
0x180009924  lea     rcx, [rbp+2B0h+var_2D0]
0x180009928  lea     rax, [rsp+3B0h+Str]
0x18000992d  mov     [rsp+3B0h+var_370], rax
0x180009932  lea     rax, [rbp+2B0h+Source]
0x180009936  mov     [rsp+3B0h+var_378], rax
0x18000993b  lea     rax, [rbp+2B0h+var_2F8]
0x18000993f  mov     [rsp+3B0h+var_380], rax
0x180009944  lea     rax, [rbp+2B0h+hProcess]
0x180009948  mov     [rsp+3B0h+var_388], rax
0x18000994d  lea     rax, [rsp+3B0h+var_33C]
0x180009952  mov     [rsp+3B0h+var_390], rax
0x180009957  call    _lambda_12563928270045ed26aca7a35a7a0e49____lambda_12563928270045ed26aca7a35a7a0e49_
0x18000995c  mov     rcx, rax
0x18000995f  call    _lambda_12563928270045ed26aca7a35a7a0e49___operator__
0x180009964  xor     edx, edx; Val
0x180009966  lea     rcx, [rbp+2B0h+applicationUserModelId]; void *
0x18000996d  mov     r8d, 104h; Size
0x180009973  mov     edi, eax
0x180009975  call    memset_0
0x18000997a  mov     rcx, [rbp+2B0h+hProcess]; hProcess
0x18000997e  lea     r8, [rbp+2B0h+applicationUserModelId]; applicationUserModelId
0x180009985  lea     rdx, [rbp+2B0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180009989  mov     [rbp+2B0h+applicationUserModelIdLength], 82h
0x180009990  call    cs:__imp_GetApplicationUserModelId
0x180009996  test    edi, edi
0x180009998  jns     short loc_1800099DD
0x18000999a  mov     rcx, [rsp+3B0h+Str]; unsigned __int16 *
0x18000999f  test    rcx, rcx
0x1800099a2  jz      short loc_1800099AB
0x1800099a4  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x1800099a9  jmp     short loc_1800099AE
0x1800099ab  mov     rax, r14
0x1800099ae  lea     rcx, [rbp+2B0h+applicationUserModelId]
0x1800099b5  mov     r9, rax
0x1800099b8  lea     rbx, aFinishpackagea_1; "[FinishPackageActivation]"
0x1800099bf  mov     edx, edi
0x1800099c1  mov     [rsp+3B0h+var_388], rbx
0x1800099c6  lea     r8, [rbp+2B0h+Source]
0x1800099ca  mov     [rsp+3B0h+var_390], rcx
0x1800099cf  mov     ecx, [rsp+3B0h+var_340]
0x1800099d3  call    ?AipLogDesktopAppXProcessStartFailure@@YAXW4DesktopAppXProcessStartFailureCheckpoint@@JPEBG111@Z; AipLogDesktopAppXProcessStartFailure(DesktopAppXProcessStartFailureCheckpoint,long,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800099d8  jmp     loc_180009B1F
0x1800099dd  mov     rbx, [rsp+3B0h+Str]
0x1800099e2  test    rbx, rbx
0x1800099e5  jz      short loc_180009A02
0x1800099e7  mov     edx, 5Ch ; '\'; Ch
0x1800099ec  mov     rcx, rbx; Str
0x1800099ef  call    cs:__imp_wcsrchr
0x1800099f5  test    rax, rax
0x1800099f8  lea     rcx, [rax+2]
0x1800099fc  cmovnz  rbx, rcx
0x180009a00  jmp     short loc_180009A05
0x180009a02  mov     rbx, r14
0x180009a05  mov     eax, [rsp+3B0h+var_33C]
0x180009a09  lea     rcx, [rbp+2B0h+Source]; Source
0x180009a0d  xorps   xmm0, xmm0
0x180009a10  mov     [rbp+2B0h+var_318], eax
0x180009a13  xorps   xmm1, xmm1
0x180009a16  movdqa  [rbp+2B0h+var_2C0], xmm0
0x180009a1b  lea     rax, [rbp+2B0h+var_318]
0x180009a1f  movdqa  [rbp+2B0h+var_2B0], xmm1
0x180009a24  mov     edx, 7Fh; MaxCount
0x180009a29  mov     [rbp+2B0h+var_2D0], rax
0x180009a2d  movdqa  [rbp+2B0h+var_2A0], xmm0
0x180009a32  movdqa  [rbp+2B0h+var_290], xmm1
0x180009a37  mov     [rbp+2B0h+var_2C8], 4
0x180009a3f  call    cs:__imp_wcsnlen
0x180009a45  movsd   xmm0, qword ptr cs:aNull_1; "<NULL>"
0x180009a4d  lea     rcx, [rbp+2B0h+Source]
0x180009a51  mov     qword ptr [rbp+2B0h+var_2C0], rcx
0x180009a55  mov     dword ptr [rbp+2B0h+var_2C0+0Ch], r14d
0x180009a59  movsd   [rbp+2B0h+var_270], xmm0
0x180009a5e  lea     eax, ds:2[rax*2]
0x180009a65  mov     dword ptr [rbp+2B0h+var_2C0+8], eax
0x180009a68  mov     eax, dword ptr cs:aNull_1+8; "L>"
0x180009a6e  mov     [rbp+2B0h+var_268], eax
0x180009a71  movzx   eax, word ptr cs:aNull_1+0Ch; ""
0x180009a78  mov     [rbp+2B0h+var_264], ax
0x180009a7c  test    rbx, rbx
0x180009a7f  jz      short loc_180009A94
0x180009a81  mov     edx, 104h; MaxCount
0x180009a86  mov     rcx, rbx; Source
0x180009a89  call    cs:__imp_wcsnlen
0x180009a8f  inc     rax
0x180009a92  jmp     short loc_180009A9D
0x180009a94  lea     rbx, [rbp+2B0h+var_270]
0x180009a98  mov     eax, 7
0x180009a9d  add     eax, eax
0x180009a9f  mov     qword ptr [rbp+2B0h+var_2B0], rbx
0x180009aa3  mov     edx, 82h; MaxCount
0x180009aa8  mov     dword ptr [rbp+2B0h+var_2B0+8], eax
0x180009aab  lea     rcx, [rbp+2B0h+applicationUserModelId]; Source
0x180009ab2  mov     dword ptr [rbp+2B0h+var_2B0+0Ch], r14d
0x180009ab6  call    cs:__imp_wcsnlen
0x180009abc  lea     rcx, [rbp+2B0h+applicationUserModelId]
0x180009ac3  mov     dword ptr [rbp+2B0h+var_2A0+0Ch], r14d
0x180009ac7  mov     qword ptr [rbp+2B0h+var_2A0], rcx
0x180009acb  lea     rbx, aFinishpackagea_1; "[FinishPackageActivation]"
0x180009ad2  mov     edx, 104h; MaxCount
0x180009ad7  mov     rcx, rbx; Source
0x180009ada  lea     eax, ds:2[rax*2]
0x180009ae1  mov     dword ptr [rbp+2B0h+var_2A0+8], eax
0x180009ae4  call    cs:__imp_wcsnlen
0x180009aea  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x180009af1  mov     qword ptr [rbp+2B0h+var_290], rbx
0x180009af5  mov     dword ptr [rbp+2B0h+var_290+0Ch], r14d
0x180009af9  lea     eax, ds:2[rax*2]
0x180009b00  mov     dword ptr [rbp+2B0h+var_290+8], eax
0x180009b03  test    rcx, rcx
0x180009b06  jz      short loc_180009B1F
0x180009b08  lea     r9, [rbp+2B0h+var_2D0]
0x180009b0c  mov     r8d, 5
0x180009b12  lea     rdx, AppModelDesktopAppXProcessStartSuccess
0x180009b19  call    cs:__imp_EtwEventWrite
0x180009b1f  mov     rcx, [rsp+3B0h+Str]; hMem
0x180009b24  test    rcx, rcx
0x180009b27  jz      short loc_180009B2F
0x180009b29  call    cs:__imp_LocalFree
0x180009b2f  test    edi, edi
0x180009b31  jns     short loc_180009B64
0x180009b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b3a  lea     rax, WPP_GLOBAL_Control
0x180009b41  cmp     rcx, rax
0x180009b44  jz      short loc_180009B64
0x180009b46  test    byte ptr [rcx+1Ch], 1
0x180009b4a  jz      short loc_180009B64
0x180009b4c  mov     rcx, [rcx+10h]
0x180009b50  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x180009b57  mov     edx, 2Ah ; '*'
0x180009b5c  mov     r9d, edi
0x180009b5f  call    WPP_SF_D
0x180009b64  test    edi, edi
0x180009b66  movzx   edx, di
0x180009b69  mov     rcx, rsi; pAsync
0x180009b6c  cmovns  edx, r14d
0x180009b70  mov     [rbp+2B0h+Reply], edx
0x180009b73  lea     rdx, [rbp+2B0h+Reply]; Reply
0x180009b77  call    cs:__imp_RpcAsyncCompleteCall
0x180009b7d  mov     rcx, [rbp+2B0h+var_50]
0x180009b84  xor     rcx, rsp; StackCookie
0x180009b87  call    __security_check_cookie
0x180009b8c  add     rsp, 378h
0x180009b93  pop     r15
0x180009b95  pop     r14
0x180009b97  pop     r13
0x180009b99  pop     r12
0x180009b9b  pop     rdi
0x180009b9c  pop     rsi
0x180009b9d  pop     rbx
0x180009b9e  pop     rbp
0x180009b9f  retn
```

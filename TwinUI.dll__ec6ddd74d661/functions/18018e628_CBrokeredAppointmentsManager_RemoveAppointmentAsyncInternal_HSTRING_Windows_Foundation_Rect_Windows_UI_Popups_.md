# CBrokeredAppointmentsManager::_RemoveAppointmentAsyncInternal(HSTRING__ *,Windows::Foundation::Rect,Windows::UI::Popups::Placement,Windows::Foundation::DateTime *,Windows::Foundation::IAsyncOperation<bool> * *)

- ea: `0x18018e628`
- end: `0x18018e7fd`
- name: `?_RemoveAppointmentAsyncInternal@CBrokeredAppointmentsManager@@CAJPEAUHSTRING__@@URect@Foundation@Windows@@W4Placement@Popups@UI@5@PEAUDateTime@45@PEAPEAU?$IAsyncOperation@_N@45@@Z`
- size: `469`
- prototype: `__int64 __usercall@<rax>(HSTRING string@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18018d460`
- `0x18018d4a0`
- `0x18018d4e0`

## callees

- `0x180055128`
- `0x180142e10`
- `0x1801848d8`
- `0x180184930`
- `0x180185fa4`
- `0x18018b040`
- `0x18018e508`
- `0x18018e628`
- `0x1803853fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018e6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18018e6f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018e6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018e6b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e7c6`

## pseudocode

```c
__int64 __fastcall CBrokeredAppointmentsManager::_RemoveAppointmentAsyncInternal(
        HSTRING string,
        __int128 *a2,
        int a3,
        __int64 *a4,
        _QWORD *a5)
{
  int CallingApplicationWindowAndVerifyVisibility; // edi
  unsigned __int16 **v10; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  char v15; // dl
  void *v16; // rbx
  LPVOID v17; // r8
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int64 v20; // r8
  _BYTE v22[12]; // [rsp+20h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  HWND v24; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  __int128 v26; // [rsp+48h] [rbp-38h]
  int v27; // [rsp+58h] [rbp-28h]
  char v28; // [rsp+5Ch] [rbp-24h]
  __int64 v29; // [rsp+60h] [rbp-20h]
  LPVOID v30; // [rsp+68h] [rbp-18h]
  HWND v31; // [rsp+70h] [rbp-10h]

  v24 = 0;
  pv = 0;
  *a5 = 0;
  CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(
                                                  &v24,
                                                  0);
  if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
  {
    CoTaskMemFree(0);
    CallingApplicationWindowAndVerifyVisibility = CallerIdentity::GetCallingProcessPackageFamilyName(
                                                    (CallerIdentity *)&pv,
                                                    v10);
    if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
    {
      if ( WindowsIsStringEmpty(string) )
      {
        CallingApplicationWindowAndVerifyVisibility = -2147024809;
        OriginateErrorWithResourceString(-2147024809, 0, 0x2BC8u);
      }
      else
      {
        *(_QWORD *)v22 = 0;
        CoTaskMemFree(0);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        CallingApplicationWindowAndVerifyVisibility = _AllocString<CTCoAllocPolicy>(v13, v12, StringRawBuffer, v22);
        if ( CallingApplicationWindowAndVerifyVisibility < 0 )
        {
          v16 = *(void **)v22;
        }
        else
        {
          if ( a4 )
          {
            v14 = *a4;
            v15 = 1;
          }
          else
          {
            v14 = 0;
            v15 = 0;
          }
          v16 = 0;
          v17 = pv;
          v18 = *a2;
          v29 = v14;
          v25 = *(_QWORD *)v22;
          v26 = v18;
          pv = 0;
          v27 = a3;
          v28 = v15;
          v30 = v17;
          v31 = v24;
          *(_DWORD *)v22 = 1;
          *(_QWORD *)&v22[4] = 4;
          v19 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<unsigned char,0>,_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_,>(&v25);
          CallingApplicationWindowAndVerifyVisibility = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler>(
                                                          v22,
                                                          a5,
                                                          v20,
                                                          v19);
          _lambda_d8c49c8fa3285360fd222d9d6c5e0a24_::~_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_((_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_ *)&v25);
          CoTaskMemFree(0);
          CoTaskMemFree(0);
        }
        CoTaskMemFree(v16);
      }
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
}

```

## disassembly

```asm
0x18018e628  mov     [rsp-28h+arg_8], rbx
0x18018e62d  mov     [rsp-28h+arg_10], rsi
0x18018e632  push    rbp
0x18018e633  push    rdi
0x18018e634  push    r12
0x18018e636  push    r14
0x18018e638  push    r15
0x18018e63a  mov     rbp, rsp
0x18018e63d  sub     rsp, 80h
0x18018e644  mov     rax, cs:__security_cookie
0x18018e64b  xor     rax, rsp
0x18018e64e  mov     [rbp+var_8], rax
0x18018e652  mov     r14, [rbp+arg_20]
0x18018e656  mov     r12, rdx
0x18018e659  mov     rsi, rcx
0x18018e65c  mov     [rbp+var_48], 0
0x18018e664  xor     edx, edx; unsigned __int16 **
0x18018e666  mov     [rbp+pv], 0
0x18018e66e  lea     rcx, [rbp+var_48]; this
0x18018e672  mov     rbx, r9
0x18018e675  mov     qword ptr [r14], 0
0x18018e67c  mov     r15d, r8d
0x18018e67f  call    ?_GetCallingApplicationWindowAndVerifyVisibility@CBrokeredAppointmentsManager@@CAJPEAPEAUHWND__@@PEAPEAG@Z; CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(HWND__ * *,ushort * *)
0x18018e684  mov     edi, eax
0x18018e686  test    eax, eax
0x18018e688  js      loc_18018E7C2
0x18018e68e  xor     ecx, ecx; pv
0x18018e690  call    cs:__imp_CoTaskMemFree
0x18018e697  nop     dword ptr [rax+rax+00h]
0x18018e69c  lea     rcx, [rbp+pv]; this
0x18018e6a0  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x18018e6a5  mov     edi, eax
0x18018e6a7  test    eax, eax
0x18018e6a9  js      loc_18018E7C2
0x18018e6af  mov     rcx, rsi; string
0x18018e6b2  call    cs:__imp_WindowsIsStringEmpty
0x18018e6b9  nop     dword ptr [rax+rax+00h]
0x18018e6be  test    eax, eax
0x18018e6c0  jz      short loc_18018E6DB
0x18018e6c2  mov     edi, 80070057h
0x18018e6c7  xor     edx, edx; HINSTANCE
0x18018e6c9  mov     ecx, edi; int
0x18018e6cb  mov     r8d, 2BC8h; unsigned int
0x18018e6d1  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x18018e6d6  jmp     loc_18018E7C2
0x18018e6db  xor     ecx, ecx; pv
0x18018e6dd  mov     [rbp+var_60], 0
0x18018e6e5  call    cs:__imp_CoTaskMemFree
0x18018e6ec  nop     dword ptr [rax+rax+00h]
0x18018e6f1  xor     edx, edx; length
0x18018e6f3  mov     rcx, rsi; string
0x18018e6f6  call    cs:__imp_WindowsGetStringRawBuffer
0x18018e6fd  nop     dword ptr [rax+rax+00h]
0x18018e702  mov     r8, rax
0x18018e705  lea     r9, [rbp+var_60]
0x18018e709  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18018e70e  mov     edi, eax
0x18018e710  test    eax, eax
0x18018e712  js      loc_18018E7AF
0x18018e718  test    rbx, rbx
0x18018e71b  jz      short loc_18018E724
0x18018e71d  mov     rax, [rbx]
0x18018e720  mov     dl, 1
0x18018e722  jmp     short loc_18018E728
0x18018e724  xor     eax, eax
0x18018e726  xor     dl, dl
0x18018e728  mov     rcx, [rbp+var_60]
0x18018e72c  xor     ebx, ebx
0x18018e72e  mov     r8, [rbp+pv]
0x18018e732  movups  xmm0, xmmword ptr [r12]
0x18018e737  mov     [rbp+var_20], rax
0x18018e73b  mov     rax, [rbp+var_48]
0x18018e73f  mov     [rbp+var_40], rcx
0x18018e743  lea     rcx, [rbp+var_40]
0x18018e747  movdqu  [rbp+var_38], xmm0
0x18018e74c  mov     [rbp+pv], 0
0x18018e754  mov     [rbp+var_28], r15d
0x18018e758  mov     [rbp+var_24], dl
0x18018e75b  mov     [rbp+var_18], r8
0x18018e75f  mov     [rbp+var_10], rax
0x18018e763  mov     dword ptr [rbp+var_60], 1
0x18018e76a  mov     [rbp+var_60+4], 4
0x18018e772  call    ??$MakeOpLambda@$0A@V?$CBasicResult@E$0A@@Internal@Windows@@V_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@V?$CBasicResult@E$0A@@Internal@Windows@@@01@$$QEAV_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CBasicResult<uchar,0>,_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_,>(_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_ &&)
0x18018e777  mov     r9, rax
0x18018e77a  lea     rcx, [rbp+var_60]
0x18018e77e  mov     rdx, r14
0x18018e781  call    ??$MakeAsyncOperationHelper@V?$CBasicResult@E$0A@@Internal@Windows@@_NVComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@_N@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@E$0A@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CBasicResult<uchar,0>,bool,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<bool> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<uchar,0>> *)
0x18018e786  lea     rcx, [rbp+var_40]; this
0x18018e78a  mov     edi, eax
0x18018e78c  call    ??1_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_@@QEAA@XZ; _lambda_d8c49c8fa3285360fd222d9d6c5e0a24_::~_lambda_d8c49c8fa3285360fd222d9d6c5e0a24_(void)
0x18018e791  xor     ecx, ecx; pv
0x18018e793  call    cs:__imp_CoTaskMemFree
0x18018e79a  nop     dword ptr [rax+rax+00h]
0x18018e79f  xor     ecx, ecx; pv
0x18018e7a1  call    cs:__imp_CoTaskMemFree
0x18018e7a8  nop     dword ptr [rax+rax+00h]
0x18018e7ad  jmp     short loc_18018E7B3
0x18018e7af  mov     rbx, [rbp+var_60]
0x18018e7b3  mov     rcx, rbx; pv
0x18018e7b6  call    cs:__imp_CoTaskMemFree
0x18018e7bd  nop     dword ptr [rax+rax+00h]
0x18018e7c2  mov     rcx, [rbp+pv]; pv
0x18018e7c6  call    cs:__imp_CoTaskMemFree
0x18018e7cd  nop     dword ptr [rax+rax+00h]
0x18018e7d2  mov     eax, edi
0x18018e7d4  mov     rcx, [rbp+var_8]
0x18018e7d8  xor     rcx, rsp; StackCookie
0x18018e7db  call    __security_check_cookie
0x18018e7e0  lea     r11, [rsp+80h+var_s0]
0x18018e7e8  mov     rbx, [r11+38h]
0x18018e7ec  mov     rsi, [r11+40h]
0x18018e7f0  mov     rsp, r11
0x18018e7f3  pop     r15
0x18018e7f5  pop     r14
0x18018e7f7  pop     r12
0x18018e7f9  pop     rdi
0x18018e7fa  pop     rbp
0x18018e7fb  retn
```

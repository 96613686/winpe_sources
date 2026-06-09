# CApplicationFrameInputPaneWindowService::InputPaneShowing(HWND__ *,tagRECT const *,IHM_DISPLAY_MODE)

- ea: `0x18005dd20`
- end: `0x18005deff`
- name: `?InputPaneShowing@CApplicationFrameInputPaneWindowService@@UEAAJPEAUHWND__@@PEBUtagRECT@@W4IHM_DISPLAY_MODE@@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004c98`
- `0x180031a20`
- `0x1800396a0`
- `0x18003ed08`
- `0x180040270`
- `0x1800422b8`
- `0x180043c30`
- `0x18005c6cc`
- `0x18005c950`
- `0x18005cacc`
- `0x18005d1fc`
- `0x18005dd20`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dd86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dd86`
- `TWINAPI!__imp_QueryWindowService` at `0x18005de48`
- `TWINAPI!__imp_QueryWindowService` at `0x18005de48`

## string_xrefs

- `0x18005de02`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`
- `0x18005de92`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CApplicationFrameInputPaneWindowService::InputPaneShowing(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        int a4)
{
  char v8; // r14
  __int64 v9; // rax
  __int64 v10; // r11
  int v11; // ebx
  int v12; // eax
  __int64 v13; // rdx
  int *v15; // [rsp+20h] [rbp-89h]
  __int64 v16; // [rsp+40h] [rbp-69h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-61h] BYREF
  _OWORD *v18; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v19[24]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v20[40]; // [rsp+70h] [rbp-39h] BYREF
  int v21[4]; // [rsp+98h] [rbp-11h] BYREF
  int v22[4]; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v23; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v18 = a3;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 80);
  v8 = *(_BYTE *)(a1 + 88);
  if ( v8 )
  {
    *(_QWORD *)(a1 + 96) = a2;
    *(_BYTE *)(a1 + 89) = 1;
    *(_DWORD *)(a1 + 92) = a4;
    *(_OWORD *)(a1 + 104) = *a3;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( !v8 )
  {
    *(_OWORD *)v21 = 0;
    *(_OWORD *)v22 = 0;
    v23 = 0;
    SRWLock = (PSRWLOCK)a1;
    Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalAddRef(&SRWLock);
    v9 = lambda_5f7c1a70b67a36d58d7180b7f4e05370_::_lambda_5f7c1a70b67a36d58d7180b7f4e05370__0(
           (unsigned int)v20,
           (unsigned int)&SRWLock,
           (unsigned int)&v18,
           (unsigned int)v21,
           (__int64)v22,
           (__int64)&v23);
    v11 = CreationThreadDispatcher::RunSync__lambda_5f7c1a70b67a36d58d7180b7f4e05370___(v10, v9);
    Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::~ComPtr<CApplicationFrameInputPaneWindowService>(v20);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v11,
        (int)v15);
LABEL_13:
      Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(&SRWLock);
      return (unsigned int)v11;
    }
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)v19);
    v16 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
    v12 = QueryWindowService(a2, &SID_InputPaneEventHandler, &GUID_87482e5d_0157_459a_bd7c_cb18085be80f, &v16);
    v11 = v12;
    if ( v12 < 0 )
    {
      v13 = 271;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v12,
        (int)v15);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v19);
      goto LABEL_13;
    }
    v15 = v21;
    v12 = (*(__int64 (__fastcall **)(__int64, _OWORD *, __int128 *, int *))(*(_QWORD *)v16 + 24LL))(v16, a3, &v23, v22);
    v11 = v12;
    if ( v12 < 0 )
    {
      v13 = 272;
      goto LABEL_12;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v19);
    Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(&SRWLock);
  }
  return 0;
}

```

## disassembly

```asm
0x18005dd20  push    rbp
0x18005dd22  push    rbx
0x18005dd23  push    rsi
0x18005dd24  push    rdi
0x18005dd25  push    r14
0x18005dd27  push    r15
0x18005dd29  lea     rbp, [rsp-2Fh]
0x18005dd2e  sub     rsp, 0D8h
0x18005dd35  mov     rax, cs:__security_cookie
0x18005dd3c  xor     rax, rsp
0x18005dd3f  mov     [rbp+57h+var_38], rax
0x18005dd43  mov     r15d, r9d
0x18005dd46  mov     rdi, r8
0x18005dd49  mov     rsi, rdx
0x18005dd4c  mov     rbx, rcx
0x18005dd4f  mov     [rbp+57h+var_B0], r8
0x18005dd53  lea     rdx, [rcx+50h]
0x18005dd57  lea     rcx, [rbp+57h+SRWLock]
0x18005dd5b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005dd60  mov     r14b, [rbx+58h]
0x18005dd64  test    r14b, r14b
0x18005dd67  jz      short loc_18005DD7D
0x18005dd69  mov     [rbx+60h], rsi
0x18005dd6d  mov     byte ptr [rbx+59h], 1
0x18005dd71  mov     [rbx+5Ch], r15d
0x18005dd75  movups  xmm0, xmmword ptr [rdi]
0x18005dd78  movdqu  xmmword ptr [rbx+68h], xmm0
0x18005dd7d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005dd81  test    rcx, rcx
0x18005dd84  jz      short loc_18005DD8C
0x18005dd86  call    cs:__imp_ReleaseSRWLockExclusive
0x18005dd8c  test    r14b, r14b
0x18005dd8f  jnz     loc_18005DEE1
0x18005dd95  xorps   xmm0, xmm0
0x18005dd98  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18005dd9c  xorps   xmm1, xmm1
0x18005dd9f  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x18005dda3  movups  [rbp+57h+var_48], xmm0
0x18005dda7  mov     [rbp+57h+SRWLock], rbx
0x18005ddab  lea     rcx, [rbp+57h+SRWLock]
0x18005ddaf  call    ?InternalAddRef@?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalAddRef(void)
0x18005ddb4  nop
0x18005ddb5  mov     r11, [rbx+40h]
0x18005ddb9  lea     rax, [rbp+57h+var_48]
0x18005ddbd  mov     [rsp+100h+var_D8], rax
0x18005ddc2  lea     rax, [rbp+57h+var_58]
0x18005ddc6  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18005ddcb  lea     r9, [rbp+57h+var_68]
0x18005ddcf  lea     r8, [rbp+57h+var_B0]
0x18005ddd3  lea     rdx, [rbp+57h+SRWLock]
0x18005ddd7  lea     rcx, [rbp+57h+var_90]
0x18005dddb  call    _lambda_5f7c1a70b67a36d58d7180b7f4e05370____lambda_5f7c1a70b67a36d58d7180b7f4e05370__0
0x18005dde0  nop
0x18005dde1  mov     rdx, rax
0x18005dde4  mov     rcx, r11
0x18005dde7  call    CreationThreadDispatcher__RunSync__lambda_5f7c1a70b67a36d58d7180b7f4e05370___
0x18005ddec  mov     ebx, eax
0x18005ddee  lea     rcx, [rbp+57h+var_90]
0x18005ddf2  call    ??1?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::~ComPtr<CApplicationFrameInputPaneWindowService>(void)
0x18005ddf7  test    ebx, ebx
0x18005ddf9  jns     short loc_18005DE18
0x18005ddfb  mov     rcx, [rbp+5Fh]; this
0x18005ddff  mov     r9d, ebx; char *
0x18005de02  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18005de09  mov     edx, 107h; void *
0x18005de0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005de13  jmp     loc_18005DEB7
0x18005de18  lea     rcx, [rbp+57h+var_A8]; this
0x18005de1c  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18005de21  nop
0x18005de22  mov     [rbp+57h+var_C0], 0
0x18005de2a  lea     rcx, [rbp+57h+var_C0]
0x18005de2e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005de33  lea     r9, [rbp+57h+var_C0]
0x18005de37  lea     r8, _GUID_87482e5d_0157_459a_bd7c_cb18085be80f
0x18005de3e  lea     rdx, SID_InputPaneEventHandler
0x18005de45  mov     rcx, rsi
0x18005de48  call    cs:__imp_QueryWindowService
0x18005de4e  mov     ebx, eax
0x18005de50  test    eax, eax
0x18005de52  jns     short loc_18005DE5B
0x18005de54  mov     edx, 10Fh
0x18005de59  jmp     short loc_18005DE8F
0x18005de5b  mov     rcx, [rbp+57h+var_C0]
0x18005de5f  mov     rax, [rcx]
0x18005de62  mov     dword ptr [rsp+100h+var_D8], r15d
0x18005de67  lea     rdx, [rbp+57h+var_68]
0x18005de6b  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x18005de70  lea     r9, [rbp+57h+var_58]
0x18005de74  lea     r8, [rbp+57h+var_48]
0x18005de78  mov     rdx, rdi
0x18005de7b  mov     rax, [rax+18h]
0x18005de7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de84  mov     ebx, eax
0x18005de86  test    eax, eax
0x18005de88  jns     short loc_18005DEC4
0x18005de8a  mov     edx, 110h; void *
0x18005de8f  mov     r9d, eax; char *
0x18005de92  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18005de99  mov     rcx, [rbp+5Fh]; this
0x18005de9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dea2  nop
0x18005dea3  lea     rcx, [rbp+57h+var_C0]
0x18005dea7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005deac  nop
0x18005dead  lea     rcx, [rbp+57h+var_A8]; this
0x18005deb1  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005deb6  nop
0x18005deb7  lea     rcx, [rbp+57h+SRWLock]
0x18005debb  call    ?InternalRelease@?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(void)
0x18005dec0  mov     eax, ebx
0x18005dec2  jmp     short loc_18005DEE3
0x18005dec4  lea     rcx, [rbp+57h+var_C0]
0x18005dec8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005decd  nop
0x18005dece  lea     rcx, [rbp+57h+var_A8]; this
0x18005ded2  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005ded7  nop
0x18005ded8  lea     rcx, [rbp+57h+SRWLock]
0x18005dedc  call    ?InternalRelease@?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(void)
0x18005dee1  xor     eax, eax
0x18005dee3  mov     rcx, [rbp+57h+var_38]
0x18005dee7  xor     rcx, rsp; StackCookie
0x18005deea  call    __security_check_cookie
0x18005deef  add     rsp, 0D8h
0x18005def6  pop     r15
0x18005def8  pop     r14
0x18005defa  pop     rdi
0x18005defb  pop     rsi
0x18005defc  pop     rbx
0x18005defd  pop     rbp
0x18005defe  retn
```

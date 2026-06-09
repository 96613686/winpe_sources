# CApplicationFrameInputPaneWindowService::InputPaneHiding(HWND__ *,IHM_DISPLAY_MODE)

- ea: `0x18005dc10`
- end: `0x18005dd18`
- name: `?InputPaneHiding@CApplicationFrameInputPaneWindowService@@UEAAJPEAUHWND__@@W4IHM_DISPLAY_MODE@@@Z`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004c98`
- `0x180031a20`
- `0x180040270`
- `0x18005cacc`
- `0x18005d1fc`
- `0x18005dc10`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dc56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dc56`
- `TWINAPI!__imp_QueryWindowService` at `0x18005dc99`
- `TWINAPI!__imp_QueryWindowService` at `0x18005dc99`

## string_xrefs

- `0x18005dccd`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CApplicationFrameInputPaneWindowService::InputPaneHiding(__int64 a1, __int64 a2, unsigned int a3)
{
  char v6; // di
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v11[18]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+70h] [rbp+8h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 80);
  v6 = *(_BYTE *)(a1 + 88);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 96) = a2;
    *(_BYTE *)(a1 + 89) = 0;
    *(_DWORD *)(a1 + 92) = a3;
    *(_OWORD *)(a1 + 104) = 0;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( !v6 )
  {
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)v11);
    SRWLock = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&SRWLock);
    v7 = QueryWindowService(a2, &SID_InputPaneEventHandler, &GUID_87482e5d_0157_459a_bd7c_cb18085be80f, &SRWLock);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 303;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v7,
        v11[0]);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&SRWLock);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v11);
      return v8;
    }
    v7 = (*((__int64 (__fastcall **)(PSRWLOCK, _QWORD))SRWLock->Ptr + 4))(SRWLock, a3);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 304;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&SRWLock);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18005dc10  push    rbx
0x18005dc12  push    rbp
0x18005dc13  push    rsi
0x18005dc14  push    rdi
0x18005dc15  sub     rsp, 48h
0x18005dc19  mov     ebp, r8d
0x18005dc1c  mov     rsi, rdx
0x18005dc1f  mov     rbx, rcx
0x18005dc22  lea     rdx, [rcx+50h]
0x18005dc26  lea     rcx, [rsp+68h+SRWLock]
0x18005dc2b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005dc30  mov     dil, [rbx+58h]
0x18005dc34  test    dil, dil
0x18005dc37  jz      short loc_18005DC4C
0x18005dc39  mov     [rbx+60h], rsi
0x18005dc3d  mov     byte ptr [rbx+59h], 0
0x18005dc41  mov     [rbx+5Ch], ebp
0x18005dc44  xorps   xmm0, xmm0
0x18005dc47  movdqu  xmmword ptr [rbx+68h], xmm0
0x18005dc4c  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18005dc51  test    rcx, rcx
0x18005dc54  jz      short loc_18005DC5C
0x18005dc56  call    cs:__imp_ReleaseSRWLockExclusive
0x18005dc5c  test    dil, dil
0x18005dc5f  jnz     loc_18005DD0D
0x18005dc65  lea     rcx, [rsp+68h+var_48]; this
0x18005dc6a  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18005dc6f  nop
0x18005dc70  mov     [rsp+68h+SRWLock], 0
0x18005dc79  lea     rcx, [rsp+68h+SRWLock]
0x18005dc7e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005dc83  lea     r9, [rsp+68h+SRWLock]
0x18005dc88  lea     r8, _GUID_87482e5d_0157_459a_bd7c_cb18085be80f
0x18005dc8f  lea     rdx, SID_InputPaneEventHandler
0x18005dc96  mov     rcx, rsi
0x18005dc99  call    cs:__imp_QueryWindowService
0x18005dc9f  mov     ebx, eax
0x18005dca1  test    eax, eax
0x18005dca3  jns     short loc_18005DCAC
0x18005dca5  mov     edx, 12Fh
0x18005dcaa  jmp     short loc_18005DCCA
0x18005dcac  mov     rcx, [rsp+68h+SRWLock]
0x18005dcb1  mov     rax, [rcx]
0x18005dcb4  mov     edx, ebp
0x18005dcb6  mov     rax, [rax+20h]
0x18005dcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcbf  mov     ebx, eax
0x18005dcc1  test    eax, eax
0x18005dcc3  jns     short loc_18005DCF8
0x18005dcc5  mov     edx, 130h; void *
0x18005dcca  mov     r9d, eax; char *
0x18005dccd  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18005dcd4  mov     rcx, [rsp+68h]; this
0x18005dcd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dcde  nop
0x18005dcdf  lea     rcx, [rsp+68h+SRWLock]
0x18005dce4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005dce9  nop
0x18005dcea  lea     rcx, [rsp+68h+var_48]; this
0x18005dcef  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005dcf4  mov     eax, ebx
0x18005dcf6  jmp     short loc_18005DD0F
0x18005dcf8  lea     rcx, [rsp+68h+SRWLock]
0x18005dcfd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005dd02  nop
0x18005dd03  lea     rcx, [rsp+68h+var_48]; this
0x18005dd08  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005dd0d  xor     eax, eax
0x18005dd0f  add     rsp, 48h
0x18005dd13  pop     rdi
0x18005dd14  pop     rsi
0x18005dd15  pop     rbp
0x18005dd16  pop     rbx
0x18005dd17  retn
```

# FindBITSJob(_GUID const &,IBackgroundCopyJob * *)

- ea: `0x18001e154`
- end: `0x18001e245`
- name: `?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(UUID *Uuid, struct IBackgroundCopyJob **)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b6bc`
- `0x18001b9d4`
- `0x18001bcd4`
- `0x18001bfcc`
- `0x18001c8e4`
- `0x18001ed00`

## callees

- `0x18000a358`
- `0x18001afb4`
- `0x18001e044`
- `0x18001e154`
- `0x18001e480`
- `0x180021010`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18001e1a0`
- `RPCRT4!UuidToStringW` at `0x18001e1a0`
- `RPCRT4!RpcStringFreeW` at `0x18001e21c`
- `RPCRT4!RpcStringFreeW` at `0x18001e21c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindBITSJob(UUID *Uuid, struct IBackgroundCopyJob **a2)
{
  LPVOID *v4; // rax
  int HttpBITSManager; // ebx
  void **v7; // [rsp+20h] [rbp-38h] BYREF
  __int64 v8[6]; // [rsp+28h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+70h] [rbp+18h] BYREF

  v8[0] = 0;
  v7 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  StringUuid = 0;
  v4 = (LPVOID *)SmartPtr<IBackgroundCopyManager>::operator&(&v7);
  HttpBITSManager = GetHttpBITSManager(v4);
  if ( HttpBITSManager >= 0 )
  {
    if ( UuidToStringW(Uuid, &StringUuid) )
    {
      HttpBITSManager = -2147467259;
    }
    else
    {
      HttpBITSManager = (*(__int64 (__fastcall **)(__int64, UUID *, struct IBackgroundCopyJob **))(*(_QWORD *)v8[0]
                                                                                                 + 32LL))(
                          v8[0],
                          Uuid,
                          a2);
      if ( HttpBITSManager == -2145386495 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids, StringUuid);
        HttpBITSManager = -2145386495;
      }
    }
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  v7 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(v8);
  return (unsigned int)HttpBITSManager;
}

```

## disassembly

```asm
0x18001e154  mov     rax, rsp
0x18001e157  push    rbx
0x18001e158  push    rsi
0x18001e159  push    rdi
0x18001e15a  push    r14
0x18001e15c  sub     rsp, 38h
0x18001e160  mov     rsi, rdx
0x18001e163  mov     rdi, rcx
0x18001e166  mov     qword ptr [rax-30h], 0
0x18001e16e  lea     r14, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e175  mov     [rax-38h], r14
0x18001e179  mov     qword ptr [rax+18h], 0
0x18001e181  lea     rcx, [rax-38h]
0x18001e185  call    ??I?$SmartPtr@UIBackgroundCopyManager@@@@QEAAPEAPEAUIBackgroundCopyManager@@XZ; SmartPtr<IBackgroundCopyManager>::operator&(void)
0x18001e18a  mov     rcx, rax; ppv
0x18001e18d  call    GetHttpBITSManager
0x18001e192  mov     ebx, eax
0x18001e194  test    eax, eax
0x18001e196  js      short loc_18001E20F
0x18001e198  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x18001e19d  mov     rcx, rdi; Uuid
0x18001e1a0  call    cs:__imp_UuidToStringW
0x18001e1a7  nop     dword ptr [rax+rax+00h]
0x18001e1ac  test    eax, eax
0x18001e1ae  jz      short loc_18001E1B7
0x18001e1b0  mov     ebx, 80004005h
0x18001e1b5  jmp     short loc_18001E20F
0x18001e1b7  mov     rcx, [rsp+58h+var_30]
0x18001e1bc  mov     rax, [rcx]
0x18001e1bf  mov     r8, rsi
0x18001e1c2  mov     rdx, rdi
0x18001e1c5  mov     rax, [rax+20h]
0x18001e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ce  mov     ebx, eax
0x18001e1d0  cmp     eax, 80200001h
0x18001e1d5  jnz     short loc_18001E20F
0x18001e1d7  lea     rax, WPP_GLOBAL_Control
0x18001e1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1e5  cmp     rcx, rax
0x18001e1e8  jz      short loc_18001E20A
0x18001e1ea  test    byte ptr [rcx+1Ch], 1
0x18001e1ee  jz      short loc_18001E20A
0x18001e1f0  mov     edx, 0Ah
0x18001e1f5  mov     r9, [rsp+58h+StringUuid]
0x18001e1fa  lea     r8, WPP_07b01dc256fa3d02f82cf27706e3d3e2_Traceguids
0x18001e201  mov     rcx, [rcx+10h]
0x18001e205  call    WPP_SF_S
0x18001e20a  mov     ebx, 80200001h
0x18001e20f  cmp     [rsp+58h+StringUuid], 0
0x18001e215  jz      short loc_18001E229
0x18001e217  lea     rcx, [rsp+58h+StringUuid]; String
0x18001e21c  call    cs:__imp_RpcStringFreeW
0x18001e223  nop     dword ptr [rax+rax+00h]
0x18001e228  nop
0x18001e229  mov     [rsp+58h+var_38], r14
0x18001e22e  lea     rcx, [rsp+58h+var_30]
0x18001e233  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e238  mov     eax, ebx
0x18001e23a  add     rsp, 38h
0x18001e23e  pop     r14
0x18001e240  pop     rdi
0x18001e241  pop     rsi
0x18001e242  pop     rbx
0x18001e243  retn
```

# CTnoRPCServerImpl::Unpublish(void *,ulong,uchar *)

- ea: `0x180123c30`
- end: `0x180123db1`
- name: `?Unpublish@CTnoRPCServerImpl@@UEAAJPEAXKPEAE@Z`
- size: `385`
- prototype: `__int64 __fastcall(CTnoRPCServerImpl *__hidden this, RPC_BINDING_HANDLE BindingHandle, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800024f0`
- `0x180008290`
- `0x180015c28`
- `0x180018170`
- `0x1800191b8`
- `0x180123b08`
- `0x180123c30`
- `0x180137470`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180123ccc`
- `RPCRT4!RpcImpersonateClient` at `0x180123ccc`
- `RPCRT4!RpcRevertToSelf` at `0x180123d32`
- `RPCRT4!RpcRevertToSelf` at `0x180123d32`

## string_xrefs

- `0x180123c64`: `PeerDist-Common-Client-Enabled`

## pseudocode

```c
__int64 __fastcall CTnoRPCServerImpl::Unpublish(
        RTL_SRWLOCK *this,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned int a3,
        unsigned __int8 *a4)
{
  void **v8; // rcx
  int PublisherIdentityForCurrentThread; // ebx
  CHostedCacheMsgEncoding *v10; // rcx
  __int64 v11; // rdx
  _BYTE v13[40]; // [rsp+20h] [rbp-28h] BYREF
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  Block = 0;
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v13, this + 2);
  if ( IsLicenseEnabled(L"PeerDist-Common-Client-Enabled") )
  {
    if ( BindingHandle && (PublisherIdentityForCurrentThread = RpcImpersonateClient(BindingHandle)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          132,
          WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
          (unsigned int)PublisherIdentityForCurrentThread);
      }
      if ( PublisherIdentityForCurrentThread >= 0 )
        PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80010000;
    }
    else
    {
      PublisherIdentityForCurrentThread = GetPublisherIdentityForCurrentThread(v8, (unsigned __int16 **)&Block);
      if ( BindingHandle )
        RpcRevertToSelf();
      if ( !PublisherIdentityForCurrentThread )
      {
        PublisherIdentityForCurrentThread = CTnoRPCServerImpl::Unpublish(
                                              (CTnoRPCServerImpl *)this,
                                              a3,
                                              a4,
                                              (unsigned __int16 *)Block);
        goto LABEL_25;
      }
      if ( PublisherIdentityForCurrentThread > 0 )
        PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 133;
        goto LABEL_6;
      }
    }
  }
  else
  {
    PublisherIdentityForCurrentThread = -2147020832;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 131;
LABEL_6:
      WPP_SF_d(
        *((_QWORD *)v10 + 12),
        v11,
        WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
        (unsigned int)PublisherIdentityForCurrentThread);
    }
  }
LABEL_25:
  operator delete(Block);
  LockSentry<ReadersWriterLock,0>::Unlock(v13);
  return (unsigned int)PublisherIdentityForCurrentThread;
}

```

## disassembly

```asm
0x180123c30  mov     rax, rsp
0x180123c33  mov     [rax+10h], rbx
0x180123c37  mov     [rax+18h], rbp
0x180123c3b  push    rsi
0x180123c3c  push    rdi
0x180123c3d  push    r14
0x180123c3f  sub     rsp, 30h
0x180123c43  mov     rdi, rdx
0x180123c46  mov     qword ptr [rax+8], 0
0x180123c4e  lea     rdx, [rcx+10h]
0x180123c52  mov     rsi, rcx
0x180123c55  lea     rcx, [rax-28h]
0x180123c59  mov     rbp, r9
0x180123c5c  mov     r14d, r8d
0x180123c5f  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x180123c64  lea     rcx, aPeerdistCommon; "PeerDist-Common-Client-Enabled"
0x180123c6b  call    ?IsLicenseEnabled@@YA_NPEBG@Z; IsLicenseEnabled(ushort const *)
0x180123c70  test    al, al
0x180123c72  jnz     short loc_180123CC4
0x180123c74  mov     ebx, 80070FE0h
0x180123c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180123c80  lea     rax, WPP_GLOBAL_Control
0x180123c87  cmp     rcx, rax
0x180123c8a  jz      loc_180123D88
0x180123c90  test    dword ptr [rcx+6Ch], 8000h
0x180123c97  jz      loc_180123D88
0x180123c9d  cmp     byte ptr [rcx+69h], 1
0x180123ca1  jb      loc_180123D88
0x180123ca7  mov     edx, 83h
0x180123cac  mov     rcx, [rcx+60h]
0x180123cb0  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180123cb7  mov     r9d, ebx
0x180123cba  call    WPP_SF_d
0x180123cbf  jmp     loc_180123D88
0x180123cc4  test    rdi, rdi
0x180123cc7  jz      short loc_180123D21
0x180123cc9  mov     rcx, rdi; BindingHandle
0x180123ccc  call    cs:__imp_RpcImpersonateClient
0x180123cd2  mov     ebx, eax
0x180123cd4  test    eax, eax
0x180123cd6  jz      short loc_180123D21
0x180123cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180123cdf  lea     rax, WPP_GLOBAL_Control
0x180123ce6  cmp     rcx, rax
0x180123ce9  jz      short loc_180123D12
0x180123ceb  test    dword ptr [rcx+6Ch], 8000h
0x180123cf2  jz      short loc_180123D12
0x180123cf4  cmp     byte ptr [rcx+69h], 1
0x180123cf8  jb      short loc_180123D12
0x180123cfa  mov     rcx, [rcx+60h]
0x180123cfe  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180123d05  mov     edx, 84h
0x180123d0a  mov     r9d, ebx
0x180123d0d  call    WPP_SF_d
0x180123d12  test    ebx, ebx
0x180123d14  js      short loc_180123D88
0x180123d16  movzx   ebx, bx
0x180123d19  or      ebx, 80010000h
0x180123d1f  jmp     short loc_180123D88
0x180123d21  lea     rdx, [rsp+48h+Block]; unsigned __int16 **
0x180123d26  call    ?GetPublisherIdentityForCurrentThread@@YAKPEAPEAXPEAPEAG@Z; GetPublisherIdentityForCurrentThread(void * *,ushort * *)
0x180123d2b  mov     ebx, eax
0x180123d2d  test    rdi, rdi
0x180123d30  jz      short loc_180123D38
0x180123d32  call    cs:__imp_RpcRevertToSelf
0x180123d38  test    ebx, ebx
0x180123d3a  jz      short loc_180123D73
0x180123d3c  jle     short loc_180123D47
0x180123d3e  movzx   ebx, bx
0x180123d41  or      ebx, 80070000h
0x180123d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180123d4e  lea     rax, WPP_GLOBAL_Control
0x180123d55  cmp     rcx, rax
0x180123d58  jz      short loc_180123D88
0x180123d5a  test    dword ptr [rcx+6Ch], 8000h
0x180123d61  jz      short loc_180123D88
0x180123d63  cmp     byte ptr [rcx+69h], 1
0x180123d67  jb      short loc_180123D88
0x180123d69  mov     edx, 85h
0x180123d6e  jmp     loc_180123CAC
0x180123d73  mov     r9, [rsp+48h+Block]; unsigned __int16 *
0x180123d78  mov     r8, rbp; unsigned __int8 *
0x180123d7b  mov     edx, r14d; unsigned int
0x180123d7e  mov     rcx, rsi; this
0x180123d81  call    ?Unpublish@CTnoRPCServerImpl@@AEAAJKPEAEPEAG@Z; CTnoRPCServerImpl::Unpublish(ulong,uchar *,ushort *)
0x180123d86  mov     ebx, eax
0x180123d88  mov     rcx, [rsp+48h+Block]; Block
0x180123d8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180123d92  lea     rcx, [rsp+48h+var_28]
0x180123d97  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x180123d9c  mov     rbp, [rsp+48h+arg_10]
0x180123da1  mov     eax, ebx
0x180123da3  mov     rbx, [rsp+48h+arg_8]
0x180123da8  add     rsp, 30h
0x180123dac  pop     r14
0x180123dae  pop     rdi
0x180123daf  pop     rsi
0x180123db0  retn
```

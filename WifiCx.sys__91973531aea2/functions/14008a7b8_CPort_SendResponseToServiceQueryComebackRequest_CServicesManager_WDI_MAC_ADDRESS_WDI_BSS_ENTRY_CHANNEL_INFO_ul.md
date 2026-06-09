# CPort::SendResponseToServiceQueryComebackRequest(CServicesManager *,_WDI_MAC_ADDRESS *,_WDI_BSS_ENTRY_CHANNEL_INFO *,ulong,_DOT11_ANQP_ACTION_FRAME *)

- ea: `0x14008a7b8`
- end: `0x14008aa62`
- name: `?SendResponseToServiceQueryComebackRequest@CPort@@QEAAXPEAVCServicesManager@@PEAU_WDI_MAC_ADDRESS@@PEAU_WDI_BSS_ENTRY_CHANNEL_INFO@@KPEAU_DOT11_ANQP_ACTION_FRAME@@@Z`
- size: `682`
- prototype: `void __fastcall(CPort *this, struct CServicesManager *, struct _WDI_MAC_ADDRESS *, struct _WDI_BSS_ENTRY_CHANNEL_INFO *, char, struct _DOT11_ANQP_ACTION_FRAME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400889f0`

## callees

- `0x14000c778`
- `0x14002ea0c`
- `0x14008a7b8`
- `0x14008cdf4`
- `0x14008cee4`
- `0x140094d78`
- `0x140095a68`
- `0x140096d14`

## pseudocode

```c
void __fastcall CPort::SendResponseToServiceQueryComebackRequest(
        CPort *this,
        struct CServicesManager *a2,
        struct _WDI_MAC_ADDRESS *a3,
        struct _WDI_BSS_ENTRY_CHANNEL_INFO *a4,
        char a5,
        struct _DOT11_ANQP_ACTION_FRAME *a6)
{
  struct _DOT11_ANQP_ACTION_FRAME *v6; // r14
  int v10; // edx
  CServiceComebackResponseContext *ComebackResponseContext; // r15
  __int64 v12; // r8
  int v13; // edx
  char v14; // di
  int NextFragmentToSend; // eax
  int v16; // edx
  __int64 v17; // r9
  unsigned __int8 *v18; // r8
  char v19; // bl
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-58h]
  unsigned __int16 v24; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int8 *v25; // [rsp+68h] [rbp-10h] BYREF

  v6 = a6;
  a5 = 0;
  ComebackResponseContext = CServicesManager::FindComebackResponseContext(a2, a3, *((_BYTE *)a6 + 2));
  v12 = 0;
  if ( ComebackResponseContext )
  {
    LOBYTE(a6) = 0;
    v24 = 0;
    v25 = 0;
    NextFragmentToSend = CServiceComebackResponseContext::GetNextFragmentToSend(
                           ComebackResponseContext,
                           (unsigned __int8 *)&a6,
                           (union DOT11_ANQP_FRAGMENT_ID *)&a5,
                           &v24,
                           &v25);
    v14 = NextFragmentToSend;
    if ( NextFragmentToSend )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        1,
        226,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        NextFragmentToSend);
    }
    else
    {
      v18 = v25;
      if ( v24 && v25 )
      {
        LOBYTE(v17) = (_BYTE)a6;
        LOBYTE(v18) = *((_BYTE *)v6 + 2);
        v19 = a5;
        LOWORD(v23) = 0;
        v20 = CPort::SendANQPQueryResponse(this, 13, v18, v17);
        v14 = v20;
        if ( v20 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return;
          WPP_RECORDER_SF__MAC_dD(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v21,
            v22,
            v23,
            (__int64)a3,
            *((_BYTE *)v6 + 2),
            v20);
        }
        else if ( v19 >= 0 )
        {
          CServicesManager::RemoveComebackResponseContext(a2, ComebackResponseContext);
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v14 = -102;
        WPP_RECORDER_SF__MAC_dDdq(
          WPP_GLOBAL_Control->DeviceExtension,
          *((unsigned __int8 *)v6 + 2),
          (_DWORD)v25,
          v17,
          v23,
          (__int64)a3,
          *((_BYTE *)v6 + 2),
          a5,
          v24,
          (char)v25);
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        1,
        225,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        154);
      v12 = 0;
    }
    LOBYTE(v12) = *((_BYTE *)v6 + 2);
    v14 = CPort::SendANQPQueryResponse(this, 13, v12, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        229,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        v14);
  }
}

```

## disassembly

```asm
0x14008a7b8  mov     [rsp-40h+arg_0], rcx
0x14008a7bd  push    rbp
0x14008a7be  push    rbx
0x14008a7bf  push    rsi
0x14008a7c0  push    rdi
0x14008a7c1  push    r12
0x14008a7c3  push    r13
0x14008a7c5  push    r14
0x14008a7c7  push    r15
0x14008a7c9  mov     rbp, rsp
0x14008a7cc  sub     rsp, 78h
0x14008a7d0  mov     r14, [rbp+arg_28]
0x14008a7d4  mov     rsi, r8
0x14008a7d7  mov     r12, rdx
0x14008a7da  mov     rdi, rcx
0x14008a7dd  xor     bl, bl
0x14008a7df  mov     rdx, rsi; struct _WDI_MAC_ADDRESS *
0x14008a7e2  mov     rcx, r12; this
0x14008a7e5  mov     [rbp+arg_20], bl
0x14008a7e8  mov     r8b, [r14+2]; unsigned __int8
0x14008a7ec  mov     r13, r9
0x14008a7ef  call    ?FindComebackResponseContext@CServicesManager@@QEAAPEAVCServiceComebackResponseContext@@PEAU_WDI_MAC_ADDRESS@@E@Z; CServicesManager::FindComebackResponseContext(_WDI_MAC_ADDRESS *,uchar)
0x14008a7f4  mov     r15, rax
0x14008a7f7  lea     rcx, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a7fe  xor     r8d, r8d
0x14008a801  lea     rax, WPP_RECORDER_INITIALIZED
0x14008a808  test    r15, r15
0x14008a80b  jnz     loc_14008A8E9
0x14008a811  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008a818  jz      short loc_14008A846
0x14008a81a  mov     dword ptr [rsp+78h+var_50], 0C000009Ah
0x14008a822  lea     r8d, [r15+1]
0x14008a826  mov     [rsp+78h+var_58], rcx
0x14008a82b  mov     r9d, 0E1h
0x14008a831  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a838  mov     dl, 2
0x14008a83a  mov     rcx, [rcx+40h]
0x14008a83e  call    WPP_RECORDER_SF_d
0x14008a843  xor     r8d, r8d
0x14008a846  mov     eax, [r13+0]
0x14008a84a  xor     r9d, r9d
0x14008a84d  mov     [rsp+78h+var_20], r8
0x14008a852  mov     rcx, rdi
0x14008a855  mov     [rsp+78h+var_28], r8w
0x14008a85b  mov     dword ptr [rsp+78h+var_30], eax
0x14008a85f  mov     eax, [r13+4]
0x14008a863  lea     edx, [r9+0Dh]
0x14008a867  mov     [rsp+78h+var_38], eax
0x14008a86b  mov     [rsp+78h+var_40], rsi
0x14008a870  mov     word ptr [rsp+78h+var_48], r8w
0x14008a876  mov     r8b, [r14+2]
0x14008a87a  mov     byte ptr [rsp+78h+var_50], bl
0x14008a87e  mov     word ptr [rsp+78h+var_58], 3Ch ; '<'
0x14008a885  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x14008a88a  mov     edi, eax
0x14008a88c  lea     r15, WPP_RECORDER_INITIALIZED
0x14008a893  xor     ebx, ebx
0x14008a895  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a89c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008a8a3  jz      short loc_14008A8D7
0x14008a8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a8ac  mov     dl, 5
0x14008a8ae  cmp     [rcx+29h], dl
0x14008a8b1  jnb     short loc_14008A8B9
0x14008a8b3  cmp     [rcx+48h], bx
0x14008a8b7  jz      short loc_14008A8D7
0x14008a8b9  mov     rcx, [rcx+40h]
0x14008a8bd  mov     r9d, 0E5h
0x14008a8c3  mov     dword ptr [rsp+78h+var_50], edi
0x14008a8c7  mov     r8d, 1
0x14008a8cd  mov     [rsp+78h+var_58], rsi
0x14008a8d2  call    WPP_RECORDER_SF_d
0x14008a8d7  add     rsp, 78h
0x14008a8db  pop     r15
0x14008a8dd  pop     r14
0x14008a8df  pop     r13
0x14008a8e1  pop     r12
0x14008a8e3  pop     rdi
0x14008a8e4  pop     rsi
0x14008a8e5  pop     rbx
0x14008a8e6  pop     rbp
0x14008a8e7  retn
0x14008a8e9  xor     ebx, ebx
0x14008a8eb  lea     rax, [rbp+var_10]
0x14008a8ef  lea     r9, [rbp+var_18]; unsigned __int16 *
0x14008a8f3  mov     byte ptr [rbp+arg_28], bl
0x14008a8f6  lea     r8, [rbp+arg_20]; union DOT11_ANQP_FRAGMENT_ID *
0x14008a8fa  mov     [rbp+var_18], bx
0x14008a8fe  lea     rdx, [rbp+arg_28]; unsigned __int8 *
0x14008a902  mov     [rbp+var_10], rbx
0x14008a906  mov     rcx, r15; this
0x14008a909  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x14008a90e  call    ?GetNextFragmentToSend@CServiceComebackResponseContext@@QEAAHPEAEPEATDOT11_ANQP_FRAGMENT_ID@@PEAGPEAPEAE@Z; CServiceComebackResponseContext::GetNextFragmentToSend(uchar *,DOT11_ANQP_FRAGMENT_ID *,ushort *,uchar * *)
0x14008a913  mov     edi, eax
0x14008a915  test    eax, eax
0x14008a917  jz      short loc_14008A95A
0x14008a919  lea     r15, WPP_RECORDER_INITIALIZED
0x14008a920  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008a927  jz      short loc_14008A8D7
0x14008a929  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a930  lea     rsi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a937  mov     dword ptr [rsp+78h+var_50], eax
0x14008a93b  lea     r8d, [rbx+1]
0x14008a93f  mov     r9d, 0E2h
0x14008a945  mov     [rsp+78h+var_58], rsi
0x14008a94a  mov     dl, 2
0x14008a94c  mov     rcx, [rcx+40h]
0x14008a950  call    WPP_RECORDER_SF_d
0x14008a955  jmp     loc_14008A89C
0x14008a95a  movzx   eax, [rbp+var_18]
0x14008a95e  mov     r8, [rbp+var_10]
0x14008a962  test    ax, ax
0x14008a965  jz      loc_14008AA15
0x14008a96b  test    r8, r8
0x14008a96e  jz      loc_14008AA15
0x14008a974  mov     r9b, byte ptr [rbp+arg_28]
0x14008a978  mov     edx, ebx
0x14008a97a  mov     rcx, [rbp+arg_0]
0x14008a97e  mov     [rsp+78h+var_20], r8
0x14008a983  mov     r8b, [r14+2]
0x14008a987  mov     [rsp+78h+var_28], ax
0x14008a98c  mov     eax, [r13+0]
0x14008a990  mov     dword ptr [rsp+78h+var_30], eax
0x14008a994  mov     eax, [r13+4]
0x14008a998  mov     [rsp+78h+var_38], eax
0x14008a99c  mov     [rsp+78h+var_40], rsi
0x14008a9a1  mov     word ptr [rsp+78h+var_48], bx
0x14008a9a6  mov     bl, [rbp+arg_20]
0x14008a9a9  mov     byte ptr [rsp+78h+var_50], bl
0x14008a9ad  mov     word ptr [rsp+78h+var_58], dx
0x14008a9b2  mov     edx, 0Dh
0x14008a9b7  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x14008a9bc  mov     edi, eax
0x14008a9be  test    eax, eax
0x14008a9c0  jz      short loc_14008A9FD
0x14008a9c2  lea     r15, WPP_RECORDER_INITIALIZED
0x14008a9c9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008a9d0  jz      loc_14008A8D7
0x14008a9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a9dd  movzx   eax, byte ptr [r14+2]
0x14008a9e2  mov     dword ptr [rsp+78h+var_40], edi
0x14008a9e6  mov     [rsp+78h+var_48], eax
0x14008a9ea  mov     rcx, [rcx+40h]
0x14008a9ee  mov     [rsp+78h+var_50], rsi
0x14008a9f3  call    WPP_RECORDER_SF__MAC_dD
0x14008a9f8  jmp     loc_14008A893
0x14008a9fd  test    bl, bl
0x14008a9ff  js      loc_14008A88C
0x14008aa05  mov     rdx, r15; struct CServiceComebackResponseContext *
0x14008aa08  mov     rcx, r12; this
0x14008aa0b  call    ?RemoveComebackResponseContext@CServicesManager@@QEAAXPEAVCServiceComebackResponseContext@@@Z; CServicesManager::RemoveComebackResponseContext(CServiceComebackResponseContext *)
0x14008aa10  jmp     loc_14008A88C
0x14008aa15  lea     r15, WPP_RECORDER_INITIALIZED
0x14008aa1c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008aa23  jz      loc_14008A8D7
0x14008aa29  movzx   ecx, [rbp+arg_20]
0x14008aa2d  mov     edi, 0C000009Ah
0x14008aa32  movzx   edx, byte ptr [r14+2]
0x14008aa37  mov     [rsp+78h+var_30], r8
0x14008aa3c  mov     [rsp+78h+var_38], eax
0x14008aa40  mov     dword ptr [rsp+78h+var_40], ecx
0x14008aa44  mov     rcx, cs:WPP_GLOBAL_Control
0x14008aa4b  mov     [rsp+78h+var_48], edx
0x14008aa4f  mov     [rsp+78h+var_50], rsi
0x14008aa54  mov     rcx, [rcx+40h]
0x14008aa58  call    WPP_RECORDER_SF__MAC_dDdq
0x14008aa5d  jmp     loc_14008A895
```

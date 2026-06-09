# MethodAttemptDisconnect(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14003d7b0`
- end: `0x14003d932`
- name: `?MethodAttemptDisconnect@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x14000e690`
- `0x140012b28`
- `0x14001bf14`
- `0x1400329ec`
- `0x14003d7b0`
- `0x14003e0f8`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14003d849`
- `ks!KsGetFilterFromIrp` at `0x14003d849`

## pseudocode

```c
__int64 __fastcall MethodAttemptDisconnect(struct _IRP *a1, struct KSIDENTIFIER *a2, void *a3)
{
  char v4; // di
  bool v5; // dl
  unsigned int v6; // ebx
  PKSFILTER FilterFromIrp; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rsi
  int v11; // eax
  NTSTATUS v12; // ebx
  __int64 *v13; // rdx

  v4 = 1;
  v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      16,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      (char)a1);
  v6 = -1073741811;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( FilterFromIrp )
  {
    v10 = *((_QWORD *)FilterFromIrp->Context + 2);
    if ( v10 )
    {
      IrpQueue::PendRequest((IrpQueue *)(v10 + 120), a1);
      v11 = A2DP_Device::RequestDisconnect((A2DP_Device *)v10);
      v12 = v11;
      if ( v11 < 0 || v11 == 258 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v4 = 0;
        }
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v13 = WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids;
          LOBYTE(v13) = v4;
          LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v13,
            v9,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            5,
            17,
            (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
            v11);
        }
        IrpQueue::CompleteAllRequests((PIO_CSQ)(v10 + 120), v12);
      }
      v6 = 259;
    }
  }
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 8) != 0 )
    McTemplateK0q_EtwWriteTransfer(v8, MethodAttemptDisconnect, v9, v6);
  return v6;
}

```

## disassembly

```asm
0x14003d7b0  push    rbx
0x14003d7b2  push    rbp
0x14003d7b3  push    rsi
0x14003d7b4  push    rdi
0x14003d7b5  push    r12
0x14003d7b7  push    r13
0x14003d7b9  push    r14
0x14003d7bb  push    r15
0x14003d7bd  sub     rsp, 58h
0x14003d7c1  mov     rbp, rcx
0x14003d7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d7cb  lea     r12, WPP_GLOBAL_Control
0x14003d7d2  mov     dil, 1
0x14003d7d5  mov     r15d, 10h
0x14003d7db  cmp     rcx, r12
0x14003d7de  jz      short loc_14003D7F3
0x14003d7e0  mov     eax, [rcx+2Ch]
0x14003d7e3  test    r15b, al
0x14003d7e6  jz      short loc_14003D7F3
0x14003d7e8  cmp     byte ptr [rcx+29h], 4
0x14003d7ec  jb      short loc_14003D7F3
0x14003d7ee  mov     dl, dil
0x14003d7f1  jmp     short loc_14003D7F5
0x14003d7f3  xor     dl, dl
0x14003d7f5  lea     r13, WPP_RECORDER_INITIALIZED
0x14003d7fc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003d803  lea     rax, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x14003d80a  setnz   r8b
0x14003d80e  test    dl, dl
0x14003d810  jnz     short loc_14003D817
0x14003d812  test    r8b, r8b
0x14003d815  jz      short loc_14003D841
0x14003d817  mov     r9, [rcx+40h]
0x14003d81b  mov     rcx, [rcx+18h]
0x14003d81f  mov     [rsp+98h+var_58], rbp
0x14003d824  mov     [rsp+98h+var_60], rax
0x14003d829  mov     [rsp+98h+var_68], r15w
0x14003d82f  mov     [rsp+98h+var_70], 5
0x14003d837  mov     [rsp+98h+var_78], 4
0x14003d83c  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003d841  mov     rcx, rbp; Irp
0x14003d844  mov     ebx, 0C000000Dh
0x14003d849  call    cs:__imp_KsGetFilterFromIrp
0x14003d850  nop     dword ptr [rax+rax+00h]
0x14003d855  test    rax, rax
0x14003d858  jz      loc_14003D906
0x14003d85e  mov     rax, [rax+10h]
0x14003d862  mov     rsi, [rax+10h]
0x14003d866  test    rsi, rsi
0x14003d869  jz      loc_14003D906
0x14003d86f  mov     rdx, rbp; struct _IRP *
0x14003d872  lea     rcx, [rsi+78h]; this
0x14003d876  call    ?PendRequest@IrpQueue@@QEAAXPEAU_IRP@@@Z; IrpQueue::PendRequest(_IRP *)
0x14003d87b  mov     rcx, rsi; this
0x14003d87e  call    ?RequestDisconnect@A2DP_Device@@QEAAJXZ; A2DP_Device::RequestDisconnect(void)
0x14003d883  mov     ebx, eax
0x14003d885  test    eax, eax
0x14003d887  js      short loc_14003D890
0x14003d889  cmp     eax, 102h
0x14003d88e  jnz     short loc_14003D901
0x14003d890  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d897  cmp     rcx, r12
0x14003d89a  jz      short loc_14003D8AA
0x14003d89c  mov     eax, [rcx+2Ch]
0x14003d89f  test    r15b, al
0x14003d8a2  jz      short loc_14003D8AA
0x14003d8a4  cmp     byte ptr [rcx+29h], 4
0x14003d8a8  jnb     short loc_14003D8AD
0x14003d8aa  xor     dil, dil
0x14003d8ad  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003d8b4  setnz   r8b
0x14003d8b8  test    dil, dil
0x14003d8bb  jnz     short loc_14003D8C2
0x14003d8bd  test    r8b, r8b
0x14003d8c0  jz      short loc_14003D8F6
0x14003d8c2  mov     r9, [rcx+40h]
0x14003d8c6  lea     rdx, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x14003d8cd  mov     rcx, [rcx+18h]
0x14003d8d1  mov     dword ptr [rsp+98h+var_58], ebx
0x14003d8d5  mov     [rsp+98h+var_60], rdx
0x14003d8da  mov     dl, dil
0x14003d8dd  mov     [rsp+98h+var_68], 11h
0x14003d8e4  mov     [rsp+98h+var_70], 5
0x14003d8ec  mov     [rsp+98h+var_78], 4
0x14003d8f1  call    WPP_RECORDER_AND_TRACE_SF_d
0x14003d8f6  mov     edx, ebx; int
0x14003d8f8  lea     rcx, [rsi+78h]; Csq
0x14003d8fc  call    ?CompleteAllRequests@IrpQueue@@QEAAXJ@Z; IrpQueue::CompleteAllRequests(long)
0x14003d901  mov     ebx, 103h
0x14003d906  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 8
0x14003d90d  jz      short loc_14003D91E
0x14003d90f  mov     r9d, ebx
0x14003d912  lea     rdx, _MethodAttemptDisconnect
0x14003d919  call    McTemplateK0q_EtwWriteTransfer
0x14003d91e  mov     eax, ebx
0x14003d920  add     rsp, 58h
0x14003d924  pop     r15
0x14003d926  pop     r14
0x14003d928  pop     r13
0x14003d92a  pop     r12
0x14003d92c  pop     rdi
0x14003d92d  pop     rsi
0x14003d92e  pop     rbp
0x14003d92f  pop     rbx
0x14003d930  retn
```

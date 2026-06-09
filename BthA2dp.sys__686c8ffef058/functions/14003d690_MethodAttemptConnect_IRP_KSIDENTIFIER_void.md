# MethodAttemptConnect(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14003d690`
- end: `0x14003d79c`
- name: `?MethodAttemptConnect@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x140012b28`
- `0x140015060`
- `0x14001bf14`
- `0x14003d400`
- `0x14003d690`
- `0x14003e0f8`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14003d71d`
- `ks!KsGetFilterFromIrp` at `0x14003d71d`

## pseudocode

```c
__int64 __fastcall MethodAttemptConnect(struct _IRP *a1, struct KSIDENTIFIER *a2, void *a3)
{
  bool v4; // dl
  unsigned int v5; // ebx
  PKSFILTER FilterFromIrp; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned __int64 *v9; // rdi
  NTSTATUS v10; // eax

  v4 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      15,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      (char)a1);
  v5 = -1073741811;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( FilterFromIrp )
  {
    v9 = (unsigned __int64 *)*((_QWORD *)FilterFromIrp->Context + 2);
    if ( v9 )
    {
      IrpQueue::PendRequest((IrpQueue *)(v9 + 4), a1);
      AVFilter::LogConnectionAttempt(v9[90]);
      v10 = A2DP_Device::RequestConnect((A2DP_Device *)v9, 0);
      if ( v10 < 0 )
        IrpQueue::CompleteAllRequests((PIO_CSQ)(v9 + 4), v10);
      v5 = 259;
    }
  }
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v7, MethodAttemptConnect, v8, v5);
  return v5;
}

```

## disassembly

```asm
0x14003d690  mov     [rsp+arg_0], rbx
0x14003d695  mov     [rsp+arg_8], rsi
0x14003d69a  push    rdi
0x14003d69b  sub     rsp, 50h
0x14003d69f  mov     rsi, rcx
0x14003d6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d6a9  lea     rax, WPP_GLOBAL_Control
0x14003d6b0  cmp     rcx, rax
0x14003d6b3  jz      short loc_14003D6C6
0x14003d6b5  mov     eax, [rcx+2Ch]
0x14003d6b8  test    al, 10h
0x14003d6ba  jz      short loc_14003D6C6
0x14003d6bc  cmp     byte ptr [rcx+29h], 4
0x14003d6c0  jb      short loc_14003D6C6
0x14003d6c2  mov     dl, 1
0x14003d6c4  jmp     short loc_14003D6C8
0x14003d6c6  xor     dl, dl
0x14003d6c8  lea     rax, WPP_RECORDER_INITIALIZED
0x14003d6cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003d6d6  setnz   r8b
0x14003d6da  test    dl, dl
0x14003d6dc  jnz     short loc_14003D6E3
0x14003d6de  test    r8b, r8b
0x14003d6e1  jz      short loc_14003D715
0x14003d6e3  mov     r9, [rcx+40h]
0x14003d6e7  lea     rax, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x14003d6ee  mov     rcx, [rcx+18h]
0x14003d6f2  mov     [rsp+58h+var_18], rsi
0x14003d6f7  mov     [rsp+58h+var_20], rax
0x14003d6fc  mov     [rsp+58h+var_28], 0Fh
0x14003d703  mov     [rsp+58h+var_30], 5
0x14003d70b  mov     [rsp+58h+var_38], 4
0x14003d710  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003d715  mov     rcx, rsi; Irp
0x14003d718  mov     ebx, 0C000000Dh
0x14003d71d  call    cs:__imp_KsGetFilterFromIrp
0x14003d724  nop     dword ptr [rax+rax+00h]
0x14003d729  test    rax, rax
0x14003d72c  jz      short loc_14003D771
0x14003d72e  mov     rax, [rax+10h]
0x14003d732  mov     rdi, [rax+10h]
0x14003d736  test    rdi, rdi
0x14003d739  jz      short loc_14003D771
0x14003d73b  mov     rdx, rsi; struct _IRP *
0x14003d73e  lea     rcx, [rdi+20h]; this
0x14003d742  call    ?PendRequest@IrpQueue@@QEAAXPEAU_IRP@@@Z; IrpQueue::PendRequest(_IRP *)
0x14003d747  mov     rcx, [rdi+2D0h]; unsigned __int64
0x14003d74e  call    ?LogConnectionAttempt@AVFilter@@SAX_K@Z; AVFilter::LogConnectionAttempt(unsigned __int64)
0x14003d753  xor     edx, edx; bool
0x14003d755  mov     rcx, rdi; this
0x14003d758  call    ?RequestConnect@A2DP_Device@@QEAAJ_N@Z; A2DP_Device::RequestConnect(bool)
0x14003d75d  test    eax, eax
0x14003d75f  jns     short loc_14003D76C
0x14003d761  mov     edx, eax; int
0x14003d763  lea     rcx, [rdi+20h]; Csq
0x14003d767  call    ?CompleteAllRequests@IrpQueue@@QEAAXJ@Z; IrpQueue::CompleteAllRequests(long)
0x14003d76c  mov     ebx, 103h
0x14003d771  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x14003d778  jz      short loc_14003D789
0x14003d77a  mov     r9d, ebx
0x14003d77d  lea     rdx, _MethodAttemptConnect
0x14003d784  call    McTemplateK0q_EtwWriteTransfer
0x14003d789  mov     rsi, [rsp+58h+arg_8]
0x14003d78e  mov     eax, ebx
0x14003d790  mov     rbx, [rsp+58h+arg_0]
0x14003d795  add     rsp, 50h
0x14003d799  pop     rdi
0x14003d79a  retn
```

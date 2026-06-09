# A2DP_Device::AVDT_Connect_Rsp(void *,void *,unsigned __int64)

- ea: `0x14001ed80`
- end: `0x14001ee8c`
- name: `?AVDT_Connect_Rsp@A2DP_Device@@CAJPEAX0_K@Z`
- size: `268`
- prototype: `__int64 __fastcall(void *, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x140006410`
- `0x140007374`
- `0x140012a5c`
- `0x14001ed80`
- `0x14001ee94`
- `0x14001f2b8`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14001ee72`
- `ntoskrnl!KeSetTimer` at `0x14001ee72`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001ee39`
- `btampm!BtaMpmUpdateConnectionStatus` at `0x14001ee39`

## pseudocode

```c
__int64 __fastcall A2DP_Device::AVDT_Connect_Rsp(void *a1, void *a2, char a3)
{
  int v4; // edx
  struct A2DP_Device *v5; // rbx
  int v6; // r8d
  _QWORD *v8; // [rsp+50h] [rbp-18h] BYREF
  utl::_RefCountBase *v9; // [rsp+58h] [rbp-10h]

  v5 = A2DP_Device::CheckCallbackParms(a1, a2);
  LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v6,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      93,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      (char)v5,
      a3);
  }
  A2DP_Device::SetAvdtpConnectionStatus(v5, 0);
  A2DP_Device::GetMPMContext(v5, &v8);
  if ( v8 )
    BtaMpmUpdateConnectionStatus(*v8, 1, 0);
  if ( v9 )
    utl::_RefCountBase::_DecStrong(v9);
  if ( *((_BYTE *)v5 + 2808) )
    KeSetTimer((PKTIMER)((char *)v5 + 3016), (LARGE_INTEGER)-15000000LL, (PKDPC)((char *)v5 + 3080));
  return 0;
}

```

## disassembly

```asm
0x14001ed80  mov     [rsp+arg_0], rbx
0x14001ed85  push    rdi
0x14001ed86  sub     rsp, 60h
0x14001ed8a  mov     rdi, r8
0x14001ed8d  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x14001ed92  mov     rbx, rax
0x14001ed95  mov     rax, cs:WPP_GLOBAL_Control
0x14001ed9c  lea     rcx, WPP_GLOBAL_Control
0x14001eda3  cmp     rax, rcx
0x14001eda6  jz      short loc_14001EDBA
0x14001eda8  mov     ecx, [rax+2Ch]
0x14001edab  test    cl, 10h
0x14001edae  jz      short loc_14001EDBA
0x14001edb0  cmp     byte ptr [rax+29h], 4
0x14001edb4  jb      short loc_14001EDBA
0x14001edb6  mov     dl, 1
0x14001edb8  jmp     short loc_14001EDBC
0x14001edba  xor     dl, dl
0x14001edbc  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001edc3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001edca  setnz   r8b
0x14001edce  test    dl, dl
0x14001edd0  jnz     short loc_14001EDD7
0x14001edd2  test    r8b, r8b
0x14001edd5  jz      short loc_14001EE0E
0x14001edd7  mov     r9, [rax+40h]
0x14001eddb  lea     rcx, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14001ede2  mov     [rsp+68h+var_20], rdi
0x14001ede7  mov     [rsp+68h+var_28], rbx
0x14001edec  mov     [rsp+68h+var_30], rcx
0x14001edf1  mov     rcx, [rax+18h]
0x14001edf5  mov     [rsp+68h+var_38], 5Dh ; ']'
0x14001edfc  mov     [rsp+68h+var_40], 5
0x14001ee04  mov     [rsp+68h+var_48], 4
0x14001ee09  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14001ee0e  xor     edx, edx
0x14001ee10  mov     rcx, rbx
0x14001ee13  call    ?SetAvdtpConnectionStatus@A2DP_Device@@QEAAXW4ConnectionStatus@@@Z; A2DP_Device::SetAvdtpConnectionStatus(ConnectionStatus)
0x14001ee18  lea     rdx, [rsp+68h+var_18]
0x14001ee1d  mov     rcx, rbx
0x14001ee20  call    ?GetMPMContext@A2DP_Device@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@utl@@XZ; A2DP_Device::GetMPMContext(void)
0x14001ee25  mov     rcx, [rsp+68h+var_18]
0x14001ee2a  test    rcx, rcx
0x14001ee2d  jz      short loc_14001EE45
0x14001ee2f  mov     rcx, [rcx]
0x14001ee32  xor     r8d, r8d
0x14001ee35  lea     edx, [r8+1]
0x14001ee39  call    cs:__imp_BtaMpmUpdateConnectionStatus
0x14001ee40  nop     dword ptr [rax+rax+00h]
0x14001ee45  mov     rcx, [rsp+68h+var_10]; this
0x14001ee4a  test    rcx, rcx
0x14001ee4d  jz      short loc_14001EE54
0x14001ee4f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001ee54  cmp     byte ptr [rbx+0AF8h], 0
0x14001ee5b  jz      short loc_14001EE7E
0x14001ee5d  lea     r8, [rbx+0C08h]; Dpc
0x14001ee64  mov     rdx, 0FFFFFFFFFF1B1E40h; DueTime
0x14001ee6b  lea     rcx, [rbx+0BC8h]; Timer
0x14001ee72  call    cs:__imp_KeSetTimer
0x14001ee79  nop     dword ptr [rax+rax+00h]
0x14001ee7e  mov     rbx, [rsp+68h+arg_0]
0x14001ee83  xor     eax, eax
0x14001ee85  add     rsp, 60h
0x14001ee89  pop     rdi
0x14001ee8a  retn
```

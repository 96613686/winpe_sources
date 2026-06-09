# Avdtp_impl::CompleteHeaderAndSendSignal(_SINGLE_PCK_CMD *,uchar,long,uchar,uchar,unsigned __int64)

- ea: `0x140016d48`
- end: `0x140016f41`
- name: `?CompleteHeaderAndSendSignal@Avdtp_impl@@AEAAXPEAU_SINGLE_PCK_CMD@@EJEE_K@Z`
- size: `505`
- prototype: `void __usercall(Avdtp_impl *__hidden this@<rcx>, struct _SINGLE_PCK_CMD *@<rdx>, unsigned __int8@<r8b>, int@<r9d>, char, unsigned __int8, unsigned __int64)`
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140045f40`
- `0x1400464b0`
- `0x140048200`
- `0x1400485b0`
- `0x1400487d0`
- `0x140049e80`
- `0x14004df64`
- `0x14004e420`
- `0x14004f510`
- `0x140050150`
- `0x1400508b0`
- `0x140051000`
- `0x140051400`

## callees

- `0x140016ae8`
- `0x140016d48`
- `0x140019f5c`
- `0x14002d890`
- `0x140046c88`
- `0x140052aa4`
- `0x140054b10`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140016ed5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016ed5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016eb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016eb5`

## pseudocode

```c
void __fastcall Avdtp_impl::CompleteHeaderAndSendSignal(
        Avdtp_impl *this,
        struct _SINGLE_PCK_CMD *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        unsigned __int64 a7)
{
  __int64 v7; // rbx
  char v9; // si
  int v11; // edx
  int v12; // r8d
  char v13; // cl
  KIRQL v14; // al
  unsigned __int16 v15; // r15
  void *v16; // r12
  unsigned __int8 v17; // r9
  unsigned __int16 v18; // cx
  unsigned __int8 v19; // [rsp+20h] [rbp-78h]

  v7 = (int)a4;
  v9 = a3;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_LLLq(WPP_GLOBAL_Control->AttachedDevice, v11, v12, WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  else
  {
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_avdtp_txnidLLL(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  v13 = (4 * v9) ^ *(_BYTE *)a2 & 3;
  *((_BYTE *)a2 + 1) = a5 & 0x3F;
  *(_BYTE *)a2 = ((16 * v7) | v13 & 0xF) ^ (a6 ^ ((16 * v7) | v13 & 0xF)) & 3;
  if ( a6 )
  {
    if ( (unsigned int)(unsigned __int8)a6 - 2 <= 1 )
      _InterlockedCompareExchange((volatile signed __int32 *)this + v7 + 418, 0, 0);
  }
  else
  {
    Avdtp_impl::AtomicStoreCmdInfo(this, (unsigned int)v7, a2, (unsigned int)a7, 1);
  }
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 200);
  v15 = *((_WORD *)this + 762);
  v16 = (void *)*((_QWORD *)this + 179);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 200, v14);
  if ( v15 )
    v18 = v15;
  else
    v18 = 672;
  if ( a7 <= v18 )
    Avdtp_impl::SingleSignalPacketTransmit(this, v16, a2, v17, a6, a7);
  else
    Avdtp_impl::BeginMultipleSignalPacketTransmit(this, v18, v16, a2, v19, a6, a7);
}

```

## disassembly

```asm
0x140016d48  push    rbx
0x140016d4a  push    rbp
0x140016d4b  push    rsi
0x140016d4c  push    rdi
0x140016d4d  push    r12
0x140016d4f  push    r14
0x140016d51  push    r15
0x140016d53  sub     rsp, 60h
0x140016d57  movsxd  rbx, r9d
0x140016d5a  mov     r14, rdx
0x140016d5d  movzx   esi, r8b
0x140016d61  mov     rdi, rcx
0x140016d64  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140016d69  movzx   ebp, [rsp+98h+arg_28]
0x140016d71  movzx   r15d, [rsp+98h+arg_20]
0x140016d7a  test    eax, eax
0x140016d7c  jz      short loc_140016DE4
0x140016d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d85  lea     rax, WPP_GLOBAL_Control
0x140016d8c  cmp     rcx, rax
0x140016d8f  jz      short loc_140016DA2
0x140016d91  mov     eax, [rcx+2Ch]
0x140016d94  test    al, 8
0x140016d96  jz      short loc_140016DA2
0x140016d98  cmp     byte ptr [rcx+29h], 4
0x140016d9c  jb      short loc_140016DA2
0x140016d9e  mov     dl, 1
0x140016da0  jmp     short loc_140016DA4
0x140016da2  xor     dl, dl
0x140016da4  lea     rax, WPP_RECORDER_INITIALIZED
0x140016dab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016db2  setnz   r8b
0x140016db6  test    dl, dl
0x140016db8  jnz     short loc_140016DC3
0x140016dba  test    r8b, r8b
0x140016dbd  jz      loc_140016E43
0x140016dc3  mov     r9, [rcx+40h]
0x140016dc7  mov     rcx, [rcx+18h]
0x140016dcb  mov     [rsp+98h+var_40], rdi
0x140016dd0  mov     [rsp+98h+var_48], esi
0x140016dd4  mov     [rsp+98h+var_50], ebp
0x140016dd8  mov     [rsp+98h+var_58], r15d
0x140016ddd  call    WPP_RECORDER_AND_TRACE_SF_LLLq
0x140016de2  jmp     short loc_140016E43
0x140016de4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016deb  lea     rax, WPP_GLOBAL_Control
0x140016df2  cmp     rcx, rax
0x140016df5  jz      short loc_140016E08
0x140016df7  mov     eax, [rcx+2Ch]
0x140016dfa  test    al, 8
0x140016dfc  jz      short loc_140016E08
0x140016dfe  cmp     byte ptr [rcx+29h], 4
0x140016e02  jb      short loc_140016E08
0x140016e04  mov     dl, 1
0x140016e06  jmp     short loc_140016E0A
0x140016e08  xor     dl, dl
0x140016e0a  lea     rax, WPP_RECORDER_INITIALIZED
0x140016e11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140016e18  setnz   r8b
0x140016e1c  test    dl, dl
0x140016e1e  jnz     short loc_140016E25
0x140016e20  test    r8b, r8b
0x140016e23  jz      short loc_140016E43
0x140016e25  mov     r9, [rcx+40h]
0x140016e29  mov     rcx, [rcx+18h]
0x140016e2d  mov     dword ptr [rsp+98h+var_40], r15d
0x140016e32  mov     [rsp+98h+var_48], ebp
0x140016e36  mov     [rsp+98h+var_50], esi
0x140016e3a  mov     [rsp+98h+var_58], ebx
0x140016e3e  call    WPP_RECORDER_AND_TRACE_SF_avdtp_txnidLLL
0x140016e43  mov     cl, [r14]
0x140016e46  and     r15b, 3Fh
0x140016e4a  and     cl, 3
0x140016e4d  shl     sil, 2
0x140016e51  xor     cl, sil
0x140016e54  mov     [r14+1], r15b
0x140016e58  mov     rsi, qword ptr [rsp+98h+arg_30]
0x140016e60  and     cl, 0Fh
0x140016e63  mov     al, bl
0x140016e65  shl     al, 4
0x140016e68  or      cl, al
0x140016e6a  mov     al, cl
0x140016e6c  xor     al, bpl
0x140016e6f  and     al, 3
0x140016e71  xor     al, cl
0x140016e73  mov     ecx, ebp
0x140016e75  mov     [r14], al
0x140016e78  test    bpl, bpl
0x140016e7b  jz      short loc_140016E96
0x140016e7d  sub     ecx, 2
0x140016e80  jz      short loc_140016E87
0x140016e82  cmp     ecx, 1
0x140016e85  jnz     short loc_140016EAB
0x140016e87  xor     ecx, ecx
0x140016e89  xor     eax, eax
0x140016e8b  lock cmpxchg [rdi+rbx*4+688h], ecx
0x140016e94  jmp     short loc_140016EAB
0x140016e96  mov     r9d, esi; unsigned int
0x140016e99  mov     [rsp+98h+var_78], 1; unsigned __int8
0x140016e9e  mov     r8, r14; struct _SINGLE_PCK_CMD *
0x140016ea1  mov     edx, ebx; int
0x140016ea3  mov     rcx, rdi; this
0x140016ea6  call    ?AtomicStoreCmdInfo@Avdtp_impl@@AEAAXJPEBU_SINGLE_PCK_CMD@@K_N@Z; Avdtp_impl::AtomicStoreCmdInfo(long,_SINGLE_PCK_CMD const *,ulong,bool)
0x140016eab  lea     rbx, [rdi+640h]
0x140016eb2  mov     rcx, rbx; SpinLock
0x140016eb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016ebc  nop     dword ptr [rax+rax+00h]
0x140016ec1  movzx   r15d, word ptr [rdi+5F4h]
0x140016ec9  mov     rcx, rbx; SpinLock
0x140016ecc  mov     r12, [rdi+598h]
0x140016ed3  mov     dl, al; NewIrql
0x140016ed5  call    cs:__imp_KeReleaseSpinLock
0x140016edc  nop     dword ptr [rax+rax+00h]
0x140016ee1  xor     eax, eax
0x140016ee3  cmp     ax, r15w
0x140016ee7  jnz     short loc_140016EF0
0x140016ee9  mov     ecx, 2A0h
0x140016eee  jmp     short loc_140016EF4
0x140016ef0  movzx   ecx, r15w
0x140016ef4  movzx   eax, cx
0x140016ef7  cmp     rsi, rax
0x140016efa  jbe     short loc_140016F19
0x140016efc  movzx   edx, cx; unsigned int
0x140016eff  mov     r9, r14; struct _SINGLE_PCK_CMD *
0x140016f02  mov     rcx, rdi; this
0x140016f05  mov     [rsp+98h+var_68], rsi; unsigned __int64
0x140016f0a  mov     r8, r12; void *
0x140016f0d  mov     [rsp+98h+var_70], bpl; char
0x140016f12  call    ?BeginMultipleSignalPacketTransmit@Avdtp_impl@@AEAAJKPEAXPEAU_SINGLE_PCK_CMD@@EE_K@Z; Avdtp_impl::BeginMultipleSignalPacketTransmit(ulong,void *,_SINGLE_PCK_CMD *,uchar,uchar,unsigned __int64)
0x140016f17  jmp     short loc_140016F31
0x140016f19  mov     qword ptr [rsp+98h+var_70], rsi; unsigned __int64
0x140016f1e  mov     r8, r14; struct _SINGLE_PCK_CMD *
0x140016f21  mov     rdx, r12; void *
0x140016f24  mov     [rsp+98h+var_78], bpl; char
0x140016f29  mov     rcx, rdi; this
0x140016f2c  call    ?SingleSignalPacketTransmit@Avdtp_impl@@AEAAJPEAXPEAU_SINGLE_PCK_CMD@@EE_K@Z; Avdtp_impl::SingleSignalPacketTransmit(void *,_SINGLE_PCK_CMD *,uchar,uchar,unsigned __int64)
0x140016f31  add     rsp, 60h
0x140016f35  pop     r15
0x140016f37  pop     r14
0x140016f39  pop     r12
0x140016f3b  pop     rdi
0x140016f3c  pop     rsi
0x140016f3d  pop     rbp
0x140016f3e  pop     rbx
0x140016f3f  retn
```

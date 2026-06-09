# CPcmPin::ProcessCloneStreamPointersToComplete(__int64,__int64)

- ea: `0x140004720`
- end: `0x140004aaf`
- name: `?ProcessCloneStreamPointersToComplete@CPcmPin@@AEAA_K_J0@Z`
- size: `911`
- prototype: `unsigned __int64 __fastcall(CPcmPin *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003cc0`

## callees

- `0x140004720`
- `0x140005060`
- `0x140012a5c`
- `0x14001be60`
- `0x14003b5ec`
- `0x14003b9ac`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004879`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004879`
- `ks!KsStreamPointerDelete` at `0x14000482d`
- `ks!KsStreamPointerDelete` at `0x14000482d`
- `ks!KsStreamPointerGetNextClone` at `0x1400047c2`
- `ks!KsStreamPointerGetNextClone` at `0x1400047c2`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x140004794`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x140004794`

## pseudocode

```c
__int64 __fastcall CPcmPin::ProcessCloneStreamPointersToComplete(CPcmPin *this, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // r13
  __int64 v6; // rsi
  PKSSTREAM_POINTER FirstCloneStreamPointer; // rbx
  _QWORD *Context; // rbp
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // r8
  PKSSTREAM_POINTER NextClone; // r14
  KIRQL v14; // al
  __int64 v15; // r8
  KIRQL v16; // r12
  __int64 v17; // r9
  __int64 v18; // rsi
  bool v19; // cl
  __int64 v20; // [rsp+20h] [rbp-78h]
  int v21; // [rsp+28h] [rbp-70h]
  int v22; // [rsp+30h] [rbp-68h]
  int v23; // [rsp+38h] [rbp-60h]
  char *v24; // [rsp+60h] [rbp-38h] BYREF
  KIRQL v25; // [rsp+68h] [rbp-30h]
  __int64 v26; // [rsp+B0h] [rbp+18h]

  v26 = a3;
  v3 = a3;
  v4 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType);
  if ( (_BYTE)a2 || (_BYTE)a3 )
  {
    LOWORD(v22) = 48;
    WPP_RECORDER_AND_TRACE_SF_i(WPP_GLOBAL_Control->AttachedDevice, a2, a3, WPP_GLOBAL_Control->DeviceExtension, 5);
  }
  v6 = -1;
  FirstCloneStreamPointer = KsPinGetFirstCloneStreamPointer(*((PKSPIN *)this + 2));
  if ( !FirstCloneStreamPointer )
    return -1;
  do
  {
    Context = FirstCloneStreamPointer->Context;
    NextClone = KsStreamPointerGetNextClone(FirstCloneStreamPointer);
    if ( FirstCloneStreamPointer == *((PKSSTREAM_POINTER *)this + 5) )
      break;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v9 || (_BYTE)v11 )
      WPP_RECORDER_AND_TRACE_SF_qid(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        v21,
        v22,
        v23,
        (char)FirstCloneStreamPointer,
        Context[2],
        *((_DWORD *)this + 12));
    if ( v6 == -1 )
    {
      if ( v4 < Context[2] )
      {
        v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 10);
        v15 = *((_QWORD *)this + 13);
        v16 = v14;
        if ( v15 )
        {
          v17 = *((_QWORD *)this + 14);
          v18 = v17 * (Context[2] - *((_QWORD *)this + 12)) / *((int *)this + 13) + v15;
          v19 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                     && LOWORD(WPP_GLOBAL_Control->DeviceType);
          if ( v19 || (_BYTE)v15 )
            WPP_RECORDER_AND_TRACE_SF_qi(
              WPP_GLOBAL_Control->AttachedDevice,
              v19,
              v15,
              WPP_GLOBAL_Control->DeviceExtension,
              5,
              14,
              50,
              (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids,
              (char)FirstCloneStreamPointer,
              1000 * v18 / v17);
          if ( v18 <= v26 )
            v18 = v26;
          v6 = 10000000 * (v18 - v26) / *((_QWORD *)this + 14);
        }
        if ( this != (CPcmPin *)-80LL )
        {
          v24 = (char *)this + 80;
          v25 = v16;
          wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v24);
        }
        v3 = v26;
      }
      else
      {
        if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
        {
          v20 = 1000 * (v3 - *Context) / Context[1];
          McTemplateK0px_EtwWriteTransfer(v10, 1000 * (v3 - *Context) % Context[1], v11, FirstCloneStreamPointer);
        }
        KsStreamPointerDelete(FirstCloneStreamPointer);
        _InterlockedDecrement((volatile signed __int32 *)this + 12);
      }
    }
    FirstCloneStreamPointer = NextClone;
  }
  while ( NextClone );
  return v6;
}

```

## disassembly

```asm
0x140004720  mov     [rsp+arg_18], rbx
0x140004725  mov     [rsp+arg_10], r8
0x14000472a  push    rsi
0x14000472b  push    rdi
0x14000472c  push    r12
0x14000472e  push    r13
0x140004730  push    r15
0x140004732  sub     rsp, 70h
0x140004736  mov     r15, r8
0x140004739  mov     r13, rdx
0x14000473c  mov     rdi, rcx
0x14000473f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004746  lea     rax, WPP_GLOBAL_Control
0x14000474d  cmp     rcx, rax
0x140004750  jz      short loc_14000475F
0x140004752  test    dword ptr [rcx+2Ch], 2000h
0x140004759  jnz     loc_1400049E3
0x14000475f  xor     dl, dl
0x140004761  lea     r12, WPP_RECORDER_INITIALIZED
0x140004768  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000476f  jnz     loc_1400049B0
0x140004775  xor     r8b, r8b
0x140004778  test    dl, dl
0x14000477a  jnz     loc_1400049F4
0x140004780  test    r8b, r8b
0x140004783  jnz     loc_1400049F4
0x140004789  mov     rcx, [rdi+10h]; Pin
0x14000478d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140004794  call    cs:__imp_KsPinGetFirstCloneStreamPointer
0x14000479b  nop     dword ptr [rax+rax+00h]
0x1400047a0  mov     rbx, rax
0x1400047a3  test    rax, rax
0x1400047a6  jz      loc_14000492F
0x1400047ac  mov     [rsp+98h+arg_0], rbp
0x1400047b4  mov     [rsp+98h+arg_8], r14
0x1400047bc  mov     rbp, [rbx]
0x1400047bf  mov     rcx, rbx; StreamPointer
0x1400047c2  call    cs:__imp_KsStreamPointerGetNextClone
0x1400047c9  nop     dword ptr [rax+rax+00h]
0x1400047ce  mov     r14, rax
0x1400047d1  cmp     rbx, [rdi+28h]
0x1400047d5  jz      short loc_140004849
0x1400047d7  mov     r10, cs:WPP_GLOBAL_Control
0x1400047de  lea     rax, WPP_GLOBAL_Control
0x1400047e5  cmp     r10, rax
0x1400047e8  jnz     loc_140004937
0x1400047ee  xor     dl, dl
0x1400047f0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400047f7  jnz     loc_14000499C
0x1400047fd  xor     r8b, r8b
0x140004800  test    dl, dl
0x140004802  jnz     loc_140004A17
0x140004808  test    r8b, r8b
0x14000480b  jnz     loc_140004A17
0x140004811  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140004815  jnz     short loc_14000483D
0x140004817  cmp     r13, [rbp+10h]
0x14000481b  jl      short loc_140004872
0x14000481d  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140004824  jnz     loc_140004A3E
0x14000482a  mov     rcx, rbx; StreamPointer
0x14000482d  call    cs:__imp_KsStreamPointerDelete
0x140004834  nop     dword ptr [rax+rax+00h]
0x140004839  lock dec dword ptr [rdi+30h]
0x14000483d  mov     rbx, r14
0x140004840  test    r14, r14
0x140004843  jnz     loc_1400047BC
0x140004849  mov     rbp, [rsp+98h+arg_0]
0x140004851  mov     rax, rsi
0x140004854  mov     r14, [rsp+98h+arg_8]
0x14000485c  mov     rbx, [rsp+98h+arg_18]
0x140004864  add     rsp, 70h
0x140004868  pop     r15
0x14000486a  pop     r13
0x14000486c  pop     r12
0x14000486e  pop     rdi
0x14000486f  pop     rsi
0x140004870  retn
0x140004872  lea     r15, [rdi+50h]
0x140004876  mov     rcx, r15; SpinLock
0x140004879  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004880  nop     dword ptr [rax+rax+00h]
0x140004885  mov     r8, [rdi+68h]
0x140004889  movzx   r12d, al
0x14000488d  test    r8, r8
0x140004890  jz      loc_140004916
0x140004896  mov     rax, [rbp+10h]
0x14000489a  sub     rax, [rdi+60h]
0x14000489e  mov     r9, [rdi+70h]
0x1400048a2  movsxd  rcx, dword ptr [rdi+34h]
0x1400048a6  imul    rax, r9
0x1400048aa  cqo
0x1400048ac  idiv    rcx
0x1400048af  lea     rsi, [rax+r8]
0x1400048b3  mov     r10, cs:WPP_GLOBAL_Control
0x1400048ba  lea     rax, WPP_GLOBAL_Control
0x1400048c1  cmp     r10, rax
0x1400048c4  jnz     loc_1400049C3
0x1400048ca  xor     cl, cl
0x1400048cc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400048d3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400048da  jnz     loc_140004988
0x1400048e0  xor     r8b, r8b
0x1400048e3  test    cl, cl
0x1400048e5  jnz     loc_140004A64
0x1400048eb  test    r8b, r8b
0x1400048ee  jnz     loc_140004A64
0x1400048f4  mov     rax, [rsp+98h+arg_10]
0x1400048fc  cmp     rsi, rax
0x1400048ff  cmovle  rsi, rax
0x140004903  sub     rsi, rax
0x140004906  imul    rax, rsi, 989680h
0x14000490d  cqo
0x14000490f  idiv    qword ptr [rdi+70h]
0x140004913  mov     rsi, rax
0x140004916  test    r15, r15
0x140004919  jnz     short loc_140004957
0x14000491b  mov     r15, [rsp+98h+arg_10]
0x140004923  lea     r12, WPP_RECORDER_INITIALIZED
0x14000492a  jmp     loc_14000483D
0x14000492f  mov     rax, rsi
0x140004932  jmp     loc_14000485C
0x140004937  test    dword ptr [r10+2Ch], 2000h
0x14000493f  jz      loc_1400047EE
0x140004945  cmp     byte ptr [r10+29h], 5
0x14000494a  jb      loc_1400047EE
0x140004950  mov     dl, 1
0x140004952  jmp     loc_1400047F0
0x140004957  mov     eax, [rsp+98h+var_2F]
0x14000495b  lea     rcx, [rsp+98h+var_38]; struct wil::details::kspin_lock_saved_irql *
0x140004960  mov     [rsp+98h+var_2F], eax
0x140004964  movzx   eax, [rsp+98h+var_2B]
0x140004969  mov     [rsp+98h+var_2B], ax
0x14000496e  movzx   eax, [rsp+98h+var_29]
0x140004973  mov     [rsp+98h+var_29], al
0x140004977  mov     [rsp+98h+var_38], r15
0x14000497c  mov     [rsp+98h+var_30], r12b
0x140004981  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x140004986  jmp     short loc_14000491B
0x140004988  cmp     word ptr [r10+48h], 0
0x14000498e  jz      loc_1400048E0
0x140004994  mov     r8b, 1
0x140004997  jmp     loc_1400048E3
0x14000499c  cmp     word ptr [r10+48h], 0
0x1400049a2  jz      loc_1400047FD
0x1400049a8  mov     r8b, 1
0x1400049ab  jmp     loc_140004800
0x1400049b0  cmp     word ptr [rcx+48h], 0
0x1400049b5  jz      loc_140004775
0x1400049bb  mov     r8b, 1
0x1400049be  jmp     loc_140004778
0x1400049c3  test    dword ptr [r10+2Ch], 2000h
0x1400049cb  jz      loc_1400048CA
0x1400049d1  cmp     byte ptr [r10+29h], 5
0x1400049d6  jb      loc_1400048CA
0x1400049dc  mov     cl, 1
0x1400049de  jmp     loc_1400048CC
0x1400049e3  cmp     byte ptr [rcx+29h], 5
0x1400049e7  jb      loc_14000475F
0x1400049ed  mov     dl, 1
0x1400049ef  jmp     loc_140004761
0x1400049f4  mov     r9, [rcx+40h]
0x1400049f8  mov     rcx, [rcx+18h]
0x1400049fc  mov     [rsp+98h+var_58], r13
0x140004a01  mov     [rsp+98h+var_68], 30h ; '0'
0x140004a08  mov     byte ptr [rsp+98h+var_78], 5
0x140004a0d  call    WPP_RECORDER_AND_TRACE_SF_i
0x140004a12  jmp     loc_140004789
0x140004a17  mov     eax, [rdi+30h]
0x140004a1a  mov     r9, [r10+40h]
0x140004a1e  mov     rcx, [r10+18h]
0x140004a22  mov     [rsp+98h+var_48], eax
0x140004a26  mov     rax, [rbp+10h]
0x140004a2a  mov     [rsp+98h+var_50], rax
0x140004a2f  mov     [rsp+98h+var_58], rbx
0x140004a34  call    WPP_RECORDER_AND_TRACE_SF_qid
0x140004a39  jmp     loc_140004811
0x140004a3e  mov     rax, r15
0x140004a41  mov     r9, rbx
0x140004a44  sub     rax, [rbp+0]
0x140004a48  imul    rax, 3E8h
0x140004a4f  cqo
0x140004a51  idiv    qword ptr [rbp+8]
0x140004a55  mov     [rsp+98h+var_78], rax
0x140004a5a  call    McTemplateK0px_EtwWriteTransfer
0x140004a5f  jmp     loc_14000482A
0x140004a64  imul    rax, rsi, 3E8h
0x140004a6b  cqo
0x140004a6d  idiv    r9
0x140004a70  mov     r9, [r10+40h]
0x140004a74  movzx   edx, cl
0x140004a77  mov     rcx, [r10+18h]
0x140004a7b  mov     [rsp+98h+var_50], rax
0x140004a80  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140004a87  mov     [rsp+98h+var_58], rbx
0x140004a8c  mov     [rsp+98h+var_60], rax
0x140004a91  mov     [rsp+98h+var_68], 32h ; '2'
0x140004a98  mov     [rsp+98h+var_70], 0Eh
0x140004aa0  mov     byte ptr [rsp+98h+var_78], 5
0x140004aa5  call    WPP_RECORDER_AND_TRACE_SF_qi
0x140004aaa  jmp     loc_1400048F4
```

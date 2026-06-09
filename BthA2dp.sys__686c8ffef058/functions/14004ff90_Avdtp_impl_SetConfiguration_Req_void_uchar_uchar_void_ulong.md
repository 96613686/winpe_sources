# Avdtp_impl::SetConfiguration_Req(void *,uchar,uchar,void *,ulong)

- ea: `0x14004ff90`
- end: `0x140050142`
- name: `?SetConfiguration_Req@Avdtp_impl@@CAJPEAXEE0K@Z`
- size: `434`
- prototype: `__int64 __fastcall(Avdtp_impl *this, __int64, __int64, void *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14002d890`
- `0x14004df64`
- `0x14004ff90`
- `0x140054528`
- `0x1400545e8`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400500b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400500b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005011b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005011b`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::SetConfiguration_Req(
        Avdtp_impl *this,
        __int64 a2,
        __int64 a3,
        void *a4,
        unsigned int Size)
{
  char v6; // bp
  char v7; // r14
  int v9; // edx
  int v10; // r8d
  __int64 Pool2; // rax
  __int64 v12; // rdi
  unsigned int v13; // esi
  void *v14; // rcx
  char v15; // al

  v6 = a3;
  v7 = a2;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seidq(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  else
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seid(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  if ( !this || !a4 || !Size )
    return 3221225485LL;
  Pool2 = ExAllocatePool2(64, Size + 6, 1096172628);
  v12 = Pool2;
  if ( Pool2 )
  {
    v14 = (void *)(Pool2 + 6);
    *(_BYTE *)(Pool2 + 2) = (4 * v6) | *(_BYTE *)(Pool2 + 2) & 3;
    v15 = *(_BYTE *)(Pool2 + 3) & 3;
    *(_WORD *)(v12 + 4) = 1;
    v13 = 0;
    *(_BYTE *)(v12 + 3) = (4 * v7) | v15;
    memmove(v14, a4, Size);
    Avdtp_impl::LabelAndSendCommand(this, (struct _SINGLE_PCK_CMD *)v12, 3, Size + 6);
    ExFreePoolWithTag((PVOID)v12, 0x41564454u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v13;
}

```

## disassembly

```asm
0x14004ff90  push    rbx
0x14004ff92  push    rbp
0x14004ff93  push    rsi
0x14004ff94  push    rdi
0x14004ff95  push    r12
0x14004ff97  push    r13
0x14004ff99  push    r14
0x14004ff9b  push    r15
0x14004ff9d  sub     rsp, 68h
0x14004ffa1  mov     r13, r9
0x14004ffa4  mov     bpl, r8b
0x14004ffa7  mov     r14b, dl
0x14004ffaa  mov     r15, rcx
0x14004ffad  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004ffb2  test    eax, eax
0x14004ffb4  jz      short loc_140050020
0x14004ffb6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ffbd  lea     rax, WPP_GLOBAL_Control
0x14004ffc4  cmp     rcx, rax
0x14004ffc7  jz      short loc_14004FFDA
0x14004ffc9  mov     eax, [rcx+2Ch]
0x14004ffcc  test    al, 8
0x14004ffce  jz      short loc_14004FFDA
0x14004ffd0  cmp     byte ptr [rcx+29h], 4
0x14004ffd4  jb      short loc_14004FFDA
0x14004ffd6  mov     dl, 1
0x14004ffd8  jmp     short loc_14004FFDC
0x14004ffda  xor     dl, dl
0x14004ffdc  lea     rax, WPP_RECORDER_INITIALIZED
0x14004ffe3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004ffea  setnz   r8b
0x14004ffee  test    dl, dl
0x14004fff0  jnz     short loc_14004FFFB
0x14004fff2  test    r8b, r8b
0x14004fff5  jz      loc_14005007F
0x14004fffb  mov     r9, [rcx+40h]
0x14004ffff  mov     rcx, [rcx+18h]
0x140050003  mov     [rsp+0A8h+var_58], r15
0x140050008  mov     [rsp+0A8h+var_60], bpl
0x14005000d  mov     [rsp+0A8h+var_68], r14b
0x140050012  mov     [rsp+0A8h+var_78], 62h ; 'b'
0x140050019  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seidq
0x14005001e  jmp     short loc_14005007F
0x140050020  mov     rcx, cs:WPP_GLOBAL_Control
0x140050027  lea     rax, WPP_GLOBAL_Control
0x14005002e  cmp     rcx, rax
0x140050031  jz      short loc_140050044
0x140050033  mov     eax, [rcx+2Ch]
0x140050036  test    al, 8
0x140050038  jz      short loc_140050044
0x14005003a  cmp     byte ptr [rcx+29h], 4
0x14005003e  jb      short loc_140050044
0x140050040  mov     dl, 1
0x140050042  jmp     short loc_140050046
0x140050044  xor     dl, dl
0x140050046  lea     rax, WPP_RECORDER_INITIALIZED
0x14005004d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140050054  setnz   r8b
0x140050058  test    dl, dl
0x14005005a  jnz     short loc_140050061
0x14005005c  test    r8b, r8b
0x14005005f  jz      short loc_14005007F
0x140050061  mov     r9, [rcx+40h]
0x140050065  mov     rcx, [rcx+18h]
0x140050069  mov     [rsp+0A8h+var_60], bpl
0x14005006e  mov     [rsp+0A8h+var_68], r14b
0x140050073  mov     [rsp+0A8h+var_78], 63h ; 'c'
0x14005007a  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seid
0x14005007f  test    r15, r15
0x140050082  jz      loc_14005012B
0x140050088  test    r13, r13
0x14005008b  jz      loc_14005012B
0x140050091  mov     ebx, dword ptr [rsp+0A8h+Size]
0x140050098  test    ebx, ebx
0x14005009a  jz      loc_14005012B
0x1400500a0  lea     r12d, [rbx+6]
0x1400500a4  mov     ecx, 40h ; '@'
0x1400500a9  mov     edx, r12d
0x1400500ac  mov     r8d, 41564454h
0x1400500b2  call    cs:__imp_ExAllocatePool2
0x1400500b9  nop     dword ptr [rax+rax+00h]
0x1400500be  mov     rdi, rax
0x1400500c1  test    rax, rax
0x1400500c4  jnz     short loc_1400500CD
0x1400500c6  mov     esi, 0C000009Ah
0x1400500cb  jmp     short loc_140050127
0x1400500cd  mov     al, [rax+2]
0x1400500d0  lea     rcx, [rdi+6]; void *
0x1400500d4  and     al, 3
0x1400500d6  shl     bpl, 2
0x1400500da  or      al, bpl
0x1400500dd  shl     r14b, 2
0x1400500e1  mov     [rdi+2], al
0x1400500e4  mov     r8, rbx; Size
0x1400500e7  mov     al, [rdi+3]
0x1400500ea  mov     rdx, r13; Src
0x1400500ed  and     al, 3
0x1400500ef  mov     word ptr [rdi+4], 1
0x1400500f5  or      al, r14b
0x1400500f8  xor     esi, esi
0x1400500fa  mov     [rdi+3], al
0x1400500fd  call    memmove
0x140050102  mov     r9d, r12d; unsigned int
0x140050105  mov     r8b, 3; char
0x140050108  mov     rdx, rdi; struct _SINGLE_PCK_CMD *
0x14005010b  mov     rcx, r15; this
0x14005010e  call    ?LabelAndSendCommand@Avdtp_impl@@AEAAXPEAU_SINGLE_PCK_CMD@@EK@Z; Avdtp_impl::LabelAndSendCommand(_SINGLE_PCK_CMD *,uchar,ulong)
0x140050113  mov     edx, 41564454h; Tag
0x140050118  mov     rcx, rdi; P
0x14005011b  call    cs:__imp_ExFreePoolWithTag
0x140050122  nop     dword ptr [rax+rax+00h]
0x140050127  mov     eax, esi
0x140050129  jmp     short loc_140050130
0x14005012b  mov     eax, 0C000000Dh
0x140050130  add     rsp, 68h
0x140050134  pop     r15
0x140050136  pop     r14
0x140050138  pop     r13
0x14005013a  pop     r12
0x14005013c  pop     rdi
0x14005013d  pop     rsi
0x14005013e  pop     rbp
0x14005013f  pop     rbx
0x140050140  retn
```

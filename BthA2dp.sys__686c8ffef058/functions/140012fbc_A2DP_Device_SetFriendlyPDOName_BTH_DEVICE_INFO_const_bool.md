# A2DP_Device::SetFriendlyPDOName(_BTH_DEVICE_INFO const &,bool)

- ea: `0x140012fbc`
- end: `0x1400131ce`
- name: `?SetFriendlyPDOName@A2DP_Device@@AEAAXAEBU_BTH_DEVICE_INFO@@_N@Z`
- size: `530`
- prototype: `void __fastcall(A2DP_Device *__hidden this, const struct _BTH_DEVICE_INFO *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140030d48`

## callees

- `0x140003530`
- `0x140012fbc`
- `0x14001e0dc`
- `0x140035134`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x140013197`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140013197`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131ad`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x1400130be`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x1400130be`

## string_xrefs

- `0x140013084`: `@System32\drivers\btha2dp.sys`

## pseudocode

```c
void __fastcall A2DP_Device::SetFriendlyPDOName(
        A2DP_Device *this,
        const struct _BTH_DEVICE_INFO *a2,
        unsigned __int8 a3)
{
  const struct _BTH_DEVICE_INFO *v3; // rsi
  char v5; // bl
  int v6; // ebp
  _WORD *v7; // rdx
  int v8; // edx
  int v9; // r8d
  PVOID P; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v11; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a2;
  P = 0;
  v11 = 0;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = a3;
    WPP_RECORDER_AND_TRACE_SF_qdidd(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    v6 = a3;
  }
  if ( (v3->flags & 4) != 0
    && (int)BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 46) + 24LL) + 8LL) + 24LL),
              (unsigned int)(v6 + 1),
              L"@System32\\drivers\\btha2dp.sys",
              v3->name,
              248,
              1346650433,
              &P,
              &v11) >= 0 )
  {
    v7 = (_WORD *)*((_QWORD *)this + 437);
    *((_QWORD *)this + 438) = v7;
    *v7 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             (char *)this + 3496,
                             P) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = v5;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          v9,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          11,
          (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
          (char)this);
      }
    }
    IoSetDevicePropertyData(
      *(PDEVICE_OBJECT *)(*((_QWORD *)this + 46) + 32LL),
      &DEVPKEY_Device_FriendlyName,
      0,
      0,
      0x19u,
      v11 + 2,
      P);
    ExFreePoolWithTag(P, 0x50444141u);
  }
}

```

## disassembly

```asm
0x140012fbc  mov     rax, rsp
0x140012fbf  mov     [rax+8], rbx
0x140012fc3  push    rbp
0x140012fc4  push    rsi
0x140012fc5  push    rdi
0x140012fc6  push    r14
0x140012fc8  push    r15
0x140012fca  sub     rsp, 70h
0x140012fce  movzx   r9d, r8b
0x140012fd2  mov     rsi, rdx
0x140012fd5  mov     rdi, rcx
0x140012fd8  mov     qword ptr [rax+10h], 0
0x140012fe0  mov     qword ptr [rax+20h], 0
0x140012fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fef  lea     r15, WPP_GLOBAL_Control
0x140012ff6  mov     bl, 1
0x140012ff8  cmp     rcx, r15
0x140012ffb  jz      short loc_14001300E
0x140012ffd  mov     eax, [rcx+2Ch]
0x140013000  test    al, 10h
0x140013002  jz      short loc_14001300E
0x140013004  cmp     byte ptr [rcx+29h], 4
0x140013008  jb      short loc_14001300E
0x14001300a  mov     dl, bl
0x14001300c  jmp     short loc_140013010
0x14001300e  xor     dl, dl
0x140013010  lea     r14, WPP_RECORDER_INITIALIZED
0x140013017  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001301e  setnz   r8b
0x140013022  test    dl, dl
0x140013024  jnz     short loc_140013030
0x140013026  test    r8b, r8b
0x140013029  jnz     short loc_140013030
0x14001302b  mov     ebp, r9d
0x14001302e  jmp     short loc_140013067
0x140013030  mov     eax, [rsi+10h]
0x140013033  mov     ebp, r9d
0x140013036  mov     [rsp+98h+var_38], r9d
0x14001303b  mov     r9, [rcx+40h]
0x14001303f  mov     rcx, [rcx+18h]
0x140013043  mov     [rsp+98h+var_40], eax
0x140013047  mov     rax, [rsi+8]
0x14001304b  mov     [rsp+98h+var_48], rax
0x140013050  mov     eax, [rsi]
0x140013052  mov     [rsp+98h+var_50], eax
0x140013056  mov     rax, [rdi+170h]
0x14001305d  mov     [rsp+98h+var_58], rax
0x140013062  call    WPP_RECORDER_AND_TRACE_SF_qdidd
0x140013067  mov     eax, [rsi]
0x140013069  test    al, 4
0x14001306b  jz      loc_1400131B9
0x140013071  mov     rax, [rdi+170h]
0x140013078  lea     r9, [rsi+14h]
0x14001307c  mov     esi, 50444141h
0x140013081  lea     edx, [rbp+1]
0x140013084  lea     r8, aSystem32Driver; "@System32\\drivers\\btha2dp.sys"
0x14001308b  mov     rcx, [rax+18h]
0x14001308f  lea     rax, [rsp+98h+arg_18]
0x140013097  mov     [rsp+98h+var_60], rax
0x14001309c  lea     rax, [rsp+98h+P]
0x1400130a4  mov     [rsp+98h+Data], rax
0x1400130a9  mov     [rsp+98h+Size], esi
0x1400130ad  mov     rcx, [rcx+8]
0x1400130b1  mov     qword ptr [rsp+98h+Type], 0F8h
0x1400130ba  mov     rcx, [rcx+18h]
0x1400130be  call    cs:__imp_BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg
0x1400130c5  nop     dword ptr [rax+rax+00h]
0x1400130ca  test    eax, eax
0x1400130cc  js      loc_1400131B9
0x1400130d2  lea     rcx, [rdi+0DA8h]
0x1400130d9  xor     eax, eax
0x1400130db  mov     rdx, [rcx]
0x1400130de  mov     [rcx+8], rdx
0x1400130e2  mov     [rdx], ax
0x1400130e5  mov     rdx, [rsp+98h+P]
0x1400130ed  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1400130f2  test    al, al
0x1400130f4  jnz     short loc_140013159
0x1400130f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130fd  cmp     rcx, r15
0x140013100  jz      short loc_14001310F
0x140013102  mov     eax, [rcx+2Ch]
0x140013105  test    al, 10h
0x140013107  jz      short loc_14001310F
0x140013109  cmp     byte ptr [rcx+29h], 2
0x14001310d  jnb     short loc_140013111
0x14001310f  xor     bl, bl
0x140013111  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140013118  setnz   r8b
0x14001311c  test    bl, bl
0x14001311e  jnz     short loc_140013125
0x140013120  test    r8b, r8b
0x140013123  jz      short loc_140013159
0x140013125  mov     r9, [rcx+40h]
0x140013129  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140013130  mov     rcx, [rcx+18h]
0x140013134  mov     dl, bl
0x140013136  mov     [rsp+98h+var_58], rdi
0x14001313b  mov     [rsp+98h+var_60], rax
0x140013140  mov     word ptr [rsp+98h+Data], 0Bh
0x140013147  mov     [rsp+98h+Size], 5
0x14001314f  mov     byte ptr [rsp+98h+Type], 2
0x140013154  call    WPP_RECORDER_AND_TRACE_SF_q
0x140013159  mov     r8d, dword ptr [rsp+98h+arg_18]
0x140013161  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x140013168  mov     rcx, [rdi+170h]
0x14001316f  add     r8d, 2
0x140013173  mov     rax, [rsp+98h+P]
0x14001317b  xor     r9d, r9d; Flags
0x14001317e  mov     [rsp+98h+Data], rax; Data
0x140013183  mov     [rsp+98h+Size], r8d; Size
0x140013188  xor     r8d, r8d; Lcid
0x14001318b  mov     rcx, [rcx+20h]; Pdo
0x14001318f  mov     [rsp+98h+Type], 19h; Type
0x140013197  call    cs:__imp_IoSetDevicePropertyData
0x14001319e  nop     dword ptr [rax+rax+00h]
0x1400131a3  mov     rcx, [rsp+98h+P]; P
0x1400131ab  mov     edx, esi; Tag
0x1400131ad  call    cs:__imp_ExFreePoolWithTag
0x1400131b4  nop     dword ptr [rax+rax+00h]
0x1400131b9  mov     rbx, [rsp+98h+arg_0]
0x1400131c1  add     rsp, 70h
0x1400131c5  pop     r15
0x1400131c7  pop     r14
0x1400131c9  pop     rdi
0x1400131ca  pop     rsi
0x1400131cb  pop     rbp
0x1400131cc  retn
```

# HandleAudioDriverScoOpen

- ea: `0x140009750`
- end: `0x1400098a3`
- name: `HandleAudioDriverScoOpen`
- size: `339`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140009750`
- `0x140013cb4`
- `0x14001ae00`
- `0x14002c5b8`

## pseudocode

```c
__int64 __fastcall HandleAudioDriverScoOpen(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int v4; // edx
  __int64 v5; // r8
  unsigned int v7; // eax

  v2 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      75,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  if ( *(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_1400220B0)
                 + 416) )
    return ScoStreamOpenRequest(a1, v2);
  LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      (_BYTE)v5,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      76,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  v7 = ScoSetStreamingModeForHf(a1, 1, v5);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           v2,
           v7);
}

```

## disassembly

```asm
0x140009750  push    rbx
0x140009752  push    rbp
0x140009753  push    rdi
0x140009754  push    r14
0x140009756  push    r15
0x140009758  sub     rsp, 40h
0x14000975c  mov     rdi, rdx
0x14000975f  mov     rbx, rcx
0x140009762  mov     rcx, cs:WPP_GLOBAL_Control
0x140009769  lea     rbp, WPP_GLOBAL_Control
0x140009770  cmp     rcx, rbp
0x140009773  jz      short loc_140009786
0x140009775  mov     eax, [rcx+2Ch]
0x140009778  test    al, 8
0x14000977a  jz      short loc_140009786
0x14000977c  cmp     byte ptr [rcx+29h], 4
0x140009780  jb      short loc_140009786
0x140009782  mov     dl, 1
0x140009784  jmp     short loc_140009788
0x140009786  xor     dl, dl
0x140009788  lea     r14, WPP_RECORDER_INITIALIZED
0x14000978f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140009796  lea     r15, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000979d  setnz   r8b
0x1400097a1  test    dl, dl
0x1400097a3  jnz     short loc_1400097AA
0x1400097a5  test    r8b, r8b
0x1400097a8  jz      short loc_1400097D0
0x1400097aa  mov     r9, [rcx+40h]
0x1400097ae  mov     rcx, [rcx+18h]
0x1400097b2  mov     [rsp+68h+var_30], r15
0x1400097b7  mov     [rsp+68h+var_38], 4Bh ; 'K'
0x1400097be  mov     [rsp+68h+var_40], 4
0x1400097c6  mov     [rsp+68h+var_48], 4
0x1400097cb  call    WPP_RECORDER_AND_TRACE_SF_
0x1400097d0  mov     rax, cs:WdfFunctions_01015
0x1400097d7  mov     rdx, rbx
0x1400097da  mov     r8, cs:off_1400220B0
0x1400097e1  mov     rcx, cs:WdfDriverGlobals
0x1400097e8  mov     rax, [rax+650h]
0x1400097ef  call    _guard_dispatch_icall
0x1400097f4  cmp     dword ptr [rax+1A0h], 0
0x1400097fb  jz      short loc_14000980D
0x1400097fd  mov     rdx, rdi
0x140009800  mov     rcx, rbx
0x140009803  call    ScoStreamOpenRequest
0x140009808  jmp     loc_140009896
0x14000980d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009814  cmp     rcx, rbp
0x140009817  jz      short loc_14000982A
0x140009819  mov     eax, [rcx+2Ch]
0x14000981c  test    al, 8
0x14000981e  jz      short loc_14000982A
0x140009820  cmp     byte ptr [rcx+29h], 4
0x140009824  jb      short loc_14000982A
0x140009826  mov     dl, 1
0x140009828  jmp     short loc_14000982C
0x14000982a  xor     dl, dl
0x14000982c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140009833  setnz   r8b
0x140009837  test    dl, dl
0x140009839  jnz     short loc_140009840
0x14000983b  test    r8b, r8b
0x14000983e  jz      short loc_140009866
0x140009840  mov     r9, [rcx+40h]
0x140009844  mov     rcx, [rcx+18h]
0x140009848  mov     [rsp+68h+var_30], r15
0x14000984d  mov     [rsp+68h+var_38], 4Ch ; 'L'
0x140009854  mov     [rsp+68h+var_40], 4
0x14000985c  mov     [rsp+68h+var_48], 4
0x140009861  call    WPP_RECORDER_AND_TRACE_SF_
0x140009866  mov     edx, 1
0x14000986b  mov     rcx, rbx
0x14000986e  call    ScoSetStreamingModeForHf
0x140009873  mov     rcx, cs:WdfFunctions_01015
0x14000987a  mov     r8d, eax
0x14000987d  mov     rdx, rdi
0x140009880  mov     r9, [rcx+838h]
0x140009887  mov     rcx, cs:WdfDriverGlobals
0x14000988e  mov     rax, r9
0x140009891  call    _guard_dispatch_icall
0x140009896  add     rsp, 40h
0x14000989a  pop     r15
0x14000989c  pop     r14
0x14000989e  pop     rdi
0x14000989f  pop     rbp
0x1400098a0  pop     rbx
0x1400098a1  retn
```

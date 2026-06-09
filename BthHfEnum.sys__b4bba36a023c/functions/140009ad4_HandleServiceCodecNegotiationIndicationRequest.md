# HandleServiceCodecNegotiationIndicationRequest

- ea: `0x140009ad4`
- end: `0x140009d6a`
- name: `HandleServiceCodecNegotiationIndicationRequest`
- size: `662`
- prototype: `__int64 __fastcall(WdfHelpers *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140009ad4`
- `0x14001ae00`
- `0x14002b22c`

## pseudocode

```c
__int64 __fastcall HandleServiceCodecNegotiationIndicationRequest(WdfHelpers *this, __int64 a2)
{
  __int64 v2; // rbp
  char v4; // bl
  __int64 *v5; // r9
  __int64 v6; // rdi
  int v7; // edx
  char v8; // r8

  v2 = a2;
  v4 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(a2) = 0;
  }
  v5 = WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      64,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WdfHelpers *, __int64 *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         this,
         off_1400220B0,
         v5);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v6 + 328),
    0);
  if ( *(_QWORD *)(v6 + 352) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v4;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        4,
        65,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v2,
      3221225488LL);
  }
  else if ( !*(_QWORD *)(v6 + 368) || *(_DWORD *)(v6 + 376) )
  {
    *(_QWORD *)(v6 + 352) = v2;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void (__fastcall *)(struct WDFREQUEST__ *)))(WdfFunctions_01015 + 3144))(
      WdfDriverGlobals,
      v2,
      EvtServiceRequestCancel);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v7) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (v8 = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      v8 = 0;
    }
    if ( (_BYTE)v7 || v8 )
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        4,
        66,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(WdfDriverGlobals, v2, 0);
    *(_DWORD *)(v6 + 376) = 1;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v6 + 328));
  return Bus_OnHfConnectionUpdate(this);
}

```

## disassembly

```asm
0x140009ad4  push    rbx
0x140009ad6  push    rbp
0x140009ad7  push    rsi
0x140009ad8  push    rdi
0x140009ad9  push    r12
0x140009adb  push    r13
0x140009add  push    r14
0x140009adf  push    r15
0x140009ae1  sub     rsp, 48h
0x140009ae5  mov     rbp, rdx
0x140009ae8  mov     r14, rcx
0x140009aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140009af2  lea     r12, WPP_GLOBAL_Control
0x140009af9  xor     r15d, r15d
0x140009afc  lea     ebx, [r15+1]
0x140009b00  cmp     rcx, r12
0x140009b03  jz      short loc_140009B14
0x140009b05  mov     eax, [rcx+2Ch]
0x140009b08  test    bl, al
0x140009b0a  jz      short loc_140009B14
0x140009b0c  cmp     byte ptr [rcx+29h], 4
0x140009b10  mov     dl, bl
0x140009b12  jnb     short loc_140009B17
0x140009b14  mov     dl, r15b
0x140009b17  lea     r13, WPP_RECORDER_INITIALIZED
0x140009b1e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009b25  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140009b2c  setnz   r8b
0x140009b30  test    dl, dl
0x140009b32  jnz     short loc_140009B39
0x140009b34  test    r8b, r8b
0x140009b37  jz      short loc_140009B5B
0x140009b39  mov     [rsp+88h+var_50], r9
0x140009b3e  mov     r9, [rcx+40h]
0x140009b42  mov     rcx, [rcx+18h]
0x140009b46  mov     [rsp+88h+var_58], 40h ; '@'
0x140009b4d  mov     [rsp+88h+var_60], ebx
0x140009b51  mov     [rsp+88h+var_68], 4
0x140009b56  call    WPP_RECORDER_AND_TRACE_SF_
0x140009b5b  mov     rax, cs:WdfFunctions_01015
0x140009b62  mov     rdx, r14
0x140009b65  mov     r8, cs:off_1400220B0
0x140009b6c  mov     rcx, cs:WdfDriverGlobals
0x140009b73  mov     rax, [rax+650h]
0x140009b7a  call    _guard_dispatch_icall
0x140009b7f  mov     rcx, cs:WdfFunctions_01015
0x140009b86  mov     rdi, rax
0x140009b89  xor     r8d, r8d
0x140009b8c  mov     rax, [rcx+9C8h]
0x140009b93  mov     rcx, cs:WdfDriverGlobals
0x140009b9a  mov     rdx, [rdi+148h]
0x140009ba1  call    _guard_dispatch_icall
0x140009ba6  cmp     [rdi+160h], r15
0x140009bad  jz      loc_140009C3D
0x140009bb3  mov     esi, r15d
0x140009bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140009bbd  cmp     rcx, r12
0x140009bc0  jz      short loc_140009BCF
0x140009bc2  mov     eax, [rcx+2Ch]
0x140009bc5  test    al, 8
0x140009bc7  jz      short loc_140009BCF
0x140009bc9  cmp     byte ptr [rcx+29h], 3
0x140009bcd  jnb     short loc_140009BD2
0x140009bcf  mov     bl, r15b
0x140009bd2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009bd9  setnz   r8b
0x140009bdd  test    bl, bl
0x140009bdf  jnz     short loc_140009BE6
0x140009be1  test    r8b, r8b
0x140009be4  jz      short loc_140009C15
0x140009be6  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140009bed  mov     dl, bl
0x140009bef  mov     [rsp+88h+var_50], r9
0x140009bf4  mov     r9, [rcx+40h]
0x140009bf8  mov     rcx, [rcx+18h]
0x140009bfc  mov     [rsp+88h+var_58], 41h ; 'A'
0x140009c03  mov     [rsp+88h+var_60], 4
0x140009c0b  mov     [rsp+88h+var_68], 3
0x140009c10  call    WPP_RECORDER_AND_TRACE_SF_
0x140009c15  mov     rax, cs:WdfFunctions_01015
0x140009c1c  mov     r8d, 0C0000010h
0x140009c22  mov     rcx, cs:WdfDriverGlobals
0x140009c29  mov     rdx, rbp
0x140009c2c  mov     rax, [rax+838h]
0x140009c33  call    _guard_dispatch_icall
0x140009c38  jmp     loc_140009D2D
0x140009c3d  mov     ecx, [rdi+0D0h]
0x140009c43  test    ecx, ecx
0x140009c45  jz      short loc_140009C53
0x140009c47  sub     ecx, ebx
0x140009c49  jz      short loc_140009C4F
0x140009c4b  sub     ecx, ebx
0x140009c4d  jnz     short loc_140009C53
0x140009c4f  mov     esi, ebx
0x140009c51  jmp     short loc_140009C56
0x140009c53  mov     esi, r15d
0x140009c56  cmp     [rdi+170h], r15
0x140009c5d  jz      loc_140009D02
0x140009c63  cmp     [rdi+178h], r15d
0x140009c6a  jnz     loc_140009D02
0x140009c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c77  cmp     rcx, r12
0x140009c7a  jz      short loc_140009C8B
0x140009c7c  mov     eax, [rcx+2Ch]
0x140009c7f  test    al, 8
0x140009c81  jz      short loc_140009C8B
0x140009c83  cmp     byte ptr [rcx+29h], 5
0x140009c87  mov     dl, bl
0x140009c89  jnb     short loc_140009C8E
0x140009c8b  mov     dl, r15b
0x140009c8e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009c95  jz      short loc_140009CA1
0x140009c97  mov     r8b, bl
0x140009c9a  cmp     [rcx+48h], r15w
0x140009c9f  jnz     short loc_140009CA4
0x140009ca1  mov     r8b, r15b
0x140009ca4  test    dl, dl
0x140009ca6  jnz     short loc_140009CAD
0x140009ca8  test    r8b, r8b
0x140009cab  jz      short loc_140009CDA
0x140009cad  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140009cb4  mov     [rsp+88h+var_50], r9
0x140009cb9  mov     r9, [rcx+40h]
0x140009cbd  mov     rcx, [rcx+18h]
0x140009cc1  mov     [rsp+88h+var_58], 42h ; 'B'
0x140009cc8  mov     [rsp+88h+var_60], 4
0x140009cd0  mov     [rsp+88h+var_68], 5
0x140009cd5  call    WPP_RECORDER_AND_TRACE_SF_
0x140009cda  mov     rax, cs:WdfFunctions_01015
0x140009ce1  xor     r8d, r8d
0x140009ce4  mov     rcx, cs:WdfDriverGlobals
0x140009ceb  mov     rdx, rbp
0x140009cee  mov     rax, [rax+838h]
0x140009cf5  call    _guard_dispatch_icall
0x140009cfa  mov     [rdi+178h], ebx
0x140009d00  jmp     short loc_140009D2D
0x140009d02  mov     [rdi+160h], rbp
0x140009d09  lea     r8, ?EvtServiceRequestCancel@@YAXPEAUWDFREQUEST__@@@Z; EvtServiceRequestCancel(WDFREQUEST__ *)
0x140009d10  mov     rax, cs:WdfFunctions_01015
0x140009d17  mov     rdx, rbp
0x140009d1a  mov     rcx, cs:WdfDriverGlobals
0x140009d21  mov     rax, [rax+0C48h]
0x140009d28  call    _guard_dispatch_icall
0x140009d2d  mov     rax, cs:WdfFunctions_01015
0x140009d34  mov     rdx, [rdi+148h]
0x140009d3b  mov     rcx, cs:WdfDriverGlobals
0x140009d42  mov     rax, [rax+9D0h]
0x140009d49  call    _guard_dispatch_icall
0x140009d4e  mov     edx, esi
0x140009d50  mov     rcx, r14; this
0x140009d53  call    Bus_OnHfConnectionUpdate
0x140009d58  add     rsp, 48h
0x140009d5c  pop     r15
0x140009d5e  pop     r14
0x140009d60  pop     r13
0x140009d62  pop     r12
0x140009d64  pop     rdi
0x140009d65  pop     rsi
0x140009d66  pop     rbp
0x140009d67  pop     rbx
0x140009d68  retn
```

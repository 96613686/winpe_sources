# ScoSetCodecId

- ea: `0x140013ae0`
- end: `0x140013cab`
- name: `ScoSetCodecId`
- size: `459`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140006f60`
- `0x140014258`
- `0x14002b22c`

## callees

- `0x140004810`
- `0x140013ae0`
- `0x140014608`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoSetCodecId(__int64 a1, int a2)
{
  __int64 v4; // rdi
  __int64 result; // rax
  int v6; // edx
  int v7; // r8d
  __int64 v8; // rbp
  char v9; // bl
  __int64 v10; // rax

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
             WdfDriverGlobals,
             a1,
             off_1400220B0);
  v8 = result;
  v9 = 1;
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    result = WPP_RECORDER_AND_TRACE_SF_CODECID(
               WPP_GLOBAL_Control->AttachedDevice,
               v6,
               v7,
               WPP_GLOBAL_Control->DeviceExtension);
  }
  *(_DWORD *)(v4 + 104) = a2;
  *(_WORD *)(v4 + 42) = 60;
  *(_WORD *)(v4 + 56) = 2;
  if ( a2 == 1 )
  {
    *(_BYTE *)(v4 + 48) = 4;
    *(_WORD *)(v4 + 54) = 16;
    *(_DWORD *)(v4 + 44) = 16000;
    *(_BYTE *)(v4 + 36) = 2;
  }
  else if ( a2 == 2 )
  {
    v10 = *(_QWORD *)(v8 + 288) - *(_QWORD *)&GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(v8 + 296) - *(_QWORD *)GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data4;
    *(_BYTE *)(v4 + 48) = (v10 != 0) + 4;
    *(_BYTE *)(v4 + 36) = 5;
    *(_WORD *)(v4 + 54) = v10 == 0 ? 16 : 480;
    result = v10 == 0 ? 32000 : 8000;
    *(_DWORD *)(v4 + 44) = result;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (result = HIDWORD(WPP_GLOBAL_Control->Timer), (result & 0x10) == 0)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v9 = 0;
    }
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = v9;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      return WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
               WPP_GLOBAL_Control->AttachedDevice,
               v6,
               v7,
               WPP_GLOBAL_Control->DeviceExtension,
               4,
               5,
               33,
               (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
               a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013ae0  push    rbx
0x140013ae2  push    rbp
0x140013ae3  push    rsi
0x140013ae4  push    rdi
0x140013ae5  push    r12
0x140013ae7  push    r13
0x140013ae9  push    r15
0x140013aeb  sub     rsp, 50h
0x140013aef  mov     rax, cs:WdfFunctions_01015
0x140013af6  mov     esi, edx
0x140013af8  mov     r8, cs:off_140022150
0x140013aff  mov     rbx, rcx
0x140013b02  mov     rdx, rcx
0x140013b05  mov     rcx, cs:WdfDriverGlobals
0x140013b0c  mov     rax, [rax+650h]
0x140013b13  call    _guard_dispatch_icall
0x140013b18  mov     r8, cs:WdfFunctions_01015
0x140013b1f  mov     rdi, rax
0x140013b22  mov     rcx, cs:WdfDriverGlobals
0x140013b29  mov     rdx, rbx
0x140013b2c  mov     rax, [r8+650h]
0x140013b33  mov     r8, cs:off_1400220B0
0x140013b3a  call    _guard_dispatch_icall
0x140013b3f  mov     rbp, rax
0x140013b42  mov     r10, cs:WPP_GLOBAL_Control
0x140013b49  lea     r13, WPP_GLOBAL_Control
0x140013b50  mov     bl, 1
0x140013b52  mov     r15d, 10h
0x140013b58  cmp     r10, r13
0x140013b5b  jz      short loc_140013B71
0x140013b5d  mov     ecx, [r10+2Ch]
0x140013b61  test    r15b, cl
0x140013b64  jz      short loc_140013B71
0x140013b66  cmp     byte ptr [r10+29h], 4
0x140013b6b  jb      short loc_140013B71
0x140013b6d  mov     dl, bl
0x140013b6f  jmp     short loc_140013B73
0x140013b71  xor     dl, dl
0x140013b73  lea     r12, WPP_RECORDER_INITIALIZED
0x140013b7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140013b81  setnz   r8b
0x140013b85  test    dl, dl
0x140013b87  jnz     short loc_140013B8E
0x140013b89  test    r8b, r8b
0x140013b8c  jz      short loc_140013BA6
0x140013b8e  mov     r9, [r10+40h]
0x140013b92  mov     rcx, [r10+18h]
0x140013b96  mov     [rsp+88h+var_48], esi
0x140013b9a  mov     [rsp+88h+var_58], 20h ; ' '
0x140013ba1  call    WPP_RECORDER_AND_TRACE_SF_CODECID
0x140013ba6  mov     ecx, esi
0x140013ba8  mov     [rdi+68h], esi
0x140013bab  mov     word ptr [rdi+2Ah], 3Ch ; '<'
0x140013bb1  mov     word ptr [rdi+38h], 2
0x140013bb7  sub     ecx, 1
0x140013bba  jz      loc_140013C87
0x140013bc0  cmp     ecx, 1
0x140013bc3  jz      short loc_140013C2E
0x140013bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140013bcc  cmp     rcx, r13
0x140013bcf  jz      short loc_140013BDF
0x140013bd1  mov     eax, [rcx+2Ch]
0x140013bd4  test    r15b, al
0x140013bd7  jz      short loc_140013BDF
0x140013bd9  cmp     byte ptr [rcx+29h], 4
0x140013bdd  jnb     short loc_140013BE1
0x140013bdf  xor     bl, bl
0x140013be1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140013be8  setnz   r8b
0x140013bec  test    bl, bl
0x140013bee  jnz     short loc_140013BF9
0x140013bf0  test    r8b, r8b
0x140013bf3  jz      loc_140013C9B
0x140013bf9  mov     r9, [rcx+40h]
0x140013bfd  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140013c04  mov     rcx, [rcx+18h]
0x140013c08  mov     dl, bl
0x140013c0a  mov     [rsp+88h+var_48], esi
0x140013c0e  mov     [rsp+88h+var_50], rax
0x140013c13  mov     [rsp+88h+var_58], 21h ; '!'
0x140013c1a  mov     [rsp+88h+var_60], 5
0x140013c22  mov     [rsp+88h+var_68], 4
0x140013c27  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140013c2c  jmp     short loc_140013C9B
0x140013c2e  mov     rax, [rbp+120h]
0x140013c35  sub     rax, qword ptr cs:GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data1
0x140013c3c  jnz     short loc_140013C4C
0x140013c3e  mov     rax, [rbp+128h]
0x140013c45  sub     rax, qword ptr cs:GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS.Data4
0x140013c4c  test    rax, rax
0x140013c4f  setz    dl
0x140013c52  mov     al, dl
0x140013c54  xor     al, bl
0x140013c56  add     al, 4
0x140013c58  mov     [rdi+30h], al
0x140013c5b  mov     al, dl
0x140013c5d  neg     al
0x140013c5f  mov     byte ptr [rdi+24h], 5
0x140013c63  sbb     cx, cx
0x140013c66  and     cx, 0FE30h
0x140013c6b  add     cx, 1E0h
0x140013c70  neg     dl
0x140013c72  mov     [rdi+36h], cx
0x140013c76  sbb     eax, eax
0x140013c78  and     eax, 5DC0h
0x140013c7d  add     eax, 1F40h
0x140013c82  mov     [rdi+2Ch], eax
0x140013c85  jmp     short loc_140013C9B
0x140013c87  mov     byte ptr [rdi+30h], 4
0x140013c8b  mov     [rdi+36h], r15w
0x140013c90  mov     dword ptr [rdi+2Ch], 3E80h
0x140013c97  mov     byte ptr [rdi+24h], 2
0x140013c9b  add     rsp, 50h
0x140013c9f  pop     r15
0x140013ca1  pop     r13
0x140013ca3  pop     r12
0x140013ca5  pop     rdi
0x140013ca6  pop     rsi
0x140013ca7  pop     rbp
0x140013ca8  pop     rbx
0x140013ca9  retn
```

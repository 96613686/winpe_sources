# CompleteAudioDeviceGetCodecIdRequest

- ea: `0x140005f38`
- end: `0x1400060ff`
- name: `CompleteAudioDeviceGetCodecIdRequest`
- size: `455`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006f60`
- `0x140009004`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x140005f38`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall CompleteAudioDeviceGetCodecIdRequest(__int64 a1, int a2)
{
  int v2; // esi
  int v4; // edx
  int v5; // r8d
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  _BYTE *v9; // [rsp+A0h] [rbp+18h] BYREF

  v2 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      58,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
      v2);
  v9 = 0;
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _BYTE **, _QWORD))(WdfFunctions_01015 + 2160))(
         WdfDriverGlobals,
         a1,
         1,
         &v9,
         0) < 0 )
  {
    LOBYTE(v4) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        v5,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        59,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    }
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a1,
             3221225485LL);
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2216))(WdfDriverGlobals, a1);
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v6,
           off_140022100);
    *v9 = v2;
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
               WdfDriverGlobals,
               a1,
               0,
               1);
    *(_DWORD *)(v7 + 20) = v2;
  }
  return result;
}

```

## disassembly

```asm
0x140005f38  push    rbx
0x140005f3a  push    rbp
0x140005f3b  push    rsi
0x140005f3c  push    rdi
0x140005f3d  push    r14
0x140005f3f  push    r15
0x140005f41  sub     rsp, 58h
0x140005f45  mov     esi, edx
0x140005f47  mov     rdi, rcx
0x140005f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f51  lea     rbx, WPP_GLOBAL_Control
0x140005f58  mov     ebp, 1
0x140005f5d  cmp     rcx, rbx
0x140005f60  jz      short loc_140005F75
0x140005f62  mov     eax, [rcx+2Ch]
0x140005f65  test    bpl, al
0x140005f68  jz      short loc_140005F75
0x140005f6a  cmp     byte ptr [rcx+29h], 4
0x140005f6e  jb      short loc_140005F75
0x140005f70  mov     dl, bpl
0x140005f73  jmp     short loc_140005F77
0x140005f75  xor     dl, dl
0x140005f77  lea     r14, WPP_RECORDER_INITIALIZED
0x140005f7e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140005f85  lea     r15, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x140005f8c  setnz   r8b
0x140005f90  test    dl, dl
0x140005f92  jnz     short loc_140005F99
0x140005f94  test    r8b, r8b
0x140005f97  jz      short loc_140005FBF
0x140005f99  mov     r9, [rcx+40h]
0x140005f9d  mov     rcx, [rcx+18h]
0x140005fa1  mov     [rsp+88h+var_48], esi
0x140005fa5  mov     [rsp+88h+var_50], r15
0x140005faa  mov     [rsp+88h+var_58], 3Ah ; ':'
0x140005fb1  mov     [rsp+88h+var_60], ebp
0x140005fb5  mov     byte ptr [rsp+88h+var_68], 4
0x140005fba  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140005fbf  mov     rax, cs:WdfFunctions_01015
0x140005fc6  lea     r9, [rsp+88h+arg_10]
0x140005fce  mov     rcx, cs:WdfDriverGlobals
0x140005fd5  mov     r8, rbp
0x140005fd8  mov     [rsp+88h+arg_10], 0
0x140005fe4  mov     rdx, rdi
0x140005fe7  mov     [rsp+88h+var_68], 0
0x140005ff0  mov     rax, [rax+870h]
0x140005ff7  call    _guard_dispatch_icall
0x140005ffc  test    eax, eax
0x140005ffe  js      short loc_140006077
0x140006000  mov     rax, cs:WdfFunctions_01015
0x140006007  mov     rdx, rdi
0x14000600a  mov     rcx, cs:WdfDriverGlobals
0x140006011  mov     rax, [rax+8A8h]
0x140006018  call    _guard_dispatch_icall
0x14000601d  mov     rcx, cs:WdfFunctions_01015
0x140006024  mov     rdx, rax
0x140006027  mov     r8, cs:off_140022100
0x14000602e  mov     rax, [rcx+650h]
0x140006035  mov     rcx, cs:WdfDriverGlobals
0x14000603c  call    _guard_dispatch_icall
0x140006041  mov     rcx, [rsp+88h+arg_10]
0x140006049  mov     rbx, rax
0x14000604c  mov     r9, rbp
0x14000604f  xor     r8d, r8d
0x140006052  mov     rdx, rdi
0x140006055  mov     [rcx], sil
0x140006058  mov     rcx, cs:WdfFunctions_01015
0x14000605f  mov     rax, [rcx+848h]
0x140006066  mov     rcx, cs:WdfDriverGlobals
0x14000606d  call    _guard_dispatch_icall
0x140006072  mov     [rbx+14h], esi
0x140006075  jmp     short loc_1400060F1
0x140006077  mov     rcx, cs:WPP_GLOBAL_Control
0x14000607e  cmp     rcx, rbx
0x140006081  jz      short loc_140006096
0x140006083  mov     eax, [rcx+2Ch]
0x140006086  test    bpl, al
0x140006089  jz      short loc_140006096
0x14000608b  cmp     byte ptr [rcx+29h], 2
0x14000608f  jb      short loc_140006096
0x140006091  mov     dl, bpl
0x140006094  jmp     short loc_140006098
0x140006096  xor     dl, dl
0x140006098  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000609f  setnz   r8b
0x1400060a3  test    dl, dl
0x1400060a5  jnz     short loc_1400060AC
0x1400060a7  test    r8b, r8b
0x1400060aa  jz      short loc_1400060CE
0x1400060ac  mov     r9, [rcx+40h]
0x1400060b0  mov     rcx, [rcx+18h]
0x1400060b4  mov     [rsp+88h+var_50], r15
0x1400060b9  mov     [rsp+88h+var_58], 3Bh ; ';'
0x1400060c0  mov     [rsp+88h+var_60], ebp
0x1400060c4  mov     byte ptr [rsp+88h+var_68], 2
0x1400060c9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400060ce  mov     rax, cs:WdfFunctions_01015
0x1400060d5  mov     r8d, 0C000000Dh
0x1400060db  mov     rcx, cs:WdfDriverGlobals
0x1400060e2  mov     rdx, rdi
0x1400060e5  mov     rax, [rax+838h]
0x1400060ec  call    _guard_dispatch_icall
0x1400060f1  add     rsp, 58h
0x1400060f5  pop     r15
0x1400060f7  pop     r14
0x1400060f9  pop     rdi
0x1400060fa  pop     rsi
0x1400060fb  pop     rbp
0x1400060fc  pop     rbx
0x1400060fd  retn
```

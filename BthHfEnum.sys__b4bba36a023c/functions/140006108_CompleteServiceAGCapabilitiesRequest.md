# CompleteServiceAGCapabilitiesRequest

- ea: `0x140006108`
- end: `0x140006293`
- name: `CompleteServiceAGCapabilitiesRequest`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140008be0`
- `0x1400098ac`

## callees

- `0x140004810`
- `0x140006108`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall CompleteServiceAGCapabilitiesRequest(__int64 a1, int a2)
{
  int v2; // esi
  char v4; // bl
  int v5; // edx
  char v7; // [rsp+40h] [rbp-48h]
  _DWORD *v8; // [rsp+A0h] [rbp+18h] BYREF

  v2 = a2;
  v4 = 1;
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
      60,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
      v2);
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **, _QWORD))(WdfFunctions_01015 + 2160))(
         WdfDriverGlobals,
         a1,
         4,
         &v8,
         0);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = v5;
      LOBYTE(v5) = v4;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        61,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids,
        v7);
    }
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a1,
             3221225485LL);
  }
  else
  {
    *v8 = v2;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
             WdfDriverGlobals,
             a1,
             0,
             4);
  }
}

```

## disassembly

```asm
0x140006108  push    rbx
0x14000610a  push    rsi
0x14000610b  push    rdi
0x14000610c  push    r12
0x14000610e  push    r14
0x140006110  push    r15
0x140006112  sub     rsp, 58h
0x140006116  mov     esi, edx
0x140006118  mov     rdi, rcx
0x14000611b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006122  lea     r14, WPP_GLOBAL_Control
0x140006129  mov     ebx, 1
0x14000612e  cmp     rcx, r14
0x140006131  jz      short loc_140006144
0x140006133  mov     eax, [rcx+2Ch]
0x140006136  test    bl, al
0x140006138  jz      short loc_140006144
0x14000613a  cmp     byte ptr [rcx+29h], 4
0x14000613e  jb      short loc_140006144
0x140006140  mov     dl, bl
0x140006142  jmp     short loc_140006146
0x140006144  xor     dl, dl
0x140006146  lea     r15, WPP_RECORDER_INITIALIZED
0x14000614d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006154  lea     r12, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000615b  setnz   r8b
0x14000615f  test    dl, dl
0x140006161  jnz     short loc_140006168
0x140006163  test    r8b, r8b
0x140006166  jz      short loc_14000618E
0x140006168  mov     r9, [rcx+40h]
0x14000616c  mov     rcx, [rcx+18h]
0x140006170  mov     dword ptr [rsp+88h+var_48], esi
0x140006174  mov     [rsp+88h+var_50], r12
0x140006179  mov     [rsp+88h+var_58], 3Ch ; '<'
0x140006180  mov     [rsp+88h+var_60], ebx
0x140006184  mov     byte ptr [rsp+88h+var_68], 4
0x140006189  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000618e  mov     rax, cs:WdfFunctions_01015
0x140006195  lea     r9, [rsp+88h+arg_10]
0x14000619d  mov     rcx, cs:WdfDriverGlobals
0x1400061a4  mov     r8d, 4
0x1400061aa  mov     [rsp+88h+arg_10], 0
0x1400061b6  mov     rdx, rdi
0x1400061b9  mov     [rsp+88h+var_68], 0
0x1400061c2  mov     rax, [rax+870h]
0x1400061c9  call    _guard_dispatch_icall
0x1400061ce  mov     edx, eax
0x1400061d0  test    eax, eax
0x1400061d2  js      short loc_140006206
0x1400061d4  mov     rax, [rsp+88h+arg_10]
0x1400061dc  mov     r9d, 4
0x1400061e2  xor     r8d, r8d
0x1400061e5  mov     rdx, rdi
0x1400061e8  mov     [rax], esi
0x1400061ea  mov     rax, cs:WdfFunctions_01015
0x1400061f1  mov     rcx, cs:WdfDriverGlobals
0x1400061f8  mov     rax, [rax+848h]
0x1400061ff  call    _guard_dispatch_icall
0x140006204  jmp     short loc_140006284
0x140006206  mov     rcx, cs:WPP_GLOBAL_Control
0x14000620d  cmp     rcx, r14
0x140006210  jz      short loc_14000621F
0x140006212  mov     eax, [rcx+2Ch]
0x140006215  test    al, 8
0x140006217  jz      short loc_14000621F
0x140006219  cmp     byte ptr [rcx+29h], 2
0x14000621d  jnb     short loc_140006221
0x14000621f  xor     bl, bl
0x140006221  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006228  setnz   r8b
0x14000622c  test    bl, bl
0x14000622e  jnz     short loc_140006235
0x140006230  test    r8b, r8b
0x140006233  jz      short loc_140006261
0x140006235  mov     r9, [rcx+40h]
0x140006239  mov     rcx, [rcx+18h]
0x14000623d  mov     dword ptr [rsp+88h+var_48], edx
0x140006241  mov     dl, bl
0x140006243  mov     [rsp+88h+var_50], r12
0x140006248  mov     [rsp+88h+var_58], 3Dh ; '='
0x14000624f  mov     [rsp+88h+var_60], 4
0x140006257  mov     byte ptr [rsp+88h+var_68], 2
0x14000625c  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140006261  mov     rax, cs:WdfFunctions_01015
0x140006268  mov     r8d, 0C000000Dh
0x14000626e  mov     rcx, cs:WdfDriverGlobals
0x140006275  mov     rdx, rdi
0x140006278  mov     rax, [rax+838h]
0x14000627f  call    _guard_dispatch_icall
0x140006284  add     rsp, 58h
0x140006288  pop     r15
0x14000628a  pop     r14
0x14000628c  pop     r12
0x14000628e  pop     rdi
0x14000628f  pop     rsi
0x140006290  pop     rbx
0x140006291  retn
```

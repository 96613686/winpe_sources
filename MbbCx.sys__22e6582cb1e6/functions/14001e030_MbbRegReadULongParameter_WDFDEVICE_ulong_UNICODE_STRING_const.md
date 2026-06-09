# MbbRegReadULongParameter(WDFDEVICE__ *,ulong &,_UNICODE_STRING const *)

- ea: `0x14001e030`
- end: `0x14001e145`
- name: `?MbbRegReadULongParameter@@YAJPEAUWDFDEVICE__@@AEAKPEBU_UNICODE_STRING@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, unsigned int *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005df4`

## callees

- `0x140001db8`
- `0x14001e030`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall MbbRegReadULongParameter(struct WDFDEVICE__ *a1, unsigned int *a2, const struct _UNICODE_STRING *a3)
{
  int v5; // edx
  int v6; // ebx
  int v7; // r9d
  __int64 v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01031 + 384))(
         WdfDriverGlobals,
         a1,
         2,
         131097,
         0,
         &v10);
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_8;
    v7 = 114;
    goto LABEL_7;
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01031 + 1920))(
         WdfDriverGlobals,
         v10,
         a3,
         a2);
  if ( v6 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 115;
LABEL_7:
    LODWORD(v9) = v6;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      v7,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      v9);
  }
LABEL_8:
  if ( v10 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001e030  mov     r11, rsp
0x14001e033  mov     [r11+8], rbx
0x14001e037  mov     [r11+10h], rsi
0x14001e03b  push    rdi
0x14001e03c  sub     rsp, 40h
0x14001e040  mov     rax, cs:WdfFunctions_01031
0x14001e047  mov     rsi, rdx
0x14001e04a  lea     rdx, [r11+20h]
0x14001e04e  mov     qword ptr [r11+20h], 0
0x14001e056  mov     [r11-20h], rdx
0x14001e05a  mov     rdi, r8
0x14001e05d  mov     rdx, rcx
0x14001e060  mov     qword ptr [r11-28h], 0
0x14001e068  mov     rax, [rax+180h]
0x14001e06f  mov     r9d, 20019h
0x14001e075  mov     rcx, cs:WdfDriverGlobals
0x14001e07c  mov     r8d, 2
0x14001e082  call    _guard_dispatch_icall
0x14001e087  mov     ebx, eax
0x14001e089  test    eax, eax
0x14001e08b  jns     short loc_14001E0A5
0x14001e08d  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e094  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e09b  jz      short loc_14001E10E
0x14001e09d  mov     r9d, 72h ; 'r'
0x14001e0a3  jmp     short loc_14001E0E6
0x14001e0a5  mov     rax, cs:WdfFunctions_01031
0x14001e0ac  mov     r9, rsi
0x14001e0af  mov     rdx, [rsp+48h+arg_18]
0x14001e0b4  mov     r8, rdi
0x14001e0b7  mov     rcx, cs:WdfDriverGlobals
0x14001e0be  mov     rax, [rax+780h]
0x14001e0c5  call    _guard_dispatch_icall
0x14001e0ca  mov     ebx, eax
0x14001e0cc  test    eax, eax
0x14001e0ce  jns     short loc_14001E10E
0x14001e0d0  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e0d7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e0de  jz      short loc_14001E10E
0x14001e0e0  mov     r9d, 73h ; 's'
0x14001e0e6  lea     rcx, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e0ed  mov     dword ptr [rsp+48h+var_20], ebx
0x14001e0f1  mov     [rsp+48h+var_28], rcx
0x14001e0f6  mov     r8d, 3
0x14001e0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e103  mov     dl, 2
0x14001e105  mov     rcx, [rcx+40h]
0x14001e109  call    WPP_RECORDER_SF_d
0x14001e10e  mov     rdx, [rsp+48h+arg_18]
0x14001e113  test    rdx, rdx
0x14001e116  jz      short loc_14001E132
0x14001e118  mov     rax, cs:WdfFunctions_01031
0x14001e11f  mov     rcx, cs:WdfDriverGlobals
0x14001e126  mov     rax, [rax+680h]
0x14001e12d  call    _guard_dispatch_icall
0x14001e132  mov     rsi, [rsp+48h+arg_8]
0x14001e137  mov     eax, ebx
0x14001e139  mov     rbx, [rsp+48h+arg_0]
0x14001e13e  add     rsp, 40h
0x14001e142  pop     rdi
0x14001e143  retn
```

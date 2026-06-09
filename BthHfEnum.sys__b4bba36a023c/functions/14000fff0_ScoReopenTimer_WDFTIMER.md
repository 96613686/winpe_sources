# ScoReopenTimer(WDFTIMER__ *)

- ea: `0x14000fff0`
- end: `0x1400100c6`
- name: `?ScoReopenTimer@@YAXPEAUWDFTIMER__@@@Z`
- size: `214`
- prototype: `void __fastcall(struct WDFTIMER__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000fff0`
- `0x1400112c4`
- `0x140014c60`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoReopenTimer(struct WDFTIMER__ *a1)
{
  __int64 v1; // rax
  int v2; // edx
  __int64 v3; // rbx
  int v4; // r8d
  int v5; // [rsp+20h] [rbp-38h]

  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFTIMER__ *))(WdfFunctions_01015 + 2568))(
         WdfDriverGlobals,
         a1);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v1,
         off_140022150);
  LOBYTE(v2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v4,
      WPP_GLOBAL_Control->DeviceExtension,
      v5);
  }
  if ( !*(_DWORD *)(v3 + 376) )
  {
    if ( *(_DWORD *)(v3 + 108) )
      SetScoState(v3, 2);
  }
}

```

## disassembly

```asm
0x14000fff0  push    rbx
0x14000fff2  sub     rsp, 50h
0x14000fff6  mov     rax, cs:WdfFunctions_01015
0x14000fffd  mov     rdx, rcx
0x140010000  mov     rcx, cs:WdfDriverGlobals
0x140010007  mov     rax, [rax+0A08h]
0x14001000e  call    _guard_dispatch_icall
0x140010013  mov     rcx, cs:WdfFunctions_01015
0x14001001a  mov     rdx, rax
0x14001001d  mov     r8, cs:off_140022150
0x140010024  mov     rax, [rcx+650h]
0x14001002b  mov     rcx, cs:WdfDriverGlobals
0x140010032  call    _guard_dispatch_icall
0x140010037  mov     rbx, rax
0x14001003a  mov     r10, cs:WPP_GLOBAL_Control
0x140010041  lea     rax, WPP_GLOBAL_Control
0x140010048  cmp     r10, rax
0x14001004b  jz      short loc_140010061
0x14001004d  mov     ecx, [r10+2Ch]
0x140010051  test    cl, 10h
0x140010054  jz      short loc_140010061
0x140010056  cmp     byte ptr [r10+29h], 4
0x14001005b  jb      short loc_140010061
0x14001005d  mov     dl, 1
0x14001005f  jmp     short loc_140010063
0x140010061  xor     dl, dl
0x140010063  lea     rax, WPP_RECORDER_INITIALIZED
0x14001006a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010071  setnz   r8b
0x140010075  test    dl, dl
0x140010077  jnz     short loc_14001007E
0x140010079  test    r8b, r8b
0x14001007c  jz      short loc_1400100A3
0x14001007e  mov     eax, [rbx+6Ch]
0x140010081  mov     r9, [r10+40h]
0x140010085  mov     rcx, [r10+18h]
0x140010089  mov     [rsp+58h+var_10], eax
0x14001008d  mov     eax, [rbx+178h]
0x140010093  mov     [rsp+58h+var_18], eax
0x140010097  mov     [rsp+58h+var_28], 1Ah
0x14001009e  call    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE
0x1400100a3  cmp     dword ptr [rbx+178h], 0
0x1400100aa  jnz     short loc_1400100BF
0x1400100ac  cmp     dword ptr [rbx+6Ch], 0
0x1400100b0  jz      short loc_1400100BF
0x1400100b2  mov     edx, 2
0x1400100b7  mov     rcx, rbx
0x1400100ba  call    SetScoState
0x1400100bf  add     rsp, 50h
0x1400100c3  pop     rbx
0x1400100c4  retn
```

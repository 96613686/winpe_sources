# EvtServiceRequestCancel(WDFREQUEST__ *)

- ea: `0x140006470`
- end: `0x14000664c`
- name: `?EvtServiceRequestCancel@@YAXPEAUWDFREQUEST__@@@Z`
- size: `476`
- prototype: `void __fastcall(struct WDFREQUEST__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1400041d0`
- `0x140006470`
- `0x14001ae00`

## pseudocode

```c
void __fastcall EvtServiceRequestCancel(struct WDFREQUEST__ *a1, __int64 a2, __int64 a3)
{
  char v4; // bl
  bool v5; // dl
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rdi
  int v9; // r8d

  v4 = 1;
  v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      69,
      (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64))(WdfFunctions_01015 + 2216))(
         WdfDriverGlobals,
         a1,
         a3);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1112))(WdfDriverGlobals, v6);
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   v7,
                   off_1400220B0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(WdfDriverGlobals, v8[41], 0);
  if ( a1 == (struct WDFREQUEST__ *)v8[42] )
  {
    v8[42] = 0;
  }
  else if ( a1 == (struct WDFREQUEST__ *)v8[44] )
  {
    v8[44] = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v4 = 0;
    }
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v4,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        4,
        70,
        (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(WdfDriverGlobals, v8[41]);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64))(WdfFunctions_01015 + 2104))(
    WdfDriverGlobals,
    a1,
    3221225760LL);
}

```

## disassembly

```asm
0x140006470  push    rbx
0x140006472  push    rbp
0x140006473  push    rsi
0x140006474  push    rdi
0x140006475  push    r14
0x140006477  push    r15
0x140006479  sub     rsp, 48h
0x14000647d  mov     rsi, rcx
0x140006480  mov     rcx, cs:WPP_GLOBAL_Control
0x140006487  lea     rbp, WPP_GLOBAL_Control
0x14000648e  mov     ebx, 1
0x140006493  cmp     rcx, rbp
0x140006496  jz      short loc_1400064A9
0x140006498  mov     eax, [rcx+2Ch]
0x14000649b  test    bl, al
0x14000649d  jz      short loc_1400064A9
0x14000649f  cmp     byte ptr [rcx+29h], 4
0x1400064a3  jb      short loc_1400064A9
0x1400064a5  mov     dl, bl
0x1400064a7  jmp     short loc_1400064AB
0x1400064a9  xor     dl, dl
0x1400064ab  lea     r14, WPP_RECORDER_INITIALIZED
0x1400064b2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400064b9  lea     r15, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x1400064c0  setnz   r8b
0x1400064c4  test    dl, dl
0x1400064c6  jnz     short loc_1400064CD
0x1400064c8  test    r8b, r8b
0x1400064cb  jz      short loc_1400064EF
0x1400064cd  mov     r9, [rcx+40h]
0x1400064d1  mov     rcx, [rcx+18h]
0x1400064d5  mov     [rsp+78h+var_40], r15
0x1400064da  mov     [rsp+78h+var_48], 45h ; 'E'
0x1400064e1  mov     [rsp+78h+var_50], ebx
0x1400064e5  mov     [rsp+78h+var_58], 4
0x1400064ea  call    WPP_RECORDER_AND_TRACE_SF_
0x1400064ef  mov     rax, cs:WdfFunctions_01015
0x1400064f6  mov     rdx, rsi
0x1400064f9  mov     rcx, cs:WdfDriverGlobals
0x140006500  mov     rax, [rax+8A8h]
0x140006507  call    _guard_dispatch_icall
0x14000650c  mov     rcx, cs:WdfFunctions_01015
0x140006513  mov     rdx, rax
0x140006516  mov     r8, [rcx+458h]
0x14000651d  mov     rcx, cs:WdfDriverGlobals
0x140006524  mov     rax, r8
0x140006527  call    _guard_dispatch_icall
0x14000652c  mov     rcx, cs:WdfFunctions_01015
0x140006533  mov     rdx, rax
0x140006536  mov     r8, cs:off_1400220B0
0x14000653d  mov     rax, [rcx+650h]
0x140006544  mov     rcx, cs:WdfDriverGlobals
0x14000654b  call    _guard_dispatch_icall
0x140006550  mov     rcx, cs:WdfFunctions_01015
0x140006557  mov     rdi, rax
0x14000655a  xor     r8d, r8d
0x14000655d  mov     rax, [rcx+9C8h]
0x140006564  mov     rcx, cs:WdfDriverGlobals
0x14000656b  mov     rdx, [rdi+148h]
0x140006572  call    _guard_dispatch_icall
0x140006577  cmp     rsi, [rdi+150h]
0x14000657e  jnz     short loc_14000658D
0x140006580  mov     qword ptr [rdi+150h], 0
0x14000658b  jmp     short loc_1400065FA
0x14000658d  cmp     rsi, [rdi+160h]
0x140006594  jnz     short loc_1400065A3
0x140006596  mov     qword ptr [rdi+160h], 0
0x1400065a1  jmp     short loc_1400065FA
0x1400065a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065aa  cmp     rcx, rbp
0x1400065ad  jz      short loc_1400065BC
0x1400065af  mov     eax, [rcx+2Ch]
0x1400065b2  test    al, 8
0x1400065b4  jz      short loc_1400065BC
0x1400065b6  cmp     byte ptr [rcx+29h], 3
0x1400065ba  jnb     short loc_1400065BE
0x1400065bc  xor     bl, bl
0x1400065be  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400065c5  setnz   r8b
0x1400065c9  test    bl, bl
0x1400065cb  jnz     short loc_1400065D2
0x1400065cd  test    r8b, r8b
0x1400065d0  jz      short loc_1400065FA
0x1400065d2  mov     r9, [rcx+40h]
0x1400065d6  mov     dl, bl
0x1400065d8  mov     rcx, [rcx+18h]
0x1400065dc  mov     [rsp+78h+var_40], r15
0x1400065e1  mov     [rsp+78h+var_48], 46h ; 'F'
0x1400065e8  mov     [rsp+78h+var_50], 4
0x1400065f0  mov     [rsp+78h+var_58], 3
0x1400065f5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400065fa  mov     rax, cs:WdfFunctions_01015
0x140006601  mov     rdx, [rdi+148h]
0x140006608  mov     rcx, cs:WdfDriverGlobals
0x14000660f  mov     rax, [rax+9D0h]
0x140006616  call    _guard_dispatch_icall
0x14000661b  mov     rax, cs:WdfFunctions_01015
0x140006622  mov     r8d, 0C0000120h
0x140006628  mov     rcx, cs:WdfDriverGlobals
0x14000662f  mov     rdx, rsi
0x140006632  mov     rax, [rax+838h]
0x140006639  call    _guard_dispatch_icall
0x14000663e  add     rsp, 48h
0x140006642  pop     r15
0x140006644  pop     r14
0x140006646  pop     rdi
0x140006647  pop     rsi
0x140006648  pop     rbp
0x140006649  pop     rbx
0x14000664a  retn
```

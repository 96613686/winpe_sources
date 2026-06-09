# WdfIoTargetCreateAndFormatRequestForBrb

- ea: `0x14000affc`
- end: `0x14000b0a4`
- name: `WdfIoTargetCreateAndFormatRequestForBrb`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b270`
- `0x14000d76c`
- `0x140011714`
- `0x140012100`
- `0x1400126dc`
- `0x14002bb34`

## callees

- `0x140006734`
- `0x14000affc`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall WdfIoTargetCreateAndFormatRequestForBrb(
        __int64 a1,
        struct WDFIOTARGET__ *a2,
        struct _BTH_PROFILE_DRIVER_INTERFACE *a3,
        struct _BRB *a4,
        struct WDFREQUEST__ **a5)
{
  int v8; // ebx
  struct WDFREQUEST__ *v9; // rax
  struct WDFREQUEST__ *v10; // rdx
  struct WDFREQUEST__ *v12; // [rsp+30h] [rbp-38h] BYREF

  v12 = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct WDFIOTARGET__ *, struct WDFREQUEST__ **))(WdfFunctions_01015 + 1976))(
         WdfDriverGlobals,
         a1,
         a2,
         &v12);
  if ( v8 < 0 || (v8 = WdfIoTargetFormatRequestForBrb(a2, v12, a3, a4), v8 < 0) )
  {
    v10 = v12;
  }
  else
  {
    v9 = v12;
    v10 = 0;
    v12 = 0;
    *a5 = v9;
  }
  if ( v10 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000affc  push    rbx
0x14000affe  push    rbp
0x14000afff  push    rsi
0x14000b000  push    rdi
0x14000b001  sub     rsp, 48h
0x14000b005  mov     rax, cs:WdfFunctions_01015
0x14000b00c  mov     rbp, r8
0x14000b00f  mov     rdi, rdx
0x14000b012  mov     [rsp+68h+var_38], 0
0x14000b01b  mov     r8, rdx
0x14000b01e  mov     rsi, r9
0x14000b021  mov     rdx, rcx
0x14000b024  lea     r9, [rsp+68h+var_38]
0x14000b029  mov     rax, [rax+7B8h]
0x14000b030  mov     rcx, cs:WdfDriverGlobals
0x14000b037  call    _guard_dispatch_icall
0x14000b03c  mov     ebx, eax
0x14000b03e  test    eax, eax
0x14000b040  js      short loc_14000B074
0x14000b042  mov     rdx, [rsp+68h+var_38]; struct WDFREQUEST__ *
0x14000b047  mov     r9, rsi; struct _BRB *
0x14000b04a  mov     r8, rbp; struct _BTH_PROFILE_DRIVER_INTERFACE *
0x14000b04d  mov     rcx, rdi; struct WDFIOTARGET__ *
0x14000b050  call    ?WdfIoTargetFormatRequestForBrb@@YAJPEAUWDFIOTARGET__@@PEAUWDFREQUEST__@@PEAU_BTH_PROFILE_DRIVER_INTERFACE@@PEAU_BRB@@@Z; WdfIoTargetFormatRequestForBrb(WDFIOTARGET__ *,WDFREQUEST__ *,_BTH_PROFILE_DRIVER_INTERFACE *,_BRB *)
0x14000b055  mov     ebx, eax
0x14000b057  test    eax, eax
0x14000b059  js      short loc_14000B074
0x14000b05b  mov     rax, [rsp+68h+var_38]
0x14000b060  xor     edx, edx
0x14000b062  mov     rcx, [rsp+68h+arg_20]
0x14000b06a  mov     [rsp+68h+var_38], rdx
0x14000b06f  mov     [rcx], rax
0x14000b072  jmp     short loc_14000B079
0x14000b074  mov     rdx, [rsp+68h+var_38]
0x14000b079  test    rdx, rdx
0x14000b07c  jz      short loc_14000B098
0x14000b07e  mov     rax, cs:WdfFunctions_01015
0x14000b085  mov     rcx, cs:WdfDriverGlobals
0x14000b08c  mov     rax, [rax+680h]
0x14000b093  call    _guard_dispatch_icall
0x14000b098  mov     eax, ebx
0x14000b09a  add     rsp, 48h
0x14000b09e  pop     rdi
0x14000b09f  pop     rsi
0x14000b0a0  pop     rbp
0x14000b0a1  pop     rbx
0x14000b0a2  retn
```

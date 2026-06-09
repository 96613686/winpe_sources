# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,void *,_GUID const *)

- ea: `0x18000ad48`
- end: `0x18000adef`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEAXPEBU_GUID@@@Z`
- size: `167`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007000`
- `0x180008b30`
- `0x18002ba28`

## callees

- `0x18000ad48`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000ad9e`
- `ntdll!EtwEventWrite` at `0x18000ad9e`
- `ntdll!EtwEventEnabled` at `0x18000ad70`
- `ntdll!EtwEventEnabled` at `0x18000ad70`

## string_xrefs

- `0x18000add2`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  __int64 v6; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-38h] BYREF

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  v8 = EtwEventWrite(*(_QWORD *)this, a2, 1, &v12);
  v10 = v8;
  if ( !v8 )
    return 0;
  EventManager::LogIt(v9, L"EventWrite error", v8);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ad48  push    rbx
0x18000ad4a  push    rsi
0x18000ad4b  push    rdi
0x18000ad4c  sub     rsp, 40h
0x18000ad50  mov     rax, cs:__security_cookie
0x18000ad57  xor     rax, rsp
0x18000ad5a  mov     [rsp+58h+var_28], rax
0x18000ad5f  mov     rdi, rcx
0x18000ad62  mov     rsi, r8
0x18000ad65  mov     rcx, [rcx]
0x18000ad68  mov     rbx, rdx
0x18000ad6b  test    rcx, rcx
0x18000ad6e  jz      short loc_18000ADC8
0x18000ad70  call    cs:__imp_EtwEventEnabled
0x18000ad77  nop     dword ptr [rax+rax+00h]
0x18000ad7c  test    al, al
0x18000ad7e  jz      short loc_18000ADB0
0x18000ad80  mov     rdx, rsi; unsigned __int16 *
0x18000ad83  lea     rcx, [rsp+58h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18000ad88  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18000ad8d  mov     rcx, [rdi]
0x18000ad90  lea     r9, [rsp+58h+var_38]
0x18000ad95  mov     rdx, rbx
0x18000ad98  mov     r8d, 1
0x18000ad9e  call    cs:__imp_EtwEventWrite
0x18000ada5  nop     dword ptr [rax+rax+00h]
0x18000adaa  mov     ebx, eax
0x18000adac  test    eax, eax
0x18000adae  jnz     short loc_18000ADCF
0x18000adb0  xor     eax, eax
0x18000adb2  mov     rcx, [rsp+58h+var_28]
0x18000adb7  xor     rcx, rsp; StackCookie
0x18000adba  call    __security_check_cookie
0x18000adbf  add     rsp, 40h
0x18000adc3  pop     rdi
0x18000adc4  pop     rsi
0x18000adc5  pop     rbx
0x18000adc6  retn
0x18000adc8  mov     eax, 1
0x18000adcd  jmp     short loc_18000ADB2
0x18000adcf  mov     r8d, ebx; unsigned int
0x18000add2  lea     rdx, aEventwriteErro; "EventWrite error"
0x18000add9  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000adde  test    ebx, ebx
0x18000ade0  jle     short loc_18000ADEB
0x18000ade2  movzx   ebx, bx
0x18000ade5  or      ebx, 80070000h
0x18000adeb  mov     eax, ebx
0x18000aded  jmp     short loc_18000ADB2
```

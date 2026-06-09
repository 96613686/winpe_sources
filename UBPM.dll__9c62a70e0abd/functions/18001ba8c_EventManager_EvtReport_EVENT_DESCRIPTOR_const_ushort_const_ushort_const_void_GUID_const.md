# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,void *,_GUID const *)

- ea: `0x18001ba8c`
- end: `0x18001bb4b`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEAXPEBU_GUID@@@Z`
- size: `191`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001ba64`

## callees

- `0x18001ba8c`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001bafa`
- `ntdll!EtwEventWrite` at `0x18001bafa`
- `ntdll!EtwEventEnabled` at `0x18001babb`
- `ntdll!EtwEventEnabled` at `0x18001babb`

## string_xrefs

- `0x18001bb2e`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-38h] BYREF

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, NO_START_USER_NOT_LOGGED_ON) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  CreateDataDescriptor(&v13, a4);
  v8 = EtwEventWrite(*(_QWORD *)this, NO_START_USER_NOT_LOGGED_ON, 2, &v12);
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
0x18001ba8c  push    rbx
0x18001ba8e  push    rsi
0x18001ba8f  push    rdi
0x18001ba90  sub     rsp, 50h
0x18001ba94  mov     rax, cs:__security_cookie
0x18001ba9b  xor     rax, rsp
0x18001ba9e  mov     [rsp+68h+var_28], rax
0x18001baa3  mov     rbx, rcx
0x18001baa6  mov     rsi, r9
0x18001baa9  mov     rcx, [rcx]
0x18001baac  mov     rdi, r8
0x18001baaf  test    rcx, rcx
0x18001bab2  jz      short loc_18001BB24
0x18001bab4  lea     rdx, NO_START_USER_NOT_LOGGED_ON
0x18001babb  call    cs:__imp_EtwEventEnabled
0x18001bac2  nop     dword ptr [rax+rax+00h]
0x18001bac7  test    al, al
0x18001bac9  jz      short loc_18001BB0C
0x18001bacb  mov     rdx, rdi; unsigned __int16 *
0x18001bace  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bad3  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bad8  mov     rdx, rsi; unsigned __int16 *
0x18001badb  lea     rcx, [rsp+68h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bae0  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001bae5  mov     rcx, [rbx]
0x18001bae8  lea     rdx, NO_START_USER_NOT_LOGGED_ON
0x18001baef  lea     r9, [rsp+68h+var_48]
0x18001baf4  mov     r8d, 2
0x18001bafa  call    cs:__imp_EtwEventWrite
0x18001bb01  nop     dword ptr [rax+rax+00h]
0x18001bb06  mov     ebx, eax
0x18001bb08  test    eax, eax
0x18001bb0a  jnz     short loc_18001BB2B
0x18001bb0c  xor     eax, eax
0x18001bb0e  mov     rcx, [rsp+68h+var_28]
0x18001bb13  xor     rcx, rsp; StackCookie
0x18001bb16  call    __security_check_cookie
0x18001bb1b  add     rsp, 50h
0x18001bb1f  pop     rdi
0x18001bb20  pop     rsi
0x18001bb21  pop     rbx
0x18001bb22  retn
0x18001bb24  mov     eax, 1
0x18001bb29  jmp     short loc_18001BB0E
0x18001bb2b  mov     r8d, ebx; unsigned int
0x18001bb2e  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001bb35  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001bb3a  test    ebx, ebx
0x18001bb3c  jle     short loc_18001BB47
0x18001bb3e  movzx   ebx, bx
0x18001bb41  or      ebx, 80070000h
0x18001bb47  mov     eax, ebx
0x18001bb49  jmp     short loc_18001BB0E
```

# LogError(_EVENT_DESCRIPTOR const *,int)

- ea: `0x1800043d8`
- end: `0x18000442e`
- name: `?LogError@@YAXPEBU_EVENT_DESCRIPTOR@@H@Z`
- size: `86`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032fc`
- `0x180003ac0`

## callees

- `0x1800051c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180004416`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180004416`

## pseudocode

```c
void __fastcall LogError(PCEVENT_DESCRIPTOR EventDescriptor, int a2)
{
  struct _EVENT_DATA_DESCRIPTOR v2; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  *(_QWORD *)&v2.Size = 4;
  v2.Ptr = (ULONGLONG)&v3;
  EventWrite(RegHandle, EventDescriptor, 1u, &v2);
}

```

## disassembly

```asm
0x1800043d8  mov     [rsp+arg_8], edx
0x1800043dc  mov     r11, rsp
0x1800043df  sub     rsp, 48h
0x1800043e3  mov     rax, cs:__security_cookie
0x1800043ea  xor     rax, rsp
0x1800043ed  mov     [rsp+48h+var_18], rax
0x1800043f2  lea     rax, [r11+10h]
0x1800043f6  mov     qword ptr [r11-20h], 4
0x1800043fe  mov     rdx, rcx; EventDescriptor
0x180004401  mov     [r11-28h], rax
0x180004405  mov     rcx, cs:RegHandle; RegHandle
0x18000440c  lea     r9, [r11-28h]; UserData
0x180004410  mov     r8d, 1; UserDataCount
0x180004416  call    cs:__imp_EventWrite
0x18000441c  mov     rcx, [rsp+48h+var_18]
0x180004421  xor     rcx, rsp; StackCookie
0x180004424  call    __security_check_cookie
0x180004429  add     rsp, 48h
0x18000442d  retn
```

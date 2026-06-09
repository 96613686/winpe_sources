# ScoChannelOpenWorkItem(WDFWORKITEM__ *)

- ea: `0x14000e180`
- end: `0x14000e241`
- name: `?ScoChannelOpenWorkItem@@YAXPEAUWDFWORKITEM__@@@Z`
- size: `193`
- prototype: `void __fastcall(struct WDFWORKITEM__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000d76c`
- `0x14000e180`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoChannelOpenWorkItem(struct WDFWORKITEM__ *a1)
{
  __int64 v2; // rbx
  struct WDFDEVICE__ *v3; // rax
  struct WDFREQUEST__ *v4; // r9
  struct WDFDEVICE__ *v5; // rdi
  const struct _SCO_OPEN_CONTEXT *v6; // r8
  int v7; // eax
  __int64 v8; // rcx
  void (__fastcall *v9)(__int64, struct WDFDEVICE__ *); // rax

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFWORKITEM__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400223A0);
  if ( v2 )
  {
    v3 = (struct WDFDEVICE__ *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFWORKITEM__ *))(WdfFunctions_01015 + 3048))(
                                 WdfDriverGlobals,
                                 a1);
    v5 = v3;
    if ( v3 )
    {
      v6 = (const struct _SCO_OPEN_CONTEXT *)(v2 + 24);
      if ( *(_DWORD *)(v2 + 16) != 1 )
        v6 = 0;
      v7 = ScoChannelOpen(v3, *(void **)v2, v6, v4);
      v8 = (unsigned int)v7;
      if ( v7 < 0 )
      {
        v9 = *(void (__fastcall **)(__int64, struct WDFDEVICE__ *))(v2 + 8);
        if ( v9 )
          v9(v8, v5);
      }
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFWORKITEM__ *))(WdfFunctions_01015 + 1664))(
    WdfDriverGlobals,
    a1);
}

```

## disassembly

```asm
0x14000e180  mov     [rsp+arg_0], rbx
0x14000e185  mov     [rsp+arg_8], rsi
0x14000e18a  push    rdi
0x14000e18b  sub     rsp, 20h
0x14000e18f  mov     rax, cs:WdfFunctions_01015
0x14000e196  mov     rsi, rcx
0x14000e199  mov     r8, cs:off_1400223A0
0x14000e1a0  mov     rdx, rcx
0x14000e1a3  mov     rcx, cs:WdfDriverGlobals
0x14000e1aa  mov     rax, [rax+650h]
0x14000e1b1  call    _guard_dispatch_icall
0x14000e1b6  mov     rbx, rax
0x14000e1b9  test    rax, rax
0x14000e1bc  jz      short loc_14000E213
0x14000e1be  mov     rcx, cs:WdfFunctions_01015
0x14000e1c5  mov     rdx, rsi
0x14000e1c8  mov     rax, [rcx+0BE8h]
0x14000e1cf  mov     rcx, cs:WdfDriverGlobals
0x14000e1d6  call    _guard_dispatch_icall
0x14000e1db  mov     rdi, rax
0x14000e1de  test    rax, rax
0x14000e1e1  jz      short loc_14000E213
0x14000e1e3  mov     rdx, [rbx]; void *
0x14000e1e6  lea     r8, [rbx+18h]
0x14000e1ea  xor     ecx, ecx
0x14000e1ec  cmp     dword ptr [rbx+10h], 1
0x14000e1f0  cmovnz  r8, rcx; struct _SCO_OPEN_CONTEXT *
0x14000e1f4  mov     rcx, rax; struct WDFDEVICE__ *
0x14000e1f7  call    ?ScoChannelOpen@@YAJPEAUWDFDEVICE__@@PEAXPEBU_SCO_OPEN_CONTEXT@@P6AXJ0@Z@Z; ScoChannelOpen(WDFDEVICE__ *,void *,_SCO_OPEN_CONTEXT const *,void (*)(long,WDFDEVICE__ *))
0x14000e1fc  mov     ecx, eax
0x14000e1fe  test    eax, eax
0x14000e200  jns     short loc_14000E213
0x14000e202  mov     rax, [rbx+8]
0x14000e206  test    rax, rax
0x14000e209  jz      short loc_14000E213
0x14000e20b  mov     rdx, rdi
0x14000e20e  call    _guard_dispatch_icall
0x14000e213  mov     rax, cs:WdfFunctions_01015
0x14000e21a  mov     rdx, rsi
0x14000e21d  mov     rcx, cs:WdfDriverGlobals
0x14000e224  mov     rax, [rax+680h]
0x14000e22b  call    _guard_dispatch_icall
0x14000e230  mov     rbx, [rsp+28h+arg_0]
0x14000e235  mov     rsi, [rsp+28h+arg_8]
0x14000e23a  add     rsp, 20h
0x14000e23e  pop     rdi
0x14000e23f  retn
```

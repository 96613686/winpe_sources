# TimeUpdate::DoNTPSync(void)

- ea: `0x1800064e4`
- end: `0x180006590`
- name: `?DoNTPSync@TimeUpdate@@AEAA?AW4SyncResult@@XZ`
- size: `172`
- prototype: `__int64 __fastcall(TimeUpdate *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180008798`

## callees

- `0x1800064e4`
- `0x180006ec4`
- `0x180007220`
- `0x180007a5c`
- `0x18000ca60`
- `0x18000d054`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall TimeUpdate::DoNTPSync(TimeUpdate *a1)
{
  unsigned int v2; // edi
  volatile signed __int32 *v3; // rbx
  _BYTE v5[8]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v6; // [rsp+28h] [rbp-10h]

  if ( !TimeUpdate::IsRunning(a1) || !TimeUpdate::HasNetwork(a1) )
    return 2;
  TimeUpdate::GetSettings(a1, v5);
  v2 = LastSyncInfo::Run(v5);
  if ( v2 - 3 <= 2 )
    v2 = NTPSync::Run(v5, (char *)a1 + 60);
  v3 = v6;
  if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x1800064e4  mov     [rsp+arg_0], rbx
0x1800064e9  push    rdi
0x1800064ea  sub     rsp, 30h
0x1800064ee  mov     rbx, rcx
0x1800064f1  call    ?IsRunning@TimeUpdate@@AEBA_NXZ; TimeUpdate::IsRunning(void)
0x1800064f6  test    al, al
0x1800064f8  jz      loc_180006580
0x1800064fe  mov     rcx, rbx; this
0x180006501  call    ?HasNetwork@TimeUpdate@@AEBA_NXZ; TimeUpdate::HasNetwork(void)
0x180006506  test    al, al
0x180006508  jz      short loc_180006580
0x18000650a  lea     rdx, [rsp+38h+var_18]
0x18000650f  mov     rcx, rbx
0x180006512  call    ?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ; TimeUpdate::GetSettings(void)
0x180006517  lea     rcx, [rsp+38h+var_18]
0x18000651c  call    ?Run@LastSyncInfo@@SA?AW4SyncResult@@AEBV?$shared_ptr@VSettings@@@std@@@Z; LastSyncInfo::Run(std::shared_ptr<Settings> const &)
0x180006521  mov     edi, eax
0x180006523  lea     ecx, [rax-3]
0x180006526  cmp     ecx, 2
0x180006529  ja      short loc_18000653B
0x18000652b  lea     rdx, [rbx+3Ch]
0x18000652f  lea     rcx, [rsp+38h+var_18]
0x180006534  call    ?Run@NTPSync@@SA?AW4SyncResult@@AEBV?$shared_ptr@VSettings@@@std@@AEAV?$slim_event_t@$00@wil@@@Z; NTPSync::Run(std::shared_ptr<Settings> const &,wil::slim_event_t<1> &)
0x180006539  mov     edi, eax
0x18000653b  mov     rbx, [rsp+38h+var_10]
0x180006540  test    rbx, rbx
0x180006543  jz      short loc_18000657C
0x180006545  or      eax, 0FFFFFFFFh
0x180006548  lock xadd [rbx+8], eax
0x18000654d  cmp     eax, 1
0x180006550  jnz     short loc_18000657C
0x180006552  mov     rax, [rbx]
0x180006555  mov     rcx, rbx
0x180006558  mov     rax, [rax]
0x18000655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006560  or      eax, 0FFFFFFFFh
0x180006563  lock xadd [rbx+0Ch], eax
0x180006568  cmp     eax, 1
0x18000656b  jnz     short loc_18000657C
0x18000656d  mov     rax, [rbx]
0x180006570  mov     rcx, rbx
0x180006573  mov     rax, [rax+8]
0x180006577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000657c  mov     eax, edi
0x18000657e  jmp     short loc_180006585
0x180006580  mov     eax, 2
0x180006585  mov     rbx, [rsp+38h+arg_0]
0x18000658a  add     rsp, 30h
0x18000658e  pop     rdi
0x18000658f  retn
```

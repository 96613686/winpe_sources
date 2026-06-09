# ServiceManager::RecheckPausedOperationState(void)

- ea: `0x18001b574`
- end: `0x18001b607`
- name: `?RecheckPausedOperationState@ServiceManager@@QEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011450`

## callees

- `0x18001b574`
- `0x18001be24`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001b5f8`

## string_xrefs

- `0x18001b5e4`: `ServiceManager::RecheckPausedOperationState`

## pseudocode

```c
int __fastcall ServiceManager::RecheckPausedOperationState(ServiceManager *this)
{
  int v2; // eax

  if ( *((_DWORD *)this + 881) == 1
    && (v2 = ServiceManager::ShowToast(
               this,
               106,
               104,
               (SAFEARRAY *)L"MapsOpPausedApp",
               L"LastOperationPausedByAppNotification",
               0x861C46800uLL,
               0,
               (unsigned __int16 *)&dword_180027ABC,
               (unsigned __int16 *)&dword_180027ABC,
               0,
               0),
        v2 < 0) )
  {
    return ZTraceReportPropagation(v2, "ServiceManager::RecheckPausedOperationState", 239, this);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001b574  mov     r11, rsp
0x18001b577  push    rbx
0x18001b578  sub     rsp, 60h
0x18001b57c  cmp     dword ptr [rcx+0DC4h], 1
0x18001b583  mov     rbx, rcx
0x18001b586  jnz     short loc_18001B5FF
0x18001b588  mov     [rsp+68h+var_18], 0; unsigned int
0x18001b590  lea     rax, dword_180027ABC
0x18001b597  mov     [rsp+68h+var_20], 0; unsigned int
0x18001b59f  lea     r9, aMapsoppausedap; "MapsOpPausedApp"
0x18001b5a6  mov     [r11-28h], rax
0x18001b5aa  mov     edx, 6Ah ; 'j'; unsigned int
0x18001b5af  mov     [r11-30h], rax
0x18001b5b3  mov     rax, 861C46800h
0x18001b5bd  mov     [rsp+68h+var_38], 0; int
0x18001b5c5  mov     [r11-40h], rax
0x18001b5c9  lea     rax, aLastoperationp_0; "LastOperationPausedByAppNotification"
0x18001b5d0  lea     r8d, [rdx-2]; unsigned int
0x18001b5d4  mov     [r11-48h], rax
0x18001b5d8  call    ?ShowToast@ServiceManager@@AEAAJIIPEBG0_KH00KK@Z; ServiceManager::ShowToast(uint,uint,ushort const *,ushort const *,unsigned __int64,int,ushort const *,ushort const *,ulong,ulong)
0x18001b5dd  test    eax, eax
0x18001b5df  jns     short loc_18001B5FF
0x18001b5e1  mov     r9, rbx
0x18001b5e4  lea     rdx, aServicemanager_58; "ServiceManager::RecheckPausedOperationS"...
0x18001b5eb  mov     r8d, 0EFh
0x18001b5f1  mov     ecx, eax
0x18001b5f3  add     rsp, 60h
0x18001b5f7  pop     rbx
0x18001b5f8  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001b5ff  xor     eax, eax
0x18001b601  add     rsp, 60h
0x18001b605  pop     rbx
0x18001b606  retn
```

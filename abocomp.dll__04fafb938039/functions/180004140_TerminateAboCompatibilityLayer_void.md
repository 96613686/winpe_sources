# TerminateAboCompatibilityLayer(void)

- ea: `0x180004140`
- end: `0x1800041e7`
- name: `?TerminateAboCompatibilityLayer@@YAXXZ`
- size: `167`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001f90`
- `0x180004080`
- `0x1800040cc`
- `0x180004140`
- `0x180019fb4`
- `0x18002c010`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180004168`
- `WS2_32!__imp_WSACleanup` at `0x180004168`
- `nativerd!TerminateNativeConfiguration` at `0x1800041a2`
- `nativerd!TerminateNativeConfiguration` at `0x1800041a2`

## pseudocode

```c
void TerminateAboCompatibilityLayer(void)
{
  if ( g_InitStatus != 1 )
  {
    if ( g_InitStatus != 2 )
    {
      if ( g_InitStatus != 3 )
      {
        if ( g_InitStatus != 4 )
        {
          if ( g_InitStatus != 5 )
          {
            if ( g_InitStatus != 6 )
              return;
            WSACleanup();
          }
          ABO_WRAPPER::RemoveChangeListener(g_pAboWrapper);
          (*(void (__fastcall **)(ABO_WRAPPER *))(*(_QWORD *)g_pAboWrapper + 16LL))(g_pAboWrapper);
          g_pAboWrapper = 0;
        }
        TerminatePropertyTables();
      }
      ABO_NODE::Terminate();
    }
    TerminateNativeConfiguration();
  }
  ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"AboMapper Shutdown");
  if ( g_pAboLog )
    (**(void (__fastcall ***)(ABO_MAPPER_LOG *, __int64))g_pAboLog)(g_pAboLog, 1);
  g_pAboLog = 0;
}

```

## disassembly

```asm
0x180004140  sub     rsp, 28h
0x180004144  mov     ecx, cs:?g_InitStatus@@3W4INIT_COMPAT_STATUS@@A; INIT_COMPAT_STATUS g_InitStatus
0x18000414a  sub     ecx, 1
0x18000414d  jz      short loc_1800041A8
0x18000414f  sub     ecx, 1
0x180004152  jz      short loc_1800041A2
0x180004154  sub     ecx, 1
0x180004157  jz      short loc_18000419D
0x180004159  sub     ecx, 1
0x18000415c  jz      short loc_180004198
0x18000415e  sub     ecx, 1
0x180004161  jz      short loc_18000416E
0x180004163  cmp     ecx, 1
0x180004166  jnz     short loc_1800041E2
0x180004168  call    cs:__imp_WSACleanup
0x18000416e  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; this
0x180004175  call    ?RemoveChangeListener@ABO_WRAPPER@@QEAAJXZ; ABO_WRAPPER::RemoveChangeListener(void)
0x18000417a  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x180004181  mov     rax, [rcx]
0x180004184  mov     rax, [rax+10h]
0x180004188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418d  mov     cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA, 0; ABO_WRAPPER * g_pAboWrapper
0x180004198  call    ?TerminatePropertyTables@@YAXXZ; TerminatePropertyTables(void)
0x18000419d  call    ?Terminate@ABO_NODE@@SAXXZ; ABO_NODE::Terminate(void)
0x1800041a2  call    cs:__imp_?TerminateNativeConfiguration@@YAXXZ; TerminateNativeConfiguration(void)
0x1800041a8  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800041af  lea     rdx, aAbomapperShutd; "AboMapper Shutdown"
0x1800041b6  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800041bb  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; ABO_MAPPER_LOG * g_pAboLog
0x1800041c2  test    rcx, rcx
0x1800041c5  jz      short loc_1800041D7
0x1800041c7  mov     rax, [rcx]
0x1800041ca  mov     edx, 1
0x1800041cf  mov     rax, [rax]
0x1800041d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d7  mov     cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA, 0; ABO_MAPPER_LOG * g_pAboLog
0x1800041e2  add     rsp, 28h
0x1800041e6  retn
```

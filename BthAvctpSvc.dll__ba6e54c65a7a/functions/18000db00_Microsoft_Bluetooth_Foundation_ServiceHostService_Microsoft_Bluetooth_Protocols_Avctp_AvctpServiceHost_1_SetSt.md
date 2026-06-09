# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatusLocked(ulong)

- ea: `0x18000db00`
- end: `0x18000db65`
- name: `?SetStatusLocked@?$ServiceHostService@VAvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009890`
- `0x18000b710`
- `0x18000dab0`

## callees

- `0x18000db00`
- `0x18000dca8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000db3e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000db3e`

## string_xrefs

- `0x18000db48`: `onecore\drivers\bluetooth\foundation\lib\ServiceHost.h`

## pseudocode

```c
int __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost,1>::SetStatusLocked(
        __int64 a1,
        int a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(SERVICE_STATUS_HANDLE *)(a1 + 80);
  if ( *(_DWORD *)(a1 + 92) == a2 )
  {
    ++*(_DWORD *)(a1 + 108);
  }
  else
  {
    *(_DWORD *)(a1 + 92) = a2;
    *(_DWORD *)(a1 + 108) = 0;
  }
  if ( v2 )
  {
    if ( a2 == 1 )
      *(_QWORD *)(a1 + 80) = 0;
    LODWORD(v2) = SetServiceStatus(v2, (LPSERVICE_STATUS)(a1 + 88));
    try
    {
      if ( !(_DWORD)v2 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
          v3);
    }
    catch ( ... )
    {
      LODWORD(v2) = wil::details::in1diag3::Log_CaughtException(
                      retaddr,
                      (void *)0xE8,
                      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ServiceHost.h",
                      v3);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x18000db00  push    rbx
0x18000db02  sub     rsp, 20h
0x18000db06  mov     rax, [rcx+50h]
0x18000db0a  cmp     [rcx+5Ch], edx
0x18000db0d  jnz     short loc_18000DB14
0x18000db0f  inc     dword ptr [rcx+6Ch]
0x18000db12  jmp     short loc_18000DB1E
0x18000db14  mov     [rcx+5Ch], edx
0x18000db17  mov     dword ptr [rcx+6Ch], 0
0x18000db1e  test    rax, rax
0x18000db21  jnz     short loc_18000DB25
0x18000db23  jmp     short loc_18000DB5F
0x18000db25  cmp     edx, 1
0x18000db28  jnz     short loc_18000DB32
0x18000db2a  mov     qword ptr [rcx+50h], 0
0x18000db32  mov     rbx, [rsp+28h]
0x18000db37  lea     rdx, [rcx+58h]; lpServiceStatus
0x18000db3b  mov     rcx, rax; hServiceStatus
0x18000db3e  call    cs:__imp_SetServiceStatus
0x18000db44  test    eax, eax
0x18000db46  jnz     short loc_18000DB5D
0x18000db48  lea     r8, aOnecoreDrivers_35; "onecore\\drivers\\bluetooth\\foundation"...
0x18000db4f  mov     edx, 0E6h; void *
0x18000db54  mov     rcx, rbx; this
0x18000db57  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000db5d  jmp     short $+2
0x18000db5f  add     rsp, 20h
0x18000db63  pop     rbx
0x18000db64  retn
```

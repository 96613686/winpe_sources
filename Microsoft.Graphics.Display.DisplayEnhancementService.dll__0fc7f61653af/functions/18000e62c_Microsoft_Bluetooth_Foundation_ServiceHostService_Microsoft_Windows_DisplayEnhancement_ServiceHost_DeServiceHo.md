# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatusLocked(ulong)

- ea: `0x18000e62c`
- end: `0x18000e691`
- name: `?SetStatusLocked@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@AEAAXK@Z`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b50`
- `0x18000a008`
- `0x18000e5dc`

## callees

- `0x18000e62c`
- `0x18000f9f0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e66a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000e66a`

## string_xrefs

- `0x18000e674`: `onecore\private\drivers\inc\bluetooth\foundation\ServiceHost.h`

## pseudocode

```c
int __fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::SetStatusLocked(
        __int64 a1,
        int a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(SERVICE_STATUS_HANDLE *)(a1 + 72);
  if ( *(_DWORD *)(a1 + 84) == a2 )
  {
    ++*(_DWORD *)(a1 + 100);
  }
  else
  {
    *(_DWORD *)(a1 + 84) = a2;
    *(_DWORD *)(a1 + 100) = 0;
  }
  if ( v2 )
  {
    if ( a2 == 1 )
      *(_QWORD *)(a1 + 72) = 0;
    LODWORD(v2) = SetServiceStatus(v2, (LPSERVICE_STATUS)(a1 + 80));
    try
    {
      if ( !(_DWORD)v2 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
          v3);
    }
    catch ( ... )
    {
      LODWORD(v2) = wil::details::in1diag3::Log_CaughtException(
                      retaddr,
                      (void *)0xE8,
                      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
                      v3);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x18000e62c  push    rbx
0x18000e62e  sub     rsp, 20h
0x18000e632  mov     rax, [rcx+48h]
0x18000e636  cmp     [rcx+54h], edx
0x18000e639  jnz     short loc_18000E640
0x18000e63b  inc     dword ptr [rcx+64h]
0x18000e63e  jmp     short loc_18000E64A
0x18000e640  mov     [rcx+54h], edx
0x18000e643  mov     dword ptr [rcx+64h], 0
0x18000e64a  test    rax, rax
0x18000e64d  jnz     short loc_18000E651
0x18000e64f  jmp     short loc_18000E68B
0x18000e651  cmp     edx, 1
0x18000e654  jnz     short loc_18000E65E
0x18000e656  mov     qword ptr [rcx+48h], 0
0x18000e65e  mov     rbx, [rsp+28h]
0x18000e663  lea     rdx, [rcx+50h]; lpServiceStatus
0x18000e667  mov     rcx, rax; hServiceStatus
0x18000e66a  call    cs:__imp_SetServiceStatus
0x18000e670  test    eax, eax
0x18000e672  jnz     short loc_18000E689
0x18000e674  lea     r8, aOnecorePrivate_3; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18000e67b  mov     edx, 0E6h; void *
0x18000e680  mov     rcx, rbx; this
0x18000e683  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e689  jmp     short $+2
0x18000e68b  add     rsp, 20h
0x18000e68f  pop     rbx
0x18000e690  retn
```

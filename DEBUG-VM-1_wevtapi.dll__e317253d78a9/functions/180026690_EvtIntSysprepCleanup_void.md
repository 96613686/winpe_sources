# EvtIntSysprepCleanup(void)

- ea: `0x180026690`
- end: `0x18002671d`
- name: `?EvtIntSysprepCleanup@@YAKXZ`
- size: `141`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180026690`
- `0x1800267dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002670a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002670a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800266c2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800266c2`

## string_xrefs

- `0x1800266e7`: `Security`

## pseudocode

```c
__int64 EvtIntSysprepCleanup(void)
{
  int v0; // edi
  DWORD v1; // ebx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  while ( 1 )
  {
    dwErrCode = 0;
    SysPrepSingleLog(L"System", &dwErrCode);
    v1 = dwErrCode;
    if ( !dwErrCode )
      break;
    Sleep(0x2710u);
    if ( (unsigned int)++v0 >= 0xC )
      goto LABEL_6;
  }
  SysPrepSingleLog(L"Application", &dwErrCode);
  SysPrepSingleLog(L"Security", &dwErrCode);
  SysPrepSingleLog(L"Setup", &dwErrCode);
  v1 = dwErrCode;
LABEL_6:
  SetLastError(v1);
  return v1;
}

```

## disassembly

```asm
0x180026690  mov     [rsp+arg_8], rbx
0x180026695  push    rdi
0x180026696  sub     rsp, 20h
0x18002669a  xor     edi, edi
0x18002669c  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x1800266a1  mov     [rsp+28h+dwErrCode], 0
0x1800266a9  lea     rcx, ChannelPath; "System"
0x1800266b0  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x1800266b5  mov     ebx, [rsp+28h+dwErrCode]
0x1800266b9  test    ebx, ebx
0x1800266bb  jz      short loc_1800266D1
0x1800266bd  mov     ecx, 2710h; dwMilliseconds
0x1800266c2  call    cs:__imp_Sleep
0x1800266c8  inc     edi
0x1800266ca  cmp     edi, 0Ch
0x1800266cd  jb      short loc_18002669C
0x1800266cf  jmp     short loc_180026708
0x1800266d1  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x1800266d6  lea     rcx, aApplication; "Application"
0x1800266dd  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x1800266e2  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x1800266e7  lea     rcx, aSecurity; "Security"
0x1800266ee  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x1800266f3  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x1800266f8  lea     rcx, aSetup; "Setup"
0x1800266ff  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x180026704  mov     ebx, [rsp+28h+dwErrCode]
0x180026708  mov     ecx, ebx; dwErrCode
0x18002670a  call    cs:__imp_SetLastError
0x180026710  mov     eax, ebx
0x180026712  mov     rbx, [rsp+28h+arg_8]
0x180026717  add     rsp, 20h
0x18002671b  pop     rdi
0x18002671c  retn
```

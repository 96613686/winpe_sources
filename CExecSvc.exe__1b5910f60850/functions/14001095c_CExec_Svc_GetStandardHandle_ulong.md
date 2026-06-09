# CExec::Svc::GetStandardHandle(ulong)

- ea: `0x14001095c`
- end: `0x1400109b1`
- name: `?GetStandardHandle@Svc@CExec@@YAPEAXK@Z`
- size: `85`
- prototype: `HANDLE __fastcall(CExec::Svc *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010cf4`

## callees

- `0x140007a18`
- `0x14000e828`
- `0x14001095c`
- `0x1400126b0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140010960`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140010960`

## string_xrefs

- `0x14001097b`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`
- `0x14001099c`: `onecore\vm\compute\service\cexec\service\cexecsvc.cpp`

## pseudocode

```c
HANDLE __fastcall CExec::Svc::GetStandardHandle(CExec::Svc *this)
{
  HANDLE result; // rax
  __int64 v2; // rdx
  const char *v3; // r9
  unsigned int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = GetStdHandle((DWORD)this);
  if ( result == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
      v3);
  if ( !result )
  {
    v4 = wil::verify_hresult<long>(2147942487LL, v2);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\service\\cexecsvc.cpp",
      (const char *)v4,
      v5);
  }
  return result;
}

```

## disassembly

```asm
0x14001095c  sub     rsp, 28h
0x140010960  call    cs:__imp_GetStdHandle
0x140010966  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001096a  jz      short loc_140010976
0x14001096c  test    rax, rax
0x14001096f  jz      short loc_14001098D
0x140010971  add     rsp, 28h
0x140010975  retn
0x140010976  mov     rcx, [rsp+28h]; this
0x14001097b  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x140010982  mov     edx, 0BDh; void *
0x140010987  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14001098d  mov     ecx, 80070057h
0x140010992  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140010997  mov     rcx, [rsp+28h]; this
0x14001099c  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\service\\cexec\\s"...
0x1400109a3  mov     r9d, eax; char *
0x1400109a6  mov     edx, 0C1h; void *
0x1400109ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

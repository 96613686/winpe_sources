# Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(wil::slim_event_t<1> &,ulong &)

- ea: `0x180011ea4`
- end: `0x180011f26`
- name: `??$WaitOnEventAndUpdateTimeout@V?$slim_event_t@$00@wil@@@Details@Core@Agent@Manager@Container@@YAJAEAV?$slim_event_t@$00@wil@@AEAK@Z`
- size: `130`
- prototype: `int __fastcall(volatile void *Address, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180020308`
- `0x180023090`
- `0x180023578`

## callees

- `0x180007b4c`
- `0x180011ea4`
- `0x180021bc8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011eda`

## string_xrefs

- `0x180011efe`: `onecore\base\gendrv\silos\clem\agent\core\lib\Utils.h`

## pseudocode

```c
int __fastcall Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(
        volatile void *Address,
        unsigned int *a2)
{
  int TickCount64; // esi
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  TickCount64 = GetTickCount64();
  if ( !*a2 || !(unsigned __int8)wil::slim_event_t<1>::wait(Address) )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3F,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\Utils.h",
             (const char *)0x5B4,
             v8);
  v5 = GetTickCount64() - TickCount64;
  v6 = *a2;
  if ( *a2 >= v5 )
    v6 = v5;
  *a2 -= v6;
  return 0;
}

```

## disassembly

```asm
0x180011ea4  mov     [rsp+arg_0], rbx
0x180011ea9  mov     [rsp+arg_8], rsi
0x180011eae  push    rdi; unsigned int
0x180011eaf  sub     rsp, 20h
0x180011eb3  mov     rbx, rdx
0x180011eb6  mov     rdi, rcx
0x180011eb9  call    cs:__imp_GetTickCount64
0x180011ec0  nop     dword ptr [rax+rax+00h]
0x180011ec5  mov     edx, [rbx]
0x180011ec7  mov     rsi, rax
0x180011eca  test    edx, edx
0x180011ecc  jz      short loc_180011EF9
0x180011ece  mov     rcx, rdi; Address
0x180011ed1  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x180011ed6  test    al, al
0x180011ed8  jz      short loc_180011EF9
0x180011eda  call    cs:__imp_GetTickCount64
0x180011ee1  nop     dword ptr [rax+rax+00h]
0x180011ee6  mov     edx, [rbx]
0x180011ee8  sub     eax, esi
0x180011eea  cmp     edx, eax
0x180011eec  mov     ecx, edx
0x180011eee  cmovnb  ecx, eax
0x180011ef1  sub     edx, ecx
0x180011ef3  mov     [rbx], edx
0x180011ef5  xor     eax, eax
0x180011ef7  jmp     short loc_180011F15
0x180011ef9  mov     rcx, [rsp+28h]; this
0x180011efe  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180011f05  mov     r9d, 5B4h; char *
0x180011f0b  mov     edx, 3Fh ; '?'; void *
0x180011f10  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011f15  mov     rbx, [rsp+28h+arg_0]
0x180011f1a  mov     rsi, [rsp+28h+arg_8]
0x180011f1f  add     rsp, 20h
0x180011f23  pop     rdi
0x180011f24  retn
```

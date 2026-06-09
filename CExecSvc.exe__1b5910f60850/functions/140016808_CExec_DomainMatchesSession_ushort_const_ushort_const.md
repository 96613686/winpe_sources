# CExec::DomainMatchesSession(ushort const *,ushort const *)

- ea: `0x140016808`
- end: `0x1400168d7`
- name: `?DomainMatchesSession@CExec@@YA_NPEBG0@Z`
- size: `207`
- prototype: `bool __fastcall(CExec *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017de8`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x14000e828`
- `0x140016808`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016832`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016889`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016832`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016889`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x140016877`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x140016877`

## string_xrefs

- `0x1400168c5`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
bool __fastcall CExec::DomainMatchesSession(CExec *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const char *v6; // r9
  DWORD nSize[4]; // [rsp+20h] [rbp-B8h] BYREF
  WCHAR Buffer[72]; // [rsp+30h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !(unsigned int)_o__wcsicmp(this, a2) )
    return 1;
  if ( *a2 && (*a2 != 46 || a2[1]) )
    return 0;
  memset_0(Buffer, 0, 0x82u);
  nSize[0] = 65;
  if ( !GetComputerNameW(Buffer, nSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B5,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v6);
  return (unsigned int)_o__wcsicmp(this, Buffer) == 0;
}

```

## disassembly

```asm
0x140016808  mov     [rsp+arg_10], rbx
0x14001680d  mov     [rsp+arg_18], rsi
0x140016812  push    rdi
0x140016813  sub     rsp, 0D0h
0x14001681a  mov     rax, cs:__security_cookie
0x140016821  xor     rax, rsp
0x140016824  mov     [rsp+0D8h+var_18], rax
0x14001682c  mov     rbx, rdx
0x14001682f  mov     rdi, rcx
0x140016832  call    cs:__imp__o__wcsicmp
0x140016838  xor     esi, esi
0x14001683a  test    eax, eax
0x14001683c  jz      short loc_140016896
0x14001683e  cmp     [rbx], si
0x140016841  jz      short loc_140016853
0x140016843  cmp     word ptr [rbx], 2Eh ; '.'
0x140016847  jnz     short loc_14001684F
0x140016849  cmp     [rbx+2], si
0x14001684d  jz      short loc_140016853
0x14001684f  xor     al, al
0x140016851  jmp     short loc_140016898
0x140016853  xor     edx, edx; Val
0x140016855  lea     rcx, [rsp+0D8h+Buffer]; void *
0x14001685a  mov     r8d, 82h; Size
0x140016860  call    memset_0
0x140016865  lea     rdx, [rsp+0D8h+nSize]; nSize
0x14001686a  mov     [rsp+0D8h+nSize], 41h ; 'A'
0x140016872  lea     rcx, [rsp+0D8h+Buffer]; lpBuffer
0x140016877  call    cs:__imp_GetComputerNameW
0x14001687d  test    eax, eax
0x14001687f  jz      short loc_1400168BD
0x140016881  lea     rdx, [rsp+0D8h+Buffer]
0x140016886  mov     rcx, rdi
0x140016889  call    cs:__imp__o__wcsicmp
0x14001688f  test    eax, eax
0x140016891  setz    al
0x140016894  jmp     short loc_140016898
0x140016896  mov     al, 1
0x140016898  mov     rcx, [rsp+0D8h+var_18]
0x1400168a0  xor     rcx, rsp; StackCookie
0x1400168a3  call    __security_check_cookie
0x1400168a8  lea     r11, [rsp+0D8h+var_8]
0x1400168b0  mov     rbx, [r11+20h]
0x1400168b4  mov     rsi, [r11+28h]
0x1400168b8  mov     rsp, r11
0x1400168bb  pop     rdi
0x1400168bc  retn
0x1400168bd  mov     rcx, [rsp+0D8h]; this
0x1400168c5  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400168cc  mov     edx, 4B5h; void *
0x1400168d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

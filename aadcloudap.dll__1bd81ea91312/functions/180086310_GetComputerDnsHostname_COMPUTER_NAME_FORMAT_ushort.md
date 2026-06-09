# GetComputerDnsHostname(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x180086310`
- end: `0x18008644b`
- name: `?GetComputerDnsHostname@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `315`
- prototype: `__int64 __fastcall(enum _COMPUTER_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180096da8`

## callees

- `0x180086310`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008ae00`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008637d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008637d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086401`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180086373`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800863f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180086373`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800863f7`

## string_xrefs

- `0x1800863be`: `ComputerNamePhysicalDnsHostname`
- `0x180086409`: `ComputerNamePhysicalDnsHostname`
- `0x1800863d1`: `GetComputerNameExW`
- `0x180086337`: `GetComputerDnsHostname`
- `0x180086351`: `GetComputerDnsHostname`
- `0x1800863a2`: `GetComputerDnsHostname`
- `0x1800863d8`: `GetComputerDnsHostname`

## pseudocode

```c
__int64 __fastcall GetComputerDnsHostname(enum _COMPUTER_NAME_FORMAT a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  unsigned int v4; // edi
  DWORD v5; // eax
  signed int LastError; // ebx
  WCHAR *v7; // rax
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  nSize = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, 0, &nSize)
      || (v5 = GetLastError(), LastError = v5, v5 == 234)
      || (Logger::WriteGetComputerNameFailureEvent(L"ComputerNamePhysicalDnsHostname", v5), !LastError) )
    {
      v7 = (WCHAR *)SafeAlloc(2LL * nSize);
      v2 = v7;
      if ( !v7 )
      {
        v4 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetComputerDnsHostname");
        goto LABEL_15;
      }
      if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, v7, &nSize)
        || (LastError = GetLastError(),
            Logger::WriteGetComputerNameFailureEvent(L"ComputerNamePhysicalDnsHostname", LastError),
            !LastError) )
      {
        v4 = 0;
        *a2 = v2;
        v2 = 0;
        goto LABEL_15;
      }
    }
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"GetComputerDnsHostname",
      L"GetComputerNameExW",
      (unsigned int)LastError);
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = LastError;
  }
  else
  {
    v4 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetComputerDnsHostname", L"pName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetComputerDnsHostname", L"pName");
  }
LABEL_15:
  SafeFree(v2);
  return v4;
}

```

## disassembly

```asm
0x180086310  mov     [rsp+nSize], ecx
0x180086314  push    rbx
0x180086315  push    rsi
0x180086316  push    rdi
0x180086317  push    r14
0x180086319  sub     rsp, 28h
0x18008631d  xor     esi, esi
0x18008631f  mov     r14, rdx
0x180086322  mov     [rsp+48h+nSize], esi
0x180086326  test    rdx, rdx
0x180086329  jnz     short loc_180086362
0x18008632b  lea     r8, aPname; "pName"
0x180086332  mov     edi, 80070057h
0x180086337  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x18008633e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180086345  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008634a  lea     rdx, aPname; "pName"
0x180086351  lea     rcx, aGetcomputerdns; "GetComputerDnsHostname"
0x180086358  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008635d  jmp     loc_180086437
0x180086362  xor     ebx, ebx
0x180086364  lea     r8, [rsp+48h+nSize]; nSize
0x180086369  mov     [rdx], rbx
0x18008636c  xor     edx, edx; lpBuffer
0x18008636e  lea     edi, [rbx+5]
0x180086371  mov     ecx, edi; NameType
0x180086373  call    cs:__imp_GetComputerNameExW
0x180086379  test    eax, eax
0x18008637b  jnz     short loc_18008638E
0x18008637d  call    cs:__imp_GetLastError
0x180086383  mov     ebx, eax
0x180086385  cmp     eax, 0EAh
0x18008638a  jnz     short loc_1800863BC
0x18008638c  xor     ebx, ebx
0x18008638e  mov     ecx, [rsp+48h+nSize]
0x180086392  add     rcx, rcx; unsigned __int64
0x180086395  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18008639a  mov     rsi, rax
0x18008639d  test    rax, rax
0x1800863a0  jnz     short loc_1800863ED
0x1800863a2  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x1800863a9  mov     edi, 8007000Eh
0x1800863ae  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800863b5  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800863ba  jmp     short loc_180086422
0x1800863bc  mov     edx, ebx; unsigned int
0x1800863be  lea     rcx, aComputernameph; "ComputerNamePhysicalDnsHostname"
0x1800863c5  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x1800863ca  test    ebx, ebx
0x1800863cc  jz      short loc_18008638E
0x1800863ce  mov     r9d, ebx
0x1800863d1  lea     r8, aGetcomputernam; "GetComputerNameExW"
0x1800863d8  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x1800863df  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800863e6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800863eb  jmp     short loc_180086426
0x1800863ed  lea     r8, [rsp+48h+nSize]; nSize
0x1800863f2  mov     rdx, rsi; lpBuffer
0x1800863f5  mov     ecx, edi; NameType
0x1800863f7  call    cs:__imp_GetComputerNameExW
0x1800863fd  test    eax, eax
0x1800863ff  jnz     short loc_18008641B
0x180086401  call    cs:__imp_GetLastError
0x180086407  mov     edx, eax; unsigned int
0x180086409  lea     rcx, aComputernameph; "ComputerNamePhysicalDnsHostname"
0x180086410  mov     ebx, eax
0x180086412  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x180086417  test    ebx, ebx
0x180086419  jnz     short loc_1800863CE
0x18008641b  xor     edi, edi
0x18008641d  mov     [r14], rsi
0x180086420  xor     esi, esi
0x180086422  test    ebx, ebx
0x180086424  jz      short loc_180086437
0x180086426  test    ebx, ebx
0x180086428  jg      short loc_18008642E
0x18008642a  mov     edi, ebx
0x18008642c  jmp     short loc_180086437
0x18008642e  movzx   edi, bx
0x180086431  or      edi, 80070000h
0x180086437  mov     rcx, rsi; void *
0x18008643a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008643f  mov     eax, edi
0x180086441  add     rsp, 28h
0x180086445  pop     r14
0x180086447  pop     rdi
0x180086448  pop     rsi
0x180086449  pop     rbx
0x18008644a  retn
```

# ___security_init_cookie

- ea: `0x40d079`
- end: `0x40d111`
- name: `___security_init_cookie`
- size: `152`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x40cb50`

## callees

- `0x40d079`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x40d0c7`
- `KERNEL32!GetTickCount` at `0x40d0c7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40d0a6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40d0a6`
- `KERNEL32!GetCurrentThreadId` at `0x40d0be`
- `KERNEL32!GetCurrentThreadId` at `0x40d0be`
- `KERNEL32!GetCurrentProcessId` at `0x40d0b5`
- `KERNEL32!GetCurrentProcessId` at `0x40d0b5`
- `KERNEL32!QueryPerformanceCounter` at `0x40d0dc`
- `KERNEL32!QueryPerformanceCounter` at `0x40d0dc`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // eax
  uintptr_t v1; // ecx
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v4; // [esp+10h] [ebp-4h] BYREF

  v0 = __security_cookie;
  SystemTimeAsFileTime = 0;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
    v4 ^= GetCurrentProcessId();
    v4 ^= GetCurrentThreadId();
    v4 ^= (unsigned int)&v4 ^ GetTickCount();
    QueryPerformanceCounter(&PerformanceCount);
    v0 = v4 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
    v1 = v0;
    if ( v0 == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
    {
      v0 = -1153374641;
      v1 = -1153374641;
    }
    __security_cookie = v1;
  }
  __security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x40d079  mov     edi, edi
0x40d07b  push    ebp
0x40d07c  mov     ebp, esp
0x40d07e  sub     esp, 14h
0x40d081  mov     eax, ___security_cookie
0x40d086  xorps   xmm0, xmm0
0x40d089  push    esi
0x40d08a  push    edi
0x40d08b  mov     edi, 0BB40E64Eh
0x40d090  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x40d095  mov     esi, 0FFFF0000h
0x40d09a  cmp     eax, edi
0x40d09c  jz      short loc_40D0A2
0x40d09e  test    esi, eax
0x40d0a0  jnz     short loc_40D106
0x40d0a2  lea     eax, [ebp+SystemTimeAsFileTime]
0x40d0a5  push    eax; lpSystemTimeAsFileTime
0x40d0a6  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x40d0ac  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x40d0af  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x40d0b2  mov     [ebp+var_4], eax
0x40d0b5  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x40d0bb  xor     [ebp+var_4], eax
0x40d0be  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40d0c4  xor     [ebp+var_4], eax
0x40d0c7  call    ds:__imp__GetTickCount@0; GetTickCount()
0x40d0cd  xor     eax, [ebp+var_4]
0x40d0d0  lea     ecx, [ebp+var_4]
0x40d0d3  xor     eax, ecx
0x40d0d5  mov     [ebp+var_4], eax
0x40d0d8  lea     eax, [ebp+PerformanceCount]
0x40d0db  push    eax; lpPerformanceCount
0x40d0dc  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x40d0e2  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x40d0e5  xor     eax, dword ptr [ebp+PerformanceCount]
0x40d0e8  xor     eax, [ebp+var_4]
0x40d0eb  mov     ecx, eax
0x40d0ed  cmp     eax, edi
0x40d0ef  jz      short loc_40D0F9
0x40d0f1  test    ___security_cookie, esi
0x40d0f7  jnz     short loc_40D100
0x40d0f9  mov     eax, 0BB40E64Fh
0x40d0fe  mov     ecx, eax
0x40d100  mov     ___security_cookie, ecx
0x40d106  not     eax
0x40d108  pop     edi
0x40d109  mov     ___security_cookie_complement, eax
0x40d10e  pop     esi
0x40d10f  leave
0x40d110  retn
```

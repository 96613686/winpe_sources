# CBdeCfgLibraryLoader::Load(void)

- ea: `0x18000d9b0`
- end: `0x18000da7a`
- name: `?Load@CBdeCfgLibraryLoader@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(CBdeCfgLibraryLoader *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d870`
- `0x18000d9b0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000d9dd`
- `KERNEL32!CreateEventW` at `0x18000da11`
- `KERNEL32!CreateEventW` at `0x18000d9dd`
- `KERNEL32!CreateEventW` at `0x18000da11`
- `KERNEL32!WaitForSingleObject` at `0x18000da3d`
- `KERNEL32!WaitForSingleObject` at `0x18000da3d`
- `KERNEL32!EnterCriticalSection` at `0x18000da5a`
- `KERNEL32!EnterCriticalSection` at `0x1800142be`
- `KERNEL32!EnterCriticalSection` at `0x18000da5a`
- `KERNEL32!EnterCriticalSection` at `0x1800142be`
- `KERNEL32!LeaveCriticalSection` at `0x18000da67`
- `KERNEL32!LeaveCriticalSection` at `0x1800142cb`
- `KERNEL32!LeaveCriticalSection` at `0x18000da67`
- `KERNEL32!LeaveCriticalSection` at `0x1800142cb`
- `KERNEL32!GetLastError` at `0x18000d9f0`
- `KERNEL32!GetLastError` at `0x18000d9f0`

## pseudocode

```c
__int64 __fastcall CBdeCfgLibraryLoader::Load(CBdeCfgLibraryLoader *this)
{
  signed int v2; // ebx
  signed int LastError; // eax

  v2 = 0;
  if ( !*((_BYTE *)this + 60) )
  {
    *((_QWORD *)this + 5) = CreateEventW(0, 0, 0, 0);
    if ( *((_QWORD *)this + 5) && (*((_QWORD *)this + 6) = CreateEventW(0, 0, 0, 0)) != 0 )
    {
      v2 = CBdeCfgLibraryLoader::InitializeAndHoldLibrary(this);
      if ( v2 >= 0 )
      {
        v2 = -1063256042;
        if ( !WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF) )
          v2 = *((_DWORD *)this + 14);
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v2 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_BYTE *)this + 60) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d9b0  mov     [rsp+arg_8], rbx
0x18000d9b5  mov     [rsp+arg_0], rcx
0x18000d9ba  push    rdi
0x18000d9bb  sub     rsp, 30h
0x18000d9bf  mov     rdi, rcx
0x18000d9c2  xor     ebx, ebx
0x18000d9c4  mov     [rsp+38h+var_18], ebx
0x18000d9c8  mov     al, [rcx+3Ch]
0x18000d9cb  test    al, al
0x18000d9cd  jnz     loc_18000DA53
0x18000d9d3  xor     r9d, r9d; lpName
0x18000d9d6  xor     r8d, r8d; bInitialState
0x18000d9d9  xor     edx, edx; bManualReset
0x18000d9db  xor     ecx, ecx; lpEventAttributes
0x18000d9dd  call    cs:__imp_CreateEventW
0x18000d9e3  mov     [rdi+28h], rax
0x18000d9e7  mov     rax, [rdi+28h]
0x18000d9eb  test    rax, rax
0x18000d9ee  jnz     short loc_18000DA07
0x18000d9f0  call    cs:__imp_GetLastError
0x18000d9f6  mov     ebx, eax
0x18000d9f8  test    eax, eax
0x18000d9fa  jle     short loc_18000DA4F
0x18000d9fc  movzx   ebx, ax
0x18000d9ff  or      ebx, 80070000h
0x18000da05  jmp     short loc_18000DA4F
0x18000da07  xor     r9d, r9d; lpName
0x18000da0a  xor     r8d, r8d; bInitialState
0x18000da0d  xor     edx, edx; bManualReset
0x18000da0f  xor     ecx, ecx; lpEventAttributes
0x18000da11  call    cs:__imp_CreateEventW
0x18000da17  mov     [rdi+30h], rax
0x18000da1b  mov     rax, [rdi+30h]
0x18000da1f  test    rax, rax
0x18000da22  jz      short loc_18000D9F0
0x18000da24  mov     rcx, rdi; this
0x18000da27  call    ?InitializeAndHoldLibrary@CBdeCfgLibraryLoader@@AEAAJXZ; CBdeCfgLibraryLoader::InitializeAndHoldLibrary(void)
0x18000da2c  mov     ebx, eax
0x18000da2e  mov     [rsp+38h+var_18], eax
0x18000da32  test    eax, eax
0x18000da34  js      short loc_18000DA53
0x18000da36  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000da39  mov     rcx, [rdi+30h]; hHandle
0x18000da3d  call    cs:__imp_WaitForSingleObject
0x18000da43  test    eax, eax
0x18000da45  mov     ebx, 0C0A00016h
0x18000da4a  jnz     short loc_18000DA4F
0x18000da4c  mov     ebx, [rdi+38h]
0x18000da4f  mov     [rsp+38h+var_18], ebx
0x18000da53  test    ebx, ebx
0x18000da55  js      short loc_18000DA6D
0x18000da57  mov     rcx, rdi; lpCriticalSection
0x18000da5a  call    cs:__imp_EnterCriticalSection
0x18000da60  mov     byte ptr [rdi+3Ch], 1
0x18000da64  mov     rcx, rdi; lpCriticalSection
0x18000da67  call    cs:__imp_LeaveCriticalSection
0x18000da6d  mov     eax, ebx
0x18000da6f  mov     rbx, [rsp+38h+arg_8]
0x18000da74  add     rsp, 30h
0x18000da78  pop     rdi
0x18000da79  retn
0x1800142a7  push    rbx
0x1800142a9  push    rbp
0x1800142aa  sub     rsp, 28h
0x1800142ae  mov     rbp, rdx
0x1800142b1  cmp     dword ptr [rbp+20h], 0
0x1800142b5  jl      short loc_1800142D2
0x1800142b7  mov     rbx, [rbp+40h]
0x1800142bb  mov     rcx, rbx; lpCriticalSection
0x1800142be  call    cs:__imp_EnterCriticalSection
0x1800142c4  mov     byte ptr [rbx+3Ch], 1
0x1800142c8  mov     rcx, rbx; lpCriticalSection
0x1800142cb  call    cs:__imp_LeaveCriticalSection
0x1800142d1  nop
0x1800142d2  add     rsp, 28h
0x1800142d6  pop     rbp
0x1800142d7  pop     rbx
0x1800142d8  retn
```

# SipcPort::Initialize(void)

- ea: `0x180029b8c`
- end: `0x180029c14`
- name: `?Initialize@SipcPort@@IEAAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(SipcPort *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180025520`
- `0x180027214`
- `0x18002774c`
- `0x180027f1c`

## callees

- `0x180029b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ba5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bdf`

## pseudocode

```c
__int64 __fastcall SipcPort::Initialize(SipcPort *this)
{
  HANDLE EventW; // rbx
  HANDLE v3; // rax
  signed int LastError; // eax
  signed int v5; // ecx
  __int64 result; // rax

  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (HANDLE)*((_QWORD *)this + 4);
  if ( EventW == v3 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 4);
  }
  else
  {
    if ( v3 )
      CloseHandle(*((HANDLE *)this + 4));
    *((_QWORD *)this + 4) = EventW;
  }
  if ( EventW )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  result = 2147549183LL;
  if ( v5 < 0 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x180029b8c  mov     [rsp+arg_0], rbx
0x180029b91  push    rdi
0x180029b92  sub     rsp, 20h
0x180029b96  xor     r9d, r9d; lpName
0x180029b99  mov     rdi, rcx
0x180029b9c  xor     r8d, r8d; bInitialState
0x180029b9f  xor     ecx, ecx; lpEventAttributes
0x180029ba1  lea     edx, [r9+1]; bManualReset
0x180029ba5  call    cs:__imp_CreateEventW
0x180029bac  nop     dword ptr [rax+rax+00h]
0x180029bb1  mov     rbx, rax
0x180029bb4  mov     rax, [rdi+20h]
0x180029bb8  cmp     rbx, rax
0x180029bbb  jz      short loc_180029BD7
0x180029bbd  test    rax, rax
0x180029bc0  jz      short loc_180029BD1
0x180029bc2  mov     rcx, rax; hObject
0x180029bc5  call    cs:__imp_CloseHandle
0x180029bcc  nop     dword ptr [rax+rax+00h]
0x180029bd1  mov     [rdi+20h], rbx
0x180029bd5  jmp     short loc_180029BDA
0x180029bd7  mov     rbx, rax
0x180029bda  test    rbx, rbx
0x180029bdd  jnz     short loc_180029C06
0x180029bdf  call    cs:__imp_GetLastError
0x180029be6  nop     dword ptr [rax+rax+00h]
0x180029beb  mov     ecx, eax
0x180029bed  test    eax, eax
0x180029bef  jle     short loc_180029BFA
0x180029bf1  movzx   ecx, ax
0x180029bf4  or      ecx, 80070000h
0x180029bfa  test    ecx, ecx
0x180029bfc  mov     eax, 8000FFFFh
0x180029c01  cmovs   eax, ecx
0x180029c04  jmp     short loc_180029C08
0x180029c06  xor     eax, eax
0x180029c08  mov     rbx, [rsp+28h+arg_0]
0x180029c0d  add     rsp, 20h
0x180029c11  pop     rdi
0x180029c12  retn
```

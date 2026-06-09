# RfbQueryBase::RfbQueryBase(void)

- ea: `0x18000e24c`
- end: `0x18000e316`
- name: `??0RfbQueryBase@@QEAA@XZ`
- size: `202`
- prototype: `RfbQueryBase *__fastcall(RfbQueryBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f4c8`
- `0x180016c40`

## callees

- `0x18000e24c`
- `0x18000e5f4`
- `0x18000e61c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e2a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e2a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2c9`

## pseudocode

```c
RfbQueryBase *__fastcall RfbQueryBase::RfbQueryBase(RfbQueryBase *this)
{
  void **v2; // rdi
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE Event; // r14
  void *v7; // rsi
  DWORD LastError; // ebp
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &RfbQueryBase::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v2 = (void **)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v4, v5);
  GetLastError();
  v7 = *v2;
  if ( *v2 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  *v2 = Event;
  *((_DWORD *)this + 16) = -1;
  return this;
}

```

## disassembly

```asm
0x18000e24c  mov     r11, rsp
0x18000e24f  mov     [r11+18h], rbx
0x18000e253  mov     [r11+20h], rbp
0x18000e257  mov     [r11+8], rcx
0x18000e25b  push    rsi
0x18000e25c  push    rdi
0x18000e25d  push    r14
0x18000e25f  sub     rsp, 20h
0x18000e263  mov     rbx, rcx
0x18000e266  lea     rax, ??_7RfbQueryBase@@6B@; const RfbQueryBase::`vftable'
0x18000e26d  mov     [rcx], rax
0x18000e270  xor     eax, eax
0x18000e272  mov     [rcx+8], rax
0x18000e276  mov     [rcx+10h], eax
0x18000e279  mov     [rcx+18h], rax
0x18000e27d  mov     [rcx+20h], rax
0x18000e281  mov     [rcx+28h], rax
0x18000e285  mov     [rcx+30h], rax
0x18000e289  lea     rdi, [rcx+38h]
0x18000e28d  mov     [r11+10h], rdi
0x18000e291  mov     [rdi], rax
0x18000e294  xor     edx, edx; lpName
0x18000e296  xor     ecx, ecx; lpEventAttributes
0x18000e298  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e29e  lea     r8d, [rax+3]; dwFlags
0x18000e2a2  call    cs:__imp_CreateEventExW
0x18000e2a8  mov     r14, rax
0x18000e2ab  test    rax, rax
0x18000e2ae  jz      short loc_18000E30B
0x18000e2b0  call    cs:__imp_GetLastError
0x18000e2b6  mov     rsi, [rdi]
0x18000e2b9  test    rsi, rsi
0x18000e2bc  jz      short loc_18000E2E0
0x18000e2be  call    cs:__imp_GetLastError
0x18000e2c4  mov     ebp, eax
0x18000e2c6  mov     rcx, rsi; hObject
0x18000e2c9  call    cs:__imp_CloseHandle
0x18000e2cf  mov     rcx, [rsp+38h]; this
0x18000e2d4  test    eax, eax
0x18000e2d6  jz      short loc_18000E300
0x18000e2d8  mov     ecx, ebp; dwErrCode
0x18000e2da  call    cs:__imp_SetLastError
0x18000e2e0  mov     [rdi], r14
0x18000e2e3  mov     dword ptr [rbx+40h], 0FFFFFFFFh
0x18000e2ea  mov     rax, rbx
0x18000e2ed  mov     rbx, [rsp+38h+arg_10]
0x18000e2f2  mov     rbp, [rsp+38h+arg_18]
0x18000e2f7  add     rsp, 20h
0x18000e2fb  pop     r14
0x18000e2fd  pop     rdi
0x18000e2fe  pop     rsi
0x18000e2ff  retn
0x18000e300  mov     edx, 0A0Bh; void *
0x18000e305  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e30b  mov     rcx, [rsp+38h]; this
0x18000e310  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

# CStandardCollectorService::CStandardCollectorService(void)

- ea: `0x140007aec`
- end: `0x140007c28`
- name: `??0CStandardCollectorService@@QEAA@XZ`
- size: `316`
- prototype: `CStandardCollectorService *__fastcall(CStandardCollectorService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001388`

## callees

- `0x140007aec`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140007b20`
- `KERNEL32!CreateEventW` at `0x140007b9e`
- `KERNEL32!CreateEventW` at `0x140007b20`
- `KERNEL32!CreateEventW` at `0x140007b9e`
- `KERNEL32!GetLastError` at `0x140007b33`
- `KERNEL32!GetLastError` at `0x140007b4c`
- `KERNEL32!GetLastError` at `0x140007bb7`
- `KERNEL32!GetLastError` at `0x140007bd3`
- `KERNEL32!GetLastError` at `0x140007b33`
- `KERNEL32!GetLastError` at `0x140007b4c`
- `KERNEL32!GetLastError` at `0x140007bb7`
- `KERNEL32!GetLastError` at `0x140007bd3`

## string_xrefs

- `0x140007afd`: `VisualStudio.StandardCollectorService170.StopEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CStandardCollectorService *__fastcall CStandardCollectorService::CStandardCollectorService(
        CStandardCollectorService *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v4; // ecx
  HANDLE v5; // rax
  signed int v6; // eax
  unsigned int v7; // ecx
  CStandardCollectorService *result; // rax

  *(_QWORD *)this = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_QWORD *)this + 6) = -1;
  *((_DWORD *)this + 14) = 0;
  EventW = CreateEventW(0, 0, 0, L"VisualStudio.StandardCollectorService170.StopEvent");
  *((_QWORD *)this + 6) = EventW;
  if ( EventW )
  {
    if ( GetLastError() == 183 )
      *((_DWORD *)this + 14) = 1;
  }
  else
  {
    *((_QWORD *)this + 6) = -1;
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
    *((_DWORD *)this + 14) = v4;
  }
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = &DiagHubCommon::HubTask<long,0>::`vftable';
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = -1;
  *((_DWORD *)this + 44) = 0;
  v5 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 21) = v5;
  if ( v5 )
  {
    if ( GetLastError() == 183 )
      *((_DWORD *)this + 44) = 1;
  }
  else
  {
    *((_QWORD *)this + 21) = -1;
    v6 = GetLastError();
    v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v7 = v6;
    *((_DWORD *)this + 44) = v7;
  }
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_BYTE *)this + 200) = 0;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  result = this;
  qword_140024AD8 = this;
  return result;
}

```

## disassembly

```asm
0x140007aec  mov     [rsp+arg_0], rbx
0x140007af1  mov     [rsp+arg_8], rbp
0x140007af6  push    rdi
0x140007af7  sub     rsp, 20h
0x140007afb  xor     edi, edi
0x140007afd  lea     r9, aVisualstudioSt_0; "VisualStudio.StandardCollectorService17"...
0x140007b04  mov     [rcx], rdi
0x140007b07  mov     rbx, rcx
0x140007b0a  mov     [rcx+24h], rdi
0x140007b0e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140007b12  mov     [rcx+30h], rbp
0x140007b16  xor     r8d, r8d; bInitialState
0x140007b19  mov     [rcx+38h], edi
0x140007b1c  xor     edx, edx; bManualReset
0x140007b1e  xor     ecx, ecx; lpEventAttributes
0x140007b20  call    cs:__imp_CreateEventW
0x140007b26  mov     [rbx+30h], rax
0x140007b2a  test    rax, rax
0x140007b2d  jnz     short loc_140007B4C
0x140007b2f  mov     [rbx+30h], rbp
0x140007b33  call    cs:__imp_GetLastError
0x140007b39  movzx   ecx, ax
0x140007b3c  or      ecx, 80070000h
0x140007b42  test    eax, eax
0x140007b44  cmovle  ecx, eax
0x140007b47  mov     [rbx+38h], ecx
0x140007b4a  jmp     short loc_140007B60
0x140007b4c  call    cs:__imp_GetLastError
0x140007b52  cmp     eax, 0B7h
0x140007b57  jnz     short loc_140007B60
0x140007b59  mov     dword ptr [rbx+38h], 1
0x140007b60  mov     [rbx+40h], rdi
0x140007b64  lea     rax, ??_7?$HubTask@J$0A@@DiagHubCommon@@6B@; const DiagHubCommon::HubTask<long,0>::`vftable'
0x140007b6b  mov     [rbx+48h], rdi
0x140007b6f  xor     r9d, r9d; lpName
0x140007b72  mov     [rbx+50h], rax
0x140007b76  xor     r8d, r8d; bInitialState
0x140007b79  mov     [rbx+58h], rdi
0x140007b7d  xor     ecx, ecx; lpEventAttributes
0x140007b7f  mov     [rbx+98h], rdi
0x140007b86  mov     [rbx+0A0h], rdi
0x140007b8d  lea     edx, [r9+1]; bManualReset
0x140007b91  mov     [rbx+0A8h], rbp
0x140007b98  mov     [rbx+0B0h], edi
0x140007b9e  call    cs:__imp_CreateEventW
0x140007ba4  mov     [rbx+0A8h], rax
0x140007bab  test    rax, rax
0x140007bae  jnz     short loc_140007BD3
0x140007bb0  mov     [rbx+0A8h], rbp
0x140007bb7  call    cs:__imp_GetLastError
0x140007bbd  movzx   ecx, ax
0x140007bc0  or      ecx, 80070000h
0x140007bc6  test    eax, eax
0x140007bc8  cmovle  ecx, eax
0x140007bcb  mov     [rbx+0B0h], ecx
0x140007bd1  jmp     short loc_140007BEA
0x140007bd3  call    cs:__imp_GetLastError
0x140007bd9  cmp     eax, 0B7h
0x140007bde  jnz     short loc_140007BEA
0x140007be0  mov     dword ptr [rbx+0B0h], 1
0x140007bea  mov     rbp, [rsp+28h+arg_8]
0x140007bef  xor     eax, eax
0x140007bf1  mov     [rbx+0B8h], edi
0x140007bf7  xorps   xmm0, xmm0
0x140007bfa  mov     [rbx+0C0h], rdi
0x140007c01  mov     [rbx+0C8h], dil
0x140007c08  movups  xmmword ptr [rbx+8], xmm0
0x140007c0c  mov     [rbx+18h], rax
0x140007c10  mov     [rbx+20h], eax
0x140007c13  mov     rax, rbx
0x140007c16  mov     cs:qword_140024AD8, rbx
0x140007c1d  mov     rbx, [rsp+28h+arg_0]
0x140007c22  add     rsp, 20h
0x140007c26  pop     rdi
0x140007c27  retn
```

# WTL::CAppModule::AddMessageLoop(WTL::CMessageLoop *)

- ea: `0x180005d88`
- end: `0x180005e3b`
- name: `?AddMessageLoop@CAppModule@WTL@@QEAAHPEAVCMessageLoop@2@@Z`
- size: `179`
- prototype: `__int64 __fastcall(WTL::CAppModule *__hidden this, struct WTL::CMessageLoop *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e70`
- `0x180016710`

## callees

- `0x180005d88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180005dcb`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180005def`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180005dcb`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180005def`
- `KERNEL32!EnterCriticalSection` at `0x180005da1`
- `KERNEL32!EnterCriticalSection` at `0x180005da1`
- `KERNEL32!LeaveCriticalSection` at `0x180005e28`
- `KERNEL32!LeaveCriticalSection` at `0x180005e28`
- `KERNEL32!GetCurrentThreadId` at `0x180005dae`
- `KERNEL32!GetCurrentThreadId` at `0x180005dae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WTL::CAppModule::AddMessageLoop(WTL::CAppModule *this, struct WTL::CMessageLoop *a2)
{
  struct ATL::CAtlModule *v2; // rsi
  int *v4; // rbx
  unsigned int v5; // edi
  DWORD CurrentThreadId; // r14d
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  DWORD *v11; // rcx
  _QWORD *v12; // rax

  v2 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v4 = (int *)qword_180050788;
  v5 = 1;
  CurrentThreadId = GetCurrentThreadId();
  v7 = _o__recalloc(*(_QWORD *)v4, v4[4] + 1, 4);
  if ( v7 && (v8 = *((_QWORD *)v4 + 1), *(_QWORD *)v4 = v7, (v9 = _o__recalloc(v8, v4[4] + 1, 8)) != 0) )
  {
    v10 = v4[4];
    *((_QWORD *)v4 + 1) = v9;
    v11 = (DWORD *)(*(_QWORD *)v4 + 4 * v10);
    if ( v11 )
      *v11 = CurrentThreadId;
    v12 = (_QWORD *)(*((_QWORD *)v4 + 1) + 8 * v10);
    if ( v12 )
      *v12 = a2;
    ++v4[4];
  }
  else
  {
    v5 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 24));
  return v5;
}

```

## disassembly

```asm
0x180005d88  push    rbx
0x180005d8a  push    rbp
0x180005d8b  push    rsi
0x180005d8c  push    rdi
0x180005d8d  push    r14
0x180005d8f  sub     rsp, 20h
0x180005d93  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d9a  mov     rbp, rdx
0x180005d9d  lea     rcx, [rsi+18h]; lpCriticalSection
0x180005da1  call    cs:__imp_EnterCriticalSection
0x180005da7  mov     rbx, cs:qword_180050788
0x180005dae  call    cs:__imp_GetCurrentThreadId
0x180005db4  mov     ecx, [rbx+10h]
0x180005db7  mov     edi, 1
0x180005dbc  add     ecx, edi
0x180005dbe  mov     r14d, eax
0x180005dc1  movsxd  rdx, ecx
0x180005dc4  mov     rcx, [rbx]
0x180005dc7  lea     r8d, [rdi+3]
0x180005dcb  call    cs:__imp__o__recalloc
0x180005dd1  test    rax, rax
0x180005dd4  jnz     short loc_180005DDA
0x180005dd6  xor     edi, edi
0x180005dd8  jmp     short loc_180005E24
0x180005dda  mov     rcx, [rbx+8]
0x180005dde  mov     r8d, 8
0x180005de4  mov     [rbx], rax
0x180005de7  mov     eax, [rbx+10h]
0x180005dea  add     eax, edi
0x180005dec  movsxd  rdx, eax
0x180005def  call    cs:__imp__o__recalloc
0x180005df5  test    rax, rax
0x180005df8  jz      short loc_180005DD6
0x180005dfa  movsxd  r8, dword ptr [rbx+10h]
0x180005dfe  mov     [rbx+8], rax
0x180005e02  mov     rax, [rbx]
0x180005e05  lea     rcx, [rax+r8*4]
0x180005e09  test    rcx, rcx
0x180005e0c  jz      short loc_180005E11
0x180005e0e  mov     [rcx], r14d
0x180005e11  mov     rdx, [rbx+8]
0x180005e15  lea     rax, [rdx+r8*8]
0x180005e19  test    rax, rax
0x180005e1c  jz      short loc_180005E21
0x180005e1e  mov     [rax], rbp
0x180005e21  add     [rbx+10h], edi
0x180005e24  lea     rcx, [rsi+18h]; lpCriticalSection
0x180005e28  call    cs:__imp_LeaveCriticalSection
0x180005e2e  mov     eax, edi
0x180005e30  add     rsp, 20h
0x180005e34  pop     r14
0x180005e36  pop     rdi
0x180005e37  pop     rsi
0x180005e38  pop     rbp
0x180005e39  pop     rbx
0x180005e3a  retn
```

# CLockRead::~CLockRead(void)

- ea: `0x18000fac0`
- end: `0x18000fb4a`
- name: `??1CLockRead@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(CLockRead *__hidden this)`
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x18000468c`
- `0x180004730`
- `0x180004af8`
- `0x180004c8c`
- `0x180005b2c`
- `0x18000f2a0`
- `0x18000f87c`
- `0x18000fb8c`
- `0x180010044`
- `0x1800106f0`
- `0x180010868`
- `0x180010994`
- `0x180010d10`
- `0x1800122d0`
- `0x180013740`
- `0x180019c1c`
- `0x18002f890`
- `0x18002fa94`
- `0x18002fb6c`
- `0x18002fc20`
- `0x18002fcf0`
- `0x1800330b4`
- `0x180033272`
- `0x180033340`
- `0x180033570`
- `0x180033780`
- `0x1800337a0`
- `0x180033930`
- `0x180033c30`
- `0x180033c50`
- `0x180033f20`
- `0x180033f60`
- `0x180033f80`
- `0x180034150`
- `0x1800342d0`
- `0x1800342f0`

## callees

- `0x18000fac0`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fb09`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb2e`

## pseudocode

```c
void __fastcall CLockRead::~CLockRead(CLockRead *this)
{
  void (__fastcall ***v2)(_QWORD, _QWORD, _QWORD); // rbx
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this) )
  {
    v2 = *(void (__fastcall ****)(_QWORD, _QWORD, _QWORD))this;
    (***(void (__fastcall ****)(_QWORD, _QWORD, _QWORD))this)(*(_QWORD *)this, 0, 0);
    if ( !--*(_DWORD *)(*(_QWORD *)this + 56LL) && !SetEvent(*(HANDLE *)(*(_QWORD *)this + 72LL)) )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v2)[1])(v2);
  }
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp+arg_8], rbx
0x18000fac5  push    rdi
0x18000fac6  sub     rsp, 20h
0x18000faca  mov     rdi, rcx
0x18000facd  mov     rcx, [rcx]
0x18000fad0  mov     rax, [rcx]
0x18000fad3  mov     rax, [rax+10h]
0x18000fad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fadc  test    eax, eax
0x18000fade  jnz     short loc_18000FB23
0x18000fae0  mov     rbx, [rdi]
0x18000fae3  mov     rax, [rbx]
0x18000fae6  xor     r8d, r8d
0x18000fae9  xor     edx, edx
0x18000faeb  mov     rcx, rbx
0x18000faee  mov     rax, [rax]
0x18000faf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf6  mov     rax, [rdi]
0x18000faf9  dec     dword ptr [rax+38h]
0x18000fafc  mov     rcx, [rdi]
0x18000faff  cmp     dword ptr [rcx+38h], 0
0x18000fb03  jnz     short loc_18000FB13
0x18000fb05  mov     rcx, [rcx+48h]; hEvent
0x18000fb09  call    cs:__imp_SetEvent
0x18000fb0f  test    eax, eax
0x18000fb11  jz      short loc_18000FB2E
0x18000fb13  mov     rax, [rbx]
0x18000fb16  mov     rcx, rbx
0x18000fb19  mov     rax, [rax+8]
0x18000fb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb22  nop
0x18000fb23  mov     rbx, [rsp+28h+arg_8]
0x18000fb28  add     rsp, 20h
0x18000fb2c  pop     rdi
0x18000fb2d  retn
0x18000fb2e  call    cs:__imp_GetLastError
0x18000fb34  mov     [rsp+28h+pExceptionObject], eax
0x18000fb38  lea     rdx, _TI1K; pThrowInfo
0x18000fb3f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000fb44  call    _CxxThrowException_0
```

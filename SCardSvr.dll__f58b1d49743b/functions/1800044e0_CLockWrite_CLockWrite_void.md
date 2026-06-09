# CLockWrite::~CLockWrite(void)

- ea: `0x1800044e0`
- end: `0x180004575`
- name: `??1CLockWrite@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(CLockWrite *__hidden this)`
- caller_count: `40`
- callee_count: `3`
- tags: ``

## callers

- `0x180001950`
- `0x180003458`
- `0x18000371c`
- `0x1800039e0`
- `0x180003ff0`
- `0x18000457c`
- `0x18000f1c0`
- `0x180015558`
- `0x180017a84`
- `0x180017c60`
- `0x180018d4c`
- `0x180019dd8`
- `0x18001a390`
- `0x18001a748`
- `0x18001af40`
- `0x18002a970`
- `0x18002ab4c`
- `0x18002bf80`
- `0x18002ccd0`
- `0x18002d530`
- `0x18002d62c`
- `0x18002d6cc`
- `0x18002d870`
- `0x18002d928`
- `0x18002daec`
- `0x18002dcc4`
- `0x18002e524`
- `0x18003290b`
- `0x180032941`
- `0x180032c20`
- `0x180032c5d`
- `0x180032d90`
- `0x1800340d0`
- `0x180034110`
- `0x180034e5f`
- `0x180034f70`
- `0x1800351b5`
- `0x180035f4b`
- `0x180035fc9`
- `0x180036054`

## callees

- `0x1800044e0`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004534`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004559`

## pseudocode

```c
void __fastcall CLockWrite::~CLockWrite(CLockWrite *this)
{
  void (__fastcall ***v2)(_QWORD, _QWORD, _QWORD); // rdi
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this) )
  {
    v2 = *(void (__fastcall ****)(_QWORD, _QWORD, _QWORD))this;
    (***(void (__fastcall ****)(_QWORD, _QWORD, _QWORD))this)(*(_QWORD *)this, 0, 0);
    if ( !--*(_DWORD *)(*(_QWORD *)this + 60LL) )
    {
      *(_QWORD *)(*(_QWORD *)this + 104LL) = 0;
      if ( !SetEvent(*(HANDLE *)(*(_QWORD *)this + 88LL)) )
      {
        pExceptionObject = GetLastError();
        throw &pExceptionObject;
      }
    }
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v2)[1])(v2);
  }
}

```

## disassembly

```asm
0x1800044e0  mov     [rsp+arg_8], rbx
0x1800044e5  push    rdi
0x1800044e6  sub     rsp, 20h
0x1800044ea  mov     rbx, rcx
0x1800044ed  mov     rcx, [rcx]
0x1800044f0  mov     rax, [rcx]
0x1800044f3  mov     rax, [rax+10h]
0x1800044f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fc  test    eax, eax
0x1800044fe  jnz     short loc_18000454E
0x180004500  mov     rdi, [rbx]
0x180004503  mov     rax, [rdi]
0x180004506  xor     r8d, r8d
0x180004509  xor     edx, edx
0x18000450b  mov     rcx, rdi
0x18000450e  mov     rax, [rax]
0x180004511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004516  mov     rax, [rbx]
0x180004519  dec     dword ptr [rax+3Ch]
0x18000451c  mov     rax, [rbx]
0x18000451f  cmp     dword ptr [rax+3Ch], 0
0x180004523  jnz     short loc_18000453E
0x180004525  mov     qword ptr [rax+68h], 0
0x18000452d  mov     rcx, [rbx]
0x180004530  mov     rcx, [rcx+58h]; hEvent
0x180004534  call    cs:__imp_SetEvent
0x18000453a  test    eax, eax
0x18000453c  jz      short loc_180004559
0x18000453e  mov     rax, [rdi]
0x180004541  mov     rcx, rdi
0x180004544  mov     rax, [rax+8]
0x180004548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454d  nop
0x18000454e  mov     rbx, [rsp+28h+arg_8]
0x180004553  add     rsp, 20h
0x180004557  pop     rdi
0x180004558  retn
0x180004559  call    cs:__imp_GetLastError
0x18000455f  mov     [rsp+28h+pExceptionObject], eax
0x180004563  lea     rdx, _TI1K; pThrowInfo
0x18000456a  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000456f  call    _CxxThrowException_0
```

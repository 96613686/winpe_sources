# CSharelock::CSharelock(int,int)

- ea: `0x18002f310`
- end: `0x18002f3d6`
- name: `??0CSharelock@@QEAA@HH@Z`
- size: `198`
- prototype: `CSharelock *__fastcall(CSharelock *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001de0`
- `0x180002450`

## callees

- `0x18002f310`
- `0x180034c04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002f364`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002f364`

## string_xrefs

- `0x18002f373`: `Create semaphore in constructor for CSharelock`

## pseudocode

```c
CSharelock *__fastcall CSharelock::CSharelock(CSharelock *this, int a2, int a3)
{
  HANDLE Semaphore; // rax
  const wchar_t *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  *(_DWORD *)this = 0;
  *((_DWORD *)this + 1) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( a2 <= 0 )
  {
    pExceptionObject = L"Maximum spins invalid in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  *((_DWORD *)this + 2) = a2;
  if ( (unsigned int)(a3 - 1) > 0xFF )
  {
    pExceptionObject = L"Maximum share invalid in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  *((_DWORD *)this + 3) = a3;
  Semaphore = CreateSemaphoreExW(0, 0, 256, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 2) = Semaphore;
  if ( !Semaphore )
  {
    pExceptionObject = L"Create semaphore in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18002f310  push    rbx
0x18002f312  sub     rsp, 30h
0x18002f316  mov     dword ptr [rcx], 0
0x18002f31c  mov     rbx, rcx
0x18002f31f  mov     dword ptr [rcx+4], 0
0x18002f326  mov     dword ptr [rcx+18h], 0
0x18002f32d  test    edx, edx
0x18002f32f  jle     loc_18002F3B8
0x18002f335  lea     eax, [r8-1]
0x18002f339  mov     [rcx+8], edx
0x18002f33c  cmp     eax, 0FFh
0x18002f341  ja      short loc_18002F39A
0x18002f343  mov     [rcx+0Ch], r8d
0x18002f347  xor     r9d, r9d; lpName
0x18002f34a  xor     ecx, ecx; lpSemaphoreAttributes
0x18002f34c  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002f354  mov     r8d, 100h; lMaximumCount
0x18002f35a  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002f362  xor     edx, edx; lInitialCount
0x18002f364  call    cs:__imp_CreateSemaphoreExW
0x18002f36a  mov     [rbx+10h], rax
0x18002f36e  test    rax, rax
0x18002f371  jnz     short loc_18002F391
0x18002f373  lea     rax, aCreateSemaphor; "Create semaphore in constructor for CSh"...
0x18002f37a  lea     rdx, _TI2PEAG; pThrowInfo
0x18002f381  mov     [rsp+38h+pExceptionObject], rax
0x18002f386  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002f38b  call    _CxxThrowException_0
0x18002f391  mov     rax, rbx
0x18002f394  add     rsp, 30h
0x18002f398  pop     rbx
0x18002f399  retn
0x18002f39a  lea     rax, aMaximumShareIn; "Maximum share invalid in constructor fo"...
0x18002f3a1  lea     rdx, _TI2PEAG; pThrowInfo
0x18002f3a8  mov     [rsp+38h+pExceptionObject], rax
0x18002f3ad  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002f3b2  call    _CxxThrowException_0
0x18002f3b8  lea     rax, aMaximumSpinsIn; "Maximum spins invalid in constructor fo"...
0x18002f3bf  lea     rdx, _TI2PEAG; pThrowInfo
0x18002f3c6  mov     [rsp+38h+pExceptionObject], rax
0x18002f3cb  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002f3d0  call    _CxxThrowException_0
```

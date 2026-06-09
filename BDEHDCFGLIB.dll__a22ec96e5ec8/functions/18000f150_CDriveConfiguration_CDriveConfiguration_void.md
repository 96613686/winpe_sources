# CDriveConfiguration::~CDriveConfiguration(void)

- ea: `0x18000f150`
- end: `0x18000f1c9`
- name: `??1CDriveConfiguration@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000f150`
- `0x18000f360`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18000f191`
- `msvcrt!_beginthreadex` at `0x18000f191`
- `KERNEL32!WaitForSingleObject` at `0x18000f1a5`
- `KERNEL32!WaitForSingleObject` at `0x18000f1a5`
- `KERNEL32!DeleteCriticalSection` at `0x18000f1c2`
- `KERNEL32!CloseHandle` at `0x18000f1ae`
- `KERNEL32!CloseHandle` at `0x18000f1ae`

## pseudocode

```c
void __fastcall CDriveConfiguration::~CDriveConfiguration(CDriveConfiguration *this)
{
  void *v2; // rax
  void *v3; // rdi
  int ArgList; // [rsp+40h] [rbp+8h] BYREF

  CDriveConfiguration::Cleanup(this);
  if ( *((_DWORD *)this + 316) )
  {
    ArgList = *((_DWORD *)this + 316);
    v2 = (void *)_beginthreadex(0, 0, CQueryCancelAutoPlay::Thread_ROTUnregister, &ArgList, 0, 0);
    v3 = v2;
    if ( v2 )
    {
      WaitForSingleObject(v2, 0xFFFFFFFF);
      CloseHandle(v3);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18000f150  mov     [rsp+arg_8], rbx
0x18000f155  push    rdi
0x18000f156  sub     rsp, 30h
0x18000f15a  mov     rbx, rcx
0x18000f15d  call    ?Cleanup@CDriveConfiguration@@AEAAXXZ; CDriveConfiguration::Cleanup(void)
0x18000f162  mov     eax, [rbx+4F0h]
0x18000f168  test    eax, eax
0x18000f16a  jz      short loc_18000F1B4
0x18000f16c  mov     [rsp+38h+ThrdAddr], 0; ThrdAddr
0x18000f175  lea     r9, [rsp+38h+ArgList]; ArgList
0x18000f17a  lea     r8, ?Thread_ROTUnregister@CQueryCancelAutoPlay@@CAIPEAX@Z; StartAddress
0x18000f181  mov     [rsp+38h+InitFlag], 0; InitFlag
0x18000f189  xor     edx, edx; StackSize
0x18000f18b  mov     [rsp+38h+ArgList], eax
0x18000f18f  xor     ecx, ecx; Security
0x18000f191  call    cs:__imp__beginthreadex
0x18000f197  mov     rdi, rax
0x18000f19a  test    rax, rax
0x18000f19d  jz      short loc_18000F1B4
0x18000f19f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f1a2  mov     rcx, rax; hHandle
0x18000f1a5  call    cs:__imp_WaitForSingleObject
0x18000f1ab  mov     rcx, rdi; hObject
0x18000f1ae  call    cs:__imp_CloseHandle
0x18000f1b4  lea     rcx, [rbx+18h]
0x18000f1b8  mov     rbx, [rsp+38h+arg_8]
0x18000f1bd  add     rsp, 30h
0x18000f1c1  pop     rdi
0x18000f1c2  jmp     cs:__imp_DeleteCriticalSection
```

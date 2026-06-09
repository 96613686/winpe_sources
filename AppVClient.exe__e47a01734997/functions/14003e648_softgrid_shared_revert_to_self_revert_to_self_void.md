# softgrid::shared::revert_to_self::~revert_to_self(void)

- ea: `0x14003e648`
- end: `0x14003e6a7`
- name: `??1revert_to_self@shared@softgrid@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(softgrid::shared::revert_to_self *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140067e24`

## callees

- `0x14003e648`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x14003e65c`
- `ADVAPI32!SetThreadToken` at `0x14003e65c`
- `KERNEL32!RaiseException` at `0x14003e69b`
- `KERNEL32!RaiseException` at `0x14003e69b`
- `KERNEL32!CloseHandle` at `0x14003e66a`
- `KERNEL32!CloseHandle` at `0x14003e686`
- `KERNEL32!CloseHandle` at `0x14003e66a`
- `KERNEL32!CloseHandle` at `0x14003e686`

## pseudocode

```c
void __fastcall softgrid::shared::revert_to_self::~revert_to_self(softgrid::shared::revert_to_self *this)
{
  void *v1; // rdx
  BOOL v3; // eax
  void *v4; // rcx

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    v3 = SetThreadToken(0, v1);
    v4 = (void *)*((_QWORD *)this + 1);
    if ( v3 )
    {
      CloseHandle(v4);
      *((_QWORD *)this + 1) = 0;
      *(_BYTE *)this = 0;
    }
    else
    {
      if ( v4 )
        CloseHandle(v4);
      RaiseException(0x29Cu, 1u, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x14003e648  push    rbx
0x14003e64a  sub     rsp, 20h
0x14003e64e  mov     rdx, [rcx+8]; Token
0x14003e652  mov     rbx, rcx
0x14003e655  test    rdx, rdx
0x14003e658  jz      short loc_14003E6A1
0x14003e65a  xor     ecx, ecx; Thread
0x14003e65c  call    cs:__imp_SetThreadToken
0x14003e662  mov     rcx, [rbx+8]; hObject
0x14003e666  test    eax, eax
0x14003e668  jz      short loc_14003E681
0x14003e66a  call    cs:__imp_CloseHandle
0x14003e670  mov     qword ptr [rbx+8], 0
0x14003e678  mov     byte ptr [rbx], 0
0x14003e67b  add     rsp, 20h
0x14003e67f  pop     rbx
0x14003e680  retn
0x14003e681  test    rcx, rcx
0x14003e684  jz      short loc_14003E68C
0x14003e686  call    cs:__imp_CloseHandle
0x14003e68c  xor     r9d, r9d; lpArguments
0x14003e68f  xor     r8d, r8d; nNumberOfArguments
0x14003e692  mov     ecx, 29Ch; dwExceptionCode
0x14003e697  lea     edx, [r9+1]; dwExceptionFlags
0x14003e69b  call    cs:__imp_RaiseException
0x14003e6a1  add     rsp, 20h
0x14003e6a5  pop     rbx
0x14003e6a6  retn
```

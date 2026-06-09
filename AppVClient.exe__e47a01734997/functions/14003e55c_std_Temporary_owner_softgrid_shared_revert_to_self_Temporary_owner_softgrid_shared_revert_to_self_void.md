# std::_Temporary_owner<softgrid::shared::revert_to_self>::~_Temporary_owner<softgrid::shared::revert_to_self>(void)

- ea: `0x14003e55c`
- end: `0x14003e5c9`
- name: `??1?$_Temporary_owner@Urevert_to_self@shared@softgrid@@@std@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14003e9d8`
- `0x140067a74`

## callees

- `0x140004558`
- `0x14003e55c`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x14003e575`
- `ADVAPI32!SetThreadToken` at `0x14003e575`
- `KERNEL32!RaiseException` at `0x14003e5b0`
- `KERNEL32!RaiseException` at `0x14003e5b0`
- `KERNEL32!CloseHandle` at `0x14003e583`
- `KERNEL32!CloseHandle` at `0x14003e59b`
- `KERNEL32!CloseHandle` at `0x14003e583`
- `KERNEL32!CloseHandle` at `0x14003e59b`

## pseudocode

```c
void __fastcall std::_Temporary_owner<softgrid::shared::revert_to_self>::~_Temporary_owner<softgrid::shared::revert_to_self>(
        void **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rdx
  BOOL v3; // eax
  void *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[1];
    if ( v2 )
    {
      v3 = SetThreadToken(0, v2);
      v4 = (void *)v1[1];
      if ( v3 )
      {
        CloseHandle(v4);
        v1[1] = 0;
        *(_BYTE *)v1 = 0;
      }
      else
      {
        if ( v4 )
          CloseHandle(v4);
        RaiseException(0x29Cu, 1u, 0, 0);
      }
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x14003e55c  push    rbx
0x14003e55e  sub     rsp, 20h
0x14003e562  mov     rbx, [rcx]
0x14003e565  test    rbx, rbx
0x14003e568  jz      short loc_14003E5C3
0x14003e56a  mov     rdx, [rbx+8]; Token
0x14003e56e  test    rdx, rdx
0x14003e571  jz      short loc_14003E5B6
0x14003e573  xor     ecx, ecx; Thread
0x14003e575  call    cs:__imp_SetThreadToken
0x14003e57b  mov     rcx, [rbx+8]; hObject
0x14003e57f  test    eax, eax
0x14003e581  jz      short loc_14003E596
0x14003e583  call    cs:__imp_CloseHandle
0x14003e589  mov     qword ptr [rbx+8], 0
0x14003e591  mov     byte ptr [rbx], 0
0x14003e594  jmp     short loc_14003E5B6
0x14003e596  test    rcx, rcx
0x14003e599  jz      short loc_14003E5A1
0x14003e59b  call    cs:__imp_CloseHandle
0x14003e5a1  xor     r9d, r9d; lpArguments
0x14003e5a4  xor     r8d, r8d; nNumberOfArguments
0x14003e5a7  mov     ecx, 29Ch; dwExceptionCode
0x14003e5ac  lea     edx, [r9+1]; dwExceptionFlags
0x14003e5b0  call    cs:__imp_RaiseException
0x14003e5b6  mov     edx, 10h
0x14003e5bb  mov     rcx, rbx; Block
0x14003e5be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003e5c3  add     rsp, 20h
0x14003e5c7  pop     rbx
0x14003e5c8  retn
```

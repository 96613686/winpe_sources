# std::_Ref_count<softgrid::shared::revert_to_self>::_Destroy(void)

- ea: `0x14003ec00`
- end: `0x14003ec6e`
- name: `?_Destroy@?$_Ref_count@Urevert_to_self@shared@softgrid@@@std@@EEAAXXZ`
- size: `110`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140004558`
- `0x14003ec00`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x14003ec1a`
- `ADVAPI32!SetThreadToken` at `0x14003ec1a`
- `KERNEL32!RaiseException` at `0x14003ec55`
- `KERNEL32!RaiseException` at `0x14003ec55`
- `KERNEL32!CloseHandle` at `0x14003ec28`
- `KERNEL32!CloseHandle` at `0x14003ec40`
- `KERNEL32!CloseHandle` at `0x14003ec28`
- `KERNEL32!CloseHandle` at `0x14003ec40`

## pseudocode

```c
void __fastcall std::_Ref_count<softgrid::shared::revert_to_self>::_Destroy(__int64 a1)
{
  _QWORD *v1; // rbx
  void *v2; // rdx
  BOOL v3; // eax
  void *v4; // rcx

  v1 = *(_QWORD **)(a1 + 16);
  if ( v1 )
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
0x14003ec00  push    rbx
0x14003ec02  sub     rsp, 20h
0x14003ec06  mov     rbx, [rcx+10h]
0x14003ec0a  test    rbx, rbx
0x14003ec0d  jz      short loc_14003EC68
0x14003ec0f  mov     rdx, [rbx+8]; Token
0x14003ec13  test    rdx, rdx
0x14003ec16  jz      short loc_14003EC5B
0x14003ec18  xor     ecx, ecx; Thread
0x14003ec1a  call    cs:__imp_SetThreadToken
0x14003ec20  mov     rcx, [rbx+8]; hObject
0x14003ec24  test    eax, eax
0x14003ec26  jz      short loc_14003EC3B
0x14003ec28  call    cs:__imp_CloseHandle
0x14003ec2e  mov     qword ptr [rbx+8], 0
0x14003ec36  mov     byte ptr [rbx], 0
0x14003ec39  jmp     short loc_14003EC5B
0x14003ec3b  test    rcx, rcx
0x14003ec3e  jz      short loc_14003EC46
0x14003ec40  call    cs:__imp_CloseHandle
0x14003ec46  xor     r9d, r9d; lpArguments
0x14003ec49  xor     r8d, r8d; nNumberOfArguments
0x14003ec4c  mov     ecx, 29Ch; dwExceptionCode
0x14003ec51  lea     edx, [r9+1]; dwExceptionFlags
0x14003ec55  call    cs:__imp_RaiseException
0x14003ec5b  mov     edx, 10h
0x14003ec60  mov     rcx, rbx; Block
0x14003ec63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14003ec68  add     rsp, 20h
0x14003ec6c  pop     rbx
0x14003ec6d  retn
```

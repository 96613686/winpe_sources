# ParallelTasks::WaitForAll(void)

- ea: `0x1800a3da8`
- end: `0x1800a3ebe`
- name: `?WaitForAll@ParallelTasks@@QEAAXXZ`
- size: `278`
- prototype: `void __fastcall(ParallelTasks *__hidden this)`
- caller_count: `42`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180031bd0`
- `0x180031e18`
- `0x180032060`
- `0x1800322a8`
- `0x1800324f0`
- `0x180032738`
- `0x180032f34`
- `0x180077a44`
- `0x180077b20`
- `0x180080dd8`
- `0x180080f88`
- `0x18008113c`
- `0x180081bf8`
- `0x180082544`
- `0x1800826cc`
- `0x180084d3c`
- `0x1800857e4`
- `0x180089090`
- `0x18008ae34`
- `0x18008af20`
- `0x18008b00c`
- `0x18008b0f8`
- `0x18008b990`
- `0x18008ba44`
- `0x18008bd0c`
- `0x18008bec0`
- `0x18008c074`
- `0x18008c228`
- `0x18008c470`
- `0x18008c6b8`
- `0x18008c900`
- `0x18008da4c`
- `0x18008db20`
- `0x18008dbf4`
- `0x18008dcc8`
- `0x18008dd9c`
- `0x18008de70`
- `0x18008df44`
- `0x18008e018`
- `0x180090e9c`
- `0x18013b658`
- `0x18013b6fc`

## callees

- `0x180002420`
- `0x180003088`
- `0x180003094`
- `0x1800a3da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a3e44`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a3e44`

## pseudocode

```c
void __fastcall ParallelTasks::WaitForAll(ParallelTasks *this)
{
  __int64 v2; // r9
  __int64 v3; // rbx
  __int64 i; // r8
  int j; // edx
  __int64 v6; // rcx
  _DWORD pExceptionObject[4]; // [rsp+30h] [rbp-228h] BYREF
  HANDLE Handles[64]; // [rsp+40h] [rbp-218h] BYREF

  memset_0(Handles, 0, sizeof(Handles));
  v2 = *(_QWORD *)this;
  v3 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 4;
  if ( (int)v3 > 64 )
  {
    pExceptionObject[0] = 4;
    throw (ErrorCode *)pExceptionObject;
  }
  for ( i = 0; (int)i < (int)v3; i = (unsigned int)(i + 1) )
    Handles[i] = *(HANDLE *)(*(_QWORD *)(v2 + 16LL * (unsigned int)i) + 16LL);
  if ( WaitForMultipleObjectsEx(v3, Handles, 1, 0xFFFFFFFF, 0) == -1 )
  {
    pExceptionObject[0] = 4;
    throw (ErrorCode *)pExceptionObject;
  }
  for ( j = 0; j < (int)v3; ++j )
  {
    v6 = *(_QWORD *)(*(_QWORD *)this + 16LL * j);
    if ( *(_DWORD *)(v6 + 24) )
    {
      pExceptionObject[0] = *(_DWORD *)(v6 + 24);
      throw (ErrorCode *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800a3da8  mov     [rsp+arg_8], rbx
0x1800a3dad  push    rdi
0x1800a3dae  sub     rsp, 250h
0x1800a3db5  mov     rax, cs:__security_cookie
0x1800a3dbc  xor     rax, rsp
0x1800a3dbf  mov     [rsp+258h+var_18], rax
0x1800a3dc7  mov     rdi, rcx
0x1800a3dca  xor     edx, edx; Val
0x1800a3dcc  lea     rcx, [rsp+258h+Handles]; void *
0x1800a3dd1  mov     r8d, 200h; Size
0x1800a3dd7  call    memset_0
0x1800a3ddc  mov     r9, [rdi]
0x1800a3ddf  mov     rbx, [rdi+8]
0x1800a3de3  sub     rbx, r9
0x1800a3de6  sar     rbx, 4
0x1800a3dea  cmp     ebx, 40h ; '@'
0x1800a3ded  jle     short loc_1800A3E09
0x1800a3def  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a3df6  mov     [rsp+258h+pExceptionObject], 4
0x1800a3dfe  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x1800a3e03  call    _CxxThrowException_0
0x1800a3e09  xor     r8d, r8d
0x1800a3e0c  test    ebx, ebx
0x1800a3e0e  jle     short loc_1800A3E2B
0x1800a3e10  mov     eax, r8d
0x1800a3e13  add     rax, rax
0x1800a3e16  mov     rax, [r9+rax*8]
0x1800a3e1a  mov     rcx, [rax+10h]
0x1800a3e1e  mov     [rsp+r8*8+258h+Handles], rcx
0x1800a3e23  inc     r8d
0x1800a3e26  cmp     r8d, ebx
0x1800a3e29  jl      short loc_1800A3E10
0x1800a3e2b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a3e2f  mov     [rsp+258h+bAlertable], 0; bAlertable
0x1800a3e37  mov     r8d, 1; bWaitAll
0x1800a3e3d  lea     rdx, [rsp+258h+Handles]; lpHandles
0x1800a3e42  mov     ecx, ebx; nCount
0x1800a3e44  call    cs:__imp_WaitForMultipleObjectsEx
0x1800a3e4a  cmp     eax, 0FFFFFFFFh
0x1800a3e4d  jnz     short loc_1800A3E69
0x1800a3e4f  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a3e56  mov     [rsp+258h+pExceptionObject], 4
0x1800a3e5e  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x1800a3e63  call    _CxxThrowException_0
0x1800a3e69  xor     edx, edx
0x1800a3e6b  cmp     edx, ebx
0x1800a3e6d  jge     short loc_1800A3E9D
0x1800a3e6f  mov     rax, [rdi]
0x1800a3e72  movsxd  rcx, edx
0x1800a3e75  add     rcx, rcx
0x1800a3e78  mov     rcx, [rax+rcx*8]
0x1800a3e7c  mov     eax, [rcx+18h]
0x1800a3e7f  test    eax, eax
0x1800a3e81  jnz     short loc_1800A3E87
0x1800a3e83  inc     edx
0x1800a3e85  jmp     short loc_1800A3E6B
0x1800a3e87  lea     rdx, _TI1?AW4ErrorCode@@; pThrowInfo
0x1800a3e8e  mov     [rsp+258h+pExceptionObject], eax
0x1800a3e92  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x1800a3e97  call    _CxxThrowException_0
0x1800a3e9d  mov     rcx, [rsp+258h+var_18]
0x1800a3ea5  xor     rcx, rsp; StackCookie
0x1800a3ea8  call    __security_check_cookie
0x1800a3ead  mov     rbx, [rsp+258h+arg_8]
0x1800a3eb5  add     rsp, 250h
0x1800a3ebc  pop     rdi
0x1800a3ebd  retn
```

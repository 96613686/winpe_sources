# StopAndWaitForService

- ea: `0x180005d90`
- end: `0x180005df2`
- name: `StopAndWaitForService`
- size: `98`
- prototype: `__int64 __fastcall(_WORD *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800054b0`
- `0x180005bf0`
- `0x180005d90`
- `0x18000a190`

## pseudocode

```c
__int64 __fastcall StopAndWaitForService(_WORD *a1, unsigned int a2)
{
  __int64 result; // rax
  signed int v4; // eax
  unsigned int v5; // ecx
  WCHAR ServiceName[264]; // [rsp+20h] [rbp-228h] BYREF

  result = GenerateUserModeServiceName(a1, ServiceName, 0x104u, 0);
  if ( (int)result >= 0 )
  {
    v4 = StopAndWaitForFullyNamedService(ServiceName, a2);
    v5 = 0;
    if ( v4 < 0 )
      return (unsigned int)v4;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180005d90  push    rbx
0x180005d92  sub     rsp, 240h
0x180005d99  mov     rax, cs:__security_cookie
0x180005da0  xor     rax, rsp
0x180005da3  mov     [rsp+248h+var_18], rax
0x180005dab  mov     ebx, edx
0x180005dad  xor     r9d, r9d
0x180005db0  lea     rdx, [rsp+248h+ServiceName]
0x180005db5  mov     r8d, 104h
0x180005dbb  call    GenerateUserModeServiceName
0x180005dc0  test    eax, eax
0x180005dc2  js      short loc_180005DD9
0x180005dc4  mov     edx, ebx
0x180005dc6  lea     rcx, [rsp+248h+ServiceName]; lpServiceName
0x180005dcb  call    StopAndWaitForFullyNamedService
0x180005dd0  xor     ecx, ecx
0x180005dd2  test    eax, eax
0x180005dd4  cmovs   ecx, eax
0x180005dd7  mov     eax, ecx
0x180005dd9  mov     rcx, [rsp+248h+var_18]
0x180005de1  xor     rcx, rsp; StackCookie
0x180005de4  call    __security_check_cookie
0x180005de9  add     rsp, 240h
0x180005df0  pop     rbx
0x180005df1  retn
```

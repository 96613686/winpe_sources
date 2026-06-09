# MVGetMccLookupTablePath(ushort *,ulong)

- ea: `0x180006e2c`
- end: `0x180006ea3`
- name: `?MVGetMccLookupTablePath@@YAJPEAGK@Z`
- size: `119`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006eb0`
- `0x180007a30`

## callees

- `0x180005e24`
- `0x180006e2c`
- `0x18000f998`
- `0x180010d44`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall MVGetMccLookupTablePath(unsigned __int16 *a1)
{
  int MccLookupTablePath; // ebx
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  MccLookupTablePath = GetMccLookupTablePath(FileName, 0x105u);
  if ( MccLookupTablePath >= 0 )
  {
    MccLookupTablePath = StringCchCopyW(a1, 0x105u, FileName);
    if ( MccLookupTablePath < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return (unsigned int)MccLookupTablePath;
}

```

## disassembly

```asm
0x180006e2c  mov     [rsp+arg_8], rbx
0x180006e31  push    rdi
0x180006e32  sub     rsp, 240h
0x180006e39  mov     rax, cs:__security_cookie
0x180006e40  xor     rax, rsp
0x180006e43  mov     [rsp+248h+var_18], rax
0x180006e4b  mov     rdi, rcx
0x180006e4e  mov     edx, 105h; unsigned int
0x180006e53  lea     rcx, [rsp+248h+FileName]; lpFileName
0x180006e58  call    ?GetMccLookupTablePath@@YAJPEAGK@Z; GetMccLookupTablePath(ushort *,ulong)
0x180006e5d  mov     ebx, eax
0x180006e5f  test    eax, eax
0x180006e61  js      short loc_180006E80
0x180006e63  lea     r8, [rsp+248h+FileName]; unsigned __int16 *
0x180006e68  mov     edx, 105h; unsigned __int64
0x180006e6d  mov     rcx, rdi; unsigned __int16 *
0x180006e70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006e75  mov     ebx, eax
0x180006e77  test    eax, eax
0x180006e79  jns     short loc_180006E80
0x180006e7b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006e80  mov     eax, ebx
0x180006e82  mov     rcx, [rsp+248h+var_18]
0x180006e8a  xor     rcx, rsp; StackCookie
0x180006e8d  call    __security_check_cookie
0x180006e92  mov     rbx, [rsp+248h+arg_8]
0x180006e9a  add     rsp, 240h
0x180006ea1  pop     rdi
0x180006ea2  retn
```

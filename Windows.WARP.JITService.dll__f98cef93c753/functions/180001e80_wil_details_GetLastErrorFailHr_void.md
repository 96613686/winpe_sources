# wil::details::GetLastErrorFailHr(void)

- ea: `0x180001e80`
- end: `0x180001ed4`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `84`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003280`
- `0x180003924`
- `0x180005b00`

## callees

- `0x180001e80`
- `0x180006c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e8b`

## pseudocode

```c
__int64 __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int LastError; // ecx
  __int64 result; // rax
  wil::details *v3; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v3) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v3);
    LastError = 668;
  }
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180001e80  push    rbx
0x180001e82  sub     rsp, 40h
0x180001e86  mov     rbx, [rsp+48h]
0x180001e8b  call    cs:__imp_GetLastError
0x180001e91  mov     ecx, eax
0x180001e93  test    eax, eax
0x180001e95  jnz     short loc_180001EC1
0x180001e97  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180001e9f  mov     [rsp+48h+var_20], rbx; __int64
0x180001ea4  mov     [rsp+48h+var_28], 0; __int64
0x180001ead  xor     r9d, r9d; int
0x180001eb0  xor     r8d, r8d; int
0x180001eb3  xor     edx, edx; int
0x180001eb5  xor     ecx, ecx; int
0x180001eb7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180001ebc  mov     ecx, 29Ch
0x180001ec1  movzx   eax, cx
0x180001ec4  or      eax, 80070000h
0x180001ec9  test    ecx, ecx
0x180001ecb  cmovle  eax, ecx
0x180001ece  add     rsp, 40h
0x180001ed2  pop     rbx
0x180001ed3  retn
```

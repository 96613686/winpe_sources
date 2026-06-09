# AiInitializePathMacroList

- ea: `0x140027ebc`
- end: `0x140028038`
- name: `AiInitializePathMacroList`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140022ad0`

## callees

- `0x140006f40`
- `0x140027ebc`
- `0x140028040`
- `0x1400281b4`
- `0x1400284d8`
- `0x1400365f0`

## import_xrefs

- `ntoskrnl!RtlGetNtSystemRoot` at `0x140027f66`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x140027f66`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f79`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f79`

## string_xrefs

- `0x140027ef7`: `%SYSTEM32%`
- `0x140027f0d`: `%WINDIR%\System32`

## pseudocode

```c
NTSTATUS AiInitializePathMacroList()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  const WCHAR *NtSystemRoot; // rax
  NTSTATUS result; // eax
  __int64 v6; // [rsp+20h] [rbp-60h] BYREF
  __int64 v7; // [rsp+30h] [rbp-50h] BYREF
  __int64 v8; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+50h] [rbp-30h] BYREF
  __int64 v10; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF

  DestinationString = 0;
  memset(&AipPathMacroList, 0, 0x48u);
  qword_1400195C0 = (__int64)&qword_1400195B8;
  qword_1400195B8 = (__int64)&qword_1400195B8;
  AipPathMacroListInitialized = 1;
  dword_140019584 = 1;
  NtSystemRoot = (const WCHAR *)RtlGetNtSystemRoot(
                                  v1,
                                  v0,
                                  v2,
                                  v3,
                                  1441812,
                                  L"%SYSTEM32%",
                                  1179664,
                                  L"%WINDIR%",
                                  1310738,
                                  L"%OSDRIVE%",
                                  2359330,
                                  L"%WINDIR%\\System32",
                                  2359330,
                                  L"%WINDIR%\\SysWOW64");
  RtlInitUnicodeString(&DestinationString, NtSystemRoot);
  result = AipAddPathMacro(&v7, &DestinationString, 12);
  if ( result >= 0 )
  {
    xmmword_140019588 = (__int128)DestinationString;
    LOWORD(xmmword_140019588) = 4;
    result = AipConvertToNtPath((struct _UNICODE_STRING *)&xmmword_140019588, &String2);
    if ( result >= 0 )
    {
      result = AipAddPathMacro(&v8, &String2, 12);
      if ( result >= 0 )
      {
        result = AipAddPathMacro(&v6, &v9, 8);
        if ( result >= 0 )
        {
          if ( !dword_140019584 || (result = AipAddPathMacro(&v6, &v10, 8), result >= 0) )
          {
            result = AipExpandPathMacros();
            if ( result >= 0 )
              return AiInitializeSoftwarePathMacroList();
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027ebc  push    rbp
0x140027ebe  mov     rbp, rsp
0x140027ec1  sub     rsp, 80h
0x140027ec8  lea     rax, aOsdrive; "%OSDRIVE%"
0x140027ecf  mov     [rbp+var_40], 140012h
0x140027ed7  mov     [rbp+var_38], rax
0x140027edb  lea     rcx, AipPathMacroList; void *
0x140027ee2  lea     rax, aWindir; "%WINDIR%"
0x140027ee9  mov     [rbp+var_50], 120010h
0x140027ef1  mov     [rbp+var_48], rax
0x140027ef5  xor     edx, edx; Val
0x140027ef7  lea     rax, aSystem32; "%SYSTEM32%"
0x140027efe  mov     [rbp+var_60], 160014h
0x140027f06  mov     [rbp+var_58], rax
0x140027f0a  xorps   xmm0, xmm0
0x140027f0d  lea     rax, aWindirSystem32; "%WINDIR%\\System32"
0x140027f14  mov     [rbp+var_30], 240022h
0x140027f1c  mov     [rbp+var_28], rax
0x140027f20  lea     r8d, [rdx+48h]; Size
0x140027f24  lea     rax, aWindirSyswow64; "%WINDIR%\\SysWOW64"
0x140027f2b  mov     [rbp+var_20], 240022h
0x140027f33  mov     [rbp+var_18], rax
0x140027f37  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140027f3b  call    memset
0x140027f40  lea     rax, qword_1400195B8
0x140027f47  mov     cs:qword_1400195C0, rax
0x140027f4e  mov     cs:qword_1400195B8, rax
0x140027f55  mov     eax, 1
0x140027f5a  mov     cs:AipPathMacroListInitialized, eax
0x140027f60  mov     cs:dword_140019584, eax
0x140027f66  call    cs:__imp_RtlGetNtSystemRoot
0x140027f6d  nop     dword ptr [rax+rax+00h]
0x140027f72  mov     rdx, rax; SourceString
0x140027f75  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027f79  call    cs:__imp_RtlInitUnicodeString
0x140027f80  nop     dword ptr [rax+rax+00h]
0x140027f85  mov     r8d, 0Ch
0x140027f8b  lea     rdx, [rbp+DestinationString]
0x140027f8f  lea     rcx, [rbp+var_50]
0x140027f93  call    AipAddPathMacro
0x140027f98  test    eax, eax
0x140027f9a  js      loc_14002802E
0x140027fa0  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x140027fa4  mov     eax, 4
0x140027fa9  lea     rdx, String2
0x140027fb0  lea     rcx, xmmword_140019588
0x140027fb7  movdqu  cs:xmmword_140019588, xmm0
0x140027fbf  mov     word ptr cs:xmmword_140019588, ax
0x140027fc6  call    AipConvertToNtPath
0x140027fcb  test    eax, eax
0x140027fcd  js      short loc_14002802E
0x140027fcf  mov     r8d, 0Ch
0x140027fd5  lea     rdx, String2
0x140027fdc  lea     rcx, [rbp+var_40]
0x140027fe0  call    AipAddPathMacro
0x140027fe5  test    eax, eax
0x140027fe7  js      short loc_14002802E
0x140027fe9  mov     r8d, 8
0x140027fef  lea     rdx, [rbp+var_30]
0x140027ff3  lea     rcx, [rbp+var_60]
0x140027ff7  call    AipAddPathMacro
0x140027ffc  test    eax, eax
0x140027ffe  js      short loc_14002802E
0x140028000  cmp     cs:dword_140019584, 0
0x140028007  jz      short loc_140028020
0x140028009  mov     r8d, 8
0x14002800f  lea     rdx, [rbp+var_20]
0x140028013  lea     rcx, [rbp+var_60]
0x140028017  call    AipAddPathMacro
0x14002801c  test    eax, eax
0x14002801e  js      short loc_14002802E
0x140028020  call    AipExpandPathMacros
0x140028025  test    eax, eax
0x140028027  js      short loc_14002802E
0x140028029  call    AiInitializeSoftwarePathMacroList
0x14002802e  add     rsp, 80h
0x140028035  pop     rbp
0x140028036  retn
```

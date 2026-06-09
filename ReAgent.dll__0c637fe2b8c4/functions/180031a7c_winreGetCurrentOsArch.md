# winreGetCurrentOsArch

- ea: `0x180031a7c`
- end: `0x180031bb0`
- name: `winreGetCurrentOsArch`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180030770`

## callees

- `0x1800059fc`
- `0x18000c658`
- `0x1800318c0`
- `0x180031a7c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031ace`
- `KERNEL32!GetLastError` at `0x180031b6f`
- `KERNEL32!GetLastError` at `0x180031ace`
- `KERNEL32!GetLastError` at `0x180031b6f`
- `KERNEL32!GetSystemDirectoryW` at `0x180031ac4`
- `KERNEL32!GetSystemDirectoryW` at `0x180031ac4`

## string_xrefs

- `0x180031ad4`: `failed to get system directory`
- `0x180031aec`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x180031b24`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x180031b0a`: `\kernel32.dll`
- `0x180031b3b`: `failed to concatenate kernel32.dll path`

## pseudocode

```c
__int64 __fastcall winreGetCurrentOsArch(_DWORD *a1, _DWORD *a2, _DWORD *a3)
{
  DWORD LastError; // eax
  const wchar_t *v7; // r8
  int v8; // ebx
  int v10; // [rsp+28h] [rbp-290h]
  int v11; // [rsp+28h] [rbp-290h]
  WCHAR Buffer[304]; // [rsp+30h] [rbp-288h] BYREF

  memset_0(Buffer, 0, 0x25Cu);
  if ( GetSystemDirectoryW(Buffer, 0x12Eu) )
  {
    v8 = StringCchCatW(Buffer, 0x12Eu, L"\\kernel32.dll");
    if ( v8 < 0 )
    {
      v11 = 2370;
      UnattendLogW(
        2,
        L"winreGetCurrentOsArch %s (0x%x) in file %S line %d",
        L"failed to concatenate kernel32.dll path",
        (unsigned int)v8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
        v11);
      return (unsigned __int16)v8;
    }
    if ( (unsigned int)winreGetBinaryArch(Buffer, a1, a2, a3) )
      return 0;
    LastError = GetLastError();
    v7 = L"failed to get binary architecture";
    v10 = 2374;
  }
  else
  {
    LastError = GetLastError();
    v7 = L"failed to get system directory";
    v10 = 2366;
  }
  v8 = LastError;
  UnattendLogW(
    2,
    L"winreGetCurrentOsArch %s (0x%x) in file %S line %d",
    v7,
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
    v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031a7c  mov     [rsp+arg_18], rbx
0x180031a81  push    rbp
0x180031a82  push    rsi
0x180031a83  push    rdi
0x180031a84  sub     rsp, 2A0h
0x180031a8b  mov     rax, cs:__security_cookie
0x180031a92  xor     rax, rsp
0x180031a95  mov     [rsp+2B8h+var_28], rax
0x180031a9d  mov     rbp, r8
0x180031aa0  mov     rsi, rdx
0x180031aa3  mov     rdi, rcx
0x180031aa6  xor     edx, edx; Val
0x180031aa8  mov     r8d, 25Ch; Size
0x180031aae  lea     rcx, [rsp+2B8h+Buffer]; void *
0x180031ab3  call    memset_0
0x180031ab8  mov     ebx, 12Eh
0x180031abd  lea     rcx, [rsp+2B8h+Buffer]; lpBuffer
0x180031ac2  mov     edx, ebx; uSize
0x180031ac4  call    cs:__imp_GetSystemDirectoryW
0x180031aca  test    eax, eax
0x180031acc  jnz     short loc_180031B0A
0x180031ace  call    cs:__imp_GetLastError
0x180031ad4  lea     r8, aFailedToGetSys_1; "failed to get system directory"
0x180031adb  mov     [rsp+2B8h+var_290], 93Eh
0x180031ae3  mov     ebx, eax
0x180031ae5  lea     rdx, aWinregetcurren; "winreGetCurrentOsArch %s (0x%x) in file"...
0x180031aec  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180031af3  mov     r9d, ebx
0x180031af6  mov     ecx, 2
0x180031afb  mov     [rsp+2B8h+var_298], rax
0x180031b00  call    UnattendLogW
0x180031b05  jmp     loc_180031B8B
0x180031b0a  lea     r8, aKernel32Dll_0; "\\kernel32.dll"
0x180031b11  mov     rdx, rbx; unsigned __int64
0x180031b14  lea     rcx, [rsp+2B8h+Buffer]; unsigned __int16 *
0x180031b19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031b1e  mov     ebx, eax
0x180031b20  test    eax, eax
0x180031b22  jns     short loc_180031B58
0x180031b24  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180031b2b  mov     [rsp+2B8h+var_290], 942h
0x180031b33  mov     r9d, ebx
0x180031b36  mov     [rsp+2B8h+var_298], rax
0x180031b3b  lea     r8, aFailedToConcat_0; "failed to concatenate kernel32.dll path"
0x180031b42  mov     ecx, 2
0x180031b47  lea     rdx, aWinregetcurren; "winreGetCurrentOsArch %s (0x%x) in file"...
0x180031b4e  call    UnattendLogW
0x180031b53  movzx   ebx, bx
0x180031b56  jmp     short loc_180031B8B
0x180031b58  mov     r9, rbp
0x180031b5b  lea     rcx, [rsp+2B8h+Buffer]
0x180031b60  mov     r8, rsi
0x180031b63  mov     rdx, rdi
0x180031b66  call    winreGetBinaryArch
0x180031b6b  test    eax, eax
0x180031b6d  jnz     short loc_180031B89
0x180031b6f  call    cs:__imp_GetLastError
0x180031b75  lea     r8, aFailedToGetBin; "failed to get binary architecture"
0x180031b7c  mov     [rsp+2B8h+var_290], 946h
0x180031b84  jmp     loc_180031AE3
0x180031b89  xor     ebx, ebx
0x180031b8b  mov     eax, ebx
0x180031b8d  mov     rcx, [rsp+2B8h+var_28]
0x180031b95  xor     rcx, rsp; StackCookie
0x180031b98  call    __security_check_cookie
0x180031b9d  mov     rbx, [rsp+2B8h+arg_18]
0x180031ba5  add     rsp, 2A0h
0x180031bac  pop     rdi
0x180031bad  pop     rsi
0x180031bae  pop     rbp
0x180031baf  retn
```

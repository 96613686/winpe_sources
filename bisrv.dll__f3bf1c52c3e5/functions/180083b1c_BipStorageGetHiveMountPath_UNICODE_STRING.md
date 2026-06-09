# BipStorageGetHiveMountPath(_UNICODE_STRING *)

- ea: `0x180083b1c`
- end: `0x180083c05`
- name: `?BipStorageGetHiveMountPath@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180083c0c`

## callees

- `0x18006d804`
- `0x180083b1c`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180083ba0`
- `ntdll!RtlAppendUnicodeToString` at `0x180083ba0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180083bb4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180083bb4`
- `ntdll!RtlFreeUnicodeString` at `0x180083bd5`
- `ntdll!RtlFreeUnicodeString` at `0x180083bdf`
- `ntdll!RtlFreeUnicodeString` at `0x180083bd5`
- `ntdll!RtlFreeUnicodeString` at `0x180083bdf`
- `ntdll!RtlStringFromGUID` at `0x180083b89`
- `ntdll!RtlStringFromGUID` at `0x180083b89`
- `RPCRT4!UuidCreate` at `0x180083b69`
- `RPCRT4!UuidCreate` at `0x180083b69`

## string_xrefs

- `0x180083b95`: `\REGISTRY\A\`

## pseudocode

```c
__int64 __fastcall BipStorageGetHiveMountPath(struct _UNICODE_STRING *a1, __int64 a2, __int64 a3)
{
  NTSTATUS appended; // ebx
  RPC_STATUS v5; // eax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  Uuid = 0;
  GuidString = 0;
  Destination = 0;
  appended = BipAllocateUnicodeString(1024, &Destination, a3);
  if ( appended >= 0 )
  {
    v5 = UuidCreate(&Uuid);
    if ( !v5 || v5 == 1824 )
    {
      appended = RtlStringFromGUID(&Uuid, &GuidString);
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeToString(&Destination, L"\\REGISTRY\\A\\");
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, &GuidString);
          if ( appended >= 0 )
          {
            appended = 0;
            *a1 = Destination;
            Destination = 0;
          }
        }
      }
    }
    else
    {
      appended = -1073741823;
    }
  }
  RtlFreeUnicodeString(&Destination);
  RtlFreeUnicodeString(&GuidString);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180083b1c  mov     [rsp-8+arg_8], rbx
0x180083b21  mov     [rsp-8+arg_10], rdi
0x180083b26  push    rbp
0x180083b27  mov     rbp, rsp
0x180083b2a  sub     rsp, 60h
0x180083b2e  mov     rax, cs:__security_cookie
0x180083b35  xor     rax, rsp
0x180083b38  mov     [rbp+var_10], rax
0x180083b3c  xorps   xmm0, xmm0
0x180083b3f  lea     rdx, [rbp+Destination]
0x180083b43  mov     rdi, rcx
0x180083b46  xorps   xmm1, xmm1
0x180083b49  mov     ecx, 400h
0x180083b4e  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180083b52  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x180083b56  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180083b5a  call    BipAllocateUnicodeString
0x180083b5f  mov     ebx, eax
0x180083b61  test    eax, eax
0x180083b63  js      short loc_180083BD1
0x180083b65  lea     rcx, [rbp+Uuid]; Uuid
0x180083b69  call    cs:__imp_UuidCreate
0x180083b6f  test    eax, eax
0x180083b71  jz      short loc_180083B81
0x180083b73  cmp     eax, 720h
0x180083b78  jz      short loc_180083B81
0x180083b7a  mov     ebx, 0C0000001h
0x180083b7f  jmp     short loc_180083BD1
0x180083b81  lea     rdx, [rbp+GuidString]; GuidString
0x180083b85  lea     rcx, [rbp+Uuid]; Guid
0x180083b89  call    cs:__imp_RtlStringFromGUID
0x180083b8f  mov     ebx, eax
0x180083b91  test    eax, eax
0x180083b93  js      short loc_180083BD1
0x180083b95  lea     rdx, aRegistryA; "\\REGISTRY\\A\\"
0x180083b9c  lea     rcx, [rbp+Destination]; Destination
0x180083ba0  call    cs:__imp_RtlAppendUnicodeToString
0x180083ba6  mov     ebx, eax
0x180083ba8  test    eax, eax
0x180083baa  js      short loc_180083BD1
0x180083bac  lea     rdx, [rbp+GuidString]; Source
0x180083bb0  lea     rcx, [rbp+Destination]; Destination
0x180083bb4  call    cs:__imp_RtlAppendUnicodeStringToString
0x180083bba  mov     ebx, eax
0x180083bbc  test    eax, eax
0x180083bbe  js      short loc_180083BD1
0x180083bc0  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x180083bc4  xor     ebx, ebx
0x180083bc6  xorps   xmm1, xmm1
0x180083bc9  movdqu  xmmword ptr [rdi], xmm0
0x180083bcd  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x180083bd1  lea     rcx, [rbp+Destination]; UnicodeString
0x180083bd5  call    cs:__imp_RtlFreeUnicodeString
0x180083bdb  lea     rcx, [rbp+GuidString]; UnicodeString
0x180083bdf  call    cs:__imp_RtlFreeUnicodeString
0x180083be5  mov     eax, ebx
0x180083be7  mov     rcx, [rbp+var_10]
0x180083beb  xor     rcx, rsp; StackCookie
0x180083bee  call    __security_check_cookie
0x180083bf3  lea     r11, [rsp+60h+var_s0]
0x180083bf8  mov     rbx, [r11+18h]
0x180083bfc  mov     rdi, [r11+20h]
0x180083c00  mov     rsp, r11
0x180083c03  pop     rbp
0x180083c04  retn
```

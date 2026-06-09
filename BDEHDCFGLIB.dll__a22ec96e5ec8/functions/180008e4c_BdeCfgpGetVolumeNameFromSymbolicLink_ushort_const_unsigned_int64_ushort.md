# BdeCfgpGetVolumeNameFromSymbolicLink(ushort const *,unsigned __int64,ushort *)

- ea: `0x180008e4c`
- end: `0x180008ff8`
- name: `?BdeCfgpGetVolumeNameFromSymbolicLink@@YAJPEBG_KPEAG@Z`
- size: `428`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007210`
- `0x180007624`
- `0x18000fb40`

## callees

- `0x180006c30`
- `0x180008e4c`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180008f8b`
- `msvcrt!_wcsnicmp` at `0x180008f8b`
- `ntdll!RtlInitUnicodeString` at `0x180008ed5`
- `ntdll!RtlInitUnicodeString` at `0x180008ed5`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180008f16`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180008f16`
- `ntdll!NtClose` at `0x180008fcc`
- `ntdll!NtClose` at `0x180008fcc`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180008f5f`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180008f5f`

## pseudocode

```c
__int64 __fastcall BdeCfgpGetVolumeNameFromSymbolicLink(PCWSTR SourceString, unsigned __int64 a2, unsigned __int16 *a3)
{
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  void *SymbolicLinkHandle; // [rsp+40h] [rbp-C0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[528]; // [rsp+80h] [rbp-80h] BYREF

  SymbolicLinkHandle = (void *)-1LL;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  memset_0(v13, 0, 0x208u);
  if ( !SourceString || !a3 )
    return 2147500035LL;
  memset_0(a3, 0, 2 * a2);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x20001u, &ObjectAttributes);
  v7 = v6;
  if ( v6 == -1073741772 || v6 == -1073741766 )
    goto LABEL_10;
  if ( !v6 )
  {
    DestinationString.Buffer = (PWSTR)v13;
    *(_DWORD *)&DestinationString.Length = 34078720;
    v7 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &DestinationString, 0);
    if ( v7 >= 0 )
    {
      DestinationString.Buffer[DestinationString.Length] = 0;
      if ( !_wcsnicmp(DestinationString.Buffer, L"\\Device\\HarddiskVolume", 0x16u) )
      {
        v8 = StringCchPrintfW(a3, a2, L"%s%s", L"\\\\?\\GLOBALROOT", DestinationString.Buffer);
        goto LABEL_11;
      }
LABEL_10:
      v8 = -1063256034;
      goto LABEL_11;
    }
  }
  v8 = v7 | 0x10000000;
LABEL_11:
  if ( SymbolicLinkHandle != (void *)-1LL )
    NtClose(SymbolicLinkHandle);
  return v8;
}

```

## disassembly

```asm
0x180008e4c  push    rbp
0x180008e4e  push    rbx
0x180008e4f  push    rsi
0x180008e50  push    rdi
0x180008e51  push    r14
0x180008e53  lea     rbp, [rsp-1A0h]
0x180008e5b  sub     rsp, 2A0h
0x180008e62  mov     rax, cs:__security_cookie
0x180008e69  xor     rax, rsp
0x180008e6c  mov     [rbp+1C0h+var_30], rax
0x180008e73  xorps   xmm0, xmm0
0x180008e76  mov     [rsp+2C0h+SymbolicLinkHandle], 0FFFFFFFFFFFFFFFFh
0x180008e7f  mov     rdi, r8
0x180008e82  mov     rsi, rdx
0x180008e85  mov     rbx, rcx
0x180008e88  xor     edx, edx; Val
0x180008e8a  mov     r8d, 208h; Size
0x180008e90  lea     rcx, [rbp+1C0h+var_240]; void *
0x180008e94  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x180008e99  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x180008e9e  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008ea3  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x180008ea8  call    memset_0
0x180008ead  test    rbx, rbx
0x180008eb0  jz      loc_180008FD6
0x180008eb6  test    rdi, rdi
0x180008eb9  jz      loc_180008FD6
0x180008ebf  lea     r8, [rsi+rsi]; Size
0x180008ec3  xor     edx, edx; Val
0x180008ec5  mov     rcx, rdi; void *
0x180008ec8  call    memset_0
0x180008ecd  mov     rdx, rbx; SourceString
0x180008ed0  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x180008ed5  call    cs:__imp_RtlInitUnicodeString
0x180008edb  lea     rax, [rsp+2C0h+DestinationString]
0x180008ee0  mov     [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x180008ee8  xorps   xmm0, xmm0
0x180008eeb  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x180008ef0  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x180008ef5  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], 0
0x180008efe  mov     edx, 20001h; DesiredAccess
0x180008f03  mov     [rsp+2C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180008f0b  lea     rcx, [rsp+2C0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180008f10  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008f16  call    cs:__imp_NtOpenSymbolicLinkObject
0x180008f1c  mov     ebx, eax
0x180008f1e  cmp     eax, 0C0000034h
0x180008f23  jz      loc_180008FBC
0x180008f29  cmp     eax, 0C000003Ah
0x180008f2e  jz      loc_180008FBC
0x180008f34  test    eax, eax
0x180008f36  jz      short loc_180008F41
0x180008f38  bts     ebx, 1Ch
0x180008f3c  jmp     loc_180008FC1
0x180008f41  mov     rcx, [rsp+2C0h+SymbolicLinkHandle]; SymLinkObjHandle
0x180008f46  lea     rax, [rbp+1C0h+var_240]
0x180008f4a  xor     r8d, r8d; DataWritten
0x180008f4d  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x180008f52  lea     rdx, [rsp+2C0h+DestinationString]; LinkTarget
0x180008f57  mov     dword ptr [rsp+2C0h+DestinationString.Length], 2080000h
0x180008f5f  call    cs:__imp_NtQuerySymbolicLinkObject
0x180008f65  mov     ebx, eax
0x180008f67  test    eax, eax
0x180008f69  js      short loc_180008F38
0x180008f6b  movzx   edx, [rsp+2C0h+DestinationString.Length]
0x180008f70  xor     ecx, ecx
0x180008f72  mov     rax, [rsp+2C0h+DestinationString.Buffer]
0x180008f77  lea     r8d, [rcx+16h]; MaxCount
0x180008f7b  mov     [rax+rdx*2], cx
0x180008f7f  lea     rdx, aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x180008f86  mov     rcx, [rsp+2C0h+DestinationString.Buffer]; String1
0x180008f8b  call    cs:__imp__wcsnicmp
0x180008f91  test    eax, eax
0x180008f93  jnz     short loc_180008FBC
0x180008f95  mov     rax, [rsp+2C0h+DestinationString.Buffer]
0x180008f9a  lea     r9, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180008fa1  lea     r8, aSS; "%s%s"
0x180008fa8  mov     [rsp+2C0h+var_2A0], rax
0x180008fad  mov     rdx, rsi; unsigned __int64
0x180008fb0  mov     rcx, rdi; unsigned __int16 *
0x180008fb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008fb8  mov     ebx, eax
0x180008fba  jmp     short loc_180008FC1
0x180008fbc  mov     ebx, 0C0A0001Eh
0x180008fc1  mov     rcx, [rsp+2C0h+SymbolicLinkHandle]; Handle
0x180008fc6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008fca  jz      short loc_180008FD2
0x180008fcc  call    cs:__imp_NtClose
0x180008fd2  mov     eax, ebx
0x180008fd4  jmp     short loc_180008FDB
0x180008fd6  mov     eax, 80004003h
0x180008fdb  mov     rcx, [rbp+1C0h+var_30]
0x180008fe2  xor     rcx, rsp; StackCookie
0x180008fe5  call    __security_check_cookie
0x180008fea  add     rsp, 2A0h
0x180008ff1  pop     r14
0x180008ff3  pop     rdi
0x180008ff4  pop     rsi
0x180008ff5  pop     rbx
0x180008ff6  pop     rbp
0x180008ff7  retn
```

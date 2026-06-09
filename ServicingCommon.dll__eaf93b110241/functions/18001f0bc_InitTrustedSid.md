# InitTrustedSid

- ea: `0x18001f0bc`
- end: `0x18001f192`
- name: `InitTrustedSid`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800105f4`

## callees

- `0x18001f0bc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001f178`
- `KERNEL32!SetLastError` at `0x18001f178`
- `KERNEL32!LocalFree` at `0x18001f14f`
- `KERNEL32!LocalFree` at `0x18001f14f`
- `KERNEL32!LocalAlloc` at `0x18001f114`
- `KERNEL32!LocalAlloc` at `0x18001f114`
- `ntdll!RtlCreateServiceSid` at `0x18001f0f9`
- `ntdll!RtlCreateServiceSid` at `0x18001f135`
- `ntdll!RtlCreateServiceSid` at `0x18001f0f9`
- `ntdll!RtlCreateServiceSid` at `0x18001f135`
- `ntdll!RtlInitUnicodeString` at `0x18001f0e1`
- `ntdll!RtlInitUnicodeString` at `0x18001f0e1`
- `ntdll!RtlNtStatusToDosError` at `0x18001f16a`
- `ntdll!RtlNtStatusToDosError` at `0x18001f16a`

## string_xrefs

- `0x18001f0d2`: `TrustedInstaller`

## pseudocode

```c
void *InitTrustedSid()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  HLOCAL v2; // rax
  void *v3; // rdi
  DWORD v5; // eax
  struct _UNICODE_STRING ServiceName; // [rsp+20h] [rbp-18h] BYREF
  ULONG ServiceSidLength; // [rsp+40h] [rbp+8h] BYREF

  ServiceSidLength = 0;
  ServiceName = 0;
  RtlInitUnicodeString(&ServiceName, L"TrustedInstaller");
  v0 = RtlCreateServiceSid(&ServiceName, 0, &ServiceSidLength);
  v1 = v0;
  if ( v0 == -1073741789 )
  {
    v2 = LocalAlloc(0, ServiceSidLength);
    v3 = v2;
    if ( v2 )
    {
      v1 = RtlCreateServiceSid(&ServiceName, v2, &ServiceSidLength);
      if ( v1 >= 0 )
        return v3;
      LocalFree(v3);
    }
    else
    {
      v1 = -1073741801;
    }
    goto LABEL_8;
  }
  if ( v0 < 0 )
  {
LABEL_8:
    v5 = RtlNtStatusToDosError(v1);
    SetLastError(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f0bc  mov     rax, rsp
0x18001f0bf  mov     [rax+10h], rbx
0x18001f0c3  push    rdi
0x18001f0c4  sub     rsp, 30h
0x18001f0c8  xorps   xmm0, xmm0
0x18001f0cb  mov     dword ptr [rax+8], 0
0x18001f0d2  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x18001f0d9  lea     rcx, [rax-18h]; DestinationString
0x18001f0dd  movups  xmmword ptr [rax-18h], xmm0
0x18001f0e1  call    cs:__imp_RtlInitUnicodeString
0x18001f0e8  nop     dword ptr [rax+rax+00h]
0x18001f0ed  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x18001f0f2  xor     edx, edx; ServiceSid
0x18001f0f4  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x18001f0f9  call    cs:__imp_RtlCreateServiceSid
0x18001f100  nop     dword ptr [rax+rax+00h]
0x18001f105  mov     ebx, eax
0x18001f107  cmp     eax, 0C0000023h
0x18001f10c  jnz     short loc_18001F164
0x18001f10e  mov     edx, [rsp+38h+ServiceSidLength]; uBytes
0x18001f112  xor     ecx, ecx; uFlags
0x18001f114  call    cs:__imp_LocalAlloc
0x18001f11b  nop     dword ptr [rax+rax+00h]
0x18001f120  mov     rdi, rax
0x18001f123  test    rax, rax
0x18001f126  jz      short loc_18001F15D
0x18001f128  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x18001f12d  mov     rdx, rax; ServiceSid
0x18001f130  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x18001f135  call    cs:__imp_RtlCreateServiceSid
0x18001f13c  nop     dword ptr [rax+rax+00h]
0x18001f141  mov     ebx, eax
0x18001f143  test    eax, eax
0x18001f145  js      short loc_18001F14C
0x18001f147  mov     rax, rdi
0x18001f14a  jmp     short loc_18001F186
0x18001f14c  mov     rcx, rdi; hMem
0x18001f14f  call    cs:__imp_LocalFree
0x18001f156  nop     dword ptr [rax+rax+00h]
0x18001f15b  jmp     short loc_18001F168
0x18001f15d  mov     ebx, 0C0000017h
0x18001f162  jmp     short loc_18001F168
0x18001f164  test    eax, eax
0x18001f166  jns     short loc_18001F184
0x18001f168  mov     ecx, ebx; Status
0x18001f16a  call    cs:__imp_RtlNtStatusToDosError
0x18001f171  nop     dword ptr [rax+rax+00h]
0x18001f176  mov     ecx, eax; dwErrCode
0x18001f178  call    cs:__imp_SetLastError
0x18001f17f  nop     dword ptr [rax+rax+00h]
0x18001f184  xor     eax, eax
0x18001f186  mov     rbx, [rsp+38h+arg_8]
0x18001f18b  add     rsp, 30h
0x18001f18f  pop     rdi
0x18001f190  retn
```

# InitTrustedSid

- ea: `0x18002125c`
- end: `0x180021332`
- name: `InitTrustedSid`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18001abd8`

## callees

- `0x18002125c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180021318`
- `KERNEL32!SetLastError` at `0x180021318`
- `KERNEL32!LocalFree` at `0x1800212ef`
- `KERNEL32!LocalFree` at `0x1800212ef`
- `KERNEL32!LocalAlloc` at `0x1800212b4`
- `KERNEL32!LocalAlloc` at `0x1800212b4`
- `ntdll!RtlCreateServiceSid` at `0x180021299`
- `ntdll!RtlCreateServiceSid` at `0x1800212d5`
- `ntdll!RtlCreateServiceSid` at `0x180021299`
- `ntdll!RtlCreateServiceSid` at `0x1800212d5`
- `ntdll!RtlNtStatusToDosError` at `0x18002130a`
- `ntdll!RtlNtStatusToDosError` at `0x18002130a`
- `ntdll!RtlInitUnicodeString` at `0x180021281`
- `ntdll!RtlInitUnicodeString` at `0x180021281`

## string_xrefs

- `0x180021272`: `TrustedInstaller`

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
0x18002125c  mov     rax, rsp
0x18002125f  mov     [rax+10h], rbx
0x180021263  push    rdi
0x180021264  sub     rsp, 30h
0x180021268  xorps   xmm0, xmm0
0x18002126b  mov     dword ptr [rax+8], 0
0x180021272  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x180021279  lea     rcx, [rax-18h]; DestinationString
0x18002127d  movups  xmmword ptr [rax-18h], xmm0
0x180021281  call    cs:__imp_RtlInitUnicodeString
0x180021288  nop     dword ptr [rax+rax+00h]
0x18002128d  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x180021292  xor     edx, edx; ServiceSid
0x180021294  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x180021299  call    cs:__imp_RtlCreateServiceSid
0x1800212a0  nop     dword ptr [rax+rax+00h]
0x1800212a5  mov     ebx, eax
0x1800212a7  cmp     eax, 0C0000023h
0x1800212ac  jnz     short loc_180021304
0x1800212ae  mov     edx, [rsp+38h+ServiceSidLength]; uBytes
0x1800212b2  xor     ecx, ecx; uFlags
0x1800212b4  call    cs:__imp_LocalAlloc
0x1800212bb  nop     dword ptr [rax+rax+00h]
0x1800212c0  mov     rdi, rax
0x1800212c3  test    rax, rax
0x1800212c6  jz      short loc_1800212FD
0x1800212c8  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x1800212cd  mov     rdx, rax; ServiceSid
0x1800212d0  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x1800212d5  call    cs:__imp_RtlCreateServiceSid
0x1800212dc  nop     dword ptr [rax+rax+00h]
0x1800212e1  mov     ebx, eax
0x1800212e3  test    eax, eax
0x1800212e5  js      short loc_1800212EC
0x1800212e7  mov     rax, rdi
0x1800212ea  jmp     short loc_180021326
0x1800212ec  mov     rcx, rdi; hMem
0x1800212ef  call    cs:__imp_LocalFree
0x1800212f6  nop     dword ptr [rax+rax+00h]
0x1800212fb  jmp     short loc_180021308
0x1800212fd  mov     ebx, 0C0000017h
0x180021302  jmp     short loc_180021308
0x180021304  test    eax, eax
0x180021306  jns     short loc_180021324
0x180021308  mov     ecx, ebx; Status
0x18002130a  call    cs:__imp_RtlNtStatusToDosError
0x180021311  nop     dword ptr [rax+rax+00h]
0x180021316  mov     ecx, eax; dwErrCode
0x180021318  call    cs:__imp_SetLastError
0x18002131f  nop     dword ptr [rax+rax+00h]
0x180021324  xor     eax, eax
0x180021326  mov     rbx, [rsp+38h+arg_8]
0x18002132b  add     rsp, 30h
0x18002132f  pop     rdi
0x180021330  retn
```

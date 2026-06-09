# SeUtilsGetTrustedInstallSid

- ea: `0x180007afc`
- end: `0x180007bbe`
- name: `SeUtilsGetTrustedInstallSid`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180007a20`

## callees

- `0x180007afc`

## import_xrefs

- `ntdll!RtlLengthRequiredSid` at `0x180007b22`
- `ntdll!RtlLengthRequiredSid` at `0x180007b22`
- `ntdll!RtlCreateServiceSid` at `0x180007b75`
- `ntdll!RtlCreateServiceSid` at `0x180007b75`
- `ntdll!RtlFreeHeap` at `0x180007b98`
- `ntdll!RtlFreeHeap` at `0x180007b98`
- `ntdll!RtlAllocateHeap` at `0x180007b42`
- `ntdll!RtlAllocateHeap` at `0x180007b42`
- `ntdll!RtlInitUnicodeStringEx` at `0x180007b5c`
- `ntdll!RtlInitUnicodeStringEx` at `0x180007b5c`

## string_xrefs

- `0x180007b50`: `TrustedInstaller`

## pseudocode

```c
__int64 __fastcall SeUtilsGetTrustedInstallSid(_QWORD *a1)
{
  PVOID Heap; // rdi
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  ULONG ServiceSidLength; // [rsp+48h] [rbp+10h] BYREF

  ServiceSidLength = 0;
  DestinationString = 0;
  ServiceSidLength = RtlLengthRequiredSid(6u);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ServiceSidLength);
  if ( Heap )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, L"TrustedInstaller");
    if ( inited < 0 || (inited = RtlCreateServiceSid(&DestinationString, Heap, &ServiceSidLength), inited < 0) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      *a1 = 0;
    }
    else
    {
      *a1 = Heap;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180007afc  mov     rax, rsp
0x180007aff  mov     [rax+8], rbx
0x180007b03  mov     [rax+18h], rsi
0x180007b07  push    rdi
0x180007b08  sub     rsp, 30h
0x180007b0c  mov     rsi, rcx
0x180007b0f  mov     dword ptr [rax+10h], 0
0x180007b16  xorps   xmm0, xmm0
0x180007b19  mov     ecx, 6; SubAuthorityCount
0x180007b1e  movups  xmmword ptr [rax-18h], xmm0
0x180007b22  call    cs:__imp_RtlLengthRequiredSid
0x180007b28  mov     r8d, eax; Size
0x180007b2b  mov     edx, 8; Flags
0x180007b30  mov     [rsp+38h+ServiceSidLength], r8d
0x180007b35  mov     rcx, gs:60h
0x180007b3e  mov     rcx, [rcx+30h]; HeapHandle
0x180007b42  call    cs:__imp_RtlAllocateHeap
0x180007b48  mov     rdi, rax
0x180007b4b  test    rax, rax
0x180007b4e  jz      short loc_180007BB7
0x180007b50  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x180007b57  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180007b5c  call    cs:__imp_RtlInitUnicodeStringEx
0x180007b62  mov     ebx, eax
0x180007b64  test    eax, eax
0x180007b66  js      short loc_180007B86
0x180007b68  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x180007b6d  mov     rdx, rdi; ServiceSid
0x180007b70  lea     rcx, [rsp+38h+DestinationString]; ServiceName
0x180007b75  call    cs:__imp_RtlCreateServiceSid
0x180007b7b  mov     ebx, eax
0x180007b7d  test    eax, eax
0x180007b7f  js      short loc_180007B86
0x180007b81  mov     [rsi], rdi
0x180007b84  jmp     short loc_180007BA5
0x180007b86  mov     rcx, gs:60h
0x180007b8f  mov     r8, rdi; P
0x180007b92  xor     edx, edx; Flags
0x180007b94  mov     rcx, [rcx+30h]; HeapHandle
0x180007b98  call    cs:__imp_RtlFreeHeap
0x180007b9e  mov     qword ptr [rsi], 0
0x180007ba5  mov     rsi, [rsp+38h+arg_10]
0x180007baa  mov     eax, ebx
0x180007bac  mov     rbx, [rsp+38h+arg_0]
0x180007bb1  add     rsp, 30h
0x180007bb5  pop     rdi
0x180007bb6  retn
0x180007bb7  mov     ebx, 0C0000017h
0x180007bbc  jmp     short loc_180007BA5
```

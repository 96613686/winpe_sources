# UnionFs::UfsFsContext::~UfsFsContext(void)

- ea: `0x140057a3c`
- end: `0x140057b38`
- name: `??1UfsFsContext@UnionFs@@QEAA@XZ`
- size: `252`
- prototype: `void __fastcall(PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008a70`
- `0x140057c38`

## callees

- `0x140010148`
- `0x140057a3c`
- `0x14005a2e0`

## import_xrefs

- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057af1`
- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057af1`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140057a5b`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140057a5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057aaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ace`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057b1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057aaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ace`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057b1b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057b0a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057b0a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140057a6a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140057a6a`

## pseudocode

```c
void __fastcall UnionFs::UfsFsContext::~UfsFsContext(PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader)
{
  struct _ERESOURCE **v2; // rbx
  PERESOURCE *p_Resource; // rsi
  struct _ERESOURCE **v4; // rax
  struct _ERESOURCE *v5; // rcx
  struct _ERESOURCE **v6; // rcx
  LARGE_INTEGER ValidDataLength; // rcx
  LARGE_INTEGER FileSize; // rbx

  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
    FsRtlUninitializeOplock((POPLOCK)&AdvancedHeader[1]);
  FsRtlTeardownPerStreamContexts(AdvancedHeader);
  Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline();
  v2 = 0;
  p_Resource = &AdvancedHeader[2].Resource;
  while ( 1 )
  {
    v4 = (struct _ERESOURCE **)*p_Resource;
    if ( *p_Resource == (PERESOURCE)p_Resource )
      break;
    if ( v4[1] != (struct _ERESOURCE *)p_Resource
      || (v5 = *v4, (struct _ERESOURCE **)(*v4)->SystemResourcesList.Blink != v4) )
    {
      __fastfail(3u);
    }
    *p_Resource = v5;
    v5->SystemResourcesList.Blink = (struct _LIST_ENTRY *)p_Resource;
    v6 = v2;
    v2 = v4;
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  ValidDataLength = AdvancedHeader[1].ValidDataLength;
  AdvancedHeader[1].ValidDataLength.QuadPart = 0;
  if ( ValidDataLength.QuadPart )
    ((void (__fastcall *)(_QWORD))FsRtlFreeAePushLock)((LARGE_INTEGER)ValidDataLength.QuadPart);
  FileSize = AdvancedHeader[1].FileSize;
  if ( FileSize.QuadPart )
  {
    ExDeleteResourceLite((PERESOURCE)(FileSize.QuadPart + 56));
    ExFreePoolWithTag((PVOID)FileSize.QuadPart, 0);
  }
}

```

## disassembly

```asm
0x140057a3c  mov     [rsp+arg_0], rbx
0x140057a41  mov     [rsp+arg_8], rsi
0x140057a46  push    rdi
0x140057a47  sub     rsp, 20h
0x140057a4b  mov     rdi, rcx
0x140057a4e  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140057a53  test    eax, eax
0x140057a55  jz      short loc_140057A67
0x140057a57  lea     rcx, [rdi+58h]; Oplock
0x140057a5b  call    cs:__imp_FsRtlUninitializeOplock
0x140057a62  nop     dword ptr [rax+rax+00h]
0x140057a67  mov     rcx, rdi; AdvancedHeader
0x140057a6a  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140057a71  nop     dword ptr [rax+rax+00h]
0x140057a76  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140057a7b  xor     ebx, ebx
0x140057a7d  lea     rsi, [rdi+0B8h]
0x140057a84  mov     rax, [rsi]
0x140057a87  cmp     rax, rsi
0x140057a8a  jz      short loc_140057AC4
0x140057a8c  cmp     [rax+8], rsi
0x140057a90  jnz     short loc_140057ABD
0x140057a92  mov     rcx, [rax]
0x140057a95  cmp     [rcx+8], rax
0x140057a99  jnz     short loc_140057ABD
0x140057a9b  mov     [rsi], rcx
0x140057a9e  mov     [rcx+8], rsi
0x140057aa2  mov     rcx, rbx; P
0x140057aa5  mov     rbx, rax
0x140057aa8  test    rcx, rcx
0x140057aab  jz      short loc_140057A84
0x140057aad  xor     edx, edx; Tag
0x140057aaf  call    cs:__imp_ExFreePoolWithTag
0x140057ab6  nop     dword ptr [rax+rax+00h]
0x140057abb  jmp     short loc_140057A84
0x140057abd  mov     ecx, 3
0x140057ac2  int     29h; Win8: RtlFailFast(ecx)
0x140057ac4  test    rbx, rbx
0x140057ac7  jz      short loc_140057ADA
0x140057ac9  xor     edx, edx; Tag
0x140057acb  mov     rcx, rbx; P
0x140057ace  call    cs:__imp_ExFreePoolWithTag
0x140057ad5  nop     dword ptr [rax+rax+00h]
0x140057ada  mov     rcx, [rdi+80h]
0x140057ae1  mov     qword ptr [rdi+80h], 0
0x140057aec  test    rcx, rcx
0x140057aef  jz      short loc_140057AFD
0x140057af1  call    cs:__imp_FsRtlFreeAePushLock
0x140057af8  nop     dword ptr [rax+rax+00h]
0x140057afd  mov     rbx, [rdi+78h]
0x140057b01  test    rbx, rbx
0x140057b04  jz      short loc_140057B27
0x140057b06  lea     rcx, [rbx+38h]; Resource
0x140057b0a  call    cs:__imp_ExDeleteResourceLite
0x140057b11  nop     dword ptr [rax+rax+00h]
0x140057b16  xor     edx, edx; Tag
0x140057b18  mov     rcx, rbx; P
0x140057b1b  call    cs:__imp_ExFreePoolWithTag
0x140057b22  nop     dword ptr [rax+rax+00h]
0x140057b27  mov     rbx, [rsp+28h+arg_0]
0x140057b2c  mov     rsi, [rsp+28h+arg_8]
0x140057b31  add     rsp, 20h
0x140057b35  pop     rdi
0x140057b36  retn
```

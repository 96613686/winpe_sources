# UnionFs::UfsFsContext::~UfsFsContext(void)

- ea: `0x140057bbc`
- end: `0x140057cb8`
- name: `??1UfsFsContext@UnionFs@@QEAA@XZ`
- size: `252`
- prototype: `void __fastcall(PFSRTL_ADVANCED_FCB_HEADER AdvancedHeader)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008a40`
- `0x140057db8`

## callees

- `0x140010168`
- `0x140057bbc`
- `0x14005a460`

## import_xrefs

- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057c71`
- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057c71`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140057bdb`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140057bdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c9b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057c8a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057c8a`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140057bea`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140057bea`

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
0x140057bbc  mov     [rsp+arg_0], rbx
0x140057bc1  mov     [rsp+arg_8], rsi
0x140057bc6  push    rdi
0x140057bc7  sub     rsp, 20h
0x140057bcb  mov     rdi, rcx
0x140057bce  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140057bd3  test    eax, eax
0x140057bd5  jz      short loc_140057BE7
0x140057bd7  lea     rcx, [rdi+58h]; Oplock
0x140057bdb  call    cs:__imp_FsRtlUninitializeOplock
0x140057be2  nop     dword ptr [rax+rax+00h]
0x140057be7  mov     rcx, rdi; AdvancedHeader
0x140057bea  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140057bf1  nop     dword ptr [rax+rax+00h]
0x140057bf6  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x140057bfb  xor     ebx, ebx
0x140057bfd  lea     rsi, [rdi+0B8h]
0x140057c04  mov     rax, [rsi]
0x140057c07  cmp     rax, rsi
0x140057c0a  jz      short loc_140057C44
0x140057c0c  cmp     [rax+8], rsi
0x140057c10  jnz     short loc_140057C3D
0x140057c12  mov     rcx, [rax]
0x140057c15  cmp     [rcx+8], rax
0x140057c19  jnz     short loc_140057C3D
0x140057c1b  mov     [rsi], rcx
0x140057c1e  mov     [rcx+8], rsi
0x140057c22  mov     rcx, rbx; P
0x140057c25  mov     rbx, rax
0x140057c28  test    rcx, rcx
0x140057c2b  jz      short loc_140057C04
0x140057c2d  xor     edx, edx; Tag
0x140057c2f  call    cs:__imp_ExFreePoolWithTag
0x140057c36  nop     dword ptr [rax+rax+00h]
0x140057c3b  jmp     short loc_140057C04
0x140057c3d  mov     ecx, 3
0x140057c42  int     29h; Win8: RtlFailFast(ecx)
0x140057c44  test    rbx, rbx
0x140057c47  jz      short loc_140057C5A
0x140057c49  xor     edx, edx; Tag
0x140057c4b  mov     rcx, rbx; P
0x140057c4e  call    cs:__imp_ExFreePoolWithTag
0x140057c55  nop     dword ptr [rax+rax+00h]
0x140057c5a  mov     rcx, [rdi+80h]
0x140057c61  mov     qword ptr [rdi+80h], 0
0x140057c6c  test    rcx, rcx
0x140057c6f  jz      short loc_140057C7D
0x140057c71  call    cs:__imp_FsRtlFreeAePushLock
0x140057c78  nop     dword ptr [rax+rax+00h]
0x140057c7d  mov     rbx, [rdi+78h]
0x140057c81  test    rbx, rbx
0x140057c84  jz      short loc_140057CA7
0x140057c86  lea     rcx, [rbx+38h]; Resource
0x140057c8a  call    cs:__imp_ExDeleteResourceLite
0x140057c91  nop     dword ptr [rax+rax+00h]
0x140057c96  xor     edx, edx; Tag
0x140057c98  mov     rcx, rbx; P
0x140057c9b  call    cs:__imp_ExFreePoolWithTag
0x140057ca2  nop     dword ptr [rax+rax+00h]
0x140057ca7  mov     rbx, [rsp+28h+arg_0]
0x140057cac  mov     rsi, [rsp+28h+arg_8]
0x140057cb1  add     rsp, 20h
0x140057cb5  pop     rdi
0x140057cb6  retn
```

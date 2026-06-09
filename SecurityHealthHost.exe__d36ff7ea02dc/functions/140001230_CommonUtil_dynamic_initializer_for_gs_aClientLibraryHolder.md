# CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__

- ea: `0x140001230`
- end: `0x1400012a2`
- name: `CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__`
- size: `114`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001230`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x140001271`
- `KERNEL32!EncodePointer` at `0x140001285`
- `KERNEL32!EncodePointer` at `0x140001271`
- `KERNEL32!EncodePointer` at `0x140001285`

## pseudocode

```c
void CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__()
{
  if ( !byte_140019194 )
  {
    qword_140018D28 = (__int64)&off_140018128;
    qword_140018D30 = (__int64)off_140018130[0];
    *off_140018130[0] = &qword_140018D28;
    off_140018130[0] = (_UNKNOWN **)&qword_140018D28;
    qword_140018D38 = (__int64)EncodePointer(CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize);
    qword_140018D40 = (__int64)EncodePointer(CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy);
  }
  xmmword_140018D50 = 0;
}

```

## disassembly

```asm
0x140001230  sub     rsp, 28h
0x140001234  cmp     cs:byte_140019194, 0
0x14000123b  jnz     short loc_140001292
0x14000123d  mov     rax, cs:off_140018130
0x140001244  lea     rcx, off_140018128
0x14000124b  mov     cs:qword_140018D28, rcx
0x140001252  lea     rcx, qword_140018D28
0x140001259  mov     cs:qword_140018D30, rax
0x140001260  mov     [rax], rcx
0x140001263  mov     cs:off_140018130, rcx
0x14000126a  lea     rcx, ?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z; Ptr
0x140001271  call    cs:__imp_EncodePointer
0x140001277  lea     rcx, ?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z; Ptr
0x14000127e  mov     cs:qword_140018D38, rax
0x140001285  call    cs:__imp_EncodePointer
0x14000128b  mov     cs:qword_140018D40, rax
0x140001292  xorps   xmm0, xmm0
0x140001295  movdqa  cs:xmmword_140018D50, xmm0
0x14000129d  add     rsp, 28h
0x1400012a1  retn
```

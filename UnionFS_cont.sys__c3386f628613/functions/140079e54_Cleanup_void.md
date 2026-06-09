# Cleanup(void)

- ea: `0x140079e54`
- end: `0x140079f28`
- name: `?Cleanup@@YAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f490`
- `0x140079f30`
- `0x140079f58`

## callees

- `0x140079e54`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140079eb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079eb0`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140079ef4`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140079ef4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140079ed1`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140079ed1`

## pseudocode

```c
void Cleanup(void)
{
  _QWORD *v0; // rbx
  __int64 v1; // rax
  void (*v2)(void); // rax

  if ( !byte_14009E398 )
  {
    while ( 1 )
    {
      v0 = exitList;
      if ( exitList == &exitList )
        break;
      if ( *((PVOID **)exitList + 1) != &exitList
        || (v1 = *(_QWORD *)exitList, *(PVOID *)(*(_QWORD *)exitList + 8LL) != exitList) )
      {
        __fastfail(3u);
      }
      exitList = *(PVOID *)exitList;
      *(_QWORD *)(v1 + 8) = &exitList;
      v2 = (void (*)(void))v0[2];
      if ( v2 )
        v2();
      if ( v0 )
        ExFreePoolWithTag(v0, 0);
    }
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
    byte_14009E398 = 1;
  }
}

```

## disassembly

```asm
0x140079e54  mov     [rsp+arg_0], rbx
0x140079e59  push    rsi
0x140079e5a  sub     rsp, 20h
0x140079e5e  cmp     cs:byte_14009E398, 0
0x140079e65  jnz     loc_140079F1C
0x140079e6b  lea     rsi, ?exitList@@3U_LIST_ENTRY@@A; _LIST_ENTRY exitList
0x140079e72  mov     rbx, cs:?exitList@@3U_LIST_ENTRY@@A; _LIST_ENTRY exitList
0x140079e79  cmp     rbx, rsi
0x140079e7c  jz      short loc_140079EC5
0x140079e7e  cmp     [rbx+8], rsi
0x140079e82  jnz     short loc_140079EBE
0x140079e84  mov     rax, [rbx]
0x140079e87  cmp     [rax+8], rbx
0x140079e8b  jnz     short loc_140079EBE
0x140079e8d  mov     cs:?exitList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY exitList
0x140079e94  mov     [rax+8], rsi
0x140079e98  mov     rax, [rbx+10h]
0x140079e9c  test    rax, rax
0x140079e9f  jz      short loc_140079EA6
0x140079ea1  call    _guard_dispatch_icall
0x140079ea6  test    rbx, rbx
0x140079ea9  jz      short loc_140079E72
0x140079eab  xor     edx, edx; Tag
0x140079ead  mov     rcx, rbx; P
0x140079eb0  call    cs:__imp_ExFreePoolWithTag
0x140079eb7  nop     dword ptr [rax+rax+00h]
0x140079ebc  jmp     short loc_140079E72
0x140079ebe  mov     ecx, 3
0x140079ec3  int     29h; Win8: RtlFailFast(ecx)
0x140079ec5  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140079ecc  test    rcx, rcx
0x140079ecf  jz      short loc_140079EE8
0x140079ed1  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140079ed8  nop     dword ptr [rax+rax+00h]
0x140079edd  mov     cs:g_wil_details_featureChangeNotification, 0
0x140079ee8  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140079eef  test    rcx, rcx
0x140079ef2  jz      short loc_140079F0B
0x140079ef4  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140079efb  nop     dword ptr [rax+rax+00h]
0x140079f00  mov     cs:g_wil_details_featureUsageProvider, 0
0x140079f0b  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140079f15  mov     cs:byte_14009E398, 1
0x140079f1c  mov     rbx, [rsp+28h+arg_0]
0x140079f21  add     rsp, 20h
0x140079f25  pop     rsi
0x140079f26  retn
```

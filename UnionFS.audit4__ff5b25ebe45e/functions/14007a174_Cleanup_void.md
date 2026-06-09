# Cleanup(void)

- ea: `0x14007a174`
- end: `0x14007a248`
- name: `?Cleanup@@YAXXZ`
- size: `212`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f4b0`
- `0x14007a250`
- `0x14007a278`

## callees

- `0x14007a174`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1d0`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007a214`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007a214`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007a1f1`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007a1f1`

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
0x14007a174  mov     [rsp+arg_0], rbx
0x14007a179  push    rsi
0x14007a17a  sub     rsp, 20h
0x14007a17e  cmp     cs:byte_14009E398, 0
0x14007a185  jnz     loc_14007A23C
0x14007a18b  lea     rsi, ?exitList@@3U_LIST_ENTRY@@A; _LIST_ENTRY exitList
0x14007a192  mov     rbx, cs:?exitList@@3U_LIST_ENTRY@@A; _LIST_ENTRY exitList
0x14007a199  cmp     rbx, rsi
0x14007a19c  jz      short loc_14007A1E5
0x14007a19e  cmp     [rbx+8], rsi
0x14007a1a2  jnz     short loc_14007A1DE
0x14007a1a4  mov     rax, [rbx]
0x14007a1a7  cmp     [rax+8], rbx
0x14007a1ab  jnz     short loc_14007A1DE
0x14007a1ad  mov     cs:?exitList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY exitList
0x14007a1b4  mov     [rax+8], rsi
0x14007a1b8  mov     rax, [rbx+10h]
0x14007a1bc  test    rax, rax
0x14007a1bf  jz      short loc_14007A1C6
0x14007a1c1  call    _guard_dispatch_icall
0x14007a1c6  test    rbx, rbx
0x14007a1c9  jz      short loc_14007A192
0x14007a1cb  xor     edx, edx; Tag
0x14007a1cd  mov     rcx, rbx; P
0x14007a1d0  call    cs:__imp_ExFreePoolWithTag
0x14007a1d7  nop     dword ptr [rax+rax+00h]
0x14007a1dc  jmp     short loc_14007A192
0x14007a1de  mov     ecx, 3
0x14007a1e3  int     29h; Win8: RtlFailFast(ecx)
0x14007a1e5  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14007a1ec  test    rcx, rcx
0x14007a1ef  jz      short loc_14007A208
0x14007a1f1  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14007a1f8  nop     dword ptr [rax+rax+00h]
0x14007a1fd  mov     cs:g_wil_details_featureChangeNotification, 0
0x14007a208  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14007a20f  test    rcx, rcx
0x14007a212  jz      short loc_14007A22B
0x14007a214  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14007a21b  nop     dword ptr [rax+rax+00h]
0x14007a220  mov     cs:g_wil_details_featureUsageProvider, 0
0x14007a22b  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14007a235  mov     cs:byte_14009E398, 1
0x14007a23c  mov     rbx, [rsp+28h+arg_0]
0x14007a241  add     rsp, 20h
0x14007a245  pop     rsi
0x14007a246  retn
```

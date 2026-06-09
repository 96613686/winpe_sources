# BthEnumUnregisterDeviceInterface

- ea: `0x14001f1ac`
- end: `0x14001f2af`
- name: `BthEnumUnregisterDeviceInterface`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002b64`
- `0x140019058`

## callees

- `0x1400013e8`
- `0x14001f1ac`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001f1e4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001f249`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001f1e4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14001f249`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f22a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f293`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f22a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001f293`

## pseudocode

```c
__int64 __fastcall BthEnumUnregisterDeviceInterface(__int64 a1, char a2)
{
  unsigned int v2; // ebx
  struct _UNICODE_STRING *v5; // rbp
  NTSTATUS v6; // eax
  int v7; // edx
  NTSTATUS v8; // eax
  int v9; // edx
  __int64 v11; // [rsp+28h] [rbp-40h]
  NTSTATUS v12; // [rsp+28h] [rbp-40h]

  v2 = 0;
  if ( *(_QWORD *)(a1 + 2896) )
  {
    v5 = (struct _UNICODE_STRING *)(a1 + 2888);
    v6 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 2888), 0);
    v2 = v6;
    if ( v6 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = v6;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v7,
        4u,
        0xAu,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
        v12);
    }
    if ( a2 )
      RtlFreeUnicodeString(v5);
  }
  if ( *(_QWORD *)(a1 + 2912) )
  {
    v8 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 2904), 0);
    v2 = v8;
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v11) = v8;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v9,
        4u,
        0xBu,
        (__int64)WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids,
        v11);
    }
    if ( a2 )
      RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 2904));
  }
  return v2;
}

```

## disassembly

```asm
0x14001f1ac  push    rbx
0x14001f1ae  push    rbp
0x14001f1af  push    rsi
0x14001f1b0  push    rdi
0x14001f1b1  push    r12
0x14001f1b3  push    r14
0x14001f1b5  sub     rsp, 38h
0x14001f1b9  xor     ebx, ebx
0x14001f1bb  lea     r14, WPP_RECORDER_INITIALIZED
0x14001f1c2  lea     r12, WPP_3ad0aac993a937fca10a477fa33a3037_Traceguids
0x14001f1c9  mov     sil, dl
0x14001f1cc  mov     rdi, rcx
0x14001f1cf  cmp     [rcx+0B50h], rbx
0x14001f1d6  jz      short loc_14001F236
0x14001f1d8  lea     rbp, [rcx+0B48h]
0x14001f1df  xor     edx, edx; Enable
0x14001f1e1  mov     rcx, rbp; SymbolicLinkName
0x14001f1e4  call    cs:__imp_IoSetDeviceInterfaceState
0x14001f1eb  nop     dword ptr [rax+rax+00h]
0x14001f1f0  mov     ebx, eax
0x14001f1f2  test    eax, eax
0x14001f1f4  jns     short loc_14001F222
0x14001f1f6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001f1fd  jz      short loc_14001F222
0x14001f1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f206  mov     r9d, 0Ah
0x14001f20c  mov     dword ptr [rsp+68h+var_40], eax
0x14001f210  mov     [rsp+68h+var_48], r12
0x14001f215  mov     rcx, [rcx+40h]
0x14001f219  lea     r8d, [r9-6]
0x14001f21d  call    WPP_RECORDER_SF_d
0x14001f222  test    sil, sil
0x14001f225  jz      short loc_14001F236
0x14001f227  mov     rcx, rbp; UnicodeString
0x14001f22a  call    cs:__imp_RtlFreeUnicodeString
0x14001f231  nop     dword ptr [rax+rax+00h]
0x14001f236  cmp     qword ptr [rdi+0B60h], 0
0x14001f23e  jz      short loc_14001F29F
0x14001f240  xor     edx, edx; Enable
0x14001f242  lea     rcx, [rdi+0B58h]; SymbolicLinkName
0x14001f249  call    cs:__imp_IoSetDeviceInterfaceState
0x14001f250  nop     dword ptr [rax+rax+00h]
0x14001f255  mov     ebx, eax
0x14001f257  test    eax, eax
0x14001f259  jns     short loc_14001F287
0x14001f25b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001f262  jz      short loc_14001F287
0x14001f264  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f26b  mov     r9d, 0Bh
0x14001f271  mov     dword ptr [rsp+68h+var_40], eax
0x14001f275  mov     [rsp+68h+var_48], r12
0x14001f27a  mov     rcx, [rcx+40h]
0x14001f27e  lea     r8d, [r9-7]
0x14001f282  call    WPP_RECORDER_SF_d
0x14001f287  test    sil, sil
0x14001f28a  jz      short loc_14001F29F
0x14001f28c  lea     rcx, [rdi+0B58h]; UnicodeString
0x14001f293  call    cs:__imp_RtlFreeUnicodeString
0x14001f29a  nop     dword ptr [rax+rax+00h]
0x14001f29f  mov     eax, ebx
0x14001f2a1  add     rsp, 38h
0x14001f2a5  pop     r14
0x14001f2a7  pop     r12
0x14001f2a9  pop     rdi
0x14001f2aa  pop     rsi
0x14001f2ab  pop     rbp
0x14001f2ac  pop     rbx
0x14001f2ad  retn
```

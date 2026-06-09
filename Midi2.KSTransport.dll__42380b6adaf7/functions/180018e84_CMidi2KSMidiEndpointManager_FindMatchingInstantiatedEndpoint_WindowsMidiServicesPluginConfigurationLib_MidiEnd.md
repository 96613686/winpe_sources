# CMidi2KSMidiEndpointManager::FindMatchingInstantiatedEndpoint(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria &)

- ea: `0x180018e84`
- end: `0x180019061`
- name: `?FindMatchingInstantiatedEndpoint@CMidi2KSMidiEndpointManager@@QEAA?AUhstring@winrt@@AEAVMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@Z`
- size: `477`
- prototype: `struct winrt::hstring __high(struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180023ac0`

## callees

- `0x18000526c`
- `0x180014864`
- `0x180018260`
- `0x180018778`
- `0x180018e84`
- `0x18002cccc`
- `0x18002cf5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CMidi2KSMidiEndpointManager::FindMatchingInstantiatedEndpoint(
        __int64 a1,
        _QWORD *a2,
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  struct winrt::impl::hstring_header *v18; // rdx
  winrt::impl *v20[2]; // [rsp+20h] [rbp-79h] BYREF
  int v21; // [rsp+30h] [rbp-69h]
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  __int128 v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+50h] [rbp-49h]
  __int16 v25; // [rsp+58h] [rbp-41h]
  __int128 v26; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v27[2]; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v28[2]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v29[2]; // [rsp+98h] [rbp-1h] BYREF
  _QWORD v30[2]; // [rsp+A8h] [rbp+Fh] BYREF
  _QWORD v31[7]; // [rsp+B8h] [rbp+1Fh] BYREF

  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(a3);
  v6 = *(__int64 **)(a1 + 32);
  v7 = *(__int64 **)(a1 + 40);
  while ( 1 )
  {
    if ( v6 == v7 )
    {
      *a2 = 0;
      return a2;
    }
    memset_0(v20, 0, 0x50u);
    v20[0] = 0;
    v20[1] = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0u;
    v24 = 0;
    v25 = 0;
    v26 = 0u;
    v8 = *v6;
    if ( *(_QWORD *)(*v6 + 56) <= 7u )
      v9 = v8 + 32;
    else
      v9 = *(_QWORD *)(v8 + 32);
    v27[0] = v9;
    v27[1] = *(_QWORD *)(v8 + 48);
    winrt::hstring::operator=(&v20[1], v27);
    v10 = *v6;
    if ( *(_QWORD *)(*v6 + 320) <= 7u )
      v11 = v10 + 296;
    else
      v11 = *(_QWORD *)(v10 + 296);
    v28[0] = v11;
    v28[1] = *(_QWORD *)(v10 + 312);
    winrt::hstring::operator=(v20, v28);
    v12 = (_QWORD *)*v6;
    v21 = *(_DWORD *)(*v6 + 288);
    v13 = v12 + 28;
    if ( v12[31] > 7u )
      v13 = (_QWORD *)*v13;
    v29[0] = v13;
    v29[1] = v12[30];
    winrt::hstring::operator=(&v22, v29);
    v14 = *v6;
    v15 = *(_QWORD *)(*v6 + 120) <= 7u ? v14 + 96 : *(_QWORD *)(v14 + 96);
    v30[0] = v15;
    v30[1] = *(_QWORD *)(v14 + 112);
    winrt::hstring::operator=(&v26, v30);
    v16 = *v6;
    v17 = *(_QWORD *)(*v6 + 280) <= 7u ? v16 + 256 : *(_QWORD *)(v16 + 256);
    v31[0] = v17;
    v31[1] = *(_QWORD *)(v16 + 272);
    winrt::hstring::operator=(&v23, v31);
    if ( WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(
           (WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)v20,
           a3) )
    {
      break;
    }
    WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria((WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)v20);
    ++v6;
  }
  *a2 = winrt::impl::duplicate_hstring(v20[0], v18);
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria((WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)v20);
  return a2;
}

```

## disassembly

```asm
0x180018e84  push    rbp
0x180018e86  push    rbx
0x180018e87  push    rsi
0x180018e88  push    rdi
0x180018e89  push    r14
0x180018e8b  lea     rbp, [rsp-37h]
0x180018e90  sub     rsp, 0D0h
0x180018e97  mov     r14, r8
0x180018e9a  mov     rsi, rdx
0x180018e9d  mov     rbx, rcx
0x180018ea0  mov     rcx, r8; this
0x180018ea3  call    ?Normalize@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAAXXZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(void)
0x180018ea8  mov     rdi, [rbx+20h]
0x180018eac  mov     rbx, [rbx+28h]
0x180018eb0  jmp     loc_180019029
0x180018eb5  xor     edx, edx; Val
0x180018eb7  lea     r8d, [rdx+50h]; Size
0x180018ebb  lea     rcx, [rbp+57h+var_D0]; void *
0x180018ebf  call    memset_0
0x180018ec4  xorps   xmm0, xmm0
0x180018ec7  movdqa  xmmword ptr [rbp+57h+var_D0], xmm0
0x180018ecc  mov     [rbp+57h+var_D0+8], 0
0x180018ed4  xor     eax, eax
0x180018ed6  mov     [rbp+57h+var_C0], eax
0x180018ed9  mov     [rbp+57h+var_B8], rax
0x180018edd  movdqa  [rbp+57h+var_B0], xmm0
0x180018ee2  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180018ee6  mov     [rbp+57h+var_A0], rax
0x180018eea  mov     [rbp+57h+var_98], ax
0x180018eee  movdqa  [rbp+57h+var_90], xmm0
0x180018ef3  mov     qword ptr [rbp+57h+var_90+8], rax
0x180018ef7  mov     rax, [rdi]
0x180018efa  cmp     qword ptr [rax+38h], 7
0x180018eff  jbe     short loc_180018F07
0x180018f01  mov     rcx, [rax+20h]
0x180018f05  jmp     short loc_180018F0B
0x180018f07  lea     rcx, [rax+20h]
0x180018f0b  mov     [rbp+57h+var_78], rcx
0x180018f0f  mov     rax, [rax+30h]
0x180018f13  mov     [rbp+57h+var_70], rax
0x180018f17  lea     rdx, [rbp+57h+var_78]
0x180018f1b  lea     rcx, [rbp+57h+var_D0+8]
0x180018f1f  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x180018f24  mov     rax, [rdi]
0x180018f27  cmp     qword ptr [rax+140h], 7
0x180018f2f  jbe     short loc_180018F3A
0x180018f31  mov     rcx, [rax+128h]
0x180018f38  jmp     short loc_180018F41
0x180018f3a  lea     rcx, [rax+128h]
0x180018f41  mov     [rbp+57h+var_68], rcx
0x180018f45  mov     rax, [rax+138h]
0x180018f4c  mov     [rbp+57h+var_60], rax
0x180018f50  lea     rdx, [rbp+57h+var_68]
0x180018f54  lea     rcx, [rbp+57h+var_D0]
0x180018f58  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x180018f5d  mov     rcx, [rdi]
0x180018f60  movzx   eax, word ptr [rcx+120h]
0x180018f67  mov     word ptr [rbp+57h+var_C0], ax
0x180018f6b  movzx   eax, word ptr [rcx+122h]
0x180018f72  mov     word ptr [rbp+57h+var_C0+2], ax
0x180018f76  lea     rax, [rcx+0E0h]
0x180018f7d  cmp     qword ptr [rcx+0F8h], 7
0x180018f85  jbe     short loc_180018F8A
0x180018f87  mov     rax, [rax]
0x180018f8a  mov     [rbp+57h+var_58], rax
0x180018f8e  mov     rax, [rcx+0F0h]
0x180018f95  mov     [rbp+57h+var_50], rax
0x180018f99  lea     rdx, [rbp+57h+var_58]
0x180018f9d  lea     rcx, [rbp+57h+var_B8]
0x180018fa1  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x180018fa6  mov     rax, [rdi]
0x180018fa9  cmp     qword ptr [rax+78h], 7
0x180018fae  jbe     short loc_180018FB6
0x180018fb0  mov     rcx, [rax+60h]
0x180018fb4  jmp     short loc_180018FBA
0x180018fb6  lea     rcx, [rax+60h]
0x180018fba  mov     [rbp+57h+var_48], rcx
0x180018fbe  mov     rax, [rax+70h]
0x180018fc2  mov     [rbp+57h+var_40], rax
0x180018fc6  lea     rdx, [rbp+57h+var_48]
0x180018fca  lea     rcx, [rbp+57h+var_90]
0x180018fce  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x180018fd3  mov     rax, [rdi]
0x180018fd6  cmp     qword ptr [rax+118h], 7
0x180018fde  jbe     short loc_180018FE9
0x180018fe0  mov     rcx, [rax+100h]
0x180018fe7  jmp     short loc_180018FF0
0x180018fe9  lea     rcx, [rax+100h]
0x180018ff0  mov     [rbp+57h+var_38], rcx
0x180018ff4  mov     rax, [rax+110h]
0x180018ffb  mov     [rbp+57h+var_30], rax
0x180018fff  lea     rdx, [rbp+57h+var_38]
0x180019003  lea     rcx, [rbp+57h+var_B0]
0x180019007  call    ??4hstring@winrt@@QEAAAEAU01@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::operator=(std::basic_string_view<ushort> const &)
0x18001900c  mov     rdx, r14; struct WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *
0x18001900f  lea     rcx, [rbp+57h+var_D0]; this
0x180019013  call    ?Matches@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV12@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Matches(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria &)
0x180019018  test    al, al
0x18001901a  jnz     short loc_18001904A
0x18001901c  lea     rcx, [rbp+57h+var_D0]; this
0x180019020  call    ??1MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(void)
0x180019025  add     rdi, 8
0x180019029  cmp     rdi, rbx
0x18001902c  jnz     loc_180018EB5
0x180019032  mov     qword ptr [rsi], 0
0x180019039  mov     rax, rsi
0x18001903c  add     rsp, 0D0h
0x180019043  pop     r14
0x180019045  pop     rdi
0x180019046  pop     rsi
0x180019047  pop     rbx
0x180019048  pop     rbp
0x180019049  retn
0x18001904a  mov     rcx, [rbp+57h+var_D0]; this
0x18001904e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180019053  mov     [rsi], rax
0x180019056  lea     rcx, [rbp+57h+var_D0]; this
0x18001905a  call    ??1MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(void)
0x18001905f  jmp     short loc_180019039
```

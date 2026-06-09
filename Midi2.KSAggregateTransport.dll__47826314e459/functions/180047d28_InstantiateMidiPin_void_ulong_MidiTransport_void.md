# InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)

- ea: `0x180047d28`
- end: `0x180047e93`
- name: `?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047294`

## callees

- `0x180005e9c`
- `0x18000b394`
- `0x1800106c8`
- `0x180047d28`

## import_xrefs

- `ksuser!KsCreatePin` at `0x180047dfd`
- `ksuser!KsCreatePin` at `0x180047dfd`

## string_xrefs

- `0x180047e40`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall InstantiateMidiPin(void *a1, ULONG a2, int a3, HANDLE *a4)
{
  unsigned int v8; // eax
  int v9; // ecx
  GUID *v10; // rax
  GUID v11; // xmm0
  signed int v12; // eax
  signed int v13; // ebx
  __int64 v14; // rdx
  __int64 result; // rax
  HANDLE ConnectionHandle; // [rsp+20h] [rbp-69h] BYREF
  $58C2C1BF6568EE28BD9B872E6BA03976 Connect; // [rsp+30h] [rbp-59h] BYREF
  int v18; // [rsp+78h] [rbp-11h]
  GUID v19; // [rsp+88h] [rbp-1h]
  GUID v20; // [rsp+98h] [rbp+Fh]
  GUID v21; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  ConnectionHandle = 0;
  memset_0(&Connect, 0, 0x88u);
  if ( ((a3 - 2) & 0xFFFFFFFD) != 0 )
  {
    v8 = 0;
LABEL_3:
    v9 = 0;
    goto LABEL_4;
  }
  v8 = 1;
  if ( a3 != 4 )
    goto LABEL_3;
  v9 = 1;
LABEL_4:
  *(&Connect.Interface.Alignment + 2) = v8;
  Connect.Priority.PriorityClass = 0x40000000;
  Connect.Interface.Set = GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
  Connect.Priority.PrioritySubClass = 0x40000000;
  v10 = &GUID_fbffd49e_ce26_464a_9dfc_fee42456c81c;
  if ( !v9 )
    v10 = &GUID_1d262760_e957_11cf_a5d6_28db04c10000;
  *(&Connect.Medium.Alignment + 2) = 0;
  Connect.Medium.Set = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
  Connect.PinId = a2;
  Connect.PinToHandle = 0;
  v19 = GUID_e725d360_62cc_11cf_a5d6_28db04c10000;
  v18 = 64;
  v11 = *v10;
  v21 = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
  v20 = v11;
  v12 = KsCreatePin(a1, &Connect, 0xC0000000, &ConnectionHandle);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
  {
    if ( v13 < 0 )
    {
      if ( v13 == -2147023727 || v13 == -2147024865 )
        return (unsigned int)v13;
      v14 = 292;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
        (const char *)(unsigned int)v13,
        (int)ConnectionHandle);
      return (unsigned int)v13;
    }
    goto LABEL_20;
  }
  if ( v13 >= 0 )
  {
LABEL_20:
    *a4 = ConnectionHandle;
    return 0;
  }
  result = 2147943569LL;
  if ( v13 != -2147023727 )
  {
    v14 = 297;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x180047d28  push    rbp
0x180047d2a  push    rbx
0x180047d2b  push    rsi
0x180047d2c  push    rdi
0x180047d2d  push    r14
0x180047d2f  lea     rbp, [rsp-37h]
0x180047d34  sub     rsp, 0C0h
0x180047d3b  mov     ebx, r8d
0x180047d3e  mov     [rbp+57h+ConnectionHandle], 0
0x180047d46  mov     esi, edx
0x180047d48  mov     r14, rcx
0x180047d4b  xor     edx, edx; Val
0x180047d4d  lea     rcx, [rbp+57h+Connect]; void *
0x180047d51  mov     r8d, 88h; Size
0x180047d57  mov     rdi, r9
0x180047d5a  call    memset_0
0x180047d5f  lea     eax, [rbx-2]
0x180047d62  test    eax, 0FFFFFFFDh
0x180047d67  jz      loc_180047E53
0x180047d6d  xor     eax, eax
0x180047d6f  xor     ecx, ecx
0x180047d71  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x180047d78  mov     dword ptr [rbp+57h+Connect.Interface+10h], eax
0x180047d7b  mov     eax, 40000000h
0x180047d80  movups  xmm1, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x180047d87  mov     [rbp+57h+Connect.Priority.PriorityClass], eax
0x180047d8a  test    ecx, ecx
0x180047d8c  movdqu  xmmword ptr [rbp+57h+Connect.Interface], xmm0
0x180047d91  mov     [rbp+57h+Connect.Priority.PrioritySubClass], eax
0x180047d94  lea     rdx, _GUID_1d262760_e957_11cf_a5d6_28db04c10000
0x180047d9b  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x180047da2  lea     rax, _GUID_fbffd49e_ce26_464a_9dfc_fee42456c81c
0x180047da9  mov     dword ptr [rbp+57h+Connect.Interface+14h], 0
0x180047db0  cmovz   rax, rdx
0x180047db4  mov     qword ptr [rbp+57h+Connect.Medium+10h], 0
0x180047dbc  movdqu  xmmword ptr [rbp+57h+Connect.Medium], xmm0
0x180047dc1  lea     r9, [rbp+57h+ConnectionHandle]; ConnectionHandle
0x180047dc5  mov     r8d, 0C0000000h; DesiredAccess
0x180047dcb  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x180047dd2  lea     rdx, [rbp+57h+Connect]; Connect
0x180047dd6  mov     [rbp+57h+Connect.PinId], esi
0x180047dd9  mov     rcx, r14; FilterHandle
0x180047ddc  mov     [rbp+57h+Connect.PinToHandle], 0
0x180047de4  movdqu  [rbp+57h+var_58], xmm0
0x180047de9  mov     [rbp+57h+var_68], 40h ; '@'
0x180047df0  movups  xmm0, xmmword ptr [rax]
0x180047df3  movdqu  [rbp+57h+var_38], xmm1
0x180047df8  movdqu  [rbp+57h+var_48], xmm0
0x180047dfd  call    cs:__imp_KsCreatePin
0x180047e03  mov     ebx, eax
0x180047e05  test    eax, eax
0x180047e07  jle     short loc_180047E12
0x180047e09  movzx   ebx, ax
0x180047e0c  or      ebx, 80070000h
0x180047e12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180047e19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x180047e1e  test    al, al
0x180047e20  jz      short loc_180047E68
0x180047e22  test    ebx, ebx
0x180047e24  jns     short loc_180047E7C
0x180047e26  mov     eax, 80070491h
0x180047e2b  cmp     ebx, eax
0x180047e2d  jz      short loc_180047E4F
0x180047e2f  cmp     ebx, 8007001Fh
0x180047e35  jz      short loc_180047E4F
0x180047e37  mov     edx, 124h; void *
0x180047e3c  mov     rcx, [rbp+5Fh]; this
0x180047e40  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180047e47  mov     r9d, ebx; char *
0x180047e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047e4f  mov     eax, ebx
0x180047e51  jmp     short loc_180047E85
0x180047e53  mov     eax, 1
0x180047e58  cmp     ebx, 4
0x180047e5b  jnz     loc_180047D6F
0x180047e61  mov     ecx, eax
0x180047e63  jmp     loc_180047D71
0x180047e68  test    ebx, ebx
0x180047e6a  jns     short loc_180047E7C
0x180047e6c  mov     eax, 80070491h
0x180047e71  cmp     ebx, eax
0x180047e73  jz      short loc_180047E85
0x180047e75  mov     edx, 129h
0x180047e7a  jmp     short loc_180047E3C
0x180047e7c  mov     rax, [rbp+57h+ConnectionHandle]
0x180047e80  mov     [rdi], rax
0x180047e83  xor     eax, eax
0x180047e85  add     rsp, 0C0h
0x180047e8c  pop     r14
0x180047e8e  pop     rdi
0x180047e8f  pop     rsi
0x180047e90  pop     rbx
0x180047e91  pop     rbp
0x180047e92  retn
```

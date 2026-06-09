# InstantiateMidiPin(void *,ulong,_MidiTransport,void * *)

- ea: `0x1800272a8`
- end: `0x180027413`
- name: `?InstantiateMidiPin@@YAJPEAXKW4_MidiTransport@@PEAPEAX@Z`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800267e4`

## callees

- `0x18000526c`
- `0x18000a814`
- `0x18001fe98`
- `0x1800272a8`

## import_xrefs

- `ksuser!KsCreatePin` at `0x18002737d`
- `ksuser!KsCreatePin` at `0x18002737d`

## string_xrefs

- `0x1800273c0`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

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
0x1800272a8  push    rbp
0x1800272aa  push    rbx
0x1800272ab  push    rsi
0x1800272ac  push    rdi
0x1800272ad  push    r14
0x1800272af  lea     rbp, [rsp-37h]
0x1800272b4  sub     rsp, 0C0h
0x1800272bb  mov     ebx, r8d
0x1800272be  mov     [rbp+57h+ConnectionHandle], 0
0x1800272c6  mov     esi, edx
0x1800272c8  mov     r14, rcx
0x1800272cb  xor     edx, edx; Val
0x1800272cd  lea     rcx, [rbp+57h+Connect]; void *
0x1800272d1  mov     r8d, 88h; Size
0x1800272d7  mov     rdi, r9
0x1800272da  call    memset_0
0x1800272df  lea     eax, [rbx-2]
0x1800272e2  test    eax, 0FFFFFFFDh
0x1800272e7  jz      loc_1800273D3
0x1800272ed  xor     eax, eax
0x1800272ef  xor     ecx, ecx
0x1800272f1  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x1800272f8  mov     dword ptr [rbp+57h+Connect.Interface+10h], eax
0x1800272fb  mov     eax, 40000000h
0x180027300  movups  xmm1, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x180027307  mov     [rbp+57h+Connect.Priority.PriorityClass], eax
0x18002730a  test    ecx, ecx
0x18002730c  movdqu  xmmword ptr [rbp+57h+Connect.Interface], xmm0
0x180027311  mov     [rbp+57h+Connect.Priority.PrioritySubClass], eax
0x180027314  lea     rdx, _GUID_1d262760_e957_11cf_a5d6_28db04c10000
0x18002731b  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x180027322  lea     rax, _GUID_fbffd49e_ce26_464a_9dfc_fee42456c81c
0x180027329  mov     dword ptr [rbp+57h+Connect.Interface+14h], 0
0x180027330  cmovz   rax, rdx
0x180027334  mov     qword ptr [rbp+57h+Connect.Medium+10h], 0
0x18002733c  movdqu  xmmword ptr [rbp+57h+Connect.Medium], xmm0
0x180027341  lea     r9, [rbp+57h+ConnectionHandle]; ConnectionHandle
0x180027345  mov     r8d, 0C0000000h; DesiredAccess
0x18002734b  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x180027352  lea     rdx, [rbp+57h+Connect]; Connect
0x180027356  mov     [rbp+57h+Connect.PinId], esi
0x180027359  mov     rcx, r14; FilterHandle
0x18002735c  mov     [rbp+57h+Connect.PinToHandle], 0
0x180027364  movdqu  [rbp+57h+var_58], xmm0
0x180027369  mov     [rbp+57h+var_68], 40h ; '@'
0x180027370  movups  xmm0, xmmword ptr [rax]
0x180027373  movdqu  [rbp+57h+var_38], xmm1
0x180027378  movdqu  [rbp+57h+var_48], xmm0
0x18002737d  call    cs:__imp_KsCreatePin
0x180027383  mov     ebx, eax
0x180027385  test    eax, eax
0x180027387  jle     short loc_180027392
0x180027389  movzx   ebx, ax
0x18002738c  or      ebx, 80070000h
0x180027392  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180027399  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18002739e  test    al, al
0x1800273a0  jz      short loc_1800273E8
0x1800273a2  test    ebx, ebx
0x1800273a4  jns     short loc_1800273FC
0x1800273a6  mov     eax, 80070491h
0x1800273ab  cmp     ebx, eax
0x1800273ad  jz      short loc_1800273CF
0x1800273af  cmp     ebx, 8007001Fh
0x1800273b5  jz      short loc_1800273CF
0x1800273b7  mov     edx, 124h; void *
0x1800273bc  mov     rcx, [rbp+5Fh]; this
0x1800273c0  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x1800273c7  mov     r9d, ebx; char *
0x1800273ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273cf  mov     eax, ebx
0x1800273d1  jmp     short loc_180027405
0x1800273d3  mov     eax, 1
0x1800273d8  cmp     ebx, 4
0x1800273db  jnz     loc_1800272EF
0x1800273e1  mov     ecx, eax
0x1800273e3  jmp     loc_1800272F1
0x1800273e8  test    ebx, ebx
0x1800273ea  jns     short loc_1800273FC
0x1800273ec  mov     eax, 80070491h
0x1800273f1  cmp     ebx, eax
0x1800273f3  jz      short loc_180027405
0x1800273f5  mov     edx, 129h
0x1800273fa  jmp     short loc_1800273BC
0x1800273fc  mov     rax, [rbp+57h+ConnectionHandle]
0x180027400  mov     [rdi], rax
0x180027403  xor     eax, eax
0x180027405  add     rsp, 0C0h
0x18002740c  pop     r14
0x18002740e  pop     rdi
0x18002740f  pop     rsi
0x180027410  pop     rbx
0x180027411  pop     rbp
0x180027412  retn
```

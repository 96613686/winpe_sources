# CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties(std::shared_ptr<KsAggregateEndpointDefinition2>,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>)

- ea: `0x18003fc04`
- end: `0x180040034`
- name: `?UpdateNameTableWithCustomProperties@CMidi2KSAggregateMidiEndpointManager2@@AEAAJV?$shared_ptr@UKsAggregateEndpointDefinition2@@@std@@V?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@3@@Z`
- size: `1072`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180036d5c`
- `0x180037fec`

## callees

- `0x1800024e0`
- `0x18000b394`
- `0x1800117d8`
- `0x18003fc04`
- `0x180056eb8`
- `0x180056fc4`
- `0x18005e010`

## string_xrefs

- `0x18003fdd2`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties`
- `0x18003ff27`: `CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties`

## pseudocode

```c
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties(
        const wchar_t *a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v5; // rdx
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rdi
  __int64 v10; // rax
  __int64 *v11; // rbx
  __int64 *v12; // r15
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  _BYTE *v16; // rsi
  _BYTE *i; // rax
  _DWORD *v18; // r8
  int v19; // r9d
  const struct winrt::hstring *v20; // rsi
  __int64 v21; // rax
  const wchar_t *v22; // rax
  const char *v23; // rax
  __int64 *v24; // rbx
  __int64 *v25; // r15
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _BYTE *v29; // rsi
  _BYTE *j; // rax
  _DWORD *v31; // r8
  int v32; // r9d
  const struct winrt::hstring *v33; // rsi
  __int64 v34; // rax
  const wchar_t *v35; // rax
  _QWORD *v36; // rax
  volatile signed __int32 *v37; // rdi
  volatile signed __int32 *v38; // rdi
  int v39; // [rsp+20h] [rbp-39h]
  const char *v40; // [rsp+50h] [rbp-9h] BYREF
  const wchar_t *v41; // [rsp+58h] [rbp-1h] BYREF
  const wchar_t *v42; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v43[2]; // [rsp+68h] [rbp+Fh] BYREF
  int v44; // [rsp+7Ch] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  char v46; // [rsp+C8h] [rbp+6Fh] BYREF
  const wchar_t *v47; // [rsp+D8h] [rbp+7Fh] BYREF

  v5 = *a2;
  if ( v5 )
  {
    v10 = *a3;
    if ( *a3 && (*(_QWORD *)(v10 + 56) || *(_QWORD *)(v10 + 40)) )
    {
      v11 = *(__int64 **)(v5 + 152);
      v12 = *(__int64 **)(v5 + 160);
      while ( v11 != v12 )
      {
        v13 = *a3;
        v14 = *v11;
        v44 = 0;
        v15 = *(_QWORD *)(v13 + 48);
        v16 = (_BYTE *)v15;
        for ( i = *(_BYTE **)(v15 + 8); !i[25]; i = *(_BYTE **)i )
        {
          if ( i[32] >= *(_BYTE *)(v14 + 145) )
            v16 = i;
          else
            i += 16;
        }
        if ( !v16[25] && *(_BYTE *)(v14 + 145) >= v16[32] && v16 != (_BYTE *)v15 )
        {
          v18 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v18 <= 5u )
          {
            v20 = (const struct winrt::hstring *)(v16 + 48);
          }
          else
          {
            v20 = (const struct winrt::hstring *)(v16 + 48);
            v21 = *(_QWORD *)v20;
            v46 = *(_BYTE *)(*v11 + 145);
            if ( v21 )
              v22 = *(const wchar_t **)(v21 + 16);
            else
              v22 = &S1;
            v47 = v22;
            v23 = (const char *)(*a2 + 96LL);
            if ( *(_QWORD *)(*a2 + 120LL) > 7u )
              v23 = *(const char **)v23;
            v40 = v23;
            v42 = a1;
            v41 = L"Found custom name for a Midi 1 destination.";
            v43[0] = "CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
              (_DWORD)v18,
              (unsigned int)&unk_18008AC68,
              (_DWORD)v18,
              v19,
              (__int64)v43,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&v40,
              (__int64)&v47,
              (__int64)&v46);
          }
          WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(
            (WindowsMidiServicesNamingLib::MidiEndpointNameTable *)(*a2 + 176LL),
            *(_BYTE *)(*v11 + 145),
            v20);
        }
        v11 += 2;
      }
      v24 = *(__int64 **)(*a2 + 128LL);
      v25 = *(__int64 **)(*a2 + 136LL);
      while ( v24 != v25 )
      {
        v26 = *a3;
        v27 = *v24;
        v44 = 0;
        v28 = *(_QWORD *)(v26 + 32);
        v29 = (_BYTE *)v28;
        for ( j = *(_BYTE **)(v28 + 8); !j[25]; j = *(_BYTE **)j )
        {
          if ( j[32] >= *(_BYTE *)(v27 + 145) )
            v29 = j;
          else
            j += 16;
        }
        if ( !v29[25] && *(_BYTE *)(v27 + 145) >= v29[32] && v29 != (_BYTE *)v28 )
        {
          v31 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v31 <= 5u )
          {
            v33 = (const struct winrt::hstring *)(v29 + 48);
          }
          else
          {
            v33 = (const struct winrt::hstring *)(v29 + 48);
            v34 = *(_QWORD *)v33;
            v46 = *(_BYTE *)(*v24 + 145);
            if ( v34 )
              v35 = *(const wchar_t **)(v34 + 16);
            else
              v35 = &S1;
            v47 = v35;
            v36 = (_QWORD *)(*a2 + 96LL);
            if ( *(_QWORD *)(*a2 + 120LL) > 7u )
              v36 = (_QWORD *)*v36;
            v43[0] = v36;
            v41 = a1;
            v42 = L"Found custom name for a Midi 1 source.";
            v40 = "CMidi2KSAggregateMidiEndpointManager2::UpdateNameTableWithCustomProperties";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
              (_DWORD)v31,
              (unsigned int)&unk_18008AC08,
              (_DWORD)v31,
              v32,
              (__int64)&v40,
              (__int64)&v41,
              (__int64)&v42,
              (__int64)v43,
              (__int64)&v47,
              (__int64)&v46);
          }
          WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(
            (WindowsMidiServicesNamingLib::MidiEndpointNameTable *)(*a2 + 176LL),
            *(_BYTE *)(*v24 + 145),
            v33);
        }
        v24 += 2;
      }
    }
    v37 = (volatile signed __int32 *)a2[1];
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    v38 = (volatile signed __int32 *)a3[1];
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiendpointmanager2.cpp",
      (const char *)0x80070057LL,
      v39);
    v7 = (volatile signed __int32 *)a2[1];
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = (volatile signed __int32 *)a3[1];
    if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18003fc04  mov     [rsp-8+arg_0], rbx
0x18003fc09  mov     [rsp-8+arg_10], rsi
0x18003fc0e  push    rbp
0x18003fc0f  push    rdi
0x18003fc10  push    r12
0x18003fc12  push    r14
0x18003fc14  push    r15
0x18003fc16  lea     rbp, [rsp-37h]
0x18003fc1b  sub     rsp, 90h
0x18003fc22  mov     rdi, rdx
0x18003fc25  mov     r14, r8
0x18003fc28  mov     rdx, [rdx]
0x18003fc2b  mov     r12, rcx
0x18003fc2e  test    rdx, rdx
0x18003fc31  jnz     loc_18003FCD6
0x18003fc37  mov     rcx, [rbp+5Fh]; this
0x18003fc3b  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18003fc42  mov     esi, 80070057h
0x18003fc47  mov     edx, 8Fh; void *
0x18003fc4c  mov     r9d, esi; char *
0x18003fc4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fc54  mov     rdi, [rdi+8]
0x18003fc58  or      ebx, 0FFFFFFFFh
0x18003fc5b  test    rdi, rdi
0x18003fc5e  jz      short loc_18003FC93
0x18003fc60  mov     eax, ebx
0x18003fc62  lock xadd [rdi+8], eax
0x18003fc67  add     eax, ebx
0x18003fc69  jnz     short loc_18003FC93
0x18003fc6b  mov     rax, [rdi]
0x18003fc6e  mov     rcx, rdi
0x18003fc71  mov     rax, [rax]
0x18003fc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc79  mov     eax, ebx
0x18003fc7b  lock xadd [rdi+0Ch], eax
0x18003fc80  add     eax, ebx
0x18003fc82  jnz     short loc_18003FC93
0x18003fc84  mov     rax, [rdi]
0x18003fc87  mov     rcx, rdi
0x18003fc8a  mov     rax, [rax+8]
0x18003fc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc93  mov     rdi, [r14+8]
0x18003fc97  test    rdi, rdi
0x18003fc9a  jz      short loc_18003FCCF
0x18003fc9c  mov     eax, ebx
0x18003fc9e  lock xadd [rdi+8], eax
0x18003fca3  add     eax, ebx
0x18003fca5  jnz     short loc_18003FCCF
0x18003fca7  mov     rax, [rdi]
0x18003fcaa  mov     rcx, rdi
0x18003fcad  mov     rax, [rax]
0x18003fcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcb5  mov     edx, ebx
0x18003fcb7  lock xadd [rdi+0Ch], edx
0x18003fcbc  add     edx, ebx
0x18003fcbe  jnz     short loc_18003FCCF
0x18003fcc0  mov     rdx, [rdi]
0x18003fcc3  mov     rcx, rdi
0x18003fcc6  mov     rax, [rdx+8]
0x18003fcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fccf  mov     eax, esi
0x18003fcd1  jmp     loc_180040018
0x18003fcd6  mov     rax, [r8]
0x18003fcd9  test    rax, rax
0x18003fcdc  jz      loc_18003FF9B
0x18003fce2  cmp     qword ptr [rax+38h], 0
0x18003fce7  jnz     short loc_18003FCF4
0x18003fce9  cmp     qword ptr [rax+28h], 0
0x18003fcee  jz      loc_18003FF9B
0x18003fcf4  mov     rbx, [rdx+98h]
0x18003fcfb  mov     r15, [rdx+0A0h]
0x18003fd02  jmp     loc_18003FE3D
0x18003fd07  mov     rax, [r14]
0x18003fd0a  xor     r8d, r8d
0x18003fd0d  mov     rdx, [rbx]
0x18003fd10  mov     [rbp+57h+var_34], r8d
0x18003fd14  mov     rcx, [rax+30h]
0x18003fd18  mov     rsi, rcx
0x18003fd1b  mov     rax, [rcx+8]
0x18003fd1f  cmp     [rax+19h], r8b
0x18003fd23  jnz     short loc_18003FD44
0x18003fd25  mov     r8b, [rdx+91h]
0x18003fd2c  cmp     [rax+20h], r8b
0x18003fd30  jnb     short loc_18003FD38
0x18003fd32  add     rax, 10h
0x18003fd36  jmp     short loc_18003FD3B
0x18003fd38  mov     rsi, rax
0x18003fd3b  mov     rax, [rax]
0x18003fd3e  cmp     byte ptr [rax+19h], 0
0x18003fd42  jz      short loc_18003FD2C
0x18003fd44  cmp     byte ptr [rsi+19h], 0
0x18003fd48  jnz     loc_18003FE39
0x18003fd4e  mov     al, [rsi+20h]
0x18003fd51  cmp     [rdx+91h], al
0x18003fd57  jb      loc_18003FE39
0x18003fd5d  cmp     rsi, rcx
0x18003fd60  jz      loc_18003FE39
0x18003fd66  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003fd6b  mov     r8, [rax+8]
0x18003fd6f  mov     eax, [r8]
0x18003fd72  cmp     eax, 5
0x18003fd75  jbe     loc_18003FE1A
0x18003fd7b  mov     rax, [rbx]
0x18003fd7e  add     rsi, 30h ; '0'
0x18003fd82  mov     cl, [rax+91h]
0x18003fd88  mov     rax, [rsi]
0x18003fd8b  mov     [rbp+57h+arg_8], cl
0x18003fd8e  test    rax, rax
0x18003fd91  jz      short loc_18003FD99
0x18003fd93  mov     rax, [rax+10h]
0x18003fd97  jmp     short loc_18003FDA0
0x18003fd99  lea     rax, S1
0x18003fda0  mov     [rbp+57h+arg_18], rax
0x18003fda4  mov     rax, [rdi]
0x18003fda7  add     rax, 60h ; '`'
0x18003fdab  cmp     qword ptr [rax+18h], 7
0x18003fdb0  jbe     short loc_18003FDB5
0x18003fdb2  mov     rax, [rax]
0x18003fdb5  mov     [rbp+57h+var_60], rax
0x18003fdb9  lea     rdx, unk_18008AC68
0x18003fdc0  lea     rax, aFoundCustomNam; "Found custom name for a Midi 1 destinat"...
0x18003fdc7  mov     [rbp+57h+var_50], r12
0x18003fdcb  mov     [rbp+57h+var_58], rax
0x18003fdcf  mov     rcx, r8
0x18003fdd2  lea     rax, aCmidi2ksaggreg_11; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18003fdd9  mov     [rbp+57h+var_48], rax
0x18003fddd  lea     rax, [rbp+57h+arg_8]
0x18003fde1  mov     [rsp+0B0h+var_68], rax
0x18003fde6  lea     rax, [rbp+57h+arg_18]
0x18003fdea  mov     [rsp+0B0h+var_70], rax
0x18003fdef  lea     rax, [rbp+57h+var_60]
0x18003fdf3  mov     [rsp+0B0h+var_78], rax
0x18003fdf8  lea     rax, [rbp+57h+var_58]
0x18003fdfc  mov     [rsp+0B0h+var_80], rax
0x18003fe01  lea     rax, [rbp+57h+var_50]
0x18003fe05  mov     [rsp+0B0h+var_88], rax
0x18003fe0a  lea     rax, [rbp+57h+var_48]
0x18003fe0e  mov     [rsp+0B0h+var_90], rax
0x18003fe13  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x18003fe18  jmp     short loc_18003FE1E
0x18003fe1a  add     rsi, 30h ; '0'
0x18003fe1e  mov     rdx, [rbx]
0x18003fe21  mov     r8, rsi; struct winrt::hstring *
0x18003fe24  mov     rcx, [rdi]
0x18003fe27  add     rcx, 0B0h; this
0x18003fe2e  mov     dl, [rdx+91h]; unsigned __int8
0x18003fe34  call    ?UpdateDestinationEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(uchar,winrt::hstring const &)
0x18003fe39  add     rbx, 10h
0x18003fe3d  cmp     rbx, r15
0x18003fe40  jnz     loc_18003FD07
0x18003fe46  mov     rax, [rdi]
0x18003fe49  mov     rbx, [rax+80h]
0x18003fe50  mov     r15, [rax+88h]
0x18003fe57  jmp     loc_18003FF92
0x18003fe5c  mov     rax, [r14]
0x18003fe5f  xor     r8d, r8d
0x18003fe62  mov     rdx, [rbx]
0x18003fe65  mov     [rbp+57h+var_34], r8d
0x18003fe69  mov     rcx, [rax+20h]
0x18003fe6d  mov     rsi, rcx
0x18003fe70  mov     rax, [rcx+8]
0x18003fe74  cmp     [rax+19h], r8b
0x18003fe78  jnz     short loc_18003FE99
0x18003fe7a  mov     r8b, [rdx+91h]
0x18003fe81  cmp     [rax+20h], r8b
0x18003fe85  jnb     short loc_18003FE8D
0x18003fe87  add     rax, 10h
0x18003fe8b  jmp     short loc_18003FE90
0x18003fe8d  mov     rsi, rax
0x18003fe90  mov     rax, [rax]
0x18003fe93  cmp     byte ptr [rax+19h], 0
0x18003fe97  jz      short loc_18003FE81
0x18003fe99  cmp     byte ptr [rsi+19h], 0
0x18003fe9d  jnz     loc_18003FF8E
0x18003fea3  mov     al, [rsi+20h]
0x18003fea6  cmp     [rdx+91h], al
0x18003feac  jb      loc_18003FF8E
0x18003feb2  cmp     rsi, rcx
0x18003feb5  jz      loc_18003FF8E
0x18003febb  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003fec0  mov     r8, [rax+8]
0x18003fec4  mov     eax, [r8]
0x18003fec7  cmp     eax, 5
0x18003feca  jbe     loc_18003FF6F
0x18003fed0  mov     rax, [rbx]
0x18003fed3  add     rsi, 30h ; '0'
0x18003fed7  mov     cl, [rax+91h]
0x18003fedd  mov     rax, [rsi]
0x18003fee0  mov     [rbp+57h+arg_8], cl
0x18003fee3  test    rax, rax
0x18003fee6  jz      short loc_18003FEEE
0x18003fee8  mov     rax, [rax+10h]
0x18003feec  jmp     short loc_18003FEF5
0x18003feee  lea     rax, S1
0x18003fef5  mov     [rbp+57h+arg_18], rax
0x18003fef9  mov     rax, [rdi]
0x18003fefc  add     rax, 60h ; '`'
0x18003ff00  cmp     qword ptr [rax+18h], 7
0x18003ff05  jbe     short loc_18003FF0A
0x18003ff07  mov     rax, [rax]
0x18003ff0a  mov     [rbp+57h+var_48], rax
0x18003ff0e  lea     rdx, unk_18008AC08
0x18003ff15  lea     rax, aFoundCustomNam_0; "Found custom name for a Midi 1 source."
0x18003ff1c  mov     [rbp+57h+var_58], r12
0x18003ff20  mov     [rbp+57h+var_50], rax
0x18003ff24  mov     rcx, r8
0x18003ff27  lea     rax, aCmidi2ksaggreg_11; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18003ff2e  mov     [rbp+57h+var_60], rax
0x18003ff32  lea     rax, [rbp+57h+arg_8]
0x18003ff36  mov     [rsp+0B0h+var_68], rax
0x18003ff3b  lea     rax, [rbp+57h+arg_18]
0x18003ff3f  mov     [rsp+0B0h+var_70], rax
0x18003ff44  lea     rax, [rbp+57h+var_48]
0x18003ff48  mov     [rsp+0B0h+var_78], rax
0x18003ff4d  lea     rax, [rbp+57h+var_50]
0x18003ff51  mov     [rsp+0B0h+var_80], rax
0x18003ff56  lea     rax, [rbp+57h+var_58]
0x18003ff5a  mov     [rsp+0B0h+var_88], rax
0x18003ff5f  lea     rax, [rbp+57h+var_60]
0x18003ff63  mov     [rsp+0B0h+var_90], rax
0x18003ff68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@55AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x18003ff6d  jmp     short loc_18003FF73
0x18003ff6f  add     rsi, 30h ; '0'
0x18003ff73  mov     rdx, [rbx]
0x18003ff76  mov     r8, rsi; struct winrt::hstring *
0x18003ff79  mov     rcx, [rdi]
0x18003ff7c  add     rcx, 0B0h; this
0x18003ff83  mov     dl, [rdx+91h]; unsigned __int8
0x18003ff89  call    ?UpdateSourceEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(uchar,winrt::hstring const &)
0x18003ff8e  add     rbx, 10h
0x18003ff92  cmp     rbx, r15
0x18003ff95  jnz     loc_18003FE5C
0x18003ff9b  mov     rdi, [rdi+8]
0x18003ff9f  or      ebx, 0FFFFFFFFh
0x18003ffa2  test    rdi, rdi
0x18003ffa5  jz      short loc_18003FFDA
0x18003ffa7  mov     eax, ebx
0x18003ffa9  lock xadd [rdi+8], eax
0x18003ffae  add     eax, ebx
0x18003ffb0  jnz     short loc_18003FFDA
0x18003ffb2  mov     rax, [rdi]
0x18003ffb5  mov     rcx, rdi
0x18003ffb8  mov     rax, [rax]
0x18003ffbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffc0  mov     eax, ebx
0x18003ffc2  lock xadd [rdi+0Ch], eax
0x18003ffc7  add     eax, ebx
0x18003ffc9  jnz     short loc_18003FFDA
0x18003ffcb  mov     rax, [rdi]
0x18003ffce  mov     rcx, rdi
0x18003ffd1  mov     rax, [rax+8]
0x18003ffd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffda  mov     rdi, [r14+8]
0x18003ffde  test    rdi, rdi
0x18003ffe1  jz      short loc_180040016
0x18003ffe3  mov     eax, ebx
0x18003ffe5  lock xadd [rdi+8], eax
0x18003ffea  add     eax, ebx
0x18003ffec  jnz     short loc_180040016
0x18003ffee  mov     rax, [rdi]
0x18003fff1  mov     rcx, rdi
0x18003fff4  mov     rax, [rax]
0x18003fff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fffc  mov     eax, ebx
0x18003fffe  lock xadd [rdi+0Ch], eax
0x180040003  add     eax, ebx
0x180040005  jnz     short loc_180040016
0x180040007  mov     rax, [rdi]
0x18004000a  mov     rcx, rdi
0x18004000d  mov     rax, [rax+8]
0x180040011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040016  xor     eax, eax
0x180040018  lea     r11, [rsp+0B0h+var_20]
0x180040020  mov     rbx, [r11+30h]
0x180040024  mov     rsi, [r11+40h]
0x180040028  mov     rsp, r11
0x18004002b  pop     r15
0x18004002d  pop     r14
0x18004002f  pop     r12
0x180040031  pop     rdi
0x180040032  pop     rbp
0x180040033  retn
```

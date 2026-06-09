# CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty(WindowsMidiServicesInternal::PackedUmp128 &)

- ea: `0x140044b74`
- end: `0x140044d6a`
- name: `?UpdateDeviceIdentityProperty@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this, struct WindowsMidiServicesInternal::PackedUmp128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140042194`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x14000984c`
- `0x14000a6b4`
- `0x140044b74`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044c95`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140044c95`

## string_xrefs

- `0x140044d31`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140044bd9`: `CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty(
        CMidiEndpointProtocolWorker *this,
        struct WindowsMidiServicesInternal::PackedUmp128 *a2)
{
  char *v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rax
  int v9; // ecx
  char v10; // al
  int v11; // ecx
  char v12; // al
  int v13; // ecx
  char v14; // al
  bool v15; // cc
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // [rsp+20h] [rbp-89h]
  __int16 v21; // [rsp+40h] [rbp-69h] BYREF
  char v22; // [rsp+42h] [rbp-67h]
  char v23; // [rsp+43h] [rbp-66h]
  char v24; // [rsp+44h] [rbp-65h]
  char v25; // [rsp+45h] [rbp-64h]
  char v26; // [rsp+46h] [rbp-63h]
  char v27; // [rsp+47h] [rbp-62h]
  char v28; // [rsp+48h] [rbp-61h]
  char v29; // [rsp+49h] [rbp-60h]
  char v30; // [rsp+4Ah] [rbp-5Fh]
  char v31; // [rsp+4Bh] [rbp-5Eh]
  char v32; // [rsp+4Ch] [rbp-5Dh]
  char v33; // [rsp+4Dh] [rbp-5Ch]
  __int64 v34; // [rsp+50h] [rbp-59h] BYREF
  char *v35; // [rsp+58h] [rbp-51h] BYREF
  const wchar_t *v36; // [rsp+60h] [rbp-49h] BYREF
  CMidiEndpointProtocolWorker *v37; // [rsp+68h] [rbp-41h] BYREF
  int v38[2]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v39; // [rsp+80h] [rbp-29h] BYREF
  int v40; // [rsp+90h] [rbp-19h]
  int v41; // [rsp+94h] [rbp-15h]
  __int64 v42; // [rsp+98h] [rbp-11h]
  int v43; // [rsp+A0h] [rbp-9h]
  int v44; // [rsp+A4h] [rbp-5h]
  __int16 *v45; // [rsp+A8h] [rbp-1h]
  __int128 v46; // [rsp+B0h] [rbp+7h]
  int v47; // [rsp+C0h] [rbp+17h]
  int v48; // [rsp+C4h] [rbp+1Bh]
  __int64 v49; // [rsp+C8h] [rbp+1Fh]
  int v50; // [rsp+D0h] [rbp+27h]
  int v51; // [rsp+D4h] [rbp+2Bh]
  __int64 *v52; // [rsp+D8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = (char *)this + 56;
  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    if ( *((_QWORD *)this + 10) <= 7u )
      v8 = (char *)this + 56;
    else
      v8 = *(char **)v4;
    v35 = v8;
    v37 = this;
    v36 = L"Enter";
    *(_QWORD *)v38 = "CMidiEndpointProtocolWorker::UpdateDeviceIdentityProperty";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)&word_14008BE26,
      v6,
      v7,
      v38,
      (__int64)&v37,
      &v36,
      &v35);
  }
  v9 = *((_DWORD *)a2 + 1);
  v21 = *(_WORD *)a2;
  v22 = HIBYTE(v9) & 0x7F;
  v23 = BYTE2(v9) & 0x7F;
  v10 = *((_BYTE *)a2 + 4) & 0x7F;
  v24 = BYTE1(v9) & 0x7F;
  v11 = *((_DWORD *)a2 + 2);
  v25 = v10;
  v26 = HIBYTE(v11) & 0x7F;
  v27 = BYTE2(v11) & 0x7F;
  v12 = *((_BYTE *)a2 + 8) & 0x7F;
  v28 = BYTE1(v11) & 0x7F;
  v13 = *((_DWORD *)a2 + 3);
  v29 = v12;
  v30 = HIBYTE(v13) & 0x7F;
  v31 = BYTE2(v13) & 0x7F;
  v14 = *((_BYTE *)a2 + 12);
  v32 = BYTE1(v13) & 0x7F;
  v33 = v14 & 0x7F;
  v34 = 0;
  GetSystemTimePreciseAsFileTime(&v34);
  v15 = *((_QWORD *)this + 10) <= 7u;
  v16 = *((_QWORD *)this + 22);
  v40 = 160;
  v45 = &v21;
  v39 = PKEY_MIDI_DeviceIdentity;
  v47 = 161;
  v52 = &v34;
  v46 = PKEY_MIDI_DeviceIdentityLastUpdateTime;
  v41 = 0;
  v42 = 0;
  v43 = 4099;
  v44 = 14;
  v48 = 0;
  v49 = 0;
  v50 = 16;
  v51 = 8;
  if ( !v15 )
    v4 = *(char **)v4;
  v17 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int128 *))(*(_QWORD *)v16 + 48LL))(v16, v4, 2, &v39);
  v18 = v17;
  if ( v17 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5C0,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
    (const char *)(unsigned int)v17,
    v20);
  return v18;
}

```

## disassembly

```asm
0x140044b74  mov     [rsp-8+arg_10], rbx
0x140044b79  push    rbp
0x140044b7a  push    rsi
0x140044b7b  push    rdi
0x140044b7c  lea     rbp, [rsp-47h]
0x140044b81  sub     rsp, 0F0h
0x140044b88  mov     rax, cs:__security_cookie
0x140044b8f  xor     rax, rsp
0x140044b92  mov     [rbp+57h+var_20], rax
0x140044b96  mov     rsi, rdx
0x140044b99  mov     rdi, rcx
0x140044b9c  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140044ba1  lea     rbx, [rdi+38h]
0x140044ba5  mov     rcx, [rax+8]
0x140044ba9  mov     eax, [rcx]
0x140044bab  cmp     eax, 4
0x140044bae  jbe     short loc_140044C0D
0x140044bb0  cmp     qword ptr [rbx+18h], 7
0x140044bb5  jbe     short loc_140044BBC
0x140044bb7  mov     rax, [rbx]
0x140044bba  jmp     short loc_140044BBF
0x140044bbc  mov     rax, rbx
0x140044bbf  mov     [rbp+57h+var_A8], rax
0x140044bc3  lea     rdx, word_14008BE26
0x140044bca  lea     rax, aEnter; "Enter"
0x140044bd1  mov     [rbp+57h+var_98], rdi
0x140044bd5  mov     [rbp+57h+var_A0], rax
0x140044bd9  lea     rax, aCmidiendpointp_16; "CMidiEndpointProtocolWorker::UpdateDevi"...
0x140044be0  mov     qword ptr [rbp+57h+var_90], rax
0x140044be4  lea     rax, [rbp+57h+var_A8]
0x140044be8  mov     [rsp+100h+var_C8], rax
0x140044bed  lea     rax, [rbp+57h+var_A0]
0x140044bf1  mov     [rsp+100h+var_D0], rax
0x140044bf6  lea     rax, [rbp+57h+var_98]
0x140044bfa  mov     [rsp+100h+var_D8], rax
0x140044bff  lea     rax, [rbp+57h+var_90]
0x140044c03  mov     qword ptr [rsp+100h+var_E0], rax; int
0x140044c08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140044c0d  mov     ecx, [rsi+4]
0x140044c10  mov     dl, 7Fh
0x140044c12  movzx   eax, word ptr [rsi]
0x140044c15  mov     [rbp+57h+var_C0], ax
0x140044c19  mov     eax, ecx
0x140044c1b  shr     eax, 18h
0x140044c1e  and     al, dl
0x140044c20  mov     [rbp+57h+var_BE], al
0x140044c23  mov     eax, ecx
0x140044c25  shr     eax, 10h
0x140044c28  and     al, dl
0x140044c2a  shr     ecx, 8
0x140044c2d  mov     [rbp+57h+var_BD], al
0x140044c30  and     cl, dl
0x140044c32  mov     al, [rsi+4]
0x140044c35  and     al, dl
0x140044c37  mov     [rbp+57h+var_BC], cl
0x140044c3a  mov     ecx, [rsi+8]
0x140044c3d  mov     [rbp+57h+var_BB], al
0x140044c40  mov     eax, ecx
0x140044c42  shr     eax, 18h
0x140044c45  and     al, dl
0x140044c47  mov     [rbp+57h+var_BA], al
0x140044c4a  mov     eax, ecx
0x140044c4c  shr     eax, 10h
0x140044c4f  and     al, dl
0x140044c51  shr     ecx, 8
0x140044c54  mov     [rbp+57h+var_B9], al
0x140044c57  and     cl, dl
0x140044c59  mov     al, [rsi+8]
0x140044c5c  and     al, dl
0x140044c5e  mov     [rbp+57h+var_B8], cl
0x140044c61  mov     ecx, [rsi+0Ch]
0x140044c64  mov     [rbp+57h+var_B7], al
0x140044c67  mov     eax, ecx
0x140044c69  shr     eax, 18h
0x140044c6c  and     al, dl
0x140044c6e  mov     [rbp+57h+var_B6], al
0x140044c71  mov     eax, ecx
0x140044c73  shr     eax, 10h
0x140044c76  and     al, dl
0x140044c78  shr     ecx, 8
0x140044c7b  mov     [rbp+57h+var_B5], al
0x140044c7e  and     cl, dl
0x140044c80  mov     al, [rsi+0Ch]
0x140044c83  xor     esi, esi
0x140044c85  and     al, dl
0x140044c87  mov     [rbp+57h+var_B4], cl
0x140044c8a  lea     rcx, [rbp+57h+var_B0]
0x140044c8e  mov     [rbp+57h+var_B3], al
0x140044c91  mov     [rbp+57h+var_B0], rsi
0x140044c95  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x140044c9b  cmp     qword ptr [rbx+18h], 7
0x140044ca0  movups  xmm0, cs:PKEY_MIDI_DeviceIdentity
0x140044ca7  mov     eax, cs:dword_14007A888
0x140044cad  mov     rcx, [rdi+0B0h]
0x140044cb4  mov     [rbp+57h+var_70], eax
0x140044cb7  lea     rax, [rbp+57h+var_C0]
0x140044cbb  mov     [rbp+57h+var_58], rax
0x140044cbf  mov     eax, cs:dword_14007A7E0
0x140044cc5  movaps  [rbp+57h+var_80], xmm0
0x140044cc9  movups  xmm0, cs:PKEY_MIDI_DeviceIdentityLastUpdateTime
0x140044cd0  mov     [rbp+57h+var_40], eax
0x140044cd3  lea     rax, [rbp+57h+var_B0]
0x140044cd7  mov     [rbp+57h+var_28], rax
0x140044cdb  movaps  [rbp+57h+var_50], xmm0
0x140044cdf  mov     [rbp+57h+var_6C], esi
0x140044ce2  mov     [rbp+57h+var_68], rsi
0x140044ce6  mov     [rbp+57h+var_60], 1003h
0x140044ced  mov     [rbp+57h+var_5C], 0Eh
0x140044cf4  mov     [rbp+57h+var_3C], esi
0x140044cf7  mov     [rbp+57h+var_38], rsi
0x140044cfb  mov     [rbp+57h+var_30], 10h
0x140044d02  mov     [rbp+57h+var_2C], 8
0x140044d09  mov     rax, [rcx]
0x140044d0c  jbe     short loc_140044D11
0x140044d0e  mov     rbx, [rbx]
0x140044d11  mov     rax, [rax+30h]
0x140044d15  lea     r9, [rbp+57h+var_80]
0x140044d19  mov     r8d, 2
0x140044d1f  mov     rdx, rbx
0x140044d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044d27  mov     ebx, eax
0x140044d29  test    eax, eax
0x140044d2b  jns     short loc_140044D49
0x140044d2d  mov     rcx, [rbp+5Fh]; this
0x140044d31  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140044d38  mov     r9d, eax; char *
0x140044d3b  mov     edx, 5C0h; void *
0x140044d40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044d45  mov     eax, ebx
0x140044d47  jmp     short loc_140044D4B
0x140044d49  xor     eax, eax
0x140044d4b  mov     rcx, [rbp+57h+var_20]
0x140044d4f  xor     rcx, rsp; StackCookie
0x140044d52  call    __security_check_cookie
0x140044d57  mov     rbx, [rsp+100h+arg_10]
0x140044d5f  add     rsp, 0F0h
0x140044d66  pop     rdi
0x140044d67  pop     rsi
0x140044d68  pop     rbp
0x140044d69  retn
```

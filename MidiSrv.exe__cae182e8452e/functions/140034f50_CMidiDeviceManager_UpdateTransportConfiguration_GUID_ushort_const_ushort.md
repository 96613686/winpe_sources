# CMidiDeviceManager::UpdateTransportConfiguration(_GUID,ushort const *,ushort * *)

- ea: `0x140034f50`
- end: `0x1400351ac`
- name: `?UpdateTransportConfiguration@CMidiDeviceManager@@UEAAJU_GUID@@PEBGPEAPEAG@Z`
- size: `604`
- prototype: `__int64 __fastcall(wchar_t *this, struct _GUID *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x14000179c`
- `0x1400018e4`
- `0x140002580`
- `0x1400054c0`
- `0x1400060d4`
- `0x14000984c`
- `0x140034f50`
- `0x14005a010`

## string_xrefs

- `0x14003513d`: `Json is null`
- `0x140034f9e`: `CMidiDeviceManager::UpdateTransportConfiguration`
- `0x14003514c`: `CMidiDeviceManager::UpdateTransportConfiguration`

## pseudocode

```c
__int64 __fastcall CMidiDeviceManager::UpdateTransportConfiguration(
        wchar_t *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  _DWORD *v7; // rcx
  __int64 v8; // rax
  __int64 *v9; // r14
  __int64 *v10; // rbx
  __int64 *i; // rdi
  __int64 v12; // rdi
  unsigned int v13; // ebx
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  _DWORD *v18; // rcx
  int v19; // r8d
  int v20; // r9d
  const char *v21; // [rsp+40h] [rbp-89h] BYREF
  const wchar_t *v22; // [rsp+48h] [rbp-81h] BYREF
  CMidiDeviceManager *v23; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-71h] BYREF
  int v25; // [rsp+6Ch] [rbp-5Dh]
  const char *v26; // [rsp+A0h] [rbp-29h]
  __int64 v27; // [rsp+A8h] [rbp-21h]
  const wchar_t **v28; // [rsp+B0h] [rbp-19h]
  __int64 v29; // [rsp+B8h] [rbp-11h]
  struct _GUID *v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]
  const unsigned __int16 *v32; // [rsp+D0h] [rbp+7h]
  int v33; // [rsp+D8h] [rbp+Fh]
  int v34; // [rsp+DCh] [rbp+13h]

  v21 = (const char *)a4;
  if ( a3 )
  {
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      v22 = this;
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
      v32 = a3;
      v33 = 2 * v8 + 2;
      v34 = 0;
      v30 = a2;
      v31 = 16;
      v28 = &v22;
      v29 = 8;
      v26 = "CMidiDeviceManager::UpdateTransportConfiguration";
      v27 = 49;
      tlgWriteTransfer_EventWriteTransfer(v7, word_14008A5D2, 0, 0);
    }
    v9 = (__int64 *)*((_QWORD *)this + 10);
    v10 = (__int64 *)v9[1];
    v25 = 0;
    for ( i = v9; !*((_BYTE *)v10 + 25); v10 = (__int64 *)*v10 )
    {
      if ( memcmp_0(v10 + 4, a2, 0x10u) >= 0 )
        i = v10;
      else
        v10 += 2;
    }
    if ( *((_BYTE *)i + 25) || memcmp_0(a2, i + 4, 0x10u) < 0 || i == v9 )
    {
      v15 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v15 > 2u )
      {
        v21 = (const char *)a2;
        v22 = L"Failed to find the referenced transport by its GUID";
        v23 = (CMidiDeviceManager *)this;
        v24[0] = "CMidiDeviceManager::UpdateTransportConfiguration";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>>(
          (_DWORD)v15,
          (unsigned int)qword_140088E10,
          v16,
          v17,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21);
      }
    }
    else
    {
      v12 = i[6];
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const char *))(*(_QWORD *)v12 + 32LL))(
                v12,
                a3,
                v21);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return v13;
      }
    }
  }
  else
  {
    v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 2u )
    {
      v24[0] = L"Json is null";
      v23 = (CMidiDeviceManager *)this;
      v21 = "CMidiDeviceManager::UpdateTransportConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v18,
        (unsigned int)&dword_1400891DC,
        v19,
        v20,
        (__int64)&v21,
        (__int64)&v23,
        (__int64)v24);
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x140034f50  mov     [rsp-8+arg_0], rbx
0x140034f55  push    rbp
0x140034f56  push    rsi
0x140034f57  push    rdi
0x140034f58  push    r12
0x140034f5a  push    r13
0x140034f5c  push    r14
0x140034f5e  push    r15
0x140034f60  lea     rbp, [rsp-27h]
0x140034f65  sub     rsp, 0F0h
0x140034f6c  mov     rax, cs:__security_cookie
0x140034f73  xor     rax, rsp
0x140034f76  mov     [rbp+57h+var_40], rax
0x140034f7a  mov     [rsp+120h+var_E0], r9
0x140034f7f  mov     r13, r8
0x140034f82  mov     r12, rdx
0x140034f85  mov     rsi, rcx
0x140034f88  xor     ebx, ebx
0x140034f8a  test    r8, r8
0x140034f8d  jz      loc_14003512D
0x140034f93  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140034f98  mov     rcx, [rax+8]
0x140034f9c  mov     eax, [rcx]
0x140034f9e  lea     r15, aCmidideviceman_10; "CMidiDeviceManager::UpdateTransportConf"...
0x140034fa5  cmp     eax, 4
0x140034fa8  jbe     short loc_14003501B
0x140034faa  mov     [rsp+120h+var_D8], rsi
0x140034faf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140034fb3  inc     rax
0x140034fb6  cmp     [r13+rax*2+0], bx
0x140034fbc  jnz     short loc_140034FB3
0x140034fbe  mov     [rbp+57h+var_50], r13
0x140034fc2  lea     eax, ds:2[rax*2]
0x140034fc9  mov     [rbp+57h+var_48], eax
0x140034fcc  mov     [rbp+57h+var_44], ebx
0x140034fcf  mov     [rbp+57h+var_60], r12
0x140034fd3  mov     [rbp+57h+var_58], 10h
0x140034fdb  lea     rax, [rsp+120h+var_D8]
0x140034fe0  mov     [rbp+57h+var_70], rax
0x140034fe4  mov     [rbp+57h+var_68], 8
0x140034fec  mov     [rbp+57h+var_80], r15
0x140034ff0  mov     [rbp+57h+var_78], 31h ; '1'
0x140034ff8  lea     rax, [rbp+57h+var_A0]
0x140034ffc  mov     [rsp+120h+var_F8], rax
0x140035001  mov     dword ptr [rsp+120h+var_100], 6
0x140035009  xor     r9d, r9d
0x14003500c  xor     r8d, r8d
0x14003500f  lea     rdx, word_14008A5D2
0x140035016  call    _tlgWriteTransfer_EventWriteTransfer
0x14003501b  mov     r14, [rsi+50h]
0x14003501f  mov     rbx, [r14+8]
0x140035023  xor     eax, eax
0x140035025  mov     [rbp+57h+var_B4], eax
0x140035028  mov     rdi, r14
0x14003502b  cmp     [rbx+19h], al
0x14003502e  jnz     short loc_140035058
0x140035030  lea     rcx, [rbx+20h]; Buf1
0x140035034  mov     r8d, 10h; Size
0x14003503a  mov     rdx, r12; Buf2
0x14003503d  call    memcmp_0
0x140035042  test    eax, eax
0x140035044  jns     short loc_14003504C
0x140035046  add     rbx, 10h
0x14003504a  jmp     short loc_14003504F
0x14003504c  mov     rdi, rbx
0x14003504f  mov     rbx, [rbx]
0x140035052  cmp     byte ptr [rbx+19h], 0
0x140035056  jz      short loc_140035030
0x140035058  cmp     byte ptr [rdi+19h], 0
0x14003505c  jnz     short loc_1400350CC
0x14003505e  lea     rdx, [rdi+20h]; Buf2
0x140035062  mov     r8d, 10h; Size
0x140035068  mov     rcx, r12; Buf1
0x14003506b  call    memcmp_0
0x140035070  test    eax, eax
0x140035072  js      short loc_1400350CC
0x140035074  cmp     rdi, r14
0x140035077  jz      short loc_1400350CC
0x140035079  mov     rdi, [rdi+30h]
0x14003507d  test    rdi, rdi
0x140035080  jz      short loc_140035092
0x140035082  mov     rax, [rdi]
0x140035085  mov     rcx, rdi
0x140035088  mov     rax, [rax+8]
0x14003508c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035091  nop
0x140035092  test    rdi, rdi
0x140035095  jz      short loc_1400350C7
0x140035097  mov     rax, [rdi]
0x14003509a  mov     r8, [rsp+120h+var_E0]
0x14003509f  mov     rdx, r13
0x1400350a2  mov     rcx, rdi
0x1400350a5  mov     rax, [rax+20h]
0x1400350a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400350ae  mov     ebx, eax
0x1400350b0  mov     rdx, [rdi]
0x1400350b3  mov     rcx, rdi
0x1400350b6  mov     rax, [rdx+10h]
0x1400350ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400350bf  nop
0x1400350c0  mov     eax, ebx
0x1400350c2  jmp     loc_140035185
0x1400350c7  jmp     loc_140035180
0x1400350cc  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400350d1  mov     rcx, [rax+8]
0x1400350d5  mov     eax, [rcx]
0x1400350d7  cmp     eax, 2
0x1400350da  jbe     loc_140035180
0x1400350e0  mov     [rsp+120h+var_E0], r12
0x1400350e5  lea     rax, aFailedToFindTh; "Failed to find the referenced transport"...
0x1400350ec  mov     [rsp+120h+var_D8], rax
0x1400350f1  mov     [rbp+57h+var_D0], rsi
0x1400350f5  mov     [rbp+57h+var_C8], r15
0x1400350f9  lea     rax, [rsp+120h+var_E0]
0x1400350fe  mov     [rsp+120h+var_E8], rax
0x140035103  lea     rax, [rsp+120h+var_D8]
0x140035108  mov     [rsp+120h+var_F0], rax
0x14003510d  lea     rax, [rbp+57h+var_D0]
0x140035111  mov     [rsp+120h+var_F8], rax
0x140035116  lea     rax, [rbp+57h+var_C8]
0x14003511a  mov     [rsp+120h+var_100], rax
0x14003511f  lea     rdx, qword_140088E10
0x140035126  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &)
0x14003512b  jmp     short loc_140035180
0x14003512d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140035132  mov     rcx, [rax+8]
0x140035136  mov     eax, [rcx]
0x140035138  cmp     eax, 2
0x14003513b  jbe     short loc_140035180
0x14003513d  lea     rax, aJsonIsNull; "Json is null"
0x140035144  mov     [rbp+57h+var_C8], rax
0x140035148  mov     [rbp+57h+var_D0], rsi
0x14003514c  lea     r15, aCmidideviceman_10; "CMidiDeviceManager::UpdateTransportConf"...
0x140035153  mov     [rsp+120h+var_E0], r15
0x140035158  lea     rax, [rbp+57h+var_C8]
0x14003515c  mov     [rsp+120h+var_F0], rax
0x140035161  lea     rax, [rbp+57h+var_D0]
0x140035165  mov     [rsp+120h+var_F8], rax
0x14003516a  lea     rax, [rsp+120h+var_E0]
0x14003516f  mov     [rsp+120h+var_100], rax
0x140035174  lea     rdx, dword_1400891DC
0x14003517b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140035180  mov     eax, 80004005h
0x140035185  mov     rcx, [rbp+57h+var_40]
0x140035189  xor     rcx, rsp; StackCookie
0x14003518c  call    __security_check_cookie
0x140035191  mov     rbx, [rsp+120h+arg_0]
0x140035199  add     rsp, 0F0h
0x1400351a0  pop     r15
0x1400351a2  pop     r14
0x1400351a4  pop     r13
0x1400351a6  pop     r12
0x1400351a8  pop     rdi
0x1400351a9  pop     rsi
0x1400351aa  pop     rbp
0x1400351ab  retn
```

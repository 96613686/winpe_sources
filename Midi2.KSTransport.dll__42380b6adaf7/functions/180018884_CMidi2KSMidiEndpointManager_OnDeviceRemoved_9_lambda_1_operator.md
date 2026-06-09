# _CMidi2KSMidiEndpointManager::OnDeviceRemoved_::_9_::_lambda_1_::operator()

- ea: `0x180018884`
- end: `0x180018a00`
- name: `_CMidi2KSMidiEndpointManager::OnDeviceRemoved_::_9_::_lambda_1_::operator()`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001e630`

## callees

- `0x180001c20`
- `0x1800052fc`
- `0x180005374`
- `0x18000db18`
- `0x1800156e4`
- `0x180018884`
- `0x18001acd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800189df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800189ea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800189df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800189ea`

## string_xrefs

- `0x180018979`: `CMidi2KSMidiEndpointManager::OnDeviceRemoved::<lambda_1>::operator ()`

## pseudocode

```c
char __fastcall CMidi2KSMidiEndpointManager::OnDeviceRemoved_::_9_::_lambda_1_::operator()(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // rbx
  __int64 *v4; // rax
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  wchar_t *v7; // r14
  size_t v8; // r8
  const wchar_t *v9; // rcx
  bool v10; // si
  void *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v14; // rbx
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  void *v18; // rbx
  int v19; // edi
  HANDLE v20; // rax
  LPVOID v22[3]; // [rsp+40h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp+38h] BYREF
  const wchar_t *v24; // [rsp+98h] [rbp+40h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+48h] BYREF
  const char *v26; // [rsp+A8h] [rbp+50h] BYREF

  v2 = *a2;
  v4 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
                    *a1,
                    &lpMem);
  if ( *(_QWORD *)(v2 + 24) <= 7u )
    v5 = (const wchar_t *)v2;
  else
    v5 = *(const wchar_t **)v2;
  v6 = *v4;
  v7 = (wchar_t *)&S1;
  if ( v6 )
  {
    v8 = *(unsigned int *)(v6 + 4);
    v9 = *(const wchar_t **)(v6 + 16);
  }
  else
  {
    v8 = 0;
    v9 = &S1;
  }
  if ( v8 == *(_QWORD *)(v2 + 16) )
  {
    if ( v8 )
      v10 = wmemcmp(v9, v5, v8) == 0;
    else
      v10 = 1;
  }
  else
  {
    v10 = 0;
  }
  v11 = lpMem;
  if ( lpMem )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
    }
  }
  if ( !v10 )
    return 0;
  v14 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    v15 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
            *a1,
            v22);
    if ( *(_QWORD *)v15 )
      v7 = *(wchar_t **)(*(_QWORD *)v15 + 16LL);
    lpMem = v7;
    v24 = L"Removing endpoint / pin entry";
    v25 = a1[1];
    v26 = "CMidi2KSMidiEndpointManager::OnDeviceRemoved::<lambda_1>::operator ()";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v14,
      (unsigned int)byte_1800688B3,
      v16,
      v17,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&lpMem);
    v18 = v22[0];
    if ( v22[0] )
    {
      v19 = _InterlockedDecrement((volatile signed __int32 *)v22[0] + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          abort();
      }
      else
      {
        v20 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v20, 0, v18);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180018884  push    rbp
0x180018886  push    rbx
0x180018887  push    rsi
0x180018888  push    rdi
0x180018889  push    r14
0x18001888b  push    r15
0x18001888d  mov     rbp, rsp
0x180018890  sub     rsp, 58h
0x180018894  mov     rbx, [rdx]
0x180018897  mov     r15, rcx
0x18001889a  mov     rcx, [rcx]
0x18001889d  lea     rdx, [rbp+lpMem]
0x1800188a1  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x1800188a6  cmp     qword ptr [rbx+18h], 7
0x1800188ab  jbe     short loc_1800188B2
0x1800188ad  mov     rdx, [rbx]
0x1800188b0  jmp     short loc_1800188B5
0x1800188b2  mov     rdx, rbx; S2
0x1800188b5  mov     rax, [rax]
0x1800188b8  lea     r14, S1
0x1800188bf  test    rax, rax
0x1800188c2  jz      short loc_1800188CE
0x1800188c4  mov     r8d, [rax+4]
0x1800188c8  mov     rcx, [rax+10h]
0x1800188cc  jmp     short loc_1800188D4
0x1800188ce  xor     r8d, r8d; N
0x1800188d1  mov     rcx, r14; S1
0x1800188d4  cmp     r8, [rbx+10h]
0x1800188d8  jz      short loc_1800188DF
0x1800188da  xor     sil, sil
0x1800188dd  jmp     short loc_1800188F4
0x1800188df  test    r8, r8
0x1800188e2  jnz     short loc_1800188E9
0x1800188e4  mov     sil, 1
0x1800188e7  jmp     short loc_1800188F4
0x1800188e9  call    wmemcmp
0x1800188ee  test    eax, eax
0x1800188f0  setz    sil
0x1800188f4  mov     rbx, [rbp+lpMem]
0x1800188f8  or      edi, 0FFFFFFFFh
0x1800188fb  test    rbx, rbx
0x1800188fe  jz      short loc_180018923
0x180018900  mov     eax, edi
0x180018902  lock xadd [rbx+18h], eax
0x180018907  sub     eax, 1
0x18001890a  jnz     loc_1800189D7
0x180018910  nop
0x180018911  call    WINRT_IMPL_GetProcessHeap
0x180018916  mov     rcx, rax; hHeap
0x180018919  mov     r8, rbx; lpMem
0x18001891c  xor     edx, edx; dwFlags
0x18001891e  call    WINRT_IMPL_HeapFree
0x180018923  test    sil, sil
0x180018926  jz      loc_1800189F1
0x18001892c  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180018931  mov     rbx, [rax+8]
0x180018935  mov     eax, [rbx]
0x180018937  cmp     eax, 4
0x18001893a  jbe     loc_1800189D3
0x180018940  mov     rcx, [r15]
0x180018943  lea     rdx, [rbp+var_18]
0x180018947  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x18001894c  mov     rcx, [rax]
0x18001894f  test    rcx, rcx
0x180018952  jz      short loc_180018958
0x180018954  mov     r14, [rcx+10h]
0x180018958  lea     rax, aRemovingEndpoi; "Removing endpoint / pin entry"
0x18001895f  mov     [rbp+lpMem], r14
0x180018963  mov     [rbp+arg_8], rax
0x180018967  lea     rdx, byte_1800688B3
0x18001896e  mov     rax, [r15+8]
0x180018972  mov     rcx, rbx
0x180018975  mov     [rbp+arg_10], rax
0x180018979  lea     rax, aCmidi2ksmidien_3; "CMidi2KSMidiEndpointManager::OnDeviceRe"...
0x180018980  mov     [rbp+arg_18], rax
0x180018984  lea     rax, [rbp+lpMem]
0x180018988  mov     [rsp+58h+var_20], rax
0x18001898d  lea     rax, [rbp+arg_8]
0x180018991  mov     [rsp+58h+var_28], rax
0x180018996  lea     rax, [rbp+arg_10]
0x18001899a  mov     [rsp+58h+var_30], rax
0x18001899f  lea     rax, [rbp+arg_18]
0x1800189a3  mov     [rsp+58h+var_38], rax
0x1800189a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800189ad  mov     rbx, [rbp+var_18]
0x1800189b1  test    rbx, rbx
0x1800189b4  jz      short loc_1800189D3
0x1800189b6  lock xadd [rbx+18h], edi
0x1800189bb  sub     edi, 1
0x1800189be  jnz     short loc_1800189E6
0x1800189c0  nop
0x1800189c1  call    WINRT_IMPL_GetProcessHeap
0x1800189c6  mov     rcx, rax; hHeap
0x1800189c9  mov     r8, rbx; lpMem
0x1800189cc  xor     edx, edx; dwFlags
0x1800189ce  call    WINRT_IMPL_HeapFree
0x1800189d3  mov     al, 1
0x1800189d5  jmp     short loc_1800189F3
0x1800189d7  test    eax, eax
0x1800189d9  jns     loc_180018923
0x1800189df  call    cs:__imp_abort
0x1800189e6  test    edi, edi
0x1800189e8  jns     short loc_1800189D3
0x1800189ea  call    cs:__imp_abort
0x1800189f1  xor     al, al
0x1800189f3  add     rsp, 58h
0x1800189f7  pop     r15
0x1800189f9  pop     r14
0x1800189fb  pop     rdi
0x1800189fc  pop     rsi
0x1800189fd  pop     rbx
0x1800189fe  pop     rbp
0x1800189ff  retn
```

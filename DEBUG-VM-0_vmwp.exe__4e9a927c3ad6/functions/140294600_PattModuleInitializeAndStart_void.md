# PattModuleInitializeAndStart(void)

- ea: `0x140294600`
- end: `0x14029481f`
- name: `?PattModuleInitializeAndStart@@YAJXZ`
- size: `543`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140065630`

## callees

- `0x1400014a4`
- `0x140002a3c`
- `0x14000dc7c`
- `0x14005611c`
- `0x1402945dc`
- `0x140294600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402946a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402946a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140294701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140294701`
- `ntdll!RtlAllocateHeap` at `0x140294771`
- `ntdll!RtlAllocateHeap` at `0x140294771`

## string_xrefs

- `0x1402946f2`: `ClientDllPath`
- `0x140294680`: `SOFTWARE\Microsoft\Azure\PageAccessTracing`

## pseudocode

```c
__int64 PattModuleInitializeAndStart(void)
{
  DWORD v0; // r8d
  LSTATUS v1; // eax
  signed int v2; // ebx
  BYTE *Heap; // rax
  LSTATUS v4; // eax
  unsigned int v5; // eax
  DWORD v6; // r8d
  int v7; // r9d
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  HKEY *v10; // [rsp+58h] [rbp+18h] BYREF
  LPCWSTR v11; // [rsp+60h] [rbp+20h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1403A9C48);
  if ( (unsigned int)dword_1403A9C48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C48, 1) )
  {
    Type = v0;
    v10 = &PattGlobals;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1403A9C48,
      (unsigned int)byte_1403644BD,
      0,
      0,
      (__int64)&v10,
      (__int64)&Type);
  }
  lpData = 0;
  *(_OWORD *)&PattGlobals = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Azure\\PageAccessTracing", 0, 0x20019u, &PattGlobals);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0xC0070000;
  }
  else
  {
    Heap = (BYTE *)lpData;
    while ( 1 )
    {
      Type = 0;
      v4 = RegQueryValueExW(PattGlobals, L"ClientDllPath", 0, &Type, Heap, (LPDWORD)&PattGlobals + 2);
      v2 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0xC0070000;
      }
      else
      {
        v2 = Type != 1 ? 0xC0000024 : 0;
      }
      if ( lpData && v2 != -1073282838 )
        break;
      v5 = *((_DWORD *)&PattGlobals + 2);
      if ( !*((_DWORD *)&PattGlobals + 2) )
      {
        v2 = -2147483614;
        goto LABEL_23;
      }
      if ( lpData )
      {
        PattHeapFree((void *)lpData);
        v5 = *((_DWORD *)&PattGlobals + 2);
      }
      Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      lpData = (LPCWSTR)Heap;
      if ( !Heap )
      {
        v2 = -1073741801;
        goto LABEL_23;
      }
    }
    if ( v2 >= 0 )
      v2 = 0;
  }
LABEL_23:
  if ( (unsigned int)dword_1403A9C48 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1403A9C48, 1) )
  {
    Type = v6;
    LODWORD(v10) = v2;
    v11 = lpData;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)lpData,
      (unsigned int)byte_140364243,
      v6,
      v7,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&Type);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140294600  mov     [rsp-8+arg_18], rbx
0x140294605  push    rbp
0x140294606  mov     rbp, rsp
0x140294609  sub     rsp, 40h
0x14029460d  lea     rcx, dword_1403A9C48; CallbackContext
0x140294614  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140294619  mov     ecx, cs:dword_1403A9C48
0x14029461f  lea     rbx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; _PAT_THUNK_GLOBALS PattGlobals
0x140294626  mov     r8d, eax
0x140294629  cmp     ecx, 5
0x14029462c  jbe     short loc_140294676
0x14029462e  mov     edx, 1
0x140294633  lea     rcx, dword_1403A9C48
0x14029463a  call    _tlgKeywordOn
0x14029463f  test    al, al
0x140294641  jz      short loc_140294676
0x140294643  lea     rax, [rbp+Type]
0x140294647  mov     [rbp+Type], r8d
0x14029464b  mov     [rsp+40h+lpcbData], rax
0x140294650  lea     rdx, byte_1403644BD
0x140294657  lea     rax, [rbp+arg_8]
0x14029465b  mov     [rbp+arg_8], rbx
0x14029465f  xor     r9d, r9d
0x140294662  mov     [rsp+40h+phkResult], rax
0x140294667  xor     r8d, r8d
0x14029466a  lea     rcx, dword_1403A9C48
0x140294671  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x140294676  xorps   xmm0, xmm0
0x140294679  mov     [rsp+40h+phkResult], rbx; phkResult
0x14029467e  xor     eax, eax
0x140294680  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Azure\\PageAccessT"...
0x140294687  mov     r9d, 20019h; samDesired
0x14029468d  mov     cs:lpData, rax
0x140294694  xor     r8d, r8d; ulOptions
0x140294697  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14029469e  movups  cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A, xmm0; _PAT_THUNK_GLOBALS PattGlobals
0x1402946a5  call    cs:__imp_RegOpenKeyExW
0x1402946ac  nop     dword ptr [rax+rax+00h]
0x1402946b1  mov     ebx, eax
0x1402946b3  test    eax, eax
0x1402946b5  jz      short loc_1402946CD
0x1402946b7  jle     short loc_1402946C2
0x1402946b9  movzx   ebx, ax
0x1402946bc  or      ebx, 0C0070000h
0x1402946c2  mov     r8d, 1000h
0x1402946c8  jmp     loc_1402947B8
0x1402946cd  mov     rax, cs:lpData
0x1402946d4  lea     rcx, ?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x1402946db  mov     [rbp+Type], 0
0x1402946e2  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x1402946e7  lea     r9, [rbp+Type]; lpType
0x1402946eb  mov     rcx, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A; hKey
0x1402946f2  lea     rdx, aClientdllpath; "ClientDllPath"
0x1402946f9  xor     r8d, r8d; lpReserved
0x1402946fc  mov     [rsp+40h+phkResult], rax; lpData
0x140294701  call    cs:__imp_RegQueryValueExW
0x140294708  nop     dword ptr [rax+rax+00h]
0x14029470d  mov     ebx, eax
0x14029470f  test    eax, eax
0x140294711  jz      short loc_140294720
0x140294713  jle     short loc_14029472F
0x140294715  movzx   ebx, ax
0x140294718  or      ebx, 0C0070000h
0x14029471e  jmp     short loc_14029472F
0x140294720  mov     eax, [rbp+Type]
0x140294723  dec     eax
0x140294725  neg     eax
0x140294727  sbb     ebx, ebx
0x140294729  and     ebx, 0C0000024h
0x14029472f  mov     rcx, cs:lpData; void *
0x140294736  test    rcx, rcx
0x140294739  jz      short loc_140294743
0x14029473b  cmp     ebx, 0C00700EAh
0x140294741  jnz     short loc_14029479A
0x140294743  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029474a  test    eax, eax
0x14029474c  jz      short loc_1402947AD
0x14029474e  test    rcx, rcx
0x140294751  jz      short loc_14029475F
0x140294753  call    ?PattHeapFree@@YAXPEAX@Z; PattHeapFree(void *)
0x140294758  mov     rax, qword ptr cs:?PattGlobals@@3U_PAT_THUNK_GLOBALS@@A+8; _PAT_THUNK_GLOBALS PattGlobals
0x14029475f  mov     rcx, gs:60h
0x140294768  xor     edx, edx; Flags
0x14029476a  mov     r8d, eax; Size
0x14029476d  mov     rcx, [rcx+30h]; HeapHandle
0x140294771  call    cs:__imp_RtlAllocateHeap
0x140294778  nop     dword ptr [rax+rax+00h]
0x14029477d  mov     cs:lpData, rax
0x140294784  test    rax, rax
0x140294787  jnz     loc_1402946D4
0x14029478d  mov     ebx, 0C0000017h
0x140294792  mov     r8d, 3000h
0x140294798  jmp     short loc_1402947B8
0x14029479a  test    ebx, ebx
0x14029479c  jns     short loc_1402947A6
0x14029479e  mov     r8d, 4000h
0x1402947a4  jmp     short loc_1402947B8
0x1402947a6  xor     ebx, ebx
0x1402947a8  xor     r8d, r8d
0x1402947ab  jmp     short loc_1402947B8
0x1402947ad  mov     ebx, 80000022h
0x1402947b2  mov     r8d, 2000h
0x1402947b8  mov     eax, cs:dword_1403A9C48
0x1402947be  cmp     eax, 5
0x1402947c1  jbe     short loc_140294811
0x1402947c3  mov     edx, 1
0x1402947c8  lea     rcx, dword_1403A9C48
0x1402947cf  call    _tlgKeywordOn
0x1402947d4  test    al, al
0x1402947d6  jz      short loc_140294811
0x1402947d8  mov     rcx, cs:lpData
0x1402947df  lea     rax, [rbp+Type]
0x1402947e3  mov     [rsp+40h+var_10], rax
0x1402947e8  lea     rdx, byte_140364243
0x1402947ef  lea     rax, [rbp+arg_8]
0x1402947f3  mov     [rbp+Type], r8d
0x1402947f7  mov     [rsp+40h+lpcbData], rax
0x1402947fc  lea     rax, [rbp+arg_10]
0x140294800  mov     [rsp+40h+phkResult], rax
0x140294805  mov     dword ptr [rbp+arg_8], ebx
0x140294808  mov     [rbp+arg_10], rcx
0x14029480c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140294811  mov     eax, ebx
0x140294813  mov     rbx, [rsp+40h+arg_18]
0x140294818  add     rsp, 40h
0x14029481c  pop     rbp
0x14029481d  retn
```

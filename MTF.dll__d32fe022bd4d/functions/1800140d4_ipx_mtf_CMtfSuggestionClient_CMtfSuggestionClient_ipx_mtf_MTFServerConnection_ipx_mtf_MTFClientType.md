# ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(ipx::mtf::MTFServerConnection,ipx::mtf::MTFClientType)

- ea: `0x1800140d4`
- end: `0x180014252`
- name: `??0CMtfSuggestionClient@mtf@ipx@@QEAA@W4MTFServerConnection@12@W4MTFClientType@12@@Z`
- size: `382`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001d120`
- `0x18001d190`
- `0x18001e260`
- `0x18001e2e0`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x1800140d4`
- `0x18001e224`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001413a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001413a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800141dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800141dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800141c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800141c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::CMtfSuggestionClient(__int64 a1, char a2, char a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  int v8; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)(a1 + 40) = 1;
  *(_QWORD *)a1 = &ipx::mtf::CMtfSuggestionClient::`vftable';
  *(_QWORD *)(a1 + 8) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfDataSourceManagement2'};
  *(_QWORD *)(a1 + 16) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'};
  *(_QWORD *)(a1 + 24) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfTransportClient'};
  *(_QWORD *)(a1 + 32) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'};
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 64), 0, 0);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_BYTE *)(a1 + 144) = a3;
  *(_BYTE *)(a1 + 145) = a2;
  *(_BYTE *)(a1 + 146) = a2;
  *(_BYTE *)(a1 + 147) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  v6 = (_QWORD *)(a1 + 160);
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  v7 = operator new(0x10u);
  if ( !v7 )
    std::_Xbad_alloc();
  *v6 = v7;
  *v7 = 0;
  v7[1] = 0;
  *(_QWORD *)*v6 = v6;
  *(_DWORD *)(a1 + 200) = GetCurrentThreadId();
  *(_WORD *)(a1 + 204) = GetTickCount64();
  _InterlockedIncrement(&g_cRefDll);
  *(_DWORD *)(a1 + 48) = GetCurrentProcessId();
  *(_DWORD *)(a1 + 52) = GetCurrentThreadId();
  *(_WORD *)(a1 + 56) = 0;
  v8 = ((__int64 (__fastcall *)(GUID *, __int64, _QWORD, GUID *))Hooked_CoGetClassObject)(
         &CLSID_MtfPropertyBag,
         1,
         0,
         &GUID_00000001_0000_0000_c000_000000000046);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v8,
      a1 + 104);
  return a1;
}

```

## disassembly

```asm
0x1800140d4  mov     [rsp+arg_8], rbx
0x1800140d9  mov     [rsp+arg_10], rbp
0x1800140de  mov     [rsp+arg_0], rcx
0x1800140e3  push    rsi
0x1800140e4  push    rdi
0x1800140e5  push    r14
0x1800140e7  sub     rsp, 30h
0x1800140eb  mov     bl, r8b
0x1800140ee  mov     dil, dl
0x1800140f1  mov     rsi, rcx
0x1800140f4  mov     dword ptr [rcx+28h], 1
0x1800140fb  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B@; const ipx::mtf::CMtfSuggestionClient::`vftable'
0x180014102  mov     [rcx], rax
0x180014105  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6BIMtfDataSourceManagement2@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfDataSourceManagement2'}
0x18001410c  mov     [rcx+8], rax
0x180014110  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@XX@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'}
0x180014117  mov     [rcx+10h], rax
0x18001411b  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6BIMtfTransportClient@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfTransportClient'}
0x180014122  mov     [rcx+18h], rax
0x180014126  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfRoamingWordsClient@@XXXX@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'}
0x18001412d  mov     [rcx+20h], rax
0x180014131  add     rcx, 40h ; '@'; lpCriticalSection
0x180014135  xor     r8d, r8d; Flags
0x180014138  xor     edx, edx; dwSpinCount
0x18001413a  call    cs:__imp_InitializeCriticalSectionEx
0x180014140  nop
0x180014141  lea     r14, [rsi+68h]
0x180014145  xor     ebp, ebp
0x180014147  mov     [r14], rbp
0x18001414a  mov     [rsi+70h], rbp
0x18001414e  mov     [rsi+78h], rbp
0x180014152  mov     [rsi+80h], rbp
0x180014159  mov     [rsi+88h], rbp
0x180014160  mov     [rsi+90h], bl
0x180014166  mov     [rsi+91h], dil
0x18001416d  mov     [rsi+92h], dil
0x180014174  mov     [rsi+93h], bpl
0x18001417b  mov     [rsi+98h], rbp
0x180014182  lea     rbx, [rsi+0A0h]
0x180014189  mov     [rbx], rbp
0x18001418c  mov     [rbx+8], rbp
0x180014190  mov     [rbx+10h], rbp
0x180014194  mov     [rbx+18h], rbp
0x180014198  mov     [rbx+20h], rbp
0x18001419c  lea     ecx, [rbp+10h]; Size
0x18001419f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800141a4  test    rax, rax
0x1800141a7  jz      loc_18001424C
0x1800141ad  mov     [rbx], rax
0x1800141b0  mov     [rax], rbp
0x1800141b3  mov     [rax+8], rbp
0x1800141b7  mov     rax, [rbx]
0x1800141ba  mov     [rax], rbx
0x1800141bd  call    cs:__imp_GetCurrentThreadId
0x1800141c3  mov     [rsi+0C8h], eax
0x1800141c9  call    cs:__imp_GetTickCount64
0x1800141cf  mov     [rsi+0CCh], ax
0x1800141d6  lock inc cs:?g_cRefDll@@3JA; long g_cRefDll
0x1800141dd  call    cs:__imp_GetCurrentProcessId
0x1800141e3  mov     [rsi+30h], eax
0x1800141e6  call    cs:__imp_GetCurrentThreadId
0x1800141ec  mov     [rsi+34h], eax
0x1800141ef  mov     [rsi+38h], bp
0x1800141f3  mov     qword ptr [rsp+48h+var_28], r14; int
0x1800141f8  lea     r9, _GUID_00000001_0000_0000_c000_000000000046
0x1800141ff  xor     r8d, r8d
0x180014202  lea     edx, [rbp+1]
0x180014205  lea     rcx, CLSID_MtfPropertyBag
0x18001420c  mov     rax, cs:?Hooked_CoGetClassObject@@3P6AJAEBU_GUID@@KPEAX0PEAPEAX@ZEA; long (*Hooked_CoGetClassObject)(_GUID const &,ulong,void *,_GUID const &,void * *)
0x180014213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014218  mov     rcx, [rsp+48h]; this
0x18001421d  test    eax, eax
0x18001421f  js      short loc_180014237
0x180014221  mov     rax, rsi
0x180014224  mov     rbx, [rsp+48h+arg_8]
0x180014229  mov     rbp, [rsp+48h+arg_10]
0x18001422e  add     rsp, 30h
0x180014232  pop     r14
0x180014234  pop     rdi
0x180014235  pop     rsi
0x180014236  retn
0x180014237  mov     r9d, eax; char *
0x18001423a  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180014241  mov     edx, 68h ; 'h'; void *
0x180014246  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001424c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

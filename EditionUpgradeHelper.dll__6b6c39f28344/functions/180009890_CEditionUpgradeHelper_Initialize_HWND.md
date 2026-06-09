# CEditionUpgradeHelper::Initialize(HWND__ *)

- ea: `0x180009890`
- end: `0x180009902`
- name: `?Initialize@CEditionUpgradeHelper@@UEAAJPEAUHWND__@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(LPVOID *this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008c60`
- `0x180009890`
- `0x180009978`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800098bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800098bf`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeHelper::Initialize(LPVOID *this, HWND a2)
{
  _QWORD *v2; // rsi
  unsigned int v3; // edi
  HRESULT Instance; // eax
  unsigned int v5; // ebx

  v2 = this + 4;
  v3 = (unsigned int)a2;
  Instance = CoCreateInstance(&CLSID_EditionUpgradeBroker, 0, 4u, &GUID_ff19cbcf_9455_4937_b872_6b7929a460af, this + 4);
  v5 = Instance;
  if ( Instance < 0
    || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, v3),
        v5 = Instance,
        Instance < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Instance);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x180009890  mov     [rsp+arg_0], rbx
0x180009895  mov     [rsp+arg_8], rsi
0x18000989a  push    rdi
0x18000989b  sub     rsp, 30h
0x18000989f  lea     rsi, [rcx+20h]
0x1800098a3  mov     rdi, rdx
0x1800098a6  xor     edx, edx; pUnkOuter
0x1800098a8  mov     [rsp+38h+ppv], rsi; ppv
0x1800098ad  lea     r9, _GUID_ff19cbcf_9455_4937_b872_6b7929a460af; riid
0x1800098b4  lea     rcx, CLSID_EditionUpgradeBroker; rclsid
0x1800098bb  lea     r8d, [rdx+4]; dwClsContext
0x1800098bf  call    cs:__imp_CoCreateInstance
0x1800098c5  mov     ebx, eax
0x1800098c7  test    eax, eax
0x1800098c9  js      short loc_1800098E2
0x1800098cb  mov     rcx, [rsi]
0x1800098ce  mov     edx, edi
0x1800098d0  mov     rax, [rcx]
0x1800098d3  mov     rax, [rax+18h]
0x1800098d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098dc  mov     ebx, eax
0x1800098de  test    eax, eax
0x1800098e0  jns     short loc_1800098E9
0x1800098e2  mov     ecx, eax
0x1800098e4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800098e9  mov     ecx, ebx
0x1800098eb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800098f0  mov     rsi, [rsp+38h+arg_8]
0x1800098f5  mov     eax, ebx
0x1800098f7  mov     rbx, [rsp+38h+arg_0]
0x1800098fc  add     rsp, 30h
0x180009900  pop     rdi
0x180009901  retn
```

# GetFlightingConfigValues(ushort * *,ushort * *)

- ea: `0x18001b5fc`
- end: `0x18001b859`
- name: `?GetFlightingConfigValues@@YAJPEAPEAG0@Z`
- size: `605`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ae10`

## callees

- `0x18001b5fc`
- `0x1800543c0`
- `0x18006a010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18001b641`
- `ole32!CoInitializeEx` at `0x18001b641`
- `ole32!CoCreateInstance` at `0x18001b694`
- `ole32!CoCreateInstance` at `0x18001b694`
- `ole32!CoUninitialize` at `0x18001b83d`
- `ole32!CoUninitialize` at `0x18001b83d`

## string_xrefs

- `0x18001b65e`: `GetFlightingConfigValues`
- `0x18001b6b1`: `GetFlightingConfigValues`
- `0x18001b708`: `GetFlightingConfigValues`
- `0x18001b748`: `GetFlightingConfigValues`
- `0x18001b7a3`: `GetFlightingConfigValues`
- `0x18001b7fb`: `GetFlightingConfigValues`
- `0x18001b6a4`: `CoCreateInstance failed 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetFlightingConfigValues(unsigned __int16 **a1, unsigned __int16 **a2)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int16 v11; // [rsp+60h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF

  v11 = 0;
  if ( __PAIR128__((unsigned __int64)a1, (unsigned __int64)a2) == 0 )
    return 2147500037LL;
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    ppv = 0;
    v7 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
    v6 = v7;
    if ( v7 )
    {
      AslLogCallPrintf(3, "GetFlightingConfigValues", 75, "CoCreateInstance failed 0x%x", v7);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, &v11);
      v6 = v8;
      if ( v8 )
      {
        AslLogCallPrintf(1, "GetFlightingConfigValues", 82, "IsFlightingEnabled failed 0x%x", v8);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      else if ( v11 )
      {
        if ( a1
          && (v9 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 **))(*(_QWORD *)ppv + 48LL))(ppv, a1),
              (v6 = v9) != 0) )
        {
          AslLogCallPrintf(1, "GetFlightingConfigValues", 97, "GetRingNameAlloc failed 0x%x", v9);
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        else if ( a2
               && (v10 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 **))(*(_QWORD *)ppv + 80LL))(ppv, a2),
                   (v6 = v10) != 0) )
        {
          AslLogCallPrintf(1, "GetFlightingConfigValues", 107, "GetBranchNameAlloc failed 0x%x", v10);
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        else
        {
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          v6 = 0;
        }
      }
      else
      {
        AslLogCallPrintf(3, "GetFlightingConfigValues", 88, "Flighting is not enabled, return");
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    CoUninitialize();
  }
  else
  {
    AslLogCallPrintf(1, "GetFlightingConfigValues", 62, "CoInitializeEx failed 0x%x", v5);
  }
  return v6;
}

```

## disassembly

```asm
0x18001b5fc  push    rbp
0x18001b5fe  push    r14
0x18001b600  push    r15
0x18001b602  mov     rbp, rsp
0x18001b605  sub     rsp, 40h
0x18001b609  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18001b611  mov     [rsp+40h+arg_8], rbx
0x18001b616  mov     [rsp+40h+arg_18], rsi
0x18001b61b  mov     rsi, rdx
0x18001b61e  mov     r14, rcx
0x18001b621  xor     r15d, r15d
0x18001b624  mov     [rbp+arg_0], r15w
0x18001b629  test    rcx, rcx
0x18001b62c  jnz     short loc_18001B63D
0x18001b62e  test    rdx, rdx
0x18001b631  jnz     short loc_18001B63D
0x18001b633  mov     eax, 80004005h
0x18001b638  jmp     loc_18001B845
0x18001b63d  xor     edx, edx; dwCoInit
0x18001b63f  xor     ecx, ecx; pvReserved
0x18001b641  call    cs:__imp_CoInitializeEx
0x18001b647  mov     ebx, eax
0x18001b649  test    eax, eax
0x18001b64b  jns     short loc_18001B673
0x18001b64d  mov     dword ptr [rsp+40h+ppv], eax
0x18001b651  lea     r9, aCoinitializeex; "CoInitializeEx failed 0x%x"
0x18001b658  mov     r8d, 3Eh ; '>'
0x18001b65e  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b665  lea     ecx, [r8-3Dh]
0x18001b669  call    AslLogCallPrintf
0x18001b66e  jmp     loc_18001B843
0x18001b673  mov     [rbp+arg_10], r15
0x18001b677  lea     rax, [rbp+arg_10]
0x18001b67b  mov     [rsp+40h+ppv], rax; ppv
0x18001b680  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x18001b687  xor     edx, edx; pUnkOuter
0x18001b689  lea     r8d, [rdx+1]; dwClsContext
0x18001b68d  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x18001b694  call    cs:__imp_CoCreateInstance
0x18001b69a  mov     ebx, eax
0x18001b69c  test    eax, eax
0x18001b69e  jz      short loc_18001B6DD
0x18001b6a0  mov     dword ptr [rsp+40h+ppv], eax
0x18001b6a4  lea     r9, aCocreateinstan; "CoCreateInstance failed 0x%x"
0x18001b6ab  mov     r8d, 4Bh ; 'K'
0x18001b6b1  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b6b8  lea     ecx, [r8-48h]
0x18001b6bc  call    AslLogCallPrintf
0x18001b6c1  nop
0x18001b6c2  mov     rcx, [rbp+arg_10]
0x18001b6c6  test    rcx, rcx
0x18001b6c9  jz      short loc_18001B6D8
0x18001b6cb  mov     rax, [rcx]
0x18001b6ce  mov     rax, [rax+10h]
0x18001b6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6d7  nop
0x18001b6d8  jmp     loc_18001B83D
0x18001b6dd  mov     rcx, [rbp+arg_10]
0x18001b6e1  mov     rax, [rcx]
0x18001b6e4  lea     rdx, [rbp+arg_0]
0x18001b6e8  mov     rax, [rax+18h]
0x18001b6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6f1  mov     ebx, eax
0x18001b6f3  test    eax, eax
0x18001b6f5  jz      short loc_18001B734
0x18001b6f7  mov     dword ptr [rsp+40h+ppv], eax
0x18001b6fb  lea     r9, aIsflightingena; "IsFlightingEnabled failed 0x%x"
0x18001b702  mov     r8d, 52h ; 'R'
0x18001b708  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b70f  lea     ecx, [r8-51h]
0x18001b713  call    AslLogCallPrintf
0x18001b718  nop
0x18001b719  mov     rcx, [rbp+arg_10]
0x18001b71d  test    rcx, rcx
0x18001b720  jz      short loc_18001B72F
0x18001b722  mov     rax, [rcx]
0x18001b725  mov     rax, [rax+10h]
0x18001b729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b72e  nop
0x18001b72f  jmp     loc_18001B83D
0x18001b734  cmp     [rbp+arg_0], r15w
0x18001b739  jnz     short loc_18001B774
0x18001b73b  lea     r9, aFlightingIsNot; "Flighting is not enabled, return"
0x18001b742  mov     r8d, 58h ; 'X'
0x18001b748  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b74f  lea     ecx, [r8-55h]
0x18001b753  call    AslLogCallPrintf
0x18001b758  nop
0x18001b759  mov     rcx, [rbp+arg_10]
0x18001b75d  test    rcx, rcx
0x18001b760  jz      short loc_18001B76F
0x18001b762  mov     rax, [rcx]
0x18001b765  mov     rax, [rax+10h]
0x18001b769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b76e  nop
0x18001b76f  jmp     loc_18001B83D
0x18001b774  test    r14, r14
0x18001b777  jz      short loc_18001B7CC
0x18001b779  mov     rcx, [rbp+arg_10]
0x18001b77d  mov     rax, [rcx]
0x18001b780  mov     rdx, r14
0x18001b783  mov     rax, [rax+30h]
0x18001b787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b78c  mov     ebx, eax
0x18001b78e  test    eax, eax
0x18001b790  jz      short loc_18001B7CC
0x18001b792  mov     dword ptr [rsp+40h+ppv], eax
0x18001b796  lea     r9, aGetringnameall; "GetRingNameAlloc failed 0x%x"
0x18001b79d  mov     r8d, 61h ; 'a'
0x18001b7a3  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b7aa  lea     ecx, [r8-60h]
0x18001b7ae  call    AslLogCallPrintf
0x18001b7b3  nop
0x18001b7b4  mov     rcx, [rbp+arg_10]
0x18001b7b8  test    rcx, rcx
0x18001b7bb  jz      short loc_18001B7CA
0x18001b7bd  mov     rax, [rcx]
0x18001b7c0  mov     rax, [rax+10h]
0x18001b7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7c9  nop
0x18001b7ca  jmp     short loc_18001B83D
0x18001b7cc  test    rsi, rsi
0x18001b7cf  jz      short loc_18001B824
0x18001b7d1  mov     rcx, [rbp+arg_10]
0x18001b7d5  mov     rax, [rcx]
0x18001b7d8  mov     rdx, rsi
0x18001b7db  mov     rax, [rax+50h]
0x18001b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e4  mov     ebx, eax
0x18001b7e6  test    eax, eax
0x18001b7e8  jz      short loc_18001B824
0x18001b7ea  mov     dword ptr [rsp+40h+ppv], eax
0x18001b7ee  lea     r9, aGetbranchnamea; "GetBranchNameAlloc failed 0x%x"
0x18001b7f5  mov     r8d, 6Bh ; 'k'
0x18001b7fb  lea     rdx, aGetflightingco; "GetFlightingConfigValues"
0x18001b802  lea     ecx, [r8-6Ah]
0x18001b806  call    AslLogCallPrintf
0x18001b80b  nop
0x18001b80c  mov     rcx, [rbp+arg_10]
0x18001b810  test    rcx, rcx
0x18001b813  jz      short loc_18001B822
0x18001b815  mov     rax, [rcx]
0x18001b818  mov     rax, [rax+10h]
0x18001b81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b821  nop
0x18001b822  jmp     short loc_18001B83D
0x18001b824  mov     rcx, [rbp+arg_10]
0x18001b828  test    rcx, rcx
0x18001b82b  jz      short loc_18001B83A
0x18001b82d  mov     rax, [rcx]
0x18001b830  mov     rax, [rax+10h]
0x18001b834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b839  nop
0x18001b83a  mov     ebx, r15d
0x18001b83d  call    cs:__imp_CoUninitialize
0x18001b843  mov     eax, ebx
0x18001b845  mov     rbx, [rsp+40h+arg_8]
0x18001b84a  mov     rsi, [rsp+40h+arg_18]
0x18001b84f  add     rsp, 40h
0x18001b853  pop     r15
0x18001b855  pop     r14
0x18001b857  pop     rbp
0x18001b858  retn
```

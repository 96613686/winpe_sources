# RunIOAVPlugin(ushort const *,ushort const *,ushort const *)

- ea: `0x14000415c`
- end: `0x1400042b1`
- name: `?RunIOAVPlugin@@YAJPEBG00@Z`
- size: `341`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400054fc`

## callees

- `0x140001600`
- `0x1400038ec`
- `0x14000415c`
- `0x140004a2c`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000420b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000420b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000428a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000428a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000418c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000418c`
- `RPCRT4!UuidFromStringW` at `0x1400041bd`
- `RPCRT4!UuidFromStringW` at `0x1400041bd`

## string_xrefs

- `0x14000419a`: `onecoreuap\inetcore\spartan\desktopbroker\ioav.cpp`
- `0x1400041cb`: `onecoreuap\inetcore\spartan\desktopbroker\ioav.cpp`

## pseudocode

```c
__int64 __fastcall RunIOAVPlugin(RPC_WSTR StringUuid, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HRESULT v6; // eax
  RPC_STATUS v7; // eax
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v12; // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+38h] [rbp-48h] BYREF
  int v14; // [rsp+3Ch] [rbp-44h]
  __int64 v15; // [rsp+40h] [rbp-40h]
  const unsigned __int16 *v16; // [rsp+48h] [rbp-38h]
  const wchar_t *v17; // [rsp+50h] [rbp-30h]
  const unsigned __int16 *v18; // [rsp+58h] [rbp-28h]
  UUID Uuid; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v6 = CoInitializeEx(0, 2u);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\ioav.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  Uuid = 0;
  v7 = UuidFromStringW(StringUuid, &Uuid);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\ioav.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v12 = 0;
  Microsoft::WRL::ComPtr<IOfficeAntiVirus>::InternalRelease(&v12);
  v8 = CoCreateInstance(&Uuid, 0, 1u, &IID_IOfficeAntiVirus, &v12);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -2147221164 || v8 == -2147467262 || v8 == -2147024770 )
      v9 = 0;
  }
  else
  {
    v15 = 0;
    v17 = L"EDGE";
    v13 = 40;
    v16 = a2;
    if ( a3 )
    {
      v14 = 9;
      v18 = a3;
    }
    else
    {
      v14 = 1;
      v18 = a2;
    }
    v9 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v12 + 24LL))(v12, &v13);
  }
  Microsoft::WRL::ComPtr<IOfficeAntiVirus>::InternalRelease(&v12);
  CoUninitialize();
  return v9;
}

```

## disassembly

```asm
0x14000415c  mov     [rsp-18h+arg_18], rbx
0x140004161  push    rbp
0x140004162  push    rsi
0x140004163  push    rdi
0x140004164  mov     rbp, rsp
0x140004167  sub     rsp, 80h
0x14000416e  mov     rax, cs:__security_cookie
0x140004175  xor     rax, rsp
0x140004178  mov     [rbp+var_10], rax
0x14000417c  mov     rsi, rdx
0x14000417f  mov     rbx, rcx
0x140004182  mov     edx, 2; dwCoInit
0x140004187  xor     ecx, ecx; pvReserved
0x140004189  mov     rdi, r8
0x14000418c  call    cs:__imp_CoInitializeEx
0x140004192  test    eax, eax
0x140004194  jns     short loc_1400041AF
0x140004196  mov     rcx, [rbp+18h]; this
0x14000419a  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400041a1  mov     r9d, eax; char *
0x1400041a4  mov     edx, 19h; void *
0x1400041a9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400041af  xorps   xmm0, xmm0
0x1400041b2  lea     rdx, [rbp+Uuid]; Uuid
0x1400041b6  mov     rcx, rbx; StringUuid
0x1400041b9  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1400041bd  call    cs:__imp_UuidFromStringW
0x1400041c3  test    eax, eax
0x1400041c5  jns     short loc_1400041E0
0x1400041c7  mov     rcx, [rbp+18h]; this
0x1400041cb  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400041d2  mov     r9d, eax; char *
0x1400041d5  mov     edx, 1Ch; void *
0x1400041da  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400041e0  lea     rcx, [rbp+var_50]
0x1400041e4  mov     [rbp+var_50], 0
0x1400041ec  call    ?InternalRelease@?$ComPtr@UIOfficeAntiVirus@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfficeAntiVirus>::InternalRelease(void)
0x1400041f1  xor     edx, edx; pUnkOuter
0x1400041f3  lea     rax, [rbp+var_50]
0x1400041f7  lea     r9, IID_IOfficeAntiVirus; riid
0x1400041fe  mov     qword ptr [rsp+80h+ppv], rax; ppv
0x140004203  lea     rcx, [rbp+Uuid]; rclsid
0x140004207  lea     r8d, [rdx+1]; dwClsContext
0x14000420b  call    cs:__imp_CoCreateInstance
0x140004211  mov     ebx, eax
0x140004213  test    eax, eax
0x140004215  js      short loc_14000426A
0x140004217  mov     [rbp+var_40], 0
0x14000421f  lea     rax, aEdge; "EDGE"
0x140004226  mov     [rbp+var_30], rax
0x14000422a  mov     [rbp+var_48], 28h ; '('
0x140004231  mov     [rbp+var_38], rsi
0x140004235  test    rdi, rdi
0x140004238  jz      short loc_140004247
0x14000423a  mov     [rbp+var_44], 9
0x140004241  mov     [rbp+var_28], rdi
0x140004245  jmp     short loc_140004252
0x140004247  mov     [rbp+var_44], 1
0x14000424e  mov     [rbp+var_28], rsi
0x140004252  mov     rcx, [rbp+var_50]
0x140004256  lea     rdx, [rbp+var_48]
0x14000425a  mov     rax, [rcx]
0x14000425d  mov     rax, [rax+18h]
0x140004261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004266  mov     ebx, eax
0x140004268  jmp     short loc_140004281
0x14000426a  cmp     eax, 80040154h
0x14000426f  jz      short loc_14000427F
0x140004271  cmp     eax, 80004002h
0x140004276  jz      short loc_14000427F
0x140004278  cmp     eax, 8007007Eh
0x14000427d  jnz     short loc_140004281
0x14000427f  xor     ebx, ebx
0x140004281  lea     rcx, [rbp+var_50]
0x140004285  call    ?InternalRelease@?$ComPtr@UIOfficeAntiVirus@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfficeAntiVirus>::InternalRelease(void)
0x14000428a  call    cs:__imp_CoUninitialize
0x140004290  mov     eax, ebx
0x140004292  mov     rcx, [rbp+var_10]
0x140004296  xor     rcx, rsp; StackCookie
0x140004299  call    __security_check_cookie
0x14000429e  mov     rbx, [rsp+80h+arg_18]
0x1400042a6  add     rsp, 80h
0x1400042ad  pop     rdi
0x1400042ae  pop     rsi
0x1400042af  pop     rbp
0x1400042b0  retn
```

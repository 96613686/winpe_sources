# MitigationStateUtils::IsPreviewBuild(bool *)

- ea: `0x1800301d4`
- end: `0x1800302db`
- name: `?IsPreviewBuild@MitigationStateUtils@@SAJPEA_N@Z`
- size: `263`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040f18`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x1800301d4`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030245`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030245`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MitigationStateUtils::IsPreviewBuild(bool *a1)
{
  int v2; // ebx
  bool v3; // si
  HRESULT v4; // eax
  __int16 v5; // ax
  int ppv; // [rsp+20h] [rbp-10h]
  int ppva; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int16 v10; // [rsp+60h] [rbp+30h] BYREF
  __int16 v11; // [rsp+68h] [rbp+38h] BYREF
  LPVOID v12; // [rsp+70h] [rbp+40h] BYREF

  if ( a1 )
  {
    v11 = 0;
    v10 = 0;
    v12 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
    v3 = 1;
    v4 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v12);
    v2 = v4;
    if ( v4 >= 0 )
    {
      if ( (*(int (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 24LL))(v12, &v11) < 0 )
        v11 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v12 + 112LL))(v12, &v10);
      if ( v2 >= 0 )
      {
        v5 = v10;
      }
      else
      {
        v5 = -1;
        v10 = -1;
        v2 = 0;
      }
      if ( v11 != -1 && v5 )
        v3 = 0;
      *a1 = v3;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationstateutils.cpp",
        (const char *)(unsigned int)v4,
        ppva);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
  }
  else
  {
    v2 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationstateutils.cpp",
      (const char *)0x80070057LL,
      ppv);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800301d4  push    rbp
0x1800301d6  push    rbx
0x1800301d7  push    rsi
0x1800301d8  push    rdi
0x1800301d9  push    r14
0x1800301db  mov     rbp, rsp
0x1800301de  sub     rsp, 30h
0x1800301e2  mov     rdi, rcx
0x1800301e5  xor     r14d, r14d
0x1800301e8  test    rcx, rcx
0x1800301eb  jnz     short loc_18003020D
0x1800301ed  mov     rcx, [rbp+28h]; this
0x1800301f1  mov     ebx, 80070057h
0x1800301f6  mov     r9d, ebx; char *
0x1800301f9  lea     r8, aOnecoreBaseDia_25; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180030200  lea     edx, [rdi+39h]; void *
0x180030203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030208  jmp     loc_1800302CE
0x18003020d  mov     [rbp+arg_8], r14w
0x180030212  mov     [rbp+arg_0], r14w
0x180030217  mov     [rbp+arg_10], r14
0x18003021b  lea     rcx, [rbp+arg_10]
0x18003021f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030224  lea     rax, [rbp+arg_10]
0x180030228  mov     qword ptr [rsp+30h+ppv], rax; int
0x18003022d  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180030234  mov     esi, 1
0x180030239  mov     r8d, esi; dwClsContext
0x18003023c  xor     edx, edx; pUnkOuter
0x18003023e  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180030245  call    cs:__imp_CoCreateInstance
0x18003024b  mov     ebx, eax
0x18003024d  test    eax, eax
0x18003024f  jns     short loc_18003026A
0x180030251  mov     rcx, [rbp+28h]; this
0x180030255  mov     r9d, eax; char *
0x180030258  lea     r8, aOnecoreBaseDia_25; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003025f  lea     edx, [rsi+3Eh]; void *
0x180030262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030267  nop
0x180030268  jmp     short loc_1800302C5
0x18003026a  mov     rcx, [rbp+arg_10]
0x18003026e  mov     rax, [rcx]
0x180030271  lea     rdx, [rbp+arg_8]
0x180030275  mov     rax, [rax+18h]
0x180030279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003027e  test    eax, eax
0x180030280  jns     short loc_180030287
0x180030282  mov     [rbp+arg_8], r14w
0x180030287  mov     rcx, [rbp+arg_10]
0x18003028b  mov     rax, [rcx]
0x18003028e  lea     rdx, [rbp+arg_0]
0x180030292  mov     rax, [rax+70h]
0x180030296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003029b  mov     ebx, eax
0x18003029d  or      ecx, 0FFFFFFFFh
0x1800302a0  test    eax, eax
0x1800302a2  jns     short loc_1800302B0
0x1800302a4  movzx   eax, cx
0x1800302a7  mov     [rbp+arg_0], cx
0x1800302ab  mov     ebx, r14d
0x1800302ae  jmp     short loc_1800302B4
0x1800302b0  movzx   eax, [rbp+arg_0]
0x1800302b4  cmp     [rbp+arg_8], cx
0x1800302b8  jz      short loc_1800302C2
0x1800302ba  test    ax, ax
0x1800302bd  jz      short loc_1800302C2
0x1800302bf  mov     sil, r14b
0x1800302c2  mov     [rdi], sil
0x1800302c5  lea     rcx, [rbp+arg_10]
0x1800302c9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800302ce  mov     eax, ebx
0x1800302d0  add     rsp, 30h
0x1800302d4  pop     r14
0x1800302d6  pop     rdi
0x1800302d7  pop     rsi
0x1800302d8  pop     rbx
0x1800302d9  pop     rbp
0x1800302da  retn
```

# ConnectionPointContainer::Copy(IEnumConnectionPoints * *)

- ea: `0x180018804`
- end: `0x1800188d8`
- name: `?Copy@ConnectionPointContainer@@QEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(ConnectionPointContainer *__hidden this, struct IEnumConnectionPoints **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001e760`

## callees

- `0x180002ec0`
- `0x18000c2a4`
- `0x180017b08`
- `0x180017b44`
- `0x180018370`
- `0x180018804`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018824`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018824`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectionPointContainer::Copy(
        struct _RTL_CRITICAL_SECTION *this,
        struct IEnumConnectionPoints **a2)
{
  __int64 v4; // rax
  struct IEnumConnectionPoints *v5; // rbx
  unsigned int v6; // edi
  struct IEnumConnectionPoints *v8; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-20h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+30h] [rbp-18h] BYREF

  *a2 = 0;
  v8 = 0;
  EnterCriticalSection(this);
  v10 = this;
  v4 = Microsoft::WRL::Details::Make<EnumConnectionPoints,IConnectionPoint * &>(v9, &this[1]);
  Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(&v8, v4);
  Microsoft::WRL::ComPtr<EnumConnectionPoints>::~ComPtr<EnumConnectionPoints>(v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  v5 = v8;
  if ( v8 )
  {
    ((void (__fastcall *)(struct IEnumConnectionPoints *))v8->lpVtbl->AddRef)(v8);
    *a2 = v5;
    v6 = 0;
  }
  else
  {
    v6 = -2147024882;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, v6);
  if ( v5 )
    ((void (__fastcall *)(struct IEnumConnectionPoints *))v5->lpVtbl->Release)(v5);
  return v6;
}

```

## disassembly

```asm
0x180018804  mov     [rsp+arg_10], rbx
0x180018809  push    rdi
0x18001880a  sub     rsp, 40h
0x18001880e  mov     rdi, rdx
0x180018811  mov     rbx, rcx
0x180018814  mov     qword ptr [rdx], 0
0x18001881b  mov     [rsp+48h+var_28], 0
0x180018824  call    cs:__imp_EnterCriticalSection
0x18001882a  mov     [rsp+48h+var_18], rbx
0x18001882f  lea     rdx, [rbx+28h]
0x180018833  lea     rcx, [rsp+48h+var_20]
0x180018838  call    ??$Make@VEnumConnectionPoints@@AEAPEAUIConnectionPoint@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnumConnectionPoints@@@12@AEAPEAUIConnectionPoint@@@Z; Microsoft::WRL::Details::Make<EnumConnectionPoints,IConnectionPoint * &>(IConnectionPoint * &)
0x18001883d  mov     rdx, rax
0x180018840  lea     rcx, [rsp+48h+var_28]
0x180018845  call    ??$?4VEnumConnectionPoints@@@?$ComPtr@UIEnumConnectionPoints@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VEnumConnectionPoints@@@12@@Z; Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(Microsoft::WRL::ComPtr<EnumConnectionPoints> &&)
0x18001884a  lea     rcx, [rsp+48h+var_20]
0x18001884f  call    ??1?$ComPtr@VEnumConnectionPoints@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<EnumConnectionPoints>::~ComPtr<EnumConnectionPoints>(void)
0x180018854  lea     rcx, [rsp+48h+var_18]
0x180018859  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001885e  mov     rbx, [rsp+48h+var_28]
0x180018863  test    rbx, rbx
0x180018866  jz      short loc_18001887F
0x180018868  mov     rax, [rbx]
0x18001886b  mov     rcx, rbx
0x18001886e  mov     rax, [rax+8]
0x180018872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018877  nop
0x180018878  mov     [rdi], rbx
0x18001887b  xor     edi, edi
0x18001887d  jmp     short loc_180018884
0x18001887f  mov     edi, 8007000Eh
0x180018884  lea     rax, WPP_GLOBAL_Control
0x18001888b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018892  cmp     rcx, rax
0x180018895  jz      short loc_1800188B6
0x180018897  test    byte ptr [rcx+1Ch], 4
0x18001889b  jz      short loc_1800188B6
0x18001889d  mov     edx, 0Fh
0x1800188a2  mov     r9d, edi
0x1800188a5  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x1800188ac  mov     rcx, [rcx+10h]
0x1800188b0  call    WPP_SF_d
0x1800188b5  nop
0x1800188b6  test    rbx, rbx
0x1800188b9  jz      short loc_1800188CB
0x1800188bb  mov     rdx, [rbx]
0x1800188be  mov     rcx, rbx
0x1800188c1  mov     rax, [rdx+10h]
0x1800188c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ca  nop
0x1800188cb  mov     eax, edi
0x1800188cd  mov     rbx, [rsp+48h+arg_10]
0x1800188d2  add     rsp, 40h
0x1800188d6  pop     rdi
0x1800188d7  retn
```

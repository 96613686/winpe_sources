# ReadDebugCtlFromRegistry(void)

- ea: `0x18000cf98`
- end: `0x18000d131`
- name: `?ReadDebugCtlFromRegistry@@YAXXZ`
- size: `409`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d8b4`

## callees

- `0x180008de0`
- `0x180009258`
- `0x18000ca18`
- `0x18000cf98`
- `0x18003f010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000cfbf`
- `ntdll!RtlInitUnicodeString` at `0x18000d064`
- `ntdll!RtlInitUnicodeString` at `0x18000cfbf`
- `ntdll!RtlInitUnicodeString` at `0x18000d064`

## pseudocode

```c
void ReadDebugCtlFromRegistry(void)
{
  __int64 v0; // rbx
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v2; // [rsp+50h] [rbp-10h] BYREF
  int v3; // [rsp+70h] [rbp+10h] BYREF
  __int64 v4; // [rsp+78h] [rbp+18h] BYREF

  v4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RdpIdd");
  v0 = v4;
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v3);
    (*(void (__fastcall **)(__int64, __int64))(WdfFunctions_02025 + 1064))(WdfDriverGlobals, v0);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v3);
  }
  v4 = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, _UNICODE_STRING *, __int64, _QWORD, __int64 *))(WdfFunctions_02025 + 1048))(
         WdfDriverGlobals,
         0,
         &DestinationString,
         0x80000000LL,
         0,
         &v4) >= 0 )
  {
    v3 = 0;
    v2 = 0;
    RtlInitUnicodeString(&v2, L"DebugCtrl");
    if ( (*(int (__fastcall **)(__int64, __int64, struct _UNICODE_STRING *, int *))(WdfFunctions_02025 + 1128))(
           WdfDriverGlobals,
           v4,
           &v2,
           &v3) >= 0 )
    {
      gDebugCtrl = v3 & 1;
      byte_180057E49 = (v3 & 2) != 0;
      byte_180057E4A = (v3 & 4) != 0;
      byte_180057E4B = (v3 & 8) != 0;
      byte_180057E4C = (v3 & 0x10) != 0;
      byte_180057E4D = (v3 & 0x20) != 0;
      byte_180057E4E = (v3 & 0x40) != 0;
      byte_180057E4F = (unsigned __int8)v3 >> 7;
      byte_180057E50 = BYTE1(v3) & 1;
      byte_180057E51 = (v3 & 0x200) != 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>(&v4);
}

```

## disassembly

```asm
0x18000cf98  mov     [rsp-8+arg_10], rbx
0x18000cf9d  push    rbp
0x18000cf9e  mov     rbp, rsp
0x18000cfa1  sub     rsp, 60h
0x18000cfa5  xorps   xmm0, xmm0
0x18000cfa8  mov     [rbp+arg_8], 0
0x18000cfb0  lea     rdx, SourceString; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18000cfb7  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000cfbb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000cfbf  call    cs:__imp_RtlInitUnicodeString
0x18000cfc6  nop     dword ptr [rax+rax+00h]
0x18000cfcb  mov     rbx, [rbp+arg_8]
0x18000cfcf  test    rbx, rbx
0x18000cfd2  jz      short loc_18000D003
0x18000cfd4  lea     rcx, [rbp+arg_0]; this
0x18000cfd8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cfdd  mov     rax, cs:WdfFunctions_02025
0x18000cfe4  mov     rdx, rbx
0x18000cfe7  mov     rcx, cs:WdfDriverGlobals
0x18000cfee  mov     rax, [rax+428h]
0x18000cff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cffa  lea     rcx, [rbp+arg_0]; this
0x18000cffe  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000d003  mov     rax, cs:WdfFunctions_02025
0x18000d00a  lea     rcx, [rbp+arg_8]
0x18000d00e  mov     [rsp+60h+var_38], rcx
0x18000d013  lea     r8, [rbp+DestinationString]
0x18000d017  mov     rcx, cs:WdfDriverGlobals
0x18000d01e  mov     r9d, 80000000h
0x18000d024  mov     [rbp+arg_8], 0
0x18000d02c  xor     edx, edx
0x18000d02e  mov     rax, [rax+418h]
0x18000d035  mov     [rsp+60h+var_40], 0
0x18000d03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d043  test    eax, eax
0x18000d045  js      loc_18000D119
0x18000d04b  xorps   xmm0, xmm0
0x18000d04e  mov     [rbp+arg_0], 0
0x18000d055  lea     rdx, aDebugctrl; "DebugCtrl"
0x18000d05c  lea     rcx, [rbp+var_10]; DestinationString
0x18000d060  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x18000d064  call    cs:__imp_RtlInitUnicodeString
0x18000d06b  nop     dword ptr [rax+rax+00h]
0x18000d070  mov     rax, cs:WdfFunctions_02025
0x18000d077  lea     r9, [rbp+arg_0]
0x18000d07b  mov     rdx, [rbp+arg_8]
0x18000d07f  lea     r8, [rbp+var_10]
0x18000d083  mov     rcx, cs:WdfDriverGlobals
0x18000d08a  mov     rax, [rax+468h]
0x18000d091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d096  test    eax, eax
0x18000d098  js      short loc_18000D119
0x18000d09a  mov     ecx, [rbp+arg_0]
0x18000d09d  mov     dl, 1
0x18000d09f  mov     al, cl
0x18000d0a1  and     al, dl
0x18000d0a3  mov     cs:?gDebugCtrl@@3URDPIDD_DEBUG_CTRL@@A, al; RDPIDD_DEBUG_CTRL gDebugCtrl
0x18000d0a9  mov     al, cl
0x18000d0ab  shr     al, 1
0x18000d0ad  and     al, dl
0x18000d0af  mov     cs:byte_180057E49, al
0x18000d0b5  mov     al, cl
0x18000d0b7  shr     al, 2
0x18000d0ba  and     al, dl
0x18000d0bc  mov     cs:byte_180057E4A, al
0x18000d0c2  mov     al, cl
0x18000d0c4  shr     al, 3
0x18000d0c7  and     al, dl
0x18000d0c9  mov     cs:byte_180057E4B, al
0x18000d0cf  mov     al, cl
0x18000d0d1  shr     al, 4
0x18000d0d4  and     al, dl
0x18000d0d6  mov     cs:byte_180057E4C, al
0x18000d0dc  mov     al, cl
0x18000d0de  shr     al, 5
0x18000d0e1  and     al, dl
0x18000d0e3  mov     cs:byte_180057E4D, al
0x18000d0e9  mov     al, cl
0x18000d0eb  shr     al, 6
0x18000d0ee  and     al, dl
0x18000d0f0  mov     cs:byte_180057E4E, al
0x18000d0f6  mov     al, cl
0x18000d0f8  shr     al, 7
0x18000d0fb  mov     cs:byte_180057E4F, al
0x18000d101  mov     eax, ecx
0x18000d103  shr     eax, 8
0x18000d106  and     al, dl
0x18000d108  shr     ecx, 9
0x18000d10b  and     cl, dl
0x18000d10d  mov     cs:byte_180057E50, al
0x18000d113  mov     cs:byte_180057E51, cl
0x18000d119  lea     rcx, [rbp+arg_8]
0x18000d11d  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAU1@@Z$1?WdfRegistryClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>(void)
0x18000d122  mov     rbx, [rsp+60h+arg_10]
0x18000d12a  add     rsp, 60h
0x18000d12e  pop     rbp
0x18000d12f  retn
```

# _anonymous_namespace_::MakeUniqueProcessParameters

- ea: `0x18002acdc`
- end: `0x18002adb4`
- name: `_anonymous_namespace_::MakeUniqueProcessParameters`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x18002acdc`
- `0x18002adbc`
- `0x180047b74`

## import_xrefs

- `ntdll!RtlCreateProcessParametersEx` at `0x18002ad54`
- `ntdll!RtlCreateProcessParametersEx` at `0x18002ad54`

## string_xrefs

- `0x18002ad6f`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall anonymous_namespace_::MakeUniqueProcessParameters(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 v5; // [rsp+68h] [rbp-20h] BYREF
  __int64 v6; // [rsp+70h] [rbp-18h] BYREF
  char v7; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v5 = a1;
  v6 = 0;
  v7 = 1;
  v3 = RtlCreateProcessParametersEx(&v6, a2, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      (const char *)(unsigned int)v3,
      0);
  wil::details::out_param_t<std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>>::~out_param_t<std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>>(&v5);
  *(_DWORD *)(*(_QWORD *)a1 + 1032LL) = NtCurrentPeb()->ProcessParameters[1].Flags;
  return a1;
}

```

## disassembly

```asm
0x18002acdc  mov     r11, rsp
0x18002acdf  mov     [r11+8], rcx
0x18002ace3  push    rbx
0x18002ace4  sub     rsp, 80h
0x18002aceb  mov     rbx, rcx
0x18002acee  mov     [rsp+88h+var_28], 0
0x18002acf6  mov     qword ptr [rcx], 0
0x18002acfd  mov     eax, 1
0x18002ad02  mov     [rsp+88h+var_28], eax
0x18002ad06  mov     [r11-20h], rcx
0x18002ad0a  mov     qword ptr [r11-18h], 0
0x18002ad12  mov     [rsp+88h+var_10], al
0x18002ad16  mov     [rsp+88h+var_38], eax
0x18002ad1a  mov     qword ptr [r11-40h], 0
0x18002ad22  mov     qword ptr [r11-48h], 0
0x18002ad2a  mov     qword ptr [r11-50h], 0
0x18002ad32  mov     qword ptr [r11-58h], 0
0x18002ad3a  mov     qword ptr [r11-60h], 0
0x18002ad42  mov     qword ptr [r11-68h], 0
0x18002ad4a  xor     r9d, r9d
0x18002ad4d  xor     r8d, r8d
0x18002ad50  lea     rcx, [r11-18h]
0x18002ad54  call    cs:__imp_RtlCreateProcessParametersEx
0x18002ad5b  nop     dword ptr [rax+rax+00h]
0x18002ad60  mov     rcx, [rsp+88h]; this
0x18002ad68  test    eax, eax
0x18002ad6a  jns     short loc_18002AD81
0x18002ad6c  mov     r9d, eax; char *
0x18002ad6f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002ad76  mov     edx, 13Dh; void *
0x18002ad7b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002ad81  lea     rcx, [rsp+88h+var_20]
0x18002ad86  call    ??1?$out_param_t@V?$unique_ptr@U_RTL_USER_PROCESS_PARAMETERS@@U?$function_deleter@P6AJPEAU_RTL_USER_PROCESS_PARAMETERS@@@Z$1?RtlDestroyProcessParameters@@YAJ0@Z@wil@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>>::~out_param_t<std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>>(void)
0x18002ad8b  mov     rax, gs:60h
0x18002ad94  mov     rax, [rax+20h]
0x18002ad98  mov     rcx, [rbx]
0x18002ad9b  mov     eax, [rax+408h]
0x18002ada1  mov     [rcx+408h], eax
0x18002ada7  mov     rax, rbx
0x18002adaa  add     rsp, 80h
0x18002adb1  pop     rbx
0x18002adb2  retn
```

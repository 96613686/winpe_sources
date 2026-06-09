# CloudPrint::CloudPrintHelper::ResetState(void)

- ea: `0x18001af48`
- end: `0x18001b059`
- name: `?ResetState@CloudPrintHelper@CloudPrint@@IEAAXXZ`
- size: `273`
- prototype: `void __fastcall(CloudPrint::CloudPrintHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001892c`

## callees

- `0x180009638`
- `0x18000e164`
- `0x18000e838`
- `0x18001af48`
- `0x18001baa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001afac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001afac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afba`

## string_xrefs

- `0x18001afdd`: `Couldn't create discovery search endpoints mutex`

## pseudocode

```c
void __fastcall CloudPrint::CloudPrintHelper::ResetState(CloudPrint::CloudPrintHelper *this)
{
  wil::details *v2; // rcx
  HANDLE Mutex; // rdi
  unsigned int LastErrorFailHr; // eax
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_WORD *)this + 4) = 0;
  *((_DWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 7) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  *((_QWORD *)this + 11) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  *((_QWORD *)this + 15) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  Mutex = CreateMutexExW(0, 0, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 136,
      Mutex);
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x33C,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)LastErrorFailHr,
    (int)"Couldn't create discovery search endpoints mutex",
    v5);
  *((_QWORD *)this + 20) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  *((_QWORD *)this + 24) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  *((_QWORD *)this + 36) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  *((_QWORD *)this + 32) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
}

```

## disassembly

```asm
0x18001af48  mov     [rsp+arg_0], rbx
0x18001af4d  mov     [rsp+arg_8], rsi
0x18001af52  push    rdi
0x18001af53  sub     rsp, 30h
0x18001af57  xor     esi, esi
0x18001af59  mov     rbx, rcx
0x18001af5c  mov     [rcx+8], si
0x18001af60  mov     [rcx+0Ch], esi
0x18001af63  mov     [rcx+10h], rsi
0x18001af67  mov     [rcx+18h], rsi
0x18001af6b  mov     [rcx+20h], rsi
0x18001af6f  add     rcx, 28h ; '('
0x18001af73  mov     [rcx+10h], rsi
0x18001af77  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001af7c  lea     rcx, [rbx+48h]
0x18001af80  mov     [rax], si
0x18001af83  mov     [rcx+10h], rsi
0x18001af87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001af8c  lea     rcx, [rbx+68h]
0x18001af90  mov     [rax], si
0x18001af93  mov     [rcx+10h], rsi
0x18001af97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001af9c  mov     r9d, 1F0001h; dwDesiredAccess
0x18001afa2  xor     r8d, r8d; dwFlags
0x18001afa5  xor     edx, edx; lpName
0x18001afa7  xor     ecx, ecx; lpMutexAttributes
0x18001afa9  mov     [rax], si
0x18001afac  call    cs:__imp_CreateMutexExW
0x18001afb2  mov     rdi, rax
0x18001afb5  test    rax, rax
0x18001afb8  jz      short loc_18001AFD3
0x18001afba  call    cs:__imp_GetLastError
0x18001afc0  lea     rcx, [rbx+88h]
0x18001afc7  mov     rdx, rdi
0x18001afca  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001afcf  mov     eax, esi
0x18001afd1  jmp     short loc_18001AFD8
0x18001afd3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001afd8  mov     rcx, [rsp+38h]; this
0x18001afdd  lea     rdx, aCouldnTCreateD; "Couldn't create discovery search endpoi"...
0x18001afe4  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001afe9  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001aff0  mov     edx, 33Ch; void *
0x18001aff5  mov     r9d, eax; char *
0x18001aff8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001affd  lea     rcx, [rbx+90h]
0x18001b004  mov     [rcx+10h], rsi
0x18001b008  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b00d  lea     rcx, [rbx+0B0h]
0x18001b014  mov     [rax], si
0x18001b017  mov     [rcx+10h], rsi
0x18001b01b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b020  lea     rcx, [rbx+110h]
0x18001b027  mov     [rax], si
0x18001b02a  mov     [rcx+10h], rsi
0x18001b02e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b033  lea     rcx, [rbx+0F0h]
0x18001b03a  mov     [rax], si
0x18001b03d  mov     [rcx+10h], rsi
0x18001b041  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b046  mov     rbx, [rsp+38h+arg_0]
0x18001b04b  mov     [rax], si
0x18001b04e  mov     rsi, [rsp+38h+arg_8]
0x18001b053  add     rsp, 30h
0x18001b057  pop     rdi
0x18001b058  retn
```

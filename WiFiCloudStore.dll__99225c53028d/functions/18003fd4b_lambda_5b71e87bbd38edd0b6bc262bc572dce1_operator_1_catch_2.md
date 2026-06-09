# __lambda_5b71e87bbd38edd0b6bc262bc572dce1_::operator()_::_1_::catch$2

- ea: `0x18003fd4b`
- end: `0x18003fdae`
- name: `__lambda_5b71e87bbd38edd0b6bc262bc572dce1_::operator()_::_1_::catch$2`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800310a8`
- `0x1800315e0`
- `0x180031724`
- `0x180041010`

## string_xrefs

- `0x18003fd5e`: `onecoreuap\net\wlan\cloudstore\provider\lib\SyncTaskCommon.h`

## pseudocode

```c
__int64 __fastcall _lambda_5b71e87bbd38edd0b6bc262bc572dce1_::operator()_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil *v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // rbx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x36,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\SyncTaskCommon.h",
    a4);
  v6 = wil::ResultFromCaughtException(v5);
  v7 = *(_QWORD *)(a2 + 128);
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    (_QWORD *)(v7 + 16),
    v6);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v7 + 8) + 32LL))(*(_QWORD *)(v7 + 8), v6);
  return 0;
}

```

## disassembly

```asm
0x18003fd4b  mov     [rsp+arg_8], rdx
0x18003fd50  push    rbx
0x18003fd51  push    rbp
0x18003fd52  push    rdi
0x18003fd53  sub     rsp, 20h
0x18003fd57  mov     rbp, rdx
0x18003fd5a  mov     rcx, [rbp+78h]; this
0x18003fd5e  lea     r8, aOnecoreuapNetW_4; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003fd65  mov     edx, 36h ; '6'; void *
0x18003fd6a  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003fd6f  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18003fd74  mov     edi, eax
0x18003fd76  mov     rbx, [rbp+80h]
0x18003fd7d  lea     rcx, [rbx+10h]
0x18003fd81  mov     edx, eax
0x18003fd83  call    ?Stop@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003fd88  mov     rcx, [rbx+8]
0x18003fd8c  mov     rdx, [rcx]
0x18003fd8f  mov     rax, [rdx+20h]
0x18003fd93  mov     edx, edi
0x18003fd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd9a  nop
0x18003fd9b  mov     rax, 0
0x18003fda5  add     rsp, 20h
0x18003fda9  pop     rdi
0x18003fdaa  pop     rbp
0x18003fdab  pop     rbx
0x18003fdac  retn
```

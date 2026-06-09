# __lambda_b9edf738e17dc43f74c922ccb415010b_::operator()_::_1_::catch$228

- ea: `0x18002f4fb`
- end: `0x18002f57d`
- name: `__lambda_b9edf738e17dc43f74c922ccb415010b_::operator()_::_1_::catch$228`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18001b2f4`
- `0x18002030c`
- `0x180021400`
- `0x180022d44`
- `0x18002f4fb`

## string_xrefs

- `0x18002f559`: `onecoreuap\windows\input\cloudstore\lib\inputtocdstaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_b9edf738e17dc43f74c922ccb415010b_::operator()_::_1_::catch_228(wil *a1, __int64 a2)
{
  int v3; // eax
  const char *v4; // r9
  __int64 v5; // rbx

  v3 = wil::ResultFromCaughtException(a1);
  if ( v3 == -2147221243 || v3 == -2147024891 )
  {
    v5 = *(_QWORD *)(a2 + 392);
    *(_QWORD *)(a2 + 264) = v5;
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 328));
    tip2::details::shared_data<1,0,0>::begin_update(v5 + 8);
    *(_BYTE *)(v5 + 320) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>::~test_data_control<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>(a2 + 264);
  }
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 792),
    (void *)0x1C8,
    (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\inputtocdstaskhandler.cpp",
    v4);
  return 0;
}

```

## disassembly

```asm
0x18002f4fb  mov     [rsp+arg_8], rdx
0x18002f500  push    rbx
0x18002f501  push    rbp
0x18002f502  sub     rsp, 48h
0x18002f506  mov     rbp, rdx
0x18002f509  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18002f50e  cmp     eax, 80040105h
0x18002f513  jz      short loc_18002F51C
0x18002f515  cmp     eax, 80070005h
0x18002f51a  jnz     short loc_18002F552
0x18002f51c  mov     rbx, [rbp+188h]
0x18002f523  test    rbx, rbx
0x18002f526  mov     [rbp+108h], rbx
0x18002f52d  jz      short loc_18002F536
0x18002f52f  lock inc dword ptr [rbx+148h]
0x18002f536  lea     rcx, [rbx+8]
0x18002f53a  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18002f53f  mov     byte ptr [rbx+140h], 1
0x18002f546  lea     rcx, [rbp+108h]
0x18002f54d  call    ??1?$test_data_control@V?$merged_data@U_tip_InputSettingsBackup@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>::~test_data_control<tip2::details::merged_data<_tip_InputSettingsBackup,_tip_InputSettingsBackup>>(void)
0x18002f552  mov     rcx, [rbp+318h]; this
0x18002f559  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\input\\cloudstore"...
0x18002f560  mov     edx, 1C8h; void *
0x18002f565  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002f56a  nop
0x18002f56b  mov     rax, 0
0x18002f575  add     rsp, 48h
0x18002f579  pop     rbp
0x18002f57a  pop     rbx
0x18002f57b  retn
```

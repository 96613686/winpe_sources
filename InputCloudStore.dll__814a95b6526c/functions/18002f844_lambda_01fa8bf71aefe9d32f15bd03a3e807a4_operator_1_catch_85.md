# __lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::operator()_::_1_::catch$85

- ea: `0x18002f844`
- end: `0x18002f8d1`
- name: `__lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::operator()_::_1_::catch$85`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18002030c`
- `0x180021400`
- `0x180022d44`
- `0x180026d54`
- `0x18002f844`

## string_xrefs

- `0x18002f8ac`: `onecoreuap\windows\input\cloudstore\lib\cdstoinputtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::operator()_::_1_::catch_85(wil *a1, __int64 a2)
{
  int v3; // eax
  bool v4; // di
  __int64 v5; // rbx
  const char *v6; // r9

  v3 = wil::ResultFromCaughtException(a1);
  v4 = v3 == -2147221243 || v3 == -2147024891;
  v5 = *(_QWORD *)(a2 + 408);
  *(_QWORD *)(a2 + 136) = v5;
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 280));
  tip2::details::shared_data<1,0,0>::begin_update(v5 + 8);
  *(_BYTE *)(v5 + 272) = v4;
  tip2::test_data_control<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>::~test_data_control<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>(a2 + 136);
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 616),
    (void *)0x1DC,
    (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\cdstoinputtaskhandler.cpp",
    v6);
  return 0;
}

```

## disassembly

```asm
0x18002f844  mov     [rsp+arg_8], rdx
0x18002f849  push    rbx
0x18002f84a  push    rbp
0x18002f84b  push    rdi
0x18002f84c  sub     rsp, 40h
0x18002f850  mov     rbp, rdx
0x18002f853  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18002f858  cmp     eax, 80040105h
0x18002f85d  jz      short loc_18002F86A
0x18002f85f  cmp     eax, 80070005h
0x18002f864  jz      short loc_18002F86A
0x18002f866  xor     edi, edi
0x18002f868  jmp     short loc_18002F86F
0x18002f86a  mov     edi, 1
0x18002f86f  mov     rbx, [rbp+198h]
0x18002f876  mov     [rbp+88h], rbx
0x18002f87d  test    rbx, rbx
0x18002f880  jz      short loc_18002F889
0x18002f882  lock inc dword ptr [rbx+118h]
0x18002f889  lea     rcx, [rbx+8]
0x18002f88d  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18002f892  mov     [rbx+110h], dil
0x18002f899  lea     rcx, [rbp+88h]
0x18002f8a0  call    ??1?$test_data_control@V?$merged_data@U_tip_InputSettingsRestore@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>::~test_data_control<tip2::details::merged_data<_tip_InputSettingsRestore,_tip_InputSettingsRestore>>(void)
0x18002f8a5  mov     rcx, [rbp+268h]; this
0x18002f8ac  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\input\\cloudstore"...
0x18002f8b3  mov     edx, 1DCh; void *
0x18002f8b8  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002f8bd  nop
0x18002f8be  mov     rax, 0
0x18002f8c8  add     rsp, 40h
0x18002f8cc  pop     rdi
0x18002f8cd  pop     rbp
0x18002f8ce  pop     rbx
0x18002f8cf  retn
```

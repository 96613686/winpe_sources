# McpService::RuntimeClassInitialize(std::shared_ptr<CloudPrint::CloudPrintHelper>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180026714`
- end: `0x1800267e6`
- name: `?RuntimeClassInitialize@McpService@@QEAAJV?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800237f0`

## callees

- `0x180011f34`
- `0x1800125e4`
- `0x1800194dc`
- `0x18001c9a8`
- `0x1800239a4`
- `0x180026714`

## pseudocode

```c
__int64 __fastcall McpService::RuntimeClassInitialize(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  std::_Ref_count_base *v6; // rcx
  unsigned int v7; // ebx
  __int64 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  std::_Ref_count_base *v11; // rcx
  _BYTE v13[8]; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-10h]

  if ( !*a2 )
  {
    v6 = (std::_Ref_count_base *)a2[1];
LABEL_7:
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    v7 = -2147024809;
    goto LABEL_15;
  }
  if ( !CloudPrint::CloudPrintHelper::IsMockEnabled() && (!*a3 || ((*(_QWORD *)*a3 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0) )
  {
    v6 = (std::_Ref_count_base *)a2[1];
    goto LABEL_7;
  }
  std::shared_ptr<CloudPrint::CloudPrintHelper>::operator=(a1 + 24, a2);
  v8 = (__int64 *)std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(v13, a3);
  v9 = *v8;
  *v8 = *(_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v9;
  v10 = v8[1];
  v8[1] = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = v10;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  v11 = (std::_Ref_count_base *)a2[1];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v7 = 0;
LABEL_15:
  std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(a3);
  return v7;
}

```

## disassembly

```asm
0x180026714  mov     rax, rsp
0x180026717  mov     [rax+8], rbx
0x18002671b  mov     [rax+20h], rsi
0x18002671f  mov     [rax+18h], r8
0x180026723  mov     [rax+10h], rdx
0x180026727  push    rdi
0x180026728  sub     rsp, 30h
0x18002672c  mov     rdi, r8
0x18002672f  mov     rbx, rdx
0x180026732  mov     rsi, rcx
0x180026735  cmp     qword ptr [rdx], 0
0x180026739  jnz     short loc_180026741
0x18002673b  mov     rcx, [rdx+8]
0x18002673f  jmp     short loc_180026764
0x180026741  call    ?IsMockEnabled@CloudPrintHelper@CloudPrint@@SA_NXZ; CloudPrint::CloudPrintHelper::IsMockEnabled(void)
0x180026746  test    al, al
0x180026748  jnz     short loc_180026775
0x18002674a  mov     rax, [rdi]
0x18002674d  test    rax, rax
0x180026750  jz      short loc_180026760
0x180026752  mov     rax, [rax]
0x180026755  inc     rax
0x180026758  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002675e  jnz     short loc_180026775
0x180026760  mov     rcx, [rbx+8]; this
0x180026764  test    rcx, rcx
0x180026767  jz      short loc_18002676E
0x180026769  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002676e  mov     ebx, 80070057h
0x180026773  jmp     short loc_1800267CC
0x180026775  lea     rcx, [rsi+18h]
0x180026779  mov     rdx, rbx
0x18002677c  call    ??4?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CloudPrint::CloudPrintHelper>::operator=(std::shared_ptr<CloudPrint::CloudPrintHelper> const &)
0x180026781  mov     rdx, rdi
0x180026784  lea     rcx, [rsp+38h+var_18]
0x180026789  call    ??0?$shared_ptr@VHInternetRAII@PrintCore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintCore::HInternetRAII>::shared_ptr<PrintCore::HInternetRAII>(std::shared_ptr<PrintCore::HInternetRAII> const &)
0x18002678e  mov     rdx, [rax]
0x180026791  mov     rcx, [rsi+28h]
0x180026795  mov     [rax], rcx
0x180026798  mov     [rsi+28h], rdx
0x18002679c  mov     rdx, [rax+8]
0x1800267a0  mov     rcx, [rsi+30h]
0x1800267a4  mov     [rax+8], rcx
0x1800267a8  mov     [rsi+30h], rdx
0x1800267ac  mov     rcx, [rsp+38h+var_10]; this
0x1800267b1  test    rcx, rcx
0x1800267b4  jz      short loc_1800267BC
0x1800267b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800267bb  nop
0x1800267bc  mov     rcx, [rbx+8]; this
0x1800267c0  test    rcx, rcx
0x1800267c3  jz      short loc_1800267CA
0x1800267c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800267ca  xor     ebx, ebx
0x1800267cc  mov     rcx, rdi
0x1800267cf  call    ??1?$shared_ptr@VCloudPrintHelper@CloudPrint@@@std@@QEAA@XZ; std::shared_ptr<CloudPrint::CloudPrintHelper>::~shared_ptr<CloudPrint::CloudPrintHelper>(void)
0x1800267d4  mov     eax, ebx
0x1800267d6  mov     rbx, [rsp+38h+arg_0]
0x1800267db  mov     rsi, [rsp+38h+arg_18]
0x1800267e0  add     rsp, 30h
0x1800267e4  pop     rdi
0x1800267e5  retn
```

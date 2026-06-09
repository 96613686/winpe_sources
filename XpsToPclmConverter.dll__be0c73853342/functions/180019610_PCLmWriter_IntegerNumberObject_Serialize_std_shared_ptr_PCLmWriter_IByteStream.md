# PCLmWriter::IntegerNumberObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x180019610`
- end: `0x1800196ad`
- name: `?Serialize@IntegerNumberObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015f0`
- `0x1800101cc`
- `0x180016a54`
- `0x180019610`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18001964f`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x18001964f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::IntegerNumberObject::Serialize(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, __int64 *, size_t); // rbx
  size_t v5; // rax
  std::_Ref_count_base *v6; // rcx
  __int64 String; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  String = 0;
  v8 = 0;
  ((void (__fastcall *)(_QWORD, __int64 *, __int64, __int64, _QWORD *))_o__itoa_s)(
    *(unsigned int *)(a1 + 24),
    &String,
    12,
    10,
    a2);
  v3 = *a2;
  v4 = *(void (__fastcall **)(__int64, __int64 *, size_t))(*(_QWORD *)*a2 + 24LL);
  v5 = strnlen_s((const char *)&String, 0xCu);
  v4(v3, &String, v5);
  v6 = (std::_Ref_count_base *)a2[1];
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
}

```

## disassembly

```asm
0x180019610  mov     r11, rsp
0x180019613  mov     [r11+18h], rbx
0x180019617  mov     [r11+20h], rsi
0x18001961b  push    rdi
0x18001961c  sub     rsp, 40h
0x180019620  mov     rax, cs:__security_cookie
0x180019627  xor     rax, rsp
0x18001962a  mov     [rsp+48h+var_10], rax
0x18001962f  mov     rsi, rdx
0x180019632  mov     [r11-28h], rdx
0x180019636  xor     eax, eax
0x180019638  mov     [r11-20h], rax
0x18001963c  mov     [rsp+48h+var_18], eax
0x180019640  lea     r9d, [rax+0Ah]
0x180019644  lea     r8d, [rax+0Ch]
0x180019648  lea     rdx, [r11-20h]
0x18001964c  mov     ecx, [rcx+18h]
0x18001964f  call    cs:__imp__o__itoa_s
0x180019655  mov     rdi, [rsi]
0x180019658  mov     rax, [rdi]
0x18001965b  mov     rbx, [rax+18h]
0x18001965f  mov     edx, 0Ch; MaxCount
0x180019664  lea     rcx, [rsp+48h+String]; String
0x180019669  call    strnlen_s
0x18001966e  mov     r8, rax
0x180019671  lea     rdx, [rsp+48h+String]
0x180019676  mov     rcx, rdi
0x180019679  mov     rax, rbx
0x18001967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019681  nop
0x180019682  mov     rcx, [rsi+8]; this
0x180019686  test    rcx, rcx
0x180019689  jz      short loc_180019690
0x18001968b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019690  mov     rcx, [rsp+48h+var_10]
0x180019695  xor     rcx, rsp; StackCookie
0x180019698  call    __security_check_cookie
0x18001969d  mov     rbx, [rsp+48h+arg_10]
0x1800196a2  mov     rsi, [rsp+48h+arg_18]
0x1800196a7  add     rsp, 40h
0x1800196ab  pop     rdi
0x1800196ac  retn
```

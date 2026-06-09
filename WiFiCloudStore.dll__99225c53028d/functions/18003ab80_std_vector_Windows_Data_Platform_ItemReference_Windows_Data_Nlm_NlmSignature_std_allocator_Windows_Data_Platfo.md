# std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> * const,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> &&)

- ea: `0x18003ab80`
- end: `0x18003ac9f`
- name: `??$_Emplace_reallocate@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAPEAU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@QEAU2345@$$QEAU2345@@Z`
- size: `287`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180009240`

## callees

- `0x180009214`
- `0x18000a188`
- `0x18000a29c`
- `0x18001776c`
- `0x18002740c`
- `0x18002862c`
- `0x1800290b4`
- `0x18003ab80`
- `0x18003b958`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Emplace_reallocate<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // r14
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  size_t size_of; // rax
  char *v13; // rsi
  char *v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-78h] BYREF
  char *v20; // [rsp+28h] [rbp-70h]
  __int64 v21; // [rsp+30h] [rbp-68h]
  char *v22; // [rsp+38h] [rbp-60h]
  char *v23; // [rsp+40h] [rbp-58h]

  v6 = (__int64)(a1[1] - *a1) >> 6;
  v7 = 0x3FFFFFFFFFFFFFFLL;
  if ( v6 == 0x3FFFFFFFFFFFFFFLL )
    std::vector<char,sfl::StlAllocator<bond::detail::stream_allocator<1040>,char>>::_Xlength();
  v8 = a2 - *a1;
  v9 = v6 + 1;
  v10 = (__int64)(a1[2] - *a1) >> 6;
  v11 = v10 >> 1;
  if ( v10 <= 0x3FFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v7 = v11 + v10;
    if ( v11 + v10 < v9 )
      v7 = v6 + 1;
  }
  size_of = std::_Get_size_of_n<64>(v7);
  v13 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = &v13[v8 & 0xFFFFFFFFFFFFFFC0uLL];
  v19 = a1;
  v20 = v13;
  v21 = v7;
  v23 = v14 + 64;
  std::_Default_allocator_traits<std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>>::construct<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>(
    v15,
    v14,
    a3);
  v22 = v14;
  v16 = a1[1];
  v17 = *a1;
  if ( a2 == v16 )
  {
    std::_Uninitialized_copy<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>>(
      v17,
      v16,
      v13,
      a1);
  }
  else
  {
    std::_Uninitialized_move<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>>(
      v17,
      a2,
      v13);
    v22 = v13;
    std::_Uninitialized_move<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>>(
      a2,
      a1[1],
      v14 + 64);
  }
  v20 = 0;
  std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>::_Change_array(a1, v13, v9, v7);
  std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocation_guard::~_Reallocation_guard(&v19);
  return v14;
}

```

## disassembly

```asm
0x18003ab80  push    rbx
0x18003ab82  push    rbp
0x18003ab83  push    rsi
0x18003ab84  push    rdi
0x18003ab85  push    r12
0x18003ab87  push    r13
0x18003ab89  push    r14
0x18003ab8b  push    r15
0x18003ab8d  sub     rsp, 58h
0x18003ab91  mov     r13, r8
0x18003ab94  mov     r15, rdx
0x18003ab97  mov     rdi, rcx
0x18003ab9a  mov     rax, [rcx+8]
0x18003ab9e  sub     rax, [rcx]
0x18003aba1  sar     rax, 6
0x18003aba5  mov     rbx, 3FFFFFFFFFFFFFFh
0x18003abaf  cmp     rax, rbx
0x18003abb2  jz      loc_18003AC99
0x18003abb8  mov     r14, rdx
0x18003abbb  sub     r14, [rcx]
0x18003abbe  lea     rbp, [rax+1]
0x18003abc2  mov     rcx, [rcx+10h]
0x18003abc6  sub     rcx, [rdi]
0x18003abc9  sar     rcx, 6
0x18003abcd  mov     rdx, rcx
0x18003abd0  shr     rdx, 1
0x18003abd3  mov     rax, rbx
0x18003abd6  sub     rax, rdx
0x18003abd9  cmp     rcx, rax
0x18003abdc  ja      short loc_18003ABE9
0x18003abde  lea     rbx, [rdx+rcx]
0x18003abe2  cmp     rbx, rbp
0x18003abe5  cmovb   rbx, rbp
0x18003abe9  mov     rcx, rbx
0x18003abec  call    ??$_Get_size_of_n@$0EA@@std@@YA_K_K@Z; std::_Get_size_of_n<64>(unsigned __int64)
0x18003abf1  mov     rcx, rax
0x18003abf4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003abf9  mov     rsi, rax
0x18003abfc  and     r14, 0FFFFFFFFFFFFFFC0h
0x18003ac00  add     r14, rax
0x18003ac03  lea     r12, [r14+40h]
0x18003ac07  mov     [rsp+98h+var_78], rdi
0x18003ac0c  mov     [rsp+98h+var_70], rax
0x18003ac11  mov     [rsp+98h+var_68], rbx
0x18003ac16  mov     [rsp+98h+var_58], r12
0x18003ac1b  mov     r8, r13
0x18003ac1e  mov     rdx, r14
0x18003ac21  call    ??$construct@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@U1234@@?$_Default_allocator_traits@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@SAXAEAV?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@1@QEAU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@$$QEAU3456@@Z; std::_Default_allocator_traits<std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>>::construct<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>(std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>> &,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> * const,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> &&)
0x18003ac26  mov     [rsp+98h+var_60], r14
0x18003ac2b  mov     rdx, [rdi+8]
0x18003ac2f  mov     r8, rsi
0x18003ac32  mov     rcx, [rdi]
0x18003ac35  cmp     r15, rdx
0x18003ac38  jnz     short loc_18003AC44
0x18003ac3a  mov     r9, rdi
0x18003ac3d  call    ??$_Uninitialized_copy@PEAU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@PEAU1234@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@YAPEAU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@PEAU1234@00AEAV?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@0@@Z; std::_Uninitialized_copy<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>>(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>> &)
0x18003ac42  jmp     short loc_18003AC60
0x18003ac44  mov     rdx, r15
0x18003ac47  call    ??$_Uninitialized_move@PEAU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@YAPEAU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@QEAU1234@0PEAU1234@AEAV?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@0@@Z; std::_Uninitialized_move<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> * const,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> * const,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>> &)
0x18003ac4c  mov     [rsp+98h+var_60], rsi
0x18003ac51  mov     r8, r12
0x18003ac54  mov     rdx, [rdi+8]
0x18003ac58  mov     rcx, r15
0x18003ac5b  call    ??$_Uninitialized_move@PEAU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@YAPEAU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@QEAU1234@0PEAU1234@AEAV?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@0@@Z; std::_Uninitialized_move<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> * const,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> * const,Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> *,std::allocator<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>> &)
0x18003ac60  mov     [rsp+98h+var_70], 0
0x18003ac69  mov     r9, rbx
0x18003ac6c  mov     r8, rbp
0x18003ac6f  mov     rdx, rsi
0x18003ac72  mov     rcx, rdi
0x18003ac75  call    ?_Change_array@?$vector@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@AEAAXQEAU?$ItemReference@UWiFiProfile@WiFi@Data@Windows@@@Platform@Data@Windows@@_K1@Z; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>::_Change_array(Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile> * const,unsigned __int64,unsigned __int64)
0x18003ac7a  nop
0x18003ac7b  lea     rcx, [rsp+98h+var_78]
0x18003ac80  call    ??1_Reallocation_guard@?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18003ac85  mov     rax, r14
0x18003ac88  add     rsp, 58h
0x18003ac8c  pop     r15
0x18003ac8e  pop     r14
0x18003ac90  pop     r13
0x18003ac92  pop     r12
0x18003ac94  pop     rdi
0x18003ac95  pop     rsi
0x18003ac96  pop     rbp
0x18003ac97  pop     rbx
0x18003ac98  retn
0x18003ac99  call    ?_Xlength@?$vector@DV?$StlAllocator@V?$stream_allocator@$0EBA@@detail@bond@@D@sfl@@@std@@CAXXZ; std::vector<char,sfl::StlAllocator<bond::detail::stream_allocator<1040>,char>>::_Xlength(void)
```

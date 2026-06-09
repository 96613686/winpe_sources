# WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000cb4c`
- end: `0x18000ccf1`
- name: `?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z`
- size: `421`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ccf8`
- `0x18000d31c`

## callees

- `0x1800033d0`
- `0x18000b7fc`
- `0x18000c758`
- `0x18000cb4c`
- `0x18000f1e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
wchar_t *__fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(
        wchar_t *Src,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  bool v8; // bl
  bool v9; // bl
  __int64 v11; // [rsp+28h] [rbp-31h]
  __int64 v12; // [rsp+28h] [rbp-31h]
  __int64 v13; // [rsp+28h] [rbp-31h]
  __int64 v14; // [rsp+28h] [rbp-31h]
  _BYTE v15[32]; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *v16; // [rsp+50h] [rbp-9h]
  wchar_t Srca[8]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh]

  v16 = Src;
  v11 = std::wstring::wstring(v15, a3);
  std::wstring::wstring(Srca, v11);
  WindowsMidiServicesInternal::InPlaceTrim(Srca);
  std::wstring::~wstring(v11);
  v8 = v18 == 0;
  std::wstring::~wstring(Srca);
  if ( v8 )
  {
    v13 = std::wstring::wstring(v15, a4);
    std::wstring::wstring(Srca, v13);
    WindowsMidiServicesInternal::InPlaceTrim(Srca);
    std::wstring::~wstring(v13);
    v9 = v18 == 0;
    std::wstring::~wstring(Srca);
    if ( v9 )
      v14 = std::wstring::wstring(v15, a2);
    else
      v14 = std::wstring::wstring(v15, a4);
    std::wstring::wstring(Src, v14);
    WindowsMidiServicesInternal::InPlaceTrim(Src);
    std::wstring::~wstring(v14);
  }
  else
  {
    v12 = std::wstring::wstring(v15, a3);
    std::wstring::wstring(Src, v12);
    WindowsMidiServicesInternal::InPlaceTrim(Src);
    std::wstring::~wstring(v12);
  }
  return Src;
}

```

## disassembly

```asm
0x18000cb4c  push    rbp
0x18000cb4e  push    rbx
0x18000cb4f  push    rsi
0x18000cb50  push    rdi
0x18000cb51  push    r14
0x18000cb53  push    r15
0x18000cb55  lea     rbp, [rsp-2Fh]
0x18000cb5a  sub     rsp, 88h
0x18000cb61  mov     rax, cs:__security_cookie
0x18000cb68  xor     rax, rsp
0x18000cb6b  mov     [rbp+57h+var_38], rax
0x18000cb6f  mov     rsi, r9
0x18000cb72  mov     r14, r8
0x18000cb75  mov     r15, rdx
0x18000cb78  mov     rdi, rcx
0x18000cb7b  mov     [rbp+57h+var_60], rcx
0x18000cb7f  mov     [rbp+57h+var_90], 0
0x18000cb86  mov     rdx, r8
0x18000cb89  lea     rcx, [rbp+57h+var_80]
0x18000cb8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cb92  mov     rbx, rax
0x18000cb95  mov     [rbp+57h+var_88], rax
0x18000cb99  mov     rdx, rax
0x18000cb9c  lea     rcx, [rbp+57h+Src]
0x18000cba0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cba5  mov     [rbp+57h+var_90], 2
0x18000cbac  lea     rcx, [rbp+57h+Src]; Src
0x18000cbb0  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000cbb5  nop
0x18000cbb6  mov     rcx, rbx
0x18000cbb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbbe  cmp     [rbp+57h+var_48], 0
0x18000cbc3  setz    bl
0x18000cbc6  mov     [rbp+57h+var_90], 0
0x18000cbcd  lea     rcx, [rbp+57h+Src]
0x18000cbd1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbd6  lea     rcx, [rbp+57h+var_80]
0x18000cbda  test    bl, bl
0x18000cbdc  jnz     short loc_18000CC16
0x18000cbde  mov     rdx, r14
0x18000cbe1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cbe6  mov     rbx, rax
0x18000cbe9  mov     [rbp+57h+var_88], rax
0x18000cbed  mov     rdx, rax
0x18000cbf0  mov     rcx, rdi
0x18000cbf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cbf8  mov     [rbp+57h+var_90], 4
0x18000cbff  mov     rcx, rdi; Src
0x18000cc02  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000cc07  nop
0x18000cc08  mov     rcx, rbx
0x18000cc0b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc10  nop
0x18000cc11  jmp     loc_18000CCD2
0x18000cc16  mov     rdx, rsi
0x18000cc19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc1e  mov     rbx, rax
0x18000cc21  mov     [rbp+57h+var_88], rax
0x18000cc25  mov     rdx, rax
0x18000cc28  lea     rcx, [rbp+57h+Src]
0x18000cc2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc31  mov     [rbp+57h+var_90], 8
0x18000cc38  lea     rcx, [rbp+57h+Src]; Src
0x18000cc3c  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000cc41  nop
0x18000cc42  mov     rcx, rbx
0x18000cc45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc4a  cmp     [rbp+57h+var_48], 0
0x18000cc4f  setz    bl
0x18000cc52  mov     [rbp+57h+var_90], 0
0x18000cc59  lea     rcx, [rbp+57h+Src]
0x18000cc5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc62  lea     rcx, [rbp+57h+var_80]
0x18000cc66  test    bl, bl
0x18000cc68  jnz     short loc_18000CC9F
0x18000cc6a  mov     rdx, rsi
0x18000cc6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc72  mov     rbx, rax
0x18000cc75  mov     [rbp+57h+var_88], rax
0x18000cc79  mov     rdx, rax
0x18000cc7c  mov     rcx, rdi
0x18000cc7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc84  mov     [rbp+57h+var_90], 10h
0x18000cc8b  mov     rcx, rdi; Src
0x18000cc8e  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000cc93  nop
0x18000cc94  mov     rcx, rbx
0x18000cc97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc9c  nop
0x18000cc9d  jmp     short loc_18000CCD2
0x18000cc9f  mov     rdx, r15
0x18000cca2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cca7  mov     rbx, rax
0x18000ccaa  mov     [rbp+57h+var_88], rax
0x18000ccae  mov     rdx, rax
0x18000ccb1  mov     rcx, rdi
0x18000ccb4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ccb9  mov     [rbp+57h+var_90], 20h ; ' '
0x18000ccc0  mov     rcx, rdi; Src
0x18000ccc3  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18000ccc8  nop
0x18000ccc9  mov     rcx, rbx
0x18000cccc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ccd1  nop
0x18000ccd2  mov     rax, rdi
0x18000ccd5  mov     rcx, [rbp+57h+var_38]
0x18000ccd9  xor     rcx, rsp; StackCookie
0x18000ccdc  call    __security_check_cookie
0x18000cce1  add     rsp, 88h
0x18000cce8  pop     r15
0x18000ccea  pop     r14
0x18000ccec  pop     rdi
0x18000cced  pop     rsi
0x18000ccee  pop     rbx
0x18000ccef  pop     rbp
0x18000ccf0  retn
```

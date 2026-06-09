# EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::CreateInstance(_GUID const &,void * *,std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> const &,int)

- ea: `0x180017674`
- end: `0x18001776c`
- name: `?CreateInstance@?$EnumObject@UIEnumIFilterRules@@PEAUIFilterRule@@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@@SAJAEBU_GUID@@PEAPEAXAEBV?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@H@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017660`
- `0x180017840`

## callees

- `0x180001a30`
- `0x18001734c`
- `0x180017674`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::CreateInstance(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4)
{
  __int64 (***v6)(void); // rbx
  _QWORD *v8; // rdi
  __int64 (*v9)(void); // rax
  unsigned int v10; // edi
  _QWORD *v11; // [rsp+40h] [rbp+8h]

  v6 = 0;
  v11 = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  try
  {
    v8 = operator new(0x30u);
    if ( v8 )
    {
      *v8 = &EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::`vftable';
      v8[2] = 0;
      v8[3] = 0;
      v8[4] = 0;
      *((_DWORD *)v8 + 2) = 0;
      std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::operator=((__int64)(v8 + 2), a3);
      *((_DWORD *)v8 + 10) = a4;
    }
    else
    {
      v8 = 0;
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
      v6 = (__int64 (***)(void))v8;
      v11 = v8;
    }
    v9 = **v6;
  }
  catch ( std::bad_alloc )
  {
    if ( v11 )
      (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
    return 2147942414LL;
  }
  v8 = operator new(0x30u);
  if ( v8 )
  {
    *v8 = &EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::`vftable';
    v8[2] = 0;
    v8[3] = 0;
    v8[4] = 0;
    *((_DWORD *)v8 + 2) = 0;
    std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::operator=((__int64)(v8 + 2), a3);
    *((_DWORD *)v8 + 10) = a4;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
    v6 = (__int64 (***)(void))v8;
    v11 = v8;
  }
}

```

## disassembly

```asm
0x180017674  mov     rax, rsp
0x180017677  mov     [rax+18h], rbx
0x18001767b  mov     [rax+20h], rsi
0x18001767f  mov     [rax+8], rcx
0x180017683  push    rdi
0x180017684  push    r14
0x180017686  push    r15
0x180017688  sub     rsp, 20h
0x18001768c  mov     r14d, r9d
0x18001768f  mov     r15, r8
0x180017692  mov     rsi, rdx
0x180017695  xor     ebx, ebx
0x180017697  mov     [rax+8], rbx
0x18001769b  test    rdx, rdx
0x18001769e  jnz     short loc_1800176AA
0x1800176a0  mov     eax, 80004003h
0x1800176a5  jmp     loc_180017758
0x1800176aa  mov     [rdx], rbx
0x1800176ad  mov     ecx, 30h ; '0'; Size
0x1800176b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800176b7  mov     rdi, rax
0x1800176ba  mov     [rsp+38h+arg_8], rax
0x1800176bf  test    rax, rax
0x1800176c2  jz      short loc_1800176EE
0x1800176c4  lea     rax, ??_7?$EnumObject@UIEnumIFilterRules@@PEAUIFilterRule@@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@@6B@; const EnumObject<IEnumIFilterRules,IFilterRule *,Microsoft::WRL::ComPtr<IFilterRule>>::`vftable'
0x1800176cb  mov     [rdi], rax
0x1800176ce  lea     rcx, [rdi+10h]
0x1800176d2  mov     [rcx], rbx
0x1800176d5  mov     [rcx+8], rbx
0x1800176d9  mov     [rcx+10h], rbx
0x1800176dd  mov     [rdi+8], ebx
0x1800176e0  mov     rdx, r15
0x1800176e3  call    ??4?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::operator=(std::vector<Microsoft::WRL::ComPtr<IFilterRule>> const &)
0x1800176e8  mov     [rdi+28h], r14d
0x1800176ec  jmp     short loc_1800176F1
0x1800176ee  mov     rdi, rbx
0x1800176f1  test    rdi, rdi
0x1800176f4  jz      short loc_18001770E
0x1800176f6  mov     rax, [rdi]
0x1800176f9  mov     rcx, rdi
0x1800176fc  mov     rax, [rax+8]
0x180017700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017705  nop
0x180017706  mov     rbx, rdi
0x180017709  mov     [rsp+38h+arg_0], rbx
0x18001770e  mov     rax, [rbx]
0x180017711  mov     r8, rsi
0x180017714  lea     rdx, _GUID_bf77ef2c_0b71_4ea8_903f_a8ffa71e4e54
0x18001771b  mov     rcx, rbx
0x18001771e  mov     rax, [rax]
0x180017721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017726  mov     edi, eax
0x180017728  mov     rdx, [rbx]
0x18001772b  mov     rcx, rbx
0x18001772e  mov     rax, [rdx+10h]
0x180017732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017737  nop
0x180017738  mov     eax, edi
0x18001773a  jmp     short loc_180017758
0x18001773c  mov     rcx, [rsp+38h+arg_0]
0x180017741  test    rcx, rcx
0x180017744  jz      short loc_180017753
0x180017746  mov     rax, [rcx]
0x180017749  mov     rax, [rax+10h]
0x18001774d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017752  nop
0x180017753  mov     eax, 8007000Eh
0x180017758  mov     rbx, [rsp+38h+arg_10]
0x18001775d  mov     rsi, [rsp+38h+arg_18]
0x180017762  add     rsp, 20h
0x180017766  pop     r15
0x180017768  pop     r14
0x18001776a  pop     rdi
0x18001776b  retn
```

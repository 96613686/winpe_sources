# RequiredLanguageFeaturesInstaller::~RequiredLanguageFeaturesInstaller(void)

- ea: `0x180013388`
- end: `0x180013471`
- name: `??1RequiredLanguageFeaturesInstaller@@QEAA@XZ`
- size: `233`
- prototype: `void __fastcall(RequiredLanguageFeaturesInstaller *this, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800140e0`
- `0x180028d02`

## callees

- `0x1800126fc`
- `0x180012b94`
- `0x180013388`
- `0x1800214f4`
- `0x18002a010`

## pseudocode

```c
void __fastcall RequiredLanguageFeaturesInstaller::~RequiredLanguageFeaturesInstaller(
        RequiredLanguageFeaturesInstaller *this,
        __int64 a2)
{
  char *v2; // rdi
  char *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = (char *)this + 280;
  v4 = (char *)*((_QWORD *)this + 42);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v2;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *((_QWORD *)v2 + 7) = 0;
  }
  v5 = *((_QWORD *)this + 34);
  if ( v5 )
  {
    LOBYTE(a2) = v5 != (_QWORD)this + 216;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 32LL))(v5, a2);
    *((_QWORD *)this + 34) = 0;
  }
  v6 = *((_QWORD *)this + 26);
  if ( v6 )
  {
    LOBYTE(a2) = v6 != (_QWORD)this + 152;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, a2);
    *((_QWORD *)this + 26) = 0;
  }
  v7 = *((_QWORD *)this + 18);
  if ( v7 )
  {
    LOBYTE(a2) = v7 != (_QWORD)this + 88;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, a2);
    *((_QWORD *)this + 18) = 0;
  }
  std::_Tree<std::_Tmap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::less<enum PayloadType>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::~_Tree<std::_Tmap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::less<enum PayloadType>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>((char *)this + 72);
  std::vector<enum PayloadType>::~vector<enum PayloadType>((char **)this + 6);
  std::vector<std::wstring>::_Tidy((char *)this + 24);
  std::vector<std::wstring>::_Tidy(this);
}

```

## disassembly

```asm
0x180013388  mov     [rsp+arg_0], rbx
0x18001338d  mov     [rsp+arg_8], rsi
0x180013392  push    rdi
0x180013393  sub     rsp, 20h
0x180013397  lea     rdi, [rcx+118h]
0x18001339e  mov     rbx, rcx
0x1800133a1  mov     rcx, [rdi+38h]
0x1800133a5  test    rcx, rcx
0x1800133a8  jz      short loc_1800133C4
0x1800133aa  mov     rax, [rcx]
0x1800133ad  cmp     rcx, rdi
0x1800133b0  setnz   dl
0x1800133b3  mov     rax, [rax+20h]
0x1800133b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133bc  mov     qword ptr [rdi+38h], 0
0x1800133c4  lea     rdi, [rbx+0D8h]
0x1800133cb  mov     rcx, [rdi+38h]
0x1800133cf  test    rcx, rcx
0x1800133d2  jz      short loc_1800133EE
0x1800133d4  mov     rax, [rcx]
0x1800133d7  cmp     rcx, rdi
0x1800133da  setnz   dl
0x1800133dd  mov     rax, [rax+20h]
0x1800133e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e6  mov     qword ptr [rdi+38h], 0
0x1800133ee  lea     rdi, [rbx+98h]
0x1800133f5  mov     rcx, [rdi+38h]
0x1800133f9  test    rcx, rcx
0x1800133fc  jz      short loc_180013418
0x1800133fe  mov     rax, [rcx]
0x180013401  cmp     rcx, rdi
0x180013404  setnz   dl
0x180013407  mov     rax, [rax+20h]
0x18001340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013410  mov     qword ptr [rdi+38h], 0
0x180013418  lea     rsi, [rbx+58h]
0x18001341c  mov     rcx, [rsi+38h]
0x180013420  test    rcx, rcx
0x180013423  jz      short loc_18001343F
0x180013425  mov     rax, [rcx]
0x180013428  cmp     rcx, rsi
0x18001342b  setnz   dl
0x18001342e  mov     rax, [rax+20h]
0x180013432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013437  mov     qword ptr [rsi+38h], 0
0x18001343f  lea     rcx, [rbx+48h]
0x180013443  call    ??1?$_Tree@V?$_Tmap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@U?$less@W4PayloadType@@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::less<PayloadType>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::~_Tree<std::_Tmap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::less<PayloadType>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>(void)
0x180013448  lea     rcx, [rbx+30h]
0x18001344c  call    ??1?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@QEAA@XZ; std::vector<PayloadType>::~vector<PayloadType>(void)
0x180013451  lea     rcx, [rbx+18h]
0x180013455  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001345a  mov     rcx, rbx
0x18001345d  mov     rbx, [rsp+28h+arg_0]
0x180013462  mov     rsi, [rsp+28h+arg_8]
0x180013467  add     rsp, 20h
0x18001346b  pop     rdi
0x18001346c  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```

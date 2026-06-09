# std::basic_filebuf<char,std::char_traits<char>>::open(char const *,int,int)

- ea: `0x182d47420`
- end: `0x182d4750f`
- name: `?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBDHH@Z`
- size: `239`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x182d463f0`
- `0x1830457a0`
- `0x183056020`
- `0x1830569f0`
- `0x1832b5910`

## callees

- `0x182d3e3b0`
- `0x182d46a50`
- `0x182d47420`
- `0x182dc4440`

## import_xrefs

- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x182d47495`
- `MSVCP140!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x182d47495`
- `MSVCP140!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x182d47480`
- `MSVCP140!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x182d47480`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x182d474b0`
- `MSVCP140!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x182d474b0`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x182d47458`
- `MSVCP140!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x182d47458`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::filebuf::open(__int64 a1, const char *a2, int a3, int a4)
{
  struct _iobuf *v5; // rax
  __int64 v6; // rax
  std::codecvt_base *v7; // rbx
  void (__fastcall ***v8)(_QWORD, __int64); // rax
  _BYTE v10[8]; // [rsp+28h] [rbp-20h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v5 = std::_Fiopen(a2, a3, a4);
  if ( !v5 )
    return 0;
  std::filebuf::_Init(a1, v5, 1);
  v6 = std::streambuf::getloc(a1, v10);
  v7 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v6);
  if ( std::codecvt_base::always_noconv(v7) )
  {
    *(_QWORD *)(a1 + 104) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 104) = v7;
    std::streambuf::_Init(a1);
  }
  if ( v11 )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v8 )
      (**v8)(v8, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x182d47420  push    rdi
0x182d47422  sub     rsp, 40h
0x182d47426  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x182d4742f  mov     [rsp+48h+arg_0], rbx
0x182d47434  mov     [rsp+48h+arg_8], rsi
0x182d47439  mov     eax, r8d
0x182d4743c  mov     r10, rdx
0x182d4743f  mov     rdi, rcx
0x182d47442  cmp     qword ptr [rcx+80h], 0
0x182d4744a  jnz     loc_182D474FD
0x182d47450  mov     r8d, r9d
0x182d47453  mov     edx, eax
0x182d47455  mov     rcx, r10
0x182d47458  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z; std::_Fiopen(char const *,int,int)
0x182d4745e  test    rax, rax
0x182d47461  jz      loc_182D474FD
0x182d47467  mov     r8d, 1
0x182d4746d  mov     rdx, rax
0x182d47470  mov     rcx, rdi
0x182d47473  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x182d47478  lea     rdx, [rsp+48h+var_20]
0x182d4747d  mov     rcx, rdi
0x182d47480  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x182d47486  nop
0x182d47487  mov     rcx, rax
0x182d4748a  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x182d4748f  mov     rbx, rax
0x182d47492  mov     rcx, rax
0x182d47495  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x182d4749b  test    al, al
0x182d4749d  jz      short loc_182D474A9
0x182d4749f  mov     qword ptr [rdi+68h], 0
0x182d474a7  jmp     short loc_182D474B7
0x182d474a9  mov     [rdi+68h], rbx
0x182d474ad  mov     rcx, rdi
0x182d474b0  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x182d474b6  nop
0x182d474b7  mov     rsi, [rsp+48h+var_18]
0x182d474bc  test    rsi, rsi
0x182d474bf  jz      short loc_182D474F8
0x182d474c1  mov     rax, [rsi]
0x182d474c4  mov     rbx, [rax+10h]
0x182d474c8  mov     rcx, rbx; this
0x182d474cb  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182d474d1  mov     rcx, rsi
0x182d474d4  call    rbx
0x182d474d6  mov     rsi, rax
0x182d474d9  test    rax, rax
0x182d474dc  jz      short loc_182D474F8
0x182d474de  mov     rcx, [rax]
0x182d474e1  mov     rbx, [rcx]
0x182d474e4  mov     rcx, rbx; this
0x182d474e7  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182d474ed  mov     edx, 1
0x182d474f2  mov     rcx, rsi
0x182d474f5  call    rbx
0x182d474f7  nop
0x182d474f8  mov     rax, rdi
0x182d474fb  jmp     short loc_182D474FF
0x182d474fd  xor     eax, eax
0x182d474ff  mov     rbx, [rsp+48h+arg_0]
0x182d47504  mov     rsi, [rsp+48h+arg_8]
0x182d47509  add     rsp, 40h
0x182d4750d  pop     rdi
0x182d4750e  retn
```

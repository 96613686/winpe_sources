# Mso::Json::TWriter<wchar_t>::TWriter<wchar_t>(Mso::Json::TIOutput<wchar_t> &,Mso::Json::PrettyPrint)

- ea: `0x18001bfd0`
- end: `0x18001c17a`
- name: `??0?$TWriter@_W@Json@Mso@@QEAA@AEAU?$TIOutput@_W@12@W4PrettyPrint@12@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001bed0`

## callees

- `0x180001bac`
- `0x1800046d8`
- `0x18000ab0c`
- `0x18001bfd0`
- `0x18002b3c0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001c138`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001c138`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001c048`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001c048`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001c121`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001c121`

## pseudocode

```c
__int64 __fastcall Mso::Json::TWriter<wchar_t>::TWriter<wchar_t>(__int64 a1, void (__fastcall ***a2)(_QWORD), int a3)
{
  void **v5; // rbx
  _QWORD *v6; // rdi
  _QWORD *v7; // rax
  unsigned __int64 v8; // rsi
  void *v9; // rbp
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  void *v12; // r14
  size_t v13; // r8
  _QWORD *v14; // rdi
  void *v16; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)a1 = &Mso::Json::TWriter<wchar_t>::`vftable';
  v5 = (void **)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 40) = a2;
  (**a2)(a2);
  v6 = (_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v7 = malloc(0x10u);
  if ( !v7 )
    std::_Xbad_alloc();
  v7[1] = 0;
  *v6 = v7;
  *v7 = v6;
  *(_BYTE *)(a1 + 92) = 0;
  *(_DWORD *)(a1 + 96) = a3;
  v8 = (unsigned __int64)v5[3];
  if ( v8 < 0x1000 )
  {
    v9 = v5[2];
    v10 = 0x7FFFFFFFFFFFFFFELL;
    if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v9 < (unsigned __int64)(4096LL - (_QWORD)v9) )
      std::_Xlen_string();
    v11 = v8 >> 1;
    if ( v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1) )
    {
      v10 = 4103;
      if ( v11 + v8 > 0x1007 )
        v10 = v11 + v8;
    }
    v16 = (void *)v10;
    v12 = (void *)std::wstring::_Allocate_for_capacity<0>(v5, &v16);
    v5[2] = (void *)4096;
    v5[3] = v16;
    v13 = 2LL * (_QWORD)v9 + 2;
    if ( v8 <= 7 )
    {
      memmove(v12, v5, v13);
    }
    else
    {
      v14 = *v5;
      memmove(v12, *v5, v13);
      if ( 2 * v8 + 2 >= 0x1000 )
      {
        if ( (unsigned __int64)v14 - *(v14 - 1) - 8 > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
        v14 = (_QWORD *)*(v14 - 1);
      }
      free(v14);
    }
    *v5 = v12;
    v5[2] = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x18001bfd0  mov     [rsp+arg_8], rbx
0x18001bfd5  mov     [rsp+arg_10], rbp
0x18001bfda  mov     [rsp+arg_18], rsi
0x18001bfdf  push    rdi
0x18001bfe0  push    r12
0x18001bfe2  push    r13
0x18001bfe4  push    r14
0x18001bfe6  push    r15
0x18001bfe8  sub     rsp, 30h
0x18001bfec  mov     esi, r8d
0x18001bfef  mov     r15, rcx
0x18001bff2  lea     rax, ??_7?$TWriter@_W@Json@Mso@@6B@; const Mso::Json::TWriter<wchar_t>::`vftable'
0x18001bff9  mov     [rcx], rax
0x18001bffc  lea     rbx, [rcx+8]
0x18001c000  xorps   xmm0, xmm0
0x18001c003  movups  xmmword ptr [rbx], xmm0
0x18001c006  xor     r12d, r12d
0x18001c009  mov     [rbx+10h], r12
0x18001c00d  mov     qword ptr [rbx+18h], 7
0x18001c015  mov     [rbx], r12w
0x18001c019  mov     [rcx+28h], rdx
0x18001c01d  mov     rax, [rdx]
0x18001c020  mov     rcx, rdx
0x18001c023  mov     rax, [rax]
0x18001c026  call    cs:__guard_dispatch_icall_fptr
0x18001c02c  lea     rdi, [r15+30h]
0x18001c030  mov     [rdi], r12
0x18001c033  mov     [rdi+8], r12
0x18001c037  mov     [rdi+10h], r12
0x18001c03b  mov     [rdi+18h], r12
0x18001c03f  mov     [rdi+20h], r12
0x18001c043  lea     ecx, [r12+10h]; Size
0x18001c048  call    cs:__imp_malloc
0x18001c04e  test    rax, rax
0x18001c051  jz      loc_18001C174
0x18001c057  mov     [rax+8], r12
0x18001c05b  mov     [rdi], rax
0x18001c05e  mov     [rax], rdi
0x18001c061  mov     [r15+5Ch], r12b
0x18001c065  mov     [r15+60h], esi
0x18001c069  mov     rsi, [rbx+18h]
0x18001c06d  mov     r13d, 1000h
0x18001c073  cmp     rsi, r13
0x18001c076  jnb     loc_18001C14E
0x18001c07c  mov     rbp, [rbx+10h]
0x18001c080  mov     ecx, r13d
0x18001c083  sub     rcx, rbp
0x18001c086  mov     rdx, 7FFFFFFFFFFFFFFEh
0x18001c090  mov     rax, rdx
0x18001c093  sub     rax, rbp
0x18001c096  cmp     rax, rcx
0x18001c099  jb      loc_18001C16E
0x18001c09f  mov     rcx, rsi
0x18001c0a2  shr     rcx, 1
0x18001c0a5  mov     rax, rdx
0x18001c0a8  sub     rax, rcx
0x18001c0ab  cmp     rsi, rax
0x18001c0ae  ja      short loc_18001C0BF
0x18001c0b0  lea     rax, [rcx+rsi]
0x18001c0b4  lea     edx, [r13+7]
0x18001c0b8  cmp     rax, rdx
0x18001c0bb  cmova   rdx, rax
0x18001c0bf  mov     [rsp+58h+arg_0], rdx
0x18001c0c4  lea     rdx, [rsp+58h+arg_0]
0x18001c0c9  mov     rcx, rbx
0x18001c0cc  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x18001c0d1  mov     r14, rax
0x18001c0d4  mov     [rbx+10h], r13
0x18001c0d8  mov     rcx, [rsp+58h+arg_0]
0x18001c0dd  mov     [rbx+18h], rcx
0x18001c0e1  lea     r8, ds:2[rbp*2]; Size
0x18001c0e9  mov     rcx, rax; void *
0x18001c0ec  cmp     rsi, 7
0x18001c0f0  jbe     short loc_18001C13F
0x18001c0f2  mov     rdi, [rbx]
0x18001c0f5  mov     rdx, rdi; Src
0x18001c0f8  call    memmove
0x18001c0fd  lea     rcx, ds:2[rsi*2]
0x18001c105  cmp     rcx, r13
0x18001c108  jb      short loc_18001C11E
0x18001c10a  mov     rcx, [rdi-8]
0x18001c10e  sub     rdi, rcx
0x18001c111  lea     rax, [rdi-8]
0x18001c115  cmp     rax, 1Fh
0x18001c119  ja      short loc_18001C129
0x18001c11b  mov     rdi, rcx
0x18001c11e  mov     rcx, rdi; Block
0x18001c121  call    cs:__imp_free
0x18001c127  jmp     short loc_18001C147
0x18001c129  mov     [rsp+58h+Reserved], r12; Reserved
0x18001c12e  xor     r9d, r9d; LineNo
0x18001c131  xor     r8d, r8d; FileName
0x18001c134  xor     edx, edx; FunctionName
0x18001c136  xor     ecx, ecx; Expression
0x18001c138  call    cs:__imp__invoke_watson
0x18001c13f  mov     rdx, rbx; Src
0x18001c142  call    memmove
0x18001c147  mov     [rbx], r14
0x18001c14a  mov     [rbx+10h], rbp
0x18001c14e  mov     rax, r15
0x18001c151  mov     rbx, [rsp+58h+arg_8]
0x18001c156  mov     rbp, [rsp+58h+arg_10]
0x18001c15b  mov     rsi, [rsp+58h+arg_18]
0x18001c160  add     rsp, 30h
0x18001c164  pop     r15
0x18001c166  pop     r14
0x18001c168  pop     r13
0x18001c16a  pop     r12
0x18001c16c  pop     rdi
0x18001c16d  retn
0x18001c16e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001c174  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```

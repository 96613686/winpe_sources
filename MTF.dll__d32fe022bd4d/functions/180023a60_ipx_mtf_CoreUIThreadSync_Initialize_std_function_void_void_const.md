# ipx::mtf::CoreUIThreadSync::Initialize(std::function<void (void)> const &)

- ea: `0x180023a60`
- end: `0x180023b47`
- name: `?Initialize@CoreUIThreadSync@mtf@ipx@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e914`

## callees

- `0x180006074`
- `0x180023a60`
- `0x18002f010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x180023acb`
- `CoreMessaging!CoreUICreate` at `0x180023acb`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CoreUIThreadSync::Initialize(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  __int64 (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = a2;
  if ( a1 != a2 )
  {
    v4 = *(_QWORD *)(a1 + 24);
    if ( v4 )
    {
      LOBYTE(a2) = v4 != a1;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
      *(_QWORD *)(a1 + 24) = 0;
    }
    v5 = *(__int64 (__fastcall ****)(_QWORD, __int64))(v2 + 24);
    if ( v5 )
    {
      if ( v5 == (__int64 (__fastcall ***)(_QWORD, __int64))v2 )
        v6 = a1;
      else
        v6 = 0;
      *(_QWORD *)(a1 + 24) = (**v5)(v5, v6);
    }
    else
    {
      *(_QWORD *)(a1 + 24) = 0;
    }
  }
  v7 = CoreUICreate(a1 + 32);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(), __int64, __int64))(**(_QWORD **)(a1 + 32) + 112LL))(
            *(_QWORD *)(a1 + 32),
            lambda_45ca3f79ebc511d2717264bbc15ea449_::_lambda_invoker_cdecl_,
            a1,
            a1 + 40);
    v11 = v10;
    if ( v10 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
        (const char *)(unsigned int)v10,
        v12);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\coreuiadapter.cpp",
      (const char *)(unsigned int)v7,
      v12);
    return v8;
  }
}

```

## disassembly

```asm
0x180023a60  mov     [rsp+arg_0], rbx
0x180023a65  mov     [rsp+arg_8], rsi
0x180023a6a  push    rdi
0x180023a6b  sub     rsp, 30h
0x180023a6f  mov     rdi, rdx
0x180023a72  mov     rbx, rcx
0x180023a75  cmp     rcx, rdx
0x180023a78  jz      short loc_180023AC7
0x180023a7a  mov     rcx, [rcx+18h]
0x180023a7e  test    rcx, rcx
0x180023a81  jz      short loc_180023A9D
0x180023a83  mov     rax, [rcx]
0x180023a86  cmp     rcx, rbx
0x180023a89  setnz   dl
0x180023a8c  mov     rax, [rax+20h]
0x180023a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a95  mov     qword ptr [rbx+18h], 0
0x180023a9d  mov     rcx, [rdi+18h]
0x180023aa1  test    rcx, rcx
0x180023aa4  jnz     short loc_180023AAC
0x180023aa6  mov     [rbx+18h], rcx
0x180023aaa  jmp     short loc_180023AC7
0x180023aac  mov     rax, [rcx]
0x180023aaf  mov     rax, [rax]
0x180023ab2  cmp     rcx, rdi
0x180023ab5  jnz     short loc_180023ABC
0x180023ab7  mov     rdx, rbx
0x180023aba  jmp     short loc_180023ABE
0x180023abc  xor     edx, edx
0x180023abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ac3  mov     [rbx+18h], rax
0x180023ac7  lea     rcx, [rbx+20h]
0x180023acb  call    cs:__imp_CoreUICreate
0x180023ad1  mov     edi, eax
0x180023ad3  test    eax, eax
0x180023ad5  jns     short loc_180023AF4
0x180023ad7  mov     rcx, [rsp+38h]; this
0x180023adc  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023ae3  mov     r9d, eax; char *
0x180023ae6  mov     edx, 123h; void *
0x180023aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023af0  mov     eax, edi
0x180023af2  jmp     short loc_180023B37
0x180023af4  mov     rcx, [rbx+20h]
0x180023af8  lea     r9, [rbx+28h]
0x180023afc  mov     r8, rbx
0x180023aff  lea     rdx, _lambda_45ca3f79ebc511d2717264bbc15ea449____lambda_invoker_cdecl_
0x180023b06  mov     rax, [rcx]
0x180023b09  mov     rax, [rax+70h]
0x180023b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b12  mov     ebx, eax
0x180023b14  test    eax, eax
0x180023b16  jns     short loc_180023B35
0x180023b18  mov     rcx, [rsp+38h]; this
0x180023b1d  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023b24  mov     r9d, eax; char *
0x180023b27  mov     edx, 12Ch; void *
0x180023b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b31  mov     eax, ebx
0x180023b33  jmp     short loc_180023B37
0x180023b35  xor     eax, eax
0x180023b37  mov     rbx, [rsp+38h+arg_0]
0x180023b3c  mov     rsi, [rsp+38h+arg_8]
0x180023b41  add     rsp, 30h
0x180023b45  pop     rdi
0x180023b46  retn
```

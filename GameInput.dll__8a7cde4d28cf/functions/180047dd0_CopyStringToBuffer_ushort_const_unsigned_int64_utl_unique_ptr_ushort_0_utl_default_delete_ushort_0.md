# CopyStringToBuffer(ushort const *,unsigned __int64,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &)

- ea: `0x180047dd0`
- end: `0x18004802c`
- name: `?CopyStringToBuffer@@YAJPEBG_KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180030308`
- `0x180030ee0`
- `0x18003c910`
- `0x18003d640`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x180047dd0`
- `0x18004c88d`

## import_xrefs

- `ntdll!wcsnlen` at `0x180047ec5`
- `ntdll!wcsnlen` at `0x180047ec5`
- `ntdll!RtlAllocateHeap` at `0x180047e1a`
- `ntdll!RtlAllocateHeap` at `0x180047f77`
- `ntdll!RtlAllocateHeap` at `0x180047e1a`
- `ntdll!RtlAllocateHeap` at `0x180047f77`

## pseudocode

```c
__int64 __fastcall CopyStringToBuffer(const wchar_t *Src, const struct std::nothrow_t *a2, void **a3)
{
  _WORD *v5; // rcx
  PVOID Heap; // rax
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  void *v10; // rcx
  __int64 v11; // rcx
  char *v12; // rdx
  __int64 result; // rax
  size_t v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  size_t v17; // rsi
  SIZE_T v18; // rax
  unsigned __int64 v19; // kr00_8
  PVOID v20; // rax
  const struct std::nothrow_t *v21; // rdx
  void *v22; // rcx
  int v23; // [rsp+60h] [rbp+20h] BYREF
  const struct std::nothrow_t *v24; // [rsp+68h] [rbp+28h] BYREF
  const char *v25; // [rsp+70h] [rbp+30h] BYREF

  v24 = a2;
  v5 = *a3;
  *a3 = 0;
  if ( v5 )
    operator delete(v5, a2);
  if ( !Src )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2u);
    v10 = *a3;
    *a3 = Heap;
    if ( v10 )
      operator delete(v10, v7);
    if ( *a3 )
    {
      result = 0;
      *(_WORD *)*a3 = 0;
      return result;
    }
    if ( (unsigned int)dword_180069000 <= 2 )
      return 2147942414LL;
    v11 = 512;
    if ( (qword_180069010 & 0x200) == 0 || (qword_180069018 & 0x200) != qword_180069018 )
      return 2147942414LL;
    v23 = 17;
    v25 = "onecore\\xbox\\gameinput\\providers\\ProviderString.cpp";
    v12 = &byte_180063C5F;
    goto LABEL_27;
  }
  v14 = wcsnlen(Src, 0xC8u);
  if ( v14 < 0xC8 )
  {
    v17 = v14 + 1;
    v19 = v14 + 1;
    v18 = 2 * (v14 + 1);
    if ( !is_mul_ok(v19, 2u) )
      v18 = -1;
    v20 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
    v22 = *a3;
    *a3 = v20;
    if ( v22 )
      operator delete(v22, v21);
    if ( !*a3 )
    {
      if ( (unsigned int)dword_180069000 <= 2
        || (qword_180069010 & 0x200) == 0
        || (qword_180069018 & 0x200) != qword_180069018 )
      {
        return 2147942414LL;
      }
      v23 = 28;
      v25 = "onecore\\xbox\\gameinput\\providers\\ProviderString.cpp";
      v12 = byte_180063A7B;
      v11 = (__int64)&v25;
LABEL_27:
      LODWORD(v24) = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned __int8 *)v12,
        v8,
        v9,
        (__int64 **)&v25,
        (__int64)&v23,
        (__int64)&v24);
      return 2147942414LL;
    }
    memcpy_0(*a3, Src, 2 * v17);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x200) != 0
      && (qword_180069018 & 0x200) == qword_180069018 )
    {
      LODWORD(v24) = -2147024809;
      v25 = "onecore\\xbox\\gameinput\\providers\\ProviderString.cpp";
      v23 = 23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        512,
        (unsigned __int8 *)&word_180063D66,
        v15,
        v16,
        (__int64 **)&v25,
        (__int64)&v23,
        (__int64)&v24);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180047dd0  mov     [rsp-18h+arg_18], rbx
0x180047dd5  mov     [rsp-18h+arg_8], rdx
0x180047dda  push    rbp
0x180047ddb  push    rsi
0x180047ddc  push    rdi
0x180047ddd  mov     rbp, rsp
0x180047de0  sub     rsp, 40h
0x180047de4  mov     rdi, rcx
0x180047de7  mov     rbx, r8
0x180047dea  mov     rcx, [r8]; P
0x180047ded  mov     qword ptr [r8], 0
0x180047df4  test    rcx, rcx
0x180047df7  jz      short loc_180047DFE
0x180047df9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047dfe  test    rdi, rdi
0x180047e01  jnz     loc_180047EBB
0x180047e07  mov     rcx, gs:60h
0x180047e10  lea     r8d, [rdi+2]; Size
0x180047e14  xor     edx, edx; Flags
0x180047e16  mov     rcx, [rcx+30h]; HeapHandle
0x180047e1a  call    cs:__imp_RtlAllocateHeap
0x180047e21  nop     dword ptr [rax+rax+00h]
0x180047e26  mov     rcx, [rbx]; P
0x180047e29  mov     [rbx], rax
0x180047e2c  test    rcx, rcx
0x180047e2f  jz      short loc_180047E36
0x180047e31  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047e36  mov     rcx, [rbx]
0x180047e39  test    rcx, rcx
0x180047e3c  jnz     short loc_180047EB1
0x180047e3e  mov     eax, cs:dword_180069000
0x180047e44  cmp     eax, 2
0x180047e47  jbe     loc_180048009
0x180047e4d  mov     rdx, cs:qword_180069018
0x180047e54  mov     ecx, 200h
0x180047e59  mov     rax, cs:qword_180069010
0x180047e60  test    rcx, rax
0x180047e63  jz      loc_180048009
0x180047e69  mov     rax, rdx
0x180047e6c  and     rax, rcx
0x180047e6f  cmp     rax, rdx
0x180047e72  jnz     loc_180048009
0x180047e78  lea     rax, aOnecoreXboxGam_24; "onecore\\xbox\\gameinput\\providers\\Pr"...
0x180047e7f  mov     [rbp+arg_0], 11h
0x180047e86  mov     [rbp+arg_10], rax
0x180047e8a  lea     rdx, byte_180063C5F
0x180047e91  lea     rax, [rbp+arg_8]
0x180047e95  mov     [rsp+40h+var_10], rax
0x180047e9a  lea     rax, [rbp+arg_0]
0x180047e9e  mov     [rsp+40h+var_18], rax
0x180047ea3  lea     rax, [rbp+arg_10]
0x180047ea7  mov     [rsp+40h+var_20], rax
0x180047eac  jmp     loc_180047FFD
0x180047eb1  xor     eax, eax
0x180047eb3  mov     [rcx], ax
0x180047eb6  jmp     loc_18004801E
0x180047ebb  mov     esi, 0C8h
0x180047ec0  mov     rcx, rdi; Source
0x180047ec3  mov     edx, esi; MaxCount
0x180047ec5  call    cs:__imp_wcsnlen
0x180047ecc  nop     dword ptr [rax+rax+00h]
0x180047ed1  cmp     rax, rsi
0x180047ed4  jb      short loc_180047F4E
0x180047ed6  mov     eax, cs:dword_180069000
0x180047edc  cmp     eax, 2
0x180047edf  jbe     short loc_180047F44
0x180047ee1  mov     rdx, cs:qword_180069018
0x180047ee8  mov     ecx, 200h
0x180047eed  mov     rax, cs:qword_180069010
0x180047ef4  test    rcx, rax
0x180047ef7  jz      short loc_180047F44
0x180047ef9  mov     rax, rdx
0x180047efc  and     rax, rcx
0x180047eff  cmp     rax, rdx
0x180047f02  jnz     short loc_180047F44
0x180047f04  lea     rax, aOnecoreXboxGam_24; "onecore\\xbox\\gameinput\\providers\\Pr"...
0x180047f0b  mov     dword ptr [rbp+arg_8], 80070057h
0x180047f12  mov     [rbp+arg_10], rax
0x180047f16  lea     rdx, word_180063D66
0x180047f1d  lea     rax, [rbp+arg_8]
0x180047f21  mov     [rbp+arg_0], 17h
0x180047f28  mov     [rsp+40h+var_10], rax
0x180047f2d  lea     rax, [rbp+arg_0]
0x180047f31  mov     [rsp+40h+var_18], rax
0x180047f36  lea     rax, [rbp+arg_10]
0x180047f3a  mov     [rsp+40h+var_20], rax
0x180047f3f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180047f44  mov     eax, 80070057h
0x180047f49  jmp     loc_18004801E
0x180047f4e  lea     rsi, [rax+1]
0x180047f52  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180047f59  mov     eax, 2
0x180047f5e  mul     rsi
0x180047f61  cmovb   rax, rcx
0x180047f65  mov     rcx, gs:60h
0x180047f6e  mov     r8, rax; Size
0x180047f71  xor     edx, edx; Flags
0x180047f73  mov     rcx, [rcx+30h]; HeapHandle
0x180047f77  call    cs:__imp_RtlAllocateHeap
0x180047f7e  nop     dword ptr [rax+rax+00h]
0x180047f83  mov     rcx, [rbx]; P
0x180047f86  mov     [rbx], rax
0x180047f89  test    rcx, rcx
0x180047f8c  jz      short loc_180047F93
0x180047f8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180047f93  mov     rcx, [rbx]; void *
0x180047f96  test    rcx, rcx
0x180047f99  jnz     short loc_180048010
0x180047f9b  mov     eax, cs:dword_180069000
0x180047fa1  cmp     eax, 2
0x180047fa4  jbe     short loc_180048009
0x180047fa6  mov     rdx, cs:qword_180069018
0x180047fad  mov     ecx, 200h
0x180047fb2  mov     rax, cs:qword_180069010
0x180047fb9  test    rcx, rax
0x180047fbc  jz      short loc_180048009
0x180047fbe  mov     rax, rdx
0x180047fc1  and     rax, rcx
0x180047fc4  cmp     rax, rdx
0x180047fc7  jnz     short loc_180048009
0x180047fc9  lea     rcx, [rbp+arg_8]
0x180047fcd  mov     [rbp+arg_0], 1Ch
0x180047fd4  mov     [rsp+40h+var_10], rcx
0x180047fd9  lea     rax, aOnecoreXboxGam_24; "onecore\\xbox\\gameinput\\providers\\Pr"...
0x180047fe0  lea     rcx, [rbp+arg_0]
0x180047fe4  mov     [rbp+arg_10], rax
0x180047fe8  mov     [rsp+40h+var_18], rcx
0x180047fed  lea     rdx, byte_180063A7B
0x180047ff4  lea     rcx, [rbp+arg_10]
0x180047ff8  mov     [rsp+40h+var_20], rcx
0x180047ffd  mov     dword ptr [rbp+arg_8], 8007000Eh
0x180048004  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048009  mov     eax, 8007000Eh
0x18004800e  jmp     short loc_18004801E
0x180048010  lea     r8, [rsi+rsi]; Size
0x180048014  mov     rdx, rdi; Src
0x180048017  call    memcpy_0
0x18004801c  xor     eax, eax
0x18004801e  mov     rbx, [rsp+40h+arg_18]
0x180048023  add     rsp, 40h
0x180048027  pop     rdi
0x180048028  pop     rsi
0x180048029  pop     rbp
0x18004802a  retn
```

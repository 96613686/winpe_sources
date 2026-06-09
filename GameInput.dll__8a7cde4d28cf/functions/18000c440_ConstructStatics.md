# ConstructStatics

- ea: `0x18000c440`
- end: `0x18000c561`
- name: `ConstructStatics`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d7a4`

## callees

- `0x180001304`
- `0x18000c440`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c4ae`
- `ntdll!RtlAllocateHeap` at `0x18000c4ae`

## string_xrefs

- `0x18000c4f7`: `onecore\xbox\gameinput\common\Crt.cpp`

## pseudocode

```c
__int64 ConstructStatics()
{
  unsigned __int64 v0; // rcx
  void (**v1)(void); // rbx
  __int64 (__fastcall **v2)(); // rax
  SIZE_T v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+58h] [rbp+10h] BYREF
  const char *v9; // [rsp+60h] [rbp+18h] BYREF

  v0 = qword_180069790;
  v1 = (void (**)(void))off_18006F008;
  v2 = off_18006F008;
  if ( off_18006F008 < (__int64 (__fastcall **)())qword_18006F030 )
  {
    do
    {
      if ( *v2 )
        ++v0;
      ++v2;
    }
    while ( v2 < (__int64 (__fastcall **)())qword_18006F030 );
    qword_180069790 = v0;
  }
  if ( !v0 )
    return 0;
  v3 = 8 * v0;
  if ( !is_mul_ok(v0, 8u) )
    v3 = -1;
  P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( P )
  {
    while ( v1 < (void (**)(void))qword_18006F030 )
    {
      if ( *v1 )
        (*v1)();
      ++v1;
    }
    return 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
  {
    v7 = -2147024882;
    v9 = "onecore\\xbox\\gameinput\\common\\Crt.cpp";
    v8 = 208;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&v9,
      (unsigned __int8 *)&word_180059E06,
      v4,
      v5,
      (__int64 **)&v9,
      (__int64)&v8,
      (__int64)&v7);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000c440  mov     [rsp+arg_18], rbx
0x18000c445  push    rdi
0x18000c446  sub     rsp, 40h
0x18000c44a  mov     rcx, cs:qword_180069790
0x18000c451  lea     rbx, off_18006F008
0x18000c458  lea     rdi, qword_18006F030
0x18000c45f  mov     rax, rbx
0x18000c462  cmp     rbx, rdi
0x18000c465  jnb     short loc_18000C480
0x18000c467  cmp     qword ptr [rax], 0
0x18000c46b  jz      short loc_18000C470
0x18000c46d  inc     rcx
0x18000c470  add     rax, 8
0x18000c474  cmp     rax, rdi
0x18000c477  jb      short loc_18000C467
0x18000c479  mov     cs:qword_180069790, rcx
0x18000c480  test    rcx, rcx
0x18000c483  jz      loc_18000C553
0x18000c489  mov     eax, 8
0x18000c48e  mul     rcx
0x18000c491  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c498  cmovb   rax, rcx
0x18000c49c  mov     rcx, gs:60h
0x18000c4a5  mov     r8, rax; Size
0x18000c4a8  xor     edx, edx; Flags
0x18000c4aa  mov     rcx, [rcx+30h]; HeapHandle
0x18000c4ae  call    cs:__imp_RtlAllocateHeap
0x18000c4b5  nop     dword ptr [rax+rax+00h]
0x18000c4ba  mov     cs:P, rax
0x18000c4c1  test    rax, rax
0x18000c4c4  jnz     loc_18000C54E
0x18000c4ca  mov     eax, cs:dword_180069000
0x18000c4d0  mov     ebx, 8007000Eh
0x18000c4d5  cmp     eax, 2
0x18000c4d8  jbe     short loc_18000C539
0x18000c4da  mov     rcx, cs:qword_180069018
0x18000c4e1  mov     rax, cs:qword_180069010
0x18000c4e8  test    al, 2
0x18000c4ea  jz      short loc_18000C539
0x18000c4ec  mov     rax, rcx
0x18000c4ef  and     eax, 2
0x18000c4f2  cmp     rax, rcx
0x18000c4f5  jnz     short loc_18000C539
0x18000c4f7  lea     rcx, aOnecoreXboxGam; "onecore\\xbox\\gameinput\\common\\Crt.c"...
0x18000c4fe  mov     [rsp+48h+arg_0], ebx
0x18000c502  mov     [rsp+48h+arg_10], rcx
0x18000c507  lea     rdx, word_180059E06
0x18000c50e  lea     rcx, [rsp+48h+arg_0]
0x18000c513  mov     [rsp+48h+arg_8], 0D0h
0x18000c51b  mov     [rsp+48h+var_18], rcx
0x18000c520  lea     rcx, [rsp+48h+arg_8]
0x18000c525  mov     [rsp+48h+var_20], rcx
0x18000c52a  lea     rcx, [rsp+48h+arg_10]
0x18000c52f  mov     [rsp+48h+var_28], rcx
0x18000c534  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c539  mov     eax, ebx
0x18000c53b  jmp     short loc_18000C555
0x18000c53d  mov     rax, [rbx]
0x18000c540  test    rax, rax
0x18000c543  jz      short loc_18000C54A
0x18000c545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c54a  add     rbx, 8
0x18000c54e  cmp     rbx, rdi
0x18000c551  jb      short loc_18000C53D
0x18000c553  xor     eax, eax
0x18000c555  mov     rbx, [rsp+48h+arg_18]
0x18000c55a  add     rsp, 40h
0x18000c55e  pop     rdi
0x18000c55f  retn
```

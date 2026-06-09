# CreateEventName

- ea: `0x140003a18`
- end: `0x140003b34`
- name: `CreateEventName`
- size: `284`
- prototype: `__int64 __fastcall(int, wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003e54`
- `0x140004950`

## callees

- `0x140001008`
- `0x140003a18`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140003a6a`
- `ntdll!RtlAllocateHeap` at `0x140003a6a`
- `ntdll!swprintf_s` at `0x140003b15`
- `ntdll!swprintf_s` at `0x140003b15`

## pseudocode

```c
__int64 __fastcall CreateEventName(int a1, wchar_t **a2)
{
  __int64 v4; // rax
  size_t v5; // rbp
  SIZE_T v6; // rax
  unsigned __int64 v7; // kr00_8
  wchar_t *Heap; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  wchar_t *v11; // rbx
  __int64 result; // rax
  __int64 *v13[7]; // [rsp+40h] [rbp-38h] BYREF
  int v14; // [rsp+90h] [rbp+18h] BYREF
  int v15; // [rsp+98h] [rbp+20h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( aGlobalGameinpu[v4] );
  v5 = v4 + 10;
  v7 = v4 + 10;
  v6 = 2 * (v4 + 10);
  if ( !is_mul_ok(v7, 2u) )
    v6 = -1;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  v11 = Heap;
  if ( Heap )
  {
    swprintf_s(Heap, v5, L"%ws_%x", L"Global\\GameInputSession", a1);
    result = 0;
    *a2 = v11;
  }
  else
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v14 = -2147024882;
      v13[0] = (__int64 *)"onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v15 = 110;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v13,
        (int)word_14000B1AA,
        v9,
        v10,
        v13,
        (__int64)&v15,
        (__int64)&v14);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x140003a18  mov     [rsp+arg_0], rbx
0x140003a1d  push    rbp
0x140003a1e  push    rsi
0x140003a1f  push    rdi
0x140003a20  push    r14
0x140003a22  push    r15
0x140003a24  sub     rsp, 50h
0x140003a28  mov     esi, ecx
0x140003a2a  lea     r14, aGlobalGameinpu; "Global\\GameInputSession"
0x140003a31  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140003a35  mov     rdi, rdx
0x140003a38  mov     rax, rcx
0x140003a3b  xor     r15d, r15d
0x140003a3e  inc     rax
0x140003a41  cmp     [r14+rax*2], r15w
0x140003a46  jnz     short loc_140003A3E
0x140003a48  lea     rbp, [rax+0Ah]
0x140003a4c  mov     eax, 2
0x140003a51  mul     rbp
0x140003a54  cmovb   rax, rcx
0x140003a58  mov     rcx, gs:60h
0x140003a61  mov     r8, rax; Size
0x140003a64  xor     edx, edx; Flags
0x140003a66  mov     rcx, [rcx+30h]; HeapHandle
0x140003a6a  call    cs:__imp_RtlAllocateHeap
0x140003a70  mov     rbx, rax
0x140003a73  test    rax, rax
0x140003a76  jnz     loc_140003B01
0x140003a7c  mov     eax, cs:dword_14000E000
0x140003a82  mov     ebx, 8007000Eh
0x140003a87  cmp     eax, 2
0x140003a8a  jbe     short loc_140003AFD
0x140003a8c  mov     rcx, cs:qword_14000E018
0x140003a93  mov     edx, 800h
0x140003a98  mov     rax, cs:qword_14000E010
0x140003a9f  test    rdx, rax
0x140003aa2  jz      short loc_140003AFD
0x140003aa4  mov     rax, rcx
0x140003aa7  and     rax, rdx
0x140003aaa  cmp     rax, rcx
0x140003aad  jnz     short loc_140003AFD
0x140003aaf  lea     rcx, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003ab6  mov     [rsp+78h+arg_10], ebx
0x140003abd  mov     [rsp+78h+var_38], rcx
0x140003ac2  lea     rdx, word_14000B1AA
0x140003ac9  lea     rcx, [rsp+78h+arg_10]
0x140003ad1  mov     [rsp+78h+arg_18], 6Eh ; 'n'
0x140003adc  mov     [rsp+78h+var_48], rcx
0x140003ae1  lea     rcx, [rsp+78h+arg_18]
0x140003ae9  mov     [rsp+78h+var_50], rcx
0x140003aee  lea     rcx, [rsp+78h+var_38]
0x140003af3  mov     [rsp+78h+var_58], rcx
0x140003af8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003afd  mov     eax, ebx
0x140003aff  jmp     short loc_140003B20
0x140003b01  mov     r9, r14
0x140003b04  mov     dword ptr [rsp+78h+var_58], esi
0x140003b08  lea     r8, aWsX_0; "%ws_%x"
0x140003b0f  mov     rdx, rbp; BufferCount
0x140003b12  mov     rcx, rbx; Buffer
0x140003b15  call    cs:__imp_swprintf_s
0x140003b1b  xor     eax, eax
0x140003b1d  mov     [rdi], rbx
0x140003b20  mov     rbx, [rsp+78h+arg_0]
0x140003b28  add     rsp, 50h
0x140003b2c  pop     r15
0x140003b2e  pop     r14
0x140003b30  pop     rdi
0x140003b31  pop     rsi
0x140003b32  pop     rbp
0x140003b33  retn
```

# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18003d528`
- end: `0x18003d5b0`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, const WCHAR **)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003ff68`
- `0x180047c78`
- `0x18004bffc`
- `0x18004c2d8`
- `0x18004c50c`
- `0x18004fa30`
- `0x18005a99c`
- `0x18007d51c`

## callees

- `0x18003d528`
- `0x180054fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d585`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d5a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d585`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003d5a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d56f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d56f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(__int64 a1, const WCHAR **a2)
{
  unsigned __int64 v3; // rbx
  const WCHAR *v4; // rsi
  unsigned int v5; // eax
  UINT32 v6; // edx
  HRESULT StringReference; // eax

  *(_QWORD *)(a1 + 24) = 0;
  v3 = -1;
  v4 = *a2;
  do
    ++v3;
  while ( v4[v3] );
  if ( v3 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18003D5AFLL);
  }
  v5 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v3);
  v6 = v5 - 1;
  if ( (unsigned int)v3 < v5 )
    v6 = v3;
  StringReference = WindowsCreateStringReference(v4, v6, (HSTRING_HEADER *)a1, (HSTRING *)(a1 + 24));
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x18003d528  push    rbx
0x18003d52a  push    rbp
0x18003d52b  push    rsi
0x18003d52c  push    rdi
0x18003d52d  push    r14
0x18003d52f  sub     rsp, 20h
0x18003d533  xor     ebp, ebp
0x18003d535  mov     rdi, rcx
0x18003d538  mov     [rcx+18h], rbp
0x18003d53c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d540  mov     rsi, [rdx]
0x18003d543  inc     rbx
0x18003d546  cmp     [rsi+rbx*2], bp
0x18003d54a  jnz     short loc_18003D543
0x18003d54c  mov     eax, 0FFFFFFFFh
0x18003d551  cmp     rbx, rax
0x18003d554  ja      short loc_18003D59A
0x18003d556  mov     ecx, ebx; unsigned int
0x18003d558  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003d55d  cmp     ebx, eax
0x18003d55f  lea     r9, [rdi+18h]; string
0x18003d563  mov     r8, rdi; hstringHeader
0x18003d566  mov     rcx, rsi; sourceString
0x18003d569  lea     edx, [rax-1]
0x18003d56c  cmovb   edx, ebx; length
0x18003d56f  call    cs:__imp_WindowsCreateStringReference
0x18003d575  test    eax, eax
0x18003d577  jns     short loc_18003D58C
0x18003d579  xor     r9d, r9d; lpArguments
0x18003d57c  xor     r8d, r8d; nNumberOfArguments
0x18003d57f  mov     ecx, eax; dwExceptionCode
0x18003d581  lea     edx, [r9+1]; dwExceptionFlags
0x18003d585  call    cs:__imp_RaiseException
0x18003d58b  int     3; Trap to Debugger
0x18003d58c  mov     rax, rdi
0x18003d58f  add     rsp, 20h
0x18003d593  pop     r14
0x18003d595  pop     rdi
0x18003d596  pop     rsi
0x18003d597  pop     rbp
0x18003d598  pop     rbx
0x18003d599  retn
0x18003d59a  xor     r9d, r9d; lpArguments
0x18003d59d  xor     r8d, r8d; nNumberOfArguments
0x18003d5a0  mov     ecx, 80070216h; dwExceptionCode
0x18003d5a5  lea     edx, [r9+1]; dwExceptionFlags
0x18003d5a9  call    cs:__imp_RaiseException
```

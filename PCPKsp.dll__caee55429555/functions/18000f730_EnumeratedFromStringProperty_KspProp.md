# EnumeratedFromStringProperty(KspProp)

- ea: `0x18000f730`
- end: `0x18000f851`
- name: `?EnumeratedFromStringProperty@@YAPEBGW4KspProp@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011c60`
- `0x180018e20`
- `0x18001d590`
- `0x1800528d0`

## callees

- `0x18000f730`
- `0x18000f858`
- `0x1800133c4`
- `0x180069088`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f820`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f83d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f820`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f83d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f755`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f755`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const wchar_t *__fastcall EnumeratedFromStringProperty(unsigned int a1)
{
  const char *v2; // r9
  int LastError; // edi
  __int64 *v4; // rcx
  __int64 *v5; // r8
  __int64 *v6; // rax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  WINBOOL fPending; // [rsp+58h] [rbp+10h] BYREF

  fPending = 0;
  if ( InitOnceBeginInitialize(&g_initOnceEnumToString, 0, &fPending, 0) )
  {
    if ( fPending )
    {
      v8 = lambda_78a0d25065c9a3e1bb832c6a29bdb43c_::operator()();
      LastError = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"wil",
          (const char *)(unsigned int)v8,
          v9);
        InitOnceComplete(&g_initOnceEnumToString, 4u, 0);
        goto LABEL_3;
      }
      InitOnceComplete(&g_initOnceEnumToString, 0, 0);
    }
    LastError = 0;
    goto LABEL_3;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v2);
LABEL_3:
  if ( LastError < 0 )
    return L"UNRECOGNIZED";
  v4 = *(__int64 **)(*(_QWORD *)qword_180109BD0 + 8LL);
  v5 = *(__int64 **)qword_180109BD0;
  if ( !*((_BYTE *)v4 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v4 + 8) >= a1 )
        v5 = v4;
      v6 = v4 + 2;
      if ( *((_DWORD *)v4 + 8) >= a1 )
        v6 = v4;
      v4 = (__int64 *)*v6;
    }
    while ( !*(_BYTE *)(*v6 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || v5 == *(__int64 **)qword_180109BD0 || a1 < *((_DWORD *)v5 + 8) )
    return L"UNRECOGNIZED";
  else
    return (const wchar_t *)v5[5];
}

```

## disassembly

```asm
0x18000f730  mov     [rsp+arg_0], rbx
0x18000f735  push    rdi
0x18000f736  sub     rsp, 40h
0x18000f73a  mov     ebx, ecx
0x18000f73c  mov     [rsp+48h+fPending], 0
0x18000f744  xor     r9d, r9d; lpContext
0x18000f747  lea     r8, [rsp+48h+fPending]; fPending
0x18000f74c  xor     edx, edx; dwFlags
0x18000f74e  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f755  call    cs:__imp_InitOnceBeginInitialize
0x18000f75c  nop     dword ptr [rax+rax+00h]
0x18000f761  test    eax, eax
0x18000f763  jnz     loc_18000F7E6
0x18000f769  mov     rcx, [rsp+48h]; this
0x18000f76e  lea     r8, aWil; "wil"
0x18000f775  mov     edx, 37Ah; void *
0x18000f77a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f77f  mov     edi, eax
0x18000f781  test    edi, edi
0x18000f783  js      short loc_18000F7C0
0x18000f785  mov     rax, cs:qword_180109BD0
0x18000f78c  mov     r9, [rax]
0x18000f78f  mov     rcx, [r9+8]
0x18000f793  xor     eax, eax
0x18000f795  mov     [rsp+48h+var_1C], eax
0x18000f799  mov     r8, r9
0x18000f79c  cmp     [rcx+19h], al
0x18000f79f  jnz     short loc_18000F7B9
0x18000f7a1  cmp     [rcx+20h], ebx
0x18000f7a4  cmovnb  r8, rcx
0x18000f7a8  lea     rax, [rcx+10h]
0x18000f7ac  cmovnb  rax, rcx
0x18000f7b0  mov     rcx, [rax]
0x18000f7b3  cmp     byte ptr [rcx+19h], 0
0x18000f7b7  jz      short loc_18000F7A1
0x18000f7b9  cmp     byte ptr [r8+19h], 0
0x18000f7be  jz      short loc_18000F7D9
0x18000f7c0  lea     rax, aUnrecognized; "UNRECOGNIZED"
0x18000f7c7  jmp     short loc_18000F7CD
0x18000f7c9  mov     rax, [r8+28h]
0x18000f7cd  mov     rbx, [rsp+48h+arg_0]
0x18000f7d2  add     rsp, 40h
0x18000f7d6  pop     rdi
0x18000f7d7  retn
0x18000f7d9  cmp     r8, r9
0x18000f7dc  jz      short loc_18000F7C0
0x18000f7de  cmp     ebx, [r8+20h]
0x18000f7e2  jb      short loc_18000F7C0
0x18000f7e4  jmp     short loc_18000F7C9
0x18000f7e6  cmp     [rsp+48h+fPending], 0
0x18000f7eb  jz      short loc_18000F849
0x18000f7ed  call    _lambda_78a0d25065c9a3e1bb832c6a29bdb43c___operator__
0x18000f7f2  mov     edi, eax
0x18000f7f4  test    eax, eax
0x18000f7f6  jns     short loc_18000F831
0x18000f7f8  mov     rcx, [rsp+48h]; this
0x18000f7fd  mov     r9d, eax; char *
0x18000f800  lea     r8, aWil; "wil"
0x18000f807  mov     edx, 37Fh; void *
0x18000f80c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f811  xor     r8d, r8d; lpContext
0x18000f814  mov     edx, 4; dwFlags
0x18000f819  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f820  call    cs:__imp_InitOnceComplete
0x18000f827  nop     dword ptr [rax+rax+00h]
0x18000f82c  jmp     loc_18000F781
0x18000f831  xor     r8d, r8d; lpContext
0x18000f834  xor     edx, edx; dwFlags
0x18000f836  lea     rcx, ?g_initOnceEnumToString@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000f83d  call    cs:__imp_InitOnceComplete
0x18000f844  nop     dword ptr [rax+rax+00h]
0x18000f849  xor     edi, edi
0x18000f84b  jmp     loc_18000F781
```

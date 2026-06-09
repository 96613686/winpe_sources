# EnumeratedFromStringProperty(ushort const *)

- ea: `0x18000f5f0`
- end: `0x18000f72a`
- name: `?EnumeratedFromStringProperty@@YA?AW4KspProp@@PEBG@Z`
- size: `314`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d110`
- `0x18001ffe0`
- `0x180024ef0`
- `0x180037b20`

## callees

- `0x18000f5f0`
- `0x18000f858`
- `0x1800133c4`
- `0x180066e9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f668`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f698`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f668`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f698`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f6fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f716`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f6fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f716`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f618`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f618`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumeratedFromStringProperty(__int64 a1)
{
  const char *v2; // r9
  int LastError; // ebx
  __int64 **v4; // rsi
  __int64 *v5; // rbx
  __int64 *v6; // rdi
  int v7; // eax
  __int64 *v8; // rcx
  int v10; // eax
  int v11; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  WINBOOL fPending; // [rsp+78h] [rbp+10h] BYREF

  fPending = 0;
  if ( InitOnceBeginInitialize(&g_initOnceStringToEnum, 0, &fPending, 0) )
  {
    if ( fPending )
    {
      v10 = lambda_77c84be3cd74da367aca49e190bf9e50_::operator()();
      LastError = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"wil",
          (const char *)(unsigned int)v10,
          v11);
        InitOnceComplete(&g_initOnceStringToEnum, 4u, 0);
        goto LABEL_3;
      }
      InitOnceComplete(&g_initOnceStringToEnum, 0, 0);
    }
    LastError = 0;
    goto LABEL_3;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v2);
LABEL_3:
  if ( LastError < 0 )
    return 0;
  v4 = (__int64 **)qword_180109BC8;
  v5 = *(__int64 **)qword_180109BC8;
  v6 = *(__int64 **)(*(_QWORD *)qword_180109BC8 + 8LL);
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      v7 = _o__wcsicmp(v6[4], a1);
      if ( v7 >= 0 )
        v5 = v6;
      v8 = v6 + 2;
      if ( v7 >= 0 )
        v8 = v6;
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || (int)_o__wcsicmp(a1, v5[4]) < 0 )
    v5 = *v4;
  if ( v5 == *(__int64 **)qword_180109BC8 )
    return 0;
  else
    return *((unsigned int *)v5 + 10);
}

```

## disassembly

```asm
0x18000f5f0  push    rbx
0x18000f5f2  push    rbp
0x18000f5f3  push    rsi
0x18000f5f4  push    rdi
0x18000f5f5  sub     rsp, 48h
0x18000f5f9  mov     rbp, rcx
0x18000f5fc  mov     [rsp+68h+fPending], 0
0x18000f604  xor     r9d, r9d; lpContext
0x18000f607  lea     r8, [rsp+68h+fPending]; fPending
0x18000f60c  xor     edx, edx; dwFlags
0x18000f60e  lea     rdi, ?g_initOnceStringToEnum@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE g_initOnceStringToEnum
0x18000f615  mov     rcx, rdi; lpInitOnce
0x18000f618  call    cs:__imp_InitOnceBeginInitialize
0x18000f61f  nop     dword ptr [rax+rax+00h]
0x18000f624  test    eax, eax
0x18000f626  jnz     loc_18000F6C8
0x18000f62c  mov     rcx, [rsp+68h]; this
0x18000f631  lea     r8, aWil; "wil"
0x18000f638  mov     edx, 37Ah; void *
0x18000f63d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f642  mov     ebx, eax
0x18000f644  test    ebx, ebx
0x18000f646  js      short loc_18000F6C4
0x18000f648  mov     rsi, cs:qword_180109BC8
0x18000f64f  mov     rbx, [rsi]
0x18000f652  mov     rdi, [rbx+8]
0x18000f656  xor     eax, eax
0x18000f658  mov     [rsp+68h+var_3C], eax
0x18000f65c  cmp     [rdi+19h], al
0x18000f65f  jnz     short loc_18000F68B
0x18000f661  mov     rdx, rbp
0x18000f664  mov     rcx, [rdi+20h]
0x18000f668  call    cs:__imp__o__wcsicmp
0x18000f66f  nop     dword ptr [rax+rax+00h]
0x18000f674  test    eax, eax
0x18000f676  cmovns  rbx, rdi
0x18000f67a  lea     rcx, [rdi+10h]
0x18000f67e  cmovns  rcx, rdi
0x18000f682  mov     rdi, [rcx]
0x18000f685  cmp     byte ptr [rdi+19h], 0
0x18000f689  jz      short loc_18000F661
0x18000f68b  cmp     byte ptr [rbx+19h], 0
0x18000f68f  jnz     short loc_18000F6A8
0x18000f691  mov     rdx, [rbx+20h]
0x18000f695  mov     rcx, rbp
0x18000f698  call    cs:__imp__o__wcsicmp
0x18000f69f  nop     dword ptr [rax+rax+00h]
0x18000f6a4  test    eax, eax
0x18000f6a6  jns     short loc_18000F6AB
0x18000f6a8  mov     rbx, [rsi]
0x18000f6ab  mov     rcx, cs:qword_180109BC8
0x18000f6b2  cmp     rbx, [rcx]
0x18000f6b5  jz      short loc_18000F6C4
0x18000f6b7  mov     eax, [rbx+28h]
0x18000f6ba  add     rsp, 48h
0x18000f6be  pop     rdi
0x18000f6bf  pop     rsi
0x18000f6c0  pop     rbp
0x18000f6c1  pop     rbx
0x18000f6c2  retn
0x18000f6c4  xor     eax, eax
0x18000f6c6  jmp     short loc_18000F6BA
0x18000f6c8  cmp     [rsp+68h+fPending], 0
0x18000f6cd  jz      short loc_18000F722
0x18000f6cf  call    _lambda_77c84be3cd74da367aca49e190bf9e50___operator__
0x18000f6d4  mov     ebx, eax
0x18000f6d6  test    eax, eax
0x18000f6d8  jns     short loc_18000F70E
0x18000f6da  mov     rcx, [rsp+68h]; this
0x18000f6df  mov     r9d, eax; char *
0x18000f6e2  lea     r8, aWil; "wil"
0x18000f6e9  mov     edx, 37Fh; void *
0x18000f6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6f3  xor     r8d, r8d; lpContext
0x18000f6f6  lea     edx, [r8+4]; dwFlags
0x18000f6fa  mov     rcx, rdi; lpInitOnce
0x18000f6fd  call    cs:__imp_InitOnceComplete
0x18000f704  nop     dword ptr [rax+rax+00h]
0x18000f709  jmp     loc_18000F644
0x18000f70e  xor     r8d, r8d; lpContext
0x18000f711  xor     edx, edx; dwFlags
0x18000f713  mov     rcx, rdi; lpInitOnce
0x18000f716  call    cs:__imp_InitOnceComplete
0x18000f71d  nop     dword ptr [rax+rax+00h]
0x18000f722  xor     ebx, ebx
0x18000f724  jmp     loc_18000F644
```

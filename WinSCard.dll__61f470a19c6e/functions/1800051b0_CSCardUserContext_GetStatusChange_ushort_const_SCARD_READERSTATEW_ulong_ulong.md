# CSCardUserContext::GetStatusChange(ushort const *,SCARD_READERSTATEW *,ulong,ulong)

- ea: `0x1800051b0`
- end: `0x1800052f9`
- name: `?GetStatusChange@CSCardUserContext@@QEAAXPEBGPEAUSCARD_READERSTATEW@@KK@Z`
- size: `329`
- prototype: `void(CSCardUserContext *__hidden this, const unsigned __int16 *, struct SCARD_READERSTATEW *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800046a0`
- `0x180005de0`

## callees

- `0x1800051b0`
- `0x180008f70`
- `0x180009c10`
- `0x18002ef20`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005272`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSCardUserContext::GetStatusChange(
        CSCardUserContext *this,
        const unsigned __int16 *a2,
        struct SCARD_READERSTATEW *a3,
        unsigned int a4,
        unsigned int a5)
{
  struct CSCardSubcontext *v8; // rdi
  char *v9; // rbx
  int v10; // ecx
  int v11; // ecx
  ulong v12; // ebx
  CSCardSubcontext *v13; // rdi
  CSCardSubcontext *v14; // rbx
  ulong pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  ulong v16; // [rsp+34h] [rbp-34h] BYREF
  ulong v17; // [rsp+38h] [rbp-30h] BYREF
  ulong v18; // [rsp+3Ch] [rbp-2Ch] BYREF
  CSCardSubcontext *v19; // [rsp+40h] [rbp-28h]
  char *v20; // [rsp+48h] [rbp-20h]

  v19 = 0;
  try
  {
    v8 = CSCardUserContext::AcquireSubcontext(this, 1);
    v19 = v8;
    if ( !v8 )
    {
      pExceptionObject = -2146435066;
      throw &pExceptionObject;
    }
    CSCardSubcontext::GetStatusChange(v8, a2, a3, a4, a5);
    v9 = (char *)v8 + 48;
    v20 = (char *)v8 + 48;
    (**((void (__fastcall ***)(__int64, _QWORD, _QWORD))v8 + 6))((__int64)v8 + 48, 0, 0);
    v10 = *((_DWORD *)v8 + 4);
    if ( v10 == 3 )
    {
      *((_DWORD *)v8 + 5) = 1;
    }
    else
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 1 )
        {
          v16 = -2146435071;
          throw &v16;
        }
        *((_DWORD *)v8 + 4) = 1;
        *((_DWORD *)v8 + 5) = 0;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))((__int64)v8 + 48);
    v20 = (char *)v8 + 48;
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v9)((__int64)v8 + 48, 0, 0);
    *((_DWORD *)v8 + 4) = *((_DWORD *)v8 + 5);
    *((_DWORD *)v8 + 5) = 0;
    if ( !SetEvent(*((HANDLE *)v8 + 3)) )
      GetLastError();
  }
  catch ( ulong v18 )
  {
    v12 = v18;
    v13 = v19;
    if ( v19 )
    {
      CSCardSubcontext::Deallocate(v19);
      CSCardSubcontext::ReleaseSubcontext(v13);
    }
    if ( v12 == -2146435070 )
    {
      if ( *((_DWORD *)this + 4) )
        v12 = -2146435054;
    }
    v17 = v12;
    throw &v17;
  }
  catch ( ... )
  {
    v14 = v19;
    if ( v19 )
    {
      CSCardSubcontext::Deallocate(v19);
      CSCardSubcontext::ReleaseSubcontext(v14);
    }
    throw;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_8], rbx
0x1800051b5  mov     [rsp+arg_10], rsi
0x1800051ba  mov     [rsp+arg_0], rcx
0x1800051bf  push    rdi
0x1800051c0  push    r14
0x1800051c2  push    r15
0x1800051c4  sub     rsp, 50h
0x1800051c8  mov     ebx, r9d
0x1800051cb  mov     rsi, r8
0x1800051ce  mov     r14, rdx
0x1800051d1  xor     r15d, r15d
0x1800051d4  mov     [rsp+68h+var_28], r15
0x1800051d9  mov     edx, 1; int
0x1800051de  call    ?AcquireSubcontext@CSCardUserContext@@QEAAPEAVCSCardSubcontext@@H@Z; CSCardUserContext::AcquireSubcontext(int)
0x1800051e3  mov     rdi, rax
0x1800051e6  mov     [rsp+68h+var_28], rax
0x1800051eb  test    rax, rax
0x1800051ee  jz      loc_1800052AA
0x1800051f4  mov     eax, [rsp+68h+arg_20]
0x1800051fb  mov     [rsp+68h+var_48], eax; unsigned int
0x1800051ff  mov     r9d, ebx; unsigned int
0x180005202  mov     r8, rsi; struct SCARD_READERSTATEW *
0x180005205  mov     rdx, r14; unsigned __int16 *
0x180005208  mov     rcx, rdi; this
0x18000520b  call    ?GetStatusChange@CSCardSubcontext@@QEAAXPEBGPEAUSCARD_READERSTATEW@@KK@Z; CSCardSubcontext::GetStatusChange(ushort const *,SCARD_READERSTATEW *,ulong,ulong)
0x180005210  lea     rbx, [rdi+30h]
0x180005214  mov     [rsp+68h+var_20], rbx
0x180005219  mov     rax, [rbx]
0x18000521c  xor     r8d, r8d
0x18000521f  xor     edx, edx
0x180005221  mov     rcx, rbx
0x180005224  mov     rax, [rax]
0x180005227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522c  nop
0x18000522d  mov     ecx, [rdi+10h]
0x180005230  cmp     ecx, 3
0x180005233  jnz     short loc_1800052A3
0x180005235  mov     dword ptr [rdi+14h], 1
0x18000523c  mov     rax, [rbx]
0x18000523f  mov     rcx, rbx
0x180005242  mov     rax, [rax+8]
0x180005246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524b  mov     [rsp+68h+var_20], rbx
0x180005250  mov     rax, [rbx]
0x180005253  xor     r8d, r8d
0x180005256  xor     edx, edx
0x180005258  mov     rcx, rbx
0x18000525b  mov     rax, [rax]
0x18000525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005263  nop
0x180005264  mov     eax, [rdi+14h]
0x180005267  mov     [rdi+10h], eax
0x18000526a  mov     [rdi+14h], r15d
0x18000526e  mov     rcx, [rdi+18h]; hEvent
0x180005272  call    cs:__imp_SetEvent
0x180005278  test    eax, eax
0x18000527a  jz      short loc_1800052EF
0x18000527c  mov     rax, [rbx]
0x18000527f  mov     rcx, rbx
0x180005282  mov     rax, [rax+8]
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  nop
0x18000528c  mov     rbx, [rsp+68h+arg_8]
0x180005291  mov     rsi, [rsp+68h+arg_10]
0x180005299  add     rsp, 50h
0x18000529d  pop     r15
0x18000529f  pop     r14
0x1800052a1  pop     rdi
0x1800052a2  retn
0x1800052a3  sub     ecx, 1
0x1800052a6  jnz     short loc_1800052C4
0x1800052a8  jmp     short loc_18000523C
0x1800052aa  mov     [rsp+68h+pExceptionObject], 80100006h
0x1800052b2  lea     rdx, _TI1K; pThrowInfo
0x1800052b9  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800052be  call    _CxxThrowException_0
0x1800052c4  cmp     ecx, 1
0x1800052c7  jz      short loc_1800052E2
0x1800052c9  mov     [rsp+68h+var_34], 80100001h
0x1800052d1  lea     rdx, _TI1K; pThrowInfo
0x1800052d8  lea     rcx, [rsp+68h+var_34]; pExceptionObject
0x1800052dd  call    _CxxThrowException_0
0x1800052e2  mov     dword ptr [rdi+10h], 1
0x1800052e9  mov     [rdi+14h], r15d
0x1800052ed  jmp     short loc_1800052A8
0x1800052ef  call    cs:__imp_GetLastError
0x1800052f5  jmp     short loc_18000527C
```

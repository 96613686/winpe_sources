# BstrWrite(IStream *,ushort *,tagSYSKIND)

- ea: `0x180096748`
- end: `0x1800968f6`
- name: `?BstrWrite@@YAJPEAUIStream@@PEAGW4tagSYSKIND@@@Z`
- size: `430`
- prototype: `int(struct IStream *, unsigned __int16 *, enum tagSYSKIND)`
- caller_count: `15`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18007f090`
- `0x180080160`
- `0x180080960`
- `0x180080c50`
- `0x180082b44`
- `0x180082d08`
- `0x180083524`
- `0x1800844b8`
- `0x180084964`
- `0x1800852f4`
- `0x180096a1c`
- `0x180096acc`
- `0x1800975dc`
- `0x18009781c`
- `0x180098304`

## callees

- `0x180027ed0`
- `0x18002e880`
- `0x18004d924`
- `0x18004dd00`
- `0x180096748`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800967ee`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180096877`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800967ee`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180096877`

## pseudocode

```c
__int64 __fastcall BstrWrite(struct IStream *a1, unsigned __int16 *a2, enum tagSYSKIND a3)
{
  __int64 result; // rax
  bool *v7; // rdx
  __int64 v8; // r8
  UINT v9; // r14d
  CHAR *lpMultiByteStr; // rax
  CHAR *v11; // rsi
  unsigned int v12; // ebx
  unsigned __int64 cbMultiByte[2]; // [rsp+40h] [rbp-10h] BYREF
  bool v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  LODWORD(cbMultiByte[0]) = SysStringByteLen(a2);
  if ( !LODWORD(cbMultiByte[0]) )
  {
    result = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64 *, __int64))(*(_QWORD *)a1 + 32LL))(
               a1,
               cbMultiByte,
               4);
    if ( (int)result <= -1 )
      return result;
    v7 = &v14;
    v8 = 1;
    v14 = a2 == 0;
    return (*(__int64 (__fastcall **)(struct IStream *, bool *, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v7, v8, 0);
  }
  if ( a3 )
  {
    result = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64 *, __int64))(*(_QWORD *)a1 + 32LL))(
               a1,
               cbMultiByte,
               4);
    if ( (int)result <= -1 )
      return result;
    v8 = LODWORD(cbMultiByte[0]);
    v7 = (bool *)a2;
    return (*(__int64 (__fastcall **)(struct IStream *, bool *, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v7, v8, 0);
  }
  v9 = SysStringLen(a2);
  LODWORD(cbMultiByte[0]) = WideCharToMultiByte(0, 0, a2, v9, 0, 0, 0, 0);
  if ( (unsigned int)(LODWORD(cbMultiByte[0]) + 1) < LODWORD(cbMultiByte[0])
    || (unsigned int)(LODWORD(cbMultiByte[0]) + 1) >= 0xFFFFFFE7
    || ((LODWORD(cbMultiByte[0]) + 26) & 0xFFFFFFF0) > 0xFFFF )
  {
    return 2147942414LL;
  }
  result = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64 *, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(
             a1,
             cbMultiByte,
             4,
             0);
  if ( (int)result <= -1 )
    return result;
  lpMultiByteStr = (CHAR *)operator new[](LODWORD(cbMultiByte[0]));
  v11 = lpMultiByteStr;
  if ( !lpMultiByteStr )
    return 2147942414LL;
  WideCharToMultiByte(0, 0, a2, v9, lpMultiByteStr, cbMultiByte[0], 0, 0);
  v12 = (*(__int64 (__fastcall **)(struct IStream *, CHAR *, _QWORD, _QWORD))(*(_QWORD *)a1 + 32LL))(
          a1,
          v11,
          LODWORD(cbMultiByte[0]),
          0);
  operator delete(v11);
  return v12;
}

```

## disassembly

```asm
0x180096748  mov     [rsp-18h+arg_0], rbx
0x18009674d  mov     [rsp-18h+arg_8], rsi
0x180096752  push    rbp
0x180096753  push    rdi
0x180096754  push    r14
0x180096756  mov     rbp, rsp
0x180096759  sub     rsp, 50h
0x18009675d  mov     rbx, rcx
0x180096760  mov     [rbp+arg_18], 0
0x180096764  mov     rcx, rdx; bstr
0x180096767  mov     esi, r8d
0x18009676a  mov     rdi, rdx
0x18009676d  call    SysStringByteLen
0x180096772  mov     dword ptr [rbp+var_10], eax
0x180096775  test    eax, eax
0x180096777  jnz     short loc_1800967B2
0x180096779  mov     rax, [rbx]
0x18009677c  lea     rdx, [rbp+var_10]
0x180096780  xor     r9d, r9d
0x180096783  mov     rcx, rbx
0x180096786  mov     rax, [rax+20h]
0x18009678a  lea     r8d, [r9+4]
0x18009678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096793  cmp     eax, 0FFFFFFFFh
0x180096796  jle     loc_1800968E3
0x18009679c  test    rdi, rdi
0x18009679f  lea     rdx, [rbp+arg_18]
0x1800967a3  mov     r8d, 1
0x1800967a9  setz    [rbp+arg_18]
0x1800967ad  jmp     loc_1800968D1
0x1800967b2  test    esi, esi
0x1800967b4  jnz     loc_1800968AB
0x1800967ba  mov     rcx, rdi; pbstr
0x1800967bd  call    SysStringLen
0x1800967c2  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800967cb  mov     r9d, eax; cchWideChar
0x1800967ce  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x1800967d7  mov     r8, rdi; lpWideCharStr
0x1800967da  mov     [rsp+50h+cbMultiByte], esi; cbMultiByte
0x1800967de  xor     edx, edx; dwFlags
0x1800967e0  xor     ecx, ecx; CodePage
0x1800967e2  mov     [rsp+50h+lpMultiByteStr], 0; lpMultiByteStr
0x1800967eb  mov     r14d, eax
0x1800967ee  call    cs:__imp_WideCharToMultiByte
0x1800967f4  mov     dword ptr [rbp+var_10], eax
0x1800967f7  lea     ecx, [rax+1]
0x1800967fa  cmp     ecx, eax
0x1800967fc  jbe     loc_1800968A4
0x180096802  lea     eax, [rcx+19h]
0x180096805  cmp     eax, 19h
0x180096808  jb      loc_1800968A4
0x18009680e  and     eax, 0FFFFFFF0h
0x180096811  cmp     eax, 0FFFFh
0x180096816  ja      loc_1800968A4
0x18009681c  mov     rax, [rbx]
0x18009681f  lea     r8d, [rsi+4]
0x180096823  xor     r9d, r9d
0x180096826  lea     rdx, [rbp+var_10]
0x18009682a  mov     rcx, rbx
0x18009682d  mov     rax, [rax+20h]
0x180096831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096836  cmp     eax, 0FFFFFFFFh
0x180096839  jle     loc_1800968E3
0x18009683f  mov     ecx, dword ptr [rbp+var_10]; unsigned __int64
0x180096842  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180096847  mov     rsi, rax
0x18009684a  test    rax, rax
0x18009684d  jz      short loc_1800968A4
0x18009684f  mov     ecx, dword ptr [rbp+var_10]
0x180096852  mov     r9d, r14d; cchWideChar
0x180096855  mov     [rsp+50h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18009685e  mov     r8, rdi; lpWideCharStr
0x180096861  mov     [rsp+50h+lpDefaultChar], 0; lpDefaultChar
0x18009686a  xor     edx, edx; dwFlags
0x18009686c  mov     [rsp+50h+cbMultiByte], ecx; cbMultiByte
0x180096870  xor     ecx, ecx; CodePage
0x180096872  mov     [rsp+50h+lpMultiByteStr], rax; lpMultiByteStr
0x180096877  call    cs:__imp_WideCharToMultiByte
0x18009687d  mov     rcx, [rbx]
0x180096880  xor     r9d, r9d
0x180096883  mov     r8d, dword ptr [rbp+var_10]
0x180096887  mov     rdx, rsi
0x18009688a  mov     rax, [rcx+20h]
0x18009688e  mov     rcx, rbx
0x180096891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096896  mov     rcx, rsi; void *
0x180096899  mov     ebx, eax
0x18009689b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800968a0  mov     eax, ebx
0x1800968a2  jmp     short loc_1800968E3
0x1800968a4  mov     eax, 8007000Eh
0x1800968a9  jmp     short loc_1800968E3
0x1800968ab  mov     rax, [rbx]
0x1800968ae  lea     rdx, [rbp+var_10]
0x1800968b2  xor     r9d, r9d
0x1800968b5  mov     rcx, rbx
0x1800968b8  mov     rax, [rax+20h]
0x1800968bc  lea     r8d, [r9+4]
0x1800968c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800968c5  cmp     eax, 0FFFFFFFFh
0x1800968c8  jle     short loc_1800968E3
0x1800968ca  mov     r8d, dword ptr [rbp+var_10]
0x1800968ce  mov     rdx, rdi
0x1800968d1  mov     rax, [rbx]
0x1800968d4  xor     r9d, r9d
0x1800968d7  mov     rcx, rbx
0x1800968da  mov     rax, [rax+20h]
0x1800968de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800968e3  mov     rbx, [rsp+50h+arg_0]
0x1800968e8  mov     rsi, [rsp+50h+arg_8]
0x1800968ed  add     rsp, 50h
0x1800968f1  pop     r14
0x1800968f3  pop     rdi
0x1800968f4  pop     rbp
0x1800968f5  retn
```

# RegTable::GetRowInternal(ushort const *,RegRow * *)

- ea: `0x18000d7a0`
- end: `0x18000db1c`
- name: `?GetRowInternal@RegTable@@QEAAJPEBGPEAPEAVRegRow@@@Z`
- size: `892`
- prototype: `int(RegTable *__hidden this, const unsigned __int16 *, struct RegRow **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d770`
- `0x18003a1f0`

## callees

- `0x18000b028`
- `0x18000b568`
- `0x18000d7a0`
- `0x18000db24`
- `0x18000db98`
- `0x180012654`
- `0x180024a94`
- `0x1800434ba`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dae1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dae1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043aac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d89b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d89b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d93e`

## string_xrefs

- `0x18000db0b`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
__int64 __fastcall RegTable::GetRowInternal(RegTable *this, const unsigned __int16 *a2, struct RegRow **a3)
{
  int v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  struct RegRow *v7; // r13
  _QWORD *v8; // r10
  const unsigned __int16 *v9; // rax
  unsigned int v10; // r8d
  int v11; // ecx
  OLECHAR *v12; // rbx
  __int64 v13; // rsi
  _DWORD *v14; // rax
  const OLECHAR *v15; // r13
  OLECHAR *v16; // rcx
  _QWORD *i; // r9
  char *v18; // rax
  char *v19; // r8
  int v20; // ecx
  int v21; // edx
  CString *v22; // rax
  struct RegRow *v24; // [rsp+20h] [rbp-78h] BYREF
  int v25; // [rsp+28h] [rbp-70h]
  const OLECHAR *v26; // [rsp+30h] [rbp-68h] BYREF
  int v27; // [rsp+38h] [rbp-60h]
  int v28; // [rsp+3Ch] [rbp-5Ch]
  int v29; // [rsp+40h] [rbp-58h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-50h]
  const unsigned __int16 *v31; // [rsp+50h] [rbp-48h]
  char *v32; // [rsp+58h] [rbp-40h]
  __int64 v35; // [rsp+B8h] [rbp+20h] BYREF

  v5 = 0;
  *a3 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 616);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 616);
  if ( !*((_DWORD *)this + 164) )
    InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
  EnterCriticalSection(v6);
  v7 = 0;
  v24 = 0;
  v8 = (_QWORD *)((char *)this + 576);
  v32 = (char *)this + 576;
  v9 = a2;
  v31 = a2;
  v10 = 0;
  while ( 1 )
  {
    v11 = *v9;
    if ( !(_WORD)v11 )
      break;
    v10 = v11 + 33 * v10;
    v31 = ++v9;
  }
  if ( *v8 )
  {
    for ( i = *(_QWORD **)(*v8 + 8LL * (v10 % *((_DWORD *)this + 146))); i; i = (_QWORD *)*i )
    {
      v18 = (char *)i[2];
      if ( a2 )
      {
        v19 = (char *)((char *)a2 - v18);
        do
        {
          v20 = *(unsigned __int16 *)&v19[(_QWORD)v18];
          v21 = *(unsigned __int16 *)v18 - v20;
          if ( v21 )
            break;
          v18 += 2;
        }
        while ( v20 );
        if ( !v21 )
        {
LABEL_35:
          v7 = (struct RegRow *)i[3];
          v24 = v7;
          if ( (*(unsigned int (__fastcall **)(struct RegRow *))(*(_QWORD *)v7 + 136LL))(v7) )
          {
            (*(void (__fastcall **)(struct RegRow *))(*(_QWORD *)v7 + 8LL))(v7);
          }
          else
          {
            v7 = 0;
            v24 = 0;
            v5 = -2147024894;
            v25 = -2147024894;
          }
          goto LABEL_49;
        }
      }
      else if ( !*((_DWORD *)v18 - 2) )
      {
        goto LABEL_35;
      }
    }
  }
  v12 = (OLECHAR *)&dword_180053104;
  v26 = &dword_180053104;
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    v35 = v13;
  }
  else
  {
    LODWORD(v13) = 0;
  }
  v5 = 0;
  v29 = 0;
  if ( (_DWORD)v13 )
  {
    LODWORD(v35) = 0;
    v28 = 0;
    if ( (int)v13 <= 0 )
    {
      v15 = &dword_180053104;
    }
    else
    {
      LODWORD(v35) = 0;
      v27 = 0;
      v14 = CoTaskMemAlloc(2LL * (int)v13 + 14);
      if ( v14 )
      {
        *v14 = 1;
        *((_WORD *)v14 + (int)v13 + 6) = 0;
        v14[1] = v13;
        v14[2] = v13;
        v12 = (OLECHAR *)(v14 + 3);
        v26 = (const OLECHAR *)(v14 + 3);
        v5 = v35;
      }
      else
      {
        v5 = -2147024882;
        LODWORD(v35) = -2147024882;
        v27 = -2147024882;
      }
      v15 = v12;
      v28 = v5;
      if ( v5 >= 0 )
        CString::Release((struct CStringData *)&qword_1800530F8);
    }
    v29 = v5;
    if ( v5 >= 0 )
    {
      memcpy_0(v12, a2, 2LL * (int)v13);
      *((_DWORD *)v15 - 2) = v13;
      v15[(int)v13] = 0;
      v5 = v35;
    }
    v7 = v24;
  }
  else
  {
    CString::Release((CString *)&v26);
    v12 = (OLECHAR *)v26;
  }
  v25 = v5;
  if ( v5 >= 0 )
  {
    v5 = RegRow::CreateExisting(this, a2, &v24);
    v25 = v5;
    if ( v5 < 0 )
    {
      v7 = v24;
    }
    else
    {
      v22 = CString::CString((CString *)&v35, (const struct CString *)&v26);
      v7 = v24;
      v5 = CMap<CString,unsigned short const *,RegRow *,RegRow *>::SetAtWithActualKeyType(v32, v22, v24);
      v25 = v5;
      if ( v5 < 0 )
      {
        if ( v7 )
          (*(void (__fastcall **)(struct RegRow *, __int64))(*(_QWORD *)v7 + 152LL))(v7, 1);
        v7 = 0;
        v24 = 0;
      }
      else
      {
        (*(void (__fastcall **)(struct RegRow *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
  }
  v16 = v12 - 6;
  if ( v12 - 6 != (OLECHAR *)&qword_1800530F8
    && _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
  {
    CoTaskMemFree(v16);
  }
  v6 = lpCriticalSection;
LABEL_49:
  *a3 = v7;
  LeaveCriticalSection(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d7a0  mov     [rsp+arg_10], r8
0x18000d7a5  mov     [rsp+arg_0], rcx
0x18000d7aa  push    rbx
0x18000d7ab  push    rsi
0x18000d7ac  push    rdi
0x18000d7ad  push    r12
0x18000d7af  push    r13
0x18000d7b1  push    r14
0x18000d7b3  push    r15
0x18000d7b5  sub     rsp, 60h
0x18000d7b9  mov     rax, r8
0x18000d7bc  mov     r12, rdx
0x18000d7bf  mov     rsi, rcx
0x18000d7c2  xor     edi, edi
0x18000d7c4  mov     [r8], rdi
0x18000d7c7  lea     rbx, [rcx+268h]
0x18000d7ce  mov     [rsp+98h+lpCriticalSection], rbx
0x18000d7d3  cmp     [rbx+28h], edi
0x18000d7d6  jz      loc_18000DAF9
0x18000d7dc  mov     rcx, rbx; lpCriticalSection
0x18000d7df  call    cs:__imp_EnterCriticalSection
0x18000d7e5  nop
0x18000d7e6  xor     r13d, r13d
0x18000d7e9  mov     [rsp+98h+var_78], r13
0x18000d7ee  lea     r10, [rsi+240h]
0x18000d7f5  mov     [rsp+98h+var_40], r10
0x18000d7fa  mov     rax, r12
0x18000d7fd  mov     [rsp+98h+var_48], rax
0x18000d802  xor     r8d, r8d
0x18000d805  movzx   ecx, word ptr [rax]
0x18000d808  test    cx, cx
0x18000d80b  jz      short loc_18000D81F
0x18000d80d  imul    r8d, 21h ; '!'
0x18000d811  add     r8d, ecx
0x18000d814  add     rax, 2
0x18000d818  mov     [rsp+98h+var_48], rax
0x18000d81d  jmp     short loc_18000D805
0x18000d81f  mov     r9, [r10]
0x18000d822  test    r9, r9
0x18000d825  jnz     loc_18000D94E
0x18000d82b  lea     rbx, dword_180053104
0x18000d832  mov     [rsp+98h+var_68], rbx
0x18000d837  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000d83e  test    r12, r12
0x18000d841  jz      loc_18000D9AC
0x18000d847  mov     rsi, r14
0x18000d84a  nop     word ptr [rax+rax+00h]
0x18000d850  inc     rsi
0x18000d853  cmp     [r12+rsi*2], r13w
0x18000d858  jnz     short loc_18000D850
0x18000d85a  mov     [rsp+98h+arg_18], rsi
0x18000d862  xor     edi, edi
0x18000d864  mov     [rsp+98h+var_58], edi
0x18000d868  test    esi, esi
0x18000d86a  jz      loc_18000DA1F
0x18000d870  mov     dword ptr [rsp+98h+arg_18], edi
0x18000d877  mov     [rsp+98h+var_5C], edi
0x18000d87b  test    esi, esi
0x18000d87d  jle     loc_18000D99D
0x18000d883  xor     eax, eax
0x18000d885  mov     dword ptr [rsp+98h+arg_18], eax
0x18000d88c  mov     [rsp+98h+var_60], eax
0x18000d890  movsxd  rdi, esi
0x18000d893  lea     rcx, ds:0Eh[rdi*2]; cb
0x18000d89b  call    cs:__imp_CoTaskMemAlloc
0x18000d8a1  mov     rcx, rax
0x18000d8a4  test    rax, rax
0x18000d8a7  jz      loc_18000D9FE
0x18000d8ad  mov     dword ptr [rax], 1
0x18000d8b3  xor     eax, eax
0x18000d8b5  mov     [rcx+rdi*2+0Ch], ax
0x18000d8ba  mov     [rcx+4], esi
0x18000d8bd  mov     [rcx+8], esi
0x18000d8c0  lea     rbx, [rcx+0Ch]
0x18000d8c4  mov     [rsp+98h+var_68], rbx
0x18000d8c9  mov     edi, dword ptr [rsp+98h+arg_18]
0x18000d8d0  mov     r13, rbx
0x18000d8d3  mov     [rsp+98h+var_5C], edi
0x18000d8d7  lea     r15, qword_1800530F8
0x18000d8de  test    edi, edi
0x18000d8e0  js      short loc_18000D8EA
0x18000d8e2  mov     rcx, r15; struct CStringData *
0x18000d8e5  call    ?Release@CString@@KAXPEAUCStringData@@@Z; CString::Release(CStringData *)
0x18000d8ea  mov     [rsp+98h+var_58], edi
0x18000d8ee  test    edi, edi
0x18000d8f0  js      short loc_18000D919
0x18000d8f2  movsxd  rax, esi
0x18000d8f5  lea     rdi, [rax+rax]
0x18000d8f9  mov     r8, rdi; Size
0x18000d8fc  mov     rdx, r12; Src
0x18000d8ff  mov     rcx, rbx; void *
0x18000d902  call    memcpy_0
0x18000d907  mov     [r13-8], esi
0x18000d90b  xor     eax, eax
0x18000d90d  mov     [rdi+r13], ax
0x18000d912  mov     edi, dword ptr [rsp+98h+arg_18]
0x18000d919  mov     r13, [rsp+98h+var_78]
0x18000d91e  mov     [rsp+98h+var_70], edi
0x18000d922  test    edi, edi
0x18000d924  jns     loc_18000DA3A
0x18000d92a  lea     rcx, [rbx-0Ch]; pv
0x18000d92e  cmp     rcx, r15
0x18000d931  jz      short loc_18000D944
0x18000d933  lock xadd [rcx], r14d
0x18000d938  cmp     r14d, 1
0x18000d93c  jnz     short loc_18000D944
0x18000d93e  call    cs:__imp_CoTaskMemFree
0x18000d944  mov     rbx, [rsp+98h+lpCriticalSection]
0x18000d949  jmp     loc_18000DAD3
0x18000d94e  xor     edx, edx
0x18000d950  mov     eax, r8d
0x18000d953  div     dword ptr [r10+8]
0x18000d957  mov     r9, [r9+rdx*8]
0x18000d95b  test    r9, r9
0x18000d95e  jz      loc_18000D82B
0x18000d964  mov     rax, [r9+10h]
0x18000d968  test    r12, r12
0x18000d96b  jz      loc_18000DA13
0x18000d971  mov     r8, r12
0x18000d974  sub     r8, rax
0x18000d977  nop     word ptr [rax+rax+00000000h]
0x18000d980  movzx   edx, word ptr [rax]
0x18000d983  movzx   ecx, word ptr [rax+r8]
0x18000d988  sub     edx, ecx
0x18000d98a  jnz     short loc_18000D994
0x18000d98c  add     rax, 2
0x18000d990  test    ecx, ecx
0x18000d992  jnz     short loc_18000D980
0x18000d994  test    edx, edx
0x18000d996  jz      short loc_18000D9B3
0x18000d998  mov     r9, [r9]
0x18000d99b  jmp     short loc_18000D95B
0x18000d99d  mov     r13, rbx
0x18000d9a0  lea     r15, qword_1800530F8
0x18000d9a7  jmp     loc_18000D8EA
0x18000d9ac  xor     esi, esi
0x18000d9ae  jmp     loc_18000D862
0x18000d9b3  mov     r13, [r9+18h]
0x18000d9b7  mov     [rsp+98h+var_78], r13
0x18000d9bc  mov     rax, [r13+0]
0x18000d9c0  mov     rcx, r13
0x18000d9c3  mov     rax, [rax+88h]
0x18000d9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9cf  test    eax, eax
0x18000d9d1  jz      short loc_18000D9E8
0x18000d9d3  mov     rax, [r13+0]
0x18000d9d7  mov     rcx, r13
0x18000d9da  mov     rax, [rax+8]
0x18000d9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9e3  jmp     loc_18000DAD3
0x18000d9e8  xor     r13d, r13d
0x18000d9eb  mov     [rsp+98h+var_78], r13
0x18000d9f0  mov     edi, 80070002h
0x18000d9f5  mov     [rsp+98h+var_70], edi
0x18000d9f9  jmp     loc_18000DAD3
0x18000d9fe  mov     edi, 8007000Eh
0x18000da03  mov     dword ptr [rsp+98h+arg_18], edi
0x18000da0a  mov     [rsp+98h+var_60], edi
0x18000da0e  jmp     loc_18000D8D0
0x18000da13  cmp     [rax-8], r13d
0x18000da17  jnz     loc_18000D998
0x18000da1d  jmp     short loc_18000D9B3
0x18000da1f  lea     rcx, [rsp+98h+var_68]; this
0x18000da24  call    ?Release@CString@@IEAAXXZ; CString::Release(void)
0x18000da29  lea     r15, qword_1800530F8
0x18000da30  mov     rbx, [rsp+98h+var_68]
0x18000da35  jmp     loc_18000D91E
0x18000da3a  lea     r8, [rsp+98h+var_78]; struct RegRow **
0x18000da3f  mov     rdx, r12; unsigned __int16 *
0x18000da42  mov     rcx, [rsp+98h+arg_0]; struct RegTable *
0x18000da4a  call    ?CreateExisting@RegRow@@SAJPEAVRegTable@@PEBGAEAPEAV1@@Z; RegRow::CreateExisting(RegTable *,ushort const *,RegRow * &)
0x18000da4f  mov     edi, eax
0x18000da51  mov     [rsp+98h+var_70], eax
0x18000da55  test    eax, eax
0x18000da57  js      short loc_18000DAC9
0x18000da59  lea     rdx, [rsp+98h+var_68]; struct CString *
0x18000da5e  lea     rcx, [rsp+98h+arg_18]; this
0x18000da66  call    ??0CString@@QEAA@AEBV0@@Z; CString::CString(CString const &)
0x18000da6b  mov     r13, [rsp+98h+var_78]
0x18000da70  mov     r8, r13
0x18000da73  mov     rdx, rax
0x18000da76  mov     rcx, [rsp+98h+var_40]
0x18000da7b  call    ?SetAtWithActualKeyType@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@QEAAJVCString@@PEAVRegRow@@@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::SetAtWithActualKeyType(CString,RegRow *)
0x18000da80  mov     edi, eax
0x18000da82  mov     [rsp+98h+var_70], eax
0x18000da86  test    eax, eax
0x18000da88  js      short loc_18000DA9F
0x18000da8a  mov     rax, [r13+0]
0x18000da8e  mov     rcx, r13
0x18000da91  mov     rax, [rax+8]
0x18000da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da9a  jmp     loc_18000D92A
0x18000da9f  test    r13, r13
0x18000daa2  jz      short loc_18000DABC
0x18000daa4  mov     rax, [r13+0]
0x18000daa8  mov     edx, 1
0x18000daad  mov     rcx, r13
0x18000dab0  mov     rax, [rax+98h]
0x18000dab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dabc  xor     r13d, r13d
0x18000dabf  mov     [rsp+98h+var_78], r13
0x18000dac4  jmp     loc_18000D92A
0x18000dac9  mov     r13, [rsp+98h+var_78]
0x18000dace  jmp     loc_18000D92A
0x18000dad3  mov     rax, [rsp+98h+arg_10]
0x18000dadb  mov     [rax], r13
0x18000dade  mov     rcx, rbx; lpCriticalSection
0x18000dae1  call    cs:__imp_LeaveCriticalSection
0x18000dae7  mov     eax, edi
0x18000dae9  add     rsp, 60h
0x18000daed  pop     r15
0x18000daef  pop     r14
0x18000daf1  pop     r13
0x18000daf3  pop     r12
0x18000daf5  pop     rdi
0x18000daf6  pop     rsi
0x18000daf7  pop     rbx
0x18000daf8  retn
0x18000daf9  mov     r8d, 10h; unsigned __int16
0x18000daff  lea     r9, aMFinitialized; "m_fInitialized"
0x18000db06  mov     edx, 12Eh; unsigned int
0x18000db0b  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x18000db12  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000db17  jmp     loc_18000D7DC
0x180043a90  push    rbp
0x180043a92  sub     rsp, 20h
0x180043a96  mov     rbp, rdx
0x180043a99  mov     rcx, [rbp+0A0h]
0x180043aa0  add     rcx, 268h
0x180043aa7  add     rsp, 20h
0x180043aab  pop     rbp
0x180043aac  jmp     cs:__imp_LeaveCriticalSection
```

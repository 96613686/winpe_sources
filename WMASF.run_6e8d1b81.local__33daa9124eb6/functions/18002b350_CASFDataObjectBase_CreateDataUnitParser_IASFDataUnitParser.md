# CASFDataObjectBase::CreateDataUnitParser(IASFDataUnitParser * *)

- ea: `0x18002b350`
- end: `0x18002b4b2`
- name: `?CreateDataUnitParser@CASFDataObjectBase@@UEAAJPEAPEAUIASFDataUnitParser@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CASFDataObjectBase *__hidden this, struct IASFDataUnitParser **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001174`
- `0x1800015d0`
- `0x18000372c`
- `0x18002b350`
- `0x18002b4dc`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFDataObjectBase::CreateDataUnitParser(CASFDataObjectBase *this, struct IASFDataUnitParser **a2)
{
  CASFDataUnitParserBase *v5; // rax
  CASFDataUnitParserBase *v6; // rsi
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 3222079478LL;
  *a2 = 0;
  v10 = 0;
  v5 = (CASFDataUnitParserBase *)operator new(0x768u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_11;
  CASFDataUnitParserBase::CASFDataUnitParserBase(v5);
  *((_QWORD *)v6 + 2) = 0;
  *(_QWORD *)v6 = &CASFDataUnitParser::`vftable'{for `IASFDataUnitParser'};
  *((_QWORD *)v6 + 1) = &CASFDataUnitParser::`vftable'{for `IASFDataUnitParserPriv'};
  *((_DWORD *)v6 + 472) = 1;
  v7 = ((__int64 (__fastcall *)(CASFDataUnitParserBase *, GUID *, struct IASFDataUnitParser **))CASFDataUnitParser::`vftable'{for `IASFDataUnitParser'})(
         v6,
         &IID_IASFDataUnitParser,
         a2);
  (*(void (__fastcall **)(CASFDataUnitParserBase *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 < 0 )
    goto LABEL_12;
  v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(*a2, &IID_IASFDataUnitParserPriv, &v10);
  if ( v7 < 0 )
    goto LABEL_12;
  v8 = CTSparseBlock<unsigned long,IASFDataUnitParserPriv *,20,0>::SetValue(
         (char *)this + 80,
         *((unsigned int *)this + 74),
         v10);
  v9 = v10;
  if ( v8 < 0 )
  {
    if ( v10 )
    {
      (*(void (**)(void))(*(_QWORD *)v10 + 16LL))();
      v10 = 0;
    }
LABEL_11:
    v7 = -2147024882;
    goto LABEL_12;
  }
  ++*((_DWORD *)this + 74);
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, *((_QWORD *)this + 5));
  if ( v7 < 0 )
  {
LABEL_12:
    if ( *a2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
      *a2 = 0;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b350  mov     [rsp+arg_10], rbx
0x18002b355  push    rbp
0x18002b356  push    rsi
0x18002b357  push    rdi
0x18002b358  sub     rsp, 30h
0x18002b35c  mov     rax, cs:__security_cookie
0x18002b363  xor     rax, rsp
0x18002b366  mov     [rsp+48h+var_20], rax
0x18002b36b  cmp     qword ptr [rcx+28h], 0
0x18002b370  mov     rdi, rdx
0x18002b373  mov     rbp, rcx
0x18002b376  jnz     short loc_18002B382
0x18002b378  mov     eax, 0C00D07F6h
0x18002b37d  jmp     loc_18002B498
0x18002b382  mov     ecx, 768h; Size
0x18002b387  mov     qword ptr [rdx], 0
0x18002b38e  mov     [rsp+48h+var_28], 0
0x18002b397  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b39c  mov     rsi, rax
0x18002b39f  test    rax, rax
0x18002b3a2  jz      loc_18002B476
0x18002b3a8  mov     rcx, rax; this
0x18002b3ab  call    ??0CASFDataUnitParserBase@@QEAA@XZ; CASFDataUnitParserBase::CASFDataUnitParserBase(void)
0x18002b3b0  lea     r9, ??_7CASFDataUnitParser@@6BIASFDataUnitParser@@@; const CASFDataUnitParser::`vftable'{for `IASFDataUnitParser'}
0x18002b3b7  mov     qword ptr [rsi+10h], 0
0x18002b3bf  lea     rax, ??_7CASFDataUnitParser@@6BIASFDataUnitParserPriv@@@; const CASFDataUnitParser::`vftable'{for `IASFDataUnitParserPriv'}
0x18002b3c6  mov     [rsi], r9
0x18002b3c9  mov     [rsi+8], rax
0x18002b3cd  lea     rdx, IID_IASFDataUnitParser
0x18002b3d4  mov     rax, [r9]
0x18002b3d7  mov     r8, rdi
0x18002b3da  mov     rcx, rsi
0x18002b3dd  mov     dword ptr [rsi+760h], 1
0x18002b3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ec  mov     rcx, [rsi]
0x18002b3ef  mov     ebx, eax
0x18002b3f1  mov     rax, [rcx+10h]
0x18002b3f5  mov     rcx, rsi
0x18002b3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3fd  test    ebx, ebx
0x18002b3ff  js      short loc_18002B47B
0x18002b401  mov     rcx, [rdi]
0x18002b404  lea     r8, [rsp+48h+var_28]
0x18002b409  lea     rdx, IID_IASFDataUnitParserPriv
0x18002b410  mov     rax, [rcx]
0x18002b413  mov     rax, [rax]
0x18002b416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b41b  mov     ebx, eax
0x18002b41d  test    eax, eax
0x18002b41f  js      short loc_18002B47B
0x18002b421  mov     r8, [rsp+48h+var_28]
0x18002b426  lea     rcx, [rbp+50h]
0x18002b42a  mov     edx, [rbp+128h]
0x18002b430  call    ?SetValue@?$CTSparseBlock@KPEAUIASFDataUnitParserPriv@@$0BE@$0A@@@QEAAJKPEAUIASFDataUnitParserPriv@@@Z; CTSparseBlock<ulong,IASFDataUnitParserPriv *,20,0>::SetValue(ulong,IASFDataUnitParserPriv *)
0x18002b435  mov     rcx, [rsp+48h+var_28]
0x18002b43a  test    eax, eax
0x18002b43c  js      short loc_18002B45C
0x18002b43e  inc     dword ptr [rbp+128h]
0x18002b444  mov     rax, [rcx]
0x18002b447  mov     rdx, [rbp+28h]
0x18002b44b  mov     rax, [rax+18h]
0x18002b44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b454  mov     ebx, eax
0x18002b456  test    eax, eax
0x18002b458  jns     short loc_18002B496
0x18002b45a  jmp     short loc_18002B47B
0x18002b45c  test    rcx, rcx
0x18002b45f  jz      short loc_18002B476
0x18002b461  mov     rax, [rcx]
0x18002b464  mov     rax, [rax+10h]
0x18002b468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b46d  mov     [rsp+48h+var_28], 0
0x18002b476  mov     ebx, 8007000Eh
0x18002b47b  mov     rcx, [rdi]
0x18002b47e  test    rcx, rcx
0x18002b481  jz      short loc_18002B496
0x18002b483  mov     rax, [rcx]
0x18002b486  mov     rax, [rax+10h]
0x18002b48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b48f  mov     qword ptr [rdi], 0
0x18002b496  mov     eax, ebx
0x18002b498  mov     rcx, [rsp+48h+var_20]
0x18002b49d  xor     rcx, rsp; StackCookie
0x18002b4a0  call    __security_check_cookie
0x18002b4a5  mov     rbx, [rsp+48h+arg_10]
0x18002b4aa  add     rsp, 30h
0x18002b4ae  pop     rdi
0x18002b4af  pop     rsi
0x18002b4b0  pop     rbp
0x18002b4b1  retn
```

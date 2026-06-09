# CASFDataObjectv1::CreateDataUnitParser(IASFDataUnitParser * *)

- ea: `0x180017550`
- end: `0x18001769b`
- name: `?CreateDataUnitParser@CASFDataObjectv1@@UEAAJPEAPEAUIASFDataUnitParser@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(CASFDataObjectv1 *__hidden this, struct IASFDataUnitParser **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001174`
- `0x1800015d0`
- `0x18000372c`
- `0x180017550`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFDataObjectv1::CreateDataUnitParser(CASFDataObjectv1 *this, struct IASFDataUnitParser **a2)
{
  CASFDataUnitParserBase *v5; // rax
  CASFDataUnitParserBase *v6; // rsi
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 3222079478LL;
  *a2 = 0;
  v5 = (CASFDataUnitParserBase *)operator new(0x770u);
  v6 = v5;
  if ( v5 )
  {
    CASFDataUnitParserBase::CASFDataUnitParserBase(v5);
    *((_QWORD *)v6 + 2) = 0;
    *(_QWORD *)v6 = &CASFDataUnitParserv1::`vftable'{for `IASFDataUnitParser'};
    *((_QWORD *)v6 + 1) = &CASFDataUnitParserv1::`vftable'{for `IASFDataUnitParserPriv'};
    *(_QWORD *)((char *)v6 + 1892) = 0;
    *((_DWORD *)v6 + 472) = 1;
    v7 = ((__int64 (__fastcall *)(CASFDataUnitParserBase *, GUID *, struct IASFDataUnitParser **))CASFDataUnitParserv1::`vftable'{for `IASFDataUnitParser'})(
           v6,
           &IID_IASFDataUnitParser,
           a2);
    (*(void (__fastcall **)(CASFDataUnitParserBase *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v7 >= 0 )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2;
      v9 = 0;
      v7 = (**v8)(v8, &IID_IASFDataUnitParserPriv, &v9);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, *((_QWORD *)this + 5));
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        if ( v7 >= 0 )
          return (unsigned int)v7;
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017550  mov     [rsp+arg_10], rbx
0x180017555  push    rbp
0x180017556  push    rsi
0x180017557  push    rdi
0x180017558  sub     rsp, 30h
0x18001755c  mov     rax, cs:__security_cookie
0x180017563  xor     rax, rsp
0x180017566  mov     [rsp+48h+var_20], rax
0x18001756b  cmp     qword ptr [rcx+28h], 0
0x180017570  mov     rdi, rdx
0x180017573  mov     rbp, rcx
0x180017576  jnz     short loc_180017582
0x180017578  mov     eax, 0C00D07F6h
0x18001757d  jmp     loc_180017681
0x180017582  mov     ecx, 770h; Size
0x180017587  mov     qword ptr [rdx], 0
0x18001758e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017593  mov     rsi, rax
0x180017596  test    rax, rax
0x180017599  jz      loc_18001765F
0x18001759f  mov     rcx, rax; this
0x1800175a2  call    ??0CASFDataUnitParserBase@@QEAA@XZ; CASFDataUnitParserBase::CASFDataUnitParserBase(void)
0x1800175a7  lea     r9, ??_7CASFDataUnitParserv1@@6BIASFDataUnitParser@@@; const CASFDataUnitParserv1::`vftable'{for `IASFDataUnitParser'}
0x1800175ae  mov     qword ptr [rsi+10h], 0
0x1800175b6  lea     rax, ??_7CASFDataUnitParserv1@@6BIASFDataUnitParserPriv@@@; const CASFDataUnitParserv1::`vftable'{for `IASFDataUnitParserPriv'}
0x1800175bd  mov     [rsi], r9
0x1800175c0  mov     [rsi+8], rax
0x1800175c4  lea     rdx, IID_IASFDataUnitParser
0x1800175cb  mov     rax, [r9]
0x1800175ce  mov     r8, rdi
0x1800175d1  mov     rcx, rsi
0x1800175d4  mov     qword ptr [rsi+764h], 0
0x1800175df  mov     dword ptr [rsi+760h], 1
0x1800175e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ee  mov     rcx, [rsi]
0x1800175f1  mov     ebx, eax
0x1800175f3  mov     rax, [rcx+10h]
0x1800175f7  mov     rcx, rsi
0x1800175fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ff  test    ebx, ebx
0x180017601  js      short loc_180017664
0x180017603  mov     rcx, [rdi]
0x180017606  lea     r8, [rsp+48h+var_28]
0x18001760b  mov     [rsp+48h+var_28], 0
0x180017614  lea     rdx, IID_IASFDataUnitParserPriv
0x18001761b  mov     rax, [rcx]
0x18001761e  mov     rax, [rax]
0x180017621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017626  mov     ebx, eax
0x180017628  test    eax, eax
0x18001762a  js      short loc_180017664
0x18001762c  mov     rcx, [rsp+48h+var_28]
0x180017631  mov     rdx, [rbp+28h]
0x180017635  mov     rax, [rcx]
0x180017638  mov     rax, [rax+18h]
0x18001763c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017641  mov     rcx, [rsp+48h+var_28]
0x180017646  mov     ebx, eax
0x180017648  test    rcx, rcx
0x18001764b  jz      short loc_180017659
0x18001764d  mov     rax, [rcx]
0x180017650  mov     rax, [rax+10h]
0x180017654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017659  test    ebx, ebx
0x18001765b  jns     short loc_18001767F
0x18001765d  jmp     short loc_180017664
0x18001765f  mov     ebx, 8007000Eh
0x180017664  mov     rcx, [rdi]
0x180017667  test    rcx, rcx
0x18001766a  jz      short loc_18001767F
0x18001766c  mov     rax, [rcx]
0x18001766f  mov     rax, [rax+10h]
0x180017673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017678  mov     qword ptr [rdi], 0
0x18001767f  mov     eax, ebx
0x180017681  mov     rcx, [rsp+48h+var_20]
0x180017686  xor     rcx, rsp; StackCookie
0x180017689  call    __security_check_cookie
0x18001768e  mov     rbx, [rsp+48h+arg_10]
0x180017693  add     rsp, 30h
0x180017697  pop     rdi
0x180017698  pop     rsi
0x180017699  pop     rbp
0x18001769a  retn
```

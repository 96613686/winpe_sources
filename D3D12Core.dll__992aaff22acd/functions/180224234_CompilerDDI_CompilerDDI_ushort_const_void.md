# CompilerDDI::CompilerDDI(ushort const *,void *)

- ea: `0x180224234`
- end: `0x1802244e9`
- name: `??0CompilerDDI@@QEAA@PEBGPEAX@Z`
- size: `693`
- prototype: `CompilerDDI *(CompilerDDI *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800af350`

## callees

- `0x180003c40`
- `0x1800560e4`
- `0x1800abbcc`
- `0x18018cafc`
- `0x1801958d0`
- `0x1802241c0`
- `0x180224234`
- `0x1802246c4`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802242a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802242a3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180224253`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180224253`

## string_xrefs

- `0x1802242e7`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x180224323`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x18022437e`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x180224433`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x180224467`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x1802244af`: `Microsoft.Direct3DUndocked\src\DriverCompilerHost\CompilerDDI\compilerddi.cpp`
- `0x18022441d`: `No supported plugin DDI version found.`
- `0x180224299`: `D3D12OpenCompilerDDI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CompilerDDI *__fastcall CompilerDDI::CompilerDDI(CompilerDDI *this, const unsigned __int16 *a2, void *a3)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  FARPROC ProcAddress; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // r9
  unsigned __int64 *i; // r9
  unsigned __int64 v15; // r10
  int *v16; // rcx
  unsigned __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  int v21; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+20h] [rbp-40h]
  __int128 v23; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+40h] [rbp-20h]
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]
  char *v27; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *v29; // [rsp+90h] [rbp+30h] BYREF
  __int64 v30; // [rsp+98h] [rbp+38h] BYREF

  v29 = a3;
  *(_QWORD *)this = LoadLibraryW(a2);
  *((_QWORD *)this + 1) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_QWORD *)this + 14) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x26, v4, v5);
  ProcAddress = GetProcAddress(*(HMODULE *)this, "D3D12OpenCompilerDDI");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x29, v7, v8);
  v25 = *((_QWORD *)this + 1);
  v26 = 0;
  v27 = (char *)this + 24;
  v9 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v25);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
      (const char *)(unsigned int)v9,
      v21);
  v10 = v26;
  *((_QWORD *)this + 2) = v26;
  LODWORD(v29) = 0;
  v11 = (*((__int64 (__fastcall **)(__int64, void **, _QWORD))this + 4))(v10, &v29, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
      (const char *)(unsigned int)v11,
      v21);
  v30 = 0;
  v23 = 0;
  v24 = 0;
  std::vector<unsigned __int64>::_Construct_n<unsigned __int64 const &>(&v23, (unsigned int)v29, &v30);
  v12 = (*((__int64 (__fastcall **)(_QWORD, void **, _QWORD))this + 4))(*((_QWORD *)this + 2), &v29, v23);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
      (const char *)(unsigned int)v12,
      v21);
  LOBYTE(v13) = (_BYTE)v29;
  std::_Sort_unchecked<unsigned __int64 *,std::greater<unsigned __int64>>(
    v23,
    *((_QWORD *)&v23 + 1),
    (__int64)(*((_QWORD *)&v23 + 1) - v23) >> 3,
    v13);
  for ( i = (unsigned __int64 *)v23; i != *((unsigned __int64 **)&v23 + 1); ++i )
  {
    v15 = *i;
    v16 = (int *)qword_1802E1FA0;
    v17 = 2;
    do
    {
      if ( *(_QWORD *)&v16[4 * (v17 >> 1)] >= v15 )
      {
        v17 >>= 1;
      }
      else
      {
        v16 += 4 * (v17 >> 1) + 4;
        v17 += -1LL - (v17 >> 1);
      }
    }
    while ( (__int64)v17 > 0 );
    if ( v16 != &_ResolveDelayLoadedAPIFlags && *(_QWORD *)v16 == v15 )
    {
      *(_OWORD *)((char *)this + 120) = *(_OWORD *)v16;
      break;
    }
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x57,
    (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
    (const char *)0x887A0004LL,
    *((_QWORD *)this + 15) == 0,
    (bool)"No supported plugin DDI version found.",
    (const char *)v23);
  v18 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))this + 5))(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 15),
          *((_QWORD *)this + 16));
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
      (const char *)(unsigned int)v18,
      v22);
  *((_BYTE *)this + 136) = Version64ToEDDI(*((_QWORD *)this + 16));
  v19 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64))this + 6))(
          *((_QWORD *)this + 2),
          0,
          (char *)this + 64,
          56);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"Microsoft.Direct3DUndocked\\src\\DriverCompilerHost\\CompilerDDI\\compilerddi.cpp",
      (const char *)(unsigned int)v19,
      v22);
  std::vector<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range,std::allocator<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range>>::~vector<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range,std::allocator<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range>>(&v23);
  return this;
}

```

## disassembly

```asm
0x180224234  mov     [rsp-18h+arg_8], rbx
0x180224239  mov     [rsp-18h+arg_10], r8
0x18022423e  mov     [rsp-18h+arg_0], rcx
0x180224243  push    rbp
0x180224244  push    rsi
0x180224245  push    rdi
0x180224246  mov     rbp, rsp
0x180224249  sub     rsp, 60h
0x18022424d  mov     rbx, rcx
0x180224250  mov     rcx, rdx; lpLibFileName
0x180224253  call    cs:__imp_LoadLibraryW
0x180224259  mov     [rbx], rax
0x18022425c  mov     qword ptr [rbx+8], 0
0x180224264  lea     rdi, [rbx+18h]
0x180224268  xorps   xmm0, xmm0
0x18022426b  xor     eax, eax
0x18022426d  movups  xmmword ptr [rdi], xmm0
0x180224270  movups  xmmword ptr [rdi+10h], xmm0
0x180224274  mov     [rdi+20h], rax
0x180224278  movups  xmmword ptr [rbx+40h], xmm0
0x18022427c  movups  xmmword ptr [rbx+50h], xmm0
0x180224280  movups  xmmword ptr [rbx+60h], xmm0
0x180224284  mov     [rbx+70h], rax
0x180224288  movups  xmmword ptr [rbx+78h], xmm0
0x18022428c  mov     rcx, [rbp+18h]; this
0x180224290  cmp     [rbx], rax
0x180224293  jz      loc_1802244DE
0x180224299  lea     rdx, aD3d12opencompi; "D3D12OpenCompilerDDI"
0x1802242a0  mov     rcx, [rbx]; hModule
0x1802242a3  call    cs:__imp_GetProcAddress
0x1802242a9  mov     rdx, rax
0x1802242ac  mov     rcx, [rbp+18h]; this
0x1802242b0  test    rax, rax
0x1802242b3  jnz     short loc_1802242BE
0x1802242b5  lea     edx, [rax+29h]; void *
0x1802242b8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1802242be  mov     rax, [rbx+8]
0x1802242c2  mov     [rbp+var_18], rax
0x1802242c6  xor     eax, eax
0x1802242c8  mov     [rbp+var_10], rax
0x1802242cc  mov     [rbp+var_8], rdi
0x1802242d0  lea     rcx, [rbp+var_18]
0x1802242d4  mov     rax, rdx
0x1802242d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802242dc  mov     rcx, [rbp+18h]; this
0x1802242e0  test    eax, eax
0x1802242e2  jns     short loc_1802242F9
0x1802242e4  mov     r9d, eax; char *
0x1802242e7  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x1802242ee  mov     edx, 32h ; '2'; void *
0x1802242f3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1802242f9  mov     rcx, [rbp+var_10]
0x1802242fd  mov     [rbx+10h], rcx
0x180224301  mov     dword ptr [rbp+arg_10], 0
0x180224308  xor     r8d, r8d
0x18022430b  lea     rdx, [rbp+arg_10]
0x18022430f  mov     rax, [rbx+20h]
0x180224313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224318  mov     rcx, [rbp+18h]; this
0x18022431c  test    eax, eax
0x18022431e  jns     short loc_180224335
0x180224320  mov     r9d, eax; char *
0x180224323  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x18022432a  mov     edx, 36h ; '6'; void *
0x18022432f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180224335  mov     [rbp+arg_18], 0
0x18022433d  xorps   xmm0, xmm0
0x180224340  movdqu  [rbp+var_30], xmm0
0x180224345  mov     [rbp+var_20], 0
0x18022434d  mov     edx, dword ptr [rbp+arg_10]
0x180224350  lea     r8, [rbp+arg_18]
0x180224354  lea     rcx, [rbp+var_30]
0x180224358  call    ??$_Construct_n@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAX_KAEB_K@Z; std::vector<unsigned __int64>::_Construct_n<unsigned __int64 const &>(unsigned __int64,unsigned __int64 const &)
0x18022435d  nop
0x18022435e  mov     r8, qword ptr [rbp+var_30]
0x180224362  lea     rdx, [rbp+arg_10]
0x180224366  mov     rcx, [rbx+10h]
0x18022436a  mov     rax, [rbx+20h]
0x18022436e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180224373  mov     rcx, [rbp+18h]; this
0x180224377  test    eax, eax
0x180224379  jns     short loc_180224390
0x18022437b  mov     r9d, eax; char *
0x18022437e  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x180224385  mov     edx, 39h ; '9'; void *
0x18022438a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180224390  mov     rdx, qword ptr [rbp+var_30+8]
0x180224394  mov     rcx, qword ptr [rbp+var_30]
0x180224398  mov     r8, rdx
0x18022439b  sub     r8, rcx
0x18022439e  sar     r8, 3
0x1802243a2  mov     r9b, byte ptr [rbp+arg_10]
0x1802243a6  call    ??$_Sort_unchecked@PEA_KU?$greater@_K@std@@@std@@YAXPEA_K0_JU?$greater@_K@0@@Z; std::_Sort_unchecked<unsigned __int64 *,std::greater<unsigned __int64>>(unsigned __int64 *,unsigned __int64 *,__int64,std::greater<unsigned __int64>)
0x1802243ab  mov     r9, qword ptr [rbp+var_30]
0x1802243af  cmp     r9, qword ptr [rbp+var_30+8]
0x1802243b3  jz      short loc_180224411
0x1802243b5  mov     r10, [r9]
0x1802243b8  lea     rcx, qword_1802E1FA0
0x1802243bf  mov     edx, 2
0x1802243c4  mov     r8, rdx
0x1802243c7  shr     r8, 1
0x1802243ca  mov     r11, r8
0x1802243cd  add     r11, r11
0x1802243d0  cmp     [rcx+r11*8], r10
0x1802243d4  jnb     short loc_1802243EA
0x1802243d6  lea     rcx, [rcx+r11*8]
0x1802243da  add     rcx, 10h
0x1802243de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802243e2  sub     rax, r8
0x1802243e5  add     rdx, rax
0x1802243e8  jmp     short loc_1802243ED
0x1802243ea  mov     rdx, r8
0x1802243ed  test    rdx, rdx
0x1802243f0  jg      short loc_1802243C4
0x1802243f2  lea     rax, __ResolveDelayLoadedAPIFlags
0x1802243f9  cmp     rcx, rax
0x1802243fc  jz      short loc_180224403
0x1802243fe  cmp     [rcx], r10
0x180224401  jz      short loc_180224409
0x180224403  add     r9, 8
0x180224407  jmp     short loc_1802243AF
0x180224409  movups  xmm0, xmmword ptr [rcx]
0x18022440c  movdqu  xmmword ptr [rbx+78h], xmm0
0x180224411  cmp     qword ptr [rbx+78h], 0
0x180224416  setz    al
0x180224419  mov     rcx, [rbp+18h]; this
0x18022441d  lea     rdx, aNoSupportedPlu; "No supported plugin DDI version found."
0x180224424  mov     qword ptr [rsp+60h+var_38], rdx; bool
0x180224429  mov     [rsp+60h+var_40], al; int
0x18022442d  mov     r9d, 887A0004h; char *
0x180224433  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x18022443a  mov     edx, 57h ; 'W'; void *
0x18022443f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180224444  mov     r8, [rbx+80h]
0x18022444b  mov     rdx, [rbx+78h]
0x18022444f  mov     rcx, [rbx+10h]
0x180224453  mov     rax, [rbx+28h]
0x180224457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022445c  mov     rcx, [rbp+18h]; this
0x180224460  test    eax, eax
0x180224462  jns     short loc_180224479
0x180224464  mov     r9d, eax; char *
0x180224467  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x18022446e  mov     edx, 58h ; 'X'; void *
0x180224473  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180224479  mov     rcx, [rbx+80h]
0x180224480  call    ?Version64ToEDDI@@YA?AW4EDDIVersion@@_K@Z; Version64ToEDDI(unsigned __int64)
0x180224485  mov     [rbx+88h], al
0x18022448b  mov     r9d, 38h ; '8'
0x180224491  lea     r8, [rbx+40h]
0x180224495  xor     edx, edx
0x180224497  mov     rcx, [rbx+10h]
0x18022449b  mov     rax, [rbx+30h]
0x18022449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802244a4  mov     rcx, [rbp+18h]; this
0x1802244a8  test    eax, eax
0x1802244aa  jns     short loc_1802244C1
0x1802244ac  mov     r9d, eax; char *
0x1802244af  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\Driver"...
0x1802244b6  mov     edx, 5Bh ; '['; void *
0x1802244bb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1802244c1  lea     rcx, [rbp+var_30]; void *
0x1802244c5  call    ??1?$vector@URange@EmulatedQuerySet@?$CCommandList@UID3D12VideoProcessCommandList4@@@@V?$allocator@URange@EmulatedQuerySet@?$CCommandList@UID3D12VideoProcessCommandList4@@@@@std@@@std@@QEAA@XZ; std::vector<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range,std::allocator<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range>>::~vector<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range,std::allocator<CCommandList<ID3D12VideoProcessCommandList4>::EmulatedQuerySet::Range>>(void)
0x1802244ca  nop
0x1802244cb  mov     rax, rbx
0x1802244ce  mov     rbx, [rsp+60h+arg_8]
0x1802244d6  add     rsp, 60h
0x1802244da  pop     rdi
0x1802244db  pop     rsi
0x1802244dc  pop     rbp
0x1802244dd  retn
0x1802244de  mov     edx, 26h ; '&'; void *
0x1802244e3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

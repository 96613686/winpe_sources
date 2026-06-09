# ShieldProvider::GetIsDevMode(bool *)

- ea: `0x140007538`
- end: `0x14000770f`
- name: `?GetIsDevMode@ShieldProvider@@YAJPEA_N@Z`
- size: `471`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x1400015f4`
- `0x140001b9c`
- `0x140002474`
- `0x140006bec`
- `0x140007538`
- `0x14000d15c`
- `0x14000d688`
- `0x14000dd0c`
- `0x14000eb7c`
- `0x14000ec0c`
- `0x14001088c`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140007562`

## string_xrefs

- `0x14000757c`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x1400075c5`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x140007556`: `MsMpLics.dll`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetIsDevMode(ShieldProvider *this, bool *a2)
{
  int WindowsPath; // eax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // ebx
  unsigned __int64 v5; // rdx
  void **v7; // rbx
  int IsFileExists; // eax
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  void *v11; // r9
  int v12; // edi
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  MpLicensing *v15; // rax
  MpLicensing *v16; // r14
  unsigned int v17; // edx
  unsigned __int64 LPCWSTRValue; // r15
  unsigned __int16 *v19; // rdi
  unsigned int v20; // edx
  unsigned __int64 v21; // rdx
  int v22; // ecx
  CommonUtil *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // [rsp+0h] [rbp-58h] BYREF
  const std::exception *v26; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void **v28; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp+18h]

  ShieldProvider::g_fDevMode = 0;
  v28 = 0;
  WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v28, L"MsMpLics.dll");
  v4 = WindowsPath;
  if ( WindowsPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
      (const char *)(unsigned int)WindowsPath,
      (int)v26);
    if ( v28 )
      operator delete(v28, v5);
    return v4;
  }
  v7 = v28;
  IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v28, v3);
  v12 = IsFileExists;
  if ( IsFileExists != -2147024894 )
  {
    if ( IsFileExists < 0 )
    {
      v13 = 126;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
        (const char *)(unsigned int)v12,
        (int)v26);
      if ( v7 )
        operator delete(v7, v14);
      return (unsigned int)v12;
    }
    v12 = CommonUtil::MpUtilMicrosoftCertCheck(v7, (const unsigned __int16 *)0x24, v10, v11);
    if ( v12 < 0 )
    {
      v13 = 129;
      goto LABEL_8;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v15 = (MpLicensing *)operator new(0x18u);
      v16 = MpLicensing::MpLicensing(v15, (const unsigned __int16 *)v7);
      LPCWSTRValue = MpLicensing::GetLPCWSTRValue(v16, v17, 0, 0);
      v19 = (unsigned __int16 *)operator new[](saturated_mul(LPCWSTRValue, 2u));
      v29 = v19;
      MpLicensing::GetLPCWSTRValue(v16, v20, v19, LPCWSTRValue);
      v22 = *v19 - 49;
      if ( *v19 == 49 )
        v22 = v19[1];
      ShieldProvider::g_fDevMode = v22 == 0;
      operator delete(v19, v21);
      if ( v16 )
      {
        _HMODULE_Finalizer((HINSTANCE)_InterlockedExchange64((volatile __int64 *)v16 + 1, 0), *((void **)v16 + 2));
        if ( *(_QWORD *)v16 )
        {
          v24 = *(_QWORD *)v16 + *(int *)(**(_QWORD **)v16 + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
        }
        operator delete(v16, 0x18u);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v26) )
        CommonUtil::HrFromStdException(v23, (const struct std::exception *)&v25);
    }
  }
  if ( v7 )
    operator delete(v7, v9);
  return 0;
}

```

## disassembly

```asm
0x140007538  mov     [rsp+arg_0], rcx
0x14000753d  push    rbx
0x14000753e  push    rsi
0x14000753f  push    rdi
0x140007540  push    r14
0x140007542  push    r15
0x140007544  sub     rsp, 30h
0x140007548  xor     esi, esi
0x14000754a  mov     cs:?g_fDevMode@ShieldProvider@@3_NA, sil; bool ShieldProvider::g_fDevMode
0x140007551  mov     [rsp+58h+arg_8], rsi
0x140007556  lea     r8, aMsmplicsDll; "MsMpLics.dll"
0x14000755d  lea     rdx, [rsp+58h+arg_8]
0x140007562  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140007569  call    CommonUtil__UtilGetWindowsPath
0x14000756e  mov     ebx, eax
0x140007570  test    eax, eax
0x140007572  jns     short loc_1400075A2
0x140007574  mov     rcx, [rsp+58h]; this
0x140007579  mov     r9d, eax; char *
0x14000757c  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x140007583  lea     edx, [rsi+77h]; void *
0x140007586  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000758b  nop
0x14000758c  mov     rcx, [rsp+58h+arg_8]; void *
0x140007591  test    rcx, rcx
0x140007594  jz      short loc_14000759B
0x140007596  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000759b  mov     eax, ebx
0x14000759d  jmp     loc_140007703
0x1400075a2  mov     rbx, [rsp+58h+arg_8]
0x1400075a7  mov     rcx, rbx; this
0x1400075aa  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x1400075af  mov     edi, eax
0x1400075b1  cmp     eax, 80070002h
0x1400075b6  jz      loc_1400076F4
0x1400075bc  test    eax, eax
0x1400075be  jns     short loc_1400075EE
0x1400075c0  mov     edx, 7Eh ; '~'; void *
0x1400075c5  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x1400075cc  mov     r9d, edi; char *
0x1400075cf  mov     rcx, [rsp+58h]; this
0x1400075d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400075d9  nop
0x1400075da  test    rbx, rbx
0x1400075dd  jz      short loc_1400075E7
0x1400075df  mov     rcx, rbx; void *
0x1400075e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400075e7  mov     eax, edi
0x1400075e9  jmp     loc_140007703
0x1400075ee  mov     edx, 24h ; '$'; unsigned __int16 *
0x1400075f3  mov     rcx, rbx; this
0x1400075f6  call    ?MpUtilMicrosoftCertCheck@CommonUtil@@YAJPEBGKPEAX@Z; CommonUtil::MpUtilMicrosoftCertCheck(ushort const *,ulong,void *)
0x1400075fb  mov     edi, eax
0x1400075fd  test    eax, eax
0x1400075ff  jns     short loc_140007608
0x140007601  mov     edx, 81h
0x140007606  jmp     short loc_1400075C5
0x140007608  mov     ecx, 18h; Size
0x14000760d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007612  mov     [rsp+58h+arg_0], rax
0x140007617  mov     rdx, rbx; unsigned __int16 *
0x14000761a  mov     rcx, rax; this
0x14000761d  call    ??0MpLicensing@@QEAA@PEBG@Z; MpLicensing::MpLicensing(ushort const *)
0x140007622  mov     r14, rax
0x140007625  mov     [rsp+58h+arg_0], rax
0x14000762a  xor     r9d, r9d; unsigned int
0x14000762d  xor     r8d, r8d; unsigned __int16 *
0x140007630  mov     rcx, rax; this
0x140007633  call    ?GetLPCWSTRValue@MpLicensing@@QEBAKIPEAGK@Z; MpLicensing::GetLPCWSTRValue(uint,ushort *,ulong)
0x140007638  mov     r15d, eax
0x14000763b  mov     eax, 2
0x140007640  mul     r15
0x140007643  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000764a  cmovb   rax, rcx
0x14000764e  mov     rcx, rax; unsigned __int64
0x140007651  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140007656  mov     rdi, rax
0x140007659  mov     [rsp+58h+arg_10], rax
0x14000765e  mov     r9d, r15d; unsigned int
0x140007661  mov     r8, rax; unsigned __int16 *
0x140007664  mov     rcx, r14; this
0x140007667  call    ?GetLPCWSTRValue@MpLicensing@@QEBAKIPEAGK@Z; MpLicensing::GetLPCWSTRValue(uint,ushort *,ulong)
0x14000766c  movzx   ecx, word ptr [rdi]
0x14000766f  sub     ecx, 31h ; '1'
0x140007672  jnz     short loc_14000767D
0x140007674  movzx   ecx, word ptr [rdi+2]
0x140007678  movzx   eax, si
0x14000767b  sub     ecx, eax
0x14000767d  test    ecx, ecx
0x14000767f  setz    cs:?g_fDevMode@ShieldProvider@@3_NA; bool ShieldProvider::g_fDevMode
0x140007686  mov     rcx, rdi; void *
0x140007689  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000768e  nop
0x14000768f  test    r14, r14
0x140007692  jz      short loc_1400076D0
0x140007694  mov     rcx, rsi
0x140007697  xchg    rcx, [r14+8]; HINSTANCE
0x14000769b  mov     rdx, [r14+10h]; void *
0x14000769f  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x1400076a4  mov     r8, [r14]
0x1400076a7  test    r8, r8
0x1400076aa  jz      short loc_1400076C2
0x1400076ac  mov     rax, [r8]
0x1400076af  movsxd  rcx, dword ptr [rax+4]
0x1400076b3  add     rcx, r8
0x1400076b6  mov     rax, [rcx]
0x1400076b9  mov     rax, [rax+8]
0x1400076bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076c2  mov     edx, 18h; unsigned __int64
0x1400076c7  mov     rcx, r14; void *
0x1400076ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400076cf  nop
0x1400076d0  jmp     short loc_1400076F4
0x1400076d2  xor     esi, esi
0x1400076d4  cmp     dword ptr [rsp+58h+arg_0], esi
0x1400076d8  jge     short loc_1400076EF
0x1400076da  mov     rcx, [rsp+58h+arg_8]; void *
0x1400076df  test    rcx, rcx
0x1400076e2  jz      short loc_1400076E9
0x1400076e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400076e9  mov     eax, dword ptr [rsp+58h+arg_0]
0x1400076ed  jmp     short loc_140007703
0x1400076ef  mov     rbx, [rsp+58h+arg_8]
0x1400076f4  test    rbx, rbx
0x1400076f7  jz      short loc_140007701
0x1400076f9  mov     rcx, rbx; void *
0x1400076fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007701  xor     eax, eax
0x140007703  add     rsp, 30h
0x140007707  pop     r15
0x140007709  pop     r14
0x14000770b  pop     rdi
0x14000770c  pop     rsi
0x14000770d  pop     rbx
0x14000770e  retn
```

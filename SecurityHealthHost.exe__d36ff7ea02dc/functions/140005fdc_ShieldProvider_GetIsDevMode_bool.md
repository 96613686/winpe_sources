# ShieldProvider::GetIsDevMode(bool *)

- ea: `0x140005fdc`
- end: `0x1400061be`
- name: `?GetIsDevMode@ShieldProvider@@YAJPEA_N@Z`
- size: `482`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140003188`

## callees

- `0x140001614`
- `0x14000164c`
- `0x140002304`
- `0x140005fdc`
- `0x14000674c`
- `0x14000c688`
- `0x14000ca7c`
- `0x14000d000`
- `0x14000d968`
- `0x14000d9e8`
- `0x14000ee14`
- `0x14000f1bc`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140005fff`

## string_xrefs

- `0x140006019`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x140006062`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetIsDevMode(ShieldProvider *this, bool *a2)
{
  int WindowsPath; // eax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // ebx
  void **v5; // rcx
  void **v7; // rsi
  int IsFileExists; // eax
  __int64 v9; // rdx
  int v10; // eax
  MpLicensing *v11; // rax
  MpLicensing *v12; // r14
  unsigned int v13; // edx
  unsigned __int64 LPCWSTRValue; // r15
  unsigned __int16 *v15; // rbx
  unsigned int v16; // edx
  int v17; // ecx
  CommonUtil *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+0h] [rbp-58h] BYREF
  const std::exception *v21; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void **v23; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v24; // [rsp+70h] [rbp+18h]

  byte_140018CBC = 0;
  v23 = 0;
  WindowsPath = CommonUtil::UtilGetWindowsPath(
                  (__int64 (__fastcall *)(void *, _QWORD))GetSystemDirectoryW,
                  (CommonUtil *)&v23);
  v4 = WindowsPath;
  if ( WindowsPath < 0 )
  {
    ((void (__stdcall *)(wil::details::in1diag3 *, void *, unsigned int, const char *, int))wil::details::in1diag3::Return_Hr)(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
      (const char *)(unsigned int)WindowsPath,
      (int)v21);
    v5 = v23;
    if ( !v23 )
      return v4;
LABEL_3:
    operator delete(v5);
    return v4;
  }
  v7 = v23;
  IsFileExists = ((__int64 (__fastcall *)(CommonUtil *, const unsigned __int16 *))CommonUtil::UtilIsFileExists)(
                   (CommonUtil *)v23,
                   v3);
  v4 = IsFileExists;
  if ( IsFileExists != -2147024894 )
  {
    if ( IsFileExists < 0 )
    {
      v9 = 126;
LABEL_8:
      ((void (__stdcall *)(wil::details::in1diag3 *, void *, unsigned int, const char *, int))wil::details::in1diag3::Return_Hr)(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldproviderutil.cpp",
        (const char *)v4,
        (int)v21);
      if ( !v7 )
        return v4;
      v5 = v7;
      goto LABEL_3;
    }
    v10 = CommonUtil::MpUtilMicrosoftSelfCertCheck((__int64)v7, 39u);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -2146762496
        || (v4 = ((__int64 (__fastcall *)(void **))CommonUtil::MpUtilMicrosoftCatalogCertCheck)(v7),
            (v4 & 0x80000000) != 0) )
      {
        v9 = 129;
        goto LABEL_8;
      }
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v11 = (MpLicensing *)operator new(0x18u);
      v12 = MpLicensing::MpLicensing(v11, (const unsigned __int16 *)v7);
      LPCWSTRValue = MpLicensing::GetLPCWSTRValue(v12, v13, 0, 0);
      v15 = (unsigned __int16 *)operator new[](saturated_mul(LPCWSTRValue, 2u));
      v24 = v15;
      MpLicensing::GetLPCWSTRValue(v12, v16, v15, LPCWSTRValue);
      v17 = *v15 - 49;
      if ( *v15 == 49 )
        v17 = v15[1];
      byte_140018CBC = v17 == 0;
      operator delete(v15);
      if ( v12 )
      {
        _HMODULE_Finalizer((HINSTANCE)_InterlockedExchange64((volatile __int64 *)v12 + 1, 0), *((void **)v12 + 2));
        if ( *(_QWORD *)v12 )
        {
          v19 = *(_QWORD *)v12 + *(int *)(**(_QWORD **)v12 + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        }
        operator delete(v12);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v21) )
        CommonUtil::HrFromStdException(v18, (const struct std::exception *)&v20);
    }
  }
  if ( v7 )
    operator delete(v7);
  return 0;
}

```

## disassembly

```asm
0x140005fdc  mov     [rsp+arg_0], rcx
0x140005fe1  push    rbx
0x140005fe2  push    rsi
0x140005fe3  push    rdi
0x140005fe4  push    r14
0x140005fe6  push    r15
0x140005fe8  sub     rsp, 30h
0x140005fec  xor     edi, edi
0x140005fee  mov     cs:byte_140018CBC, dil
0x140005ff5  mov     [rsp+58h+arg_8], rdi
0x140005ffa  lea     rdx, [rsp+58h+arg_8]
0x140005fff  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140006006  call    CommonUtil__UtilGetWindowsPath
0x14000600b  mov     ebx, eax
0x14000600d  test    eax, eax
0x14000600f  jns     short loc_14000603F
0x140006011  mov     rcx, [rsp+58h]; this
0x140006016  mov     r9d, eax; char *
0x140006019  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x140006020  lea     edx, [rdi+77h]; void *
0x140006023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006028  nop
0x140006029  mov     rcx, [rsp+58h+arg_8]; void *
0x14000602e  test    rcx, rcx
0x140006031  jz      short loc_140006038
0x140006033  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006038  mov     eax, ebx
0x14000603a  jmp     loc_1400061B2
0x14000603f  mov     rsi, [rsp+58h+arg_8]
0x140006044  mov     rcx, rsi; this
0x140006047  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x14000604c  mov     ebx, eax
0x14000604e  cmp     eax, 80070002h
0x140006053  jz      loc_1400061A3
0x140006059  test    eax, eax
0x14000605b  jns     short loc_140006081
0x14000605d  mov     edx, 7Eh ; '~'; void *
0x140006062  lea     r8, aOnecoreAmcoreA; "onecore\\amcore\\antimalware\\source\\s"...
0x140006069  mov     r9d, ebx; char *
0x14000606c  mov     rcx, [rsp+58h]; this
0x140006071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006076  nop
0x140006077  test    rsi, rsi
0x14000607a  jz      short loc_140006038
0x14000607c  mov     rcx, rsi
0x14000607f  jmp     short loc_140006033
0x140006081  mov     r14d, 27h ; '''
0x140006087  mov     edx, r14d
0x14000608a  mov     rcx, rsi
0x14000608d  call    CommonUtil__MpUtilMicrosoftSelfCertCheck
0x140006092  mov     ebx, eax
0x140006094  test    eax, eax
0x140006096  jns     short loc_1400060B7
0x140006098  cmp     eax, 800B0100h
0x14000609d  jnz     short loc_1400060B0
0x14000609f  mov     edx, r14d
0x1400060a2  mov     rcx, rsi; void **
0x1400060a5  call    CommonUtil__MpUtilMicrosoftCatalogCertCheck
0x1400060aa  mov     ebx, eax
0x1400060ac  test    eax, eax
0x1400060ae  jns     short loc_1400060B7
0x1400060b0  mov     edx, 81h
0x1400060b5  jmp     short loc_140006062
0x1400060b7  mov     ecx, 18h; Size
0x1400060bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400060c1  mov     [rsp+58h+arg_0], rax
0x1400060c6  mov     rdx, rsi; unsigned __int16 *
0x1400060c9  mov     rcx, rax; this
0x1400060cc  call    ??0MpLicensing@@QEAA@PEBG@Z; MpLicensing::MpLicensing(ushort const *)
0x1400060d1  mov     r14, rax
0x1400060d4  mov     [rsp+58h+arg_0], rax
0x1400060d9  xor     r9d, r9d; unsigned int
0x1400060dc  xor     r8d, r8d; unsigned __int16 *
0x1400060df  mov     rcx, rax; this
0x1400060e2  call    ?GetLPCWSTRValue@MpLicensing@@QEBAKIPEAGK@Z; MpLicensing::GetLPCWSTRValue(uint,ushort *,ulong)
0x1400060e7  mov     r15d, eax
0x1400060ea  mov     eax, 2
0x1400060ef  mul     r15
0x1400060f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400060f9  cmovb   rax, rcx
0x1400060fd  mov     rcx, rax; unsigned __int64
0x140006100  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140006105  mov     rbx, rax
0x140006108  mov     [rsp+58h+arg_10], rax
0x14000610d  mov     r9d, r15d; unsigned int
0x140006110  mov     r8, rax; unsigned __int16 *
0x140006113  mov     rcx, r14; this
0x140006116  call    ?GetLPCWSTRValue@MpLicensing@@QEBAKIPEAGK@Z; MpLicensing::GetLPCWSTRValue(uint,ushort *,ulong)
0x14000611b  movzx   ecx, word ptr [rbx]
0x14000611e  sub     ecx, 31h ; '1'
0x140006121  jnz     short loc_14000612C
0x140006123  movzx   ecx, word ptr [rbx+2]
0x140006127  movzx   eax, di
0x14000612a  sub     ecx, eax
0x14000612c  test    ecx, ecx
0x14000612e  setz    cs:byte_140018CBC
0x140006135  mov     rcx, rbx; void *
0x140006138  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000613d  nop
0x14000613e  test    r14, r14
0x140006141  jz      short loc_14000617F
0x140006143  mov     rcx, rdi
0x140006146  xchg    rcx, [r14+8]; HINSTANCE
0x14000614a  mov     rdx, [r14+10h]; void *
0x14000614e  call    ?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z; _HMODULE_Finalizer(HINSTANCE__ *,void *)
0x140006153  mov     r8, [r14]
0x140006156  test    r8, r8
0x140006159  jz      short loc_140006171
0x14000615b  mov     rax, [r8]
0x14000615e  movsxd  rcx, dword ptr [rax+4]
0x140006162  add     rcx, r8
0x140006165  mov     rax, [rcx]
0x140006168  mov     rax, [rax+8]
0x14000616c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006171  mov     edx, 18h; unsigned __int64
0x140006176  mov     rcx, r14; void *
0x140006179  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000617e  nop
0x14000617f  jmp     short loc_1400061A3
0x140006181  xor     edi, edi
0x140006183  cmp     dword ptr [rsp+58h+arg_0], edi
0x140006187  jge     short loc_14000619E
0x140006189  mov     rcx, [rsp+58h+arg_8]; void *
0x14000618e  test    rcx, rcx
0x140006191  jz      short loc_140006198
0x140006193  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006198  mov     eax, dword ptr [rsp+58h+arg_0]
0x14000619c  jmp     short loc_1400061B2
0x14000619e  mov     rsi, [rsp+58h+arg_8]
0x1400061a3  test    rsi, rsi
0x1400061a6  jz      short loc_1400061B0
0x1400061a8  mov     rcx, rsi; void *
0x1400061ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400061b0  xor     eax, eax
0x1400061b2  add     rsp, 30h
0x1400061b6  pop     r15
0x1400061b8  pop     r14
0x1400061ba  pop     rdi
0x1400061bb  pop     rsi
0x1400061bc  pop     rbx
0x1400061bd  retn
```

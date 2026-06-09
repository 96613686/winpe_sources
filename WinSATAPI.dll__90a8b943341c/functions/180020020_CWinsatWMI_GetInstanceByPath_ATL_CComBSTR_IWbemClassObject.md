# CWinsatWMI::GetInstanceByPath(ATL::CComBSTR,IWbemClassObject * *)

- ea: `0x180020020`
- end: `0x1800202a4`
- name: `?GetInstanceByPath@CWinsatWMI@@EEAAJVCComBSTR@ATL@@PEAPEAUIWbemClassObject@@@Z`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e490`
- `0x180012bd0`
- `0x18001d358`
- `0x180020020`
- `0x180033010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800201d3`
- `msvcrt!_wcsicmp` at `0x1800201d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002006e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800201b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800201e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020257`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002006e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800201b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800201e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020257`
- `OLEAUT32!__imp_SysFreeString` at `0x180020098`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180020281`
- `OLEAUT32!__imp_SysFreeString` at `0x180020098`
- `OLEAUT32!__imp_SysFreeString` at `0x1800200e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180020281`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinsatWMI::GetInstanceByPath(_QWORD **a1, BSTR *a2, _QWORD *a3)
{
  __int64 (__fastcall *v7)(_QWORD **, __int64, _QWORD, __int64); // rbx
  _QWORD *v8; // rax
  int v9; // edi
  unsigned __int64 v10; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  wchar_t *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+30h] BYREF
  int v19; // [rsp+88h] [rbp+38h] BYREF
  __int64 v20; // [rsp+98h] [rbp+48h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v16 = 0;
  v20 = 0;
  v15 = 0;
  if ( ((int (__fastcall *)(_QWORD **, BSTR, __int64 *))(*a1)[6])(a1, *a2, &v16) < 0 )
  {
    operator delete(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    SysFreeString(*a2);
    return 2147749896LL;
  }
  v7 = (__int64 (__fastcall *)(_QWORD **, __int64, _QWORD, __int64))(*a1)[7];
  v8 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"Win32_WinSAT");
  LODWORD(v7) = v7(a1, v16, *v8, 8);
  SysFreeString(bstrString[0]);
  if ( (int)v7 < 0 )
    goto LABEL_7;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 176LL))(v16, &v20);
  if ( v9 < 0 )
    goto LABEL_13;
  v19 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 24LL))(v20, &v19);
  if ( v9 < 0 )
    goto LABEL_13;
  if ( v19 != 1
    || (v18 = 0, (*(int (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v20 + 96LL))(v20, 2, &v18) < 0) )
  {
LABEL_7:
    v9 = -2147217400;
LABEL_13:
    v13 = 0;
LABEL_26:
    operator delete(v13);
    goto LABEL_27;
  }
  v10 = 2LL * v18;
  if ( !is_mul_ok(v18, 2u) )
    v10 = -1;
  v11 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147217402;
    goto LABEL_13;
  }
  if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, wchar_t *))(*(_QWORD *)v20 + 96LL))(v20, 2, &v18, v11) >= 0 )
  {
    if ( !_wcsicmp(L"TimeTaken=\"MostRecentAssessment\"", v12) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*a1[11] + 120LL))(a1[11], 0, &v15);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(_QWORD **, __int64))(*a1)[4])(a1, v15);
        if ( v9 >= 0 )
        {
          if ( a3 )
          {
            v14 = v15;
            *a3 = v15;
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
            v9 = 0;
          }
          else
          {
            v9 = -2147467261;
          }
        }
      }
      v13 = v12;
      goto LABEL_26;
    }
    operator delete(v12);
    v9 = -2147217406;
  }
  else
  {
    operator delete(v12);
    v9 = -2147217400;
  }
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  SysFreeString(*a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180020020  mov     rax, rsp
0x180020023  push    rbp
0x180020024  push    rsi
0x180020025  push    rdi
0x180020026  push    r14
0x180020028  push    r15
0x18002002a  mov     rbp, rsp
0x18002002d  sub     rsp, 50h
0x180020031  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180020039  mov     [rax+18h], rbx
0x18002003d  mov     r14, r8
0x180020040  mov     r15, rdx
0x180020043  mov     rsi, rcx
0x180020046  and     [rbp+var_18], 0
0x18002004b  and     [rbp+arg_18], 0
0x180020050  and     [rbp+var_20], 0
0x180020055  mov     rax, [rcx]
0x180020058  lea     r8, [rbp+var_18]
0x18002005c  mov     rdx, [rdx]
0x18002005f  mov     rax, [rax+30h]
0x180020063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020068  test    eax, eax
0x18002006a  jns     short loc_1800200AE
0x18002006c  xor     ecx, ecx
0x18002006e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020075  nop     dword ptr [rax+rax+00h]
0x18002007a  lea     rcx, [rbp+var_20]
0x18002007e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020083  lea     rcx, [rbp+arg_18]
0x180020087  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002008c  lea     rcx, [rbp+var_18]
0x180020090  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020095  mov     rcx, [r15]; bstrString
0x180020098  call    cs:__imp_SysFreeString
0x18002009f  nop     dword ptr [rax+rax+00h]
0x1800200a4  mov     eax, 80041008h
0x1800200a9  jmp     loc_18002028F
0x1800200ae  mov     rax, [rsi]
0x1800200b1  mov     rbx, [rax+38h]
0x1800200b5  lea     rdx, aWin32Winsat; "Win32_WinSAT"
0x1800200bc  lea     rcx, [rbp+bstrString]; this
0x1800200c0  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800200c5  mov     r9d, 8
0x1800200cb  mov     r8, [rax]
0x1800200ce  mov     rdx, [rbp+var_18]
0x1800200d2  mov     rcx, rsi
0x1800200d5  mov     rax, rbx
0x1800200d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200dd  mov     ebx, eax
0x1800200df  mov     rcx, [rbp+bstrString]; bstrString
0x1800200e3  call    cs:__imp_SysFreeString
0x1800200ea  nop     dword ptr [rax+rax+00h]
0x1800200ef  test    ebx, ebx
0x1800200f1  js      short loc_180020134
0x1800200f3  mov     rcx, [rbp+var_18]
0x1800200f7  mov     rax, [rcx]
0x1800200fa  lea     rdx, [rbp+arg_18]
0x1800200fe  mov     rax, [rax+0B0h]
0x180020105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002010a  mov     edi, eax
0x18002010c  test    eax, eax
0x18002010e  js      short loc_18002018C
0x180020110  and     [rbp+arg_8], 0
0x180020114  mov     rcx, [rbp+arg_18]
0x180020118  mov     rax, [rcx]
0x18002011b  lea     rdx, [rbp+arg_8]
0x18002011f  mov     rax, [rax+18h]
0x180020123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020128  mov     edi, eax
0x18002012a  test    eax, eax
0x18002012c  js      short loc_18002018C
0x18002012e  cmp     [rbp+arg_8], 1
0x180020132  jz      short loc_18002013B
0x180020134  mov     edi, 80041008h
0x180020139  jmp     short loc_18002018C
0x18002013b  and     [rbp+arg_0], 0
0x18002013f  mov     rcx, [rbp+arg_18]
0x180020143  mov     rax, [rcx]
0x180020146  xor     r9d, r9d
0x180020149  lea     r8, [rbp+arg_0]
0x18002014d  lea     edi, [r9+2]
0x180020151  mov     edx, edi
0x180020153  mov     rax, [rax+60h]
0x180020157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002015c  test    eax, eax
0x18002015e  js      short loc_180020134
0x180020160  mov     ecx, [rbp+arg_0]
0x180020163  mov     eax, edi
0x180020165  mul     rcx
0x180020168  lea     rcx, [rdi-3]
0x18002016c  cmovo   rax, rcx
0x180020170  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020177  mov     rcx, rax; unsigned __int64
0x18002017a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002017f  mov     rbx, rax
0x180020182  test    rax, rax
0x180020185  jnz     short loc_180020193
0x180020187  mov     edi, 80041006h
0x18002018c  xor     ecx, ecx
0x18002018e  jmp     loc_180020257
0x180020193  mov     rcx, [rbp+arg_18]
0x180020197  mov     rax, [rcx]
0x18002019a  mov     r9, rbx
0x18002019d  lea     r8, [rbp+arg_0]
0x1800201a1  mov     edx, edi
0x1800201a3  mov     rax, [rax+60h]
0x1800201a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201ac  test    eax, eax
0x1800201ae  jns     short loc_1800201C9
0x1800201b0  mov     rcx, rbx
0x1800201b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800201ba  nop     dword ptr [rax+rax+00h]
0x1800201bf  mov     edi, 80041008h
0x1800201c4  jmp     loc_180020263
0x1800201c9  mov     rdx, rbx; String2
0x1800201cc  lea     rcx, aTimetakenMostr; "TimeTaken=\"MostRecentAssessment\""
0x1800201d3  call    cs:__imp__wcsicmp
0x1800201da  nop     dword ptr [rax+rax+00h]
0x1800201df  test    eax, eax
0x1800201e1  jz      short loc_1800201F9
0x1800201e3  mov     rcx, rbx
0x1800201e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800201ed  nop     dword ptr [rax+rax+00h]
0x1800201f2  mov     edi, 80041002h
0x1800201f7  jmp     short loc_180020263
0x1800201f9  mov     rcx, [rsi+58h]
0x1800201fd  mov     rax, [rcx]
0x180020200  lea     r8, [rbp+var_20]
0x180020204  xor     edx, edx
0x180020206  mov     rax, [rax+78h]
0x18002020a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002020f  mov     edi, eax
0x180020211  test    eax, eax
0x180020213  js      short loc_180020254
0x180020215  mov     rax, [rsi]
0x180020218  mov     rdx, [rbp+var_20]
0x18002021c  mov     rcx, rsi
0x18002021f  mov     rax, [rax+20h]
0x180020223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020228  mov     edi, eax
0x18002022a  test    eax, eax
0x18002022c  js      short loc_180020254
0x18002022e  test    r14, r14
0x180020231  jnz     short loc_18002023A
0x180020233  mov     edi, 80004003h
0x180020238  jmp     short loc_180020254
0x18002023a  mov     rcx, [rbp+var_20]
0x18002023e  mov     [r14], rcx
0x180020241  test    rcx, rcx
0x180020244  jz      short loc_180020252
0x180020246  mov     rax, [rcx]
0x180020249  mov     rax, [rax+8]
0x18002024d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020252  xor     edi, edi
0x180020254  mov     rcx, rbx
0x180020257  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002025e  nop     dword ptr [rax+rax+00h]
0x180020263  lea     rcx, [rbp+var_20]
0x180020267  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002026c  lea     rcx, [rbp+arg_18]
0x180020270  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020275  lea     rcx, [rbp+var_18]
0x180020279  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002027e  mov     rcx, [r15]; bstrString
0x180020281  call    cs:__imp_SysFreeString
0x180020288  nop     dword ptr [rax+rax+00h]
0x18002028d  mov     eax, edi
0x18002028f  mov     rbx, [rsp+50h+arg_10]
0x180020297  add     rsp, 50h
0x18002029b  pop     r15
0x18002029d  pop     r14
0x18002029f  pop     rdi
0x1800202a0  pop     rsi
0x1800202a1  pop     rbp
0x1800202a2  retn
```

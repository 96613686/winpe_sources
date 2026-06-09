# ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x180001618`
- end: `0x18000181f`
- name: `?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `519`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800013c0`

## callees

- `0x180001618`
- `0x180001f88`
- `0x180002238`
- `0x180007700`
- `0x180007bd4`
- `0x18000bb9c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180001770`
- `KERNEL32!GetModuleHandleW` at `0x180001770`
- `KERNEL32!GetProcAddress` at `0x180001785`
- `KERNEL32!GetProcAddress` at `0x180001785`
- `USER32!CharNextW` at `0x18000170c`
- `USER32!CharNextW` at `0x18000170c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800016ac`
- `OLEAUT32!__imp_SysStringLen` at `0x1800016ac`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180001790`

## string_xrefs

- `0x180001769`: `OLEAUT32.DLL`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  wchar_t *v3; // rbx
  UINT v4; // eax
  errno_t v5; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rbx
  wchar_t *v11; // rdi
  LPWSTR v12; // rax
  __int64 v13; // rbx
  HMODULE ModuleHandleW; // rax
  __int64 (__fastcall *ProcAddress)(struct ITypeLib *, BSTR, wchar_t *); // rax
  BSTR pbstr; // [rsp+38h] [rbp-D0h] BYREF
  struct ITypeLib *v18; // [rsp+40h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t Destination[264]; // [rsp+58h] [rbp-B0h] BYREF

  bstrString = 0;
  v18 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v18);
  if ( v2 >= 0 )
  {
    pbstr = 0;
    v3 = 0;
    if ( ((int (__fastcall *)(struct ITypeLib *, __int64, _QWORD, _QWORD, _QWORD, BSTR *))v18->lpVtbl->GetDocumentation)(
           v18,
           0xFFFFFFFFLL,
           0,
           0,
           0,
           &pbstr) >= 0
      && pbstr )
    {
      v4 = SysStringLen(pbstr);
      v5 = wcsncpy_s(Destination, 0x104u, pbstr, v4);
      if ( v5 )
      {
        if ( v5 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v5 == 22 || v5 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v5 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v10 = Destination;
      Destination[259] = 0;
      v11 = Destination;
      if ( Destination[0] )
      {
        do
        {
          v12 = CharNextW(v11);
          v7 = *v11;
          LOWORD(v7) = v7 - 47;
          if ( (unsigned __int16)v7 <= 0x2Du )
          {
            v6 = 0x200000000801LL;
            if ( _bittest64(&v6, v7) )
              v10 = v12;
          }
          v11 = v12;
        }
        while ( *v12 );
      }
      v13 = v10 - Destination;
      if ( 2 * (unsigned __int64)(unsigned int)v13 >= 0x208 )
        _report_rangecheckfailure(v7, v6, v8, v9);
      Destination[(unsigned int)v13] = 0;
      v3 = Destination;
    }
    if ( !ATL::_AtlRegisterPerUser
      || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
      || (ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, wchar_t *))GetProcAddress(
                                                                                      ModuleHandleW,
                                                                                      "RegisterTypeLibForUser")) == 0 )
    {
      ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, wchar_t *))RegisterTypeLib;
    }
    v2 = ProcAddress(v18, bstrString, v3);
    SysFreeString(pbstr);
  }
  if ( v18 )
    ((void (__fastcall *)(struct ITypeLib *))v18->lpVtbl->Release)(v18);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001618  mov     rax, rsp
0x18000161b  mov     [rax+10h], rbx
0x18000161f  mov     [rax+18h], rsi
0x180001623  mov     [rax+20h], rdi
0x180001627  push    rbp
0x180001628  lea     rbp, [rax-178h]
0x18000162f  sub     rsp, 270h
0x180001636  mov     rax, cs:__security_cookie
0x18000163d  xor     rax, rsp
0x180001640  mov     [rbp+170h+var_10], rax
0x180001647  xor     esi, esi
0x180001649  lea     r9, [rsp+270h+var_238]; struct ITypeLib **
0x18000164e  lea     r8, [rsp+270h+bstrString]; unsigned __int16 **
0x180001653  mov     [rsp+270h+bstrString], rsi
0x180001658  mov     [rsp+270h+var_238], rsi
0x18000165d  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x180001662  mov     ebx, eax
0x180001664  test    eax, eax
0x180001666  js      loc_1800017B3
0x18000166c  mov     rcx, [rsp+270h+var_238]
0x180001671  lea     rdx, [rsp+270h+pbstr]
0x180001676  mov     [rsp+270h+var_248], rdx
0x18000167b  xor     r9d, r9d
0x18000167e  mov     [rsp+270h+pbstr], rsi
0x180001683  xor     r8d, r8d
0x180001686  or      edx, 0FFFFFFFFh
0x180001689  mov     [rsp+270h+var_250], rsi
0x18000168e  mov     rax, [rcx]
0x180001691  mov     ebx, esi
0x180001693  call    qword ptr [rax+48h]
0x180001696  test    eax, eax
0x180001698  js      loc_180001760
0x18000169e  mov     rcx, [rsp+270h+pbstr]; pbstr
0x1800016a3  test    rcx, rcx
0x1800016a6  jz      loc_180001760
0x1800016ac  call    cs:__imp_SysStringLen
0x1800016b2  mov     r8, [rsp+270h+pbstr]; Source
0x1800016b7  lea     rcx, [rsp+270h+Destination]; Destination
0x1800016bc  mov     r9d, eax; MaxCount
0x1800016bf  mov     edx, 104h; SizeInWords
0x1800016c4  call    wcsncpy_s
0x1800016c9  test    eax, eax
0x1800016cb  jz      short loc_1800016F1
0x1800016cd  cmp     eax, 0Ch
0x1800016d0  jz      loc_1800017F8
0x1800016d6  cmp     eax, 16h
0x1800016d9  jz      loc_180001814
0x1800016df  cmp     eax, 22h ; '"'
0x1800016e2  jz      loc_180001814
0x1800016e8  cmp     eax, 50h ; 'P'
0x1800016eb  jnz     loc_180001809
0x1800016f1  lea     rbx, [rsp+270h+Destination]
0x1800016f6  mov     [rbp+170h+var_1A], si
0x1800016fd  lea     rdi, [rsp+270h+Destination]
0x180001702  cmp     [rsp+270h+Destination], si
0x180001707  jz      short loc_18000173A
0x180001709  mov     rcx, rdi; lpsz
0x18000170c  call    cs:__imp_CharNextW
0x180001712  movzx   ecx, word ptr [rdi]
0x180001715  sub     cx, 2Fh ; '/'
0x180001719  cmp     cx, 2Dh ; '-'
0x18000171d  ja      short loc_180001732
0x18000171f  mov     rdx, 200000000801h
0x180001729  bt      rdx, rcx
0x18000172d  jnb     short loc_180001732
0x18000172f  mov     rbx, rax
0x180001732  mov     rdi, rax
0x180001735  cmp     [rax], si
0x180001738  jnz     short loc_180001709
0x18000173a  lea     rax, [rsp+270h+Destination]
0x18000173f  sub     rbx, rax
0x180001742  sar     rbx, 1
0x180001745  mov     eax, ebx
0x180001747  add     rax, rax
0x18000174a  cmp     rax, 208h
0x180001750  jnb     loc_180001803
0x180001756  mov     [rsp+rax+270h+Destination], si
0x18000175b  lea     rbx, [rsp+270h+Destination]
0x180001760  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1; bool ATL::_AtlRegisterPerUser
0x180001767  jnz     short loc_180001790
0x180001769  lea     rcx, ModuleName; "OLEAUT32.DLL"
0x180001770  call    cs:__imp_GetModuleHandleW
0x180001776  test    rax, rax
0x180001779  jz      short loc_180001790
0x18000177b  lea     rdx, ProcName; "RegisterTypeLibForUser"
0x180001782  mov     rcx, rax; hModule
0x180001785  call    cs:__imp_GetProcAddress
0x18000178b  test    rax, rax
0x18000178e  jnz     short loc_180001797
0x180001790  mov     rax, cs:__imp_RegisterTypeLib
0x180001797  mov     rdx, [rsp+270h+bstrString]
0x18000179c  mov     r8, rbx
0x18000179f  mov     rcx, [rsp+270h+var_238]
0x1800017a4  call    rax
0x1800017a6  mov     rcx, [rsp+270h+pbstr]; bstrString
0x1800017ab  mov     ebx, eax
0x1800017ad  call    cs:__imp_SysFreeString
0x1800017b3  mov     rcx, [rsp+270h+var_238]
0x1800017b8  test    rcx, rcx
0x1800017bb  jz      short loc_1800017C3
0x1800017bd  mov     rax, [rcx]
0x1800017c0  call    qword ptr [rax+10h]
0x1800017c3  mov     rcx, [rsp+270h+bstrString]; bstrString
0x1800017c8  call    cs:__imp_SysFreeString
0x1800017ce  mov     eax, ebx
0x1800017d0  mov     rcx, [rbp+170h+var_10]
0x1800017d7  xor     rcx, rsp; StackCookie
0x1800017da  call    __security_check_cookie
0x1800017df  lea     r11, [rsp+270h+var_s0]
0x1800017e7  mov     rbx, [r11+18h]
0x1800017eb  mov     rsi, [r11+20h]
0x1800017ef  mov     rdi, [r11+28h]
0x1800017f3  mov     rsp, r11
0x1800017f6  pop     rbp
0x1800017f7  retn
0x1800017f8  mov     ecx, 8007000Eh; int
0x1800017fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180001803  call    __report_rangecheckfailure
0x180001809  mov     ecx, 80004005h; int
0x18000180e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180001814  mov     ecx, 80070057h; int
0x180001819  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

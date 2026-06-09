# DllGetClassObject

- ea: `0x180005760`
- end: `0x18000599b`
- name: `DllGetClassObject`
- size: `571`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005760`
- `0x18000684c`
- `0x180007580`
- `0x1800075f0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005887`
- `KERNEL32!EnterCriticalSection` at `0x180005887`
- `KERNEL32!LeaveCriticalSection` at `0x1800058b4`
- `KERNEL32!LeaveCriticalSection` at `0x1800058b4`
- `ADVAPI32!RegGetValueW` at `0x18000597a`
- `ADVAPI32!RegGetValueW` at `0x18000597a`

## string_xrefs

- `0x180005945`: `DisableEhStorShellExtension`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v3; // r9
  HRESULT v8; // edi
  _QWORD **v9; // rcx
  _QWORD *v10; // rbx
  _DWORD *v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, const IID *const, LPVOID *); // rcx
  BOOL v13; // eax
  DWORD pcbData[10]; // [rsp+40h] [rbp-28h] BYREF
  int pvData; // [rsp+88h] [rbp+20h] BYREF

  v3 = (unsigned int)tls_index;
  if ( dword_180012990 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180012990);
    if ( dword_180012990 == -1 )
    {
      pvData = 0;
      pcbData[0] = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Storage",
             L"DisableEhStorShellExtension",
             0x10u,
             0,
             &pvData,
             pcbData) )
      {
        LOBYTE(v13) = 1;
      }
      else
      {
        v13 = pvData != 0;
      }
      byte_180012994 = v13;
      Init_thread_footer(&dword_180012990);
    }
  }
  if ( byte_180012994 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_70386b98fddf309fe90785df7da13b57_Traceguids, v3);
    *ppv = 0;
    return -2147221231;
  }
  else
  {
    if ( !ATL::_AtlComModule )
      return -2147418113;
    if ( !ppv )
      return -2147467261;
    *ppv = 0;
    v8 = 0;
    v9 = (_QWORD **)qword_180012950;
    if ( qword_180012950 < (unsigned __int64)qword_180012958 )
    {
      while ( 1 )
      {
        v10 = *v9;
        if ( *v9 )
        {
          if ( v10[2] )
          {
            v11 = (_DWORD *)*v10;
            if ( rclsid->Data1 == *(_DWORD *)*v10
              && *(_DWORD *)&rclsid->Data2 == v11[1]
              && *(_DWORD *)rclsid->Data4 == v11[2]
              && *(_DWORD *)&rclsid->Data4[4] == v11[3] )
            {
              break;
            }
          }
        }
        if ( (unsigned __int64)++v9 >= qword_180012958 )
          goto LABEL_26;
      }
      if ( !v10[4] )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)&stru_180012960);
        if ( !v10[4] )
          v8 = ((__int64 (__fastcall *)(_QWORD, GUID *, _QWORD *))v10[2])(
                 v10[3],
                 &GUID_00000000_0000_0000_c000_000000000046,
                 v10 + 4);
        LeaveCriticalSection((LPCRITICAL_SECTION)&stru_180012960);
      }
      v12 = (__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))v10[4];
      if ( v12 )
        v8 = (**v12)(v12, riid, ppv);
    }
LABEL_26:
    if ( !*ppv && !v8 )
      return -2147221231;
    return v8;
  }
}

```

## disassembly

```asm
0x180005760  mov     [rsp+arg_10], rbp
0x180005765  push    rsi
0x180005766  push    r14
0x180005768  push    r15
0x18000576a  sub     rsp, 50h
0x18000576e  mov     r9d, cs:_tls_index
0x180005775  mov     rsi, rcx
0x180005778  mov     rax, gs:58h
0x180005781  xor     r15d, r15d
0x180005784  mov     ecx, 4
0x180005789  mov     r14, r8
0x18000578c  mov     rbp, rdx
0x18000578f  mov     rax, [rax+r9*8]
0x180005793  mov     eax, [rcx+rax]
0x180005796  cmp     cs:dword_180012990, eax
0x18000579c  jg      loc_18000591A
0x1800057a2  cmp     cs:byte_180012994, r15b
0x1800057a9  jz      short loc_1800057F3
0x1800057ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057b2  lea     rax, WPP_GLOBAL_Control
0x1800057b9  cmp     rcx, rax
0x1800057bc  jz      short loc_1800057D9
0x1800057be  test    byte ptr [rcx+1Ch], 20h
0x1800057c2  jz      short loc_1800057D9
0x1800057c4  mov     rcx, [rcx+10h]
0x1800057c8  lea     r8, WPP_70386b98fddf309fe90785df7da13b57_Traceguids
0x1800057cf  mov     edx, 0Ch
0x1800057d4  call    WPP_SF_
0x1800057d9  mov     [r14], r15
0x1800057dc  mov     eax, 80040111h
0x1800057e1  mov     rbp, [rsp+68h+arg_10]
0x1800057e9  add     rsp, 50h
0x1800057ed  pop     r15
0x1800057ef  pop     r14
0x1800057f1  pop     rsi
0x1800057f2  retn
0x1800057f3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, r15d; ATL::CAtlComModule ATL::_AtlComModule
0x1800057fa  mov     [rsp+68h+arg_8], rdi
0x1800057ff  jnz     short loc_18000580B
0x180005801  mov     edi, 8000FFFFh
0x180005806  jmp     loc_1800058EA
0x18000580b  test    r14, r14
0x18000580e  jnz     short loc_18000581A
0x180005810  mov     edi, 80004003h
0x180005815  jmp     loc_1800058EA
0x18000581a  mov     [r14], r15
0x18000581d  mov     edi, r15d
0x180005820  mov     rcx, cs:qword_180012950
0x180005827  mov     r8, cs:qword_180012958
0x18000582e  cmp     rcx, r8
0x180005831  jnb     loc_1800058DB
0x180005837  mov     [rsp+68h+arg_0], rbx
0x18000583c  nop     dword ptr [rax+00h]
0x180005840  mov     rbx, [rcx]
0x180005843  test    rbx, rbx
0x180005846  jz      short loc_18000586F
0x180005848  cmp     [rbx+10h], rdi
0x18000584c  jz      short loc_18000586F
0x18000584e  mov     rdx, [rbx]
0x180005851  mov     eax, [rdx]
0x180005853  cmp     [rsi], eax
0x180005855  jnz     short loc_18000586F
0x180005857  mov     eax, [rdx+4]
0x18000585a  cmp     [rsi+4], eax
0x18000585d  jnz     short loc_18000586F
0x18000585f  mov     eax, [rdx+8]
0x180005862  cmp     [rsi+8], eax
0x180005865  jnz     short loc_18000586F
0x180005867  mov     eax, [rdx+0Ch]
0x18000586a  cmp     [rsi+0Ch], eax
0x18000586d  jz      short loc_18000587A
0x18000586f  add     rcx, 8
0x180005873  cmp     rcx, r8
0x180005876  jb      short loc_180005840
0x180005878  jmp     short loc_1800058D6
0x18000587a  cmp     [rbx+20h], rdi
0x18000587e  jnz     short loc_1800058BA
0x180005880  lea     rcx, stru_180012960; lpCriticalSection
0x180005887  call    cs:__imp_EnterCriticalSection
0x18000588d  cmp     [rbx+20h], rdi
0x180005891  jnz     short loc_1800058AD
0x180005893  mov     rcx, [rbx+18h]
0x180005897  lea     r8, [rbx+20h]
0x18000589b  mov     rax, [rbx+10h]
0x18000589f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800058a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ab  mov     edi, eax
0x1800058ad  lea     rcx, stru_180012960; lpCriticalSection
0x1800058b4  call    cs:__imp_LeaveCriticalSection
0x1800058ba  mov     rcx, [rbx+20h]
0x1800058be  test    rcx, rcx
0x1800058c1  jz      short loc_1800058D6
0x1800058c3  mov     rax, [rcx]
0x1800058c6  mov     r8, r14
0x1800058c9  mov     rdx, rbp
0x1800058cc  mov     rax, [rax]
0x1800058cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d4  mov     edi, eax
0x1800058d6  mov     rbx, [rsp+68h+arg_0]
0x1800058db  cmp     [r14], r15
0x1800058de  jnz     short loc_1800058EA
0x1800058e0  test    edi, edi
0x1800058e2  mov     eax, 80040111h
0x1800058e7  cmovz   edi, eax
0x1800058ea  mov     rbp, [rsp+68h+arg_10]
0x1800058f2  mov     eax, edi
0x1800058f4  mov     rdi, [rsp+68h+arg_8]
0x1800058f9  add     rsp, 50h
0x1800058fd  pop     r15
0x1800058ff  pop     r14
0x180005901  pop     rsi
0x180005902  retn
0x180005903  lea     rcx, dword_180012990
0x18000590a  mov     cs:byte_180012994, al
0x180005910  call    _Init_thread_footer
0x180005915  jmp     loc_1800057A2
0x18000591a  lea     rcx, dword_180012990
0x180005921  call    _Init_thread_header
0x180005926  cmp     cs:dword_180012990, 0FFFFFFFFh
0x18000592d  jnz     loc_1800057A2
0x180005933  lea     rax, [rsp+68h+var_28]
0x180005938  mov     [rsp+68h+arg_18], r15d
0x180005940  mov     [rsp+68h+pcbData], rax; pcbData
0x180005945  lea     r8, Value; "DisableEhStorShellExtension"
0x18000594c  lea     rax, [rsp+68h+arg_18]
0x180005954  mov     [rsp+68h+var_28], 4
0x18000595c  mov     [rsp+68h+pvData], rax; pvData
0x180005961  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180005968  mov     r9d, 10h; dwFlags
0x18000596e  mov     [rsp+68h+pdwType], r15; pdwType
0x180005973  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000597a  call    cs:__imp_RegGetValueW
0x180005980  test    eax, eax
0x180005982  jz      short loc_18000598B
0x180005984  mov     al, 1
0x180005986  jmp     loc_180005903
0x18000598b  cmp     [rsp+68h+arg_18], r15d
0x180005993  setnz   al
0x180005996  jmp     loc_180005903
```

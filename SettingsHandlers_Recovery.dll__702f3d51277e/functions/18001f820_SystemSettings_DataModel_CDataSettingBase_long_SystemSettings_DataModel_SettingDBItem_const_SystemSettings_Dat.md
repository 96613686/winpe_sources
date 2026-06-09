# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(HSTRING__ *,IInspectable *)

- ea: `0x18001f820`
- end: `0x18001f9f2`
- name: `?SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x18001f820`
- `0x1800220d8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f8dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f8dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f924`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f924`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f865`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f865`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f847`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
        RTL_SRWLOCK *a1,
        HSTRING a2,
        __int64 (***a3)(void))
{
  const WCHAR *StringRawBuffer; // rax
  int v6; // eax
  int v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v10; // edi
  __int64 result; // rax
  PVOID Ptr; // rcx
  int v13; // eax
  unsigned int v14; // edi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v6 = CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0);
  try
  {
    if ( v6 == 2 )
    {
      if ( !a3 )
      {
        v7 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))a1->Ptr + 31))(a1);
        v10 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8B7,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
            (const char *)(unsigned int)v7,
            bIgnoreCase);
          if ( LOBYTE(a1[19].Ptr) )
            BYTE2(a1[19].Ptr) = 1;
          return v10;
        }
        goto LABEL_21;
      }
      if ( LODWORD(a1[23].Ptr) )
      {
        AcquireSRWLockExclusive(a1 + 25);
        if ( a1[24].Ptr != a3 )
        {
          ((void (__fastcall *)(__int64 (***)(void)))(*a3)[1])(a3);
          Ptr = a1[24].Ptr;
          a1[24].Ptr = a3;
          if ( Ptr )
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
        }
        if ( a1 != (RTL_SRWLOCK *)-200LL )
          ReleaseSRWLockExclusive(a1 + 25);
        (*((void (__fastcall **)(RTL_SRWLOCK *, RTL_SRWLOCK *))a1->Ptr + 24))(a1, a1);
        if ( LOBYTE(a1[19].Ptr) )
          BYTE2(a1[19].Ptr) = 1;
        result = 0;
      }
      else
      {
        v13 = SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(
                a1,
                a3);
        v14 = v13;
        if ( v13 >= 0 )
        {
LABEL_21:
          if ( LOBYTE(a1[19].Ptr) )
            BYTE2(a1[19].Ptr) = 1;
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8C9,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v13,
          bIgnoreCase);
        if ( LOBYTE(a1[19].Ptr) )
          BYTE2(a1[19].Ptr) = 1;
        result = v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8CF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        (const char *)0x80070057LL,
        bIgnoreCase);
      if ( LOBYTE(a1[19].Ptr) )
        BYTE2(a1[19].Ptr) = 1;
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x8D4, v8, v9);
  }
  return result;
}

```

## disassembly

```asm
0x18001f820  mov     [rsp+arg_8], rbx
0x18001f825  mov     [rsp+arg_10], rsi
0x18001f82a  push    rdi
0x18001f82b  sub     rsp, 40h
0x18001f82f  mov     rdi, r8
0x18001f832  mov     rax, rdx
0x18001f835  mov     rbx, rcx
0x18001f838  mov     [rsp+48h+var_18], rcx
0x18001f83d  mov     [rsp+48h+var_10], 1
0x18001f842  xor     edx, edx; length
0x18001f844  mov     rcx, rax; string
0x18001f847  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f84d  mov     rcx, rax; lpString1
0x18001f850  mov     [rsp+48h+bIgnoreCase], 0; int
0x18001f858  or      edx, 0FFFFFFFFh; cchCount1
0x18001f85b  mov     r9d, edx; cchCount2
0x18001f85e  lea     r8, aValue; "Value"
0x18001f865  call    cs:__imp_CompareStringOrdinal
0x18001f86b  cmp     eax, 2
0x18001f86e  jnz     loc_18001F9AA
0x18001f874  test    rdi, rdi
0x18001f877  jnz     short loc_18001F8C6
0x18001f879  mov     rax, [rbx]
0x18001f87c  mov     rcx, rbx
0x18001f87f  mov     rax, [rax+0F8h]
0x18001f886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f88b  mov     edi, eax
0x18001f88d  test    eax, eax
0x18001f88f  jns     loc_18001F996
0x18001f895  mov     rcx, [rsp+48h]; this
0x18001f89a  mov     r9d, eax; char *
0x18001f89d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001f8a4  mov     edx, 8B7h; void *
0x18001f8a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f8ae  nop
0x18001f8af  cmp     byte ptr [rbx+98h], 0
0x18001f8b6  jz      short loc_18001F8BF
0x18001f8b8  mov     byte ptr [rbx+9Ah], 1
0x18001f8bf  mov     eax, edi
0x18001f8c1  jmp     loc_18001F9E1
0x18001f8c6  cmp     dword ptr [rbx+0B8h], 0
0x18001f8cd  jz      loc_18001F957
0x18001f8d3  lea     rsi, [rbx+0C8h]
0x18001f8da  mov     rcx, rsi; SRWLock
0x18001f8dd  call    cs:__imp_AcquireSRWLockExclusive
0x18001f8e3  cmp     [rbx+0C0h], rdi
0x18001f8ea  jz      short loc_18001F91C
0x18001f8ec  mov     rax, [rdi]
0x18001f8ef  mov     rcx, rdi
0x18001f8f2  mov     rax, [rax+8]
0x18001f8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8fb  nop
0x18001f8fc  mov     rcx, [rbx+0C0h]
0x18001f903  mov     [rbx+0C0h], rdi
0x18001f90a  test    rcx, rcx
0x18001f90d  jz      short loc_18001F91C
0x18001f90f  mov     rax, [rcx]
0x18001f912  mov     rax, [rax+10h]
0x18001f916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f91b  nop
0x18001f91c  test    rsi, rsi
0x18001f91f  jz      short loc_18001F92A
0x18001f921  mov     rcx, rsi; SRWLock
0x18001f924  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f92a  mov     rax, [rbx]
0x18001f92d  mov     rdx, rbx
0x18001f930  mov     rcx, rbx
0x18001f933  mov     rax, [rax+0C0h]
0x18001f93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f93f  nop
0x18001f940  cmp     byte ptr [rbx+98h], 0
0x18001f947  jz      short loc_18001F950
0x18001f949  mov     byte ptr [rbx+9Ah], 1
0x18001f950  xor     eax, eax
0x18001f952  jmp     loc_18001F9E1
0x18001f957  mov     rdx, rdi
0x18001f95a  mov     rcx, rbx
0x18001f95d  call    ?_SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@AEAAJPEAUIInspectable@@@Z; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::_SetValue(IInspectable *)
0x18001f962  mov     edi, eax
0x18001f964  test    eax, eax
0x18001f966  jns     short loc_18001F996
0x18001f968  mov     rcx, [rsp+48h]; this
0x18001f96d  mov     r9d, eax; char *
0x18001f970  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001f977  mov     edx, 8C9h; void *
0x18001f97c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f981  nop
0x18001f982  cmp     byte ptr [rbx+98h], 0
0x18001f989  jz      short loc_18001F992
0x18001f98b  mov     byte ptr [rbx+9Ah], 1
0x18001f992  mov     eax, edi
0x18001f994  jmp     short loc_18001F9E1
0x18001f996  cmp     byte ptr [rbx+98h], 0
0x18001f99d  jz      short loc_18001F9A6
0x18001f99f  mov     byte ptr [rbx+9Ah], 1
0x18001f9a6  xor     eax, eax
0x18001f9a8  jmp     short loc_18001F9E1
0x18001f9aa  mov     rcx, [rsp+48h]; this
0x18001f9af  mov     edi, 80070057h
0x18001f9b4  mov     r9d, edi; char *
0x18001f9b7  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001f9be  mov     edx, 8CFh; void *
0x18001f9c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9c8  nop
0x18001f9c9  cmp     byte ptr [rbx+98h], 0
0x18001f9d0  jz      short loc_18001F9D9
0x18001f9d2  mov     byte ptr [rbx+9Ah], 1
0x18001f9d9  mov     eax, edi
0x18001f9db  jmp     short loc_18001F9E1
0x18001f9dd  mov     eax, [rsp+48h+arg_0]
0x18001f9e1  mov     rbx, [rsp+48h+arg_8]
0x18001f9e6  mov     rsi, [rsp+48h+arg_10]
0x18001f9eb  add     rsp, 40h
0x18001f9ef  pop     rdi
0x18001f9f0  retn
```

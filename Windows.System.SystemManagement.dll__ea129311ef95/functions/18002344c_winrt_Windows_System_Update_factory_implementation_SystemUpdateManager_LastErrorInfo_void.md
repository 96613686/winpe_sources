# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastErrorInfo(void)

- ea: `0x18002344c`
- end: `0x1800235c1`
- name: `?LastErrorInfo@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AUSystemUpdateLastErrorInfo@3456@XZ`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800262e0`

## callees

- `0x180002dc0`
- `0x180002de4`
- `0x18001e5cc`
- `0x18001edd4`
- `0x180022a0c`
- `0x18002344c`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x1800234b7`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::LastErrorInfo(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        _QWORD *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // esi
  bool v7; // r14
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // r8
  _QWORD *result; // rax
  __int64 v13; // [rsp+28h] [rbp-50h] BYREF
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v14; // [rsp+30h] [rbp-48h]
  const wil::ResultException *v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    v14 = a1;
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v13);
    *((_DWORD *)a1 + 14) = 0;
    v16 = 0;
    v17 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v16);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v4,
        (int)a2);
    if ( (_DWORD)v16 )
    {
      switch ( (_DWORD)v16 )
      {
        case 1:
          v5 = 1;
          break;
        case 2:
          v5 = 3;
          break;
        case 3:
          v5 = 5;
          break;
        default:
          v5 = 2;
          if ( (_DWORD)v16 == 5 )
          {
            v5 = 8;
          }
          else if ( (_DWORD)v16 == 6 )
          {
            v5 = 9;
          }
          else if ( (_DWORD)v16 != 7 )
          {
            if ( (_DWORD)v16 == 8 )
            {
              v5 = 4;
            }
            else if ( (_DWORD)v16 == 10 )
            {
              v5 = 7;
            }
            else
            {
              v5 = 11;
            }
          }
          break;
      }
    }
    else
    {
      v5 = 0;
    }
    v6 = HIDWORD(v16);
    v7 = v17 != 0;
    operator new(0x28u);
    winrt::impl::producers_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,std::tuple<winrt::Windows::System::Update::SystemUpdateLastErrorInfo>>::producers_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,std::tuple<winrt::Windows::System::Update::SystemUpdateLastErrorInfo>>();
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v8 + 8);
    *(_DWORD *)(v9 + 24) = v5;
    *(_DWORD *)(v9 + 28) = v6;
    *(_BYTE *)(v9 + 32) = v7;
    *(_QWORD *)v9 = &winrt::impl::heap_implements<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo>::`vftable';
    *a2 = v10;
    if ( v13 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v13);
    result = a2;
  }
  catch ( const wil::ResultException *v15 )
  {
    *((_DWORD *)v14 + 14) = *((_DWORD *)v15 + 8);
    *a2 = 0;
    return a2;
  }
  catch ( ... )
  {
    *((_DWORD *)v14 + 14) = -2147467259;
    *a2 = 0;
    return a2;
  }
  return result;
}

```

## disassembly

```asm
0x18002344c  mov     [rsp+arg_10], rbx
0x180023451  push    rsi
0x180023452  push    rdi
0x180023453  push    r14
0x180023455  sub     rsp, 60h
0x180023459  mov     rax, cs:__security_cookie
0x180023460  xor     rax, rsp
0x180023463  mov     [rsp+78h+var_20], rax
0x180023468  mov     rdi, rdx
0x18002346b  mov     rbx, rcx
0x18002346e  mov     [rsp+78h+var_48], rcx
0x180023473  mov     qword ptr [rsp+78h+var_58], rdx; int
0x180023478  lea     rdx, [rsp+78h+var_50]
0x18002347d  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180023482  nop
0x180023483  mov     dword ptr [rbx+38h], 0
0x18002348a  xor     eax, eax
0x18002348c  mov     [rsp+78h+var_30], rax
0x180023491  mov     [rsp+78h+var_28], eax
0x180023495  mov     rcx, [rsp+78h+var_50]
0x18002349a  mov     rax, [rcx]
0x18002349d  lea     rdx, [rsp+78h+var_30]
0x1800234a2  mov     rax, [rax+28h]
0x1800234a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ab  mov     rcx, [rsp+78h]; this
0x1800234b0  test    eax, eax
0x1800234b2  jns     short loc_1800234C8
0x1800234b4  mov     r9d, eax; char *
0x1800234b7  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800234be  mov     edx, 18Ch; void *
0x1800234c3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800234c8  mov     ecx, dword ptr [rsp+78h+var_30]
0x1800234cc  test    ecx, ecx
0x1800234ce  jz      short loc_180023533
0x1800234d0  sub     ecx, 1
0x1800234d3  jz      short loc_18002352C
0x1800234d5  sub     ecx, 1
0x1800234d8  jz      short loc_180023525
0x1800234da  sub     ecx, 1
0x1800234dd  jz      short loc_18002351E
0x1800234df  mov     ebx, 2
0x1800234e4  sub     ecx, ebx
0x1800234e6  jz      short loc_180023517
0x1800234e8  sub     ecx, 1
0x1800234eb  jz      short loc_180023510
0x1800234ed  sub     ecx, 1
0x1800234f0  jz      short loc_180023535
0x1800234f2  sub     ecx, 1
0x1800234f5  jz      short loc_180023509
0x1800234f7  cmp     ecx, ebx
0x1800234f9  jz      short loc_180023502
0x1800234fb  mov     ebx, 0Bh
0x180023500  jmp     short loc_180023535
0x180023502  mov     ebx, 7
0x180023507  jmp     short loc_180023535
0x180023509  mov     ebx, 4
0x18002350e  jmp     short loc_180023535
0x180023510  mov     ebx, 9
0x180023515  jmp     short loc_180023535
0x180023517  mov     ebx, 8
0x18002351c  jmp     short loc_180023535
0x18002351e  mov     ebx, 5
0x180023523  jmp     short loc_180023535
0x180023525  mov     ebx, 3
0x18002352a  jmp     short loc_180023535
0x18002352c  mov     ebx, 1
0x180023531  jmp     short loc_180023535
0x180023533  xor     ebx, ebx
0x180023535  mov     esi, dword ptr [rsp+78h+var_30+4]
0x180023539  cmp     [rsp+78h+var_28], 0
0x18002353e  setnz   r14b
0x180023542  mov     ecx, 28h ; '('; Size
0x180023547  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002354c  mov     r9, rax
0x18002354f  lea     r8, [rax+10h]
0x180023553  mov     rcx, r8
0x180023556  call    ??0?$producers_base@USystemUpdateLastErrorInfo@implementation@Update@System@Windows@winrt@@V?$tuple@USystemUpdateLastErrorInfo@Update@System@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,std::tuple<winrt::Windows::System::Update::SystemUpdateLastErrorInfo>>::producers_base<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo,std::tuple<winrt::Windows::System::Update::SystemUpdateLastErrorInfo>>(void)
0x18002355b  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180023562  lea     rcx, [r9+8]
0x180023566  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18002356b  mov     [r9+18h], ebx
0x18002356f  mov     [r9+1Ch], esi
0x180023573  mov     [r9+20h], r14b
0x180023577  lea     rax, ??_7?$heap_implements@USystemUpdateLastErrorInfo@implementation@Update@System@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::System::Update::implementation::SystemUpdateLastErrorInfo>::`vftable'
0x18002357e  mov     [r9], rax
0x180023581  mov     [rdi], r8
0x180023584  cmp     [rsp+78h+var_50], 0
0x18002358a  jz      short loc_180023596
0x18002358c  lea     rcx, [rsp+78h+var_50]
0x180023591  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180023596  mov     rax, rdi
0x180023599  jmp     short loc_1800235A2
0x18002359b  jmp     short $+2
0x18002359d  mov     rax, qword ptr [rsp+78h+var_58]
0x1800235a2  mov     rcx, [rsp+78h+var_20]
0x1800235a7  xor     rcx, rsp; StackCookie
0x1800235aa  call    __security_check_cookie
0x1800235af  mov     rbx, [rsp+78h+arg_10]
0x1800235b7  add     rsp, 60h
0x1800235bb  pop     r14
0x1800235bd  pop     rdi
0x1800235be  pop     rsi
0x1800235bf  retn
```

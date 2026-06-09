# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::State(void)

- ea: `0x180024cd8`
- end: `0x180024ea5`
- name: `?State@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AW4SystemUpdateManagerState@3456@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800264c0`

## callees

- `0x180022a0c`
- `0x180024cd8`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x180024d1a`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x180024d79`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x180024df6`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::State(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1)
{
  int v2; // eax
  __int64 result; // rax
  int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  const wil::ResultException *v8; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int16 v11; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v7);
    v11 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v7 + 112LL))(v7, &v11);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v2,
        v7);
    if ( v11 == -1 )
    {
      if ( v7 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v7);
      result = 6;
    }
    else
    {
      v12 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 64LL))(v7, &v12);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
          (const char *)(unsigned int)v4,
          v7);
      if ( v12 == 11 )
      {
        if ( v7 )
          winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v7);
        result = 0;
      }
      else if ( v12 )
      {
        if ( v7 )
          winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v7);
        result = 10;
      }
      else
      {
        v13 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 32LL))(v7, &v13);
        if ( v5 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
            (const char *)(unsigned int)v5,
            v7);
        v6 = 0;
        if ( v13 > 6 )
        {
          switch ( v13 )
          {
            case 7:
              v6 = 2;
              break;
            case 8:
              v6 = 4;
              break;
            case 10:
              v6 = 7;
              break;
            case 11:
              v6 = 11;
              *((_DWORD *)a1 + 14) = -2147024726;
              break;
          }
        }
        else if ( v13 == 6 )
        {
          v6 = 9;
        }
        else if ( v13 )
        {
          switch ( v13 )
          {
            case 1:
              v6 = 1;
              break;
            case 2:
              v6 = 3;
              break;
            case 3:
              v6 = 5;
              break;
            case 5:
              v6 = 8;
              break;
          }
        }
        if ( v7 )
          winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v7);
        result = v6;
      }
    }
  }
  catch ( const wil::ResultException *v8 )
  {
    *((_DWORD *)a1 + 14) = *((_DWORD *)v8 + 8);
    return 11;
  }
  catch ( ... )
  {
    *((_DWORD *)a1 + 14) = -2147467259;
    return 11;
  }
  return result;
}

```

## disassembly

```asm
0x180024cd8  mov     [rsp+arg_0], rcx
0x180024cdd  push    rbx
0x180024cde  push    rdi
0x180024cdf  sub     rsp, 38h
0x180024ce3  mov     rdi, rcx
0x180024ce6  lea     rdx, [rsp+48h+var_28]
0x180024ceb  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180024cf0  nop
0x180024cf1  xor     eax, eax
0x180024cf3  mov     [rsp+48h+arg_8], ax
0x180024cf8  mov     rcx, [rsp+48h+var_28]
0x180024cfd  mov     rax, [rcx]
0x180024d00  lea     rdx, [rsp+48h+arg_8]
0x180024d05  mov     rax, [rax+70h]
0x180024d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d0e  mov     rcx, [rsp+48h]; this
0x180024d13  test    eax, eax
0x180024d15  jns     short loc_180024D2B
0x180024d17  mov     r9d, eax; char *
0x180024d1a  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024d21  mov     edx, 65h ; 'e'; void *
0x180024d26  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024d2b  cmp     [rsp+48h+arg_8], 0FFFFh
0x180024d31  jnz     short loc_180024D4F
0x180024d33  cmp     [rsp+48h+var_28], 0
0x180024d39  jz      short loc_180024D45
0x180024d3b  lea     rcx, [rsp+48h+var_28]
0x180024d40  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024d45  mov     eax, 6
0x180024d4a  jmp     loc_180024E9D
0x180024d4f  mov     [rsp+48h+arg_10], 0
0x180024d57  mov     rcx, [rsp+48h+var_28]
0x180024d5c  mov     rax, [rcx]
0x180024d5f  lea     rdx, [rsp+48h+arg_10]
0x180024d64  mov     rax, [rax+40h]
0x180024d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d6d  mov     rcx, [rsp+48h]; this
0x180024d72  test    eax, eax
0x180024d74  jns     short loc_180024D8A
0x180024d76  mov     r9d, eax; char *
0x180024d79  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024d80  mov     edx, 6Ch ; 'l'; void *
0x180024d85  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024d8a  mov     eax, [rsp+48h+arg_10]
0x180024d8e  cmp     eax, 0Bh
0x180024d91  jnz     short loc_180024DAC
0x180024d93  cmp     [rsp+48h+var_28], 0
0x180024d99  jz      short loc_180024DA5
0x180024d9b  lea     rcx, [rsp+48h+var_28]
0x180024da0  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024da5  xor     eax, eax
0x180024da7  jmp     loc_180024E9D
0x180024dac  test    eax, eax
0x180024dae  jz      short loc_180024DCC
0x180024db0  cmp     [rsp+48h+var_28], 0
0x180024db6  jz      short loc_180024DC2
0x180024db8  lea     rcx, [rsp+48h+var_28]
0x180024dbd  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024dc2  mov     eax, 0Ah
0x180024dc7  jmp     loc_180024E9D
0x180024dcc  mov     [rsp+48h+arg_18], 0
0x180024dd4  mov     rcx, [rsp+48h+var_28]
0x180024dd9  mov     rax, [rcx]
0x180024ddc  lea     rdx, [rsp+48h+arg_18]
0x180024de1  mov     rax, [rax+20h]
0x180024de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dea  mov     rcx, [rsp+48h]; this
0x180024def  test    eax, eax
0x180024df1  jns     short loc_180024E07
0x180024df3  mov     r9d, eax; char *
0x180024df6  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180024dfd  mov     edx, 7Ah ; 'z'; void *
0x180024e02  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024e07  xor     ebx, ebx
0x180024e09  mov     ecx, [rsp+48h+arg_18]
0x180024e0d  cmp     ecx, 6
0x180024e10  jg      short loc_180024E4D
0x180024e12  jz      short loc_180024E46
0x180024e14  test    ecx, ecx
0x180024e16  jz      short loc_180024E80
0x180024e18  sub     ecx, 1
0x180024e1b  jz      short loc_180024E3F
0x180024e1d  sub     ecx, 1
0x180024e20  jz      short loc_180024E38
0x180024e22  sub     ecx, 1
0x180024e25  jz      short loc_180024E31
0x180024e27  cmp     ecx, 2
0x180024e2a  jnz     short loc_180024E80
0x180024e2c  lea     ebx, [rcx+6]
0x180024e2f  jmp     short loc_180024E80
0x180024e31  mov     ebx, 5
0x180024e36  jmp     short loc_180024E80
0x180024e38  mov     ebx, 3
0x180024e3d  jmp     short loc_180024E80
0x180024e3f  mov     ebx, 1
0x180024e44  jmp     short loc_180024E80
0x180024e46  mov     ebx, 9
0x180024e4b  jmp     short loc_180024E80
0x180024e4d  sub     ecx, 7
0x180024e50  jz      short loc_180024E7B
0x180024e52  sub     ecx, 1
0x180024e55  jz      short loc_180024E74
0x180024e57  sub     ecx, 2
0x180024e5a  jz      short loc_180024E6D
0x180024e5c  cmp     ecx, 1
0x180024e5f  jnz     short loc_180024E80
0x180024e61  lea     ebx, [rcx+0Ah]
0x180024e64  mov     dword ptr [rdi+38h], 800700AAh
0x180024e6b  jmp     short loc_180024E80
0x180024e6d  mov     ebx, 7
0x180024e72  jmp     short loc_180024E80
0x180024e74  mov     ebx, 4
0x180024e79  jmp     short loc_180024E80
0x180024e7b  mov     ebx, 2
0x180024e80  cmp     [rsp+48h+var_28], 0
0x180024e86  jz      short loc_180024E92
0x180024e88  lea     rcx, [rsp+48h+var_28]
0x180024e8d  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180024e92  mov     eax, ebx
0x180024e94  jmp     short loc_180024E9D
0x180024e96  jmp     short $+2
0x180024e98  mov     eax, 0Bh
0x180024e9d  add     rsp, 38h
0x180024ea1  pop     rdi
0x180024ea2  pop     rbx
0x180024ea3  retn
```

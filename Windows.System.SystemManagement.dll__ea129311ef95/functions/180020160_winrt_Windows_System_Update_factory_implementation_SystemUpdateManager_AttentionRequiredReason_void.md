# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::AttentionRequiredReason(void)

- ea: `0x180020160`
- end: `0x180020222`
- name: `?AttentionRequiredReason@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AW4SystemUpdateAttentionRequiredReason@3456@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025dd0`

## callees

- `0x180020160`
- `0x180022a0c`
- `0x1800257a8`
- `0x1800271ac`
- `0x18002b010`

## string_xrefs

- `0x18002019f`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::AttentionRequiredReason(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 result; // rax
  const wil::ResultException *v4; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+48h] [rbp+10h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v8);
    v7 = 0;
    v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 64LL))(v8, &v7);
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x314,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v1,
        (int)v4);
    if ( v7 > 6 )
    {
      if ( v7 != 7 && v7 != 8 )
      {
        if ( v7 == 9 )
        {
          v2 = 4;
          goto LABEL_19;
        }
        goto LABEL_13;
      }
    }
    else if ( v7 != 6 )
    {
      if ( (unsigned int)v7 >= 2 )
      {
        if ( v7 == 2 || v7 == 3 || v7 == 4 )
        {
          v2 = 1;
          goto LABEL_19;
        }
        if ( v7 == 5 )
        {
          v2 = 2;
LABEL_19:
          if ( v8 )
            winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v8);
          return v2;
        }
      }
LABEL_13:
      v2 = 0;
      goto LABEL_19;
    }
    v2 = 3;
    goto LABEL_19;
  }
  catch ( const wil::ResultException *v4 )
  {
    *((_DWORD *)a1 + 14) = *((_DWORD *)v4 + 8);
    return 0;
  }
  catch ( ... )
  {
    *((_DWORD *)a1 + 14) = -2147467259;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180020160  mov     [rsp+arg_0], rcx
0x180020165  push    rbx
0x180020166  sub     rsp, 30h
0x18002016a  lea     rdx, [rsp+38h+arg_10]
0x18002016f  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180020174  nop
0x180020175  mov     [rsp+38h+arg_8], 0
0x18002017d  mov     rcx, [rsp+38h+arg_10]
0x180020182  mov     rax, [rcx]
0x180020185  lea     rdx, [rsp+38h+arg_8]
0x18002018a  mov     rax, [rax+40h]
0x18002018e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020193  mov     rcx, [rsp+38h]; this
0x180020198  test    eax, eax
0x18002019a  jns     short loc_1800201B0
0x18002019c  mov     r9d, eax; char *
0x18002019f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800201a6  mov     edx, 314h; void *
0x1800201ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800201b0  mov     ecx, [rsp+38h+arg_8]
0x1800201b4  cmp     ecx, 6
0x1800201b7  jg      short loc_1800201E8
0x1800201b9  jz      short loc_1800201FC
0x1800201bb  test    ecx, ecx
0x1800201bd  jz      short loc_1800201E4
0x1800201bf  sub     ecx, 1
0x1800201c2  jz      short loc_1800201E4
0x1800201c4  sub     ecx, 1
0x1800201c7  jz      short loc_1800201DD
0x1800201c9  sub     ecx, 1
0x1800201cc  jz      short loc_1800201DD
0x1800201ce  sub     ecx, 1
0x1800201d1  jz      short loc_1800201DD
0x1800201d3  cmp     ecx, 1
0x1800201d6  jnz     short loc_1800201E4
0x1800201d8  lea     ebx, [rcx+1]
0x1800201db  jmp     short loc_180020201
0x1800201dd  mov     ebx, 1
0x1800201e2  jmp     short loc_180020201
0x1800201e4  xor     ebx, ebx
0x1800201e6  jmp     short loc_180020201
0x1800201e8  sub     ecx, 7
0x1800201eb  jz      short loc_1800201FC
0x1800201ed  sub     ecx, 1
0x1800201f0  jz      short loc_1800201FC
0x1800201f2  sub     ecx, 1
0x1800201f5  jnz     short loc_1800201E4
0x1800201f7  lea     ebx, [rcx+4]
0x1800201fa  jmp     short loc_180020201
0x1800201fc  mov     ebx, 3
0x180020201  cmp     [rsp+38h+arg_10], 0
0x180020207  jz      short loc_180020213
0x180020209  lea     rcx, [rsp+38h+arg_10]
0x18002020e  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180020213  mov     eax, ebx
0x180020215  jmp     short loc_18002021B
0x180020217  jmp     short $+2
0x180020219  xor     eax, eax
0x18002021b  add     rsp, 30h
0x18002021f  pop     rbx
0x180020220  retn
```

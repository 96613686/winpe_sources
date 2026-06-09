# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180020cc8`
- end: `0x180020e96`
- name: `?ReadStringValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022d84`
- `0x1800252ec`

## callees

- `0x1800045b0`
- `0x1800166dc`
- `0x1800174f0`
- `0x1800175f4`
- `0x180020cc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020d32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020dfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020d32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020dfc`

## string_xrefs

- `0x180020d63`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x180020e11`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4)
{
  unsigned int ValueW; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rdx
  PVOID *v11; // rcx
  PVOID *pvData; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int pdwType; // [rsp+20h] [rbp-68h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-68h]
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  PVOID Src[2]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v19; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_OWORD *)Src = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v19 + 1) = 7;
  LOWORD(Src[0]) = 0;
  pcbData = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 2u, 0, 0, &pcbData);
  if ( ValueW - 2 > 1 )
  {
    if ( ValueW )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x193,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
             (const char *)ValueW,
             pdwType);
      std::wstring::_Tidy_deallocate(Src);
      return v9;
    }
    else
    {
      v10 = (unsigned __int64)pcbData >> 1;
      v11 = Src;
      if ( v10 > (unsigned __int64)v19 )
      {
        std::wstring::append(Src);
      }
      else
      {
        *(_QWORD *)&v19 = (unsigned __int64)pcbData >> 1;
        if ( *((_QWORD *)&v19 + 1) > 7u )
          v11 = (PVOID *)Src[0];
        *((_WORD *)v11 + v10) = 0;
      }
      pvData = Src;
      if ( *((_QWORD *)&v19 + 1) > 7u )
        pvData = (PVOID *)Src[0];
      v13 = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 2u, 0, pvData, &pcbData);
      if ( v13 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x196,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                (const char *)v13,
                pdwTypea);
        std::wstring::_Tidy_deallocate(Src);
        return v14;
      }
      else
      {
        if ( (PVOID *)a4 != Src )
        {
          std::wstring::_Tidy_deallocate(a4);
          *(_OWORD *)a4 = *(_OWORD *)Src;
          *(_OWORD *)(a4 + 16) = v19;
          *(_QWORD *)&v19 = 0;
          *((_QWORD *)&v19 + 1) = 7;
          LOWORD(Src[0]) = 0;
        }
        std::wstring::_Tidy_deallocate(Src);
        return 0;
      }
    }
  }
  else
  {
    std::wstring::_Tidy_deallocate(Src);
    return 2147943569LL;
  }
}

```

## disassembly

```asm
0x180020cc8  mov     r11, rsp
0x180020ccb  push    rbx
0x180020ccc  push    rsi
0x180020ccd  push    rdi
0x180020cce  sub     rsp, 70h
0x180020cd2  mov     rax, cs:__security_cookie
0x180020cd9  xor     rax, rsp
0x180020cdc  mov     [rsp+88h+var_20], rax
0x180020ce1  mov     rbx, r9
0x180020ce4  mov     rsi, r8
0x180020ce7  mov     rdi, rdx
0x180020cea  xorps   xmm0, xmm0
0x180020ced  movups  xmmword ptr [rsp+88h+Src], xmm0
0x180020cf2  mov     qword ptr [r11-30h], 0
0x180020cfa  mov     qword ptr [r11-28h], 7
0x180020d02  xor     eax, eax
0x180020d04  mov     word ptr [rsp+88h+Src], ax
0x180020d09  mov     [rsp+88h+var_48], eax
0x180020d0d  lea     rax, [r11-48h]
0x180020d11  mov     [r11-58h], rax
0x180020d15  mov     qword ptr [r11-60h], 0
0x180020d1d  mov     qword ptr [r11-68h], 0
0x180020d25  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180020d2c  mov     r9d, 2; dwFlags
0x180020d32  call    cs:__imp_RegGetValueW
0x180020d38  lea     ecx, [rax-2]
0x180020d3b  cmp     ecx, 1
0x180020d3e  ja      short loc_180020D54
0x180020d40  lea     rcx, [rsp+88h+Src]
0x180020d45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020d4a  mov     eax, 80070491h
0x180020d4f  jmp     loc_180020E80
0x180020d54  test    eax, eax
0x180020d56  jz      short loc_180020D87
0x180020d58  mov     rcx, [rsp+88h]; this
0x180020d60  mov     r9d, eax; char *
0x180020d63  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020d6a  mov     edx, 193h; void *
0x180020d6f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020d74  mov     ebx, eax
0x180020d76  lea     rcx, [rsp+88h+Src]
0x180020d7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020d80  mov     eax, ebx
0x180020d82  jmp     loc_180020E80
0x180020d87  mov     edx, [rsp+88h+var_48]
0x180020d8b  shr     rdx, 1
0x180020d8e  lea     rcx, [rsp+88h+Src]; Src
0x180020d93  cmp     rdx, qword ptr [rsp+88h+var_30]
0x180020d98  ja      short loc_180020DB3
0x180020d9a  mov     qword ptr [rsp+88h+var_30], rdx
0x180020d9f  cmp     qword ptr [rsp+88h+var_30+8], 7
0x180020da5  cmova   rcx, [rsp+88h+Src]
0x180020dab  xor     eax, eax
0x180020dad  mov     [rcx+rdx*2], ax
0x180020db1  jmp     short loc_180020DC0
0x180020db3  xor     r8d, r8d
0x180020db6  sub     rdx, qword ptr [rsp+88h+var_30]
0x180020dbb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180020dc0  lea     rax, [rsp+88h+Src]
0x180020dc5  cmp     qword ptr [rsp+88h+var_30+8], 7
0x180020dcb  cmova   rax, [rsp+88h+Src]
0x180020dd1  lea     rdx, [rsp+88h+var_48]
0x180020dd6  mov     [rsp+88h+pcbData], rdx; pcbData
0x180020ddb  mov     [rsp+88h+pvData], rax; pvData
0x180020de0  mov     [rsp+88h+pdwType], 0; unsigned int
0x180020de9  mov     r9d, 2; dwFlags
0x180020def  mov     r8, rsi; lpValue
0x180020df2  mov     rdx, rdi; lpSubKey
0x180020df5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180020dfc  call    cs:__imp_RegGetValueW
0x180020e02  test    eax, eax
0x180020e04  jz      short loc_180020E32
0x180020e06  mov     rcx, [rsp+88h]; this
0x180020e0e  mov     r9d, eax; char *
0x180020e11  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020e18  mov     edx, 196h; void *
0x180020e1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020e22  mov     ebx, eax
0x180020e24  lea     rcx, [rsp+88h+Src]
0x180020e29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e2e  mov     eax, ebx
0x180020e30  jmp     short loc_180020E80
0x180020e32  lea     rax, [rsp+88h+Src]
0x180020e37  cmp     rbx, rax
0x180020e3a  jz      short loc_180020E6E
0x180020e3c  mov     rcx, rbx
0x180020e3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e44  movups  xmm0, xmmword ptr [rsp+88h+Src]
0x180020e49  movups  xmmword ptr [rbx], xmm0
0x180020e4c  movups  xmm1, [rsp+88h+var_30]
0x180020e51  movups  xmmword ptr [rbx+10h], xmm1
0x180020e55  mov     qword ptr [rsp+88h+var_30], 0
0x180020e5e  mov     qword ptr [rsp+88h+var_30+8], 7
0x180020e67  xor     eax, eax
0x180020e69  mov     word ptr [rsp+88h+Src], ax
0x180020e6e  lea     rcx, [rsp+88h+Src]
0x180020e73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020e78  xor     eax, eax
0x180020e7a  jmp     short loc_180020E80
0x180020e7c  mov     eax, [rsp+88h+var_48]
0x180020e80  mov     rcx, [rsp+88h+var_20]
0x180020e85  xor     rcx, rsp; StackCookie
0x180020e88  call    __security_check_cookie
0x180020e8d  add     rsp, 70h
0x180020e91  pop     rdi
0x180020e92  pop     rsi
0x180020e93  pop     rbx
0x180020e94  retn
```

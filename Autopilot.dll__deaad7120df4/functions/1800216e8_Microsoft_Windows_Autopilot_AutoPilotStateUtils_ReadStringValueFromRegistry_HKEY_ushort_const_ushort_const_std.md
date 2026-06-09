# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800216e8`
- end: `0x1800218c2`
- name: `?ReadStringValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800238cc`
- `0x1800260b8`

## callees

- `0x1800045d0`
- `0x180016b80`
- `0x180017a20`
- `0x180017b2c`
- `0x1800216e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021752`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021822`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021752`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021822`

## string_xrefs

- `0x180021789`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18002183d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
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
      std::wstring::_Tidy_deallocate((char **)Src);
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
        std::wstring::_Tidy_deallocate((char **)Src);
        return v14;
      }
      else
      {
        if ( (PVOID *)a4 != Src )
        {
          std::wstring::_Tidy_deallocate((char **)a4);
          *(_OWORD *)a4 = *(_OWORD *)Src;
          *(_OWORD *)(a4 + 16) = v19;
          *(_QWORD *)&v19 = 0;
          *((_QWORD *)&v19 + 1) = 7;
          LOWORD(Src[0]) = 0;
        }
        std::wstring::_Tidy_deallocate((char **)Src);
        return 0;
      }
    }
  }
  else
  {
    std::wstring::_Tidy_deallocate((char **)Src);
    return 2147943569LL;
  }
}

```

## disassembly

```asm
0x1800216e8  mov     r11, rsp
0x1800216eb  push    rbx
0x1800216ec  push    rsi
0x1800216ed  push    rdi
0x1800216ee  sub     rsp, 70h
0x1800216f2  mov     rax, cs:__security_cookie
0x1800216f9  xor     rax, rsp
0x1800216fc  mov     [rsp+88h+var_20], rax
0x180021701  mov     rbx, r9
0x180021704  mov     rsi, r8
0x180021707  mov     rdi, rdx
0x18002170a  xorps   xmm0, xmm0
0x18002170d  movups  xmmword ptr [rsp+88h+Src], xmm0
0x180021712  mov     qword ptr [r11-30h], 0
0x18002171a  mov     qword ptr [r11-28h], 7
0x180021722  xor     eax, eax
0x180021724  mov     word ptr [rsp+88h+Src], ax
0x180021729  mov     [rsp+88h+var_48], eax
0x18002172d  lea     rax, [r11-48h]
0x180021731  mov     [r11-58h], rax
0x180021735  mov     qword ptr [r11-60h], 0
0x18002173d  mov     qword ptr [r11-68h], 0
0x180021745  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002174c  mov     r9d, 2; dwFlags
0x180021752  call    cs:__imp_RegGetValueW
0x180021759  nop     dword ptr [rax+rax+00h]
0x18002175e  lea     ecx, [rax-2]
0x180021761  cmp     ecx, 1
0x180021764  ja      short loc_18002177A
0x180021766  lea     rcx, [rsp+88h+Src]
0x18002176b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021770  mov     eax, 80070491h
0x180021775  jmp     loc_1800218AC
0x18002177a  test    eax, eax
0x18002177c  jz      short loc_1800217AD
0x18002177e  mov     rcx, [rsp+88h]; this
0x180021786  mov     r9d, eax; char *
0x180021789  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021790  mov     edx, 193h; void *
0x180021795  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002179a  mov     ebx, eax
0x18002179c  lea     rcx, [rsp+88h+Src]
0x1800217a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800217a6  mov     eax, ebx
0x1800217a8  jmp     loc_1800218AC
0x1800217ad  mov     edx, [rsp+88h+var_48]
0x1800217b1  shr     rdx, 1
0x1800217b4  lea     rcx, [rsp+88h+Src]; Src
0x1800217b9  cmp     rdx, qword ptr [rsp+88h+var_30]
0x1800217be  ja      short loc_1800217D9
0x1800217c0  mov     qword ptr [rsp+88h+var_30], rdx
0x1800217c5  cmp     qword ptr [rsp+88h+var_30+8], 7
0x1800217cb  cmova   rcx, [rsp+88h+Src]
0x1800217d1  xor     eax, eax
0x1800217d3  mov     [rcx+rdx*2], ax
0x1800217d7  jmp     short loc_1800217E6
0x1800217d9  xor     r8d, r8d
0x1800217dc  sub     rdx, qword ptr [rsp+88h+var_30]
0x1800217e1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800217e6  lea     rax, [rsp+88h+Src]
0x1800217eb  cmp     qword ptr [rsp+88h+var_30+8], 7
0x1800217f1  cmova   rax, [rsp+88h+Src]
0x1800217f7  lea     rdx, [rsp+88h+var_48]
0x1800217fc  mov     [rsp+88h+pcbData], rdx; pcbData
0x180021801  mov     [rsp+88h+pvData], rax; pvData
0x180021806  mov     [rsp+88h+pdwType], 0; unsigned int
0x18002180f  mov     r9d, 2; dwFlags
0x180021815  mov     r8, rsi; lpValue
0x180021818  mov     rdx, rdi; lpSubKey
0x18002181b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180021822  call    cs:__imp_RegGetValueW
0x180021829  nop     dword ptr [rax+rax+00h]
0x18002182e  test    eax, eax
0x180021830  jz      short loc_18002185E
0x180021832  mov     rcx, [rsp+88h]; this
0x18002183a  mov     r9d, eax; char *
0x18002183d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021844  mov     edx, 196h; void *
0x180021849  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002184e  mov     ebx, eax
0x180021850  lea     rcx, [rsp+88h+Src]
0x180021855  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002185a  mov     eax, ebx
0x18002185c  jmp     short loc_1800218AC
0x18002185e  lea     rax, [rsp+88h+Src]
0x180021863  cmp     rbx, rax
0x180021866  jz      short loc_18002189A
0x180021868  mov     rcx, rbx
0x18002186b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021870  movups  xmm0, xmmword ptr [rsp+88h+Src]
0x180021875  movups  xmmword ptr [rbx], xmm0
0x180021878  movups  xmm1, [rsp+88h+var_30]
0x18002187d  movups  xmmword ptr [rbx+10h], xmm1
0x180021881  mov     qword ptr [rsp+88h+var_30], 0
0x18002188a  mov     qword ptr [rsp+88h+var_30+8], 7
0x180021893  xor     eax, eax
0x180021895  mov     word ptr [rsp+88h+Src], ax
0x18002189a  lea     rcx, [rsp+88h+Src]
0x18002189f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800218a4  xor     eax, eax
0x1800218a6  jmp     short loc_1800218AC
0x1800218a8  mov     eax, [rsp+88h+var_48]
0x1800218ac  mov     rcx, [rsp+88h+var_20]
0x1800218b1  xor     rcx, rsp; StackCookie
0x1800218b4  call    __security_check_cookie
0x1800218b9  add     rsp, 70h
0x1800218bd  pop     rdi
0x1800218be  pop     rsi
0x1800218bf  pop     rbx
0x1800218c0  retn
```

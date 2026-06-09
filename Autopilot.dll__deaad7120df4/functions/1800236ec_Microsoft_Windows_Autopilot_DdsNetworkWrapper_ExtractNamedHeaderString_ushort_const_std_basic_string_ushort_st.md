# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800236ec`
- end: `0x1800238c4`
- name: `?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `472`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025f90`

## callees

- `0x180004a08`
- `0x1800097f0`
- `0x1800098e7`
- `0x180010744`
- `0x180010764`
- `0x1800192a4`
- `0x1800236ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002375f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002375f`
- `WINHTTP!WinHttpQueryHeaders` at `0x18002372a`
- `WINHTTP!WinHttpQueryHeaders` at `0x180023801`
- `WINHTTP!WinHttpQueryHeaders` at `0x18002372a`
- `WINHTTP!WinHttpQueryHeaders` at `0x180023801`

## string_xrefs

- `0x180023747`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002378b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023816`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023898`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdi
  _WORD *v12; // rbx
  __int64 v13; // r8
  const char *v14; // r9
  unsigned int v15; // edi
  const char *v16; // r9
  char *v17; // r14
  size_t v18; // rdi
  int lpdwBufferLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD dwBufferLength; // [rsp+60h] [rbp+8h] BYREF
  _WORD *v22; // [rsp+78h] [rbp+20h]

  dwBufferLength = 0;
  if ( WinHttpQueryHeaders(*(HINTERNET *)(a1 + 80), 0xFFFFu, a2, 0, &dwBufferLength, 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)0x8000FFFFLL,
      lpdwBufferLength);
    return 2147549183LL;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 122 )
    {
      if ( dwBufferLength < 2 || (dwBufferLength & 1) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27C,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)0x8000FFFFLL,
          lpdwBufferLength);
        return 2147549183LL;
      }
      else
      {
        v22 = 0;
        v9 = (unsigned __int64)dwBufferLength >> 1;
        v10 = 2 * v9;
        v11 = -1;
        if ( !is_mul_ok(v9, 2u) )
          v10 = -1;
        try
        {
          v12 = operator new[](v10);
          v22 = v12;
          if ( WinHttpQueryHeaders(*(HINTERNET *)(a1 + 80), 0xFFFFu, a2, v12, &dwBufferLength, 0) )
          {
            do
              ++v11;
            while ( v12[v11] );
            if ( v11 > *(_QWORD *)(a3 + 24) )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                (char **)a3,
                v11,
                v13,
                v12);
            }
            else
            {
              if ( *(_QWORD *)(a3 + 24) <= 7u )
                v17 = (char *)a3;
              else
                v17 = *(char **)a3;
              *(_QWORD *)(a3 + 16) = v11;
              v18 = 2 * v11;
              memmove_0(v17, v12, v18);
              *(_WORD *)&v17[v18] = 0;
            }
            operator delete(v12);
            result = 0;
          }
          else
          {
            v15 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x287,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    v14);
            operator delete(v12);
            result = v15;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x28D,
                                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                                 v16);
        }
      }
    }
    else
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)v8,
          lpdwBufferLength);
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800236ec  mov     r11, rsp
0x1800236ef  mov     [r11+10h], rbx
0x1800236f3  push    rsi
0x1800236f4  push    rdi
0x1800236f5  push    r12
0x1800236f7  push    r14
0x1800236f9  push    r15
0x1800236fb  sub     rsp, 30h
0x1800236ff  mov     rsi, r8
0x180023702  mov     r14, rdx
0x180023705  mov     r15, rcx
0x180023708  xor     r12d, r12d
0x18002370b  mov     [r11+8], r12d
0x18002370f  mov     [r11-30h], r12
0x180023713  lea     rax, [r11+8]
0x180023717  mov     [r11-38h], rax
0x18002371b  xor     r9d, r9d; lpBuffer
0x18002371e  mov     r8, rdx; pwszName
0x180023721  mov     edx, 0FFFFh; dwInfoLevel
0x180023726  mov     rcx, [rcx+50h]; hRequest
0x18002372a  call    cs:__imp_WinHttpQueryHeaders
0x180023731  nop     dword ptr [rax+rax+00h]
0x180023736  test    eax, eax
0x180023738  jz      short loc_18002375F
0x18002373a  mov     rcx, [rsp+58h]; this
0x18002373f  mov     ebx, 8000FFFFh
0x180023744  mov     r9d, ebx; char *
0x180023747  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002374e  mov     edx, 278h; void *
0x180023753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023758  mov     eax, ebx
0x18002375a  jmp     loc_1800238B1
0x18002375f  call    cs:__imp_GetLastError
0x180023766  nop     dword ptr [rax+rax+00h]
0x18002376b  mov     ebx, eax
0x18002376d  cmp     eax, 7Ah ; 'z'
0x180023770  jz      short loc_1800237A3
0x180023772  test    eax, eax
0x180023774  jle     short loc_18002377F
0x180023776  movzx   ebx, ax
0x180023779  or      ebx, 80070000h
0x18002377f  test    ebx, ebx
0x180023781  jns     short loc_18002379C
0x180023783  mov     rcx, [rsp+58h]; this
0x180023788  mov     r9d, ebx; char *
0x18002378b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023792  mov     edx, 27Ah; void *
0x180023797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002379c  mov     eax, ebx
0x18002379e  jmp     loc_1800238B1
0x1800237a3  mov     ecx, [rsp+58h+dwBufferLength]
0x1800237a7  mov     eax, 2
0x1800237ac  cmp     ecx, eax
0x1800237ae  jb      loc_18002388B
0x1800237b4  test    cl, 1
0x1800237b7  jnz     loc_18002388B
0x1800237bd  mov     [rsp+58h+arg_18], r12
0x1800237c2  shr     rcx, 1
0x1800237c5  mul     rcx
0x1800237c8  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800237cf  cmovb   rax, rdi
0x1800237d3  mov     rcx, rax; unsigned __int64
0x1800237d6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800237db  mov     rbx, rax
0x1800237de  mov     [rsp+58h+arg_18], rax
0x1800237e3  mov     [rsp+58h+lpdwIndex], r12; lpdwIndex
0x1800237e8  lea     rax, [rsp+58h+dwBufferLength]
0x1800237ed  mov     [rsp+58h+lpdwBufferLength], rax; lpdwBufferLength
0x1800237f2  mov     r9, rbx; lpBuffer
0x1800237f5  mov     r8, r14; pwszName
0x1800237f8  mov     edx, 0FFFFh; dwInfoLevel
0x1800237fd  mov     rcx, [r15+50h]; hRequest
0x180023801  call    cs:__imp_WinHttpQueryHeaders
0x180023808  nop     dword ptr [rax+rax+00h]
0x18002380d  test    eax, eax
0x18002380f  jnz     short loc_180023835
0x180023811  mov     rcx, [rsp+58h]; this
0x180023816  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002381d  mov     edx, 287h; void *
0x180023822  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023827  mov     edi, eax
0x180023829  mov     rcx, rbx; void *
0x18002382c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023831  mov     eax, edi
0x180023833  jmp     short loc_1800238B1
0x180023835  inc     rdi
0x180023838  cmp     [rbx+rdi*2], r12w
0x18002383d  jnz     short loc_180023835
0x18002383f  cmp     rdi, [rsi+18h]
0x180023843  ja      short loc_180023870
0x180023845  cmp     qword ptr [rsi+18h], 7
0x18002384a  jbe     short loc_180023851
0x18002384c  mov     r14, [rsi]
0x18002384f  jmp     short loc_180023854
0x180023851  mov     r14, rsi
0x180023854  mov     [rsi+10h], rdi
0x180023858  add     rdi, rdi
0x18002385b  mov     r8, rdi; Size
0x18002385e  mov     rdx, rbx; Src
0x180023861  mov     rcx, r14; void *
0x180023864  call    memmove_0
0x180023869  mov     [rdi+r14], r12w
0x18002386e  jmp     short loc_18002387F
0x180023870  mov     r9, rbx
0x180023873  mov     rdx, rdi
0x180023876  mov     rcx, rsi
0x180023879  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002387e  nop
0x18002387f  mov     rcx, rbx; void *
0x180023882  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023887  xor     eax, eax
0x180023889  jmp     short loc_1800238B1
0x18002388b  mov     rcx, [rsp+58h]; this
0x180023890  mov     ebx, 8000FFFFh
0x180023895  mov     r9d, ebx; char *
0x180023898  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002389f  mov     edx, 27Ch; void *
0x1800238a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238a9  mov     eax, ebx
0x1800238ab  jmp     short loc_1800238B1
0x1800238ad  mov     eax, [rsp+58h+dwBufferLength]
0x1800238b1  mov     rbx, [rsp+58h+arg_8]
0x1800238b6  add     rsp, 30h
0x1800238ba  pop     r15
0x1800238bc  pop     r14
0x1800238be  pop     r12
0x1800238c0  pop     rdi
0x1800238c1  pop     rsi
0x1800238c2  retn
```

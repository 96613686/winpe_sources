# Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180022bb8`
- end: `0x180022d7e`
- name: `?ExtractNamedHeaderString@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800251d0`

## callees

- `0x1800049f4`
- `0x180009860`
- `0x180009957`
- `0x1800105d4`
- `0x1800105f4`
- `0x180018cd0`
- `0x180022bb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c25`
- `WINHTTP!WinHttpQueryHeaders` at `0x180022bf6`
- `WINHTTP!WinHttpQueryHeaders` at `0x180022cc1`
- `WINHTTP!WinHttpQueryHeaders` at `0x180022bf6`
- `WINHTTP!WinHttpQueryHeaders` at `0x180022cc1`

## string_xrefs

- `0x180022c0d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180022c4b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180022cd0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180022d52`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString(
        __int64 a1,
        const WCHAR *a2,
        char **a3)
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
            if ( v11 > (unsigned __int64)a3[3] )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                a3,
                v11,
                v13,
                v12);
            }
            else
            {
              if ( (unsigned __int64)a3[3] <= 7 )
                v17 = (char *)a3;
              else
                v17 = *a3;
              a3[2] = (char *)v11;
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
0x180022bb8  mov     r11, rsp
0x180022bbb  mov     [r11+10h], rbx
0x180022bbf  push    rsi
0x180022bc0  push    rdi
0x180022bc1  push    r12
0x180022bc3  push    r14
0x180022bc5  push    r15
0x180022bc7  sub     rsp, 30h
0x180022bcb  mov     rsi, r8
0x180022bce  mov     r14, rdx
0x180022bd1  mov     r15, rcx
0x180022bd4  xor     r12d, r12d
0x180022bd7  mov     [r11+8], r12d
0x180022bdb  mov     [r11-30h], r12
0x180022bdf  lea     rax, [r11+8]
0x180022be3  mov     [r11-38h], rax
0x180022be7  xor     r9d, r9d; lpBuffer
0x180022bea  mov     r8, rdx; pwszName
0x180022bed  mov     edx, 0FFFFh; dwInfoLevel
0x180022bf2  mov     rcx, [rcx+50h]; hRequest
0x180022bf6  call    cs:__imp_WinHttpQueryHeaders
0x180022bfc  test    eax, eax
0x180022bfe  jz      short loc_180022C25
0x180022c00  mov     rcx, [rsp+58h]; this
0x180022c05  mov     ebx, 8000FFFFh
0x180022c0a  mov     r9d, ebx; char *
0x180022c0d  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022c14  mov     edx, 278h; void *
0x180022c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c1e  mov     eax, ebx
0x180022c20  jmp     loc_180022D6B
0x180022c25  call    cs:__imp_GetLastError
0x180022c2b  mov     ebx, eax
0x180022c2d  cmp     eax, 7Ah ; 'z'
0x180022c30  jz      short loc_180022C63
0x180022c32  test    eax, eax
0x180022c34  jle     short loc_180022C3F
0x180022c36  movzx   ebx, ax
0x180022c39  or      ebx, 80070000h
0x180022c3f  test    ebx, ebx
0x180022c41  jns     short loc_180022C5C
0x180022c43  mov     rcx, [rsp+58h]; this
0x180022c48  mov     r9d, ebx; char *
0x180022c4b  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022c52  mov     edx, 27Ah; void *
0x180022c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c5c  mov     eax, ebx
0x180022c5e  jmp     loc_180022D6B
0x180022c63  mov     ecx, [rsp+58h+dwBufferLength]
0x180022c67  mov     eax, 2
0x180022c6c  cmp     ecx, eax
0x180022c6e  jb      loc_180022D45
0x180022c74  test    cl, 1
0x180022c77  jnz     loc_180022D45
0x180022c7d  mov     [rsp+58h+arg_18], r12
0x180022c82  shr     rcx, 1
0x180022c85  mul     rcx
0x180022c88  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180022c8f  cmovb   rax, rdi
0x180022c93  mov     rcx, rax; unsigned __int64
0x180022c96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180022c9b  mov     rbx, rax
0x180022c9e  mov     [rsp+58h+arg_18], rax
0x180022ca3  mov     [rsp+58h+lpdwIndex], r12; lpdwIndex
0x180022ca8  lea     rax, [rsp+58h+dwBufferLength]
0x180022cad  mov     [rsp+58h+lpdwBufferLength], rax; lpdwBufferLength
0x180022cb2  mov     r9, rbx; lpBuffer
0x180022cb5  mov     r8, r14; pwszName
0x180022cb8  mov     edx, 0FFFFh; dwInfoLevel
0x180022cbd  mov     rcx, [r15+50h]; hRequest
0x180022cc1  call    cs:__imp_WinHttpQueryHeaders
0x180022cc7  test    eax, eax
0x180022cc9  jnz     short loc_180022CEF
0x180022ccb  mov     rcx, [rsp+58h]; this
0x180022cd0  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022cd7  mov     edx, 287h; void *
0x180022cdc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022ce1  mov     edi, eax
0x180022ce3  mov     rcx, rbx; Block
0x180022ce6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022ceb  mov     eax, edi
0x180022ced  jmp     short loc_180022D6B
0x180022cef  inc     rdi
0x180022cf2  cmp     [rbx+rdi*2], r12w
0x180022cf7  jnz     short loc_180022CEF
0x180022cf9  cmp     rdi, [rsi+18h]
0x180022cfd  ja      short loc_180022D2A
0x180022cff  cmp     qword ptr [rsi+18h], 7
0x180022d04  jbe     short loc_180022D0B
0x180022d06  mov     r14, [rsi]
0x180022d09  jmp     short loc_180022D0E
0x180022d0b  mov     r14, rsi
0x180022d0e  mov     [rsi+10h], rdi
0x180022d12  add     rdi, rdi
0x180022d15  mov     r8, rdi; Size
0x180022d18  mov     rdx, rbx; Src
0x180022d1b  mov     rcx, r14; void *
0x180022d1e  call    memmove_0
0x180022d23  mov     [rdi+r14], r12w
0x180022d28  jmp     short loc_180022D39
0x180022d2a  mov     r9, rbx
0x180022d2d  mov     rdx, rdi
0x180022d30  mov     rcx, rsi
0x180022d33  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180022d38  nop
0x180022d39  mov     rcx, rbx; Block
0x180022d3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d41  xor     eax, eax
0x180022d43  jmp     short loc_180022D6B
0x180022d45  mov     rcx, [rsp+58h]; this
0x180022d4a  mov     ebx, 8000FFFFh
0x180022d4f  mov     r9d, ebx; char *
0x180022d52  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022d59  mov     edx, 27Ch; void *
0x180022d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d63  mov     eax, ebx
0x180022d65  jmp     short loc_180022D6B
0x180022d67  mov     eax, [rsp+58h+dwBufferLength]
0x180022d6b  mov     rbx, [rsp+58h+arg_8]
0x180022d70  add     rsp, 30h
0x180022d74  pop     r15
0x180022d76  pop     r14
0x180022d78  pop     r12
0x180022d7a  pop     rdi
0x180022d7b  pop     rsi
0x180022d7c  retn
```

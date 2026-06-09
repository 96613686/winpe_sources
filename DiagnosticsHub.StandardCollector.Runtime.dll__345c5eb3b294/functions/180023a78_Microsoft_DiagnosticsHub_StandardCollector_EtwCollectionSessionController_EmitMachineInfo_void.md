# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(void)

- ea: `0x180023a78`
- end: `0x180023bae`
- name: `?EmitMachineInfo@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b320`
- `0x18001c3b0`

## callees

- `0x180002604`
- `0x18000a2d0`
- `0x18001c7a0`
- `0x180023a78`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180023aae`
- `KERNEL32!GetComputerNameExW` at `0x180023ad5`
- `KERNEL32!GetComputerNameExW` at `0x180023aae`
- `KERNEL32!GetComputerNameExW` at `0x180023ad5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023b81`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180023b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x180023b4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x180023b4f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180023af8`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180023af8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this)
{
  unsigned int v2; // edi
  OLECHAR *v3; // rbx
  int v4; // eax
  int v5; // eax
  OLECHAR *v7; // [rsp+20h] [rbp-40h] BYREF
  DWORD nSize; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v9[3]; // [rsp+30h] [rbp-30h] BYREF
  int v10; // [rsp+48h] [rbp-18h]

  v2 = 0;
  nSize = 0;
  GetComputerNameExW(ComputerNamePhysicalDnsHostname, 0, &nSize);
  if ( (nSize & 0x80000000) != 0 )
    ATL::AtlThrowImpl(-2147024809);
  if ( nSize )
  {
    _mm_lfence();
    v3 = SysAllocStringLen(0, nSize);
    v7 = v3;
    if ( !v3 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v3 = 0;
    v7 = 0;
  }
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, v3, &nSize) || !nSize )
  {
    SysFreeString(v3);
    v7 = 0;
    v4 = wcslen(L"Unknown");
    v5 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v7, L"Unknown", v4);
    v3 = v7;
    if ( v5 < 0 )
      goto LABEL_8;
  }
  v9[0] = &Microsoft::DiagnosticsHub::StandardCollector::MachineInfoEvent::`vftable';
  v9[1] = v3;
  v9[2] = L"Windows (64-bit)";
  v10 = 1;
  v5 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::InjectArtificialEvent(
         this,
         (const struct Microsoft::DiagnosticsHub::StandardCollector::ArtificialEvent *)v9);
  if ( v5 < 0 )
LABEL_8:
    v2 = v5;
  SysFreeString(v3);
  return v2;
}

```

## disassembly

```asm
0x180023a78  mov     [rsp-8+arg_8], rbx
0x180023a7d  mov     [rsp-8+arg_10], rsi
0x180023a82  mov     [rsp-8+arg_18], rdi
0x180023a87  push    rbp
0x180023a88  mov     rbp, rsp
0x180023a8b  sub     rsp, 60h
0x180023a8f  mov     rax, cs:__security_cookie
0x180023a96  xor     rax, rsp
0x180023a99  mov     [rbp+var_10], rax
0x180023a9d  mov     rsi, rcx
0x180023aa0  xor     edi, edi
0x180023aa2  mov     [rbp+nSize], edi
0x180023aa5  lea     r8, [rbp+nSize]; nSize
0x180023aa9  xor     edx, edx; lpBuffer
0x180023aab  lea     ecx, [rdi+5]; NameType
0x180023aae  call    cs:__imp_GetComputerNameExW
0x180023ab4  cmp     [rbp+nSize], edi
0x180023ab7  jl      loc_180023B98
0x180023abd  jnz     loc_180023B79
0x180023ac3  mov     ebx, edi
0x180023ac5  mov     [rbp+var_40], rbx
0x180023ac9  lea     r8, [rbp+nSize]; nSize
0x180023acd  mov     rdx, rbx; lpBuffer
0x180023ad0  mov     ecx, 5; NameType
0x180023ad5  call    cs:__imp_GetComputerNameExW
0x180023adb  test    eax, eax
0x180023add  jz      short loc_180023AE4
0x180023adf  cmp     [rbp+nSize], edi
0x180023ae2  jnz     short loc_180023B19
0x180023ae4  mov     rcx, rbx; bstrString
0x180023ae7  call    cs:__imp_SysFreeString
0x180023aed  mov     [rbp+var_40], rdi
0x180023af1  lea     rcx, aUnknown; "Unknown"
0x180023af8  call    cs:__imp_wcslen
0x180023afe  mov     r8d, eax; int
0x180023b01  lea     rdx, aUnknown; "Unknown"
0x180023b08  lea     rcx, [rbp+var_40]; this
0x180023b0c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180023b11  mov     rbx, [rbp+var_40]
0x180023b15  test    eax, eax
0x180023b17  js      short loc_180023B4A
0x180023b19  lea     rax, ??_7MachineInfoEvent@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::MachineInfoEvent::`vftable'
0x180023b20  mov     [rbp+var_30], rax
0x180023b24  mov     [rbp+var_28], rbx
0x180023b28  lea     rax, aWindows64Bit; "Windows (64-bit)"
0x180023b2f  mov     [rbp+var_20], rax
0x180023b33  mov     [rbp+var_18], 1
0x180023b3a  lea     rdx, [rbp+var_30]; struct Microsoft::DiagnosticsHub::StandardCollector::ArtificialEvent *
0x180023b3e  mov     rcx, rsi; this
0x180023b41  call    ?InjectArtificialEvent@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJAEBVArtificialEvent@234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::InjectArtificialEvent(Microsoft::DiagnosticsHub::StandardCollector::ArtificialEvent const &)
0x180023b46  test    eax, eax
0x180023b48  jns     short loc_180023B4C
0x180023b4a  mov     edi, eax
0x180023b4c  mov     rcx, rbx; bstrString
0x180023b4f  call    cs:__imp_SysFreeString
0x180023b55  mov     eax, edi
0x180023b57  mov     rcx, [rbp+var_10]
0x180023b5b  xor     rcx, rsp; StackCookie
0x180023b5e  call    __security_check_cookie
0x180023b63  lea     r11, [rsp+60h+var_s0]
0x180023b68  mov     rbx, [r11+18h]
0x180023b6c  mov     rsi, [r11+20h]
0x180023b70  mov     rdi, [r11+28h]
0x180023b74  mov     rsp, r11
0x180023b77  pop     rbp
0x180023b78  retn
0x180023b79  lfence
0x180023b7c  mov     edx, [rbp+nSize]; ui
0x180023b7f  xor     ecx, ecx; strIn
0x180023b81  call    cs:__imp_SysAllocStringLen
0x180023b87  mov     rbx, rax
0x180023b8a  mov     [rbp+var_40], rax
0x180023b8e  test    rax, rax
0x180023b91  jz      short loc_180023BA3
0x180023b93  jmp     loc_180023AC9
0x180023b98  mov     ecx, 80070057h; int
0x180023b9d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180023ba3  mov     ecx, 8007000Eh; int
0x180023ba8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

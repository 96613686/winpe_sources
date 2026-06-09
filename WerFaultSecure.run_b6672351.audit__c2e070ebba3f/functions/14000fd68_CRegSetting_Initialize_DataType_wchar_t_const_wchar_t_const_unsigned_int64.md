# CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)

- ea: `0x14000fd68`
- end: `0x14000fdd0`
- name: `?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400104f4`

## callees

- `0x14000dc44`
- `0x14000fd68`

## pseudocode

```c
__int64 __fastcall CRegSetting::Initialize(__int64 a1)
{
  __int64 result; // rax

  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a1 + 32,
                           L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug")
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a1 + 64,
                           L"WaitOnStart") )
  {
    return 2147500037LL;
  }
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  result = 0;
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_WORD *)a1 = 256;
  return result;
}

```

## disassembly

```asm
0x14000fd68  push    rbx
0x14000fd6a  sub     rsp, 20h
0x14000fd6e  mov     rbx, rcx
0x14000fd71  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x14000fd78  add     rcx, 20h ; ' '
0x14000fd7c  mov     r8d, 38h ; '8'
0x14000fd82  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000fd87  test    al, al
0x14000fd89  jz      short loc_14000FDC5
0x14000fd8b  lea     rcx, [rbx+40h]
0x14000fd8f  mov     r8d, 0Bh
0x14000fd95  lea     rdx, aWaitonstart; "WaitOnStart"
0x14000fd9c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000fda1  test    al, al
0x14000fda3  jz      short loc_14000FDC5
0x14000fda5  mov     rax, [rbx+8]
0x14000fda9  mov     [rbx+10h], rax
0x14000fdad  xor     eax, eax
0x14000fdaf  mov     dword ptr [rbx+4], 0
0x14000fdb6  mov     qword ptr [rbx+60h], 0
0x14000fdbe  mov     word ptr [rbx], 100h
0x14000fdc3  jmp     short loc_14000FDCA
0x14000fdc5  mov     eax, 80004005h
0x14000fdca  add     rsp, 20h
0x14000fdce  pop     rbx
0x14000fdcf  retn
```

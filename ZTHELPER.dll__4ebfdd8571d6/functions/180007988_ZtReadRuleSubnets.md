# ZtReadRuleSubnets

- ea: `0x180007988`
- end: `0x180007b5c`
- name: `ZtReadRuleSubnets`
- size: `468`
- prototype: `ULONG __fastcall(HKEY hKey, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007f4c`

## callees

- `0x180007988`
- `0x180009eac`
- `0x18000cc24`
- `0x18000f9c8`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`
- `0x180015114`
- `0x180015398`

## pseudocode

```c
ULONG __fastcall ZtReadRuleSubnets(HKEY hKey, __int64 a2, __int64 a3)
{
  signed int v5; // ebx
  int StringValueW; // eax
  int v7; // eax
  ULONG v8; // eax
  __int64 v10; // [rsp+70h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+48h] BYREF

  v10 = 0;
  lpMem = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 0x1Bu, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, hKey, a2);
  if ( hKey )
  {
    if ( a2 )
    {
      v5 = 0;
      StringValueW = privateRegReadStringValueW(hKey, L"Subnets", a3, (BYTE **)&lpMem, (DWORD *)&v10);
      if ( StringValueW == 2 )
      {
        if ( (xmmword_18001F260 & 4) != 0 )
          WPP_SF_(1026, 0x1Cu, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids);
      }
      else
      {
        if ( StringValueW > 0 )
          v5 = (unsigned __int16)StringValueW | 0x80070000;
        else
          v5 = StringValueW;
        if ( v5 >= 0 )
        {
          if ( (_DWORD)v10 )
          {
            v7 = DnsParseSubnetList((PCWSTR)lpMem);
            v5 = v7;
            if ( v7 > 0 )
              v5 = (unsigned __int16)v7 | 0x80070000;
            if ( v5 < 0 )
              HIDWORD(v10) = 264;
          }
          else
          {
            v10 = 0x10400000000LL;
            v5 = -2147024883;
          }
        }
        else
        {
          HIDWORD(v10) = 258;
        }
      }
    }
    else
    {
      v5 = -2147024809;
      HIDWORD(v10) = 245;
    }
  }
  else
  {
    v5 = -2147024809;
    HIDWORD(v10) = 244;
  }
  Dns_Free(lpMem);
  Dns_Free(0);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v8 = WX_WIN32_FROM_HR(v5);
    WPP_SF_d(1026, 0x1Du, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v8);
  }
  return WX_WIN32_FROM_HR(v5);
}

```

## disassembly

```asm
0x180007988  push    rbp
0x18000798a  push    rbx
0x18000798b  push    rsi
0x18000798c  push    rdi
0x18000798d  push    r14
0x18000798f  mov     rbp, rsp
0x180007992  sub     rsp, 30h
0x180007996  xor     esi, esi
0x180007998  mov     dword ptr [rbp+arg_10+4], 0
0x18000799f  mov     [rbp+arg_0], esi
0x1800079a2  mov     r14, rdx
0x1800079a5  mov     dword ptr [rbp+arg_10], esi
0x1800079a8  mov     rdi, rcx
0x1800079ab  mov     [rbp+lpMem], 0
0x1800079b3  test    byte ptr cs:xmmword_18001F260, 4
0x1800079ba  jz      short loc_1800079D8
0x1800079bc  lea     edx, [rsi+1Bh]
0x1800079bf  mov     [rsp+30h+var_10], r14
0x1800079c4  mov     ecx, 402h
0x1800079c9  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x1800079d0  mov     r9, rdi
0x1800079d3  call    WPP_SF_qq
0x1800079d8  test    rdi, rdi
0x1800079db  jnz     short loc_1800079EE
0x1800079dd  mov     ebx, 80070057h
0x1800079e2  mov     dword ptr [rbp+arg_10+4], 0F4h
0x1800079e9  jmp     loc_180007B10
0x1800079ee  test    r14, r14
0x1800079f1  jnz     short loc_180007A04
0x1800079f3  mov     ebx, 80070057h
0x1800079f8  mov     dword ptr [rbp+arg_10+4], 0F5h
0x1800079ff  jmp     loc_180007B10
0x180007a04  lea     rax, [rbp+arg_10]
0x180007a08  mov     rcx, rdi; hKey
0x180007a0b  lea     r9, [rbp+lpMem]
0x180007a0f  mov     [rsp+30h+var_10], rax; __int64
0x180007a14  lea     rdx, aSubnets; "Subnets"
0x180007a1b  xor     ebx, ebx
0x180007a1d  call    privateRegReadStringValueW
0x180007a22  cmp     eax, 2
0x180007a25  jnz     short loc_180007A4D
0x180007a27  test    byte ptr cs:xmmword_18001F260, 4
0x180007a2e  jz      loc_180007B10
0x180007a34  lea     edx, [rbx+1Ch]
0x180007a37  mov     ecx, 402h
0x180007a3c  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007a43  call    WPP_SF_
0x180007a48  jmp     loc_180007B10
0x180007a4d  mov     edi, 80070000h
0x180007a52  test    eax, eax
0x180007a54  jg      short loc_180007A5A
0x180007a56  mov     ebx, eax
0x180007a58  jmp     short loc_180007A5F
0x180007a5a  movzx   ebx, ax
0x180007a5d  or      ebx, edi
0x180007a5f  test    ebx, ebx
0x180007a61  jns     short loc_180007A6F
0x180007a63  mov     dword ptr [rbp+arg_10+4], 102h
0x180007a6a  jmp     loc_180007B10
0x180007a6f  cmp     dword ptr [rbp+arg_10], esi
0x180007a72  ja      short loc_180007A85
0x180007a74  mov     ebx, 8007000Dh
0x180007a79  mov     dword ptr [rbp+arg_10+4], 104h
0x180007a80  jmp     loc_180007B10
0x180007a85  mov     rcx, [rbp+lpMem]; S
0x180007a89  lea     r8, [rbp+arg_0]
0x180007a8d  xor     edx, edx
0x180007a8f  call    DnsParseSubnetList
0x180007a94  mov     ebx, eax
0x180007a96  test    eax, eax
0x180007a98  jle     short loc_180007A9F
0x180007a9a  movzx   ebx, ax
0x180007a9d  or      ebx, edi
0x180007a9f  test    ebx, ebx
0x180007aa1  jns     short loc_180007AAC
0x180007aa3  mov     dword ptr [rbp+arg_10+4], 108h
0x180007aaa  jmp     short loc_180007B10
0x180007aac  mov     eax, [rbp+arg_0]
0x180007aaf  test    eax, eax
0x180007ab1  jz      short loc_180007B10
0x180007ab3  mov     ecx, eax
0x180007ab5  shl     rcx, 5
0x180007ab9  call    Dns_Allocate
0x180007abe  mov     rsi, rax
0x180007ac1  test    rax, rax
0x180007ac4  jnz     short loc_180007AD4
0x180007ac6  mov     ebx, 80070057h
0x180007acb  mov     dword ptr [rbp+arg_10+4], 10Fh
0x180007ad2  jmp     short loc_180007B10
0x180007ad4  mov     rcx, [rbp+lpMem]; S
0x180007ad8  lea     r8, [rbp+arg_0]
0x180007adc  mov     rdx, rsi
0x180007adf  call    DnsParseSubnetList
0x180007ae4  mov     ebx, eax
0x180007ae6  test    eax, eax
0x180007ae8  jle     short loc_180007AEF
0x180007aea  movzx   ebx, ax
0x180007aed  or      ebx, edi
0x180007aef  test    ebx, ebx
0x180007af1  jns     short loc_180007AFC
0x180007af3  mov     dword ptr [rbp+arg_10+4], 113h
0x180007afa  jmp     short loc_180007B10
0x180007afc  mov     eax, [rbp+arg_0]
0x180007aff  mov     [r14+20h], rsi
0x180007b03  xor     esi, esi
0x180007b05  mov     [r14+28h], eax
0x180007b09  mov     [rbp+arg_0], 0
0x180007b10  mov     rcx, [rbp+lpMem]; lpMem
0x180007b14  call    Dns_Free
0x180007b19  mov     rcx, rsi; lpMem
0x180007b1c  call    Dns_Free
0x180007b21  test    byte ptr cs:xmmword_18001F260, 4
0x180007b28  jz      short loc_180007B4A
0x180007b2a  mov     ecx, ebx
0x180007b2c  call    WX_WIN32_FROM_HR
0x180007b31  mov     r9d, eax
0x180007b34  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007b3b  mov     edx, 1Dh
0x180007b40  mov     ecx, 402h
0x180007b45  call    WPP_SF_d
0x180007b4a  mov     ecx, ebx
0x180007b4c  call    WX_WIN32_FROM_HR
0x180007b51  add     rsp, 30h
0x180007b55  pop     r14
0x180007b57  pop     rdi
0x180007b58  pop     rsi
0x180007b59  pop     rbx
0x180007b5a  pop     rbp
0x180007b5b  retn
```

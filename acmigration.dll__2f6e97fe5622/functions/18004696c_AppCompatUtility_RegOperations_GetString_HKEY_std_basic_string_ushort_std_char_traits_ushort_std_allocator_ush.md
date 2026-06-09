# AppCompatUtility::RegOperations::GetString(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004696c`
- end: `0x180046b60`
- name: `?GetString@RegOperations@AppCompatUtility@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAV45@@Z`
- size: `500`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180046b68`
- `0x18004bc04`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x18000e504`
- `0x18002ec04`
- `0x18004696c`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800469df`
- `ADVAPI32!RegGetValueW` at `0x180046abb`
- `ADVAPI32!RegGetValueW` at `0x1800469df`
- `ADVAPI32!RegGetValueW` at `0x180046abb`

## string_xrefs

- `0x180046a12`: `Failed read string from (0x%x, %ws, %ws). 0x%x`
- `0x180046aee`: `Failed read string from (0x%x, %ws, %ws). 0x%x`
- `0x180046a1f`: `AppCompatUtility::RegOperations::GetString`
- `0x180046afb`: `AppCompatUtility::RegOperations::GetString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppCompatUtility::RegOperations::GetString(
        HKEY hkey,
        const WCHAR *lpSubKey,
        const WCHAR *lpValue,
        __int64 a4)
{
  const WCHAR *v5; // rdi
  const WCHAR *v6; // rbx
  int ValueW; // esi
  PVOID *pvData; // rax
  const WCHAR *v10; // r8
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  __int64 pcbData; // [rsp+40h] [rbp-19h] BYREF
  __int64 v15; // [rsp+48h] [rbp-11h]
  PVOID Src[2]; // [rsp+50h] [rbp-9h] BYREF
  __m128i si128; // [rsp+60h] [rbp+7h]

  v15 = -2;
  v5 = lpValue;
  v6 = lpSubKey;
  LODWORD(pcbData) = 0;
  if ( *((_QWORD *)lpValue + 3) > 7u )
    lpValue = *(const WCHAR **)lpValue;
  if ( *((_QWORD *)lpSubKey + 3) > 7u )
    lpSubKey = *(const WCHAR **)lpSubKey;
  ValueW = RegGetValueW(hkey, lpSubKey, lpValue, 2u, 0, 0, (LPDWORD)&pcbData);
  if ( ValueW )
  {
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const WCHAR **)v5;
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(const WCHAR **)v6;
    AslLogCallPrintf(
      3,
      "AppCompatUtility::RegOperations::GetString",
      135,
      "Failed read string from (0x%x, %ws, %ws). 0x%x",
      hkey,
      v6,
      v5,
      ValueW,
      pcbData,
      v15);
    if ( ValueW > 0 )
      return (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    *(_OWORD *)Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src[0]) = 0;
    std::wstring::resize(Src);
    pvData = Src;
    if ( si128.m128i_i64[1] > 7uLL )
      pvData = (PVOID *)Src[0];
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v10 = v5;
    else
      v10 = *(const WCHAR **)v5;
    if ( *((_QWORD *)v6 + 3) <= 7u )
      v11 = v6;
    else
      v11 = *(const WCHAR **)v6;
    v12 = RegGetValueW(hkey, v11, v10, 2u, 0, pvData, (LPDWORD)&pcbData);
    ValueW = v12;
    if ( v12 )
    {
      if ( *((_QWORD *)v5 + 3) > 7u )
        v5 = *(const WCHAR **)v5;
      if ( *((_QWORD *)v6 + 3) > 7u )
        v6 = *(const WCHAR **)v6;
      AslLogCallPrintf(
        3,
        "AppCompatUtility::RegOperations::GetString",
        153,
        "Failed read string from (0x%x, %ws, %ws). 0x%x",
        hkey,
        v6,
        v5,
        v12,
        pcbData,
        v15);
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    else
    {
      std::wstring::resize(Src);
      std::wstring::operator=(a4, Src);
      ValueW = 0;
    }
    std::wstring::~wstring(Src);
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18004696c  push    rbp
0x18004696e  push    rbx
0x18004696f  push    rsi
0x180046970  push    rdi
0x180046971  push    r14
0x180046973  push    r15
0x180046975  lea     rbp, [rsp-2Fh]
0x18004697a  sub     rsp, 88h
0x180046981  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x180046989  mov     rax, cs:__security_cookie
0x180046990  xor     rax, rsp
0x180046993  mov     [rbp+57h+var_40], rax
0x180046997  mov     r15, r9
0x18004699a  mov     rdi, r8
0x18004699d  mov     rbx, rdx
0x1800469a0  mov     r14, rcx
0x1800469a3  mov     dword ptr [rbp+57h+var_70], 0
0x1800469aa  cmp     qword ptr [r8+18h], 7
0x1800469af  jbe     short loc_1800469B4
0x1800469b1  mov     r8, [r8]; lpValue
0x1800469b4  cmp     qword ptr [rdx+18h], 7
0x1800469b9  jbe     short loc_1800469BE
0x1800469bb  mov     rdx, [rdx]; lpSubKey
0x1800469be  lea     rax, [rbp+57h+var_70]
0x1800469c2  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800469c7  mov     [rsp+0B0h+pvData], 0; pvData
0x1800469d0  mov     [rsp+0B0h+pdwType], 0; pdwType
0x1800469d9  mov     r9d, 2; dwFlags
0x1800469df  call    cs:__imp_RegGetValueW
0x1800469e5  mov     esi, eax
0x1800469e7  test    eax, eax
0x1800469e9  jz      short loc_180046A46
0x1800469eb  cmp     qword ptr [rdi+18h], 7
0x1800469f0  jbe     short loc_1800469F5
0x1800469f2  mov     rdi, [rdi]
0x1800469f5  cmp     qword ptr [rbx+18h], 7
0x1800469fa  jbe     short loc_1800469FF
0x1800469fc  mov     rbx, [rbx]
0x1800469ff  mov     [rsp+0B0h+var_78], esi
0x180046a03  mov     [rsp+0B0h+pcbData], rdi
0x180046a08  mov     [rsp+0B0h+pvData], rbx
0x180046a0d  mov     [rsp+0B0h+pdwType], r14
0x180046a12  lea     r9, aFailedReadStri; "Failed read string from (0x%x, %ws, %ws"...
0x180046a19  mov     r8d, 87h
0x180046a1f  lea     rdx, aAppcompatutili_6; "AppCompatUtility::RegOperations::GetStr"...
0x180046a26  mov     ecx, 3
0x180046a2b  call    AslLogCallPrintf
0x180046a30  test    esi, esi
0x180046a32  jle     loc_180046B42
0x180046a38  movzx   esi, si
0x180046a3b  or      esi, 80070000h
0x180046a41  jmp     loc_180046B42
0x180046a46  xorps   xmm0, xmm0
0x180046a49  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180046a4d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180046a55  movdqu  [rbp+57h+var_50], xmm1
0x180046a5a  xor     eax, eax
0x180046a5c  mov     word ptr [rbp+57h+Src], ax
0x180046a60  mov     edx, dword ptr [rbp+57h+var_70]
0x180046a63  shr     rdx, 1
0x180046a66  lea     rcx, [rbp+57h+Src]; Src
0x180046a6a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180046a6f  lea     rax, [rbp+57h+Src]
0x180046a73  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180046a78  cmova   rax, [rbp+57h+Src]
0x180046a7d  cmp     qword ptr [rdi+18h], 7
0x180046a82  jbe     short loc_180046A89
0x180046a84  mov     r8, [rdi]
0x180046a87  jmp     short loc_180046A8C
0x180046a89  mov     r8, rdi; lpValue
0x180046a8c  cmp     qword ptr [rbx+18h], 7
0x180046a91  jbe     short loc_180046A98
0x180046a93  mov     rdx, [rbx]
0x180046a96  jmp     short loc_180046A9B
0x180046a98  mov     rdx, rbx; lpSubKey
0x180046a9b  lea     rcx, [rbp+57h+var_70]
0x180046a9f  mov     [rsp+0B0h+pcbData], rcx; pcbData
0x180046aa4  mov     [rsp+0B0h+pvData], rax; pvData
0x180046aa9  mov     [rsp+0B0h+pdwType], 0; pdwType
0x180046ab2  mov     r9d, 2; dwFlags
0x180046ab8  mov     rcx, r14; hkey
0x180046abb  call    cs:__imp_RegGetValueW
0x180046ac1  mov     esi, eax
0x180046ac3  test    eax, eax
0x180046ac5  jz      short loc_180046B1B
0x180046ac7  cmp     qword ptr [rdi+18h], 7
0x180046acc  jbe     short loc_180046AD1
0x180046ace  mov     rdi, [rdi]
0x180046ad1  cmp     qword ptr [rbx+18h], 7
0x180046ad6  jbe     short loc_180046ADB
0x180046ad8  mov     rbx, [rbx]
0x180046adb  mov     [rsp+0B0h+var_78], esi
0x180046adf  mov     [rsp+0B0h+pcbData], rdi
0x180046ae4  mov     [rsp+0B0h+pvData], rbx
0x180046ae9  mov     [rsp+0B0h+pdwType], r14
0x180046aee  lea     r9, aFailedReadStri; "Failed read string from (0x%x, %ws, %ws"...
0x180046af5  mov     r8d, 99h
0x180046afb  lea     rdx, aAppcompatutili_6; "AppCompatUtility::RegOperations::GetStr"...
0x180046b02  mov     ecx, 3
0x180046b07  call    AslLogCallPrintf
0x180046b0c  test    esi, esi
0x180046b0e  jle     short loc_180046B39
0x180046b10  movzx   esi, si
0x180046b13  or      esi, 80070000h
0x180046b19  jmp     short loc_180046B39
0x180046b1b  mov     edx, dword ptr [rbp+57h+var_70]
0x180046b1e  shr     edx, 1
0x180046b20  dec     edx
0x180046b22  lea     rcx, [rbp+57h+Src]; Src
0x180046b26  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180046b2b  lea     rdx, [rbp+57h+Src]
0x180046b2f  mov     rcx, r15
0x180046b32  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180046b37  xor     esi, esi
0x180046b39  lea     rcx, [rbp+57h+Src]; void *
0x180046b3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046b42  mov     eax, esi
0x180046b44  mov     rcx, [rbp+57h+var_40]
0x180046b48  xor     rcx, rsp; StackCookie
0x180046b4b  call    __security_check_cookie
0x180046b50  add     rsp, 88h
0x180046b57  pop     r15
0x180046b59  pop     r14
0x180046b5b  pop     rdi
0x180046b5c  pop     rsi
0x180046b5d  pop     rbx
0x180046b5e  pop     rbp
0x180046b5f  retn
```

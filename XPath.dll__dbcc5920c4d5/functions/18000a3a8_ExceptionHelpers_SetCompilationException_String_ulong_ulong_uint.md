# ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)

- ea: `0x18000a3a8`
- end: `0x18000a5dc`
- name: `?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z`
- size: `564`
- prototype: `__int64 __fastcall(const unsigned __int16 **, unsigned int, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009164`
- `0x180009448`
- `0x180009890`
- `0x180009b1c`
- `0x180009c58`
- `0x180009d84`
- `0x180009f24`
- `0x18000a280`
- `0x18000dc40`
- `0x18000e128`
- `0x18000e1c0`
- `0x18000e26c`
- `0x18000f138`

## callees

- `0x18000a3a8`
- `0x180010f08`
- `0x180010fac`
- `0x18001118c`
- `0x1800112d8`
- `0x180011840`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18000a45d`
- `msvcrt!_ultow_s` at `0x18000a478`
- `msvcrt!_ultow_s` at `0x18000a45d`
- `msvcrt!_ultow_s` at `0x18000a478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a520`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a516`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a516`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a555`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a555`

## pseudocode

```c
__int64 __fastcall ExceptionHelpers::SetCompilationException(
        const unsigned __int16 **a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v6; // rdi
  signed int ResourceString; // ebx
  bool v8; // zf
  const unsigned __int16 *v9; // r14
  const unsigned __int16 *v10; // rcx
  HINSTANCE v11; // rcx
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rcx
  DWORD v15; // eax
  signed int LastError; // eax
  const unsigned __int16 *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR lpBuffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPCVOID lpSource; // [rsp+60h] [rbp-A0h] BYREF
  va_list Arguments[5]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[40]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v25[40]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a2;
  v18 = 0;
  ResourceString = LoadResourceString((HINSTANCE)a1, a4, (struct String *)&v18);
  if ( ResourceString >= 0 )
  {
    v8 = *a1 == 0;
    v9 = &qword_180016F98;
    v10 = &qword_180016F98;
    v20 = 0;
    if ( !v8 )
      v10 = *a1;
    ResourceString = String::Initialize((String *)&v20, &v10[v6], a3);
    if ( ResourceString >= 0 )
    {
      lpSource = 0;
      ResourceString = LoadResourceString(v11, 0xC9u, (struct String *)&lpSource);
      if ( ResourceString >= 0 )
      {
        if ( _ultow_s(v6, Buffer, 0x22u, 10) || _ultow_s(a3, v25, 0x22u, 10) )
        {
          ResourceString = -2147467259;
        }
        else
        {
          v12 = &qword_180016F98;
          v19 = 0;
          *(_QWORD *)lpBuffer = 0;
          if ( v18 )
            v12 = v18;
          v8 = *a1 == 0;
          Arguments[0] = (va_list)v12;
          v13 = &qword_180016F98;
          if ( !v8 )
            v13 = *a1;
          v14 = &qword_180016F98;
          Arguments[1] = (va_list)v13;
          Arguments[2] = (va_list)Buffer;
          Arguments[3] = (va_list)v25;
          if ( v20 )
            v14 = v20;
          Arguments[4] = (va_list)v14;
          if ( lpSource )
            v9 = (const unsigned __int16 *)lpSource;
          v15 = FormatMessageW(0x2500u, v9, 0, 0, lpBuffer, 0, Arguments);
          if ( v15 )
          {
            ResourceString = String::Initialize((String *)&v19, *(const unsigned __int16 **)lpBuffer, v15);
          }
          else
          {
            LastError = GetLastError();
            ResourceString = LastError;
            if ( LastError > 0 )
              ResourceString = (unsigned __int16)LastError | 0x80070000;
          }
          if ( *(_QWORD *)lpBuffer )
            LocalFree(*(HLOCAL *)lpBuffer);
          if ( ResourceString < 0
            || (ResourceString = XPathException::SetException(
                                   (struct String *)a1,
                                   v6,
                                   a3,
                                   (struct String *)&v18,
                                   (struct String *)&v19),
                ResourceString < 0) )
          {
            String::Reset((String *)&v19);
          }
          else
          {
            String::Reset((String *)&v19);
            ResourceString = 0;
          }
        }
      }
      String::Reset((String *)&lpSource);
    }
    String::Reset((String *)&v20);
  }
  String::Reset((String *)&v18);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x18000a3a8  push    rbp
0x18000a3aa  push    rbx
0x18000a3ab  push    rsi
0x18000a3ac  push    rdi
0x18000a3ad  push    r14
0x18000a3af  push    r15
0x18000a3b1  lea     rbp, [rsp-48h]
0x18000a3b6  sub     rsp, 148h
0x18000a3bd  mov     rax, cs:__security_cookie
0x18000a3c4  xor     rax, rsp
0x18000a3c7  mov     [rbp+70h+var_40], rax
0x18000a3cb  mov     esi, r8d
0x18000a3ce  mov     r15, rcx
0x18000a3d1  mov     edi, edx
0x18000a3d3  lea     r8, [rsp+170h+var_130]; struct String *
0x18000a3d8  mov     edx, r9d; unsigned int
0x18000a3db  mov     [rsp+170h+var_130], 0
0x18000a3e4  call    ?LoadResourceString@@YAJPEAUHINSTANCE__@@IAEAVString@@@Z; LoadResourceString(HINSTANCE__ *,uint,String &)
0x18000a3e9  mov     ebx, eax
0x18000a3eb  test    eax, eax
0x18000a3ed  js      loc_18000A5B4
0x18000a3f3  cmp     qword ptr [r15], 0
0x18000a3f7  lea     r14, qword_180016F98
0x18000a3fe  mov     rcx, r14
0x18000a401  mov     [rsp+170h+var_120], 0
0x18000a40a  cmovnz  rcx, [r15]
0x18000a40e  mov     r8d, esi; unsigned __int64
0x18000a411  lea     rdx, [rcx+rdi*2]; Src
0x18000a415  lea     rcx, [rsp+170h+var_120]; this
0x18000a41a  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000a41f  mov     ebx, eax
0x18000a421  test    eax, eax
0x18000a423  js      loc_18000A5AA
0x18000a429  lea     r8, [rsp+170h+lpSource]; struct String *
0x18000a42e  mov     [rsp+170h+lpSource], 0
0x18000a437  mov     edx, 0C9h; unsigned int
0x18000a43c  call    ?LoadResourceString@@YAJPEAUHINSTANCE__@@IAEAVString@@@Z; LoadResourceString(HINSTANCE__ *,uint,String &)
0x18000a441  mov     ebx, eax
0x18000a443  test    eax, eax
0x18000a445  js      loc_18000A5A0
0x18000a44b  mov     ebx, 0Ah
0x18000a450  lea     rdx, [rbp+70h+Buffer]; Buffer
0x18000a454  mov     r9d, ebx; Radix
0x18000a457  mov     ecx, edi; Value
0x18000a459  lea     r8d, [rbx+18h]; BufferCount
0x18000a45d  call    cs:__imp__ultow_s
0x18000a463  test    eax, eax
0x18000a465  jnz     loc_18000A59B
0x18000a46b  mov     r9d, ebx; Radix
0x18000a46e  lea     r8d, [rbx+18h]; BufferCount
0x18000a472  lea     rdx, [rbp+70h+var_90]; Buffer
0x18000a476  mov     ecx, esi; Value
0x18000a478  call    cs:__imp__ultow_s
0x18000a47e  test    eax, eax
0x18000a480  jnz     loc_18000A59B
0x18000a486  mov     rax, [rsp+170h+var_130]
0x18000a48b  mov     rcx, r14
0x18000a48e  test    rax, rax
0x18000a491  mov     [rsp+170h+var_128], 0
0x18000a49a  mov     qword ptr [rsp+170h+var_118], 0
0x18000a4a3  cmovnz  rcx, rax
0x18000a4a7  cmp     qword ptr [r15], 0
0x18000a4ab  mov     [rsp+170h+var_108], rcx
0x18000a4b0  mov     rax, r14
0x18000a4b3  cmovnz  rax, [r15]
0x18000a4b7  mov     rcx, r14
0x18000a4ba  mov     [rsp+170h+var_100], rax
0x18000a4bf  lea     rax, [rbp+70h+Buffer]
0x18000a4c3  mov     [rsp+170h+var_F8], rax
0x18000a4c8  lea     rax, [rbp+70h+var_90]
0x18000a4cc  mov     [rbp+70h+var_F0], rax
0x18000a4d0  mov     rax, [rsp+170h+var_120]
0x18000a4d5  test    rax, rax
0x18000a4d8  cmovnz  rcx, rax
0x18000a4dc  mov     rax, [rsp+170h+lpSource]
0x18000a4e1  test    rax, rax
0x18000a4e4  mov     [rbp+70h+var_E8], rcx
0x18000a4e8  mov     ecx, 2500h; dwFlags
0x18000a4ed  cmovnz  r14, rax
0x18000a4f1  lea     rax, [rsp+170h+var_108]
0x18000a4f6  mov     [rsp+170h+Arguments], rax; Arguments
0x18000a4fb  xor     r9d, r9d; dwLanguageId
0x18000a4fe  lea     rax, [rsp+170h+var_118]
0x18000a503  mov     [rsp+170h+nSize], 0; nSize
0x18000a50b  xor     r8d, r8d; dwMessageId
0x18000a50e  mov     [rsp+170h+lpBuffer], rax; lpBuffer
0x18000a513  mov     rdx, r14; lpSource
0x18000a516  call    cs:__imp_FormatMessageW
0x18000a51c  test    eax, eax
0x18000a51e  jnz     short loc_18000A537
0x18000a520  call    cs:__imp_GetLastError
0x18000a526  mov     ebx, eax
0x18000a528  test    eax, eax
0x18000a52a  jle     short loc_18000A54B
0x18000a52c  movzx   ebx, ax
0x18000a52f  or      ebx, 80070000h
0x18000a535  jmp     short loc_18000A54B
0x18000a537  mov     rdx, qword ptr [rsp+170h+var_118]; Src
0x18000a53c  lea     rcx, [rsp+170h+var_128]; this
0x18000a541  mov     r8d, eax; unsigned __int64
0x18000a544  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000a549  mov     ebx, eax
0x18000a54b  mov     rcx, qword ptr [rsp+170h+var_118]; hMem
0x18000a550  test    rcx, rcx
0x18000a553  jz      short loc_18000A55B
0x18000a555  call    cs:__imp_LocalFree
0x18000a55b  test    ebx, ebx
0x18000a55d  jns     short loc_18000A56B
0x18000a55f  lea     rcx, [rsp+170h+var_128]; this
0x18000a564  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a569  jmp     short loc_18000A5A0
0x18000a56b  lea     rax, [rsp+170h+var_128]
0x18000a570  mov     r8d, esi; unsigned int
0x18000a573  lea     r9, [rsp+170h+var_130]; struct String *
0x18000a578  mov     [rsp+170h+lpBuffer], rax; struct String *
0x18000a57d  mov     edx, edi; unsigned int
0x18000a57f  mov     rcx, r15; struct String *
0x18000a582  call    ?SetException@XPathException@@SAJAEAVString@@KK00@Z; XPathException::SetException(String &,ulong,ulong,String &,String &)
0x18000a587  lea     rcx, [rsp+170h+var_128]; this
0x18000a58c  mov     ebx, eax
0x18000a58e  test    eax, eax
0x18000a590  js      short loc_18000A564
0x18000a592  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a597  xor     ebx, ebx
0x18000a599  jmp     short loc_18000A5A0
0x18000a59b  mov     ebx, 80004005h
0x18000a5a0  lea     rcx, [rsp+170h+lpSource]; this
0x18000a5a5  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a5aa  lea     rcx, [rsp+170h+var_120]; this
0x18000a5af  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a5b4  lea     rcx, [rsp+170h+var_130]; this
0x18000a5b9  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000a5be  mov     eax, ebx
0x18000a5c0  mov     rcx, [rbp+70h+var_40]
0x18000a5c4  xor     rcx, rsp; StackCookie
0x18000a5c7  call    __security_check_cookie
0x18000a5cc  add     rsp, 148h
0x18000a5d3  pop     r15
0x18000a5d5  pop     r14
0x18000a5d7  pop     rdi
0x18000a5d8  pop     rsi
0x18000a5d9  pop     rbx
0x18000a5da  pop     rbp
0x18000a5db  retn
```

# CreateScratchDirectory(ushort *)

- ea: `0x180020c7c`
- end: `0x180020e23`
- name: `?CreateScratchDirectory@@YAJPEAG@Z`
- size: `423`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18002817c`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18000d520`
- `0x180020c7c`
- `0x18006c910`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180020d40`
- `msvcrt!swprintf_s` at `0x180020d40`
- `ntdll!RtlRandomEx` at `0x180020d20`
- `ntdll!RtlRandomEx` at `0x180020d20`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020d7d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020d7d`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180020ca9`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180020ca9`

## string_xrefs

- `0x180020cea`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020dfa`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
__int64 __fastcall CreateScratchDirectory(unsigned __int16 *a1)
{
  __int64 v2; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  signed int v5; // edi
  __int64 v6; // rdx
  ULONG v8; // eax
  __int64 v9; // rax
  WCHAR *v10; // rcx
  unsigned __int16 *v11; // rdx
  ULONG Seed; // [rsp+20h] [rbp-268h] BYREF
  wchar_t v13[12]; // [rsp+28h] [rbp-260h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v2 = 260;
  if ( GetTempPathW(0x104u, Buffer) )
  {
    v5 = StringCchCatW(Buffer, 0x104u, L"scratch_");
    if ( v5 >= 0 )
    {
      Seed = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
      v8 = RtlRandomEx(&Seed);
      if ( swprintf_s(v13, 0xAu, L"%08x\\", v8) <= 0 )
      {
        v4 = 106;
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)v4,
                 (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\p"
                               "ackagemanager.cpp",
                 v3);
      }
      v5 = StringCchCatW(Buffer, 0x104u, v13);
      if ( v5 >= 0 )
      {
        if ( !CreateDirectoryW(Buffer, 0) )
        {
          v4 = 113;
          return wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)v4,
                   (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\"
                                 "packagemanager.cpp",
                   v3);
        }
        v9 = 2147483646;
        v10 = Buffer;
        do
        {
          if ( !v9 )
            break;
          if ( !*v10 )
            break;
          *a1++ = *v10++;
          --v9;
          --v2;
        }
        while ( v2 );
        v11 = a1 - 1;
        v5 = v2 == 0 ? 0x8007007A : 0;
        if ( v2 )
          v11 = a1;
        *v11 = 0;
        if ( v2 )
          return 0;
        v6 = 115;
      }
      else
      {
        v6 = 109;
      }
    }
    else
    {
      v6 = 99;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v5,
      Seed);
    return (unsigned int)v5;
  }
  v4 = 98;
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v4,
           (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
           v3);
}

```

## disassembly

```asm
0x180020c7c  push    rbx
0x180020c7e  push    rbp
0x180020c7f  push    rsi
0x180020c80  push    rdi
0x180020c81  sub     rsp, 268h
0x180020c88  mov     rax, cs:__security_cookie
0x180020c8f  xor     rax, rsp
0x180020c92  mov     [rsp+288h+var_38], rax
0x180020c9a  mov     rsi, rcx
0x180020c9d  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180020ca2  mov     ebx, 104h
0x180020ca7  mov     ecx, ebx; nBufferLength
0x180020ca9  call    cs:__imp_GetTempPathW
0x180020cb0  nop     dword ptr [rax+rax+00h]
0x180020cb5  xor     ebp, ebp
0x180020cb7  test    eax, eax
0x180020cb9  jnz     short loc_180020CC3
0x180020cbb  lea     edx, [rbp+62h]
0x180020cbe  jmp     loc_180020DF2
0x180020cc3  lea     r8, aScratch; "scratch_"
0x180020cca  mov     rdx, rbx; unsigned __int64
0x180020ccd  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x180020cd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020cd7  mov     edi, eax
0x180020cd9  test    eax, eax
0x180020cdb  jns     short loc_180020D00
0x180020cdd  mov     edx, 63h ; 'c'; void *
0x180020ce2  mov     rcx, [rsp+288h]; this
0x180020cea  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020cf1  mov     r9d, edi; char *
0x180020cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cf9  mov     eax, edi
0x180020cfb  jmp     loc_180020E06
0x180020d00  mov     eax, 7FFE0320h
0x180020d05  mov     rax, [rax]
0x180020d08  mov     ecx, ds:7FFE0004h
0x180020d0f  imul    rcx, rax
0x180020d13  shr     rcx, 18h
0x180020d17  mov     [rsp+288h+Seed], ecx
0x180020d1b  lea     rcx, [rsp+288h+Seed]; Seed
0x180020d20  call    cs:__imp_RtlRandomEx
0x180020d27  nop     dword ptr [rax+rax+00h]
0x180020d2c  lea     r8, a08x; "%08x\\"
0x180020d33  mov     edx, 0Ah; BufferCount
0x180020d38  mov     r9d, eax
0x180020d3b  lea     rcx, [rsp+288h+var_260]; Buffer
0x180020d40  call    cs:__imp_swprintf_s
0x180020d47  nop     dword ptr [rax+rax+00h]
0x180020d4c  test    eax, eax
0x180020d4e  jle     loc_180020DED
0x180020d54  lea     r8, [rsp+288h+var_260]; unsigned __int16 *
0x180020d59  mov     rdx, rbx; unsigned __int64
0x180020d5c  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x180020d61  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020d66  mov     edi, eax
0x180020d68  test    eax, eax
0x180020d6a  jns     short loc_180020D76
0x180020d6c  mov     edx, 6Dh ; 'm'
0x180020d71  jmp     loc_180020CE2
0x180020d76  xor     edx, edx; lpSecurityAttributes
0x180020d78  lea     rcx, [rsp+288h+Buffer]; lpPathName
0x180020d7d  call    cs:__imp_CreateDirectoryW
0x180020d84  nop     dword ptr [rax+rax+00h]
0x180020d89  test    eax, eax
0x180020d8b  jz      short loc_180020DE6
0x180020d8d  mov     eax, 7FFFFFFEh
0x180020d92  lea     rcx, [rsp+288h+Buffer]
0x180020d97  test    rax, rax
0x180020d9a  jz      short loc_180020DB8
0x180020d9c  movzx   edx, word ptr [rcx]
0x180020d9f  test    dx, dx
0x180020da2  jz      short loc_180020DB8
0x180020da4  mov     [rsi], dx
0x180020da7  add     rcx, 2
0x180020dab  add     rsi, 2
0x180020daf  dec     rax
0x180020db2  sub     rbx, 1
0x180020db6  jnz     short loc_180020D97
0x180020db8  mov     rax, rbx
0x180020dbb  lea     rdx, [rsi-2]
0x180020dbf  neg     rax
0x180020dc2  sbb     edi, edi
0x180020dc4  not     edi
0x180020dc6  and     edi, 8007007Ah
0x180020dcc  test    rbx, rbx
0x180020dcf  cmovnz  rdx, rsi
0x180020dd3  mov     [rdx], bp
0x180020dd6  jnz     short loc_180020DE2
0x180020dd8  mov     edx, 73h ; 's'
0x180020ddd  jmp     loc_180020CE2
0x180020de2  xor     eax, eax
0x180020de4  jmp     short loc_180020E06
0x180020de6  mov     edx, 71h ; 'q'
0x180020deb  jmp     short loc_180020DF2
0x180020ded  mov     edx, 6Ah ; 'j'; void *
0x180020df2  mov     rcx, [rsp+288h]; this
0x180020dfa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020e01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020e06  mov     rcx, [rsp+288h+var_38]
0x180020e0e  xor     rcx, rsp; StackCookie
0x180020e11  call    __security_check_cookie
0x180020e16  add     rsp, 268h
0x180020e1d  pop     rdi
0x180020e1e  pop     rsi
0x180020e1f  pop     rbp
0x180020e20  pop     rbx
0x180020e21  retn
```

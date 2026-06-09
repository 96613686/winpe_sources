# CreateScratchDirectory(ushort *)

- ea: `0x18001f6a0`
- end: `0x18001f82e`
- name: `?CreateScratchDirectory@@YAJPEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180026390`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18000d11c`
- `0x18001f6a0`
- `0x180066df0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001f758`
- `msvcrt!swprintf_s` at `0x18001f758`
- `ntdll!RtlRandomEx` at `0x18001f73e`
- `ntdll!RtlRandomEx` at `0x18001f73e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001f78f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001f78f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001f6cd`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001f6cd`

## string_xrefs

- `0x18001f708`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f806`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18001f6a0  push    rbx
0x18001f6a2  push    rbp
0x18001f6a3  push    rsi
0x18001f6a4  push    rdi
0x18001f6a5  sub     rsp, 268h
0x18001f6ac  mov     rax, cs:__security_cookie
0x18001f6b3  xor     rax, rsp
0x18001f6b6  mov     [rsp+288h+var_38], rax
0x18001f6be  mov     rsi, rcx
0x18001f6c1  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x18001f6c6  mov     ebx, 104h
0x18001f6cb  mov     ecx, ebx; nBufferLength
0x18001f6cd  call    cs:__imp_GetTempPathW
0x18001f6d3  xor     ebp, ebp
0x18001f6d5  test    eax, eax
0x18001f6d7  jnz     short loc_18001F6E1
0x18001f6d9  lea     edx, [rbp+62h]
0x18001f6dc  jmp     loc_18001F7FE
0x18001f6e1  lea     r8, aScratch; "scratch_"
0x18001f6e8  mov     rdx, rbx; unsigned __int64
0x18001f6eb  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x18001f6f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f6f5  mov     edi, eax
0x18001f6f7  test    eax, eax
0x18001f6f9  jns     short loc_18001F71E
0x18001f6fb  mov     edx, 63h ; 'c'; void *
0x18001f700  mov     rcx, [rsp+288h]; this
0x18001f708  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f70f  mov     r9d, edi; char *
0x18001f712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f717  mov     eax, edi
0x18001f719  jmp     loc_18001F812
0x18001f71e  mov     eax, 7FFE0320h
0x18001f723  mov     rax, [rax]
0x18001f726  mov     ecx, ds:7FFE0004h
0x18001f72d  imul    rcx, rax
0x18001f731  shr     rcx, 18h
0x18001f735  mov     [rsp+288h+Seed], ecx
0x18001f739  lea     rcx, [rsp+288h+Seed]; Seed
0x18001f73e  call    cs:__imp_RtlRandomEx
0x18001f744  lea     r8, a08x; "%08x\\"
0x18001f74b  mov     edx, 0Ah; BufferCount
0x18001f750  mov     r9d, eax
0x18001f753  lea     rcx, [rsp+288h+var_260]; Buffer
0x18001f758  call    cs:__imp_swprintf_s
0x18001f75e  test    eax, eax
0x18001f760  jle     loc_18001F7F9
0x18001f766  lea     r8, [rsp+288h+var_260]; unsigned __int16 *
0x18001f76b  mov     rdx, rbx; unsigned __int64
0x18001f76e  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x18001f773  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f778  mov     edi, eax
0x18001f77a  test    eax, eax
0x18001f77c  jns     short loc_18001F788
0x18001f77e  mov     edx, 6Dh ; 'm'
0x18001f783  jmp     loc_18001F700
0x18001f788  xor     edx, edx; lpSecurityAttributes
0x18001f78a  lea     rcx, [rsp+288h+Buffer]; lpPathName
0x18001f78f  call    cs:__imp_CreateDirectoryW
0x18001f795  test    eax, eax
0x18001f797  jz      short loc_18001F7F2
0x18001f799  mov     eax, 7FFFFFFEh
0x18001f79e  lea     rcx, [rsp+288h+Buffer]
0x18001f7a3  test    rax, rax
0x18001f7a6  jz      short loc_18001F7C4
0x18001f7a8  movzx   edx, word ptr [rcx]
0x18001f7ab  test    dx, dx
0x18001f7ae  jz      short loc_18001F7C4
0x18001f7b0  mov     [rsi], dx
0x18001f7b3  add     rcx, 2
0x18001f7b7  add     rsi, 2
0x18001f7bb  dec     rax
0x18001f7be  sub     rbx, 1
0x18001f7c2  jnz     short loc_18001F7A3
0x18001f7c4  mov     rax, rbx
0x18001f7c7  lea     rdx, [rsi-2]
0x18001f7cb  neg     rax
0x18001f7ce  sbb     edi, edi
0x18001f7d0  not     edi
0x18001f7d2  and     edi, 8007007Ah
0x18001f7d8  test    rbx, rbx
0x18001f7db  cmovnz  rdx, rsi
0x18001f7df  mov     [rdx], bp
0x18001f7e2  jnz     short loc_18001F7EE
0x18001f7e4  mov     edx, 73h ; 's'
0x18001f7e9  jmp     loc_18001F700
0x18001f7ee  xor     eax, eax
0x18001f7f0  jmp     short loc_18001F812
0x18001f7f2  mov     edx, 71h ; 'q'
0x18001f7f7  jmp     short loc_18001F7FE
0x18001f7f9  mov     edx, 6Ah ; 'j'; void *
0x18001f7fe  mov     rcx, [rsp+288h]; this
0x18001f806  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f80d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f812  mov     rcx, [rsp+288h+var_38]
0x18001f81a  xor     rcx, rsp; StackCookie
0x18001f81d  call    __security_check_cookie
0x18001f822  add     rsp, 268h
0x18001f829  pop     rdi
0x18001f82a  pop     rsi
0x18001f82b  pop     rbp
0x18001f82c  pop     rbx
0x18001f82d  retn
```

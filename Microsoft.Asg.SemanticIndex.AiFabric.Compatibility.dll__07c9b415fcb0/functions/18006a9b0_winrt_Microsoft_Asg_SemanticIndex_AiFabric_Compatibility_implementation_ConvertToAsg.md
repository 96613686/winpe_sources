# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ConvertToAsg

- ea: `0x18006a9b0`
- end: `0x18006ad86`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ConvertToAsg`
- size: `982`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006b080`
- `0x18006bec0`
- `0x18006bf80`

## callees

- `0x180003bd0`
- `0x180007830`
- `0x180010dd0`
- `0x180017640`
- `0x18006a9b0`
- `0x180078d00`
- `0x180078d10`
- `0x1801f7110`
- `0x180206a58`
- `0x180242120`

## string_xrefs

- `0x18006a9f8`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18006ab49`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18006ab86`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18006abc1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18006abfe`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ConvertToAsg(
        __int64 a1,
        __int64 *a2)
{
  int v4; // eax
  LPVOID v5; // r15
  int v6; // eax
  _OWORD *v7; // rsi
  __int64 v8; // rcx
  int v9; // eax
  LPVOID v10; // r14
  int v11; // eax
  volatile signed __int32 *v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // eax
  LPVOID v17; // rsi
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  LPVOID v21; // rdi
  int v22; // eax
  LPVOID v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // r12d
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-69h] BYREF
  __int128 v30; // [rsp+28h] [rbp-61h] BYREF
  __int64 v31; // [rsp+38h] [rbp-51h]
  __int64 v32; // [rsp+40h] [rbp-49h]
  __int64 v33; // [rsp+48h] [rbp-41h] BYREF
  LPVOID v34; // [rsp+50h] [rbp-39h] BYREF
  LPVOID v35[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v36; // [rsp+68h] [rbp-21h]
  LPVOID v37; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v38[4]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v39; // [rsp+98h] [rbp+Fh] BYREF

  v38[1] = a1;
  v36 = *a2;
  lpMem = 0;
  LODWORD(v30) = 373;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v36 + 64LL))(v36, &lpMem);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v4, &v30);
  }
  v5 = lpMem;
  v38[0] = lpMem;
  v39 = 0;
  LODWORD(v30) = 977;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)lpMem + 48LL))(lpMem, &v39);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, &v30);
  }
  *(_OWORD *)a1 = v39;
  v7 = (_OWORD *)(a1 + 16);
  v35[0] = (LPVOID)(a1 + 16);
  lpMem = 0;
  v8 = *a2;
  LODWORD(v30) = 373;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 64LL))(v8, &lpMem);
  if ( v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9, &v30);
  }
  v10 = lpMem;
  v37 = lpMem;
  lpMem = 0;
  LODWORD(v30) = 995;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v37 + 56LL))(v37, &lpMem);
  if ( v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, &v30);
  }
  v12 = (volatile signed __int32 *)lpMem;
  v38[3] = lpMem;
  if ( lpMem )
    v13 = (const wchar_t *)*((_QWORD *)lpMem + 2);
  else
    v13 = &String;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  *v7 = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 7;
  *(_WORD *)v7 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v30);
  asg::SemanticPipelines::RegionId::SetValue(a1 + 16, &v30);
  lpMem = 0;
  v15 = *a2;
  LODWORD(v30) = 373;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 64LL))(v15, &lpMem);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, &v30);
  }
  v17 = lpMem;
  v35[0] = lpMem;
  v33 = 0;
  LODWORD(v30) = 1047;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v18 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)lpMem + 80LL))(lpMem, &v33);
  if ( v18 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v18, &v30);
  }
  lpMem = 0;
  v19 = *a2;
  LODWORD(v30) = 373;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v19 + 64LL))(v19, &lpMem);
  if ( v20 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v20, &v30);
  }
  v21 = lpMem;
  v34 = lpMem;
  lpMem = 0;
  LODWORD(v30) = 1065;
  *((_QWORD *)&v30 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v31 = 0;
  v22 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v34 + 88LL))(v34, &lpMem);
  _mm_lfence();
  if ( v22 < 0 )
    winrt::throw_hresult((unsigned int)v22, &v30);
  v23 = lpMem;
  *(_QWORD *)(a1 + 48) = v33;
  *(_QWORD *)(a1 + 56) = v23;
  *(_BYTE *)(a1 + 64) = 1;
  v24 = v36 + 48;
  if ( !v36 )
    v24 = 64;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v25 = *(_QWORD *)(v24 + 8);
  if ( v25 )
    _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
  *(_QWORD *)(a1 + 72) = *(_QWORD *)v24;
  *(_QWORD *)(a1 + 80) = *(_QWORD *)(v24 + 8);
  if ( v21 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v34);
  if ( v17 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v35);
  if ( v12 )
  {
    v26 = _InterlockedDecrement(v12 + 6);
    if ( v26 )
    {
      if ( v26 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
    }
  }
  if ( v10 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v37);
  if ( v5 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v38);
  return a1;
}

```

## disassembly

```asm
0x18006a9b0  mov     [rsp-8+arg_10], rbx
0x18006a9b5  push    rbp
0x18006a9b6  push    rsi
0x18006a9b7  push    rdi
0x18006a9b8  push    r12
0x18006a9ba  push    r13
0x18006a9bc  push    r14
0x18006a9be  push    r15
0x18006a9c0  lea     rbp, [rsp-27h]
0x18006a9c5  sub     rsp, 0B0h
0x18006a9cc  mov     rax, cs:__security_cookie
0x18006a9d3  xor     rax, rsp
0x18006a9d6  mov     [rbp+57h+var_38], rax
0x18006a9da  mov     rdi, rdx
0x18006a9dd  mov     r13, rcx
0x18006a9e0  mov     [rbp+57h+var_60], rcx
0x18006a9e4  xor     ebx, ebx
0x18006a9e6  mov     rcx, [rdx]
0x18006a9e9  mov     [rbp+57h+var_78], rcx
0x18006a9ed  mov     [rbp+57h+lpMem], rbx
0x18006a9f1  mov     dword ptr [rbp+57h+var_B8], 175h
0x18006a9f8  lea     r12, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18006a9ff  mov     qword ptr [rbp+57h+var_B8+8], r12
0x18006aa03  mov     [rbp+57h+var_A8], rbx
0x18006aa07  mov     rax, [rcx]
0x18006aa0a  lea     rdx, [rbp+57h+lpMem]
0x18006aa0e  mov     rax, [rax+40h]
0x18006aa12  call    cs:__guard_dispatch_icall_fptr
0x18006aa18  test    eax, eax
0x18006aa1a  js      loc_18006AD1D
0x18006aa20  mov     r15, [rbp+57h+lpMem]
0x18006aa24  mov     [rbp+57h+var_68], r15
0x18006aa28  xorps   xmm0, xmm0
0x18006aa2b  movups  [rbp+57h+var_48], xmm0
0x18006aa2f  mov     dword ptr [rbp+57h+var_B8], 3D1h
0x18006aa36  mov     qword ptr [rbp+57h+var_B8+8], r12
0x18006aa3a  mov     [rbp+57h+var_A8], rbx
0x18006aa3e  mov     rax, [r15]
0x18006aa41  lea     rdx, [rbp+57h+var_48]
0x18006aa45  mov     rcx, r15
0x18006aa48  mov     rax, [rax+30h]
0x18006aa4c  call    cs:__guard_dispatch_icall_fptr
0x18006aa52  test    eax, eax
0x18006aa54  js      loc_18006AD2C
0x18006aa5a  movups  xmm0, [rbp+57h+var_48]
0x18006aa5e  movups  xmmword ptr [r13+0], xmm0
0x18006aa63  lea     rsi, [r13+10h]
0x18006aa67  mov     [rbp+57h+var_88], rsi
0x18006aa6b  mov     [rbp+57h+lpMem], rbx
0x18006aa6f  mov     rcx, [rdi]
0x18006aa72  mov     dword ptr [rbp+57h+var_B8], 175h
0x18006aa79  mov     qword ptr [rbp+57h+var_B8+8], r12
0x18006aa7d  mov     [rbp+57h+var_A8], rbx
0x18006aa81  mov     rax, [rcx]
0x18006aa84  lea     rdx, [rbp+57h+lpMem]
0x18006aa88  mov     rax, [rax+40h]
0x18006aa8c  call    cs:__guard_dispatch_icall_fptr
0x18006aa92  test    eax, eax
0x18006aa94  js      loc_18006AD3B
0x18006aa9a  mov     r14, [rbp+57h+lpMem]
0x18006aa9e  mov     [rbp+57h+var_70], r14
0x18006aaa2  mov     [rbp+57h+lpMem], rbx
0x18006aaa6  mov     dword ptr [rbp+57h+var_B8], 3E3h
0x18006aaad  mov     qword ptr [rbp+57h+var_B8+8], r12
0x18006aab1  mov     [rbp+57h+var_A8], rbx
0x18006aab5  mov     rax, [r14]
0x18006aab8  lea     rdx, [rbp+57h+lpMem]
0x18006aabc  mov     rcx, r14
0x18006aabf  mov     rax, [rax+38h]
0x18006aac3  call    cs:__guard_dispatch_icall_fptr
0x18006aac9  test    eax, eax
0x18006aacb  js      loc_18006AD4A
0x18006aad1  mov     rbx, [rbp+57h+lpMem]
0x18006aad5  mov     [rbp+57h+var_50], rbx
0x18006aad9  test    rbx, rbx
0x18006aadc  jz      short loc_18006AAE4
0x18006aade  mov     rdx, [rbx+10h]
0x18006aae2  jmp     short loc_18006AAEB
0x18006aae4  lea     rdx, String
0x18006aaeb  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18006aaf2  mov     r8, r12
0x18006aaf5  inc     r8
0x18006aaf8  cmp     word ptr [rdx+r8*2], 0
0x18006aafe  jnz     short loc_18006AAF5
0x18006ab00  xorps   xmm0, xmm0
0x18006ab03  movups  xmmword ptr [rsi], xmm0
0x18006ab06  xor     ecx, ecx
0x18006ab08  mov     [rsi+10h], rcx
0x18006ab0c  mov     qword ptr [rsi+18h], 7
0x18006ab14  mov     [rsi], cx
0x18006ab17  movups  [rbp+57h+var_B8], xmm0
0x18006ab1b  mov     [rbp+57h+var_A8], rcx
0x18006ab1f  mov     [rbp+57h+var_A0], rcx
0x18006ab23  lea     rcx, [rbp+57h+var_B8]
0x18006ab27  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18006ab2c  lea     rdx, [rbp+57h+var_B8]
0x18006ab30  mov     rcx, rsi
0x18006ab33  call    ?SetValue@RegionId@SemanticPipelines@asg@@AEAAXV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@@Z; asg::SemanticPipelines::RegionId::SetValue(std::basic_string<char16_t>)
0x18006ab38  nop
0x18006ab39  xor     eax, eax
0x18006ab3b  mov     [rbp+57h+lpMem], rax
0x18006ab3f  mov     rcx, [rdi]
0x18006ab42  mov     dword ptr [rbp+57h+var_B8], 175h
0x18006ab49  lea     rdx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18006ab50  mov     qword ptr [rbp+57h+var_B8+8], rdx
0x18006ab54  mov     [rbp+57h+var_A8], rax
0x18006ab58  mov     rax, [rcx]
0x18006ab5b  lea     rdx, [rbp+57h+lpMem]
0x18006ab5f  mov     rax, [rax+40h]
0x18006ab63  call    cs:__guard_dispatch_icall_fptr
0x18006ab69  test    eax, eax
0x18006ab6b  js      loc_18006AD59
0x18006ab71  mov     rsi, [rbp+57h+lpMem]
0x18006ab75  mov     [rbp+57h+var_88], rsi
0x18006ab79  xor     eax, eax
0x18006ab7b  mov     [rbp+57h+var_98], rax
0x18006ab7f  mov     dword ptr [rbp+57h+var_B8], 417h
0x18006ab86  lea     rcx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18006ab8d  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x18006ab91  mov     [rbp+57h+var_A8], rax
0x18006ab95  mov     rax, [rsi]
0x18006ab98  lea     rdx, [rbp+57h+var_98]
0x18006ab9c  mov     rcx, rsi
0x18006ab9f  mov     rax, [rax+50h]
0x18006aba3  call    cs:__guard_dispatch_icall_fptr
0x18006aba9  test    eax, eax
0x18006abab  js      loc_18006AD68
0x18006abb1  xor     eax, eax
0x18006abb3  mov     [rbp+57h+lpMem], rax
0x18006abb7  mov     rcx, [rdi]
0x18006abba  mov     dword ptr [rbp+57h+var_B8], 175h
0x18006abc1  lea     rdx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18006abc8  mov     qword ptr [rbp+57h+var_B8+8], rdx
0x18006abcc  mov     [rbp+57h+var_A8], rax
0x18006abd0  mov     rax, [rcx]
0x18006abd3  lea     rdx, [rbp+57h+lpMem]
0x18006abd7  mov     rax, [rax+40h]
0x18006abdb  call    cs:__guard_dispatch_icall_fptr
0x18006abe1  test    eax, eax
0x18006abe3  js      loc_18006AD77
0x18006abe9  mov     rdi, [rbp+57h+lpMem]
0x18006abed  mov     [rbp+57h+var_90], rdi
0x18006abf1  xor     eax, eax
0x18006abf3  mov     [rbp+57h+lpMem], rax
0x18006abf7  mov     dword ptr [rbp+57h+var_B8], 429h
0x18006abfe  lea     rcx, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18006ac05  mov     qword ptr [rbp+57h+var_B8+8], rcx
0x18006ac09  mov     [rbp+57h+var_A8], rax
0x18006ac0d  mov     rax, [rdi]
0x18006ac10  lea     rdx, [rbp+57h+lpMem]
0x18006ac14  mov     rcx, rdi
0x18006ac17  mov     rax, [rax+58h]
0x18006ac1b  call    cs:__guard_dispatch_icall_fptr
0x18006ac21  lfence
0x18006ac24  test    eax, eax
0x18006ac26  js      loc_18006AD0B
0x18006ac2c  mov     rcx, [rbp+57h+lpMem]
0x18006ac30  mov     rax, [rbp+57h+var_98]
0x18006ac34  mov     [r13+30h], rax
0x18006ac38  mov     [r13+38h], rcx
0x18006ac3c  mov     byte ptr [r13+40h], 1
0x18006ac41  mov     rax, [rbp+57h+var_78]
0x18006ac45  lea     rcx, [rax+30h]
0x18006ac49  mov     edx, 40h ; '@'
0x18006ac4e  test    rax, rax
0x18006ac51  cmovz   rcx, rdx
0x18006ac55  xor     eax, eax
0x18006ac57  mov     [r13+48h], rax
0x18006ac5b  mov     [r13+50h], rax
0x18006ac5f  mov     rax, [rcx+8]
0x18006ac63  test    rax, rax
0x18006ac66  jz      short loc_18006AC6C
0x18006ac68  lock inc dword ptr [rax+8]
0x18006ac6c  mov     rax, [rcx]
0x18006ac6f  mov     [r13+48h], rax
0x18006ac73  mov     rax, [rcx+8]
0x18006ac77  mov     [r13+50h], rax
0x18006ac7b  test    rdi, rdi
0x18006ac7e  jz      short loc_18006AC8A
0x18006ac80  lea     rcx, [rbp+57h+var_90]
0x18006ac84  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18006ac89  nop
0x18006ac8a  test    rsi, rsi
0x18006ac8d  jz      short loc_18006AC99
0x18006ac8f  lea     rcx, [rbp+57h+var_88]
0x18006ac93  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18006ac98  nop
0x18006ac99  test    rbx, rbx
0x18006ac9c  jz      short loc_18006ACBD
0x18006ac9e  lock xadd [rbx+18h], r12d
0x18006aca4  sub     r12d, 1
0x18006aca8  jnz     short loc_18006AD04
0x18006acaa  call    WINRT_IMPL_GetProcessHeap
0x18006acaf  mov     rcx, rax; hHeap
0x18006acb2  mov     r8, rbx; lpMem
0x18006acb5  xor     edx, edx; dwFlags
0x18006acb7  call    WINRT_IMPL_HeapFree
0x18006acbc  nop
0x18006acbd  test    r14, r14
0x18006acc0  jz      short loc_18006ACCC
0x18006acc2  lea     rcx, [rbp+57h+var_70]
0x18006acc6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18006accb  nop
0x18006accc  test    r15, r15
0x18006accf  jz      short loc_18006ACDA
0x18006acd1  lea     rcx, [rbp+57h+var_68]
0x18006acd5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18006acda  mov     rax, r13
0x18006acdd  mov     rcx, [rbp+57h+var_38]
0x18006ace1  xor     rcx, rsp; StackCookie
0x18006ace4  call    __security_check_cookie
0x18006ace9  mov     rbx, [rsp+0E0h+arg_10]
0x18006acf1  add     rsp, 0B0h
0x18006acf8  pop     r15
0x18006acfa  pop     r14
0x18006acfc  pop     r13
0x18006acfe  pop     r12
0x18006ad00  pop     rdi
0x18006ad01  pop     rsi
0x18006ad02  pop     rbp
0x18006ad03  retn
0x18006ad04  test    r12d, r12d
0x18006ad07  js      short loc_18006AD17
0x18006ad09  jmp     short loc_18006ACBD
0x18006ad0b  lea     rdx, [rbp+57h+var_B8]
0x18006ad0f  mov     ecx, eax
0x18006ad11  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad17  call    abort
0x18006ad1d  lfence
0x18006ad20  lea     rdx, [rbp+57h+var_B8]
0x18006ad24  mov     ecx, eax
0x18006ad26  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad2c  lfence
0x18006ad2f  lea     rdx, [rbp+57h+var_B8]
0x18006ad33  mov     ecx, eax
0x18006ad35  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad3b  lfence
0x18006ad3e  lea     rdx, [rbp+57h+var_B8]
0x18006ad42  mov     ecx, eax
0x18006ad44  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad4a  lfence
0x18006ad4d  lea     rdx, [rbp+57h+var_B8]
0x18006ad51  mov     ecx, eax
0x18006ad53  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad59  lfence
0x18006ad5c  lea     rdx, [rbp+57h+var_B8]
0x18006ad60  mov     ecx, eax
0x18006ad62  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad68  lfence
0x18006ad6b  lea     rdx, [rbp+57h+var_B8]
0x18006ad6f  mov     ecx, eax
0x18006ad71  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18006ad77  lfence
0x18006ad7a  lea     rdx, [rbp+57h+var_B8]
0x18006ad7e  mov     ecx, eax
0x18006ad80  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

# ResolverData::StoreInWdi(void *)

- ea: `0x18000595c`
- end: `0x180005b13`
- name: `?StoreInWdi@ResolverData@@QEAAJPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(ResolverData *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003ac8`

## callees

- `0x180002590`
- `0x18000595c`

## import_xrefs

- `wdi!WdiAddParameter` at `0x1800059db`
- `wdi!WdiAddParameter` at `0x180005a1c`
- `wdi!WdiAddParameter` at `0x180005a51`
- `wdi!WdiAddParameter` at `0x180005a81`
- `wdi!WdiAddParameter` at `0x180005aae`
- `wdi!WdiAddParameter` at `0x180005adb`
- `wdi!WdiAddParameter` at `0x1800059db`
- `wdi!WdiAddParameter` at `0x180005a1c`
- `wdi!WdiAddParameter` at `0x180005a51`
- `wdi!WdiAddParameter` at `0x180005a81`
- `wdi!WdiAddParameter` at `0x180005aae`
- `wdi!WdiAddParameter` at `0x180005adb`

## string_xrefs

- `0x180005afa`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall ResolverData::StoreInWdi(ResolverData *this, void *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // r9
  int v8; // eax
  int v9; // r9d
  __int64 v10; // r9
  int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+70h] [rbp+18h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v14 = *((_DWORD *)this + 8);
  v13 = *((_DWORD *)this + 7);
  v12 = *((_DWORD *)this + 6);
  v15 = *((_QWORD *)this + 2);
  if ( a2 )
  {
    v4 = -1;
    v5 = *((_QWORD *)this + 1);
    if ( *(_QWORD *)this )
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(*(_QWORD *)this + 2 * v6) );
      v7 = (unsigned int)(2 * v6);
    }
    else
    {
      v7 = 0;
    }
    v8 = WdiAddParameter(a2, 0, L"ProductName", v7, *(_QWORD *)this);
    v3 = v8;
    if ( v8 >= 0 )
    {
      if ( v5 )
      {
        do
          ++v4;
        while ( *(_WORD *)(v5 + 2 * v4) );
        v10 = (unsigned int)(2 * v4);
      }
      else
      {
        v10 = 0;
      }
      v8 = WdiAddParameter(a2, 0, L"ProductVersion", v10, v5);
      v3 = v8;
      if ( v8 >= 0 )
      {
        v8 = WdiAddParameter(a2, 0, L"OnScreenTime", 4, &v15);
        v3 = v8;
        if ( v8 >= 0 )
        {
          v8 = WdiAddParameter(a2, 0, L"UiUserAction", 4, &v12);
          v3 = v8;
          if ( v8 >= 0 )
          {
            v8 = WdiAddParameter(a2, 0, L"ResolverResult", 4, &v13);
            v3 = v8;
            if ( v8 >= 0 )
            {
              v8 = WdiAddParameter(a2, 0, L"ResolverError", 4, &v14);
              v3 = v8;
              if ( v8 >= 0 )
                return v3;
              v9 = 418;
            }
            else
            {
              v9 = 410;
            }
          }
          else
          {
            v9 = 402;
          }
        }
        else
        {
          v9 = 394;
        }
      }
      else
      {
        v9 = 386;
      }
    }
    else
    {
      v9 = 378;
    }
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::StoreInWdi", v9, v8);
    return v3;
  }
  v3 = -2147024809;
  DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "ResolverData::StoreInWdi", 370, -2147024809);
  return v3;
}

```

## disassembly

```asm
0x18000595c  push    rbx
0x18000595e  push    rbp
0x18000595f  push    rsi
0x180005960  push    rdi
0x180005961  push    r14
0x180005963  sub     rsp, 30h
0x180005967  mov     eax, [rcx+20h]
0x18000596a  xor     r14d, r14d
0x18000596d  mov     [rsp+58h+arg_10], eax
0x180005971  mov     rsi, rdx
0x180005974  mov     eax, [rcx+1Ch]
0x180005977  mov     [rsp+58h+arg_8], eax
0x18000597b  mov     eax, [rcx+18h]
0x18000597e  mov     [rsp+58h+arg_0], eax
0x180005982  mov     rax, [rcx+10h]
0x180005986  mov     [rsp+58h+arg_18], rax
0x18000598b  test    rdx, rdx
0x18000598e  jnz     short loc_1800059A4
0x180005990  mov     ebx, 80070057h
0x180005995  mov     r9d, 172h
0x18000599b  mov     dword ptr [rsp+58h+var_38], ebx
0x18000599f  jmp     loc_180005AF1
0x1800059a4  mov     rdx, [rcx]
0x1800059a7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800059ab  mov     rbp, [rcx+8]
0x1800059af  test    rdx, rdx
0x1800059b2  jz      short loc_1800059C7
0x1800059b4  mov     rax, rdi
0x1800059b7  inc     rax
0x1800059ba  cmp     [rdx+rax*2], r14w
0x1800059bf  jnz     short loc_1800059B7
0x1800059c1  lea     r9d, [rax+rax]
0x1800059c5  jmp     short loc_1800059CA
0x1800059c7  mov     r9d, r14d
0x1800059ca  mov     [rsp+58h+var_38], rdx
0x1800059cf  lea     r8, aProductname; "ProductName"
0x1800059d6  xor     edx, edx
0x1800059d8  mov     rcx, rsi
0x1800059db  call    cs:__imp_WdiAddParameter
0x1800059e1  mov     ebx, eax
0x1800059e3  test    eax, eax
0x1800059e5  jns     short loc_1800059F2
0x1800059e7  mov     r9d, 17Ah
0x1800059ed  jmp     loc_180005AED
0x1800059f2  test    rbp, rbp
0x1800059f5  jz      short loc_180005A08
0x1800059f7  inc     rdi
0x1800059fa  cmp     [rbp+rdi*2+0], r14w
0x180005a00  jnz     short loc_1800059F7
0x180005a02  lea     r9d, [rdi+rdi]
0x180005a06  jmp     short loc_180005A0B
0x180005a08  mov     r9d, r14d
0x180005a0b  lea     r8, aProductversion; "ProductVersion"
0x180005a12  mov     [rsp+58h+var_38], rbp
0x180005a17  xor     edx, edx
0x180005a19  mov     rcx, rsi
0x180005a1c  call    cs:__imp_WdiAddParameter
0x180005a22  mov     ebx, eax
0x180005a24  test    eax, eax
0x180005a26  jns     short loc_180005A33
0x180005a28  mov     r9d, 182h
0x180005a2e  jmp     loc_180005AED
0x180005a33  lea     rax, [rsp+58h+arg_18]
0x180005a38  mov     edi, 4
0x180005a3d  mov     r9d, edi
0x180005a40  mov     [rsp+58h+var_38], rax
0x180005a45  lea     r8, aOnscreentime; "OnScreenTime"
0x180005a4c  xor     edx, edx
0x180005a4e  mov     rcx, rsi
0x180005a51  call    cs:__imp_WdiAddParameter
0x180005a57  mov     ebx, eax
0x180005a59  test    eax, eax
0x180005a5b  jns     short loc_180005A68
0x180005a5d  mov     r9d, 18Ah
0x180005a63  jmp     loc_180005AED
0x180005a68  lea     rax, [rsp+58h+arg_0]
0x180005a6d  mov     r9d, edi
0x180005a70  lea     r8, aUiuseraction; "UiUserAction"
0x180005a77  mov     [rsp+58h+var_38], rax
0x180005a7c  xor     edx, edx
0x180005a7e  mov     rcx, rsi
0x180005a81  call    cs:__imp_WdiAddParameter
0x180005a87  mov     ebx, eax
0x180005a89  test    eax, eax
0x180005a8b  jns     short loc_180005A95
0x180005a8d  mov     r9d, 192h
0x180005a93  jmp     short loc_180005AED
0x180005a95  lea     rax, [rsp+58h+arg_8]
0x180005a9a  mov     r9d, edi
0x180005a9d  lea     r8, aResolverresult; "ResolverResult"
0x180005aa4  mov     [rsp+58h+var_38], rax
0x180005aa9  xor     edx, edx
0x180005aab  mov     rcx, rsi
0x180005aae  call    cs:__imp_WdiAddParameter
0x180005ab4  mov     ebx, eax
0x180005ab6  test    eax, eax
0x180005ab8  jns     short loc_180005AC2
0x180005aba  mov     r9d, 19Ah
0x180005ac0  jmp     short loc_180005AED
0x180005ac2  lea     rax, [rsp+58h+arg_10]
0x180005ac7  mov     r9d, edi
0x180005aca  lea     r8, aResolvererror; "ResolverError"
0x180005ad1  mov     [rsp+58h+var_38], rax
0x180005ad6  xor     edx, edx
0x180005ad8  mov     rcx, rsi
0x180005adb  call    cs:__imp_WdiAddParameter
0x180005ae1  mov     ebx, eax
0x180005ae3  test    eax, eax
0x180005ae5  jns     short loc_180005B06
0x180005ae7  mov     r9d, 1A2h
0x180005aed  mov     dword ptr [rsp+58h+var_38], eax
0x180005af1  lea     r8, aResolverdataSt; "ResolverData::StoreInWdi"
0x180005af8  xor     ecx, ecx; Level
0x180005afa  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180005b01  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180005b06  mov     eax, ebx
0x180005b08  add     rsp, 30h
0x180005b0c  pop     r14
0x180005b0e  pop     rdi
0x180005b0f  pop     rsi
0x180005b10  pop     rbp
0x180005b11  pop     rbx
0x180005b12  retn
```

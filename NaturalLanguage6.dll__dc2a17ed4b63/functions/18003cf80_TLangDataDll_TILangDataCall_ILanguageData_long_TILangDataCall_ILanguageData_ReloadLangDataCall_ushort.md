# TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::ReloadLangDataCall(ushort)

- ea: `0x18003cf80`
- end: `0x18003d194`
- name: `?ReloadLangDataCall@?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@QEAA_NG@Z`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180001b1c`

## callees

- `0x180035640`
- `0x18003cf80`
- `0x18003d1a0`
- `0x18003ed6c`
- `0x18004ed80`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d022`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d022`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::ReloadLangDataCall(
        __int64 a1,
        __int16 a2)
{
  HINSTANCE v4; // rdx
  FARPROC ProcAddress; // rax
  int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  __int64 (__fastcall ***v12)(_QWORD); // [rsp+20h] [rbp-308h] BYREF
  __int64 v13; // [rsp+28h] [rbp-300h]
  unsigned int v14; // [rsp+30h] [rbp-2F8h]
  __int64 v15; // [rsp+38h] [rbp-2F0h]
  unsigned int v16; // [rsp+40h] [rbp-2E8h]
  __int64 v17; // [rsp+48h] [rbp-2E0h]
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-2C8h] BYREF
  _BYTE v19[64]; // [rsp+A0h] [rbp-288h] BYREF
  void **v20; // [rsp+E0h] [rbp-248h] BYREF
  HMODULE hModule; // [rsp+E8h] [rbp-240h]
  int v22; // [rsp+F0h] [rbp-238h]
  __int16 v23; // [rsp+F4h] [rbp-234h]
  __int64 v24; // [rsp+300h] [rbp-28h]
  char v25; // [rsp+308h] [rbp-20h]
  int v26; // [rsp+30Ch] [rbp-1Ch]
  const void *retaddr; // [rsp+328h] [rbp+0h]

  v17 = -2;
  v20 = &CDll::`vftable';
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v26 = 2006971176;
  hModule = 0;
  v23 = 0;
  v4 = *(HINSTANCE *)(a1 + 16);
  if ( v4 && (CDll::Attach((CDll *)&v20, v4, 0), (ProcAddress = GetProcAddress(hModule, "LangDataCall")) != 0) )
  {
    v12 = 0;
    v6 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(&v12);
    if ( v6 < 0 )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)v6, retaddr);
      throw (CNLException *)pExceptionObject;
    }
    LOWORD(v14) = a2;
    HIWORD(v14) = a2;
    v13 = 0x1F80500028003LL;
    v7 = (**v12)(v12);
    v8 = v13 - *(_QWORD *)v7;
    if ( v13 == *(_QWORD *)v7 )
      v8 = v14 - (unsigned __int64)*(unsigned int *)(v7 + 8);
    if ( v8 )
    {
      LOWORD(v16) = a2 & 0x3FF;
      HIWORD(v16) = a2 & 0x3FF;
      v15 = 0x1F80500028003LL;
      v9 = (**v12)(v12);
      v10 = v15 - *(_QWORD *)v9;
      if ( v15 == *(_QWORD *)v9 )
        v10 = v16 - (unsigned __int64)*(unsigned int *)(v9 + 8);
      if ( v10 )
      {
        CNLException::CNLException((CNLException *)v19, 3241218065LL, retaddr);
        throw (CNLException *)v19;
      }
    }
    *(_QWORD *)(a1 + 24) = v12;
    v20 = &CDll::`vftable';
    CDll::Unload((CDll *)&v20);
    return 1;
  }
  else
  {
    v20 = &CDll::`vftable';
    CDll::Unload((CDll *)&v20);
    return 0;
  }
}

```

## disassembly

```asm
0x18003cf80  mov     r11, rsp
0x18003cf83  push    rdi
0x18003cf84  sub     rsp, 320h
0x18003cf8b  mov     [rsp+328h+var_2E0], 0FFFFFFFFFFFFFFFEh
0x18003cf94  mov     [r11+10h], rbx
0x18003cf98  mov     [r11+18h], rsi
0x18003cf9c  mov     rax, cs:__security_cookie
0x18003cfa3  xor     rax, rsp
0x18003cfa6  mov     [rsp+328h+var_18], rax
0x18003cfae  movzx   esi, dx
0x18003cfb1  mov     rdi, rcx
0x18003cfb4  lea     rbx, ??_7CDll@@6B@; const CDll::`vftable'
0x18003cfbb  mov     [r11-248h], rbx
0x18003cfc2  mov     [rsp+328h+var_238], 0
0x18003cfcd  mov     qword ptr [r11-28h], 0
0x18003cfd5  mov     byte ptr [r11-20h], 1
0x18003cfda  mov     dword ptr [r11-1Ch], 779FF328h
0x18003cfe2  mov     qword ptr [r11-240h], 0
0x18003cfed  xor     eax, eax
0x18003cfef  mov     [rsp+328h+var_234], ax
0x18003cff7  mov     rdx, [rcx+10h]; HINSTANCE
0x18003cffb  test    rdx, rdx
0x18003cffe  jz      loc_18003D14B
0x18003d004  xor     r8d, r8d; bool
0x18003d007  lea     rcx, [r11-248h]; this
0x18003d00e  call    ?Attach@CDll@@UEAAXPEAUHINSTANCE__@@_N@Z; CDll::Attach(HINSTANCE__ *,bool)
0x18003d013  lea     rdx, ProcName; "LangDataCall"
0x18003d01a  mov     rcx, [rsp+328h+hModule]; hModule
0x18003d022  call    cs:__imp_GetProcAddress
0x18003d028  test    rax, rax
0x18003d02b  jz      loc_18003D14B
0x18003d031  mov     [rsp+328h+var_308], 0
0x18003d03a  lea     rcx, [rsp+328h+var_308]
0x18003d03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d044  test    eax, eax
0x18003d046  jns     short loc_18003D06D
0x18003d048  mov     r8, [rsp+328h]; void *
0x18003d050  mov     edx, eax; int
0x18003d052  lea     rcx, [rsp+328h+pExceptionObject]; this
0x18003d057  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003d05c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003d063  lea     rcx, [rsp+328h+pExceptionObject]; pExceptionObject
0x18003d068  call    _CxxThrowException_0
0x18003d06d  mov     word ptr [rsp+328h+var_2F8], si
0x18003d072  mov     word ptr [rsp+328h+var_2F8+2], si
0x18003d077  mov     dword ptr [rsp+328h+var_300], 28003h
0x18003d07f  mov     dword ptr [rsp+328h+var_300+4], 1F805h
0x18003d087  mov     rcx, [rsp+328h+var_308]
0x18003d08c  mov     rax, [rcx]
0x18003d08f  mov     rax, [rax]
0x18003d092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d097  mov     rcx, [rsp+328h+var_300]
0x18003d09c  sub     rcx, [rax]
0x18003d09f  jnz     short loc_18003D0AB
0x18003d0a1  mov     ecx, [rsp+328h+var_2F8]
0x18003d0a5  mov     eax, [rax+8]
0x18003d0a8  sub     rcx, rax
0x18003d0ab  test    rcx, rcx
0x18003d0ae  jz      short loc_18003D129
0x18003d0b0  mov     eax, 3FFh
0x18003d0b5  and     si, ax
0x18003d0b8  mov     word ptr [rsp+328h+var_2E8], si
0x18003d0bd  mov     word ptr [rsp+328h+var_2E8+2], si
0x18003d0c2  mov     dword ptr [rsp+328h+var_2F0], 28003h
0x18003d0ca  mov     dword ptr [rsp+328h+var_2F0+4], 1F805h
0x18003d0d2  mov     rcx, [rsp+328h+var_308]
0x18003d0d7  mov     rax, [rcx]
0x18003d0da  mov     rax, [rax]
0x18003d0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0e2  mov     rcx, [rsp+328h+var_2F0]
0x18003d0e7  sub     rcx, [rax]
0x18003d0ea  jnz     short loc_18003D0F6
0x18003d0ec  mov     ecx, [rsp+328h+var_2E8]
0x18003d0f0  mov     eax, [rax+8]
0x18003d0f3  sub     rcx, rax
0x18003d0f6  test    rcx, rcx
0x18003d0f9  jz      short loc_18003D129
0x18003d0fb  mov     r8, [rsp+328h]; void *
0x18003d103  mov     edx, 0C1311011h; int
0x18003d108  lea     rcx, [rsp+328h+var_288]; this
0x18003d110  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003d115  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003d11c  lea     rcx, [rsp+328h+var_288]; pExceptionObject
0x18003d124  call    _CxxThrowException_0
0x18003d129  mov     rcx, [rsp+328h+var_308]
0x18003d12e  mov     [rdi+18h], rcx
0x18003d132  mov     [rsp+328h+var_248], rbx
0x18003d13a  lea     rcx, [rsp+328h+var_248]; this
0x18003d142  call    ?Unload@CDll@@MEAA_NXZ; CDll::Unload(void)
0x18003d147  mov     al, 1
0x18003d149  jmp     short loc_18003D16F
0x18003d14b  jmp     short loc_18003D158
0x18003d14d  jmp     short loc_18003D151
0x18003d14f  jmp     short $+2
0x18003d151  lea     rbx, ??_7CDll@@6B@; const CDll::`vftable'
0x18003d158  mov     [rsp+328h+var_248], rbx
0x18003d160  lea     rcx, [rsp+328h+var_248]; this
0x18003d168  call    ?Unload@CDll@@MEAA_NXZ; CDll::Unload(void)
0x18003d16d  xor     al, al
0x18003d16f  mov     rcx, [rsp+328h+var_18]
0x18003d177  xor     rcx, rsp; StackCookie
0x18003d17a  call    __security_check_cookie
0x18003d17f  lea     r11, [rsp+328h+var_8]
0x18003d187  mov     rbx, [r11+18h]
0x18003d18b  mov     rsi, [r11+20h]
0x18003d18f  mov     rsp, r11
0x18003d192  pop     rdi
0x18003d193  retn
```

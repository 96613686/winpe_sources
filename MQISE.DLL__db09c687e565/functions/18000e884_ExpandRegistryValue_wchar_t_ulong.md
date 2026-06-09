# ExpandRegistryValue(wchar_t *,ulong)

- ea: `0x18000e884`
- end: `0x18000eb6a`
- name: `?ExpandRegistryValue@@YAXPEA_WK@Z`
- size: `742`
- prototype: `void __fastcall(LPWSTR lpDst, DWORD nSize)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000ecf8`

## callees

- `0x180001c0c`
- `0x18000dbb4`
- `0x18000ddd4`
- `0x18000e76c`
- `0x18000e884`
- `0x18000f374`
- `0x18000f5f0`
- `0x18000f680`
- `0x180011010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000e9d4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000e9d4`
- `KERNEL32!GetLastError` at `0x18000eab3`
- `KERNEL32!GetLastError` at `0x18000ead8`
- `KERNEL32!GetLastError` at `0x18000eb3c`
- `KERNEL32!GetLastError` at `0x18000eab3`
- `KERNEL32!GetLastError` at `0x18000ead8`
- `KERNEL32!GetLastError` at `0x18000eb3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ExpandRegistryValue(LPWSTR lpDst, DWORD nSize)
{
  __int64 v4; // r15
  unsigned __int64 v5; // rdi
  const WCHAR *v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  WCHAR *v11; // rax
  int v12; // edi
  __int64 v13; // rax
  LPWSTR v14; // rcx
  WCHAR *v15; // rdx
  WCHAR v16; // r8
  WCHAR *v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rdx
  DWORD LastError; // eax
  signed int v21; // eax
  signed int v22; // eax
  _DWORD v23[12]; // [rsp+0h] [rbp-30h] BYREF
  int v24; // [rsp+30h] [rbp+0h] BYREF
  const WCHAR *v25; // [rsp+38h] [rbp+8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp+10h] BYREF

  v25 = 0;
  v4 = nSize;
  v5 = 2LL * nSize;
  if ( v5 > 0xFFFFFFFF )
  {
    v24 = -2147024362;
    throw (long *)&v24;
  }
  v6 = 0;
  if ( !(_DWORD)v5
    || (unsigned int)v5 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v5 + g_ulAdditionalProbeSize + 8 < (unsigned int)v5
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_49;
  }
  v7 = (unsigned int)v5 + 23LL;
  if ( v7 <= (unsigned __int64)(unsigned int)v5 + 8 )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
  v9 = alloca(v8);
  v10 = alloca(v8);
  v6 = (const WCHAR *)&v24;
  if ( v23 == (_DWORD *)-48LL || (v24 = 1801679955, (v6 = (const WCHAR *)&v25) == 0) )
  {
LABEL_49:
    if ( (unsigned __int64)(unsigned int)v5 + 8 >= (unsigned int)v5 )
    {
      v11 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v6 = v11;
      if ( v11 )
      {
        *(_DWORD *)v11 = 1885431112;
        v6 = v11 + 4;
      }
    }
  }
  v25 = v6;
  if ( !nSize )
  {
    v12 = -2147024809;
    goto LABEL_30;
  }
  if ( nSize > 0x7FFFFFFF )
  {
    v12 = -2147024809;
    *v6 = 0;
    goto LABEL_30;
  }
  v13 = 2147483646;
  v14 = lpDst;
  v15 = (WCHAR *)v6;
  do
  {
    if ( !v13 )
      break;
    v16 = *v14;
    if ( !*v14 )
      break;
    ++v14;
    *v15++ = v16;
    --v13;
    --v4;
  }
  while ( v4 );
  v12 = v4 == 0 ? 0x8007007A : 0;
  v17 = v15 - 1;
  if ( v4 )
    v17 = v15;
  *v17 = 0;
  if ( !v4 )
  {
LABEL_30:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids, nSize);
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v12);
    throw (registry_access_error *)pExceptionObject;
  }
  v18 = ExpandEnvironmentStringsW(v6, lpDst, nSize);
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids, LastError);
    }
    v21 = GetLastError();
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v21);
    throw (registry_access_error *)pExceptionObject;
  }
  if ( nSize < v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23[8] = v18;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids);
    }
    v22 = GetLastError();
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v22);
    throw (registry_access_error *)pExceptionObject;
  }
  if ( v6 && *((_DWORD *)v6 - 2) == 1885431112 )
    ((void (__fastcall *)(const WCHAR *, __int64, _QWORD))g_pfnFree)(v6 - 4, v19, v18);
}

```

## disassembly

```asm
0x18000e884  push    rbp
0x18000e886  push    rbx
0x18000e887  push    rsi
0x18000e888  push    rdi
0x18000e889  push    r12
0x18000e88b  push    r13
0x18000e88d  push    r14
0x18000e88f  push    r15
0x18000e891  sub     rsp, 78h
0x18000e895  lea     rbp, [rsp+30h]
0x18000e89a  mov     rax, cs:__security_cookie
0x18000e8a1  xor     rax, rbp
0x18000e8a4  mov     [rbp+80h+var_50], rax
0x18000e8a8  mov     esi, edx
0x18000e8aa  mov     r12, rcx
0x18000e8ad  xor     r13d, r13d
0x18000e8b0  mov     [rbp+80h+var_78], r13
0x18000e8b4  mov     r15d, edx
0x18000e8b7  lea     rdi, [rsi+rsi]
0x18000e8bb  mov     eax, 0FFFFFFFFh
0x18000e8c0  cmp     rdi, rax
0x18000e8c3  ja      loc_18000EA82
0x18000e8c9  mov     ebx, r13d
0x18000e8cc  test    edi, edi
0x18000e8ce  jz      short loc_18000E934
0x18000e8d0  mov     r14d, edi
0x18000e8d3  cmp     r14, cs:g_ulMaxStackAllocSize
0x18000e8da  ja      short loc_18000E934
0x18000e8dc  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000e8e3  add     rcx, 8
0x18000e8e7  add     rcx, r14
0x18000e8ea  cmp     rcx, r14
0x18000e8ed  jb      short loc_18000E934
0x18000e8ef  call    VerifyStackAvailable
0x18000e8f4  test    eax, eax
0x18000e8f6  jz      short loc_18000E934
0x18000e8f8  lea     rax, [r14+8]
0x18000e8fc  lea     rcx, [rax+0Fh]
0x18000e900  cmp     rcx, rax
0x18000e903  ja      short loc_18000E90F
0x18000e905  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000e90f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000e913  mov     rax, rcx
0x18000e916  call    _alloca_probe
0x18000e91b  sub     rsp, rcx
0x18000e91e  lea     rbx, [rsp+0B0h+var_80]
0x18000e923  test    rbx, rbx
0x18000e926  jz      short loc_18000E934
0x18000e928  mov     dword ptr [rbx], 6B637453h
0x18000e92e  add     rbx, 8
0x18000e932  jnz     short loc_18000E95D
0x18000e934  mov     eax, edi
0x18000e936  lea     rcx, [rax+8]
0x18000e93a  cmp     rcx, rax
0x18000e93d  jb      short loc_18000E95D
0x18000e93f  mov     rax, cs:g_pfnAllocate
0x18000e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94b  mov     rbx, rax
0x18000e94e  test    rax, rax
0x18000e951  jz      short loc_18000E95D
0x18000e953  mov     dword ptr [rax], 70616548h
0x18000e959  add     rbx, 8
0x18000e95d  mov     [rbp+80h+var_78], rbx
0x18000e961  test    esi, esi
0x18000e963  jz      loc_18000EA28
0x18000e969  cmp     esi, 7FFFFFFFh
0x18000e96f  jbe     short loc_18000E97B
0x18000e971  mov     edi, 80070057h
0x18000e976  jmp     loc_18000EA31
0x18000e97b  mov     eax, 7FFFFFFEh
0x18000e980  mov     rcx, r12
0x18000e983  mov     rdx, rbx
0x18000e986  test    rax, rax
0x18000e989  jz      short loc_18000E9AA
0x18000e98b  movzx   r8d, word ptr [rcx]
0x18000e98f  test    r8w, r8w
0x18000e993  jz      short loc_18000E9AA
0x18000e995  add     rcx, 2
0x18000e999  mov     [rdx], r8w
0x18000e99d  add     rdx, 2
0x18000e9a1  dec     rax
0x18000e9a4  sub     r15, 1
0x18000e9a8  jnz     short loc_18000E986
0x18000e9aa  mov     rax, r15
0x18000e9ad  neg     rax
0x18000e9b0  sbb     edi, edi
0x18000e9b2  not     edi
0x18000e9b4  and     edi, 8007007Ah
0x18000e9ba  lea     rcx, [rdx-2]
0x18000e9be  test    r15, r15
0x18000e9c1  cmovnz  rcx, rdx
0x18000e9c5  mov     [rcx], r13w
0x18000e9c9  jz      short loc_18000EA35
0x18000e9cb  mov     r8d, esi; nSize
0x18000e9ce  mov     rdx, r12; lpDst
0x18000e9d1  mov     rcx, rbx; lpSrc
0x18000e9d4  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e9da  mov     r8d, eax
0x18000e9dd  test    eax, eax
0x18000e9df  jz      loc_18000EA9A
0x18000e9e5  cmp     esi, eax
0x18000e9e7  jb      loc_18000EB06
0x18000e9ed  test    rbx, rbx
0x18000e9f0  jz      short loc_18000EA0B
0x18000e9f2  lea     rcx, [rbx-8]
0x18000e9f6  cmp     dword ptr [rcx], 70616548h
0x18000e9fc  jnz     short loc_18000EA0B
0x18000e9fe  mov     rax, cs:g_pfnFree
0x18000ea05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea0a  nop
0x18000ea0b  mov     rcx, [rbp+80h+var_50]
0x18000ea0f  xor     rcx, rbp; StackCookie
0x18000ea12  call    __security_check_cookie
0x18000ea17  lea     rsp, [rbp+48h]
0x18000ea1b  pop     r15
0x18000ea1d  pop     r14
0x18000ea1f  pop     r13
0x18000ea21  pop     r12
0x18000ea23  pop     rdi
0x18000ea24  pop     rsi
0x18000ea25  pop     rbx
0x18000ea26  pop     rbp
0x18000ea27  retn
0x18000ea28  mov     edi, 80070057h
0x18000ea2d  test    esi, esi
0x18000ea2f  jz      short loc_18000EA35
0x18000ea31  mov     [rbx], r13w
0x18000ea35  lea     rax, WPP_GLOBAL_Control
0x18000ea3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea43  cmp     rcx, rax
0x18000ea46  jz      short loc_18000EA66
0x18000ea48  test    byte ptr [rcx+1Ch], 1
0x18000ea4c  jz      short loc_18000EA66
0x18000ea4e  mov     edx, 0Ah
0x18000ea53  mov     r9d, esi
0x18000ea56  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x18000ea5d  mov     rcx, [rcx+10h]
0x18000ea61  call    WPP_SF_d
0x18000ea66  mov     edx, edi; int
0x18000ea68  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000ea6c  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18000ea71  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18000ea78  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000ea7c  call    _CxxThrowException_0
0x18000ea82  mov     [rbp+80h+var_80], 80070216h
0x18000ea89  lea     rdx, _TI1J; pThrowInfo
0x18000ea90  lea     rcx, [rbp+80h+var_80]; pExceptionObject
0x18000ea94  call    _CxxThrowException_0
0x18000ea9a  lea     rax, WPP_GLOBAL_Control
0x18000eaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eaa8  cmp     rcx, rax
0x18000eaab  jz      short loc_18000EAD8
0x18000eaad  test    byte ptr [rcx+1Ch], 1
0x18000eab1  jz      short loc_18000EAD8
0x18000eab3  call    cs:__imp_GetLastError
0x18000eab9  mov     edx, 0Bh
0x18000eabe  mov     r9d, eax
0x18000eac1  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x18000eac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eacf  mov     rcx, [rcx+10h]
0x18000ead3  call    WPP_SF_d
0x18000ead8  call    cs:__imp_GetLastError
0x18000eade  test    eax, eax
0x18000eae0  jle     short loc_18000EAEA
0x18000eae2  movzx   eax, ax
0x18000eae5  or      eax, 80070000h
0x18000eaea  mov     edx, eax; int
0x18000eaec  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000eaf0  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18000eaf5  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18000eafc  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000eb00  call    _CxxThrowException_0
0x18000eb06  lea     rax, WPP_GLOBAL_Control
0x18000eb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb14  cmp     rcx, rax
0x18000eb17  jz      short loc_18000EB3C
0x18000eb19  test    byte ptr [rcx+1Ch], 1
0x18000eb1d  jz      short loc_18000EB3C
0x18000eb1f  mov     edx, 0Ch
0x18000eb24  mov     [rsp+0B0h+var_90], r8d
0x18000eb29  mov     r9d, esi
0x18000eb2c  lea     r8, WPP_45b597e3d7703f55d09231576c0512fb_Traceguids
0x18000eb33  mov     rcx, [rcx+10h]
0x18000eb37  call    WPP_SF_dd
0x18000eb3c  call    cs:__imp_GetLastError
0x18000eb42  test    eax, eax
0x18000eb44  jle     short loc_18000EB4E
0x18000eb46  movzx   eax, ax
0x18000eb49  or      eax, 80070000h
0x18000eb4e  mov     edx, eax; int
0x18000eb50  lea     rcx, [rbp+80h+pExceptionObject]; this
0x18000eb54  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18000eb59  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18000eb60  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18000eb64  call    _CxxThrowException_0
```

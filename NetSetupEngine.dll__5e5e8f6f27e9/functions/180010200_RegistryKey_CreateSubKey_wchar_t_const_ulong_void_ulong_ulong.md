# RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)

- ea: `0x180010200`
- end: `0x180010439`
- name: `?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z`
- size: `569`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `38`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004080`
- `0x18000ee54`
- `0x18000ffb0`
- `0x1800115cc`
- `0x180011614`
- `0x1800163d0`
- `0x180017a48`
- `0x18001c010`
- `0x18001ef74`
- `0x18001f3ec`
- `0x18001fecc`
- `0x18001ff44`
- `0x180024b2c`
- `0x1800274f0`
- `0x180028740`
- `0x180028c28`
- `0x180038b30`
- `0x18003f1bc`
- `0x18003fc90`
- `0x1800418b4`
- `0x18004c4d0`
- `0x18004c830`
- `0x180059848`
- `0x18005e3d8`
- `0x1800612e0`
- `0x1800623a0`
- `0x180062bf8`
- `0x180062d84`
- `0x18006a55c`
- `0x18006a7d8`
- `0x18006a958`
- `0x18006e694`
- `0x18006e9f4`
- `0x1800740a4`
- `0x1800762a0`
- `0x1800787f0`
- `0x18007bd74`
- `0x18007f894`

## callees

- `0x180010200`
- `0x180052620`
- `0x180052698`
- `0x180065035`
- `0x180067750`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800102f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010426`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800102f6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010426`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18001028a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010397`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18001028a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010397`

## pseudocode

```c
HKEY __fastcall RegistryKey::CreateSubKey(
        HKEY *a1,
        HKEY a2,
        const WCHAR *a3,
        REGSAM samDesired,
        HANDLE hTransaction,
        DWORD *lpdwDisposition)
{
  HKEY v7; // r15
  LSTATUS v10; // edi
  LSTATUS v12; // edi
  _BYTE pExceptionObject[208]; // [rsp+68h] [rbp-130h] BYREF
  HKEY phkResult; // [rsp+138h] [rbp-60h] BYREF

  phkResult = a2;
  v7 = *a1;
  phkResult = 0;
  if ( hTransaction )
  {
    v10 = RegCreateKeyTransactedW(v7, a3, 0, 0, 0, samDesired, 0, &phkResult, lpdwDisposition, hTransaction, 0);
    if ( v10 == 5 )
      v10 = RegCreateKeyTransactedW(v7, a3, 0, 0, 4u, samDesired, 0, &phkResult, lpdwDisposition, hTransaction, 0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v10);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v10);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    v12 = RegCreateKeyExW(v7, a3, 0, 0, 0, samDesired, 0, &phkResult, lpdwDisposition);
    if ( v12 == 5 )
      v12 = RegCreateKeyExW(v7, a3, 0, 0, 4u, samDesired, 0, &phkResult, lpdwDisposition);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
          (_DWORD)a3,
          v12);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v12);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  if ( !phkResult )
    Win32Exception::ThrowLastError();
  *(_QWORD *)a2 = phkResult;
  return a2;
}

```

## disassembly

```asm
0x180010200  mov     r11, rsp
0x180010203  push    rbx
0x180010204  push    rbp
0x180010205  push    rsi
0x180010206  push    rdi
0x180010207  push    r12
0x180010209  push    r13
0x18001020b  push    r14
0x18001020d  push    r15
0x18001020f  sub     rsp, 158h
0x180010216  mov     rax, cs:__security_cookie
0x18001021d  xor     rax, rsp
0x180010220  mov     [rsp+198h+var_58], rax
0x180010228  mov     rsi, [rsp+198h+arg_20]
0x180010230  lea     rax, [r11-60h]
0x180010234  mov     r14, [rsp+198h+arg_28]
0x18001023c  mov     r12, r8
0x18001023f  mov     [rsp+198h+var_60], rdx
0x180010247  xor     r13d, r13d
0x18001024a  mov     r15, [rcx]
0x18001024d  mov     ebp, r9d
0x180010250  xor     r9d, r9d; lpClass
0x180010253  mov     [r11-60h], r13
0x180010257  xor     r8d, r8d; Reserved
0x18001025a  mov     rbx, rdx
0x18001025d  mov     rdx, r12; lpSubKey
0x180010260  mov     rcx, r15; hKey
0x180010263  test    rsi, rsi
0x180010266  jz      short loc_1800102DE
0x180010268  mov     [rsp+198h+pExtendedParemeter], r13; pExtendedParemeter
0x18001026d  mov     [rsp+198h+hTransaction], rsi; hTransaction
0x180010272  mov     [rsp+198h+lpdwDisposition], r14; lpdwDisposition
0x180010277  mov     [rsp+198h+phkResult], rax; phkResult
0x18001027c  mov     [rsp+198h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180010281  mov     [rsp+198h+samDesired], ebp; samDesired
0x180010285  mov     [rsp+198h+dwOptions], r13d; dwOptions
0x18001028a  call    cs:__imp_RegCreateKeyTransactedW
0x180010290  mov     edi, eax
0x180010292  cmp     eax, 5
0x180010295  jz      loc_18001035E
0x18001029b  test    edi, edi
0x18001029d  jnz     loc_1800103A4
0x1800102a3  mov     rax, [rsp+198h+var_60]
0x1800102ab  test    rax, rax
0x1800102ae  jz      loc_180010433
0x1800102b4  mov     [rbx], rax
0x1800102b7  mov     rax, rbx
0x1800102ba  mov     rcx, [rsp+198h+var_58]
0x1800102c2  xor     rcx, rsp; StackCookie
0x1800102c5  call    __security_check_cookie
0x1800102ca  add     rsp, 158h
0x1800102d1  pop     r15
0x1800102d3  pop     r14
0x1800102d5  pop     r13
0x1800102d7  pop     r12
0x1800102d9  pop     rdi
0x1800102da  pop     rsi
0x1800102db  pop     rbp
0x1800102dc  pop     rbx
0x1800102dd  retn
0x1800102de  mov     [rsp+198h+lpdwDisposition], r14; lpdwDisposition
0x1800102e3  mov     [rsp+198h+phkResult], rax; phkResult
0x1800102e8  mov     [rsp+198h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800102ed  mov     [rsp+198h+samDesired], ebp; samDesired
0x1800102f1  mov     [rsp+198h+dwOptions], r13d; dwOptions
0x1800102f6  call    cs:__imp_RegCreateKeyExW
0x1800102fc  mov     edi, eax
0x1800102fe  cmp     eax, 5
0x180010301  jz      loc_1800103F7
0x180010307  test    edi, edi
0x180010309  jz      short loc_1800102A3
0x18001030b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010312  lea     rax, WPP_GLOBAL_Control
0x180010319  cmp     rcx, rax
0x18001031c  jz      short loc_180010340
0x18001031e  cmp     byte ptr [rcx+19h], 2
0x180010322  jb      short loc_180010340
0x180010324  mov     rcx, [rcx+10h]
0x180010328  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18001032f  mov     edx, 10h
0x180010334  mov     [rsp+198h+dwOptions], edi
0x180010338  mov     r9, r12
0x18001033b  call    WPP_SF_Sd
0x180010340  mov     edx, edi; int
0x180010342  lea     rcx, [rsp+198h+pExceptionObject]; this
0x180010347  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18001034c  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010353  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180010358  call    _CxxThrowException_0
0x18001035e  mov     [rsp+198h+pExtendedParemeter], r13; pExtendedParemeter
0x180010363  lea     rax, [rsp+198h+var_60]
0x18001036b  mov     [rsp+198h+hTransaction], rsi; hTransaction
0x180010370  xor     r9d, r9d; lpClass
0x180010373  mov     [rsp+198h+lpdwDisposition], r14; lpdwDisposition
0x180010378  xor     r8d, r8d; Reserved
0x18001037b  mov     [rsp+198h+phkResult], rax; phkResult
0x180010380  mov     rdx, r12; lpSubKey
0x180010383  mov     [rsp+198h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180010388  mov     rcx, r15; hKey
0x18001038b  mov     [rsp+198h+samDesired], ebp; samDesired
0x18001038f  mov     [rsp+198h+dwOptions], 4; dwOptions
0x180010397  call    cs:__imp_RegCreateKeyTransactedW
0x18001039d  mov     edi, eax
0x18001039f  jmp     loc_18001029B
0x1800103a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103ab  lea     rax, WPP_GLOBAL_Control
0x1800103b2  cmp     rcx, rax
0x1800103b5  jz      short loc_1800103D9
0x1800103b7  cmp     byte ptr [rcx+19h], 2
0x1800103bb  jb      short loc_1800103D9
0x1800103bd  mov     rcx, [rcx+10h]
0x1800103c1  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800103c8  mov     edx, 0Fh
0x1800103cd  mov     [rsp+198h+dwOptions], edi
0x1800103d1  mov     r9, r12
0x1800103d4  call    WPP_SF_Sd
0x1800103d9  mov     edx, edi; int
0x1800103db  lea     rcx, [rsp+198h+pExceptionObject]; this
0x1800103e0  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800103e5  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800103ec  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x1800103f1  call    _CxxThrowException_0
0x1800103f7  mov     [rsp+198h+lpdwDisposition], r14; lpdwDisposition
0x1800103fc  lea     rax, [rsp+198h+var_60]
0x180010404  mov     [rsp+198h+phkResult], rax; phkResult
0x180010409  xor     r9d, r9d; lpClass
0x18001040c  mov     [rsp+198h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180010411  xor     r8d, r8d; Reserved
0x180010414  mov     [rsp+198h+samDesired], ebp; samDesired
0x180010418  mov     rdx, r12; lpSubKey
0x18001041b  mov     rcx, r15; hKey
0x18001041e  mov     [rsp+198h+dwOptions], 4; dwOptions
0x180010426  call    cs:__imp_RegCreateKeyExW
0x18001042c  mov     edi, eax
0x18001042e  jmp     loc_180010307
0x180010433  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
```

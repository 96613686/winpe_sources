# CComObjectRegistrationT<CEmptyType>::Unregister(void)

- ea: `0x180016d34`
- end: `0x180016f69`
- name: `?Unregister@?$CComObjectRegistrationT@VCEmptyType@@@@QEAAJXZ`
- size: `565`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015864`
- `0x1800178d8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c238`
- `0x180011e90`
- `0x1800128c4`
- `0x180016d34`
- `0x180022944`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f3c`
- `RPCRT4!UuidToStringW` at `0x180016e2b`
- `RPCRT4!UuidToStringW` at `0x180016e2b`
- `RPCRT4!RpcStringFreeW` at `0x180016f29`
- `RPCRT4!RpcStringFreeW` at `0x180016f29`

## string_xrefs

- `0x180016ea1`: `CLSID\{%s}`

## pseudocode

```c
__int64 __fastcall CComObjectRegistrationT<CEmptyType>::Unregister(int *a1)
{
  int v1; // edx
  WCHAR *v2; // rsi
  bool v4; // zf
  int v5; // ebx
  __int64 v6; // rcx
  const WCHAR *v7; // r14
  int v8; // eax
  const WCHAR *v9; // r14
  int v10; // eax
  int v11; // ecx
  const wchar_t *v12; // rbx
  int appended; // eax
  __int64 v14; // rcx
  int v15; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-10h] BYREF
  RPC_WSTR String; // [rsp+60h] [rbp+30h] BYREF
  RPC_WSTR StringUuid; // [rsp+68h] [rbp+38h] BYREF

  v1 = *a1;
  v2 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  StringUuid = 0;
  if ( v1 )
  {
    v4 = v1 == 1;
  }
  else
  {
    v12 = (const wchar_t *)*((_QWORD *)a1 + 9);
    if ( !v12 )
      goto LABEL_21;
    if ( !wcscmp_0(*((const wchar_t **)a1 + 9), L"Apartment") || !wcscmp_0(v12, L"Free") )
      goto LABEL_4;
    v4 = wcscmp_0(v12, L"Both") == 0;
  }
  if ( !v4 )
  {
LABEL_21:
    v5 = -2147418113;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147418113);
    goto LABEL_5;
  }
LABEL_4:
  v5 = 0;
LABEL_5:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
    goto LABEL_32;
  v7 = (const WCHAR *)*((_QWORD *)a1 + 6);
  if ( v7 )
  {
    LODWORD(String) = 0;
    v8 = CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(v6, v7, (int *)&String);
    v5 = v8;
    if ( v8 < 0
      || (_DWORD)String
      && (v8 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY_CLASSES_ROOT, v7), v5 = v8, v8 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
    if ( v5 < 0 )
      goto LABEL_32;
  }
  v9 = (const WCHAR *)*((_QWORD *)a1 + 7);
  if ( v9 )
  {
    LODWORD(String) = 0;
    v10 = CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(v6, v9, (int *)&String);
    v5 = v10;
    if ( v10 < 0
      || (_DWORD)String
      && (v10 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY_CLASSES_ROOT, v9), v5 = v10, v10 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
    if ( v5 < 0 )
      goto LABEL_32;
  }
  if ( UuidToStringW((const UUID *)(a1 + 1), &StringUuid) )
  {
    v5 = -2147418113;
    v11 = -2147418113;
LABEL_33:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    goto LABEL_34;
  }
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)lpMem,
               L"CLSID\\{%s}",
               StringUuid);
  v5 = appended;
  if ( appended < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(appended);
    v2 = (WCHAR *)lpMem[0];
    goto LABEL_34;
  }
  v2 = (WCHAR *)lpMem[0];
  LODWORD(String) = 0;
  v15 = CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(v14, (const WCHAR *)lpMem[0], (int *)&String);
  v5 = v15;
  if ( v15 < 0
    || (_DWORD)String
    && (v15 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY_CLASSES_ROOT, v2), v5 = v15, v15 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
  {
LABEL_32:
    v11 = v5;
    goto LABEL_33;
  }
LABEL_34:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( StringUuid )
  {
    String = StringUuid;
    RpcStringFreeW(&String);
    StringUuid = 0;
  }
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016d34  mov     [rsp-28h+arg_10], rbx
0x180016d39  mov     [rsp-28h+arg_18], rsi
0x180016d3e  push    rbp
0x180016d3f  push    rdi
0x180016d40  push    r12
0x180016d42  push    r13
0x180016d44  push    r14
0x180016d46  mov     rbp, rsp
0x180016d49  sub     rsp, 30h
0x180016d4d  mov     edx, [rcx]
0x180016d4f  xor     esi, esi
0x180016d51  mov     [rbp+lpMem], rsi
0x180016d55  mov     rdi, rcx
0x180016d58  mov     [rbp+var_8], rsi
0x180016d5c  mov     r12d, 8000FFFFh
0x180016d62  mov     [rbp+StringUuid], rsi
0x180016d66  test    edx, edx
0x180016d68  jz      loc_180016E40
0x180016d6e  cmp     edx, 1
0x180016d71  jnz     loc_180016E49
0x180016d77  xor     ebx, ebx
0x180016d79  mov     ecx, ebx
0x180016d7b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016d80  test    ebx, ebx
0x180016d82  js      loc_180016F0A
0x180016d88  mov     r14, [rdi+30h]
0x180016d8c  mov     r13, 0FFFFFFFF80000000h
0x180016d93  test    r14, r14
0x180016d96  jz      short loc_180016DD9
0x180016d98  lea     r8, [rbp+String]
0x180016d9c  mov     dword ptr [rbp+String], esi
0x180016d9f  mov     rdx, r14
0x180016da2  call    ?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z; CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)
0x180016da7  mov     ebx, eax
0x180016da9  test    eax, eax
0x180016dab  js      short loc_180016DC3
0x180016dad  cmp     dword ptr [rbp+String], esi
0x180016db0  jz      short loc_180016DCA
0x180016db2  mov     rdx, r14
0x180016db5  mov     rcx, r13
0x180016db8  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180016dbd  mov     ebx, eax
0x180016dbf  test    eax, eax
0x180016dc1  jns     short loc_180016DCA
0x180016dc3  mov     ecx, eax
0x180016dc5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016dca  mov     ecx, ebx
0x180016dcc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016dd1  test    ebx, ebx
0x180016dd3  js      loc_180016F0A
0x180016dd9  mov     r14, [rdi+38h]
0x180016ddd  test    r14, r14
0x180016de0  jz      short loc_180016E23
0x180016de2  lea     r8, [rbp+String]
0x180016de6  mov     dword ptr [rbp+String], esi
0x180016de9  mov     rdx, r14
0x180016dec  call    ?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z; CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)
0x180016df1  mov     ebx, eax
0x180016df3  test    eax, eax
0x180016df5  js      short loc_180016E0D
0x180016df7  cmp     dword ptr [rbp+String], esi
0x180016dfa  jz      short loc_180016E14
0x180016dfc  mov     rdx, r14
0x180016dff  mov     rcx, r13
0x180016e02  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180016e07  mov     ebx, eax
0x180016e09  test    eax, eax
0x180016e0b  jns     short loc_180016E14
0x180016e0d  mov     ecx, eax
0x180016e0f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016e14  mov     ecx, ebx
0x180016e16  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016e1b  test    ebx, ebx
0x180016e1d  js      loc_180016F0A
0x180016e23  lea     rcx, [rdi+4]; Uuid
0x180016e27  lea     rdx, [rbp+StringUuid]; StringUuid
0x180016e2b  call    cs:__imp_UuidToStringW
0x180016e31  test    eax, eax
0x180016e33  jz      short loc_180016E9D
0x180016e35  mov     ebx, r12d
0x180016e38  mov     ecx, r12d
0x180016e3b  jmp     loc_180016F0C
0x180016e40  mov     rbx, [rcx+48h]
0x180016e44  test    rbx, rbx
0x180016e47  jnz     short loc_180016E59
0x180016e49  mov     ecx, r12d
0x180016e4c  mov     ebx, r12d
0x180016e4f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016e54  jmp     loc_180016D79
0x180016e59  lea     rdx, aApartment; "Apartment"
0x180016e60  mov     rcx, rbx; String1
0x180016e63  call    wcscmp_0
0x180016e68  test    eax, eax
0x180016e6a  jz      loc_180016D77
0x180016e70  lea     rdx, aFree; "Free"
0x180016e77  mov     rcx, rbx; String1
0x180016e7a  call    wcscmp_0
0x180016e7f  test    eax, eax
0x180016e81  jz      loc_180016D77
0x180016e87  lea     rdx, aBoth; "Both"
0x180016e8e  mov     rcx, rbx; String1
0x180016e91  call    wcscmp_0
0x180016e96  test    eax, eax
0x180016e98  jmp     loc_180016D71
0x180016e9d  mov     r8, [rbp+StringUuid]
0x180016ea1  lea     rdx, aClsidS_0; "CLSID\\{%s}"
0x180016ea8  lea     rcx, [rbp+lpMem]
0x180016eac  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180016eb1  mov     ebx, eax
0x180016eb3  test    eax, eax
0x180016eb5  jns     short loc_180016EC4
0x180016eb7  mov     ecx, eax
0x180016eb9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016ebe  mov     rsi, [rbp+lpMem]
0x180016ec2  jmp     short loc_180016F11
0x180016ec4  mov     rsi, [rbp+lpMem]
0x180016ec8  lea     r8, [rbp+String]
0x180016ecc  mov     rdx, rsi
0x180016ecf  mov     dword ptr [rbp+String], 0
0x180016ed6  call    ?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z; CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)
0x180016edb  mov     ebx, eax
0x180016edd  test    eax, eax
0x180016edf  js      short loc_180016EF8
0x180016ee1  cmp     dword ptr [rbp+String], 0
0x180016ee5  jz      short loc_180016EFF
0x180016ee7  mov     rdx, rsi
0x180016eea  mov     rcx, r13
0x180016eed  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180016ef2  mov     ebx, eax
0x180016ef4  test    eax, eax
0x180016ef6  jns     short loc_180016EFF
0x180016ef8  mov     ecx, eax
0x180016efa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016eff  mov     ecx, ebx
0x180016f01  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016f06  test    ebx, ebx
0x180016f08  jns     short loc_180016F11
0x180016f0a  mov     ecx, ebx
0x180016f0c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016f11  mov     ecx, ebx
0x180016f13  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016f18  mov     rax, [rbp+StringUuid]
0x180016f1c  test    rax, rax
0x180016f1f  jz      short loc_180016F37
0x180016f21  lea     rcx, [rbp+String]; String
0x180016f25  mov     [rbp+String], rax
0x180016f29  call    cs:__imp_RpcStringFreeW
0x180016f2f  mov     [rbp+StringUuid], 0
0x180016f37  test    rsi, rsi
0x180016f3a  jz      short loc_180016F50
0x180016f3c  call    cs:__imp_GetProcessHeap
0x180016f42  mov     r8, rsi; lpMem
0x180016f45  xor     edx, edx; dwFlags
0x180016f47  mov     rcx, rax; hHeap
0x180016f4a  call    cs:__imp_HeapFree
0x180016f50  mov     rsi, [rsp+30h+arg_18]
0x180016f55  mov     eax, ebx
0x180016f57  mov     rbx, [rsp+30h+arg_10]
0x180016f5c  add     rsp, 30h
0x180016f60  pop     r14
0x180016f62  pop     r13
0x180016f64  pop     r12
0x180016f66  pop     rdi
0x180016f67  pop     rbp
0x180016f68  retn
```

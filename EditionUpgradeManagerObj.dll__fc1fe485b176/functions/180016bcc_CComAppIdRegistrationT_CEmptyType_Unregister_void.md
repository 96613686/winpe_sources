# CComAppIdRegistrationT<CEmptyType>::Unregister(void)

- ea: `0x180016bcc`
- end: `0x180016d2b`
- name: `?Unregister@?$CComAppIdRegistrationT@VCEmptyType@@@@QEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800156d0`
- `0x1800178d8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c238`
- `0x180011e90`
- `0x1800128c4`
- `0x180016bcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016d13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016c64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016d04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016c64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016d04`

## pseudocode

```c
__int64 __fastcall CComAppIdRegistrationT<CEmptyType>::Unregister(__int64 *a1)
{
  __int64 v1; // r8
  int appended; // eax
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // ecx
  int v7; // eax
  HANDLE ProcessHeap; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // eax
  HANDLE v12; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+28h] [rbp-8h]
  int v16; // [rsp+40h] [rbp+10h] BYREF

  v1 = *a1;
  lpMem = 0;
  v15 = 0;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)&lpMem,
               L"AppID\\%s",
               v1);
  v5 = appended;
  if ( appended < 0 )
  {
LABEL_2:
    v6 = appended;
LABEL_17:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_18;
  }
  v16 = 0;
  v7 = CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(v4, (const WCHAR *)lpMem, &v16);
  v5 = v7;
  if ( v7 < 0
    || v16
    && (v7 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY_CLASSES_ROOT, (const WCHAR *)lpMem),
        v5 = v7,
        v7 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
    goto LABEL_16;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    lpMem = 0;
  }
  v9 = a1[2];
  v15 = 0;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)&lpMem,
               L"AppID\\%s",
               v9);
  v5 = appended;
  if ( appended < 0 )
    goto LABEL_2;
  v16 = 0;
  v11 = CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(v10, (const WCHAR *)lpMem, &v16);
  v5 = v11;
  if ( v11 < 0
    || v16
    && (v11 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY_CLASSES_ROOT, (const WCHAR *)lpMem),
        v5 = v11,
        v11 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
  {
LABEL_16:
    v6 = v5;
    goto LABEL_17;
  }
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( lpMem )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, lpMem);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016bcc  mov     [rsp-8+arg_8], rbx
0x180016bd1  mov     [rsp-8+arg_10], rsi
0x180016bd6  push    rbp
0x180016bd7  mov     rbp, rsp
0x180016bda  sub     rsp, 30h
0x180016bde  mov     r8, [rcx]
0x180016be1  lea     rdx, aAppidS; "AppID\\%s"
0x180016be8  mov     rsi, rcx
0x180016beb  mov     [rbp+lpMem], 0
0x180016bf3  lea     rcx, [rbp+lpMem]
0x180016bf7  mov     [rbp+var_8], 0
0x180016bff  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180016c04  mov     ebx, eax
0x180016c06  test    eax, eax
0x180016c08  jns     short loc_180016C11
0x180016c0a  mov     ecx, eax
0x180016c0c  jmp     loc_180016CF1
0x180016c11  mov     rdx, [rbp+lpMem]
0x180016c15  lea     r8, [rbp+arg_0]
0x180016c19  mov     [rbp+arg_0], 0
0x180016c20  call    ?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z; CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)
0x180016c25  mov     ebx, eax
0x180016c27  test    eax, eax
0x180016c29  js      short loc_180016C47
0x180016c2b  cmp     [rbp+arg_0], 0
0x180016c2f  jz      short loc_180016C4E
0x180016c31  mov     rdx, [rbp+lpMem]
0x180016c35  mov     rcx, 0FFFFFFFF80000000h
0x180016c3c  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180016c41  mov     ebx, eax
0x180016c43  test    eax, eax
0x180016c45  jns     short loc_180016C4E
0x180016c47  mov     ecx, eax
0x180016c49  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016c4e  mov     ecx, ebx
0x180016c50  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016c55  test    ebx, ebx
0x180016c57  js      loc_180016CEF
0x180016c5d  cmp     [rbp+lpMem], 0
0x180016c62  jz      short loc_180016C81
0x180016c64  call    cs:__imp_GetProcessHeap
0x180016c6a  mov     r8, [rbp+lpMem]; lpMem
0x180016c6e  xor     edx, edx; dwFlags
0x180016c70  mov     rcx, rax; hHeap
0x180016c73  call    cs:__imp_HeapFree
0x180016c79  mov     [rbp+lpMem], 0
0x180016c81  mov     r8, [rsi+10h]
0x180016c85  lea     rdx, aAppidS; "AppID\\%s"
0x180016c8c  lea     rcx, [rbp+lpMem]
0x180016c90  mov     [rbp+var_8], 0
0x180016c98  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180016c9d  mov     ebx, eax
0x180016c9f  test    eax, eax
0x180016ca1  js      loc_180016C0A
0x180016ca7  mov     rdx, [rbp+lpMem]
0x180016cab  lea     r8, [rbp+arg_0]
0x180016caf  mov     [rbp+arg_0], 0
0x180016cb6  call    ?KeyExists@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBGPEAH@Z; CRegUtilT<CEmptyType,CRegType,0,0>::KeyExists(HKEY__ *,ushort const *,int *)
0x180016cbb  mov     ebx, eax
0x180016cbd  test    eax, eax
0x180016cbf  js      short loc_180016CDD
0x180016cc1  cmp     [rbp+arg_0], 0
0x180016cc5  jz      short loc_180016CE4
0x180016cc7  mov     rdx, [rbp+lpMem]
0x180016ccb  mov     rcx, 0FFFFFFFF80000000h
0x180016cd2  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180016cd7  mov     ebx, eax
0x180016cd9  test    eax, eax
0x180016cdb  jns     short loc_180016CE4
0x180016cdd  mov     ecx, eax
0x180016cdf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016ce4  mov     ecx, ebx
0x180016ce6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016ceb  test    ebx, ebx
0x180016ced  jns     short loc_180016CF6
0x180016cef  mov     ecx, ebx
0x180016cf1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016cf6  mov     ecx, ebx
0x180016cf8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016cfd  cmp     [rbp+lpMem], 0
0x180016d02  jz      short loc_180016D19
0x180016d04  call    cs:__imp_GetProcessHeap
0x180016d0a  mov     r8, [rbp+lpMem]; lpMem
0x180016d0e  xor     edx, edx; dwFlags
0x180016d10  mov     rcx, rax; hHeap
0x180016d13  call    cs:__imp_HeapFree
0x180016d19  mov     rsi, [rsp+30h+arg_10]
0x180016d1e  mov     eax, ebx
0x180016d20  mov     rbx, [rsp+30h+arg_8]
0x180016d25  add     rsp, 30h
0x180016d29  pop     rbp
0x180016d2a  retn
```

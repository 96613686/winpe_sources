# CComAppIdRegistrationT<CEmptyType>::Register(void)

- ea: `0x1800156d0`
- end: `0x18001585b`
- name: `?Register@?$CComAppIdRegistrationT@VCEmptyType@@@@QEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800178d8`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c0cc`
- `0x18000c45c`
- `0x180011e90`
- `0x1800127a0`
- `0x1800156d0`
- `0x180016bcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001578f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015849`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001578f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015849`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001583b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001583b`

## pseudocode

```c
__int64 __fastcall CComAppIdRegistrationT<CEmptyType>::Register(_QWORD *a1)
{
  int appended; // eax
  int v3; // ebx
  int v4; // ecx
  __int64 v5; // rcx
  _WORD *v6; // r14
  int PointerDataSize; // eax
  __int64 v8; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  _WORD *v12; // rdi
  int v13; // eax
  __int64 v14; // rcx
  void *v15; // rdi
  HANDLE v16; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-18h] BYREF
  __int64 v19; // [rsp+38h] [rbp-10h]
  int v20; // [rsp+78h] [rbp+30h] BYREF

  lpMem = 0;
  v19 = 0;
  appended = CComAppIdRegistrationT<CEmptyType>::Unregister();
  v3 = appended;
  if ( appended < 0 )
    goto LABEL_2;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)&lpMem,
               L"AppID\\%s",
               *a1);
  v3 = appended;
  if ( appended < 0 )
    goto LABEL_2;
  appended = CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(v5, (const WCHAR *)lpMem);
  v3 = appended;
  if ( appended < 0 )
    goto LABEL_2;
  v6 = (_WORD *)a1[1];
  v20 = 0;
  PointerDataSize = CRegType<unsigned short *>::GetPointerDataSize(v6, &v20);
  v3 = PointerDataSize;
  if ( PointerDataSize < 0
    || (PointerDataSize = CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(v8, lpMem, 0, v6, v20),
        v3 = PointerDataSize,
        PointerDataSize < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(PointerDataSize);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v3 < 0 )
    goto LABEL_17;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    lpMem = 0;
  }
  v10 = a1[2];
  v19 = 0;
  appended = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::AppendFormat(
               (__int64)&lpMem,
               L"AppID\\%s",
               v10);
  v3 = appended;
  if ( appended < 0
    || (appended = CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(v11, (const WCHAR *)lpMem),
        v3 = appended,
        appended < 0) )
  {
LABEL_2:
    v4 = appended;
LABEL_18:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_19;
  }
  v12 = (_WORD *)*a1;
  v20 = 0;
  v13 = CRegType<unsigned short *>::GetPointerDataSize(v12, &v20);
  v3 = v13;
  if ( v13 < 0
    || (v13 = CRegUtilT<unsigned short *,CRegType,0,0>::SetValue(v14, lpMem, L"AppID", v12, v20), v3 = v13, v13 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v3 < 0 )
  {
LABEL_17:
    v4 = v3;
    goto LABEL_18;
  }
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  v15 = lpMem;
  if ( lpMem )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800156d0  push    rbp
0x1800156d2  push    rbx
0x1800156d3  push    rdi
0x1800156d4  push    r14
0x1800156d6  mov     rbp, rsp
0x1800156d9  sub     rsp, 48h
0x1800156dd  mov     rdi, rcx
0x1800156e0  mov     [rbp+lpMem], 0
0x1800156e8  mov     [rbp+var_10], 0
0x1800156f0  call    ?Unregister@?$CComAppIdRegistrationT@VCEmptyType@@@@QEAAJXZ; CComAppIdRegistrationT<CEmptyType>::Unregister(void)
0x1800156f5  mov     ebx, eax
0x1800156f7  test    eax, eax
0x1800156f9  jns     short loc_180015702
0x1800156fb  mov     ecx, eax
0x1800156fd  jmp     loc_180015826
0x180015702  mov     r8, [rdi]
0x180015705  lea     rdx, aAppidS; "AppID\\%s"
0x18001570c  lea     rcx, [rbp+lpMem]
0x180015710  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x180015715  mov     ebx, eax
0x180015717  test    eax, eax
0x180015719  js      short loc_1800156FB
0x18001571b  mov     rdx, [rbp+lpMem]
0x18001571f  call    ?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x180015724  mov     ebx, eax
0x180015726  test    eax, eax
0x180015728  js      short loc_1800156FB
0x18001572a  mov     r14, [rdi+8]
0x18001572e  lea     rdx, [rbp+arg_8]
0x180015732  mov     rcx, r14
0x180015735  mov     [rbp+arg_8], 0
0x18001573c  call    ?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z; CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)
0x180015741  mov     ebx, eax
0x180015743  test    eax, eax
0x180015745  js      short loc_180015763
0x180015747  mov     eax, [rbp+arg_8]
0x18001574a  mov     r9, r14
0x18001574d  mov     rdx, [rbp+lpMem]
0x180015751  xor     r8d, r8d
0x180015754  mov     [rsp+48h+var_28], eax
0x180015758  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z; CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18001575d  mov     ebx, eax
0x18001575f  test    eax, eax
0x180015761  jns     short loc_18001576A
0x180015763  mov     ecx, eax
0x180015765  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001576a  mov     ecx, ebx
0x18001576c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180015771  test    ebx, ebx
0x180015773  js      loc_180015824
0x180015779  cmp     [rbp+lpMem], 0
0x18001577e  jz      short loc_18001579D
0x180015780  call    cs:__imp_GetProcessHeap
0x180015786  mov     r8, [rbp+lpMem]; lpMem
0x18001578a  xor     edx, edx; dwFlags
0x18001578c  mov     rcx, rax; hHeap
0x18001578f  call    cs:__imp_HeapFree
0x180015795  mov     [rbp+lpMem], 0
0x18001579d  mov     r8, [rdi+10h]
0x1800157a1  lea     rdx, aAppidS; "AppID\\%s"
0x1800157a8  lea     rcx, [rbp+lpMem]
0x1800157ac  mov     [rbp+var_10], 0
0x1800157b4  call    ?AppendFormat@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBGZZ; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::AppendFormat(ushort const *,...)
0x1800157b9  mov     ebx, eax
0x1800157bb  test    eax, eax
0x1800157bd  js      loc_1800156FB
0x1800157c3  mov     rdx, [rbp+lpMem]
0x1800157c7  call    ?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)
0x1800157cc  mov     ebx, eax
0x1800157ce  test    eax, eax
0x1800157d0  js      loc_1800156FB
0x1800157d6  mov     rdi, [rdi]
0x1800157d9  lea     rdx, [rbp+arg_8]
0x1800157dd  mov     rcx, rdi
0x1800157e0  mov     [rbp+arg_8], 0
0x1800157e7  call    ?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z; CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)
0x1800157ec  mov     ebx, eax
0x1800157ee  test    eax, eax
0x1800157f0  js      short loc_180015812
0x1800157f2  mov     eax, [rbp+arg_8]
0x1800157f5  lea     r8, aAppid; "AppID"
0x1800157fc  mov     rdx, [rbp+lpMem]
0x180015800  mov     r9, rdi
0x180015803  mov     [rsp+48h+var_28], eax
0x180015807  call    ?SetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG11K@Z; CRegUtilT<ushort *,CRegType,0,0>::SetValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18001580c  mov     ebx, eax
0x18001580e  test    eax, eax
0x180015810  jns     short loc_180015819
0x180015812  mov     ecx, eax
0x180015814  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180015819  mov     ecx, ebx
0x18001581b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180015820  test    ebx, ebx
0x180015822  jns     short loc_18001582B
0x180015824  mov     ecx, ebx
0x180015826  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001582b  mov     ecx, ebx
0x18001582d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180015832  mov     rdi, [rbp+lpMem]
0x180015836  test    rdi, rdi
0x180015839  jz      short loc_18001584F
0x18001583b  call    cs:__imp_GetProcessHeap
0x180015841  mov     r8, rdi; lpMem
0x180015844  xor     edx, edx; dwFlags
0x180015846  mov     rcx, rax; hHeap
0x180015849  call    cs:__imp_HeapFree
0x18001584f  mov     eax, ebx
0x180015851  add     rsp, 48h
0x180015855  pop     r14
0x180015857  pop     rdi
0x180015858  pop     rbx
0x180015859  pop     rbp
0x18001585a  retn
```
